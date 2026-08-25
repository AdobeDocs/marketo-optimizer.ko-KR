---
title: Personalization용 사용자 지정 토큰
description: 마케팅 아티팩트의 동적 개인화를 위해 사용자 지정 내 토큰을 만들고 관리합니다. Marketo Optimizer에서 프로그램의 텍스트 및 숫자 변수를 정의합니다.
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: 629
ht-degree: 3%

---

# 개인화를 위한 사용자 지정 토큰

콘텐츠 개인화는 토큰을 콘텐츠 아티팩트가 생성될 때 채워지는 자리 표시자 또는 변수로 사용합니다. 표준 개인화 토큰은 이메일, 랜딩 페이지, 조각 및 템플릿에 사용할 수 있습니다. 프로그램 또는 폴더와 관련된 값을 사용하여 사용자 지정 토큰 세트를 정의할 수도 있습니다. 이 사용자 지정 토큰 집합을 _내 토큰_&#x200B;이라고 하며 이러한 사용자 지정 토큰은 모두 개인화용입니다.

사용자 지정 토큰을 전자 메일에 추가하면 `{{my.TokenName}}`(으)로 표시됩니다. 예를 들어 예정된 웨비나와 관련된 이메일 콘텐츠를 관리하기 위해 만든 토큰이 `{{my.EventDate}}` 또는 `{{my.WebinarSpeaker}}`개일 수 있습니다.

프로그램 또는 폴더에만 해당되는 _내 토큰_ 외에도 개인화를 위해 표준(기본 제공) 토큰을 사용할 수 있습니다.

>[!NOTE]
>
>_내 토큰_&#x200B;은(는) 현재 이 Beta 릴리스의 Personalization 편집기에서 사용할 수 없습니다.

## 토큰 액세스

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
| 날짜 | 이 유형에는 날짜 값이 있습니다. 날짜는 월-일-년(예: 09-23-2026)으로 표시됩니다. |
| 날짜 및 시간 | 이 유형에는 날짜 및 시간 값이 있습니다. |
| 숫자 | 이 유형은 표준 정수 값을 보유합니다. |
| 이메일 | 이 유형에는 유효한 이메일 주소가 있습니다. |
| 점수 | 여정 작업 노드의 점수 변경에 이 토큰을 사용합니다. |
| 부울 | 이 유형은 true 또는 false의 표준 부울 값을 보유합니다. |
| 리치 텍스트 | 이 형식에는 서식이 지정된 텍스트가 포함됩니다. |

### 토큰 중첩

프로그램 또는 폴더에서 토큰을 만들 때 다른 하위 개체에서 참조할 수 있습니다.

* 로컬 토큰 - 토큰은 동일한 프로그램 또는 폴더에 정의됩니다.
* 상속된 토큰 - 토큰은 상위 프로그램 또는 폴더에 정의되어 있으며 현재 프로그램 또는 폴더보다 한 수준 이상 높습니다.
* 재정의된 토큰 - 토큰은 상위 프로그램 또는 폴더에 정의되어 있지만 다른 값이 현재 프로그램 또는 폴더에 정의되어 있습니다. 토큰 상태가 _재정의됨_(으)로 바뀌고 모든 하위 폴더, 프로그램 및 마케팅 아티팩트가 새 값을 상속합니다.

![토큰 형식 및 상속](./assets/program-tokens-inherited-overridden.png){width="600" zoomable="yes"}

### 토큰 만들기

1. _[!UICONTROL 토큰]_ 탭에서 **[!UICONTROL 만들기]**&#x200B;를 클릭합니다.

1. 대화 상자에서 토큰의 **[!UICONTROL 이름]**&#x200B;을 입력합니다.

   ![텍스트 토큰의 이름과 값을 입력하십시오](./assets/token-create-dialog.png){width="400"}

   토큰 이름에는 공백이나 특수 문자를 사용할 수 없습니다. `EventType`과(와) 같은 _카멜 대/소문자_&#x200B;을(를) 사용하여 쉽게 식별할 수 있는 여러 단어 이름을 사용할 수 있습니다.

1. 토큰의 **[!UICONTROL Type]**&#x200B;을(를) 선택하십시오.

1. 토큰에 대해 **[!UICONTROL 값]**&#x200B;을(를) 설정합니다.

1. **[!UICONTROL 만들기]**&#x200B;를 클릭합니다.

### 토큰 편집

정의된 내 토큰의 값을 편집할 수 있습니다. 상속된 토큰의 값을 재정의하려면 이 작업을 수행합니다.

<!-- (How does this affect live person journeys? ) -->

1. _[!UICONTROL 토큰]_&#x200B;에서 토큰 이름 옆에 있는 _편집_ 아이콘을 클릭합니다.

1. 필드에서 필요에 따라 값을 변경합니다.

   ![토큰의 이름과 값을 변경합니다](assets/my-tokens-edit-text-token-dialog.png){width="400"}

1. _저장_ 아이콘을 클릭합니다.

### 토큰 삭제

사용자 지정 토큰이 현재 여정 이메일 콘텐츠에 사용되지 않는 경우 목록에서 삭제할 수 있습니다.

1. _[!UICONTROL 토큰]_&#x200B;에서 토큰 이름 옆에 있는 _삭제_ 아이콘을 클릭합니다.

1. 확인 대화 상자에서 **[!UICONTROL 삭제]**&#x200B;를 클릭합니다.

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
