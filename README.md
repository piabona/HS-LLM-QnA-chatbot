## Dacon 도배하자 Q&A 챗봇 : 한솔데코 시즌2 AI 경진대회 [Private 3rd]

- 대회 개요 (2024.01.29 ~ 2024.03.11)
- https://dacon.io/competitions/official/236216/overview/description
- LLM 챗봇 대회 (Cosine Similarity)
- 한솔데코 도배하자와 관련된 다양한 질문과 상황을 제공하고, 이에 대한 정확하고 신속한 응답을 제공하는 AI 모델 개발
- 성과 : 팀(3인) private 0.6%이내 - 3등/557팀
- [발표자료 pdf](https://github.com/piabona/HS-QnA-chatbot/blob/4f83d4498e5c62329e7de4994b4e03a355ad9452/report/Hansoldeco_%E1%84%89%E1%85%A1%E1%86%B7%E1%84%8E%E1%85%A9%E1%86%BC%E1%84%89%E1%85%A1_ppt.pdf)

## Summary  
- **Data Preprocessing** : 형식 오류 문장, 질문 간 유사도 동떨어진 문장 등을 확인 후 수정 및 대체하여 예외 문장 최소화
- **Data Augmentation** : GPT 증강 및 인덱스 Permutation 활용 문장 간 연결 증강
- **Modeling** : [KoGPT2](https://huggingface.co/skt/kogpt2-base-v2) Fine-Tuning, probabilistic sampling 
- **Validation** : 증강 데이터 임의 추출하여 검증셋 생성, 검증답변 - 모델 생성답변 간 cosine 유사도 평균으로 모델 평가
- **Refinement** : 질문 - 답변간 유사도 확인하여 후보 답변 중 선택
- **Application** : RAG 방식 Vector DB 추가 활용 가능성 
  
### Environment
- OS: Linux-6.1.58+-x86_64-with-glibc2.35
- Google Colab GPU (학습 V100, 추론 T4)

### Libraries 
- `pandas` : 1.5.3
- `numpy` : 1.25.2
- `torch` : 2.2.1+cu121
- `transformers` : 4.38.2
- `sentence_transformers` : 2.5.1
