---
title: 개인 대상 여정 노드
description: Journey Optimizer B2B에서 개인 대상 노드를 구성하여 동적 사용자 목록 또는 이벤트 기반 대상을 사용하여 여정에 입력하는 프로필을 지정합니다.
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%

---

# 개인 대상 노드

_개인 대상_ 노드는 여정에 들어오는 개인 프로필을 지정합니다. [개인 여정을 만듭니다](./person-journeys.md). 여정은 항상 입력을 정의하는 개인 대상 노드로 시작합니다. 개인 대상 노드에는 동적 사람 목록 또는 이벤트 트리거와 같은 두 가지 대상 입력 유형 중 하나가 있을 수 있습니다.

사용자 여정에 필요한 동적 사용자 목록이 이미 없는 경우 [사용자 목록을 만들고](../audiences/people-lists.md#create-a-people-list) 사용자 대상 노드를 구성하십시오.

여정 대상을 구성하려면(_T):_

1. **[!UICONTROL 개인 대상]** 노드를 클릭합니다.

   이 작업은 오른쪽에 노드 속성을 표시합니다.

   ![개인 대상 여정 노드](./assets/person-audience-node-properties.png){width="600" zoomable="yes"}

1. 개인 대상에 대해 다음 대상 구성 옵션 중 하나를 사용합니다.

   * **[!UICONTROL 동적 목록]** - 규칙 기반의 동적 사용자 목록을 사용합니다. 목록 규칙은 여정 런타임 시 평가되어 여정 멤버를 우량으로 선별합니다. 나중에 다이내믹 목록의 자격을 박탈하는 사람은 여정에서 제거되지 않습니다. _[동적 목록](../audiences/people-lists.md#dynamic-lists)_&#x200B;을 참조하세요.

   * **[!UICONTROL 이벤트 대상]** - 이벤트 대상을 사용하면 자격 있는 이벤트를 기반으로 여정 대상을 정의할 수 있습니다. 개인 프로필 필터링을 사용하여 대상 구성원을 정의하고 이벤트 기준을 사용하여 여정 항목을 트리거합니다. _[이벤트 기반 대상](../audiences/event-based-audiences.md)_&#x200B;을 참조하세요.