# 제 3회 KRX 금융 모델 경진대회
📅 기간 : 24년 10.14 ~ 12.6

👬 팀명 & 팀원 수 : KR-X-AI / 4명

🏆 수상 내역 : 예선 3위, 본선 12위

💻 기술 스택 : SFT, Continual-pretrain, DAFT, distillation, QLoRA

🛠 사용 도구 : Unsloth, Bedrock

# 대회 소개 및 내용
본 대회를 통해 참가자들은 금융 특화 언어 모델을 개발하고, 한국거래소와 금융 특화 언어 모델 전문 기업 원라인AI가 공동 개발한 ‘KRX-Bench’를 이용하여 그 성능을 평가받을 수 있습니다.
이 대회는 금융 시장의 효율성을 높이고, 투자자들에게 더욱 정확하고 유용한 정보를 제공하는 데 기여할 것입니다.
#### 예선
금융분야 전반을 다루는 MCQA(Multiple Choice Question Answering)로 구성된 ‘KRX-Bench Easy’를 이용하여 금융 한글 언어 모델 성능 평가
#### 본선
금융분야 심화된 내용을 다루는 MCQA(Multiple Choice Question Answering) 및 생성형 질문으로 구성된 ‘KRX-Bench Challenge’를 이용하여 금융 한글 언어 모델 성능 평가

# 모델 별 성능 분석
![image](https://github.com/user-attachments/assets/1b71bffa-4d7a-4361-8938-f818d39ef840)
<img width="841" alt="image" src="https://github.com/user-attachments/assets/3a836800-033e-490a-b988-1c3106fe6f50" />
| 모델명 | 전체 평균 | 국내기업 | 재무회계 | 주가예측 | 금융에이전트 | 금융시장 |url|
|--------|-----------|----------|----------|----------|--------------|----------|----------|
| qwen2-7B-Instruct | 0.44 | 0.51 | 0.27 | 0.54 | 0.62 | 0.26 |-|
| v1 | 0.39 | 0.38 | 0.27 | 0.50 | 0.47 | 0.31 |[KR-X-AI:v1](https://huggingface.co/KR-X-AI/krx-qwen2-7b-instruct-v1)|
| v2 | 0.50 | 0.61 | 0.34 | 0.55 | 0.66 | 0.35 |[KR-X-AI:v2](https://huggingface.co/KR-X-AI/krx-qwen2-7b-instruct-v2)|
| v3 | 0.59 | 0.90 | 0.40 | 0.49 | 0.72 | 0.44 |[KR-X-AI:V3](https://huggingface.co/KR-X-AI/krx-qwen2-7b-instruct-v3)|
| v4_mix | 0.61 | 0.92 | 0.40 | 0.55 | 0.77 | 0.41 |[KR-X-AI:v4_m](https://huggingface.co/KR-X-AI/krx-qwen2-7b-instruct-v4_m)|


# 모델 설명

# 참고 문서
[Adapting Large Language Models to Domains via Reading Comprehensio 논문](https://arxiv.org/abs/2309.09530)
