---
title: 사용자 목록
description: 여정 타깃팅, 동적 규칙 기반 멤버십 및 정적 목록 대상 활성화를 위해 Marketo Optimizer에서 사람 목록을 만들고 관리합니다.
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '1145'
ht-degree: 1%

---

# 사용자 목록

[!DNL Adobe Marketo Optimizer]에서 사람 목록은 타깃팅과 개인 여정 항목을 위한 개인 수준 대상 컨테이너이며, 규칙 기반 라이브 자격에 대한 동적 목록과 고정 또는 여정 관리 멤버십에 대한 정적 목록이 있습니다.

## 직원 목록 액세스 및 찾아보기 {#access-browse}

1. 왼쪽 탐색에서 **[!UICONTROL 마케팅 관리]**&#x200B;를 확장합니다.

1. **[!UICONTROL 마케팅]** 리소스 목록의 오른쪽에서 **[!UICONTROL 사람 목록]**&#x200B;을 선택합니다.

   ![대상자 목록을 관리하도록 액세스](./assets/people-lists.png){width="800" zoomable="yes"}

**[!UICONTROL 동적 목록]**&#x200B;과 **[!UICONTROL 정적 목록]**&#x200B;을 보고 관리할 수 있는 두 가지 탭이 있습니다. 탭을 클릭하여 두 유형 간에 목록 보기를 전환합니다.

목록 맨 위에 있는 _검색_ 도구에 텍스트를 입력하여 표시된 목록을 이름별로 필터링할 수 있습니다. 목록 도구를 사용하여 표시된 목록을 사용자 정의합니다.

* _표 사용자 지정_( ![표 사용자 지정 아이콘](../assets/do-not-localize/icon-falco-customize-table.svg) ) 아이콘을 클릭하여 표시된 열을 제어합니다.
* _열 재설정_( ![열 너비 재설정 아이콘](../assets/do-not-localize/icon-falco-reset-columns.svg) ) 아이콘을 클릭하여 열 너비를 재설정합니다.

이 스페이스에서 다음과 같은 작업을 수행할 수도 있습니다.

* 새 동적 및 정적 목록 만들기
* 현재 멤버십을 검토할 수 있는 목록에 액세스
* 멤버십 필터 적용

<!--
## Audience Hub

The AI Audience Hub is a centralized, AI-driven starting point for all audience-related capabilities across [!DNL Adobe Marketo Optimizer]. It is designed to accelerate first-time user success while progressively unlocking advanced intelligence, insights, and control for returning and power users.

The Hub acts as:

* A guided starting point for discovering, creating, and refining person lists, account lists, and buying groups

* A visibility layer for audience health, coverage, overlap, engagement patterns, and AI-driven insights

* A control center for audience governance, optimization, reuse, and readiness for activation across journeys and sales workflows

### High level structure

Prompt-based starting point - Quick Start prompts and freeform input to help users discover, create, or optimize audiences.

1. AI insights feed - Surfaces key audience signals such as overlap, gaps, saturation risk, and optimization opportunities.

1. Adaptive audience library - A personalized view of people lists, account lists, and buying groups that adapts based on usage, relevance, and activation.

1. Optimization and arbitration nudges - Guides users to refine, split, or reuse audiences before activation.

1. Audience visibility and reporting - High-level insight into audience health, engagement patterns, and usage across active journeys.


### Empty and Error States (High-Level)

No audiences / no data - Show Quick Start prompts to help first-time users create or import person lists

Low data or incomplete audience - Explain what's missing (e.g., insufficient contacts, missing persona coverage, or low engagement data) and suggest next steps.

AI insights unavailable - Provide a graceful fallback with a clear explanation, so users understand why insights aren't shown and what actions they can take manually.
-->

## 사람 목록 만들기 {#create-people-list}

1. _[!UICONTROL 사람 목록]_ 페이지의 오른쪽 상단에 있는 **[!UICONTROL 목록 만들기]**&#x200B;를 클릭합니다.

1. 대화 상자에서 목록에 대한 **[!UICONTROL 상위]**(으)로 프로그램을 선택합니다.

1. 목록에 **[!UICONTROL 이름]**(필수) 및 **[!UICONTROL 설명]**(선택 사항)을 입력하십시오.

1. **[!UICONTROL 유형]** 목록 선택:

   * [**[!UICONTROL 정적]**](#static-lists) - 구성원 자격은 목록을 만들 때 평가되는 자격 부여 필터에 의해 결정됩니다. 수동으로 레코드를 한정하거나 한정하지 않으면 목록 멤버십이 업데이트되지 않습니다.
   * [**[!UICONTROL Dynamic]**](#dynamic-lists) - 멤버십은 자격을 갖춘 필터에 의해 동적으로 결정됩니다. 목록 멤버십이 자동으로 새로 고쳐집니다.

   ![사람 목록 만들기 대화 상자](./assets/people-list-create-dialog.png){width="450"}

1. **[!UICONTROL 만들기]**&#x200B;를 클릭합니다.

>[!NOTE]
>
>이 Beta 릴리스의 사람 목록은 현재 삭제 및 복제가 지원되지 않습니다.

## 정적 목록 {#static-lists}

정적 목록 멤버십은 사용자 특성 및 활동을 참조하는 간단한 필터로 정의됩니다. 구성원이 자격을 수동으로 부여하거나 자격을 박탈하지 않는 한 멤버십은 변경되지 않습니다.

>[!NOTE]
>
>정적 목록 필터 정의는 목록에 멤버를 추가하거나 목록에서 제거할 때 한 번만 적용됩니다. 정의된 필터는 나중에 사용할 수 없습니다. 필터를 사용하여 일관된 대상 정의를 유지하려면 동적 목록을 대신 사용하십시오.

<!--
What internet says about Marketo static lists -- which of these is also true in Marketo Optimizer?

* Manual Targeting: Storing fixed cohorts, such as attendees of a specific webinar, people who purchased a certain product, or a list of competitors.
* Third-Party Syncing: Allowing external platforms (like Amplitude or Twilio Segment) to automatically sync and export groups of users directly into Marketo as targeted audiences.
* Status Tracking: Helping marketers organize leads into specific categories or track multi-value interests without needing to create new, permanent database fields.List 
* Segmentation: Acting as a reliable, unchanging recipient or suppression list for email campaigns and engagement programs. Unlike a Smart List—which dynamically adds or removes people based on changing criteria or rules—a static list serves as a reliable snapshot. People remain on the list until explicitly added or removed by you or a backend flow.

So far, activating to a destination is the only thing that they are used for that I have found.
-->

### 구성원 추가 {#static-list-add-members}

1. 정적 목록을 열고 오른쪽 상단에서 **[!UICONTROL 사람 추가]**&#x200B;를 클릭합니다.

1. 대화 상자에서 왼쪽에서 필터를 드래그 앤 드롭하여 잠재 고객을 선별하는 규칙을 정의합니다.

   다음을 조합하여 사람을 필터링할 수 있습니다.

   * 활동 기록
   * 회사 속성
   * 개인 속성
   * 여정 멤버십과 같은 특수 필터

   추가하는 각 필터에 대해 **[!UICONTROL 제한 추가]**&#x200B;를 클릭하여 필터에 대해 일치하는 조건을 구체화합니다.

   ![정적 목록에 사용자를 추가하려면 제약 조건이 있는 필터를 추가하십시오.](./assets/people-list-static-add-people-filters.png){width="700" zoomable="yes"}

1. 변경 내용을 저장하려면 **[!UICONTROL 완료]**&#x200B;를 클릭하세요.

1. **[!UICONTROL 구성원]** 탭을 선택합니다.

   잠시 후 자격을 갖춘 멤버가 목록에 나타납니다.

   정적 목록의 ![구성원](./assets/people-list-static-members.png){width="700" zoomable="yes"}

### 멤버 제거 {#static-list-remove-members}

1. 정적 목록을 열고 오른쪽 상단에서 **[!UICONTROL 사람 제거]**&#x200B;를 클릭합니다.

1. _[!UICONTROL 직원 제거]_ 대화 상자에서 자격을 박탈하려는 구성원과 일치하는 필터를 추가합니다.

   ![정적 목록에서 사람을 제거하는 필터를 추가](./assets/people-list-static-members-remove-people-filters.png){width="700" zoomable="yes"}

1. 변경 내용을 저장하려면 **[!UICONTROL 완료]**&#x200B;를 클릭하세요.

1. **[!UICONTROL 구성원]** 탭을 선택합니다.

   잠시 후 실격된 구성원들은 명단에서 탈퇴합니다.

### 대상에 활성화 {#static-list-activate}

정적 목록을 활성화하면 수동 내보내기 대신 지속적인 동기화를 사용하여 다운스트림 시스템에서 실행할 수 있습니다. 이 기능은 유료 미디어 타깃팅, 제외 및 다운스트림 오케스트레이션에 유용합니다.

* 정적 목록은 사용자를 위한 컨테이너 역할을 합니다.
* 활성화는 해당 멤버십을 대상으로 전송/동기화합니다.
* 그런 다음 대상은 그러한 사용자와 함께 LinkedIn에서 타깃팅하거나 외부 대상자에서 제거하는 등의 작업을 수행할 수 있습니다.

활성화 모델은 일회성 내보내기가 아니라 지속적이어야 하기 때문입니다.

* 나중에 목록에 추가된 사용자가 자동으로 전파됩니다.
* 나중에 제거된 직원은 자동으로 비활성화됩니다.
* 마케터는 CSV 내보내기 및 수동 업로드를 반복하지 않습니다.
* 여정은 지속적인 오케스트레이션을 위해 시간이 지남에 따라 대상자를 새로 고칠 수 있습니다.

>[!PREREQUISITES]
>
>대상에 정적 목록을 활성화하려면 먼저 [!DNL Marketo Optimizer] 샌드박스에 대해 하나 이상의 [구성된 대상](./destinations.md)이 있어야 합니다.

1. **[!UICONTROL 정적 목록]** 탭을 선택합니다.

1. 대상에 활성화할 정적 목록을 찾습니다.

1. 목록 옆에 있는 _추가 메뉴_( **...** ) 아이콘을 클릭하고 **[!UICONTROL 대상에 활성화]**&#x200B;를 선택합니다.

   ![정적 목록의 기타 메뉴에 액세스](./assets/people-lists-static-more-menu.png){width="450"}

   정적 목록을 열고 오른쪽 상단의 _[!UICONTROL 자세히]_ 메뉴를 사용할 수도 있습니다.

   <!-- which UI is it?  _Activate_ ( ![Customize table icon](../assets/do-not-localize/icon-falco-activate-dest.svg) ) icon next to the static list name. -->

1. 구성된 대상 연결에 대한 확인란을 선택합니다.

   ![구성된 대상을 활성화하도록 사용](./assets/static-list-activate-destination-select.png){width="600" zoomable="yes"}

1. **[!UICONTROL 저장]**&#x200B;을 클릭합니다.

1. **[!UICONTROL 활성화]**&#x200B;를 클릭하여 _[!UICONTROL 대상에 목록 활성화]_ 대화 상자에서 활성화를 확인합니다.

활성화가 완료되면 확인이 표시됩니다(_대상이 활성화되었습니다._) 대상이 목록의 **[!UICONTROL 대상]** 탭에 **[!UICONTROL 활성]**(으)로 나열됩니다. 정적 목록은 한 번에 두 개 이상의 대상에 활성화될 수 있습니다. 멤버십은 모든 대상에 동기화됩니다.

정적 목록이 활성화된 대상을 검토하려면 목록을 열고 **[!UICONTROL 대상]** 탭을 선택합니다. 기본적으로 새 목록에는 연결된 대상이 없습니다.

#### 대상 비활성화 {#deactivate-destination}

1. 정적 목록을 열고 **[!UICONTROL 대상]** 탭을 선택합니다.

1. 제거할 대상의 행에서 _마이너스_( **-**) 아이콘을 클릭합니다.

1. _[!UICONTROL 대상 비활성화]_ 대화 상자에서 확인하십시오.

비활성화하면 목록에서 대상이 제거됩니다. 목록의 사람도 연결된 대상 대상에서 제거됩니다.

## 동적 목록 {#dynamic-lists}

동적 목록 멤버십은 사용자 특성 및 활동을 참조하는 간단한 필터를 사용하여 정의됩니다. 필터 논리에 따라 자격 및 자격 취소 리드에 의해 멤버십이 자동으로 유지됩니다.

### 멤버십 규칙 설정 {#set-membership-rules}

1. 동적 목록을 열고 **[!UICONTROL 규칙]** 탭을 선택합니다.

1. **[!UICONTROL 규칙 편집]**&#x200B;을 클릭합니다.

   ![동적 사용자 목록 작성을 위한 액세스 규칙](./assets/people-list-dynamic-rules-edit.png){width="550" zoomable="yes"}

1. 대화 상자에서 왼쪽에서 필터를 드래그 앤 드롭하여 잠재 고객을 선별하는 규칙을 정의합니다.

   다음 조합을 사용하여 목록에 대한 잠재 고객을 우량으로 선별할 수 있습니다.

   * 활동 기록
   * 회사 속성
   * 개인 속성
   * 여정 멤버십과 같은 특수 필터

   추가하는 각 필터에 대해 **[!UICONTROL 제한 추가]**&#x200B;를 클릭하여 필터에 대해 일치하는 조건을 구체화합니다.

   ![제약 조건이 있는 필터를 추가하여 동적 목록 채우기](./assets/people-list-dynamic-rules-edit-filters.png){width="700" zoomable="yes"}

1. 변경 내용을 저장하려면 **[!UICONTROL 완료]**&#x200B;를 클릭하세요.

1. **[!UICONTROL 구성원]** 탭을 선택합니다.

   잠시 후 자격을 갖춘 멤버가 목록에 나타납니다.

   ![동적 목록에 대해 생성된 구성원](./assets/people-list-dynamic-rules-members.png){width="700" zoomable="yes"}

   요약 및 최근 활동을 볼 수 있는 [개인 정보](./person-details.md) 페이지를 열려면 목록에서 개인 이름을 클릭합니다.

### 동적 목록 복제 {#duplicate-dynamic-list}

동적 목록의 경우 복제 작업은 복제 함수와 유사합니다. 이 함수를 사용하여 멤버십 필터링을 복제하고 다른 프로그램에 추가합니다.

1. _[!UICONTROL 동적 목록]_ 탭에서 목록 옆에 있는 _추가 메뉴_(**...**) 아이콘을 클릭하고 **[!UICONTROL 복제]**&#x200B;를 선택합니다.

1. 대화 상자에서 중복된 목록에 대한 **[!UICONTROL 부모]** 프로그램을 선택합니다.

1. 고유한 **[!UICONTROL 이름]**(필수) 및 **[!UICONTROL 설명]**(선택 사항)을 입력하십시오.

   기본적으로 대화 상자는 `_copy`이(가) 추가된 원래 목록의 이름을 사용합니다. 필요에 따라 목록의 다른 고유 이름을 입력합니다.

   ![목록 대화 상자 복제](./assets/people-list-duplicate-dialog.png){width="375"}

1. **[!UICONTROL 복제]**&#x200B;를 클릭합니다.
