---
title: 대상
description: 필요한 권한, 지원되는 대상 및 Marketo Optimizer에서 대상을 연결하여 광고 및 소셜 플랫폼에 정적 사용자 목록을 활성화하는 방법에 대해 알아봅니다.
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 6%

---

# 대상

대상은 [!DNL Marketo Optimizer]에서 외부 광고 또는 소셜 플랫폼(예: LinkedIn 캠페인 대상, Google Customer Match 대상 또는 Facebook 사용자 지정 대상)으로 [정적 사람 목록](./people-lists.md#static-lists)을 보낼 수 있는 미리 빌드된 통합입니다. 정적 목록을 대상으로 활성화하면 구성원이 목록에 추가되거나 제거될 때 대상 대상 대상 대상 및 확장에 따라 대상이 피딩하는 모든 캠페인에서 해당 구성원이 추가되거나 제거됩니다.

연결된 대상에 사용자를 활성화하는 방법에는 두 가지가 있습니다.

* **정적 목록에서** — **_[!UICONTROL 사람 목록]_** 탭에서 직접 기존 정적 목록을 활성화합니다. [대상에 활성화](./people-lists.md#static-list-activate)를 참조하십시오.
* **사용자 여정에서** — 해당 노드에 도달한 모든 사용자가 목록에 추가되고 대상으로 전송될 수 있도록 여정 경로에 **_[!UICONTROL 대상에 활성화]_** 작업을 추가합니다. [_작업 노드 추가_](../marketing/action-nodes.md#add-an-action-node)&#x200B;를 참조하십시오.

>[!BEGINSHADEBOX]

## 필요한 권한 {#required-permissions}

전체 대상 기능을 사용하려면 다음 [!DNL Adobe Experience Platform] 권한이 활성화되어야 합니다.

| 카테고리 | 사용 권한 | 필수 |
|--- |--- |--- |
| 샌드박스 | 샌드박스 액세스 _(기본적으로 활성화됨)_ | 예 |
| 대시보드 | 표준 대시보드 보기 | 예 |
| 대시보드 | 표준 대시보드 관리 | 예 |
| 대상 | 대상 보기 | 예 |
| 대상 | 대상 관리 | 예 |
| 대상 | 대상 활성화 | 예 |
| 대상 | 매핑 없이 세그먼트 활성화 | 예 |
| 대상 | 데이터 세트 대상 관리 및 활성화 | 예 |
| 대상 | 대상 작성 | 예 |
| 데이터 거버넌스 | 데이터 사용 정책 보기 | 예 |
| 데이터 거버넌스 | 데이터 사용 정책 관리 | 예 |
| 데이터 수집 | 소스 보기 | 예 |
| 데이터 수집 | 소스 관리 | 예 |
| 프로필 관리 | 프로필 설정 보기 | 예 |
| 프로필 관리 | 프로필 설정 관리 | 예 |

>[!ENDSHADEBOX]

## 지원되는 대상 {#supported-destinations}

정적 목록을 활성화하려면 대상 카탈로그에 대상이 있어야 합니다. 왼쪽 탐색에서 **[!UICONTROL 연결]**&#x200B;을 확장하고 **[!UICONTROL 대상]**&#x200B;을 선택합니다. [!DNL Marketo Optimizer]은(는) 현재 다음 대상을 지원합니다.

* **[!UICONTROL Google Customer Match]**(Advertising)
* **[!UICONTROL Facebook 사용자 지정 대상]**(소셜)
* **[!UICONTROL 일치하는 대상자]**(소셜)

![사용 가능한 커넥터 유형에 액세스](./assets/destinations-catalog.png){width="800" zoomable="yes"}

>[!NOTE]
>
>이 카탈로그는 전체 [!DNL Adobe Experience Platform] 대상 카탈로그가 아닙니다. [!DNL Experience Platform]에서 바로 대상에 액세스하는 경우 더 큰 카탈로그가 표시되지만 현재 [!DNL Marketo Optimizer]에서 활성화할 수 있는 대상만 있습니다. 향후 릴리스를 위해 추가 대상이 계획되어 있습니다.

## 대상 설정 {#set-up-destination}

지원되는 각 대상 카드에 **[!UICONTROL 새 대상 구성]**&#x200B;이 표시됩니다. 활성화 전 요구 사항은 대상을 구성하는 것입니다.

1. 커넥터 카드에서 **[!UICONTROL 새 대상 구성]**&#x200B;을 클릭합니다.

1. **[!UICONTROL 기존 계정]** 또는 **[!UICONTROL 새 계정]**&#x200B;을 선택하고 계정 이름, 설명 등 계정 세부 정보를 입력하십시오.

   ![새 대상 계정 연결](./assets/destinations-configure-new.png){width="500"}

1. **[!UICONTROL 대상에 연결]**&#x200B;을 클릭합니다.

   OAuth 흐름을 사용하면 해당 계정인 LinkedIn, Google 또는 Facebook에 로그인할 수 있습니다.

   >[!IMPORTANT]
   >
   >이 시점에서 **하지 않음** _[!UICONTROL 대상 세부 정보]_&#x200B;를 입력하십시오. 연결만 필요합니다.

1. 사용자 속성과 대상에 필요한 필드 간의 필수 필드 매핑을 완료합니다.

1. 데이터 거버넌스 및 마케팅 작업 설정을 검토한 다음 **[!UICONTROL 저장]**&#x200B;을 클릭합니다.

전체 설정 단계는 [!DNL Experience Platform] 설명서에서 [새 대상 연결 만들기](https://experienceleague.adobe.com/ko/docs/experience-platform/destinations/ui/connect-destination){target="_blank"}를 참조하십시오.

구성된 경우 [!DNL Marketo Optimizer]에서 대상을 선택할 수 있는 모든 곳에서 대상을 활성화할 수 있습니다.

## 활성화 및 동기화 {#activation-sync}

활성화는 목록과 대상 대상 대상 간의 양방향 동기화를 통해 정적 목록 멤버십에 의해 결정됩니다.

* 정적 목록에 개인을 추가하면 24시간 내에 대상에 활성화되고 대상 대상에 추가되며 이후 대상이 피딩하는 모든 캠페인에 추가됩니다.
* 정적 목록에서 사용자를 제거하면 대상에서 비활성화됩니다. 대상 대상자 및 연결된 캠페인에서 제거됩니다.
* 동일한 목록을 여러 대상에 한 번에 활성화할 수 있습니다. 멤버십이 모든 대상에 동기화됩니다.

>[!TIP]
>
>세그먼트에 대해 LinkedIn 캠페인을 실행하려면 LinkedIn 일치하는 대상 대상에 이러한 사람들의 정적 목록을 활성화합니다. 목록의 모든 사람은 LinkedIn에서 일치하는 대상자에 추가됩니다. 여기서 캠페인은 이러한 대상자를 타깃팅할 수 있으며 대상자는 목록이 변경될 때 자동으로 현재 상태를 유지합니다.
