---
title: WhatsApp 작성
description: Marketo Optimizer에서 승인된 Meta 템플릿, 개인화 토큰 및 게재 설정을 사용하여 개인 여정을 위한 WhatsApp 메시지를 만듭니다.
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: 801
ht-degree: 1%

---

# WhatsApp 작성

[!DNL Adobe Marketo Optimizer]을(를) 사용하여 모바일 장치에 있는 사람들에게 WhatsApp 메시지를 보냅니다. WhatsApp 편집기에서 승인된 Meta 메시지 템플릿을 사용하여 메시지를 만들고, 개인화하고, 미리 볼 수 있습니다.

개인 여정에 대한 WhatsApp 메시지를 만들기 전에 _[!UICONTROL 관리자]_ 설정에서 [WhatsApp 채널이 구성](../admin/configuration-channels-whatsapp.md)되어 있는지 확인하십시오.

>[!NOTE]
>
>[!DNL Marketo Optimizer]에서는 _아웃바운드_ WhatsApp 메시지 요소만 지원됩니다.

+++ 지원되는 메시지 요소 및 call-to-action 옵션

이 섹션의 표는 승인된 Meta 템플릿에 포함할 수 있는 아웃바운드 WhatsApp 콘텐츠 및 메시지에 추가할 수 있는 대화형 단추에 대한 참조로 사용됩니다.

다음 표에는 지원되는 메시지 요소 및 해당 요구 사항이 요약되어 있습니다.

| 메시지 요소 | 설명 |
| - | - |
| 헤더 | 메시지 본문 위에 표시되는 선택적 텍스트입니다. |
| 텍스트 | 매개 변수를 통해 다이내믹 콘텐츠를 지원합니다. |
| 이미지(JPEG, PNG) | 8비트 RGB 또는 RGBA 형식이어야 하며 크기가 5MB 미만이어야 합니다. |
| 비디오 | 16MB 이하의 3GPP 또는 MP4여야 하며 URL로 호스팅되어야 합니다. |
| 오디오 | 응답 메시지에만 사용할 수 있습니다. AAC, AMR, MP3, MP4 오디오 또는 OGG 형식이어야 하며 URL에서 호스팅되고 16MB 미만이어야 합니다. |
| 문서 | URL에서 호스팅되는 100MB 미만이어야 하며 `.txt`, `.xls`/`.xlsx`, `.doc`/`.docx`, `.ppt`/`.pptx` 또는 `.pdf` 형식 중 하나여야 합니다. |
| 본문 | 매개 변수를 통해 다이내믹 콘텐츠를 지원합니다. |
| 바닥글 텍스트 | 매개 변수를 통해 다이내믹 콘텐츠를 지원합니다. |

다음 표에는 call-to-action 단추 유형과 각 단추가 메시지에서 작동하는 방식이 나열되어 있습니다.

| Call to action | 설명 |
| - | - |
| 웹 사이트 방문 | 변수 매개 변수가 포함된 단추는 하나만 허용됩니다. |
| WhatsApp 호출 | 메시지에서 직접 지정된 전화번호로 WhatsApp 채팅을 여는 단추를 제공합니다. |
| 전화 번호 | 사용자가 탭하면 지정된 번호로 전화를 걸 수 있는 단추를 제공합니다. |

+++

## 개인 여정에 WhatsApp 작업 추가 {#add-whatsapp-journey-action}

>[!IMPORTANT]
>
>**WhatsApp 동의 관리**: Meta의 정책 및 해당 규정에 따라 모든 WhatsApp 마케팅 메시지는 커뮤니케이션 수신을 선택한 수신자에게만 전송되어야 합니다. WhatsApp 수신자는 언제든지 옵트아웃 키워드로 회신하여 옵트아웃할 수 있습니다. 옵트아웃 응답은 자동으로 적용되며, 해당 프로필은 향후 마케팅 메시지 대상자에서 제거됩니다.

[_[!UICONTROL 작업 수행]_ 여정](../marketing/action-nodes.md)을 추가하고 작업 목록에서 **[!UICONTROL WhatsApp 보내기]**&#x200B;를 선택하면 개인 노드에서 WhatsApp 메시지 게재를 설정할 수 있습니다.

## WhatsApp 메시지 만들기 {#create-whatsapp-message}

1. _[!UICONTROL 작업 수행]_ 패널 아래쪽에서 **[!UICONTROL WhatsApp 만들기]**&#x200B;를 클릭합니다.

1. 대화 상자에서 WhatsApp 메시지에 고유한 **[!UICONTROL 이름]**(필수)과 **[!UICONTROL 설명]**(선택 사항)을 입력합니다.

   ![새 WhatsApp 메시지 대화 상자 만들기](assets/whatsapp-create-dialog.png){width="400"}

1. **[!UICONTROL 만들기]**&#x200B;를 클릭합니다.

   WhatsApp 작업을 정의하고 메시지를 보낼 콘텐츠를 만들 수 있는 _WhatsApp 디자인 공간_&#x200B;이 열립니다.

### 작업 구성 선택 {#select-actions-configuration}

1. _WhatsApp 디자인 공간_&#x200B;에서 **[!UICONTROL 작업]** 탭을 선택합니다.

1. **[!UICONTROL WhatsApp 구성]**&#x200B;에 대해 필요에 따라 마케팅 액션 및 메시지 게재 설정을 지원하는 구성을 선택하십시오.

   ![WhatsApp 만들기 - 작업 탭](assets/whatsapp-create-actions-tab.png){width="700" zoomable="yes"}

1. 메시지 매개 변수 및 텍스트로 진행하려면 **[!UICONTROL 콘텐츠 편집]**&#x200B;을 클릭하세요.

### 메시지 템플릿 선택 {#select-message-template}

WhatsApp 메시지는 Meta WhatsApp 비즈니스 계정에서 사전 승인된 메시지 템플릿을 사용하여 전송됩니다. [!DNL Marketo Optimizer]에서 사용하려면 **Meta에서 템플릿을 검토하고 승인**&#x200B;해야 합니다. 승인을 위해 템플릿을 관리하고 제출하려면 [!DNL Meta Business Manager] 계정 관리자와 협력하십시오.

1. **[!UICONTROL 템플릿 범주 선택]**&#x200B;에 대해 다음 중 하나를 선택하십시오.

   * 마케팅
   * 유틸리티
   * 인증

1. **[!UICONTROL WhatsApp 템플릿 선택]**&#x200B;의 경우 구성된 비즈니스 계정에 대해 승인된 템플릿을 선택하십시오.

   템플릿 컨텐츠가 메시지 편집기에 로드되고 템플릿 구조와 개인화에 사용할 수 있는 모든 변수 필드가 표시됩니다.

   미리 보기 창에 메시지가 로드된 ![선택한 WhatsApp 메시지 템플릿](assets/whatsapp-create-select-template.png){width="700" zoomable="yes"}

   시스템은 범주(_마케팅_, _유틸리티_, _인증_) 및 상태별로 템플릿을 구성합니다. **_승인됨_** 템플릿만 선택할 수 있습니다. WhatsApp 템플릿 만들기에 대한 자세한 내용은 Meta 설명서에서 [_WhatsApp 비즈니스 계정에 대한 메시지 템플릿 만들기_](https://www.facebook.com/business/help/2055875911147364?id=2129163877102343)를 참조하십시오.

### 이미지 URL {#image-urls}

템플릿에 이미지가 포함된 경우 **[!UICONTROL 이미지 URL]** 필드를 사용하여 미디어 URL을 추가하여 템플릿의 자리 표시자를 바꾸십시오. Meta의 템플릿 미디어는 자리 표시자일 뿐입니다. 이미지, 오디오 또는 비디오를 올바르게 표시하려면 Adobe Experience Manager 또는 기타 소스의 외부 URL을 사용해야 합니다.

### 메시지 콘텐츠 개인화 {#personalize-message-content}

승인된 WhatsApp 템플릿에는 프로필 데이터 또는 동적 값을 사용하여 정의하는 변수 자리 표시자가 포함될 수 있습니다.

템플릿에 표시된 각 변수 필드에 대해 필드 옆에 있는 _개인화_ 아이콘(![개인화 아이콘](../assets/do-not-localize/icon-personalize.svg))을 클릭합니다.

![WhatsApp 템플릿의 변수](assets/whatsapp-create-variables.png){width="700" zoomable="yes"}

이 대화 상자에서는 개인 토큰 및 시스템 토큰에 액세스할 수 있습니다. 표준 및 사용자 지정 토큰이 모두 포함됩니다. _검색_ 막대를 사용하여 필요한 토큰을 찾거나 폴더 트리를 탐색하여 원하는 토큰을 찾아 선택할 수 있습니다.

개인화 토큰이 정의되면 **[!UICONTROL 저장]**&#x200B;을 클릭하여 변경 내용을 저장하고 기본 WhatsApp 메시지 작업 영역으로 돌아갑니다.
