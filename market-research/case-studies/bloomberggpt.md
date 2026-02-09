# Case Study: BloombergGPT (Finance)

**Title:** BloombergGPT: 금융 특화 LLM 구축의 정석 (Build from Scratch)
**Industry:** Finance & Investment
**Subject:** 500억 파라미터 규모의 금융 특화 언어 모델 개발기

## 1. Executive Summary

Bloomberg는 범용 LLM(GPT-3.5 등)이 금융 도메인의 특수성(복잡한 수치, 전문 용어, 시간 민감성)을 완벽히 소화하지 못한다고 판단, 40년간 축적된 자사 금융 데이터와 일반 웹 데이터를 결합하여 **500억 파라미터 규모의 'BloombergGPT'**를 자체 개발했다. 이는 "Build vs Buy" 논쟁에서 **"압도적인 도메인 데이터가 있다면 Build가 정답"**임을 증명한 대표적 사례다.

## 2. The Challenge (문제 정의)

- **범용 모델의 한계:** 일반적인 LLM은 "2023년 1분기 영업이익률"과 같은 구체적인 수치 연산이나, "매파적(Hawkish)"과 같은 금융 은어의 맥락을 정확히 이해하는 데 어려움을 겪음.
- **데이터 보안 및 최신성:** 금융 데이터는 보안이 생명이며, 실시간으로 변하는 시장 상황을 반영해야 함. 외부 API 의존 시 데이터 유출 우려와 레이턴시 문제가 발생.
- **토큰화(Tokenization)의 비효율:** 기존 BPE(Byte Pair Encoding) 방식은 숫자를 무의미한 조각으로 쪼개어 수치적 추론 능력을 저하시킴.

## 3. The Solution (해결 방안 및 기술 아키텍처)

### 3.1 Data Strategy: 'FinPile' 구축
Bloomberg는 총 7,000억(700B) 토큰의 학습 데이터를 구축했으며, 이는 금융 데이터와 일반 데이터의 **51:49** 황금비율로 구성됨.

- **FinPile (363B Tokens):** Bloomberg 터미널, 뉴스, 공시 자료(Filings), 프레스 릴리스 등 40년치 독점 데이터.
- **Public Data (345B Tokens):** The Pile, C4, Wikipedia 등 일반 상식 및 언어 능력 확보용 데이터.
- **특이점:** 금융 데이터는 **시간 순서(Chronological order)**가 중요하므로, 학습 데이터 배치 시 시간적 인과관계를 보존하도록 설계.

### 3.2 Model Architecture & Tokenization
- **Model Size:** 50B Parameters (700B 토큰 학습). 이는 Chinchilla Scaling Law(최적의 데이터/파라미터 비율)를 따름.
- **Unigram Tokenizer:** 숫자를 더 의미 있는 단위로 처리하고, 금융 전문 용어(티커 심볼 등)를 보존하기 위해 표준 BPE 대신 **Unigram 토크나이저**를 채택. 이는 모델이 "123.45"를 하나의 수치로 인식하는 데 도움을 줌.

### 3.3 Training Infrastructure
- **Compute:** AWS SageMaker 기반, 512개의 NVIDIA A100(40GB) GPU 활용.
- **Optimization:** PyTorch FSDP(Fully Sharded Data Parallel)를 사용하여 대규모 모델을 효율적으로 분산 학습.
- **Challenge:** 학습 중 발생하는 손실 스파이크(Loss Spikes) 문제를 해결하기 위해 배치 사이즈와 학습률(Learning Rate)을 세밀하게 조정(Warmup & Decay).

## 4. Results & Impact (성과)

### 4.1 Benchmark Performance
- **Financial Tasks:** 금융 감성 분석(FiQA SA), 뉴스 분류(FPB), 수치 질의응답(ConvFinQA) 등 금융 특화 벤치마크에서 **GPT-NeoX, OPT-66B, BLOOM-176B 등 동급 모델을 압도**하고, 일부 태스크에서는 훨씬 큰 모델(GPT-3 등)보다 우수한 성능 기록.
- **General Tasks:** MMLU 등 일반 상식 벤치마크에서도 성능 저하 없이 **GPT-3 수준**을 유지. "Specialist 모델이 Generalist 능력도 잃지 않음"을 입증.

### 4.2 Business Value
- **Bloomberg Terminal 강화:** 자연어 질의(Bloomberg Query Language, BQL)를 코드로 변환하거나, 뉴스 헤드라인을 자동 생성하고 감성을 분석하는 기능을 터미널에 내장하여 유료 구독자의 가치 제고.
- **Data Moat:** 타사가 복제할 수 없는 'FinPile' 데이터의 가치를 재확인하고, 금융 AI 분야의 기술적 리더십 확보.

## 5. Key Takeaways (시사점)

1.  **데이터가 깡패다:** 모델 아키텍처보다 중요한 것은 "얼마나 양질의 도메인 데이터를 보유하고 있는가"이다.
2.  **토크나이저부터 고민하라:** 도메인 특화 모델을 만들 때는 범용 토크나이저를 그대로 쓰지 말고, 해당 도메인의 언어적 특성(숫자, 화학식, 코드 등)에 맞는 전처리 방식이 필수적이다.
3.  **Hybrid Training:** 도메인 데이터만으로는 일반 언어 능력이 떨어질 수 있으므로, 일반 데이터와의 적절한 혼합(Mixing) 비율을 찾는 것이 성능의 핵심이다.

## References
- arXiv:2303.17564 ("BloombergGPT: A Large Language Model for Finance")
- Bloomberg Tech Blog
