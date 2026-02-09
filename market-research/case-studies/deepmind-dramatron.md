# Case Study: DeepMind Dramatron (Co-Writing Tool)

**Title:** DeepMind Dramatron - 계층적 구조 생성을 통한 공동 집필(Co-Writing)
**Industry:** Theatre / Screenwriting / R&D
**Subject:** 대규모 언어 모델(LLM)을 활용하여 이야기의 일관성을 유지하며 대본을 공동 집필하는 인터랙티브 도구

## 1. Executive Summary

Google DeepMind가 개발한 **Dramatron**은 "AI가 긴 일관성 있는 텍스트를 생성하기 어렵다"는 한계를 극복하기 위해 **계층적 생성(Hierarchical Generation)** 방식을 도입한 도구이다. 전문 작가들과의 협업 테스트를 통해, AI가 단순한 문장 생성기가 아니라 '로그라인 → 캐릭터 → 플롯 → 씬'으로 이어지는 구조적 사고의 파트너가 될 수 있음을 증명했다.

## 2. The Challenge (문제 정의)

- **Long-Range Coherence:** 일반적인 챗봇은 이야기가 길어지면 앞뒤 맥락이 맞지 않거나, 캐릭터의 성격이 변하는 등 일관성을 잃기 쉽다.
- **Creative Control:** 작가들은 AI가 무작위로 쓴 텍스트를 원하지 않으며, 이야기의 구조와 흐름을 직접 통제하고 싶어 한다.

## 3. The Solution (해결 방안)

### 3.1 Hierarchical Generation (계층적 생성)
Dramatron은 한 번에 대본을 쓰지 않고, 탑다운(Top-down) 방식으로 작동한다.
1.  **Logline:** 사용자가 한 줄 요약(로그라인)을 입력.
2.  **Character:** 로그라인을 바탕으로 캐릭터 설명 생성.
3.  **Plot Outline:** 캐릭터와 로그라인을 바탕으로 씬별 요약(Outline) 생성.
4.  **Scene Dialogue:** 각 씬의 요약과 캐릭터 정보를 바탕으로 실제 대사 생성.
*작가는 각 단계에서 생성된 내용을 수정(Edit)할 수 있으며, 수정된 내용은 다음 단계 생성에 반영된다.*

### 3.2 Interactive Co-Authorship
- 작가는 생성된 결과물 중 마음에 드는 것을 선택(Cherry-picking)하거나, 직접 다시 쓸 수 있다.
- AI는 '완성품'을 내놓는 것이 아니라, 작가의 아이디어를 확장해주는 '계층적 인터페이스'를 제공한다.

## 4. Results & Impact (성과)

- **User Study:** 15명의 전문 작가(극작가, 시나리오 작가)가 Dramatron을 사용하여 단편 대본을 집필.
- **Theatrical Performance:** 캐나다 에드먼턴 프린지 페스티벌 등에서 Dramatron으로 집필된 대본이 실제 배우들에 의해 무대에서 공연됨.
- **Feedback:** 작가들은 AI가 생성한 대사를 그대로 쓰기보다는, **"구조적 아이디어"**와 **"예상치 못한 전개"**를 얻는 데 매우 유용하다고 평가함.

## 5. Key Takeaways (시사점)

1.  **Structure First:** 긴 글을 잘 쓰기 위해서는 문장력이 아니라 '구조(Structure)'를 먼저 설계해야 한다는 작법 원리를 AI 모델 설계에 반영함.
2.  **Human-in-the-Loop:** AI를 자율적인 창작 주체가 아니라, 인간 작가의 워크플로우 안에 통합된 도구로 설계할 때 가장 효과적임.
3.  **Inspiration Tool:** AI의 역할은 '대체'가 아니라 '영감(Inspiration)'과 '세계관 확장(World Building)'에 있음.

## References
- DeepMind Research Paper: "Co-Writing Screenplays and Theatre Scripts with Language Models" (2022)
- Mirowski et al., ACM Conference on Human Factors in Computing Systems (CHI) 2023
