# 제 3회 KRX 금융 모델 경진대회
📅 기간 : 24년 10.14 ~ 12.6

👬 팀명 & 팀원 수 : KR-X-AI / 4명

🏆 수상 내역 : 예선 3위, 본선 12위

🙋🏻 맡은 역할 : MCQA 데이터 제작, SFT학습 : V3, V4_m 모델 학습

💻 기술 스택 : SFT, DAPT, Adapting LLM, QLoRA

🛠 사용 도구 : Unsloth, Bedrock, GPT API

# 대회 소개 및 내용
본 대회를 통해 참가자들은 금융 특화 언어 모델을 개발하고, 한국거래소와 금융 특화 언어 모델 전문 기업 원라인AI가 공동 개발한 ‘KRX-Bench’를 이용하여 그 성능을 평가받을 수 있습니다.
이 대회는 금융 시장의 효율성을 높이고, 투자자들에게 더욱 정확하고 유용한 정보를 제공하는 데 기여할 것입니다.
#### 예선
금융분야 전반을 다루는 MCQA(Multiple Choice Question Answering)로 구성된 ‘KRX-Bench Easy’를 이용하여 금융 한글 언어 모델 성능 평가
#### 본선
금융분야 심화된 내용을 다루는 MCQA(Multiple Choice Question Answering) 및 생성형 질문으로 구성된 ‘KRX-Bench Challenge’를 이용하여 금융 한글 언어 모델 성능 평가

# 모델 별 성능 분석
![krx_모델 성능 비교](https://github.com/user-attachments/assets/4800d089-f943-43ef-ba40-7b10daa2e322)

| 모델명 | 전체 평균 | 국내기업 | 재무회계 | 주가예측 | 금융에이전트 | 금융시장 |url|
|--------|-----------|----------|----------|----------|--------------|----------|----------|
| qwen2-7B-Instruct | 0.44 | 0.51 | 0.27 | 0.54 | 0.62 | 0.26 |-|
| v1 | 0.39 | 0.38 | 0.27 | 0.50 | 0.47 | 0.31 |[KR-X-AI:v1](https://huggingface.co/KR-X-AI/krx-qwen2-7b-instruct-v1)|
| v2 | 0.50 | 0.61 | 0.34 | 0.55 | 0.66 | 0.35 |[KR-X-AI:v2](https://huggingface.co/KR-X-AI/krx-qwen2-7b-instruct-v2)|
| v3 | 0.59 | 0.90 | 0.40 | 0.49 | 0.72 | 0.44 |[KR-X-AI:v3](https://huggingface.co/KR-X-AI/krx-qwen2-7b-instruct-v3)|
| v4_m | 0.61 | 0.92 | 0.40 | 0.55 | 0.77 | 0.41 |[KR-X-AI:v4_m](https://huggingface.co/KR-X-AI/krx-qwen2-7b-instruct-v4_m)|

# 모델 설명
### V1

: 금융 용어 관련 대규모 데이터셋을 Qwen2-7B-Instruct 모델에 SFT 학습

📍`model name` : KR-X-AI/krx-qwen2-7b-instruct-v2

📍`base model` : Qwen/Qwen2-7B-Instruct

📍`training method` : DAPT, QLoRA

📍`dataset` : ai hub 금융 합성 데이터셋(14.44GB)

📍`train time` : 4hour 48min 12sec

📍`hardware` : AMD 3960X RTX3090

### V2

: 금융 용어 multi task 데이터셋 Adapting LLM 학습

📍`model name` : KR-X-AI/krx-qwen2-7b-instruct-v2

📍`base model` : Qwen/Qwen2-7B-Instruct

📍`training method` : Adapting LLM, QLoRA

📍`dataset` : 금융 용어 데이터 셋 

📍`train time` : 29min 16sec

📍`hardware` : AMD 3960X RTX3090

### V3

: V2 모델에 MCQA 데이터 셋 SFT 학습

📍`model name`**:** KR-X-AI/krx-qwen2-7b-instruct-v3

📍`base model`**:** KR-X-AI/krx-qwen2-7b-instruct-v2

📍`training method` : SFT

📍`dataset` : MCQA 데이터 셋

📍`train time` : 12분 32초

📍`hardware` : AMD 3960X RTX3090

### V4_m

: V2모델에 MCQA 데이터 셋과 주가 예측 데이터 셋을 섞어 SFT 학습

📍`model name`**:** KR-X-AI/krx-qwen2-7b-instruct-v3

📍`base model`**:** KR-X-AI/krx-qwen2-7b-instruct-v2

📍`training method` : SFT

📍`dataset` : MCQA 데이터 셋 + 주가 예측 데이터

📍`train time` : 27분 46초

📍`hardware` : AMD 3960X RTX3090

# 합성 데이터 설명
### 금융 용어 합성 데이터
📦 데이터 크기 : 2.1 MB

📍데이터 출처 : [기획 재정부 금융 용어집(941KB)](https://www.econedu.go.kr/user/playEcon/currEconTermDoc/menu/list)

📄 참고 논문 : [Adapting Large Language Models to Domains via Reading Comprehension](https://arxiv.org/abs/2309.09530)

<img width="595" alt="image" src="https://github.com/user-attachments/assets/fe5608f6-cac2-444c-8c56-8ee83622b48e" />

1. raw data에서 금융 주제만 뽑는다 ⇒ 총 816개
2. gpt api를 활용하여 합성 데이터를 생성한다.
3. SFT 학습 형태에 맞게 format을 맞춘다.

### MCQA 합성 데이터
📦 데이터 크기 : 700 KB

📍데이터 출처 : [huggingface - Cartinoe5930/raw_text_synthetic_dataset_50k](https://huggingface.co/datasets/Cartinoe5930/raw_text_synthetic_dataset_50k)

📄 참고 논문 : [KRX-Bench: Automating Financial Benchmark Creation via Large Language Models](https://aclanthology.org/2024.finnlp-1.2/)

<img width="601" alt="스크린샷 2025-02-25 오후 1 15 48" src="https://github.com/user-attachments/assets/82b6835c-f1a0-4884-ad25-ea513a823988" />

1. 유사한 내용을 가진 데이터를 BM25기반으로 검색. - **BM25**
2. 내용이 매우 비슷한 금융에 관한 context 두개를 입력으로 주어 해당 context에 관련된 MCQA 합성데이터를 만들도록 GPT-4o-mini에게 요청 - **generate data**
3. 생성한 데이터에 중복 정답이 없는지 체크하고 있다면 다른 선택지로 바꾸도록 처리 - **quality control**

### 주가 예측 합성 데이터
파이썬 코드를 활용하여 랜덤성을 부여한 상승, 하락 주가 데이터 제작.

# 보고서
[KRX-금융 언어 모델 경진대회 보고서.pdf](https://github.com/user-attachments/files/18964371/KRX-.pdf)

# 참고 문서
📄 [Adapting Large Language Models to Domains via Reading Comprehensio 논문](https://arxiv.org/abs/2309.09530)

📄 [KRX-Bench: Automating Financial Benchmark Creation via Large Language Models 논문](https://aclanthology.org/2024.finnlp-1.2.pdf)

📄 [Allganize 금융 LLM 제작 후기 블로그](https://www.allganize.ai/ko/blog-posts-ko/defining-evaluating-performance-of-financial-llm-models)
