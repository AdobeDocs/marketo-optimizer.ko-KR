---
title: Personalization 편집기
description: Marketo Optimizer에서 개인화 편집기를 사용하여 이메일, WhatsApp 메시지, 랜딩 페이지 및 URL 필드에서 프로필 속성 토큰을 선택, 정렬, 사용자 지정 및 확인하는 방법을 알아봅니다.
feature: Content Design Tools
role: User
source-git-commit: 75b481faf0d66210329f95c8afabdfa59e7bcb79
workflow-type: tm+mt
source-wordcount: '1002'
ht-degree: 12%

---

# 개인화 편집기

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_personalization_editor"
>title="개인화 편집기 정보"
>abstract="개인화 편집기를 통해 프로필 속성을 선택하고, 배열하고, 사용자 정의하고 검증하여 개인 맞춤화된 콘텐츠를 제작할 수 있습니다."

개인화 편집기는 [!DNL Marketo Optimizer]에서 개인화의 중심입니다. 이메일, WhatsApp 메시지, 랜딩 페이지 및 URL 필드 등 다이내믹 컨텐츠가 필요한 곳에서 사용할 수 있습니다.

개인화 편집기 인터페이스에서 프로필 속성을 선택하고, 정렬하고, 맞춤화하고, 유효성을 검사하여 개인화된 콘텐츠를 만들 수 있습니다.

![개인화 표현식 편집기](./assets/personalization-editor.png){width="700" zoomable="yes"}

>[!NOTE]
>
>이 Beta 릴리스의 개인화 편집기에서는 프로필 속성만 사용할 수 있습니다. 계정 수준 개인화 및 사용자 지정 개체 데이터를 사용할 수 없습니다. [현재 제한](../marketing/email-channel.md#limitations)을 참조하십시오.

_개인화_( ![개인화 아이콘](../assets/do-not-localize/icon-personalize.svg) ) 아이콘을 사용하여 모든 필드에 개인화를 추가할 수 있습니다. 자세한 내용을 보려면 다음 섹션을 확장하십시오.

+++이메일 및 WhatsApp 메시지

[이메일](./email-authoring.md#personalize-content) 및 [WhatsApp 메시지](./whatsapp-authoring.md#personalize-message-content)에서 이메일의 **[!UICONTROL 제목 줄]** 필드 또는 승인된 WhatsApp 템플릿의 동적 매개 변수와 같은 다른 위치에 개인화를 추가할 수 있습니다.

이메일 본문 텍스트, 사전 머리글 및 단추 URL을 포함하여 콘텐츠의 다른 섹션에도 추가할 수 있습니다.

+++

+++콘텐츠 디자인 공간

시각적 컨텐츠를 편집할 때 상황별 도구 모음의 아이콘을 사용하여 대부분의 텍스트 요소에 개인화를 추가할 수 있습니다.

<!-- ![](assets/perso_insert.png) -->

+++

+++URL

[!DNL Marketo Optimizer]을(를) 사용하면 메시지에서 **URL**&#x200B;을(를) 개인화할 수도 있습니다. 개인화된 URL은 프로필 속성에 따라 수신자를 웹사이트의 특정 페이지 또는 개인화된 마이크로사이트로 이동합니다.

<!-- ![](assets/perso-url.png){width="50%"} -->

>[!NOTE]
>
>URL 개인화는 **외부 링크**, **구독 취소 링크** 및 **옵트아웃** 유형의 링크에서 사용할 수 있습니다.

+++

+++이메일 구성

[전자 메일 채널 구성](../admin/email-channel-configuration.md)을 만들 때 하위 도메인, 헤더 및 URL 추적 매개 변수에 대해 개인화된 값을 정의할 수 있습니다.

+++

## 개인화 추가 {#add}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_perso_editor_autocomplete"
>title="자동 완성"
>abstract="이 옵션을 토글하여 활성화하면 코드 입력 시 시스템이 자동으로 코드를 제안하고 완성합니다. 이 기능은 HTML 및 텍스트 형식에 대해서만 사용할 수 있으며, 프로필 속성을 지원합니다. 이 옵션을 토글하여 비활성화하면 편집기는 기본 HTML 코드 자동 완성 기능을 대신 제공합니다."

중앙 작업 영역은 개인화 구문을 작성하는 위치입니다. 특성을 사용하여 메시지를 개인화하려면 왼쪽 탐색 창에서 특성을 찾은 다음 `+` 단추를 클릭하여 식에 추가하십시오.

<!-- ![](assets/personalization-add-attribute.png) -->

`+` 아이콘 옆에 있는 줄임표 메뉴를 사용하면 각 속성에 대한 자세한 내용을 확인하고 자주 사용하는 특성을 즐겨찾기에 추가할 수 있습니다. 즐겨찾기에 추가된 특성은 탐색 창의 **[!UICONTROL 즐겨찾기]** 메뉴에서 액세스할 수 있습니다.

>[!NOTE]
>
>기본적으로 속성 창에는 채워진 속성만 표시됩니다. 모든 특성을 표시하려면 특성 창에서 **[!UICONTROL 설정]** 단추를 선택하고 **[!UICONTROL 채워진 특성만 표시]** 옵션을 끄십시오.

또한 문자열 유형 프로필 속성이 비어 있는 경우 표시될 기본 대체 텍스트를 정의할 수 있습니다. 이렇게 하려면 특성 옆에 있는 줄임표 버튼을 클릭하고 **[!UICONTROL 대체 텍스트로 삽입]**&#x200B;을 선택합니다. 프로필에 대한 특성 값이 비어 있는 경우 기본적으로 표시되는 텍스트를 작성한 다음 **[!UICONTROL 추가]**&#x200B;를 클릭합니다.

<!-- ![](assets/attribute-details.png) -->

예를 들어 값이 누락된 경우 `{{profile.firstName}}`을(를) 사용하여 이름별로 각 수신자에게 인사할 수 있습니다. `{{profile.firstName | default: "there"}}`.

## 표현식 편집 옵션 {#options}

중앙 작업 영역은 개인화 표현식을 작성하는 데 도움이 되는 다양한 도구를 제공합니다.

<!-- ![](assets/perso-workspace.png) -->

사용 가능한 옵션은 다음과 같습니다.

1. **[!UICONTROL 찾기]** / **[!UICONTROL 찾기 및 바꾸기]**: 식을 검색하고 코드 부분을 자동으로 바꿉니다.
1. **[!UICONTROL 실행 취소]** / **[!UICONTROL 다시 실행]**: 마지막 작업을 실행 취소/다시 실행합니다.
1. **[!UICONTROL 자동 완성]**: 입력할 때 코드를 자동으로 제안하고 완료합니다. 이 기능은 HTML 및 텍스트 형식에 대해서만 사용할 수 있으며, 프로필 속성을 지원합니다. 이 옵션을 토글하여 비활성화하면 편집기는 기본 HTML 코드 자동 완성 기능을 대신 제공합니다.

   <!-- ![](assets/perso-complete.png){width="70%" align="center" zoomable="yes"} -->

1. **[!UICONTROL HTML]** / **[!UICONTROL JSON]** / **[!UICONTROL 텍스트]**: 코드 형식을 식별합니다. 이렇게 하면 시스템이 선택한 언어를 기반으로 유효성 검사 및 자동 완성 기능을 조정할 수 있습니다.
1. **[!UICONTROL 유효성 검사]**: 식의 구문을 확인하십시오.
1. **[!UICONTROL 글꼴 크기]**: 가독성을 높이기 위해 편집기 내의 콘텐츠 글꼴 크기를 조정합니다.
1. **[!UICONTROL 자동 줄 바꿈]**: 자동 줄 바꿈을 사용하거나 사용하지 않도록 설정하여 긴 식을 한 줄에 표시하거나 편집기 내에서 줄 바꿈할 수 있습니다. 옵션은 다음과 같습니다.
   * **해제**(기본값) - 줄 바꿈이 없습니다. 긴 줄은 편집기 보기를 넘어 확장되므로 수평 스크롤이 필요합니다.
   * **On** - 편집기 너비의 줄을 줄바꿈합니다.
   * **줄 바꿈 열** - 줄이 80자에 도달하면 줄을 바꿈합니다.
   * **Bounded** - 편집기 너비 또는 80자 중 더 작은 문자를 줄바꿈합니다.
1. **[!UICONTROL 알약]**: 특성을 작은 &quot;알약&quot;으로 표시하여 긴 특성 경로를 숨겨서 가독성을 향상시킵니다. 속성을 클릭하여 전체 경로를 표시합니다.

   >[!NOTE]
   >
   >이 옵션은 프로필 속성에만 사용할 수 있습니다.

탐색 창에서는 개인화 표현식을 작성하는 데 도움이 되는 추가 기능을 사용할 수 있습니다.

<!-- ![](assets/perso-features.png) -->

* **[!UICONTROL 도우미 함수]** - 도우미 함수를 사용하면 계산, 데이터 서식 또는 전환, 조건 등 데이터에 대한 작업을 수행하고 개인 맞춤화의 컨텍스트에서 조작할 수 있습니다.

* **[!UICONTROL 즐겨찾기]** - 즐겨찾기에 추가한 특성이 이 목록에 표시됩니다. 이를 통해 가장 자주 사용하는 항목에 빠르게 액세스할 수 있습니다. 즐겨찾기에 특성을 추가하려면 줄임표 메뉴를 클릭하고 **[!UICONTROL 즐겨찾기에 추가]**&#x200B;를 선택하십시오.

동료는 일반 언어 설명에서 Handlebars 표현식을 생성하고, 기존 표현식을 설명하고, 잠재적인 문제를 식별할 수 있습니다.

개인화 식이 준비되면 **[!UICONTROL 확인]** 또는 **[!UICONTROL 삽입]**&#x200B;을 클릭하여 콘텐츠에 추가하십시오.

## 유효성 검사 메커니즘 {#validation-mechanisms}

편집기를 닫으려면 **[!UICONTROL 확인]** 또는 **[!UICONTROL 삽입]**&#x200B;을 클릭하면 식의 유효성 검사가 자동으로 실행됩니다. 닫기 전에 **[!UICONTROL 유효성 검사]**&#x200B;를 클릭하여 개인화 구문을 확인할 수도 있습니다.

여정 활성화를 차단하는 콘텐츠 경고에 대해서는 [전자 메일 콘텐츠 확인](./email-authoring.md#validation)을 참조하세요.

다음 섹션을 확장하여 개인화를 확인할 때 발생할 수 있는 일반적인 오류를 확인합니다.

+++일반적인 오류

* **경로 &quot;XYZ&quot;를 찾을 수 없음**

이 오류는 스키마에 정의되지 않은 필드를 참조할 때 발생합니다.

이 경우 **firstName1**&#x200B;은(는) 프로필 스키마에 특성으로 정의되어 있지 않습니다.

```handlebars
{{profile.firstName1}}
```

* **변수 &quot;XYZ&quot;에 대한 형식이 일치하지 않습니다. 배열이 필요합니다. 문자열을 찾았습니다.**

이 오류는 배열 대신 문자열을 반복하려고 할 때 발생합니다.

이 경우 **jobTitle**&#x200B;은(는) 배열이 아닌 문자열입니다.

```handlebars
{{#each profile.jobTitle as |item|}}
  {{item}}
{{/each}}
```

* **잘못된 Handlebars 구문입니다.`'[XYZ}}'`**&#x200B;을(를) 찾음

이 오류는 잘못된 Handlebars 구문을 사용할 때 발생합니다.

```handlebars
{{[profile.firstName}}
```

+++
