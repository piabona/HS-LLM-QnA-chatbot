# HS-QnA-chatbot
- 목표 : sLLM 활용 챗봇 서비스 개발 (end user 수준)
- DACON 도배 하자 질의 응답 처리 : 한솔데코 시즌2 AI 경진대회

![image](https://github.com/piabona/HS-QnA-chatbot/assets/54427769/8cd13b6c-0a44-46e6-b703-465765ba3e7b)


### Detail 및 각 단계 
- 1) 데이터 EDA 및 전처리
- 2) 데이터 증강
- 3) 모델 학습 + 모델링 
     - 최적화 (파라미터, optimizer, scheduler 등등)
- 4) 개발 환경
     - 제한된 환경, gpu, ram 등 정보
- 5) 모델 평가 및 고도화 
     - BLEU, 강화학습 활용
     - rule based - 유사도 평가 활용
- 6) 모델 서빙 프로세스

-------------------


### 평가 기준 
- 자체 모델 검증 방법
- 데이터 전처리, 증강 
- 모델 학습 
- 모델 서빙 프로세스 제안 

-----------------------


### Leaderboard 결과 
- trial 1 (Feb 13) : 0.58578  [loss : 2.07]
- trial 1-2 (Feb 13) : 0.66776  [loss : 0.20]
- trial 2 (Feb 14) : 0.72278  [loss :0.17]
- trial 2-2 (Feb 14) : 0.71471 [loss : 0.14]

-----

### 아이디어 리스트 
- 모델 서빙프로세스
  - 
- 모델 자체 검증
  - 
- 모델링
  - ~kogpt2 기본 답변생성 및 추론 baseline 만들기~   : **LB 0.66776**
  - Full fine tuning 말고 부분 학습 해보기
    - PEFT
    - QLoRA
    - ~Transfer learning (전이학습)~
    - ~Freezing (동결학습)~
  - ~fine tuning 말고 RAG 방법 활용 추론 해보기~ -> RAG 와 Fine tuning 한번에 
  - Self-supervised / Semi-supervised language 모델 활용해보기
  - Human based reinforced learning 적용
- 모델 종류
  - '**yanolja/KoSOLAR-10.7B-v0.2**',
  - '**ONS-AI-RESEARCH/ONS-SOLAR-10.7B**',
  - 'kimwooglae/WebSquareAI-Instruct-KoSOLAR-10.7b-v0.5.34',
  - '**LDCC/LDCC-SOLAR-10.7B**'
  - ~LLaMA 기본 답변생성 및 추론 baseline 만들기~
  - KoAlpaca 기본 답변생성 및 추론 baseline 만들기 https://github.com/Beomi/KoAlpaca
- 증강
  - ~연결어 기준 2개 질문 연합~  : 20000개 증강 **LB 0.66776 -> 0.72278**
  - ~연결어 기준 2개 질문 연합~  : 30000개 증강 **LB 0.66776 -> 
  - 3개, 4개 등등 질문 연합
  - 연결어 확장 : 역접어 (그러나, 그럼에도, 인과관계 표현 등등) 
  - 문장간 유사도 혹은 단어들 포함 여부 확인 -> **문장들 세부분류하기 (category) -> 카테고리 포함하여 생성시에 인식하도록** 
  - Q&A 사전학습모델로 학습 시켜서 데이터 증강 시킬 것 
- 분석 및 전처리
  - word embedding / 단어 사전 생성 / 세부 및 대분류 카테고리 확인하기 
- 답변 정제
  - 숫자 처리 / 영어 처리 등
- 후처리
  - ~similarity  / 답변을 평가하는 gpt / Optuna로 cosine, jaccard 유사도 하이퍼파라미터 튜닝~
--------

### 경과 
- 2/13 : kogpt + supervised fine tuning
  - kogpt2 기본 답변생성 및 추론 baseline 만들기
  - kogpt2 (6440개) epoch 1 **0.58578 (trial 1)**
  - kogpt2 (6440개) epoch 14 **0.66776 (trial 1-2)**  : Hansol_1__kogpt2_epoch14_loss0.2082 (LB 0.66776)
- 2/14 : llama + supervised fine tuning
  - kogpt2 (26440개) epoch 6 **0.72278 (trial 2)**  : Hansol_2_kogpt2_trial2_date_2_13_epoch6_loss0.1751 (LB 0.72278).ipynb
  - kogpt2 (26440개) epoch 14 **(trial 2-2)** : Hansol_2-2_kogpt2_trial2-2_date0214_06_epoch14_loss0.1417 (LB 0.71471).ipynb
  - kogpt2 (36440개) epoch 
   

