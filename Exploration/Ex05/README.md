# AIFFEL Campus Online Code Peer Review Templete
- 코더 : 정민규.
- 리뷰어 : 정수연.


# PRT(Peer Review Template)
- [x]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - 문제에서 요구하는 최종 결과물이 첨부되었는지 확인
        - 중요! 해당 조건을 만족하는 부분을 캡쳐해 근거로 첨부
        - 구축한 3개의 기본 모델(RNN, stacked RNN, LSTM)과 Worcd2Vec embedding 값을 가져와서 돌린 결과와 정량적 및 정성적 비교를 잘 정리하여서 표현하셨다.
        - <img width="1176" height="1843" alt="image" src="https://github.com/user-attachments/assets/dddf35d2-f40f-4914-87a1-e03f6be5ccb6" />


    
- [x]  **2. 전체 코드에서 가장 핵심적이거나 가장 복잡하고 이해하기 어려운 부분에 작성된 
주석 또는 doc string을 보고 해당 코드가 잘 이해되었나요?**
    - 해당 코드 블럭을 왜 핵심적이라고 생각하는지 확인
    - 해당 코드 블럭에 doc string/annotation이 달려 있는지 확인
    - 해당 코드의 기능, 존재 이유, 작동 원리 등을 기술했는지 확인
    - 주석을 보고 코드 이해가 잘 되었는지 확인
        - 중요! 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부
        - 
        - Word2Vec를 가져와서 적용하는 부분이 가장 핵심적이라고 생각했습니다. 
        - <img width="543" height="257" alt="image" src="https://github.com/user-attachments/assets/8744e147-d963-4577-91a7-147f63683690" />
        - <img width="538" height="232" alt="image" src="https://github.com/user-attachments/assets/9d3c84a6-2d36-4221-aa99-7ce5b713959a" />
        - <img width="540" height="221" alt="image" src="https://github.com/user-attachments/assets/9b40446f-47a0-4675-a8c8-4e2119540e69" />



        
- [x]  **3. 에러가 난 부분을 디버깅하여 문제를 해결한 기록을 남겼거나
새로운 시도 또는 추가 실험을 수행해봤나요?**
    - 문제 원인 및 해결 과정을 잘 기록하였는지 확인
    - 프로젝트 평가 기준에 더해 추가적으로 수행한 나만의 시도, 
    실험이 기록되어 있는지 확인
        - 중요! 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부
        - LSTM에서 단방향에서 성능을 더 확인해보고자 양방향으로 추가로 더 실험하신 부분이 있었습니다.
        - <img width="541" height="217" alt="image" src="https://github.com/user-attachments/assets/8fd81fca-6040-4372-a49c-90283ecc1d42" />

        
- [x]  **4. 회고를 잘 작성했나요?**
    - 주어진 문제를 해결하는 완성된 코드 내지 프로젝트 결과물에 대해
    배운점과 아쉬운점, 느낀점 등이 기록되어 있는지 확인
    - 전체 코드 실행 플로우를 그래프로 그려서 이해를 돕고 있는지 확인
        - 중요! 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부
     
        - 전체적인 결과를 깔끔하게 정리했다고 생각했습니다.
        - <img width="556" height="122" alt="image" src="https://github.com/user-attachments/assets/c6b94577-8e8f-4edb-b2ee-45e562209789" />


        
- [x]  **5. 코드가 간결하고 효율적인가요?**
    - 파이썬 스타일 가이드 (PEP8) 를 준수하였는지 확인
    - 코드 중복을 최소화하고 범용적으로 사용할 수 있도록 함수화/모듈화했는지 확인
        - 중요! 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부
        - 함수를 시작할 때 전체적인 함수 설명과 주석 설명이 잘 되어있다고 생각했습니다
        - <img width="421" height="377" alt="image" src="https://github.com/user-attachments/assets/f08c9939-cb2f-4b17-a020-ce7d602bef60" />



# 회고(참고 링크 및 코드 개선)

코드 전개가 깔끔하여서 앞으로 정리를 해야할 방향을 잘 알 수 있었습니다. 또한 실험 수행을 잘 하신 것 같아서 코드를 따라가는 것만으로도 배울 수 있는 점이 많았습니다. 
