# Cross-Industry Overview: AI-Powered Digital Products & Internalization

작성일: 2026-02-09

## 목적

이 문서는 산업별 문서(`market-research/industries/*.md`)를 읽기 전에, 공통적으로 반복되는 시장 구조와 내재화(빌드/바이/하이브리드) 의사결정 프레임을 정리한다.

## 공통 패턴 (2024-2026)

- 제품 레벨: 검색/추천/개인화, 고객지원(챗/에이전트), 콘텐츠 생성(텍스트/이미지/비디오), 자동 요약/정리, 사기/리스크 탐지
- 내부 레벨(내재화): 문서/지식 Q&A, 개발/운영 코파일럿, 워크플로우 자동화(RPA+LLM), 품질/컴플라이언스(감사 로그, 정책 엔진)

## 내재화가 빨라지는 조건

- 규모: 호출량이 커져 API 단가가 핵심 비용이 되는 경우
- 차별화: 도메인 특화 성능이 핵심 경쟁력인 경우
- 규제/데이터: 개인정보/민감정보/콘텐츠 IP로 인해 외부 전송이 어려운 경우
- 신뢰/SLA: 장애/쿼터/벤더 정책 변화가 치명적인 경우

## API 도입이 우세한 조건

- 출시 속도: 빠른 실험과 제품-시장 적합성(PMF) 탐색이 우선
- 모델 품질: 최신 멀티모달/프론티어 성능이 필요
- 운영 부담: MLOps 인력/인프라/보안·감사 체계가 미성숙

## 하이브리드가 표준이 되는 이유

- 핵심 워크로드(고정/대규모)는 인하우스/프라이빗으로, 탐색 워크로드(변동/실험)는 API로 라우팅하는 것이 비용/리스크/속도의 균형점이기 쉽다.
- 보안/거버넌스 요구가 커질수록 "모델"보다 "정책/평가/로그/감사" 레이어가 표준화된다.

## 데이터/거버넌스 체크리스트(산업 공통)

- 입력 데이터 분류(PII/PHI/기밀/저작권 콘텐츠), 보관/삭제 정책
- 출력 정책(금칙어/브랜드 가이드/민감정보 노출), 휴먼 리뷰 포인트
- 모델 리스크(환각/편향), 평가셋과 온라인 모니터링
- 출처/권리 추적(워터마킹/메타데이터, 라이선스 증빙)

## References

- Deloitte: GenAI 모달리티 사용 비중(텍스트/코드/오디오/이미지/비디오/3D) 설문 결과.[^deloitte-genai-2024]
- IDC: 전세계 AI 지출 및 GenAI 지출 전망(2028년 $632B, GenAI $202B 등).[^idc-ai-spend-2024]
- MarketsandMarkets: Generative AI 시장 규모/전망(2025-2032).[^mnm-genai-2025]

[^deloitte-genai-2024]: Deloitte. "The State of Generative AI in the Enterprise". https://www.deloitte.com/ce/en/services/consulting/research/state-of-generative-ai-in-enterprise.html (accessed 2026-02-09)
[^idc-ai-spend-2024]: IDC. "Worldwide Spending on Artificial Intelligence Forecast to Reach $632 Billion in 2028" (19 Aug 2024). https://my.idc.com/getdoc.jsp?containerId=prUS52530724 (accessed 2026-02-09)
[^mnm-genai-2025]: MarketsandMarkets. "Generative AI Market" (Published May 2025). https://www.marketsandmarkets.com/Market-Reports/generative-ai-market-142870584.html (accessed 2026-02-09)
