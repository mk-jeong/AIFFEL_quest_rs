# AIFFEL Campus Online Code Peer Review Templete
- 코더 : 정민규
- 리뷰어 : 송세미


# PRT(Peer Review Template)
- [X]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - SentencePiece 과정- 코퍼스 분석(길이 분포 확인), 전처리, SentencePiece 학습, 토크나이저 구현까지 전 과정을 누락 없이 보여줌.

    - 모델 결합 및 성능- SentencePiece 토크나이저를 적용한 모델이 정상적으로 학습되고 특히 BiLSTM 모델에서 Test Accuracy가 약 84.62%를 기록하며 80%을 넘음.

    - 다각도 분석- 동일한 토크나이저 조건에서 단방향 LSTM과 양방향 LSTM(BiLSTM) 모델의 구조적 차이에 따른 성능 변화를 비교 분석하여 모델 선택의 근거를 실험적으로 제시했다.
      <img width="339" height="115" alt="image" src="https://github.com/user-attachments/assets/0d332f54-7cb3-4955-a622-4ed2a83181fc" />

    
- [X]  **2. 전체 코드에서 가장 핵심적이거나 가장 복잡하고 이해하기 어려운 부분에 작성된 
주석 또는 doc string을 보고 해당 코드가 잘 이해되었나요?**
    - SentencePiece tokenize 함수정의 라는 주석 아래에 있는 spm_tokenize 함수 정의 구간이 핵심적임. SentencePiece 모델 학습부터 인덱스 변환, 딥러닝 모델 입력의 마지막 관문인 pad_sequences 처리까지 한 번에 수행하는 통합 함수다. 전처리된 텍스트가 어떻게 최종적인 Tensor 데이터로 변환되는지 결정짓는 가장 복잡하고 중요한 부분임을 보여줌.
    - 작동원리는 spm.SentencePieceTrainer.Train: 텍스트 파일을 읽어 서브워드 사전 생성 -> sp.Load: 생성된 모델 파일을 불러와 프로세서 객체를 초기화함. -> sp.EncodeAsIds: 자연어를 정수 인덱스로 인코딩함. -> tf.keras.preprocessing.sequence.pad_sequences: 서로 다른 문장 길이를 맞춰 모델 입력을 완성함. 이렇게 이해했다.
    - for idx, line in enumerate(vocab): 루프 내부에서 탭(\t)을 기준으로 단어와 인덱스를 분리하여 딕셔너리를 업데이트하는 로직에 주석이 잘 달려 있어, SentencePiece가 내부적으로 사전을 어떻게 관리하고 이를 모델에서 어떻게 활용하는지 그 작동 원리를 직관적으로 이해했다. 마지막에 padding='post'를 적용하여 데이터의 형상을 맞추는 부분까지 완결성을 보여준다.
        <img width="619" height="457" alt="image" src="https://github.com/user-attachments/assets/7c9f83ac-a4a7-4b5c-a5b1-45b7654d8d4d" />

        
- [X]  **3. 에러가 난 부분을 디버깅하여 문제를 해결한 기록을 남겼거나
새로운 시도 또는 추가 실험을 수행해봤나요?**
    - 매우 꼼꼼하게 수행되었다. 모델의 과적합을 방지하고 성능을 안정화하기 위해 Dropout(0.5)을 적용한 LSTM 모델을 설계한걸로 보여준다. word_vector_dim을 128, lstm_cnt를 128로 설정하여 충분한 파라미터를 확보함으로써 자연어의 복잡한 특징을 학습하려 시도했다. 모델 성능을 높이기 위해 단순 LSTM 구조에서 Bidirectional LSTM 구조로 변경하여 실험을 수행했고, 결과적으로 Test Accuracy를 ~85%까지 끌어올렸다.
    - <img width="920" height="560" alt="image" src="https://github.com/user-attachments/assets/1441fee4-4e32-4ead-8db0-a597ae8f82a8" />

- [X]  **4. 회고를 잘 작성했나요?**
    - 잘 작성했다. 실험군(SentencePiece)과 대조군의 결과를 비교하며 느낀 점, 서브워드 토크나이징이 한국어에서 가지는 이점과 한계점에 대해 기술되어있다.
      <img width="1338" height="353" alt="image" src="https://github.com/user-attachments/assets/7a5c5131-23a4-4a3b-97ef-e22375d4c4a4" />

      <img width="1365" height="164" alt="image" src="https://github.com/user-attachments/assets/fb942daf-7736-4b2f-b01b-e6a8fe7d5860" />

        
- [X]  **5. 코드가 간결하고 효율적인가요?**
    - SentencePiece 학습, 인코딩, 패딩 처리를 각각 분산하지 않고 sp_tokenize(s, corpus) 하나의 함수로 통합하여 코드 재사용성을 높임.
      <img width="647" height="443" alt="image" src="https://github.com/user-attachments/assets/2a134474-4214-452e-93ec-13ec1ab227bd" />
 

# 회고(참고 링크 및 코드 개선)
```
SentencePiece를 활용하여 한국어 형태소 분석기의 한계를 넘어서, 실제 모델 학습까지 매우 안정적으로 구현된 사례였다. sp_tokenize 함수를 통해 전처리 과정을 하나로 묶은 모듈화 능력이 돋보였습니다.

리뷰를 통해 배운 점은 SentencePiece 모델 학습 후 생성되는 .vocab 파일을 직접 파싱하여 word_index를 구축하는 방식이었습니다. 이를 통해 토크나이저 내부 동작 원리를 명확히 이해할 수 있었다. 다만, LSTM 모델의 성능을 극대화하기 위해 패딩(padding)의 위치를 조정하거나 데이터 유실을 줄이는 사소한 개선이 더해진다면 더 완벽한 프로젝트가 될 것 같습니다.

TensorFlow Padding 공식 문서(https://www.tensorflow.org/api_docs/python/tf/keras/utils/pad_sequences)- padding='pre'가 RNN(LSTM) 모델의 성능(기울기 소실 방지)에 왜 더 유리한지 확인하기 위해 참고했음

```
