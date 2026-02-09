# Case Study: Lionsgate x Runway (GenAI Partnership)

**Title:** Lionsgate x Runway - 스튜디오 아카이브 기반의 맞춤형 비디오 생성 모델
**Industry:** Film Production / Studio
**Subject:** 기존 IP 자산(Archive)을 활용한 맞춤형 비디오 생성 모델 개발 및 프리비즈(Pre-viz) 혁신

## 1. Executive Summary

2024년 9월, <존 윅>, <헝거게임> 등을 제작한 메이저 스튜디오 **Lionsgate**는 AI 비디오 기업 **Runway**와 파트너십을 체결했다. 이는 할리우드 메이저 스튜디오가 생성형 AI 기업과 맺은 최초의 대규모 파트너십으로, 스튜디오가 보유한 방대한 영상 자산을 학습시켜 **"Lionsgate 전용 모델"**을 구축하고, 이를 프리비즈(Pre-visualization) 및 스토리보드 제작에 활용하는 사례다.

## 2. The Challenge (문제 정의)

- **Inefficient Pre-production:** 영화 기획 단계에서 스토리보드와 프리비즈(사전 시각화)를 만드는 데 많은 시간과 비용이 소요됨.
- **Generic AI limitations:** 시중의 범용 비디오 생성 모델(Sora, Gen-3 등)은 스튜디오 고유의 톤앤매너, 특정 배우의 스타일, 기존 IP의 시각적 특징을 정확히 구현하지 못함.

## 3. The Solution (해결 방안)

### 3.1 Custom Model Training
- **Data:** Lionsgate가 보유한 20,000개 이상의 영화 및 TV 타이틀 아카이브를 학습 데이터로 활용.
- **Technology:** Runway의 Gen-3 Alpha 등 최신 비디오 생성 모델을 기반으로 하되, Lionsgate의 영상 문법과 스타일을 파인튜닝(Fine-tuning)하거나 LoRA(Low-Rank Adaptation) 방식으로 적용.

### 3.2 Integrated Workflow
- **Storyboard-to-Video:** 대본이나 간단한 스케치를 입력하면, 기존 <존 윅> 스타일의 액션 시퀀스나 <트와일라잇> 풍의 조명/색감을 반영한 고품질 프리비즈 영상을 생성.
- **Internal Tool:** 이 모델은 외부 공개용이 아닌, Lionsgate 내부의 감독, 작가, 아티스트들이 사용하는 창작 도구로 제공됨.

## 4. Expected Impact (기대 효과)

- **Cost & Time Reduction:** 기획 및 프리 프로덕션 단계의 비용과 시간을 획기적으로 단축. 투자 결정(Greenlight)을 위한 시각 자료를 빠르게 확보.
- **Creative Consistency:** 시리즈물의 경우, 전작의 스타일을 완벽하게 계승한 시각적 레퍼런스를 생성하여 제작진 간의 커뮤니케이션 오류를 줄임.

## 5. Key Takeaways (시사점)

1.  **Asset Value:** 스튜디오가 가진 '과거의 콘텐츠(IP)'가 AI 시대에는 '학습 데이터'라는 새로운 자산 가치를 갖게 됨.
2.  **Enterprise Customization:** 범용 모델 API를 그대로 쓰는 것이 아니라, 기업 고유 데이터로 커스터마이징하는 'Private/Vertical AI'가 엔터테인먼트 산업의 표준이 되고 있음.
3.  **Legal Safety:** 합법적으로 보유한 저작물을 학습시켰으므로, 저작권 이슈에서 자유로운 'Clean Model'을 구축할 수 있음.

## References
- Lionsgate Press Release (Sep 2024)
- Runway Official Blog
- Variety / Hollywood Reporter Articles
