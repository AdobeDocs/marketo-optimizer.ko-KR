---
title: 조각
description: 이메일 및 템플릿에 대한 시각적 콘텐츠 조각을 만들고, 관리하고, 재사용할 수 있습니다. Marketo Optimizer에서 재사용 가능한 블록을 빌드하고, 버전을 게시하고, 사용을 추적합니다.
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '2634'
ht-degree: 3%

---

# 조각

조각은 [!DNL Marketo Optimizer]에서 하나 이상의 전자 메일 및 전자 메일 템플릿에서 참조할 수 있는 재사용 가능한 구성 요소입니다. 일반적으로 미리 만들어 이메일 또는 이메일 템플릿에 신속하게 삽입할 수 있는 콘텐츠 블록(텍스트, 이미지 또는 둘 다)입니다. 이 기능을 사용하면 마케팅 팀원이 이메일 콘텐츠를 취합하여 디자인 프로세스를 개선하는 데 사용할 여러 사용자 지정 콘텐츠 블록을 미리 빌드할 수 있습니다. 일반적인 사용 사례로는 이메일, 이벤트 초대 배너 및 시즌 인사말을 위한 머리글/바닥글 콘텐츠 블록이 있습니다.

>[!BEGINSHADEBOX]

**시각적 조각**

시각적 조각은 여러 이메일 또는 이메일 템플릿에서 재사용할 수 있는 시각적 디자인 도구를 사용하여 빌드된 사전 정의된 시각적 블록입니다. [!DNL Marketo Optimizer]의 현재 범위와 이 설명서에는 시각적 조각만 포함되어 있습니다.

>[!NOTE]
>
>식 기반 조각은 [!DNL Marketo Optimizer]에서 아직 지원되지 않습니다.

>[!ENDSHADEBOX]

워크플로우에서 조각을 최대한 활용하려면 다음 작업을 수행하십시오.

* _나만의 조각 만들기_ - 처음부터 만들거나 콘텐츠를 시각적 콘텐츠 디자인 공간의 조각으로 저장하여 시각적 조각을 만듭니다.
* _조각 재사용_ - 전자 메일 또는 전자 메일 템플릿 콘텐츠에 필요한 만큼 조각을 사용합니다.

## 조각 액세스 및 관리 {#access-manage-fragments}

[!DNL Marketo Optimizer]에서 시각적 조각에 액세스하려면 왼쪽 탐색으로 이동하여 **[!UICONTROL 콘텐츠 관리]**&#x200B;를 확장하세요. 그런 다음 **[!UICONTROL 조각]**&#x200B;을 선택합니다. 이 작업을 수행하면 테이블에 나열된 인스턴스에서 만든 모든 조각이 포함된 목록 페이지가 열립니다.

![조각 라이브러리에 액세스](./assets/fragments-list.png){width="700" zoomable="yes"}

표는 _[!UICONTROL 수정됨]_ 열을 기준으로 정렬되며 가장 최근에 업데이트된 조각이 기본적으로 맨 위에 있습니다. 오름차순과 내림차순 간을 변경하려면 열 제목을 클릭합니다.

왼쪽의 폴더 구조를 사용하여 조각을 구성할 수 있습니다. 기본적으로 모든 조각이 표시됩니다. 폴더를 선택하면 선택한 폴더에 포함된 조각과 하위 폴더만 표시됩니다.

### 조각 상태 {#fragment-status}

조각 상태는 이메일이나 이메일 템플릿에서 조각을 사용할 수 있는지 여부와 조각에 적용할 수 있는 변경 사항을 결정합니다.

| 상태 | 설명 |
| ------ | ----------- |
| 초안 | 조각을 만들면 초안 상태가 됩니다. 이메일 또는 이메일 템플릿에 사용하기 위해 게시하기 전까지 시각적 디자인 공간을 정의하거나 편집할 때 이 상태로 유지됩니다. 사용 가능한 작업: <br/><ul><li>모든 세부 정보 편집<li>시각적 디자인 공간에서 편집<li>게시<li>복제<li>삭제 |
| 라이브 | 조각을 게시하면 이메일 또는 이메일 템플릿에서 사용할 수 있습니다. 게시된 조각 콘텐츠는 시각적 디자인 공간에서 수정할 수 없습니다. 사용 가능한 작업: <br/><ul><li>설명 편집<li>이메일 또는 템플릿에 추가<li>초안 버전 만들기<li>복제<li>삭제(사용하지 않는 경우) |
| 라이브(초안 사용) | 라이브 조각에서 초안을 만들 때 라이브 버전은 이메일 또는 이메일 템플릿에서 사용할 수 있으며 시각적 디자인 공간에서 초안 콘텐츠를 수정할 수 있습니다. 초안 버전을 게시하면 현재 라이브 버전이 대체되며 콘텐츠는 사용 중인 이메일 및 이메일 템플릿에서 업데이트됩니다. 사용 가능한 작업: <br/><ul><li>설명 편집<li>이메일 또는 템플릿에 추가<li>시각적 디자인 공간에서 초안 버전 편집<li>초안 버전 게시<li>복제<li>삭제(사용하지 않는 경우) |
| 보관 | 조각이 보관되어 _조각_ 목록에 표시되지 않습니다. |

### 조각 목록 필터링 {#filter-list}

이름별로 조각을 검색하려면 검색 막대에 일치 항목 텍스트 문자열을 입력합니다. [폴더](#folders)을(를) 선택하면 해당 폴더의 첫 번째 계층 구조 수준에 있는 모든 조각이나 폴더에 검색이 적용됩니다.

![표시된 조각 필터링](./assets/fragments-list-filtered.png){width="500" zoomable="yes"}

_필터_ 아이콘(![필터 표시 또는 숨기기 아이콘](../assets/do-not-localize/icon-filter.svg) )을 클릭하여 사용 가능한 필터 옵션을 표시하고 설정을 변경하여 지정된 조건에 따라 표시된 항목을 필터링합니다.

### 열 표시 사용자 정의 {#column-display}

오른쪽 상단의 _표 사용자 지정_ 아이콘(![표 사용자 지정 아이콘](../assets/do-not-localize/icon-column-settings.svg))을 클릭하여 표에 표시할 열을 사용자 지정합니다.

대화 상자에서 표시할 열을 선택하고 **[!UICONTROL 적용]**&#x200B;을 클릭합니다.

![표시할 열 선택](assets/fragments-customize-table-dialog.png){width="300"}

### 일괄 액션 {#bulk-actions}

확인란을 사용하여 여러 조각을 선택하고 모든 조각에 일괄 작업을 적용할 수 있습니다. 사용 가능한 작업은 목록 페이지 하단에 있는 일괄 작업 표시줄에 표시됩니다. 다음 작업을 사용할 수 있습니다.

* **[!UICONTROL 폴더로 이동]** - 선택한 조각을 폴더로 이동합니다.
* **[!UICONTROL 보관]** - 선택한 조각 보관

열 머리글을 클릭하여 조각 목록을 정렬하고 열 테두리를 필요한 데이터에 맞게 드래그하여 열 크기를 조정할 수도 있습니다.

## 조각 만들기 {#create-fragments}

오른쪽 상단의 **[!UICONTROL 조각 만들기]**&#x200B;를 클릭하여 [!DNL Marketo Optimizer]에서 새 시각적 조각을 만들 수 있습니다.

1. _[!UICONTROL 조각 만들기]_ 페이지에서 유용한 **[!UICONTROL 이름]**(필수)과 **[!UICONTROL 설명]**(선택 사항)을 입력하십시오.

   * 이름 - 최대 100자이며, 고유해야 하며 대소문자를 구분하지 않습니다.

   * 설명 - 최대 300자

   * Alpha, 숫자 및 특수 문자가 허용됩니다.

   * 예약된 문자가 **_허용되지 않음_**: `\ / : * ? " < > |`

   ![조각 페이지 만들기](./assets/fragments-create.png){width="700" zoomable="yes"}

1. **[!UICONTROL 만들기]**&#x200B;를 클릭합니다.

   시각적 디자인 공간이 빈 캔버스로 열립니다.

1. 콘텐츠 디자인 도구를 사용하여 시각적 조각 콘텐츠를 만듭니다.

   * [구조 및 콘텐츠 추가](./fragment-authoring.md#design-fragment)
   * [에셋 추가](./fragment-authoring.md#add-assets)
   * [레이어, 설정 및 스타일 탐색](./fragment-authoring.md#navigate-layers-settings-styles)
   * [콘텐츠 개인화](./fragment-authoring.md#personalize-content)
   * [연결된 URL 추적 편집](./fragment-authoring.md#edit-linked-url-tracking)

1. 언제든지 **[!UICONTROL 저장]**&#x200B;을 클릭하여 초안 조각을 저장합니다.

1. 전자 메일 또는 전자 메일 템플릿에서 사용할 수 있는 조각을 만들 준비가 되면 **[!UICONTROL 게시]**&#x200B;를 클릭합니다.

## 조각 세부 사항 보기 {#view-details}

목록 페이지에서 조각 이름을 클릭하여 조각 세부 사항 페이지를 엽니다. 조각을 편집하거나, 조각 이름을 바꾸거나, 조각 설명을 업데이트하도록 선택할 수 있습니다. 변경 사항을 자동으로 저장하려면 업데이트하고 이름 또는 설명 필드 외부를 클릭합니다.

>[!NOTE]
>
>게시된 조각을 이메일 또는 이메일 템플릿에서 사용 중인 경우 이름을 변경하거나 콘텐츠를 편집할 수 없습니다. 조각을 변경하려는 경우 초안 버전을 생성할 수 있습니다.

![조각에 대한 세부 정보 보기](./assets/fragment-details.png){width="700" zoomable="yes"}

**[!UICONTROL 조각 편집]**&#x200B;을 클릭하여 시각적 콘텐츠 편집기에서 조각을 엽니다.

왼쪽 상단의 _뒤로_ 화살표를 클릭하여 언제든지 보기를 종료하십시오. 그러면 _조각_ 목록 페이지로 돌아갑니다.

## 조각 참조 보기 {#references}

_Live_ 조각의 경우 현재 해당 조각을 참조(사용)하는 에셋 목록을 볼 수 있습니다.

1. 조각 세부 정보 페이지에서 자세히(**...**)를 클릭합니다. 오른쪽 상단의 아이콘

1. **[!UICONTROL 참조 탐색]**&#x200B;을 선택합니다.

   _[!UICONTROL 조각 사용]_ 페이지에는 전자 메일 및 전자 메일 서식 파일에 걸쳐 현재 [!DNL Marketo Optimizer] 내에서 조각이 사용되는 에셋 목록이 표시됩니다.

   >[!IMPORTANT]
   >
   >현재 이메일 또는 이메일 템플릿에서 사용 중인 모든 조각은 삭제할 수 없습니다.

   _전자 메일_ 또는 _전자 메일 템플릿_ 범주에 따라 참조가 표시됩니다. [!DNL Marketo Optimizer]의 모든 전자 메일은 개인 여정의 _전자 메일 보내기_ 작업 여정 내에 정의되어 있으므로 조각을 사용하는 전자 메일의 상위 노드가 참조에 표시됩니다.

1. 링크를 클릭하여 조각이 사용되는 해당 이메일 또는 이메일 템플릿을 엽니다.

## 폴더를 사용하여 조각 관리 {#folders}

조각을 쉽게 탐색하기 위해 폴더를 사용하여 조각을 구조화된 계층으로 보다 효과적으로 구성할 수 있습니다. 이를 통해 조직의 요구 사항에 따라 항목을 분류하고 관리할 수 있습니다.

모든 하위 폴더에 있는 조각을 포함하여 모든 조각을 표시하려면 _[!UICONTROL 루트]_ 폴더를 선택하십시오. 구조에서 컨텐츠를 표시할 폴더를 선택합니다. 폴더를 선택한 상태에서 조각 만들기 를 클릭하여 해당 폴더에서 새 조각을 만듭니다.

### 폴더 만들기 {#folders-create}

1. 상위 폴더(루트 또는 다른 폴더)를 선택한 상태에서 오른쪽 상단의 **[!UICONTROL 폴더 만들기]**&#x200B;를 클릭합니다.

1. 새 폴더에 대해 **[!UICONTROL 이름]**&#x200B;을(를) 입력하고 **[!UICONTROL 저장]**&#x200B;을(를) 클릭합니다.

   새 폴더는 선택한 상위 폴더 내의 목록 맨 위에 나타납니다.

   기타 메뉴( **...**) 아이콘을 클릭하여 폴더 이름을 바꾸거나, 이동하거나, 폴더를 삭제할 수 있습니다.

### 폴더 이동 {#folders-move}

1. _추가 메뉴_(**...**) 클릭 아이콘 이동할 조각 이름 옆에 있습니다.

1. **[!UICONTROL 폴더로 이동]**&#x200B;을 선택하세요.

1. 대화 상자에서 폴더 구조를 탐색하고 조각을 이동할 폴더를 선택합니다.

1. **[!UICONTROL 이동]**&#x200B;을 클릭합니다.

### 폴더 삭제 {#folders-delete}

1. 폴더 구조에서 삭제할 폴더의 상위 폴더를 선택합니다.

1. _추가 메뉴_(**...**) 클릭 아이콘 - 삭제하려는 표시된 하위 폴더의 이름 옆에 있습니다.

1. **[!UICONTROL 폴더 삭제]**&#x200B;를 선택하세요.

## 조각 편집 {#edit-fragments}

조각에 대한 편집은 현재 상태에 따라 다릅니다.

* 조각이 _초안_ 상태일 때 조각의 세부 정보와 시각적 콘텐츠를 편집할 수 있습니다.
* 조각이 _Live_ 상태일 때 조각 설명을 편집할 수 있지만 이름은 편집할 수 없습니다. 초안을 만들지 않으면 시각적 콘텐츠를 편집할 수 없습니다.
* 기존 초안을 사용하여 조각이 _Live_ 상태일 때 세부 정보 편집은 설명으로 제한됩니다. 초안 버전의 시각적 콘텐츠를 편집할 수도 있습니다.

>[!BEGINTABS]

>[!TAB 초안]

1. _[!UICONTROL 조각]_ 목록 페이지에서 조각 이름을 클릭하여 엽니다.

   시각적 콘텐츠의 미리보기가 표시됩니다.

1. 필요한 경우 설명을 수정합니다.

   ![초안 상태의 조각에 대한 세부 정보](assets/fragment-draft-details.png){width="600" zoomable="yes"}

1. 시각적 디자인 영역의 콘텐츠를 변경하려면 오른쪽 상단의 **[!UICONTROL 편집]**&#x200B;을 클릭합니다.

   필요에 따라 시각적 디자인 도구를 사용합니다.

   * [구조 및 콘텐츠 추가](./fragment-authoring.md#design-fragment)
   * [에셋 추가](./fragment-authoring.md#add-assets)
   * [레이어, 설정 및 스타일 탐색](./fragment-authoring.md#navigate-layers-settings-styles)
   * [콘텐츠 개인화](./fragment-authoring.md#personalize-content)
   * [연결된 URL 추적 편집](./fragment-authoring.md#edit-linked-url-tracking)

   조각 세부 정보로 돌아가려면 **[!UICONTROL 저장]** 또는 **[!UICONTROL 저장 및 닫기]**&#x200B;를 클릭하십시오.

1. 조각이 조건을 충족하고 전자 메일 또는 전자 메일 템플릿에서 사용할 수 있도록 하려면 **[!UICONTROL 게시]**&#x200B;를 클릭합니다.

>[!TAB 라이브]

1. _[!UICONTROL 조각]_ 목록 페이지에서 조각 이름을 클릭하여 엽니다.

   오른쪽에 조각 세부 사항이 있는 시각적 콘텐츠의 미리보기가 표시됩니다.

1. 필요한 경우 설명을 수정합니다.

1. 콘텐츠를 업데이트하려면 오른쪽 상단의 **[!UICONTROL 수정]**&#x200B;을 클릭하세요.

1. 대화 상자에서 **[!UICONTROL 확인]**&#x200B;을 클릭하여 조각의 초안 버전을 만듭니다.

   ![초안 버전 만들기 대화 상자](./assets/fragments-modify-dialog.png){width="300"}

1. 오른쪽 상단의 **[!UICONTROL 편집]**&#x200B;을 클릭합니다.

1. 필요에 따라 시각적 디자인 도구를 사용하여 초안의 콘텐츠를 업데이트합니다.

* [구조 및 콘텐츠 추가](./fragment-authoring.md#design-fragment)
* [에셋 추가](./fragment-authoring.md#add-assets)
* [레이어, 설정 및 스타일 탐색](./fragment-authoring.md#navigate-layers-settings-styles)
* [콘텐츠 개인화](./fragment-authoring.md#personalize-content)
* [연결된 URL 추적 편집](./fragment-authoring.md#edit-linked-url-tracking)

조각 세부 정보로 돌아가려면 **[!UICONTROL 저장]** 또는 **[!UICONTROL 저장 및 닫기]**&#x200B;를 클릭하십시오.

1. 초안 조각이 조건에 맞고 변경 사항을 전자 메일 또는 전자 메일 템플릿에 사용할 수 있게 하려면 **[!UICONTROL 게시]**&#x200B;를 클릭합니다.

   초안 버전을 게시하면 현재 라이브 버전이 대체되며 콘텐츠는 이미 사용 중인 이메일 및 이메일 템플릿에서 업데이트됩니다.

>[!TAB 라이브(초안 포함)]

_[!UICONTROL 조각]_ 목록 페이지에서 편집할 초안 버전을 여는 방법에는 두 가지가 있습니다.

* 조각 이름 옆에 있는 _초안_ 아이콘(![초안 아이콘](../assets/do-not-localize/icon-draft.svg))을 클릭합니다.

* 조각 이름을 클릭하여 엽니다. 그런 다음 오른쪽 상단의 _추가 메뉴_(***...***) 아이콘을 클릭하고 **[!UICONTROL 초안 버전 열기]**&#x200B;를 선택합니다.

초안 버전에 대한 시각적 콘텐츠의 미리보기가 표시됩니다.

초안 콘텐츠를 업데이트하려면(_T):_

1. 오른쪽 상단의 **[!UICONTROL 편집]**&#x200B;을 클릭합니다.

1. 필요에 따라 시각적 디자인 도구를 사용합니다.

   * [구조 및 콘텐츠 추가](./fragment-authoring.md#design-fragment)
   * [에셋 추가](./fragment-authoring.md#add-assets)
   * [레이어, 설정 및 스타일 탐색](./fragment-authoring.md#navigate-layers-settings-styles)
   * [콘텐츠 개인화](./fragment-authoring.md#personalize-content)
   * [연결된 URL 추적 편집](./fragment-authoring.md#edit-linked-url-tracking)

   조각 세부 정보로 돌아가려면 **[!UICONTROL 저장]** 또는 **[!UICONTROL 저장 및 닫기]**&#x200B;를 클릭하십시오.

1. 초안 조각이 조건에 맞고 변경 사항을 전자 메일 또는 전자 메일 템플릿에 사용할 수 있게 하려면 **[!UICONTROL 게시]**&#x200B;를 클릭합니다.

   초안 버전을 게시하면 현재 게시된 버전이 대체되며 콘텐츠는 이미 사용 중인 이메일 및 이메일 템플릿에서 업데이트됩니다.

>[!ENDTABS]

## 중복 조각 {#duplicate-fragments}

다음 방법 중 하나를 사용하여 조각을 복제할 수 있습니다.

* _[!UICONTROL 조각]_ 목록 페이지에서 _자세히_ 아이콘(**...**)을 클릭합니다. 조각 이름 옆에 있는 **[!UICONTROL 복제]**&#x200B;를 선택합니다.
* 조각 세부 정보 페이지의 오른쪽 상단에서 _자세히_(**...**)을 클릭합니다. 아이콘을 클릭하고 **[!UICONTROL 복제]**&#x200B;를 선택합니다.

대화 상자에서 유용한 이름(고유)과 설명을 입력합니다. 작업을 완료하려면 **[!UICONTROL 복제]**&#x200B;를 클릭하십시오.

그런 다음 복제된(새) 조각은 동일한 폴더에 있는 _조각_ 목록에 나타납니다.

<!-- 

## Save a new fragment from email or template content {#save-as-fragment}

When you are creating/editing an email or email template in the visual content editor, you can choose to save all or parts of the content as a fragment so that it is available for reuse.

1. When you have some content to be saved as a fragment, click **[!UICONTROL More]** and choose **[!UICONTROL Save as Fragment]**.

1. Select the different elements to be included in the fragment.

   Select multiple structures by holding the Shift or Control button.

   You can only select structures that are adjacent to each other and the interface does not allow you to select non-adjacent elements.

1. With the content selected, click **[!UICONTROL Create]** at the top right.

1. In the dialog, enter a useful name and description for the fragment. Then click **[!UICONTROL Create]**.

   The new fragment is then displayed in the _Fragments_ listing page and is also available for use within emails and email templates.

-->

## 이메일 또는 템플릿 콘텐츠에 시각적 조각 추가 {#add-to-content}

조각은 재사용을 위해 설계되었으며 이메일 및 이메일 템플릿 작성에 삽입할 수 있습니다. 이메일 또는 템플릿에 최대 30개의 조각을 추가할 수 있습니다. 조각은 한 수준까지만 중첩할 수 있습니다.

>[!BEGINTABS]

>[!TAB 전자 메일에 조각 추가]

1. 개인 여정으로 이동하여 기존 _[!UICONTROL 전자 메일 보내기]_ 작업 노드를 열거나 [새 노드를 추가](../marketing/action-nodes.md#add-an-action-node)하세요.

1. **[!UICONTROL 전자 메일 본문 편집]**&#x200B;을 클릭하여 [전자 메일 콘텐츠 작성](./email-authoring.md)을 열거나 계속합니다.

1. **[!UICONTROL 구조]** 메뉴에서 항목을 끌어다 놓아 조각에 대한 _구조_&#x200B;을(를) 제공하세요.

1. 게시된 조각 목록을 열려면 _조각_ 아이콘을 클릭합니다.

   다음과 같은 작업을 수행할 수 있습니다.
   * 목록을 정렬합니다.
   * 목록을 검색 및 필터링합니다.
   * 카드(썸네일)와 목록 보기 간에 전환합니다.
   * 최근에 만들어진 조각을 반영하도록 목록을 새로 고칩니다.

   ![시각적 디자이너에서 조각을 검색합니다](assets/fragments-list-designer-search.png){width="600"}

1. 조각을 구조 구성 요소 자리 표시자로 끌어서 놓습니다.

   편집기는 이메일 구조의 섹션/요소 내에서 조각을 렌더링합니다.

조각의 콘텐츠는 구조 내에서 동적으로 업데이트되어 이메일에 콘텐츠가 표시되는 방식을 시각적으로 렌더링합니다.

>[!TIP]
>
>조각이 전자 메일 내의 전체 가로 레이아웃을 차지하도록 하려면 [!UICONTROL 1:1 열] 구조를 추가한 다음 조각을 끌어서 놓습니다.

전자 메일이 저장되면 _[!UICONTROL 사용한 사람]_ 탭을 선택하면 조각 세부 정보 페이지에 나타납니다. 이메일에 추가된 조각은 이메일 또는 템플릿 내에서 편집할 수 없습니다. 게시된 소스 조각은 콘텐츠를 정의합니다.

>[!TAB 전자 메일 템플릿에 조각 추가]

1. 왼쪽 탐색에서 **[!UICONTROL 콘텐츠 관리]**&#x200B;를 확장하고 **[!UICONTROL 템플릿]**&#x200B;을 선택합니다.

1. [새 템플릿을 만들거나](./templates-create.md) 기존 전자 메일 템플릿을 엽니다.

1. 오른쪽의 템플릿 속성 패널에서 **[!UICONTROL 전자 메일 본문 편집]**&#x200B;을 클릭합니다.

1. **[!UICONTROL 구조]** 메뉴에서 항목을 끌어다 놓아 조각에 포함된 _구조_&#x200B;을(를) 제공하세요.

1. 조각 목록을 열려면 왼쪽의 _조각_ 아이콘을 클릭합니다.

   다음과 같은 작업을 수행할 수 있습니다.
   * 목록을 정렬합니다.
   * 목록을 검색 및 필터링합니다.
   * 카드(썸네일)와 목록 보기 간에 전환합니다.
   * 최근에 만들어진 조각을 반영하도록 목록을 새로 고칩니다.

   ![시각적 디자이너에서 조각을 검색합니다](assets/fragments-list-designer-search.png){width="600"}

1. 조각을 구조 구성 요소로 끌어다 놓습니다.

   편집기는 이메일 템플릿 구조의 섹션/요소 내에서 조각을 렌더링합니다.

>[!TIP]
>
>조각이 전자 메일 템플릿 내의 전체 가로 레이아웃을 차지하도록 하려면 _[!UICONTROL 1:1 열]_ 구조를 추가한 다음 조각을 끌어서 놓습니다.

전자 메일 템플릿이 저장되면 _[!UICONTROL 사용 사용자]_ 탭을 선택하면 조각 세부 정보 페이지에 표시됩니다. 이메일 템플릿에 추가된 조각은 템플릿 내에서 편집할 수 없습니다. 게시된 소스 조각은 콘텐츠를 정의합니다.

>[!ENDTABS]

## 이메일 및 템플릿 작성 중 조각 작업 {#fragment-actions}

이메일 또는 이메일 템플릿에 조각을 추가하면 이메일 또는 템플릿 내에서 조각 콘텐츠를 편집할 수 없습니다. 하지만 다음 작업을 적용할 수 있습니다.

* **[!UICONTROL 삭제]** - 이 작업은 현재 전자 메일 또는 전자 메일 템플릿 콘텐츠에서 조각을 제거합니다(조각 소스는 영향을 받지 않음).
* **[!UICONTROL 새로 고침]** - 이 작업은 현재 전자 메일 또는 전자 메일 템플릿의 조각 콘텐츠를 새로 고칩니다. 새로 고침은 이메일 또는 이메일 템플릿에 추가한 후 조각에 대한 최근 편집 내용을 반영하려는 경우에 유용합니다.
* **[!UICONTROL 복제]** - 이 작업은 편집기 내의 동일한 전자 메일 또는 전자 메일 템플릿 내의 조각을 동일한 차원으로 복제하고 바로 아래에 추가합니다.
* **[!UICONTROL 조각 열기]** - 이 작업을 수행하면 조각 편집기 페이지와 세부 정보가 있는 새 브라우저 탭이 열립니다.
* **[!UICONTROL 참조 탐색]** - 이 작업은 조각의 사용량을 유형별로 볼 수 있는 조각 사용 페이지를 엽니다.
* **[!UICONTROL 상속 중단]** - 이 작업은 소스에서 조각의 상속(및 변경 내용)을 중단합니다. 이 작업을 사용하여 조각 콘텐츠를 이메일 또는 이메일 템플릿 내에서 독립적이고 편집 가능한 콘텐츠로 사용할 수 있도록 합니다. 이 작업은 원본 조각에 대한 _사용한 사람_ 참조에서 전자 메일 또는 전자 메일 템플릿도 제거합니다.

편집기 페이지에서 조각을 선택하면 이러한 작업은 컨텍스트 도구 모음과 오른쪽의 속성 패널에서 사용할 수 있습니다.

![선택한 조각에 작업 적용](./assets/fragment-actions-email-authoring.png){width="600" zoomable="yes"}
