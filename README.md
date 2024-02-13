# HS-QnA-chatbot
DACON 도배 하자 질의 응답 처리 : 한솔데코 시즌2 AI 경진대회

### Leaderboard 결과 
- trial 1 (Feb 13) : 0.58578  [loss : 2.07]
- trial 2 (Feb 13) :

### 아이디어 리스트 
- 모델링
  - ~kogpt2 기본 답변생성 및 추론 baseline 만들기~  
  - llama 기본 답변생성 및 추론 baseline 만들기
  - fine tuning 말고 RAG 방법 활용 추론 해보기 
- 증강
  - 문장간 유사도 혹은 단어들 포함 여부 확인 -> 문장들 세부분류하기 (category)
  - 2개, 3개, 4개 등등 질문 연합
  - Q&A 사전학습모델로 학습 시켜서 데이터 증강 시킬 것 
- 분석 및 전처리
  - word embedding / 단어 사전 생성 / 세부 및 대분류 카테고리 확인하기 


### 경과 
- 2/13 : kogpt + supervised fine tuning
  - kogpt2 기본 답변생성 및 추론 baseline 만들기 : epoch 1 **0.58578 (trial 1)**  /  epoch 20 


