# Case Study: Klarna (Customer Service)

**Title:** Klarna AI Assistant: "AI First" 전략의 명과 암
**Industry:** Fintech / E-commerce
**Subject:** 고객 서비스 상담원 700명 업무의 AI 대체와 하이브리드 전략으로의 회귀

## 1. Executive Summary

![Klarna AI App](../images/klarna_app.jpeg)

Klarna는 2024년 초, OpenAI 기반의 AI 어시스턴트를 전격 도입하여 상담원 700명분의 업무를 자동화하고 연간 4천만 달러의 수익 개선을 이뤄냈다. 그러나 2025년 중반, "비용 절감이 과도했다"는 판단 하에 고객이 원하면 언제든 인간 상담원과 연결될 수 있는 옵션을 강화하며 **'AI 효율성'과 '인간적 공감'의 균형점(Hybrid Model)**을 찾아가고 있다.

## 2. The Challenge (문제 정의)

- **폭발적인 상담량:** 전 세계 1억 5천만 명 이상의 사용자가 발생시키는 막대한 양의 구매/환불 문의 처리 비용 급증.
- **다국어 지원의 한계:** 24/7 다국어 상담을 위해 각국에 콜센터를 운영하거나 BPO(아웃소싱) 업체를 쓰는 비용과 관리 부담.
- **상담 품질의 불일치:** 상담원 숙련도에 따라 답변의 정확도와 친절도가 달라지는 문제.

## 3. The Solution (해결 방안 및 기술 아키텍처)

### 3.1 AI Agent Architecture
- **Tech Stack:** OpenAI의 **GPT-4** 모델을 기반으로 하되, 단순 API 호출이 아닌 Klarna의 백엔드 시스템(계정 조회, 환불 실행 등)과 연동된 **'AI Agent'** 형태로 구현.
- **RAG Implementation:** 환불 정책, 약관 등 내부 지식 베이스를 실시간으로 검색(Retrieve)하여 답변을 생성. 이는 "없는 정책을 지어내는" 환각(Hallucination)을 방지하는 핵심 장치.

### 3.2 Hallucination Control & Safety
- **Strict Prompts:** "확실하지 않으면 답변하지 말고 인간에게 넘길 것", "정책 문서에 근거해서만 답변할 것" 등 강력한 시스템 프롬프트 적용.
- **Customer Verification:** 민감한 개인정보 조회나 결제 취소 시, 앱 내 본인 인증 절차를 강제하여 보안 사고 방지.

### 3.3 Human Handover Strategy
- **Trigger Conditions:**
  - AI가 고객의 의도를 2회 이상 이해하지 못할 때.
  - **감정 분석(Sentiment Analysis):** 고객의 대화 톤에서 분노, 좌절 등이 감지될 때.
  - 복잡한 분쟁(Dispute) 등 정책상 자동 처리가 불가능한 카테고리.
  - **고객의 명시적 요청:** (2025년 강화된 정책) 고객이 원하면 즉시 인간 상담원 연결 버튼 노출.

## 4. Results & Impact (성과 및 부작용)

### 4.1 Quantitative Success
- **Workload Replacement:** 출시 1개월 만에 전체 문의의 **2/3(약 230만 건)**를 AI가 단독 처리. 이는 정규직 상담원 **700명의 업무량**에 해당.
- **Efficiency:** 평균 해결 시간(Resolution Time)이 **11분에서 2분 미만**으로 단축.
- **Financial Impact:** 연간 **4,000만 달러(약 550억 원)**의 수익 개선 효과 추산.
- **Accuracy:** 반복 문의(Repeat Inquiries)가 **25% 감소**하여 AI 답변의 정확도가 높음을 입증.

### 4.2 Qualitative Shift & Lessons Learned
- **BPO 축소:** 외부 아웃소싱 업체와의 계약을 대폭 줄이고 내부 인력 위주로 재편.
- **The Pivot (2025):** 초기에는 "AI 우선"으로 인간 연결을 어렵게 만들었으나, 고객 경험 저하 우려로 CEO가 직접 "인간 상담원 채용 확대" 및 "연결 옵션 강화"를 발표. **"비용 절감"만 추구하면 "고객 이탈"이라는 역풍을 맞을 수 있음**을 시사.

## 5. Key Takeaways (시사점)

1.  **AI는 '대체'가 아닌 '전환'이다:** 상담원을 해고하는 것이 아니라, 단순 업무는 AI에게 맡기고 상담원은 고부가가치(분쟁 해결, 감정 케어) 업무로 전환해야 한다.
2.  **RAG는 필수다:** 금융/커머스 영역에서 LLM의 환각은 치명적이다. 반드시 최신 정책 문서를 참조하는 RAG 아키텍처와 엄격한 프롬프트가 동반되어야 한다.
3.  **Exit Button을 숨기지 마라:** 고객이 AI에 갇혀 답답해하면 서비스 자체를 떠난다. 언제든 인간에게 탈출할 수 있는 문(Handover)을 열어두는 것이 AI 성공의 역설적인 핵심이다.

## References
- Klarna Press Releases (2024, 2025)
- Interviews with CEO Sebastian Siemiatkowski
