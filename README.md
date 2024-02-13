# HS-QnA-chatbot
DACON 도배 하자 질의 응답 처리 : 한솔데코 시즌2 AI 경진대회

### Leaderboard 결과 
- trial 1 (Feb 13) : 0.58578  [loss : 2.07]
- trial 1-2 (Feb 13) : 0.66776  [loss : 0.20]
- trial 2 (Feb 14) : 0.72278  [loss :0.17]

-----

### 아이디어 리스트 
- 모델링
  - ~kogpt2 기본 답변생성 및 추론 baseline 만들기~  
  - Full fine tuning 말고 부분 학습 해보기
    - PEFT
    - LoRA
    - Transfer learning (전이학습)
    - Freezing (동결학습)
  - fine tuning 말고 RAG 방법 활용 추론 해보기
  - Self-supervised / Semi-supervised language 모델 활용해보기
  - Human based reinforced learning 적용
- 모델 종류 
  - LLaMA 기본 답변생성 및 추론 baseline 만들기 
  - KoAlpaca 기본 답변생성 및 추론 baseline 만들기 https://github.com/Beomi/KoAlpaca
- 증강
  - 2개, 3개, 4개 등등 질문 연합
  - 문장간 유사도 혹은 단어들 포함 여부 확인 -> 문장들 세부분류하기 (category)
  - Q&A 사전학습모델로 학습 시켜서 데이터 증강 시킬 것 
- 분석 및 전처리
  - word embedding / 단어 사전 생성 / 세부 및 대분류 카테고리 확인하기 

--------

### 경과 
- 2/13 : kogpt + supervised fine tuning
  - kogpt2 기본 답변생성 및 추론 baseline 만들기
  - kogpt2 (6440개) epoch 1 **0.58578 (trial 1)**
  - kogpt2 (6440개) epoch 14 **0.66776 (trial 1-2)**  : Hansol_1__kogpt2_epoch14_loss0.2082 (LB 0.66776)
- 2/14 : llama + supervised fine tuning
  - kogpt2 (26440개) epoch 6 **0.72278 (trial 2)**  : Hansol_2_kogpt2_trial2_date_2_13_epoch6_loss0.1751 (LB 0.72278) .ipynb
  - kogpt2 (26440개) 
   

