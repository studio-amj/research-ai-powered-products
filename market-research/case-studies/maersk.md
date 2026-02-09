# Case Study: Maersk (Logistics / IoT)

**Title:** Maersk Captain Peter: 바다 위 컨테이너와 대화하다 (IoT + Edge AI)
**Industry:** Logistics / Supply Chain
**Subject:** 냉동 컨테이너(Reefer) 실시간 모니터링을 위한 IoT, 위성 통신, Edge AI의 결합

## 1. Executive Summary

![Maersk Captain Peter](../images/maersk_dashboard.jpg)

Maersk는 전 세계 38만 개의 냉동 컨테이너를 실시간으로 모니터링하기 위해 'Captain Peter'라는 디지털 비서를 도입했다. 망망대해에서의 통신 단절 문제를 **Starlink 위성 통신**과 **선박 내 프라이빗 LTE**로 극복하고, 엣지(Edge) 단에서 데이터를 수집/분석하여 화주에게 화물의 상태(온도, 위치)를 실시간으로 제공함으로써 물류의 투명성을 혁신했다.

## 2. The Challenge (문제 정의)

- **Black Hole:** 컨테이너가 바다로 나가면 통신이 두절되어 도착할 때까지 화물 상태(특히 신선식품, 의약품의 온도)를 알 수 없음.
- **Cargo Loss:** 냉동기 고장이나 설정 오류로 인해 바나나, 아보카도 등 민감한 화물이 운송 중 부패하여 막대한 손실 발생.
- **Connectivity:** 깊은 바다(Deep Sea)와 선박의 깊숙한 적재 공간(Cargo Hold)은 전파가 닿지 않는 통신의 불모지.

## 3. The Solution (해결 방안 및 기술 아키텍처)

### 3.1 RCM (Remote Container Management) System
- **Smart Reefers:** 38만 개 이상의 모든 냉동 컨테이너에 IoT 모뎀과 센서(온도, 습도, O2/CO2, 위치, 충격 감지)를 기본 장착.
- **Edge Computing:** 컨테이너 내 모뎀이 1차적으로 데이터를 수집하고 이상 징후를 감지. 통신이 끊겨도 데이터를 자체 저장(Buffering)했다가 연결 시 전송.

### 3.2 Connectivity: Hybrid Network
- **On-Vessel (Private LTE):** 선박 내에 Nokia와 협력하여 **'OneWireless' 프라이빗 4G/LTE 망**을 구축. 두꺼운 강철 벽으로 둘러싸인 선박 내부 깊숙한 곳의 컨테이너 신호까지 포착.
- **Satellite Backhaul (Starlink):** 선박에 모인 데이터는 **SpaceX의 Starlink(저궤도 위성)**를 통해 지상으로 전송. 기존 VSAT 위성 대비 대역폭은 100배, 지연시간(Latency)은 1/10로 단축.

### 3.3 User Interface: Captain Peter
- **Digital Assistant:** 화주에게 웹/앱을 통해 화물의 상태를 보여주는 챗봇 형태의 비서.
- **Alerts:** 온도가 설정 범위를 벗어나거나(Temperature Deviation), 전원이 차단되면 즉시 화주에게 알림 발송.

## 4. Results & Impact (성과)

### 4.1 Operational Efficiency
- **Real-time Visibility:** 과거 12~24시간 지연되던 데이터가 이제는 **'Near Real-time' (매 시간 업데이트)** 수준으로 제공됨.
- **Proactive Intervention:** 운송 중 온도 이상 감지 시, Maersk 운영팀이 원격으로 냉동기 설정을 조정하거나, 도착 항구에서 즉시 수리/검수하도록 조치하여 화물 폐기를 예방.

### 4.2 Business Value
- **Sustainability:** 과일 숙성 제어(Controlled Atmosphere) 데이터를 통해 음식물 쓰레기(Food Waste)를 줄이고 탄소 배출 감축에 기여.
- **Transparency:** "믿고 맡겨라"가 아닌 "직접 확인하라"는 투명성을 제공하여 화주와의 신뢰 구축 및 프리미엄 서비스(Captain Peter Plus) 수익 창출.

## 5. Key Takeaways (시사점)

1.  **인프라가 없으면 만들어라:** Maersk는 통신사가 망을 깔아주길 기다리지 않고, 직접 배 안에 기지국(Private LTE)을 세우고 위성(Starlink)을 달았다. 딥테크(Deep Tech) 없이는 혁신도 없다.
2.  **Edge AI의 중요성:** 통신이 불안정한 환경에서는 클라우드만 믿을 수 없다. 디바이스(컨테이너) 스스로 데이터를 판단하고 저장하는 엣지 컴퓨팅 능력이 필수다.
3.  **데이터는 고객에게 돌려줘라:** 내부 관리용으로 수집하던 데이터를 가공하여 고객에게 서비스(Captain Peter)로 제공함으로써, '데이터' 자체를 '상품'으로 전환했다.

## References
- Maersk Digital Services Blog
- Nokia & Maersk 'OneWireless' Press Release
- Starlink Maritime Announcements
