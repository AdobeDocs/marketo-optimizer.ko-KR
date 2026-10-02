---
title: 데이터 아키텍처
description: 엔티티 동기화 방향 및 지연, 활동 데이터 흐름 및 샌드박스 기반 데이터 격리를 포함하여 Marketo Optimizer 및 Marketo Engage이 데이터를 공유하는 방법을 알아봅니다.
role: User, Admin
autotag-review: '2026-10-01T18:40:38.362Z'
TQID: 'https://experienceleague.adobe.com/oelEtys81g6TzM8bi-qy1nuWw6scOBry7tbZkMkZ6u0'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
  - id: 3cf5f37e-e87e-5179-812b-53ce05d7eebb
    internal-label: Setup
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
    internal-label: Audiences
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
  - id: d4203578-d294-5145-b397-f26f4488a904
    internal-label: Channels
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
source-git-commit: 518a807aeed2471772b4f0a4d6d8d525cd3e22fd
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 1%
---

# 데이터 아키텍처

[!DNL Adobe Marketo Optimizer]은(는) B2B 리드에 대한 포괄적인 보기를 제공하기 위해 [!DNL Adobe Marketo Engage]과(와) 통합됩니다. 양방향 신뢰할 수 있는 동기화를 통해 두 제품이 서로 정렬되므로 사용자, 회사, 사용자 정의 개체 및 활동에 대한 하나의 보기를 공유할 수 있습니다. [!DNL Marketo Engage]은(는) 개인 데이터의 신뢰할 수 있는 소스로 유지됩니다. 각 [!DNL Marketo Optimizer] 인스턴스는 하나의 [!DNL Marketo Engage] 인스턴스와 연결되어 있습니다.

## 데이터 기반 {#data-foundation}

[!DNL Marketo Optimizer]과(와) [!DNL Marketo Engage]은(는) 다운스트림 분석을 제공하는 동안 동기화를 유지하는 공통 데이터 기반을 공유합니다.

두 제품의 서비스, 런타임 및 데이터 저장소가 Microsoft Azure 및 AWS에서 어떻게 연결되는지 보여 주는 ![Marketo Optimizer 및 Marketo Engage 아키텍처 다이어그램](./assets/marketo-optimizer-architecture.svg)

높은 수준에서:

* **[!DNL Marketo Engage]**&#x200B;은(는) 리드 및 사용자 지정 개체 데이터의 확실한 소스이며, 캡처 시점에 데이터 무결성을 보장합니다.
* **데이터 브로커 계층**&#x200B;은(는) 두 제품 간에 데이터가 이동하는 방식을 조정합니다. 공유 및 복제된 데이터를 사용할 준비가 된 운영 데이터베이스로 집계합니다. 전체 교환은 단일 Aurora MySQL 클러스터 내에서 실행됩니다.
* **[!DNL Marketo Optimizer]**&#x200B;은(는) 실행 중인 여정 활동에 대한 신뢰할 수 있는 소스입니다.

## 엔티티 동기화 {#entity-sync}

각 엔터티 유형은 데이터 무결성을 가장 잘 보호하는 방향과 속도로 동기화됩니다.

| [!DNL Marketo Engage] 엔터티 | 동기화 방향 | 지연 |
| --- | --- | --- |
| 리드 | 양방향 | 1초 미만 |
| 회사 | 양방향 | 1초 미만 |
| 사용자 지정 개체 | 단방향 | 5초 미만 |
| 활동 | 단방향 | 5초 미만 |
| 프로그램 멤버십 | 동기화되지 않음 | 적용할 수 없음 |
| 자산 | 동기화되지 않음 | 적용할 수 없음 |

동기화는 다음 두 가지 방식으로 작동합니다.

* **잠재 고객, 회사 및 표준 개체:** [!DNL Marketo Engage]은(는) 개인 테이블을 소유하며 데이터베이스 읽기 및 쓰기 보기를 통해 공유합니다. 한 제품의 업데이트는 다른 제품에 즉시 표시되며 중복 사본은 생성되지 않습니다.
* **사용자 지정 개체:** 데이터가 [!DNL Marketo Engage]에서 몇 초 내에 복제됩니다. 활성 여정이 [!DNL Marketo Engage]의 스키마 업데이트를 즉시 사용할 수 있습니다.

[!DNL Marketo Engage]과(와) [!DNL Marketo Optimizer]은(는) 프로그램 멤버십 또는 자산을 동기화하지 않습니다. 이 제외는 시스템 속도와 무결성을 유지합니다.

>[!NOTE]
>
>[!DNL Marketo Optimizer] 및 Data Warehouse에 동기화된 데이터는 결국 일관됩니다. 타이밍은 기본 변경 데이터 캡처, 일괄 처리 또는 스트림 메커니즘에 따라 다릅니다.

이 실시간에 가까운 설계는 여정 및 보고서의 현재 데이터를 제공합니다. 우선 순위가 높은 리드에 대해 빠르게 후속 작업을 수행할 수 있습니다. 제품 사용 및 의도와 같은 B2B 컨텍스트 데이터를 변경될 때 여정 결정에 사용할 수도 있습니다.

## 활동 데이터 흐름 {#activity-flow}

활동은 다른 엔티티와 별도의 경로를 따릅니다. 각 활동은 다음 5단계를 거칩니다.

1. **기본 캡처:** [!DNL Marketo Engage]은(는) [!DNL Marketo Engage] 내의 빠른 검색을 위해 공유 데이터베이스에 활동을 쓰고 Apache SOLR에서 인덱싱합니다.
1. **제품 간 인식:** [!DNL Marketo Engage]이(가) 활동을 활동 파이프라인에 게시하므로 [!DNL Marketo Optimizer]이(가) 즉시 받습니다.
1. **분석 변환:** 여정 런타임에서 활동을 처리하고 Snowflake에 기록하면 운영 데이터가 분석 준비가 된 데이터로 바뀝니다. 지금까지의 모든 단계는 Amazon Web Services(AWS)에서 실행됩니다.
1. **다운스트림 대상:** [!DNL Marketo Optimizer]이(가) 활동을 [!DNL Adobe Experience Platform]개의 데이터 집합에 복제합니다.
1. **보고:** 데이터 세트 피드에 [!DNL Adobe Customer Journey Analytics] 보고서가 포함되었습니다. [!DNL Customer Journey Analytics]은(는) Microsoft Azure 또는 AWS에서 호스팅할 수 있습니다. [!DNL Query Service]을(를) 사용하여 데이터 세트를 쿼리할 수도 있습니다. [Experience Platform 데이터 세트](./reports/aep-datasets.md)를 참조하세요.

여정 및 이벤트 대상자는 [!DNL Marketo Optimizer] 활동과 [!DNL Marketo Engage] 활동의 하위 집합을 모두 사용할 수 있습니다. 두 세트를 같은 방식으로 사용하시면 됩니다. [!DNL Marketo Optimizer]개의 활동이 [!DNL Marketo Engage]&#x200B;(으)로 다시 전송되지 않습니다.

양식 채우기, 웹 방문 및 이메일 참여와 같은 활동을 사용하여 개인 여정을 트리거, 필터링 및 분기합니다.

* [이벤트 노드 수신 대기에 대한 이벤트 트리거](./marketing/listen-for-event-nodes.md#event-triggers)
* [이벤트 노드 수신 대기용 이벤트 필터](./marketing/listen-for-event-nodes.md#event-filters)
* [분할 경로 노드에 대해 일치하는 개인 필터](./marketing/split-merge-paths-nodes.md#matched-person-filters)
* [이벤트 기반 대상](./audiences/event-based-audiences.md)

## 데이터 격리 및 샌드박스 {#data-isolation}

[!DNL Marketo Engage], [!DNL Marketo Optimizer] 및 [!DNL Experience Platform]이(가) 이 아키텍처의 일부로 고객 데이터를 공유합니다. Adobe은 [!DNL Experience Platform] 샌드박스를 사용하여 데이터를 다른 테넌트와 논리적으로 격리합니다. 데이터는 안전한 암호화 채널을 통해 이동합니다. Adobe은 업계 표준 암호화 및 액세스 제어를 사용하여 Adobe Managed Services에 저장합니다.

각 [!DNL Marketo Optimizer] 인스턴스에는 [!DNL Adobe Admin Console]의 전용 제품 카드와 전용 샌드박스가 있습니다. Adobe은 두 가지를 모두 자동으로 프로비저닝하므로 샌드박스를 생성하지 않습니다. 샌드박스 이름은 `mktoaep<prefix>` 패턴을 사용합니다. 여기서 접두사는 [!DNL Marketo Engage] 접두사입니다. [!DNL Marketo Optimizer]을(를) 둘 이상의 [!DNL Marketo Engage] 인스턴스와 함께 사용하는 경우 각 인스턴스에는 고유한 제품 카드와 샌드박스가 있습니다.

[!DNL Marketo Optimizer]은(는) 조직에 다른 샌드박스가 있는 경우에도 이 샌드박스에서만 사용할 수 있습니다.

프로비저닝에서 샌드박스 액세스 권한을 할당하지 않습니다. 역할은 일반적으로 기본 `prod` 샌드박스에 액세스할 수 있지만 [!DNL Marketo Optimizer]은(는) 이를 사용하지 않습니다. 전용 샌드박스를 각 [!DNL Experience Platform] 역할에 명시적으로 할당하십시오. 그렇지 않으면 사용자가 [!DNL Marketo Optimizer]에서 작업할 수 없습니다. 사용자 그룹을 사용하여 역할 설정을 반복하지 않고 사용자를 추가 및 제거합니다. 전체 프로시저는 [사용자 액세스 및 권한](./start/user-management.md)을 참조하십시오.

[!DNL Marketo Optimizer]은(는) 백그라운드에서 [!DNL Experience Platform]개의 서비스를 사용하기도 합니다. 여기에는 스키마 레지스트리, 유료 미디어 내보내기 대상, 액세스 제어 및 [!DNL Customer Journey Analytics]이 포함됩니다. 스키마나 네임스페이스는 설정하지 않습니다. [!DNL Marketo Optimizer]에는 [!DNL Real-Time Customer Data Platform], 실시간 고객 프로필 또는 세그먼테이션이 필요하지 않습니다.

>[!WARNING]
>
>전용 [!DNL Marketo Optimizer] 샌드박스를 삭제하지 마십시오. 삭제는 영구적이며 실행 취소할 수 없습니다. 복구하려면 [!DNL Marketo Optimizer]을(를) 다시 프로비전하세요.
