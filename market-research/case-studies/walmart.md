# Case Study: Walmart (Retail / Search)

**Title:** Walmart GenAI Search: "상품"이 아닌 "해결책"을 검색하다
**Industry:** Retail / E-commerce
**Subject:** 키워드 검색을 넘어선 '목적 기반(Solution-based)' 하이브리드 검색 구현

## 1. Executive Summary

Walmart는 고객이 구체적인 상품명이 아닌 "파티 준비", "이사 선물" 같은 모호한 의도로 검색할 때 겪는 불편함을 해소하기 위해 **GenAI Search**를 도입했다. Microsoft Azure OpenAI(GPT-4)와 자체 벡터 검색 기술을 결합한 **하이브리드 아키텍처**를 통해, 단순 상품 나열이 아닌 "테마별 통합 솔루션"을 제안하는 새로운 검색 경험(SGE)을 구현했다.

## 2. The Challenge (문제 정의)

- **Keyword Mismatch:** 고객은 "유니콘 테마 파티 준비해줘"라고 검색하지만, 기존 검색 엔진은 '유니콘', '테마', '파티'라는 단어가 포함된 상품만 기계적으로 나열함.
- **High Friction:** 파티를 준비하려면 접시, 풍선, 간식, 음료 등을 일일이 따로 검색해서 장바구니에 담아야 함. (검색 횟수 증가 -> 이탈률 증가)
- **Zero Results:** 복잡한 자연어 쿼리에 대해 기존 검색 엔진은 "검색 결과 없음"을 반환하는 경우가 많음.

## 3. The Solution (해결 방안 및 기술 아키텍처)

### 3.1 Hybrid Search Architecture
Walmart는 정확성(Precision)과 맥락 이해(Context)를 모두 잡기 위해 두 가지 검색 방식을 결합했다.

- **Lexical Search (Keyword):** 기존의 역색인(Inverted Index) 방식. 정확한 상품명(예: "Galaxy S24") 검색 시 사용.
- **Semantic Search (Vector):** 자체 구축한 **BERT 기반 인코더**를 사용해 상품과 쿼리를 임베딩. "여름 휴가 필수템" 같은 추상적 쿼리의 의미를 파악하여 관련 상품 추천.
- **Fusion:** 두 검색 결과를 결합(Hybrid)하고, 고객의 구매 이력 및 실시간 재고 상황을 반영하여 재정렬(Re-ranking).

### 3.2 GenAI Integration (GPT-4 on Azure)
- **Query Understanding:** 사용자의 자연어 쿼리를 LLM이 먼저 해석하여 "이 사용자는 지금 파티 용품, 간식, 장식품을 찾고 있다"는 **'검색 의도(Intent)'**를 파악.
- **Solution Generation:** 파악된 의도에 맞춰 "파티 장식", "다과", "일회용품" 등 카테고리별로 상품을 묶어서(Bundling) 제안.

### 3.3 Inventory-Awareness (InvAwr-RAG)
- **The Problem:** LLM이 추천한 상품이 품절 상태라면 고객 경험은 최악이 됨.
- **The Fix:** **'InvAwr-RAG'** 모델을 도입. 생성 단계에서 실시간 재고 데이터(Real-time Inventory)를 강제로 참조하게 하여, **"지금 구매 가능한"** 상품만 추천하도록 제약(Constraint)을 걺.

## 4. Results & Impact (성과)

### 4.1 Quantitative Metrics
- **Productivity:** 제품 카탈로그 업데이트 및 태깅 작업 생산성 **100배 향상**.
- **Revenue Growth:** 이커머스 매출 **21% 성장**의 핵심 동력으로 작용 (2024-2025 실적 기준).
- **Search Experience:** 고객의 평균 검색 횟수 감소 및 장바구니 담기(Add-to-Cart) 전환율 상승.

### 4.2 UX Innovation
- **Cross-category Bundling:** "축구 관람 간식" 검색 시, TV(가전), 윙(델리), 맥주(주류)를 한 화면에 보여주는 '솔루션 뷰' 제공.
- **Conversational Refinement:** "채식주의자용으로 바꿔줘" 같은 후속 질문을 통해 검색 결과를 실시간으로 좁혀가는 대화형 인터페이스 제공.

## 5. Key Takeaways (시사점)

1.  **검색은 더 이상 '매칭'이 아니다:** 검색은 고객의 문제를 해결해주는 '솔루션 제안' 과정이어야 한다. GenAI는 이를 위한 '맥락 해석기' 역할을 한다.
2.  **재고 없는 추천은 죄악이다:** 리테일 AI의 핵심은 화려한 생성이 아니라, **"실시간 재고(Inventory)"와의 연동**이다. 이를 위한 RAG 파이프라인 구축이 필수다.
3.  **속도와 정확도의 균형:** 모든 쿼리에 LLM을 쓰면 느리고 비싸다. 키워드 검색으로 충분한 쿼리는 기존 방식을, 복잡한 쿼리는 GenAI를 타도록 **라우팅(Routing)**하는 것이 현실적이다.

## References
- Walmart Global Tech Blog
- arXiv:2412.04637 ("Semantic Retrieval at Walmart")
- CES 2024 Keynote
