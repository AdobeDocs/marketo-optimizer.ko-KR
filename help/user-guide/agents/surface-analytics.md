---
title: Analytics 보고서 생성
description: 동료 채팅에서 Surface Analytics 기술을 사용하여 자연어 프롬프트에서 활동, 이메일, 리드, 세그먼트 및 여정 보고서를 생성하는 방법을 알아봅니다.
autotag-review: '2026-09-21T14:58:26.479Z'
TQID: 'https://experienceleague.adobe.com/BSDEihjdpz-YZjMWrYTmIuyjqtcjRHRrJdz4xPFZbHU'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 1650dadf-b034-5ac9-a309-77ad1e2f5035
    internal-label: Chat Interface
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
subfeature_v2:
  - id: b9e5c7f3-be30-563c-9e41-cc8ea76e2fee
    internal-label: Skills
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: 1dcc3bcdc59114c7fc1e16178db8921ae173b955
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%
---
# 분석 보고서 생성

[!DNL Adobe Marketo Optimizer]의 [_Surface Analytics_ 스킬](./skills.md#analytics-reporting)은(는) 데이터에 대한 자연어 질문에 답합니다. [동료 채팅 인터페이스](./chat-interface.md)에서 활동 트렌드, 전자 메일 성능, 리드 및 계정 데이터, 세그먼트 및 목록 멤버십, 여정 지표를 살펴볼 수 있습니다. 결과는 차트 및 표로 반환되므로 쿼리 또는 대시보드를 수동으로 빌드할 필요가 없습니다.

* **스킬** - `surface-analytics`
* **호출** - 자연어로 질문하거나 슬래시 명령을 사용하여 Surface Analytics 스킬을 실행합니다. 예: _&quot;지난 30일 동안의 일일 활동 수를 표시합니다.&quot;_
* **다음 기간 동안 분석 데이터를 읽음** - [!DNL Marketo Optimizer], 두 제품에 걸친 질문에 대한 분석 데이터를 읽음 [!DNL Marketo Engage]

>[!NOTE]
>
>보고서 데이터는 2시간마다 새로 고침됩니다. 결과는 지난 2시간의 활동을 반영하지 않을 수 있습니다.

## 활동 트렌드 보기 {#activity-trends}

일별 또는 주별 활동 수에 대해 질문하고 활동 유형 또는 제품 영역별로 결과를 분류합니다.

* _&quot;지난 30일 동안의 일일 활동 수를 표시합니다.&quot;_
* _&quot;이번 주 상위 활동 유형은 무엇입니까?&quot;_
* _&quot;앱 영역별로 지난달 활동을 분류합니다.&quot;_

## 이메일 성능 확인 {#email-performance}

이메일 프로그램의 전송 볼륨, 열람 및 클릭률, 바운스 및 구독 취소에 대해 질문합니다.

* _&quot;여정에 따른 이메일 열람률은 얼마입니까?&quot;_
* _&quot;지난 90일 동안의 클릭률을 표시합니다.&quot;_
* _&quot;지난 주에 받은 구독 취소 수는 몇 개입니까?&quot;_

## 리드 및 계정 데이터 분석 {#lead-account-data}

잠재 고객 스코어 배포, 사용자 분류 및 지리적 또는 그래픽 롤업에 대해 질문합니다.

* _&quot;잠재 고객 간 점수 분포를 보여 주십시오.&quot;_
* _&quot;각 계정에 몇 명이 있습니까?&quot;_
* _&quot;담당자별로 잠재 고객 분류&quot;_

## 세그먼트 및 목록 멤버십 검토 {#segment-list-membership}

특정 목록 또는 세그먼트에 속하는 사람을 확인합니다.

* _&quot;1분기 육성 목록에 몇 명이 있습니까?&quot;_
* _&quot;구성원이 가장 많은 세그먼트는 무엇입니까?&quot;_

## 여정 지표 탐색 {#journey-metrics}

여정 멤버십, 완료율, 노드 트래버스 및 funnel 분석에 대해 질문합니다.

* _&quot;데모 후속 여정 완료율은 얼마입니까?&quot;_
* _&quot;LeadGroothJourney의 각 노드에 몇 명이 있습니까?&quot;_

## 제품 전반에 걸쳐 질문하기 {#cross-product}

Surface Analytics는 한 번의 프롬프트에서 [!DNL Marketo Engage]과(와) [!DNL Marketo Optimizer] 데이터 모두에 걸쳐 있는 질문에 답변할 수 있습니다.

* _&quot;LumaSecure 및 LumaStorage에서 가장 성과가 좋은 전자 메일은 무엇입니까?&quot;_

## 제한 사항 {#limitations}

| 제한 사항 | 세부 정보 |
|---|---|
| 레코드 편집 또는 만들기 | 지원되지 않습니다. Surface Analytics는 기존 데이터에 대한 읽기 및 보고만 수행합니다. |
| 사람이 인식할 수 있는 결과 이름 | 항상 사용 가능한 것은 아닙니다. 일부 보고서에는 이름 대신 여정 또는 이메일 ID와 같은 내부 ID가 표시됩니다. |
| 보고서 카드 복제 | 하나의 질문이 동일한 결과에 대해 두 개 이상의 보고서 카드를 반환하는 경우가 있습니다. |
