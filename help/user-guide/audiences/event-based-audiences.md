---
title: 이벤트 기반 대상
description: Marketo Optimizer의 이벤트 기반 대상을 사용하여 Marketo Engage 활동을 기반으로 거의 실시간으로 개인 여정 항목을 트리거할 수 있습니다.
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 0%

---

# 이벤트 기반 대상

[!DNL Adobe Marketo Optimizer]에서 _이벤트 기반 대상_&#x200B;을(를) 사용하면 [!DNL Marketo Engage] 활동이 발생할 때 거의 실시간으로 실시간 [개인 여정](../marketing/person-journeys.md)에 대상 구성원을 추가할 수 있습니다. 여정 캔버스의 대상 노드에서 이벤트 기반 대상을 구성합니다.

* 하나 이상의 [!DNL Marketo Engage] 활동(표준 또는 사용자 지정)을 자격 이벤트로 선택합니다.
* 개인 프로필 필터(예: 산업, 지역 또는 라이프사이클 단계)를 추가하여 사용자가 입력할 수 있는 범위를 좁힐 수 있습니다(선택적).
* 선택적으로 활동 속성 제한(예: 특정 양식, URL 또는 프로그램)을 정의하여 각 활동의 발생 횟수를 좁힐 수 있습니다.

자격 있는 활동이 잠재 고객에 대해 [!DNL Marketo Engage]에 로그인하고 [!DNL Adobe Marketo Optimizer]에 복제되면 시스템은 구성된 필터 및 제한에 대해 해당 개인 레코드를 평가합니다. 조건이 충족되면 대상자는 대상자 노드를 통해 즉시 여정에 들어갑니다.

개인 여정에 대한 이벤트 기반 대상자를 정의하려면(_T):_

1. [_개인 대상_ 노드](../marketing/person-audience-node.md)를 선택하십시오.

1. 오른쪽의 노드 속성에서 항목 유형으로 **[!UICONTROL 이벤트 대상]**&#x200B;을 선택합니다.

   ![개인 대상 여정 노드가 이벤트 기반 대상으로 설정됨](./assets/event-based-audience-node.png){width="400"}

1. **[!UICONTROL 이벤트 조건 추가]**&#x200B;를 클릭합니다.

1. _[!UICONTROL 이벤트 기준 편집]_ 대화 상자에서 다음과 같이 하나 이상의 [!DNL Marketo Engage] 활동을 자격 있는 이벤트로 추가합니다.

   * _웨비나에 참여_
   * _전자 메일 전달됨_
   * _전자 메일의 링크 클릭_

   >[!NOTE]
   >
   >연결된 [!DNL Marketo Engage] 인스턴스에 정의된 사용자 지정 활동을 선택할 수도 있습니다.

   각 활동에 대해 일치하는 연산자 및 값을 설정합니다.

   이벤트 기반 대상자에 대한 ![활동 트리거](./assets/event-based-audience-triggers.png){width="700" zoomable="yes"}

   구성된 활동 중 하나가 해당 잠재 고객에 대해 기록되면 개인이 여정 자격을 갖습니다.

1. (선택 사항) 대상 자격에 대한 이벤트 및 필터 조합을 사용하려면 개인 수준 필터를 추가합니다.

   * **[!UICONTROL 필터]** 탭을 선택합니다.
   * 각 필터를 드래그하고 일치 기준을 설정합니다.

   이벤트 기반 대상자에 대한 ![개인 필터](./assets/event-based-audience-filters.png){width="700" zoomable="yes"}

   필터를 추가하는 경우 개인은 구성된 활동 조건 및 구성된 필터를 하나 이상 충족해야 합니다.

1. **[!UICONTROL 저장]**&#x200B;을 클릭합니다.