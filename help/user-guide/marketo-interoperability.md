---
title: Marketo Engage과의 상호 운용성
description: 데이터, 활동 및 대상을 포함하여 Marketo Optimizer이 Marketo Engage과 공유하는 내용과 여정 내 두 제품의 이메일을 보내는 방법에 대해 알아봅니다.
role: User, Admin
autotag-review: '2026-10-01T18:40:01.444Z'
TQID: 'https://experienceleague.adobe.com/7TB6JG9yiUT-l0VevNW4tvwieCyFjOypZwI0SlUzmmY'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
    internal-label: Audiences
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
  - id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
    internal-label: Programs
  - id: d4203578-d294-5145-b397-f26f4488a904
    internal-label: Channels
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 518a807aeed2471772b4f0a4d6d8d525cd3e22fd
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 0%
---

# Marketo Engage과의 상호 운용성

[!DNL Adobe Marketo Optimizer]과(와) [!DNL Adobe Marketo Engage]이(가) 데이터, 일부 활동 및 대상을 공유합니다. 자산을 별도로 유지합니다. 각 제품이 공유하는 내용을 파악하여 마케팅 자료를 작성하고 전송할 위치를 결정합니다.

## 제품 간에 공유됨 {#shared}

* [!DNL Marketo Engage]개의 리드와 활동이 [!DNL Marketo Optimizer]에 자동으로 유입됩니다.
* 여정은 [!DNL Marketo Engage] 활동을 수신할 수 있습니다.
* 이벤트 기반 대상에는 [!DNL Marketo Engage] 활동을 수행하는 사람이 포함될 수 있습니다.
* 여정 작업은 [!DNL Marketo Engage]과(와) 상호 작용할 수 있습니다. [!DNL Marketo Engage] 목록에 사용자를 추가하거나 목록에서 제거하고 [!DNL Marketo Engage] 캠페인을 요청할 수 있습니다.
* [!UICONTROL Scoring Studio]에서 [!DNL Marketo Engage] 및 [!DNL Marketo Optimizer]개 활동에 대해 사람 점수를 매깁니다. [!DNL Marketo Engage]에서 점수를 사용할 수 있습니다.
* 두 제품 모두 IP 주소와 하위 도메인을 공유합니다.
* 통합 대화 보고는 두 제품을 모두 다룹니다.

## 별도로 유지 {#separate}

* **Assets:** 전자 메일, 템플릿, 프로그램 및 이미지가 별도의 저장소에 있습니다.
* **활동:** [!DNL Marketo Optimizer] 활동이 [!DNL Marketo Engage]&#x200B;(으)로 다시 공유되지 않습니다.
* **필드 및 제한:** [!DNL Marketo Optimizer]에서 파생된 사용자 필드는 [!DNL Marketo Engage]에서 사용할 수 없습니다. 통신 제한은 각 제품에서 별도로 설정됩니다.

동기화 세부 정보는 [엔터티 동기화](./data-architecture.md#entity-sync)를 참조하십시오.

## Marketo Engage에서 이메일 보내기 {#send-from-marketo}

[!DNL Marketo Engage]이(가) 모든 전자 메일을 전송하는 동안 [!DNL Marketo Optimizer]에서 여정, 대기 단계 및 AI 의사 결정을 실행하려면 이 방법을 사용합니다.

1. [!DNL Marketo Optimizer]에서 대기 단계 및 AI 의사 결정을 포함하는 여정을 빌드합니다.
1. 각 전송 단계에 대해 **[!UICONTROL Marketo Engage 캠페인 요청]** 액션을 추가하고 일치하는 [!DNL Marketo Engage] 캠페인을 선택하십시오.
1. 선택 사항: [!DNL Marketo Engage]에 중요한 기본 프로그램을 추가하여 여정 전반의 성공 보고를 집계합니다.

작업에 대한 자세한 내용은 [작업 노드 만들기](./marketing/action-nodes.md)를 참조하십시오.

[!DNL Marketo Engage]이(가) 기존 채널 설정을 통해 전자 메일을 보냅니다. [!DNL Marketo Engage]에서 전자 메일을 보내므로 [!DNL Marketo Optimizer]에서 채널 또는 전자 메일을 구성하지 않습니다. 또한

* 전송, 열기 및 클릭이 [!DNL Marketo Engage]에 기록됩니다.
* 구독 취소 관리 및 전자 메일 거버넌스는 [!DNL Marketo Engage]에 적용됩니다.
* 전자 메일 활동은 기존 [!DNL Marketo Engage]개의 채점 캠페인을 피드합니다.
* 활동이 트리거된 Salesforce 동기화 캠페인은 예상대로 실행됩니다.
* 각 전송에는 [!DNL Marketo Engage] 캠페인이 매핑되므로 이메일 캠페인별로 프로그램 멤버십을 추적하고 익숙한 프로그램에서 보고할 수 있습니다.

## Marketo Optimizer에서 이메일 보내기 {#send-from-optimizer}

이 방법을 사용하여 여정을 빌드하고 이메일을 완전히 [!DNL Marketo Optimizer]에 보냅니다. [!DNL Marketo Engage]은(는) CRM(고객 관계 관리) 시스템에 대한 전환 기록 시스템으로 유지됩니다.

1. 이메일 채널을 설정합니다. 이메일 템플릿을 만들고 IP 주소 및 하위 도메인, 구독 취소 링크 및 랜딩 페이지를 구성합니다. [전자 메일 게재 기능](./start/email-deliverability.md)을 참조하세요.
1. [!DNL Marketo Optimizer]에서 통신 제한을 설정합니다. 공유 통신 제한을 사용할 수 없습니다.
1. 대상자, AI 의사 결정 및 다음 최적 경로로 여정을 구축합니다.
1. [!DNL Marketo Optimizer]에서 전자 메일을 보냅니다. [!DNL Marketo Optimizer]이(가) 활동을 기록합니다.
1. [!UICONTROL Scoring Studio]에서 사람들에게 점수를 매겨 [!DNL Marketo Engage] 및 [!DNL Marketo Optimizer] 활동에서 하나의 모델을 만듭니다. [채점 스튜디오](./labs/scoring-studio.md)를 참조하세요.

구독 취소는 공유 필드를 통해 [!DNL Marketo Engage]에 자동으로 동기화됩니다. [!DNL Marketo Optimizer] 전자 메일 활동이 [!DNL Marketo Engage]&#x200B;(으)로 다시 전송되지 않지만 [!UICONTROL Scoring Studio]에서 여전히 사용합니다.

### 잠재 고객을 판매로 전달 {#hand-off}

[!DNL Marketo Optimizer]에 직접 CRM 통합이 없습니다. 다음 방법 중 하나를 사용하여 [!DNL Marketo Engage]을(를) 통해 리드 라우팅:

* **점수 기준:** 점수 필드가 [!DNL Marketo Engage]에 나타나고 스마트 캠페인이 리드를 CRM과 동기화합니다.
* **활동 기반:** [!DNL Marketo Optimizer] 여정이 활동을 수신하고 [!DNL Marketo Engage] 스마트 캠페인에 잠재 고객을 추가합니다.
* **프로그램 구성원:** 여정이 [!DNL Marketo Optimizer] 프로그램에 있으므로 처음부터 끝까지 상태를 추적합니다.
