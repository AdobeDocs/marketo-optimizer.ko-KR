---
title: 자산
description: 이메일, 템플릿 및 시각적 조각에 대한 Marketo Optimizer의 이미지 에셋을 관리합니다.
feature: Assets, Content
role: User
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 19%

---

# 자산

[!DNL Adobe Marketo Optimizer]에서 에셋은 일반적으로 여정을 지원하는 콘텐츠를 디자인할 때 사용되는 이미지입니다. 자산 선택기의 [전자 메일](email-authoring.md), [전자 메일 템플릿](templates.md) 및 [시각적 조각](email-authoring.md#visual-fragments) 또는 시각적 디자인 공간 내의 간단한 드래그 앤 드롭 인터페이스에서 이러한 이미지를 사용할 수 있습니다.

지원되는 파일 형식: JPG, JPEG, GIF, PNG, EPS, SVG 및 RGB

<!--

>In this Beta release, you can choose images and assets from a one-time copy of your Marketo Engage asset library directly inside the email canvas. Modifying assets in Marketo Engage after the initial copy is **not** reflected in [!DNL Marketo Optimizer].

-->

>[!NOTE]
>
>_[!UICONTROL Assets]_ 라이브러리 또는 콘텐츠 디자인 공간에서 이미지 에셋을 업로드할 수 있습니다. 업로드된 이러한 자산은 [!DNL Marketo Optimizer] 인스턴스에서만 사용할 수 있습니다.
>
>외부 시스템에서 에셋을 가져오고 미리 채워진 에셋 라이브러리에 액세스할 수 없습니다. 향후 릴리스에는 기존 시스템의 자산 가져오기, 폴더 지원 및 확장된 자산 관리 기능이 포함될 것으로 예상됩니다.

<!-- You can [edit these assets using Adobe Express](./image-edit-adobe-express.md), and move them into folders to organize them for use across your emails, templates, and fragments. -->

**Assets** 라이브러리는 이미지 및 기타 크리에이티브 자산을 저장하고 관리하기 위한 중앙 저장소에 대한 액세스를 제공합니다. 여기에는 메타데이터를 자동으로 생성하고 자연어 검색을 가능하게 하는 AI 기반의 기능이 포함되어 있습니다.

왼쪽 탐색에서 **[!UICONTROL 콘텐츠 관리]**&#x200B;를 확장하고 **[!UICONTROL Assets]**&#x200B;을 선택합니다.

정렬 가능한 메타데이터 열을 표시하는 ![Assets 라이브러리 목록 보기](./assets/dam-asset-library-list-view.png){width="800" zoomable="yes"}

>[!BEGINSHADEBOX]

_[!UICONTROL Assets]_ 라이브러리에 처음 액세스하면 [_[!UICONTROL Generative AI 사용 약관&#x200B;]_](https://www.adobe.com/kr/legal/licenses-terms/adobe-gen-ai-user-guidelines.html)을 검토하고 동의를 확인하십시오.

Assets 라이브러리의 ![생성 AI 사용 약관 계약 대화 상자](./assets/dam-asset-library-gen-ai-agree.png){width="500"}

>[!ENDSHADEBOX]

라이브러리는 다음 두 가지 레이아웃 옵션을 지원합니다.

* **[!UICONTROL 목록]** — 메타데이터 열이 있는 정렬 가능한 테이블에 에셋을 표시하려면 _목록 보기_( ![목록 보기 아이콘](../assets/do-not-localize/icon-falco-list-view.svg) ) 아이콘을 클릭합니다.
* **[!UICONTROL 갤러리]** — 자산을 시각적 썸네일 격자로 표시하려면 _갤러리 보기_( ![갤러리 보기 아이콘](../assets/do-not-localize/icon-falco-gallery-view.svg)) 아이콘을 클릭합니다.

## 자산 검색 {#find-assets}

필요한 내용을 자연어로 설명하여 자산을 찾으려면 _[!UICONTROL 검색]_ 필드를 사용하십시오. 검색 결과는 AI가 생성한 메타데이터를 기반으로 하므로 파일 이름별로 검색하도록 제한되지 않습니다.

**예:**

* `team members`
* `nature`
* `exercise`

![Assets 라이브러리의 검색 결과에서 선택한 이미지](./assets/dam-asset-library-select-image.png){width="700" zoomable="yes"}

## 자산 세부 사항 보기 {#view-details}

목록 또는 갤러리 보기에서 에셋을 선택하여 오른쪽에 세부 사항 보기를 엽니다. 이 보기에는 AI가 생성한 설명, 태그, 키워드 및 추가 메타데이터 필드가 표시됩니다. 에셋이 업로드되면 이 정보가 자동으로 생성됩니다. 생성된 설명, 태그 및 메타데이터를 검토하려면 **[!UICONTROL AI 메타데이터]** 탭을 선택하십시오.

![AI가 생성한 메타데이터와 태그를 보여 주는 자산 세부 정보 보기](./assets/dam-asset-library-select-image-metadata.png){width="700" zoomable="yes"}

## 에셋 업로드 {#upload}

1. 오른쪽 상단의 **[!UICONTROL 업로드]**&#x200B;를 클릭합니다.

1. 대화 상자에서 로컬 시스템에서 파일을 끌어서 놓습니다.

   ![이미지 자산 업로드](./assets/dam-upload-assets-dialog.png){width="450"}

   또는 **[!UICONTROL 컴퓨터에서 파일 선택]**&#x200B;을 클릭하여 로컬 파일 시스템을 사용하여 파일을 찾아 선택할 수 있습니다.

1. **[!UICONTROL 파일 업로드]**&#x200B;를 클릭하여 파일을 확인하고 저장소에 업로드합니다.

업로드가 완료되면 시스템에서 설명을 자동으로 생성하고, 태그와 키워드를 지정하며, 제목 및 설정과 같은 시각적 속성을 추출합니다. 수동 태깅은 필요하지 않습니다. 이 프로세스가 완료될 때까지 새 이미지가 _[!UICONTROL 처리 중]_ 상태로 표시됩니다.

![처리 중인 새 이미지 자산](./assets/dam-asset-library-upload-processing.png){width="700" zoomable="yes"}

## 자산을 사용하여 콘텐츠 작성 {#assets-authoring}

이메일, 이메일 템플릿 및 시각적 조각을 작성할 때 에셋을 사용하십시오. 시각적 콘텐츠 편집기에서 _Assets_ 라이브러리의 이미지에 액세스할 수 있습니다. 이미지 에셋을 업로드하여 내부 에셋 저장소에 배치할 수도 있습니다.

이미지 구성 요소에 대한 설정을 편집할 때 또는 캔버스에서 직접 이미지 에셋을 선택할 수 있습니다.

* **_구성 요소 비어 있음_** - 캔버스에 이미지 구성 요소를 추가하면 해당 구성 요소가 비어 있고 이미지 파일을 선택하거나 가져올 수 있는 간편한 액세스를 제공합니다.

  ![소스를 선택하여 빈 이미지 구성 요소에 대한 이미지 파일 선택](./assets/dam-assets-image-component-empty.png){width="500"}

* **_이미지 구성 요소 도구 모음_** - 캔버스에서 이미지 구성 요소를 선택한 경우 도구 모음을 통해 소스를 선택하고 이미지 파일을 선택할 수 있습니다.

  ![도구 모음을 사용하여 이미지 구성 요소에 대한 이미지 파일을 선택할 소스 선택](./assets/dam-assets-image-toolbar-settings.png){width="500"}

* **_이미지 구성 요소 설정_** - 캔버스에서 이미지 구성 요소를 선택한 경우 오른쪽 패널에서 설정을 보고 편집할 수 있습니다. 구성 요소에 표시되는 이미지 파일을 추가하거나 변경하려면 소스 유형을 선택하고 이미지 파일을 선택합니다.

  ![오른쪽 패널에서 이미지 구성 요소 설정 편집](./assets/dam-assets-image-settings.png){width="350"}

[!DNL Marketo Optimizer] 자산 저장소에서 이미지를 선택할 수 있는 자산 선택기를 열려면 **[!UICONTROL 자산 선택]**&#x200B;을 클릭합니다.

![이미지 자산 선택](./assets/dam-assets-internal-image-selected.png){width="700" zoomable="yes"}

검색어와 필터를 사용하여 원하는 이미지 자산을 찾을 수 있습니다. 자산을 선택하고 **[!UICONTROL 선택]**&#x200B;을 클릭하여 이미지 구성 요소에 사용합니다.

구조 구성 요소의 배경 설정에서 이미지 에셋을 선택할 수도 있습니다.
