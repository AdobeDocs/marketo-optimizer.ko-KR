---
title: 여정에 이메일 추가
description: 개인 여정에 이메일 작업 노드를 추가하고 Marketo Optimizer에서 타깃팅된 커뮤니케이션을 위한 새 이메일을 만듭니다.
feature: Email Authoring, Person Journeys
role: User
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '1048'
ht-degree: 7%

---

# 여정에 이메일 추가

[!DNL Adobe Marketo Optimizer]은(는) B2B 마케터에게 현대적인 엔터프라이즈급 이메일 작성 및 게재 환경을 제공합니다.

>[!NOTE]
>
>전자 메일을 처음 보내는 경우 [전자 메일 게재 기능](../start/email-deliverability.md) 및 필요한 [전자 메일 채널](../admin/email-channel-configuration.md)이 구성되어 있는지 확인하십시오.

<!-- 
* **Email channel configurations** - Manage the sender identity, reply behavior, marketing vs. transactional message types, and tracking.
* **Email deliverability controls** - Set up your email deliverability channel, including subdomain delegation (Fully Delegated and CNAME methods), DMARC, SPF/DKIM auto-configuration, and shared IP pool support.
* **Send Email action** - From a journey, add a _Send email_ action node, including personalization using profile attributes (Handlebars syntax).
* **Visual drag-and-drop email design tools** -  Design your email content with structures, content components, themes, dark-mode support, and reusable visual fragments.
* **Marketo Design Studio assets** — Choose images and assets from a one-time copy of your Marketo Engage asset library directly inside the email canvas.
* **Reusable templates and fragments** — Save common headers, footers, CTAs, and full email layouts and reuse them across journeys.
* **Role-Based Access Control (RBAC)** — Apply granular permissions for creating, editing, approving, and sending email. 
-->

## 현재 제한 사항 {#limitations}

* 이 릴리스에서는 **테스트 프로필, 콘텐츠 시뮬레이션 및 증명 보내기**&#x200B;를 사용할 수 없습니다. Litmus 렌더링 및 SpamAssassin 기반 스팸 보고서는 GA 로드맵에 있습니다.
* 이 릴리스에서는 **계정 수준 개인화 및 사용자 지정 개체 데이터**&#x200B;를 사용할 수 없습니다. 프로필 속성을 사용합니다.
* 기존 Marketo Engage 템플릿의 **Velocity-to-Handlebars 자동 마이그레이션**&#x200B;이(가) GA에 제공됩니다.
* **이메일에 대한 댓글 및 공동 작업**(인라인 댓글, @mentions, 요청 검토 워크플로)은 예정된 릴리스에 제공됩니다.
* **AEM Assets, AEM 콘텐츠 조각 및 Adobe Express** 통합이 _빠른 후속_ 로드맵에 있습니다.

## 주요 개념 {#key-concepts}

개인 여정을 위한 이메일을 만들고 이메일 콘텐츠를 작성하기 전에 다음 개념을 검토하십시오.

| 개념 | [!DNL Adobe Marketo Optimizer]에서 |
| ------- | ---------------------- |
| **_전자 메일 디자인 공간_** | 이메일 콘텐츠를 구성하는 데 사용되는 시각적 캔버스 및 디자인 도구입니다. 여기에는 드래그 앤 드롭 레이아웃 구성 요소, 템플릿, 조각, 테마 및 개인화 편집기가 포함되어 있습니다. |
| **_템플릿_** | 새 이메일을 만드는 데 사용할 수 있는 재사용 가능한 이메일 레이아웃. Adobe에서 제공하는 내장 샘플 템플릿 또는 팀에서 만드는 사용자 지정 빌드 템플릿일 수 있습니다. |
| **_시각적 조각_** | 여러 이메일에 삽입할 수 있는 재사용 가능한 콘텐츠 블록(예: 머리글, 바닥글, CTA, 법적 고지 사항). 조각을 업데이트하면 해당 조각을 사용하는 모든 이메일에 변경 사항이 전파됩니다. |
| **_테마_** | 이메일 전체에 적용되는 재사용 가능한 스타일 사전 설정(색상, 타이포그래피, 간격, 버튼 스타일). |
| **_Personalization 토큰_** | Handlebars 식(예: `{{profile.firstName}}`)은 각 받는 사람의 프로필 데이터를 사용하여 전송 시 확인됩니다. |
| **_전자 메일 동작 보내기_** | 채널 구성 및 이메일 콘텐츠를 사용하여 이메일을 전달하는 여정 작업 노드입니다. |

## 여정에서 이메일 추가

여정에서 전자 메일을 보내려면 [_작업 수행_ 노드를 추가하고](action-nodes.md#add-an-action-node)전자 메일을 보내도록 구성하십시오.

1. 여정 캔버스에서 **+** 아이콘을 클릭하고 **[!UICONTROL 작업 수행]**&#x200B;을 선택합니다.

1. 오른쪽의 노드 속성에서 작업을 **[!UICONTROL 전자 메일 보내기]**(으)로 설정합니다.

   ![작업 수행 - 전자 메일 보내기](./assets/person-action-node-send-email.png){width="500"}

1. 이메일 소스 선택:

   * **전자 메일 만들기/편집** - 전자 메일 디자인 공간에 제목란, 보낸 사람 정보 및 전자 메일 본문을 포함하는 전자 메일 콘텐츠를 정의하려면 이 옵션을 선택하십시오.

   * **[!UICONTROL AI 개인화 이메일 사용]** - (_Beta에서는 사용할 수 없음_) 이메일 디자인 공간에서 AI 생성 이메일을 세분화하려면 이 옵션을 선택하십시오. 이러한 이메일은 AI 지원 받은 편지함 클라이언트가 오퍼 및 작업 호출에서 요약 및 답변을 작성하도록 최적화되었습니다.

1. **[!UICONTROL 전자 메일 만들기]**&#x200B;를 클릭합니다.

1. _[!UICONTROL 전자 메일 만들기]_ 대화 상자에서 고유한 **[!UICONTROL 이름]**(필수)과 **[!UICONTROL 설명]**(선택 사항)을 입력하십시오.

   ![전자 메일 대화 상자 만들기](./assets/email-channel-create-email-dialog.png){width="400"}

1. **[!UICONTROL 만들기]**&#x200B;를 클릭합니다.

선택적 [전송 시간 최적화](email-send-time-optimization.md)의 경우 전자 메일을 만든 후 여정 작업 노드를 구성하십시오.

## 이메일 속성 및 작업 정의 {#define-email-properties}

전자 메일 페이지는 _[!UICONTROL 전자 메일 보내기]_ 노드에 대한 전자 메일을 만들 때 열립니다. 전자 메일을 만든 후 오른쪽의 노드 속성에서 **[!UICONTROL 전자 메일 편집]**&#x200B;을 클릭하여 이 페이지에 액세스할 수도 있습니다.

1. (선택 사항) **[!UICONTROL 속성]** 탭에서 전자 메일에 대해 캡처할 설명 정보를 입력합니다.

1. **[!UICONTROL 작업]** 탭을 선택하고 전자 메일에 대한 기능 설정을 완료합니다.

   * **[!UICONTROL 전자 메일]** - 사용할 **[!UICONTROL 전자 메일 채널 구성]**&#x200B;을 선택하거나 만듭니다.

     발신자 ID, 회신 주소, 하위 도메인, IP 풀, 이메일 유형(마케팅 또는 트랜잭션) 및 추적을 정의하는 재사용 가능한 이메일 게재 설정 세트입니다. _보기_ 아이콘을 클릭하여 선택한 구성에 대한 설정을 검토합니다.

     관리자는 [전자 메일 채널 구성](../admin/email-channel-configuration.md)에서 구성을 만듭니다.

   * **[!UICONTROL 비즈니스 규칙]** - (선택 사항) 규칙 집합을 선택하여 전자 메일 작업에 최대 가용량 또는 자동 시간 규칙을 적용합니다.

     비즈니스 규칙과 채널 통신을 위한 규칙 집합을 정의하고 활성화하는 방법에 대한 자세한 내용은 [_비즈니스 규칙_](../admin/business-rules.md)&#x200B;을 참조하세요.

   * **[!UICONTROL 작업 추적]** - 전자 메일에 대해 추적할 작업의 확인란을 선택합니다.

   ![전자 메일 채널 - 작업 탭](./assets/email-channel-actions-tab.png){width="600" zoomable="yes"}

1. **[!UICONTROL 콘텐츠 편집]**&#x200B;을 클릭하거나 **[!UICONTROL 콘텐츠]** 탭을 선택하십시오.

1. 전자 메일의 제목 필드에 표시할 **[!UICONTROL 제목 줄]** 텍스트를 입력하십시오.

   필드에서 개인화 토큰을 사용하려면 _개인화_ 아이콘( ![개인화 아이콘](../assets/do-not-localize/icon-personalize.svg))을 클릭하십시오.

1. (선택 사항) 게시 프로세스 중에 이메일 HTML의 크기를 줄이려면 **[!UICONTROL HTML 크기 최적화]** 확인란을 선택합니다.

   이를 통해 100KB를 초과하는 메시지를 잘라버리는 Gmail 등의 클라이언트에서 이메일 클리핑을 방지할 수 있습니다. 자세한 내용은 [_이메일 HTML 크기 최적화_](#optimize-html-size)&#x200B;를 참조하십시오.

1. **[!UICONTROL 전자 메일 본문 편집]**&#x200B;을 클릭하여 시각적 디자인 도구에 액세스하고 [콘텐츠 빌드](../content/email-authoring.md)를 시작합니다.

   또는 **[!UICONTROL 코드 편집기]**&#x200B;를 클릭하여 일반 HTML에서 자신의 콘텐츠를 코딩할 수 있습니다. 이메일 디자인에 재사용할 기존 HTML이 있는 경우 이를 복사하여 편집기에 붙여넣을 수 있습니다.

### 경고 확인 {#alerts}

[!DNL Adobe Marketo Optimizer]은(는) 전자 메일 페이지의 오른쪽 상단 모서리에서 문제를 표시합니다. 여정을 활성화하기 전에 모든 오류를 해결하십시오. 경고는 권장 사항만 해당됩니다.

**오류**(여정 활성화 금지):

* 보낸 사람 이름이 비어 있음
* 제목 줄이 누락되었습니다.
* 이메일 콘텐츠가 비어 있음

**경고**(권장 사항):

* 옵트아웃 링크가 이메일 본문에 없습니다.
* HTML의 텍스트 버전이 비어 있음
* 빈 링크가 검색됨
* 이메일이 100K를 초과함

## 이메일 HTML 크기 최적화 {#optimize-html-size}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_email_minification"
>title="HTML 크기 축소"
>abstract="이 옵션을 활성화하면 게시 시 불필요한 공백, 들여쓰기 및 불필요한 주석을 제거하여 이메일 HTML을 압축할 수 있습니다. 이를 통해 100KB를 초과하는 메시지를 잘라버리는 Gmail 등의 클라이언트에서 이메일 클리핑을 방지할 수 있습니다."

[!DNL Marketo Optimizer]을(를) 사용하면 불필요한 공백, 들여쓰기 및 불필요한 설명을 제거하여 게시 프로세스 중에 전자 메일 HTML 버전을 압축할 수 있습니다. HTML 크기를 작게 유지하면 다음과 같은 이점이 있습니다.

* **전자 메일 클리핑** 방지 - Gmail과 같은 일부 클라이언트는 ~100KB보다 큰 메시지를 잘라내어 수신자가 전체 콘텐츠를 볼 수 없습니다.
* 받는 사람의 받은 편지함에서 **전자 메일 로드 시간**&#x200B;을 개선합니다.
* **전달성**&#x200B;을 개선하고 대역폭 사용을 줄입니다.

이 최적화는 자동으로 적용되지 않습니다. _[!UICONTROL 콘텐츠]_ 탭에서 활성화해야 합니다.

<!-- ![](assets/email-optimize-html-size.png) -->

>[!IMPORTANT]
>
> HTML 크기 감소는 게시 시간에만 적용됩니다.

최적화는 이메일 클라이언트 안전 장치입니다.

* MSO/Outlook 조건부 주석을 보존합니다.
* 실제 콘텐츠, 이미지 또는 비디오는 변경되지 않습니다.

>[!NOTE]
>
>이메일 크기의 감소는 이메일의 원래 HTML 구조에 따라 다릅니다. 콘텐츠가 이미 컴팩트하거나 이메일 페이로드가 매우 큰 경우, 감소는 최소화될 수 있으며 모든 경우에 클리핑을 완전히 방지할 수 없습니다.

<!-- 
Proof and simulate workflows are not available in this release. See [Current limitations](#limitations).

### Test HTML size optimization {#optimize-html-proof}

If you have enabled the [HTML size optimization](#optimize-html-size) option, you can evaluate its impact before publishing when sending proofs. Follow the following steps.

1. In the email design space, click the _Issues_ icon on the top right. If the rendered email size exceeds 100 KB, a message is displayed to warn you that this may cause truncation in some email clients.

1. Click **[!UICONTROL Simulate content]**.

1. To test the optimized version, click the **[!UICONTROL Send proof]** button and select the **[!UICONTROL Optimize HTML size]** option. This will send a proof with the reduced HTML size to your test recipients.

    >[!NOTE]
    >
    >This setting is independent from the email editor — the proof reflects what you select in the proof, regardless of whether the option is enabled or disabled in the email itself.

1. Select the test recipients and click **[!UICONTROL Send proof]**.

1. Back in the **[!UICONTROL Simulate]** screen, click the **[!UICONTROL View Proof]** button.

1. Click the _Information_ icon next to the status of the proof.

   The optimization details are displayed in a pop-up window, including the original HTML size, the optimized HTML size, and the size reduction percentage.
    
    Use this information to validate the optimized output and confirm the email stays within the recommended 100 KB threshold before publishing.

-->
