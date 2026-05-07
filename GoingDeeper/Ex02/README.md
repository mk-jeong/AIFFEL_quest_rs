# AIFFEL Campus Online Code Peer Review Templete
- 코더 : 정민규
- 리뷰어 : 정주열

# PRT(Peer Review Template)
- [x]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - 문제에서 요구하는 최종 결과물이 첨부되었는지 확인
        - RetinaNet 모델 학습과 학습한 모델로 추론 후 Go/Stop 판단까지 모두 잘 진행되었습니다.
    <img width="777" height="319" alt="image" src="https://github.com/user-attachments/assets/d93782e3-7e2d-4555-9c5b-bc73b90ec8b9" />
    <img width="771" height="276" alt="image" src="https://github.com/user-attachments/assets/d454aaf8-b6ba-40e1-97e6-4c57a2e653e8" />

- [x]  **2. 전체 코드에서 가장 핵심적이거나 가장 복잡하고 이해하기 어려운 부분에 작성된 
주석 또는 doc string을 보고 해당 코드가 잘 이해되었나요?**
    - 해당 코드 블럭을 왜 핵심적이라고 생각하는지 확인
    - 해당 코드 블럭에 doc string/annotation이 달려 있는지 확인
    - 해당 코드의 기능, 존재 이유, 작동 원리 등을 기술했는지 확인
    - 주석을 보고 코드 이해가 잘 되었는지 확인
        - RetinaNet 모델 구성하는 부분이 복잡하고, 어려웠는데 Loss 구성이나 모델 구성하는 부분이 주석이 자세히 설명되어 있어서 이해하기 쉬웠습니다.
    <img width="676" height="634" alt="image" src="https://github.com/user-attachments/assets/7bc2133d-8c9e-40a9-962f-77f86223aacf" />

- [x]  **3. 에러가 난 부분을 디버깅하여 문제를 해결한 기록을 남겼거나
새로운 시도 또는 추가 실험을 수행해봤나요?**
    - 문제 원인 및 해결 과정을 잘 기록하였는지 확인
    - 프로젝트 평가 기준에 더해 추가적으로 수행한 나만의 시도, 
    실험이 기록되어 있는지 확인
        - RetinaNet 모델 뿐만아니라 regnet 이라는 모델을 학습해서 추론하는 추가실험을 진행했습니다.
    <img width="772" height="313" alt="image" src="https://github.com/user-attachments/assets/ace755cd-9c7b-4250-ab75-8e87abe54f0b" />
    <img width="667" height="401" alt="image" src="https://github.com/user-attachments/assets/749ced25-9a7c-43c5-83f6-692ac17dc2f0" />

- [ ]  **4. 회고를 잘 작성했나요?**
    - 주어진 문제를 해결하는 완성된 코드 내지 프로젝트 결과물에 대해
    배운점과 아쉬운점, 느낀점 등이 기록되어 있는지 확인
        - 모델 학습, 추론 결과에 대한 내용은 잘 작성되어 있지만 회고 내용은 없는 것 같습니다.
        
- [x]  **5. 코드가 간결하고 효율적인가요?**
    - 파이썬 스타일 가이드 (PEP8) 를 준수하였는지 확인
    - 코드 중복을 최소화하고 범용적으로 사용할 수 있도록 함수화/모듈화했는지 확인
        - 전체적으로 코드가 간결하고 효율적이게 작성되어 있는것 같습니다. 특히 아래 Loss함수 부분 구현이 모듈화가 잘되어 있어서 이해하기 쉬웠습니다.
    <img width="763" height="734" alt="image" src="https://github.com/user-attachments/assets/cf2d5024-95de-49bf-891f-5b08b3369794" />


# 회고(참고 링크 및 코드 개선)
- RetinaNet의 전체 파이프라인(백본 → FPN → 헤드 → 후처리)을 직접 구현한 코드를 리뷰하면서, Object Detection 모델의 구조를 깊이 이해할 수 있었습니다. 특히 Focal Loss와 Smooth L1 Loss를 조합한 Loss 함수 설계가 인상적이었습니다.
- RetinaNet 외에 RegNet을 동일 조건으로 비교 실험한 점이 좋았습니다.
