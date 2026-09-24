---
title: Personalization용 사용자 지정 토큰
description: 마케팅 아티팩트의 동적 개인화를 위해 사용자 지정 내 토큰을 만들고 관리합니다. Marketo Optimizer에서 프로그램의 텍스트 및 숫자 변수를 정의합니다.
TQID: 'https://experienceleague.adobe.com/utVM69g7aQSuF-V3XQIdVBqvBXyiDz1ZWr0WtE67UCg'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
  - id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
    internal-label: Programs
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 177e7c3d0806febd730104b19787ba3cbea2914a
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 2%
---
# 개인화를 위한 사용자 지정 토큰

콘텐츠 개인화는 토큰을 콘텐츠 아티팩트가 생성될 때 채워지는 자리 표시자 또는 변수로 사용합니다. 표준 개인화 토큰은 이메일, 랜딩 페이지, 조각 및 템플릿에 사용할 수 있습니다. 프로그램 또는 폴더와 관련된 값을 사용하여 사용자 지정 토큰 세트를 정의할 수도 있습니다. 이 사용자 지정 토큰 집합을 _내 토큰_&#x200B;이라고 하며 이러한 사용자 지정 토큰 중 하나를 개인화할 수 있습니다.

<!-- 
When you add a custom token to an email, it is displayed as `{{my.TokenName}}`. For example, you might have `{{my.EventDate}}` or `{{my.WebinarSpeaker}}` tokens created to manage email content related to upcoming webinars in your program.
-->

프로그램 또는 폴더에만 해당되는 _내 토큰_ 외에도 개인화를 위해 표준(기본 제공) 토큰을 사용할 수 있습니다.

>[!IMPORTANT]
>
>초기 Marketo Optimizer 릴리스의 경우 _내 토큰_&#x200B;은(는) 데이터 값 변경 여정 작업 노드에 대해 지원되며 문자열 및 텍스트 특성에서 사용하도록 제한됩니다. _내 토큰_&#x200B;이 현재 Personalization 편집기에서 **활성화되지 않음**&#x200B;입니다.

## 토큰 액세스 {#access-tokens}

1. 왼쪽 탐색에서 **[!UICONTROL 마케팅 관리]**&#x200B;를 확장합니다.

1. **[!UICONTROL 마케팅]** 리소스 목록의 오른쪽에서 **[!UICONTROL 프로그램]**&#x200B;을 선택합니다.

1. 트리 구조에서 프로그램 또는 폴더를 선택하여 중앙 작업 공간에서 세부 정보를 엽니다.

1. **[!UICONTROL 토큰]** 탭을 클릭합니다.

   선택한 프로그램의 ![토큰 탭](./assets/program-tokens-tab.png){width="800" zoomable="yes"}

   탭에는 폴더 또는 프로그램 내에 정의된 모든 사용자 지정 토큰과 상위 폴더 또는 프로그램에 대해 정의된 모든 사용자 지정 토큰이 표시됩니다.

### 토큰 유형 {#my-tokens}

_내 토큰_&#x200B;은(는) 프로그램 또는 폴더에 대해 만들거나 수정하는 사용자 지정 변수입니다. 이 사용자 지정 토큰 세트는 다음 토큰 유형을 지원합니다.

| 토큰 유형 | 설명 |
| ---------- | ----------- |
| 텍스트 | 이 유형은 표준 텍스트 문자열을 포함합니다. 텍스트 토큰의 크기 제한은 524,288자(UTF-8) 또는 2MB입니다. |
| 일자 | 이 유형에는 날짜 값이 있습니다. 날짜는 월-일-년(예: 09-23-2026)으로 표시됩니다. |
| 날짜 및 시간 | 이 유형에는 날짜 및 시간 값이 있습니다. |
| 숫자 | 이 유형은 표준 정수 값을 보유합니다. |
| 이메일 | 이 유형에는 유효한 이메일 주소가 있습니다. |
| 점수 | 여정 작업 노드의 점수 변경에 이 토큰을 사용합니다. |
| 부울 | 이 유형은 true 또는 false의 표준 부울 값을 보유합니다. |
| 리치 텍스트 | 이 형식에는 서식이 지정된 텍스트가 포함됩니다. |

### 토큰 중첩 {#nesting}

프로그램 또는 폴더에서 토큰을 만들 때 계층 구조 내의 객체에서 참조할 수 있습니다.

* **로컬 토큰** - 토큰이 동일한 프로그램 또는 폴더에 정의되어 있습니다.
* **상속된 토큰** - 토큰이 현재 프로그램 또는 폴더보다 한 수준 이상 높은 상위 프로그램 또는 폴더에 정의되어 있습니다.
* **재정의된 토큰** - 토큰이 상위 프로그램 또는 폴더에 정의되어 있지만 현재 프로그램 또는 폴더에는 다른 값이 정의되어 있습니다. 토큰 상태가 _재정의됨_(으)로 바뀌고 모든 하위 폴더, 프로그램 및 마케팅 아티팩트가 새 값을 상속합니다.

![토큰 형식 및 상속](./assets/program-tokens-inherited-overridden.png){width="600" zoomable="yes"}

### 토큰 만들기 {#create}

1. _[!UICONTROL 토큰]_ 탭에서 **[!UICONTROL 만들기]**&#x200B;를 클릭합니다.

1. 대화 상자에서 토큰의 **[!UICONTROL 이름]**&#x200B;을 입력합니다.

   ![텍스트 토큰의 이름과 값을 입력하십시오](./assets/token-create-dialog.png){width="400"}

   토큰 이름에는 공백이나 특수 문자를 사용할 수 없습니다. `EventType`과(와) 같은 _카멜 대/소문자_&#x200B;을(를) 사용하여 쉽게 식별할 수 있는 여러 단어 이름을 사용할 수 있습니다.

1. 토큰의 **[!UICONTROL Type]**&#x200B;을(를) 선택하십시오.

1. 토큰에 대해 **[!UICONTROL 값]**&#x200B;을(를) 설정합니다.

1. **[!UICONTROL 만들기]**&#x200B;를 클릭합니다.

### 토큰 편집 {#edit}

정의된 내 토큰의 값을 편집할 수 있습니다. 이는 상속된 토큰의 값을 재정의합니다.

<!-- (How does this affect live person journeys? ) -->

1. _[!UICONTROL 토큰]_&#x200B;에서 토큰 이름 옆에 있는 _편집_ 아이콘을 클릭합니다.

1. 필드에서 필요에 따라 값을 변경합니다.

   ![토큰의 이름과 값을 변경합니다](assets/my-tokens-edit-text-token-dialog.png){width="400"}

1. _저장_ 아이콘을 클릭합니다.

### 토큰 삭제 {#delete}

사용자 지정 토큰이 현재 여정 이메일 콘텐츠에 사용되지 않는 경우 목록에서 삭제할 수 있습니다.

1. _[!UICONTROL 토큰]_&#x200B;에서 토큰 이름 옆에 있는 _삭제_ 아이콘을 클릭합니다.

1. 확인 대화 상자에서 **[!UICONTROL 삭제]**&#x200B;를 클릭합니다.

## 자동 제안 및 미리보기 {#autosuggest}

여정에 _데이터 값 변경_ [작업 노드](./action-nodes.md)을(를) 포함하는 경우 **[!UICONTROL 새 값]** 필드에 `{{`을(를) 입력하여 토큰 _자동 제안_ 메뉴를 표시할 수 있습니다. 표시된 목록에는 지원되는 네임스페이스 및 개별 토큰이 표시됩니다. 호환되는 데이터 형식의 토큰만 나열됩니다.

_내 토큰_&#x200B;의 경우 올바른 값을 쉽게 선택할 수 있도록 토큰 이름과 함께 토큰 값의 미리 보기가 표시됩니다.

![토큰에 대한 자동 사용자 지정 메뉴를 표시하는 새 값 필드의 구문](./assets/program-tokens-change-data-value-autosuggest.png){width="500" zoomable="yes"}

<!--

## Use custom tokens in your content

When you are authoring email content for your programs, you can use any of the tokens from the _My Tokens_ list when you use the personalization tools in the visual design space.

1. Select the text component and click the _Add personalization_ ( ![Add personalization icon](../assets/do-not-localize/icon-personalization-field.svg) ) icon in the toolbar.

   ![Click the Add personalization icon](assets/email-personalize-text.png){width="600"}

   This action opens the _Edit Personalization_ dialog. The dialog includes a _[!UICONTROL My tokens]_ folder in the _[!UICONTROL Personalization Tokens]_ library if there are custom tokens defined for the account journey.

1. To add one of your custom tokens to the blank space, expand the **[!UICONTROL My tokens]** folder, then click **+** or **...**.

   You can add any additional static text as needed.

   ![Construct personalized text using My tokens](assets/personalization-edit-dialog-my-tokens.png){width="700" zoomable="yes"}

1. Click **[!UICONTROL Save]**.

-->
