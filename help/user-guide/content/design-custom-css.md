---
title: 콘텐츠에 대한 사용자 지정 CSS 추가
description: Marketo Optimizer의 표준 구성 요소를 넘어 고급 스타일 지정 및 정밀한 디자인 제어를 위해 이메일 및 랜딩 페이지에 사용자 지정 CSS를 추가합니다.
feature: Content Design Tools, Email Authoring, Landing Pages
role: User
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 0%

---

# 콘텐츠에 대한 사용자 지정 CSS 추가

이메일 또는 랜딩 페이지 디자인 공간 내에 직접 사용자 지정 CSS를 추가할 수 있습니다. 사용자 지정 CSS를 사용하여 콘텐츠의 모양을 보다 유연하게 제어하고, 고급 및 특정 스타일을 적용할 수 있습니다.

사용자 지정 CSS는 `data-name="global-custom"` 특성을 사용하여 `<style>` 태그 내의 `<head>` 섹션에 추가됩니다. 이 구조를 사용하면 사용자 지정 스타일이 콘텐츠에 전체적으로 적용됩니다.

+++ 예제 구현

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="content-version" content="3.3.31">
    <meta name="x-apple-disable-message-reformatting">
    <meta name="viewport" content="width=device-width,initial-scale=1.0">
    <style data-name="default" type="text/css">
      td { padding: 0; }
      th { font-weight: normal; }
    </style>
    <style data-name="grid" type="text/css">
      .acr-grid-table { width: 100%; }
    </style>
    <style data-name="acr-theme" type="text/css" data-theme="default" data-variant="0">
      body { margin: 0; font-family: Arial; }
    </style>
    <style data-name="media-default-max-width-500px" type="text/css">
      @media screen and (max-width: 500px) {
        body { width: 100% !important; }
      }
    </style>
    <style data-name="global-custom" type="text/css">
      /* Add you custom CSS here */
    </style>
  </head>
  <body>
    <!-- Minimal content -->
  </body>
</html>
```

+++

>[!NOTE]
>
>사용자 지정 CSS가 선택한 구성 요소의 _[!UICONTROL 스타일]_ 패널에 반영되거나 확인되지 않았습니다. 완전히 독립적이며 본문 구성 요소 수준에서 [!UICONTROL 사용자 지정 CSS 추가] 옵션을 통해서만 수정할 수 있습니다.

## 사용자 지정 CSS 추가

1. 캔버스에 콘텐츠 구성 요소를 하나 이상 추가한 상태에서 왼쪽 탐색에서 **[!UICONTROL 본문]** 구성 요소를 선택합니다.

1. 오른쪽의 _스타일_ 탭을 선택하고 **[!UICONTROL 사용자 지정 CSS 추가]**&#x200B;를 클릭합니다.

   ![본문 스타일에 액세스](assets/email-body-styles.png){width="800" zoomable="yes"}

   >[!NOTE]
   >
   >_[!UICONTROL 사용자 지정 CSS 추가]_ 단추는 _[!UICONTROL Body]_ 구성 요소를 선택한 경우에만 사용할 수 있습니다. 그러나 사용자 지정 CSS 스타일을 그 안의 모든 구성 요소에 적용할 수 있습니다.

   _[!UICONTROL 사용자 지정 CSS 추가]_ 팝업 편집기에 자리 표시자 코드 주석이 표시됩니다.

1. 편집기에 CSS 코드를 입력합니다.

   사용자 지정 CSS가 올바르고 적절한 구문을 따르는지 확인하십시오. 입력한 CSS가 올바르지 않으면 오류 메시지가 표시되고 CSS를 저장할 수 없습니다. 자세한 내용은 [CSS 유효성](#css-validity)을 참조하세요.

   ![편집기에 사용자 지정 CSS 입력](assets/content-design-add-custom-css.png){width="450"}

1. 사용자 지정 CSS를 저장하려면 **[!UICONTROL 저장]**&#x200B;을 클릭합니다.

   사용자 지정 스타일 시트가 기존 콘텐츠에 적용됩니다. 사용자 지정 CSS가 필요에 따라 적용되는지 확인할 수 있습니다. 스타일 시트 응용 프로그램을 변경하고 조정하는 방법에 대한 자세한 내용은 [문제 해결](#troubleshooting)을 참조하십시오.

   ![콘텐츠에 적용된 사용자 지정 CSS](assets/email-body-custom-css-applied.png){width="600" zoomable="yes"}

## CSS 유효성 {#css-validity}

>[!CAUTION]
>
>사용자는 사용자 지정 CSS의 보안을 책임집니다. CSS에 취약점이 도입되거나 기존 콘텐츠와 충돌하지 않는지 확인하십시오.
>
>의도하지 않게 컨텐츠의 레이아웃 또는 기능을 손상시킬 수 있는 CSS를 사용하지 마십시오.

+++ 유효한 CSS의 예

```css
.acr-component[data-component-id="form"] {
  display: flex;
  justify-content: center;
  background: none;
}

.acr-Form {
  width: 100%;
  padding: 20px 100px;
  border-spacing: 0px 8px;
  box-sizing: border-box;
  margin: 0;
}

.acr-Form .spectrum-FieldLabel {
  width: 20%;
}

.acr-Form.spectrum-Form--labelsAbove .spectrum-FieldLabel,
.acr-Form [data-form-item="checkbox"] .spectrum-FieldLabel {
  width: auto;
}

.acr-Form .spectrum-Textfield {
  width: 100%;
}

#acr-form-error,
#acr-form-confirmation {
  width: 100%;
  padding: var(--spectrum-global-dimension-static-size-500);
  display: flex;
  align-items: center;
  flex-direction: column;
  justify-content: center;
  gap: var(--spectrum-global-dimension-static-size-200);
}

.spectrum-Form-item.is-required .spectrum-FieldLabel:after{
  content: '*';
  font-size: 1.25rem;
  margin-left: 5px;
  position: absolute;
}

/* Error field placeholder */
.spectrum-HelpText {
  display: none !important;
}

.spectrum-HelpText.is-invalid,
.is-invalid ~ .spectrum-HelpText {
  display: flex !important;
}
```

```css
@media only screen and (min-width: 600px) {
  .acr-paragraph-1 {
    width: 100% !important;
  }
}
```

+++

+++ 잘못된 CSS의 예

`<style>` 태그를 사용할 수 없습니다.

```html
<style type="text/css">
  .acr-Form {
    width: 100%;
    padding: 20px 100px;
    border-spacing: 0px 8px;
    box-sizing: border-box;
    margin: 0;
  }
</style>
```

중괄호 누락과 같은 잘못된 구문은 허용되지 않습니다.

```css
body {
  background: red;
```

+++

## 가져온 콘텐츠의 CSS {#imported-content}

이메일 또는 랜딩 페이지 디자인 공간으로 가져온 콘텐츠와 함께 사용자 지정 CSS를 사용하려면 다음을 고려하십시오.

* CSS를 포함한 외부 HTML 콘텐츠를 가져오는 경우 [!UICONTROL 호환성 모드]에서 채워지고 [!UICONTROL CSS 스타일] 섹션을 사용할 수 없습니다.

* [!UICONTROL 사용자 지정 CSS 추가] 옵션을 사용하여 전자 메일 또는 랜딩 페이지 디자인 공간에서 원래 만들어진 콘텐츠를 가져오는 경우 적용된 CSS가 동일한 옵션에서 표시되고 편집할 수 있습니다.

## 문제 해결 {#troubleshooting}

사용자 지정 CSS가 예상대로 적용되지 않는 경우 브라우저 개발자 도구를 사용하여 콘텐츠를 검사하고 CSS가 올바른 선택기를 대상으로 하는지 확인하십시오. 스타일 코드를 검토할 때 다음 사항을 고려하십시오.

* CSS가 올바르고 구문 오류가 없는지 확인합니다(예: 중괄호 누락, 잘못된 속성 이름).

* CSS가 `data-name="global-custom"` 특성이 있는 `<style>` 태그에 추가되었는지 확인하십시오.

* `global-custom` 스타일 태그의 특성 `data-disabled`이(가) true로 설정되어 있는지 확인합니다. 예:

  `<style data-name="global-custom" type="text/css" data-disabled="true"> body: { color: red; } </style>`

* CSS가 적용된 인라인 스타일링과 같이 컨텐츠의 어딘가에 재정의되지 않았는지 확인하십시오.

* 다음과 같이 우선 순위를 두려면 선언에 `!important`을(를) 추가하십시오.

  ```
  .acr-Form {
  background: red !important;
  }
  ```
