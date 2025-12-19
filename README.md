# 🌊 Surfancer: 환경 문제 해결을 위한 생존 디펜스 게임
> **"Surface + Survivor + Defense" : 오염된 지구 표면에서 살아남아라!**"

### 🛠️ Engine & Tools
<img src="https://img.shields.io/badge/Unity-000000?style=for-the-badge&logo=unity&logoColor=white"> <img src="https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=c-sharp&logoColor=white"> <img src="https://img.shields.io/badge/Adobe%20Photoshop-31A8FF?style=for-the-badge&logo=adobe%20photoshop&logoColor=white">

### 📝 Role & Contribution
<img src="https://img.shields.io/badge/Role-Main_Planner-FF5722?style=for-the-badge&logo=target&logoColor=white"> <img src="https://img.shields.io/badge/Task-Level_Design-blue?style=for-the-badge"> <img src="https://img.shields.io/badge/Task-System_Logic-blueviolet?style=for-the-badge">

### 🏆 Status
<img src="https://img.shields.io/badge/Award-Grand_Prize-F39C12?style=for-the-badge&logo=trophy&logoColor=white"> <img src="https://img.shields.io/badge/Social_Game_Contest-Winner-yellow?style=for-the-badge">

<br>

## 📌 1. Game Overview (게임 개요)
**Surfancer**는 'Surface(표면)'와 'Survivor(생존자)', 'Defense(방어)'를 결합한 제목으로, 환경 오염이라는 사회적 문제를 게임 시스템에 녹여낸 2D 탑다운 생존 디펜스 게임입니다.
플레이어의 행동(발전기 가동, 나무 심기 등)이 실시간으로 **타일맵의 오염도**를 변화시키고, 이것이 몬스터의 난이도와 자원 생성에 직접적인 영향을 미치도록 설계했습니다.

* **팀명:** 몰컴중 (물리/컴과/중문과 융합 팀)
* **장르:** Survival + Defense Strategy
* **핵심 메시지:** "극단적 상황에서도 인간성을 잃지 않고 환경을 구할 수 있는가?"

---

## 💡 2. Core Mechanics (핵심 시스템 기획)
![Dashboard Screenshot](./assets/Demo_UI.png)

### 2.1. Dynamic Pollution System (동적 오염도 시스템)
단순한 체력바가 아니라, **육각 타일(Hexagon Tile)** 단위로 오염도가 전이되는 로직을 설계했습니다.

* **Logic:** 중심 타일의 오염도는 이웃한 6개 타일 오염도의 평균값에 영향을 받습니다.
    > *Formula: Center_Pollution = Round(Average(Neighbor_Pollution_1...6))*
* **Feedback:** 오염도가 높으면(+n) 타일이 붉게 변하고 몬스터가 강해지며, 낮으면(-n) 녹색으로 변하고 청정 자원이 생성됩니다.

### 2.2. Resource Regeneration Algorithm (자원 리젠 알고리즘)
오염도 수치에 따라 자원(나무, 물)의 생성 주기를 수치적으로 기획하여 플레이어가 환경 보호의 필요성을 체감하게 했습니다.

| 환경 상태 | 나무 리젠 주기 (기획 데이터) |
| :--- | :--- |
| 오염 2~3단계 | **생성 불가 (0)** |
| 오염 1단계 | 30일에 1개 |
| 정화 1단계 | 20일에 1개 |
| **정화 3단계** | **5일에 1개 (최적 효율)** |

### 2.3. Day & Night Cycle (낮과 밤의 순환)
* **Day (Survival):** 오염된 지역을 탐험하며 'EM 원액', '청정수' 등 정화 아이템과 생존 자원 파밍.
* **Night (Defense):** 낮 동안의 활동 결과에 따라 몬스터 웨이브 강도가 달라짐. 나무를 많이 베면 몬스터 이동속도가 증가하는 등 **인과관계(Causality)** 구현.

---

## 🎨 3. Content Design (콘텐츠 기획)

### 🧩 Items & Crafting
* **EM(유용미생물) 활용:** 실제 환경 정화에 쓰이는 EM을 게임 내 핵심 아이템으로 도입하여 교육적 효과 유도.
* **Tower System:** 길막 타워(방어형), 함정 타워(CC기), EM 타워(적 느려짐) 등 전략적 타워 배치.

### 🎭 Multi-Ending System (멀티 엔딩)
플레이어의 선택에 따라 3가지의 분기된 결말을 제공합니다.
1.  **Escape (탈출):** 식물학자의 도움을 받아 친환경 연료를 개발, 우주선으로 지구 탈출.
2.  **Terraforming (치유):** 자연 세제 제작, 나무 심기 등을 통해 지구를 정화하고 진정한 생존 달성.
3.  **Mutation (배드 엔딩):** 오염에 잠식되어 플레이어가 몬스터(돌연변이)로 변이.

---

## 🛠️ 4. Retrospective (회고: 기획자의 시선)

* **시스템 기획의 구체화:** 추상적인 "환경 보호"라는 주제를 **'타일 오염도 평균값 연산'** 이라는 구체적인 게임 규칙으로 변환하며 시스템 기획력을 길렀습니다.
* **레벨 디자인 밸런싱:** 낮의 자원 수집량과 밤의 몬스터 웨이브 강도 사이의 밸런스를 조절하여, 긴장감을 유지하되 불합리하지 않도록 난이도 곡선을 설계했습니다.
* **팀 커뮤니케이션:** 개발자가 구현 가능한 로직(오염도 전이 알고리즘)을 문서화하여 제안하고, 디자이너에게 필요한 도트 리소스(오염 단계별 타일 색상)를 명확히 요청하여 PM으로서 협업을 주도했습니다.

---

## 📂 Repository Contents
* `/docs` : **기획서 원본 (Game Design Document)** 및 발표 자료 (PPT)
* `/assets` : 인게임 플레이 영상 및 스크린샷
