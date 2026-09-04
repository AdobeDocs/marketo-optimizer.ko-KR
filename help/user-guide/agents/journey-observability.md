---
title: 여정 진행률 모니터링 및 디버그
description: 동료 채팅에서 여정 관찰 가능성 기술을 사용하여 사람과 리드가 여정, 분할 경로 결정 및 타이밍을 어떻게 이동하는지 디버깅하고 모니터링하는 방법에 대해 알아봅니다.
source-git-commit: 9db94582512d95f6c07d4e978a0a27291b471900
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 0%

---

# 여정 진행률 모니터링 및 디버그

[!DNL Adobe Marketo Optimizer]의 [_여정 가시성_ 스킬](./skills.md#journeys)은(는) 사람과 리드가 여정을 통해 이동하는 방식에 대한 자연어 질문에 답합니다. [동료 채팅 인터페이스](./chat-interface.md)에서 진행률을 추적하고, 분할 경로 결정을 이해하고, 여정 노드 내의 사람을 분석하고, 시간 지표를 확인하는 데 사용합니다. 여정 간 행동 패턴에 대해서도 물을 수 있습니다.

* **스킬** - `journey-observability`
* **호출** - 자연어로 질문하거나 슬래시 명령을 사용하여 여정 관찰 스킬을 실행합니다. 예: _&quot;demo_ lead_24@company.com이 LeadGurtureJourney를 어떻게 이동했습니까?&quot;_
* **여정 데이터를**&#x200B;부터 [!DNL Marketo Optimizer]까지 읽으며, 목록 멤버십을 확인하기 위해 정적 목록 [!DNL Marketo Engage]개를 읽습니다.

## 개인 또는 가망 고객 세부 정보 보기 {#person-details}

개인 또는 잠재 고객에 대한 기본 읽기 전용 세부 정보를 물은 다음 해당 여정을 조사합니다. 개인의 이메일 주소, 잠재 고객 ID 또는 잠재 고객 이름을 입력합니다.

* _&quot;잠재 고객에 대한 기본 정보 제공 demo_ lead_24@company.com.&quot;_
* _&quot;프로필 john.doe@company.com의 직책 및 국가가 무엇입니까?&quot;_
* _&quot;lead_ 01에 대한 전자 메일과 역할을 표시합니다.&quot;_

## 여정 진행 추적 {#journey-progression}

개인 또는 잠재 고객이 여정을 통해 어떻게 이동했는지 질문하여 노드 수준의 시작, 종료, 기간 및 경로를 확인합니다. 개인의 이메일 주소 또는 잠재 고객 ID와 여정 이름을 입력합니다.

* _&quot;demo_ lead_24@company.com이 LeadGroothJourney를 어떻게 통과했습니까?&quot;_
* _&quot;제품 데모 여정에서 john.doe@company.com에서 전달한 노드는 무엇입니까?&quot;_

## 분할 경로 결정 이해 {#split-path-analysis}

개인 또는 잠재 고객이 분할된 노드에서 특정 경로를 택했거나 택하지 않은 이유를 묻습니다. 여정 관찰 가능성에서는 해당 시점에서 평가된 속성 값을 사용하여 결정을 설명합니다. 개인의 이메일 주소 또는 잠재 고객 ID, 여정 이름 및 분할 노드 ID를 입력합니다.

* _&quot;demo_ lead_24@company.com이 split 노드 c764a9의 &#39;많이 참여하는&#39; 경로로 이동한 이유는 무엇입니까?&quot;_
* _&quot;LeadGurtureJourney의 ab123f 노드에서 john.doe@company.com이 정규화된 경로를 사용하지 않은 이유는 무엇입니까?&quot;_
* _&quot;split 노드 x99f3b에서 lead_ 01과 lead_02가 다른 경로를 사용하는 이유를 비교합니다.&quot;_

## 여정 노드에서 사람 분석 {#node-analysis}

여정 노드 또는 분할 경로 내에서 개인 또는 잠재 고객 수 및 세부 정보를 요청합니다. 성향, 역할, 위치 또는 참여 수준별로 결과를 필터링합니다. 노드 ID를 입력합니다.

* _&quot;현재 node-459c7c의 &#39;높은 참여&#39; 경로에 있는 모든 사람을 제공합니다.&quot;_
* _&quot;데모 육성 여정의 자격 노드에는 몇 개의 리드가 있습니까?&quot;_
* _&quot;마케팅 관리자 역할로 필터링된 &#39;낮은 인텐트&#39; 분할 경로의 잠재 고객을 표시합니다.&quot;_

## 여정 간 패턴 식별 {#pattern-recognition}

여정 가시성에 여정 전반에서 공통 경로, 드롭오프 포인트 및 반복된 행동을 식별하도록 요청합니다. 여정 이름과 필요한 경우 결과 범위를 좁히기 위한 일정, 사용자, 제품 또는 계정을 입력합니다.

* _&quot;제품 데모 여정에서 SDR이 취하는 가장 일반적인 경로는 무엇입니까?&quot;_
* _&quot;LeadGroothJourney에서 리드가 주로 중단되는 위치는 어디입니까?&quot;_
* _&quot;1분기 교육 여정에 비정상적인 지연 또는 예기치 않은 경로 지정이 있습니까?&quot;_

## 시간 및 운영 지표 확인 {#operational-metrics}

여정에 대한 시작 시간, 대기 기간, 전환 지연 및 정지된 진행에 대해 질문합니다. 여정 이름과 필요한 경우 노드 ID 또는 개인 식별자를 제공합니다.

* _&quot;john.doe@company.com에서 언제 데모 후속 여정을 입력했습니까?&quot;_
* _&quot;잠재 고객이 LeadGroothJourney의 자격 노드에서 보통 얼마나 오래 대기합니까?&quot;_
* _&quot;7일 이상 데모 후속 여정에서 정지된 잠재 고객은 무엇입니까?&quot;_

## 제한 사항 {#limitations}

| 제한 사항 | 세부 정보 |
|---|---|
| 사용자 또는 잠재 고객 속성 편집 | 지원되지 않습니다. [!DNL Marketo Engage] 또는 [!DNL Marketo Optimizer]에서 직접 사용자 및 잠재 고객 레코드를 업데이트합니다. |
| 여정 만들기, 편집, 일시 중지 또는 재개 | 지원되지 않습니다. 대신 [여정 캔버스](../marketing/person-journeys.md) 또는 [동료 기술](./skills.md#journeys)의 여정 편집 기술을 사용하십시오. |
| 분할 논리 또는 여정 구성 변경 | 지원되지 않습니다. [여정 캔버스](../marketing/split-merge-paths-nodes.md)에서 직접 분할 경로를 편집합니다. |
| 구매 그룹 구성 또는 계정 수준 롤업 | 범위를 벗어났습니다. 여정 가시성 보고서는 개인 및 잠재 고객 수준에서만 보고합니다. |
| 여정 일정 또는 시간 변경 | 지원되지 않습니다. |
