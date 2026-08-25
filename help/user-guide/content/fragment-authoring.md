---
title: 조각 작성
description: 시각적 디자인 도구를 통해 재사용 가능한 콘텐츠 조각을 작성 - Marketo Optimizer에서 이메일 및 템플릿에 대한 구조, 에셋, 개인화, 조건부 콘텐츠 및 연결된 URL 추적을 추가합니다.
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 3%

---

# 조각 작성

[조각을 만들고](./fragments.md#create-fragments) 나면 시각적 디자인 공간을 사용하여 조각의 구조 및 콘텐츠 구성 요소를 작성합니다.

## 구조 및 콘텐츠 추가 {#design-fragment}

{{$include /help/_includes/content-design-components-prime.md}}

## 에셋 추가 {#add-assets}

시각적 디자인 공간에서 왼쪽 탐색 막대의 _Assets_( ![Assets 아이콘](../assets/do-not-localize/icon-assets-me.svg)) 아이콘을 선택하여 [!DNL Marketo Optimizer] 자산 라이브러리에서 이미지 자산을 찾아 선택합니다.

이미지 에셋을 선택, 대체 또는 업로드하는 단계는 [콘텐츠 작성에 에셋 사용](./digital-asset-management.md#assets-authoring)을 참조하십시오.

## 레이어, 설정 및 스타일 탐색 {#navigate-layers-settings-styles}

{{$include /help/_includes/content-design-navigation.md}}

## 콘텐츠 개인화 {#personalize-content}

[!DNL Marketo Optimizer]은(는) 개인화에 Handlebars 구문을 사용합니다. 전송 시 토큰은 각 수신자의 프로필 데이터에 있는 값으로 대체됩니다.

개인화를 추가하려면(_T):_

1. 텍스트 구성 요소를 선택하고 도구 모음에서 _개인화 추가_( ![개인화 아이콘](../assets/do-not-localize/icon-personalize.svg) ) 아이콘을 클릭합니다.
1. 개인화 대화 상자에서 왼쪽의 스키마 트리를 탐색하고 프로필 속성을 선택합니다. 편집기에서 해당 Handlebars 식을 삽입합니다(예: `{{profile.firstName}}`).
1. 필요한 경우 누락된 데이터를 처리할 대체 값을 추가합니다(예: `{{profile.firstName | default: "there"}}`).
1. **[!UICONTROL 확인]** 또는 **[!UICONTROL 삽입]**&#x200B;을 클릭합니다. 표현식이 필드에 인라인으로 표시됩니다.

표현식 편집기 도구 및 구문에 대한 자세한 내용은 [Personalization 편집기](./personalization-expressions.md)를 참조하십시오.

## 연결된 URL 추적 편집 {#edit-linked-url-tracking}

{{$include /help/_includes/content-design-links.md}}
