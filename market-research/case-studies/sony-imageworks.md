# Case Study: Sony Pictures Imageworks (Animation / Film)

**Title:** Spider-Man: Across the Spider-Verse의 머신러닝 잉크 라인 (ML Ink Line)
**Industry:** Animation / Film Production
**Subject:** 수작업의 감성을 유지하면서 대규모 3D 렌더링에 2D 펜 선을 자동 생성하는 ML 파이프라인

## 1. Executive Summary

Sony Pictures Imageworks는 영화 *<스파이더맨: 어크로스 더 유니버스>*의 독창적인 "코믹북 스타일"을 구현하기 위해 머신러닝(ML) 기술을 프로덕션 파이프라인에 도입했다. 수백 명의 아티스트가 모든 프레임에 잉크 선(Ink Line)을 그려넣는 것은 불가능했기에, 아티스트의 스타일을 학습한 ML 모델이 3D 지오메트리 위에 2D 펜 선을 자동으로 생성하고, 아티스트가 이를 수정하는 하이브리드 워크플로우를 구축했다.

## 2. The Challenge (문제 정의)

- **Scale Issue:** 전작보다 캐릭터와 배경의 디테일이 기하급수적으로 증가하여, 모든 장면에 수작업으로 펜 선(Hatching, Contours)을 그리는 것은 물리적으로 불가능.
- **Style Consistency:** 여러 아티스트가 작업하더라도 마치 한 명의 코믹북 작가가 그린 것처럼 일관된 펜 터치 스타일을 유지해야 함.
- **Geometry Limitation:** 단순한 3D 엣지 감지(Edge Detection) 알고리즘은 코믹북 특유의 불규칙하고 예술적인 선 느낌을 살리지 못함.

## 3. The Solution (해결 방안 및 기술 아키텍처)

### 3.1 ML Ink Line Tool
- **Training Data:** 아티스트들이 특정 캐릭터의 얼굴이나 포즈에 대해 "이상적인 펜 선"을 직접 그린 드로잉 데이터를 학습 데이터셋으로 구축.
- **Model:** 3D 캐릭터의 지오메트리 정보(Depth, Normal, Curvature)를 입력받아, 해당 위치에 아티스트 스타일의 펜 선이 그려질 확률을 예측하는 지도 학습 모델 개발.
- **Inference:** 렌더링 단계에서 ML 모델이 프레임별로 잉크 선을 생성하되, 단순히 선을 긋는 것이 아니라 "어디에 선이 끊겨야 하고(Breakup), 어디에 두껍게 들어가야 하는지"를 예술적으로 결정.

### 3.2 Human-in-the-Loop Workflow
- **Automation First:** ML이 초안(First Pass) 잉크 선을 생성하여 작업량의 70~80%를 자동화.
- **Artistic Control:** 아티스트는 ML이 생성한 결과물 위에 노드 기반 툴(Houdini 등)을 사용하여 선의 굵기, 위치, 스타일을 미세 조정하거나, 중요한 표정 연기 부분만 직접 다시 그리는 방식으로 작업 효율 극대화.

## 4. Results & Impact (성과)

- **Productivity:** 수천 샷에 달하는 영화 전체 분량에서 고퀄리티의 2D 스타일을 유지하면서도 제작 마감 기한 준수.
- **Visual Innovation:** 3D CG의 차가움을 없애고, 손으로 그린 듯한 따뜻하고 역동적인 코믹북 스타일의 영상미(NPR: Non-Photorealistic Rendering) 완성.
- **Award:** 아카데미 장편 애니메이션상 노미네이트 및 전 세계적인 시각 효과 호평.

## 5. Key Takeaways (시사점)

1.  **AI는 아티스트의 도구다:** AI가 아티스트를 대체한 것이 아니라, 반복적인 노동(단순 펜 선 채우기)을 제거하여 아티스트가 창의적인 연출에 집중할 수 있게 했다.
2.  **데이터가 스타일이다:** 특정 아티스트의 드로잉을 데이터로 학습시킴으로써, 그만의 고유한 화풍을 대량 생산 가능한 자산(Asset)으로 변환했다.
3.  **파이프라인 통합:** AI 모델을 독립적인 소프트웨어가 아니라, 기존 3D 제작 파이프라인(Maya, Houdini, Katana) 내에 자연스럽게 녹여내는 것이 성공의 열쇠다.

## References
- Sony Pictures Imageworks Tech Blog
- SIGGRAPH 2023 Technical Papers
