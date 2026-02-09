# Case Study: Ubisoft (Game Development)

**Title:** Ubisoft Ghostwriter: 게임 작가를 위한 AI 대사 생성 도구
**Industry:** Game Development
**Subject:** 오픈월드 게임의 방대한 NPC 군중 대사(Barks) 작성 자동화 및 효율화

## 1. Executive Summary

Ubisoft는 오픈월드 게임의 몰입감을 높이는 데 필수적인 NPC들의 군중 대사(Barks)를 효율적으로 생성하기 위해 자체 R&D 부서인 Ubisoft La Forge에서 **'Ghostwriter'**라는 AI 도구를 개발했다. 이 도구는 작가들이 창의적인 메인 스토리와 캐릭터 개발에 집중할 수 있도록, 반복적이고 소모적인 "배경 대사" 작성 업무를 AI가 초안을 잡는 방식으로 혁신했다.

## 2. The Challenge (문제 정의)

- **Volume:** 오픈월드 게임(예: Assassin's Creed, Watch Dogs)은 수천 명의 NPC가 등장하며, 이들이 상황에 따라 외치는 짧은 대사(전투 중 비명, 인사, 잡담 등)가 수만 줄 필요함.
- **Repetitiveness:** "저기 봐!", "공격하라!", "도망쳐!"와 같은 단순한 대사를 수백 가지 버전으로 변형(Variation)해서 작성하는 것은 작가들에게 지루하고 창의력을 소모하는 노동임.
- **Immersion:** 플레이어의 몰입을 위해 같은 대사가 반복해서 들리지 않도록 엄청난 양의 변형이 필수적임.

## 3. The Solution (해결 방안 및 기술 아키텍처)

### 3.1 Ghostwriter Architecture
- **In-house LLM Tool:** 외부의 범용 LLM API를 그대로 쓰는 것이 아니라, Ubisoft 게임 데이터에 특화된 모델을 자체적으로 튜닝하여 사내 도구로 구축.
- **Workflow:**
    1.  **Input:** 작가가 상황(예: "적을 발견했을 때"), 캐릭터 성격(예: "겁이 많은 병사"), 문장 스타일을 입력.
    2.  **Generation:** Ghostwriter가 해당 조건에 맞는 수십 개의 대사 변형(Variation) 후보를 생성.
    3.  **Selection & Edit:** 작가는 생성된 목록에서 마음에 드는 것을 선택하거나, 약간 수정하여 최종 대사로 확정. (Human-in-the-Loop)

### 3.2 Design Philosophy
- **"Not Replacing, But Assisting":** 도구의 이름을 'Ghostwriter(대필 작가)'로 지은 것은, AI가 최종 저작자가 아니라 인간 작가를 돕는 보조적 역할임을 명확히 하기 위함.
- **Crowd Barks Focus:** 메인 스토리나 감정적인 컷신 대사는 인간이 전담하고, AI는 오직 '군중 대사(Barks)'와 같은 기능적 텍스트에만 집중하도록 범위 제한.

## 4. Results & Impact (성과)

- **Efficiency:** 작가들이 단순 대사 변형을 만드는 데 쓰는 시간을 획기적으로 줄여, 퀘스트 디자인이나 메인 스토리 집필 등 더 중요한 업무에 시간을 쏟을 수 있게 됨.
- **Scale:** 이전보다 훨씬 더 다양하고 방대한 양의 군중 대사를 게임에 집어넣을 수 있어, 오픈월드의 청각적 디테일과 몰입감 향상.
- **Adoption:** GDC(Game Developers Conference) 발표 등을 통해 게임 업계 내 '생성형 AI의 올바른 활용 사례'로 자리 잡음.

## 5. Key Takeaways (시사점)

1.  **지루한 일을 자동화하라:** 창작자들에게 AI를 도입할 때 가장 설득력 있는 접근은 "당신이 하기 싫어하는 반복 업무를 대신 해주겠다"는 것이다.
2.  **도구의 주도권은 인간에게:** AI가 100% 자동 생성해서 게임에 바로 넣는 것이 아니라, 작가가 '선택'하고 '수정'하는 권한을 가질 때 품질과 수용성이 모두 높아진다.
3.  **목적별 특화:** 모든 대사를 다 쓰는 만능 AI보다, '군중 대사'라는 특정 니즈에 최적화된 도구가 실무에서는 더 강력하다.

## References
- Ubisoft News: "Ubisoft La Forge unveils Ghostwriter"
- GDC 2023 Presentations
