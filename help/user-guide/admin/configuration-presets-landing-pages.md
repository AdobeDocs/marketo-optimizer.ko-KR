---
title: 랜딩 페이지 구성
description: 플레이스홀더
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '971'
ht-degree: 21%

---


# 랜딩 페이지 구성

관리자는 랜딩 페이지 구성이 이러한 페이지를 작성하고 게시하는 마케터를 위해 제대로 되어 있는지 확인해야 합니다. 브랜드 및 트랙 참여를 효과적으로 반영하는 랜딩 페이지를 만드는 데 필요한 구성 유형은 다음 두 가지입니다.

* **_하위 도메인_** — 랜딩 페이지를 호스팅하는 위치를 설정합니다. 랜딩 페이지 하위 도메인을 관리하여 도메인 설정을 위임, 구성 또는 위임 취소합니다.
* **_사전 설정_** — 마케터가 랜딩 페이지를 일관되게 만들고 관리할 수 있도록 재사용 가능한 구성(하위 도메인 및 기타 채널 설정 포함)을 정의합니다.

## 하위 도메인 {#lp-subdomains}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_subdomain_lp_header"
>title="랜딩 페이지 하위 도메인 위임"
>abstract="랜딩 페이지 사용을 위한 하위 도메인을 설정합니다. Adobe에 이미 위임된 하위 도메인을 사용하거나 다른 하위 도메인을 구성할 수 있습니다."

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_subdomain_lp"
>title="랜딩 페이지 하위 도메인 위임"
>abstract="랜딩 페이지 사전 설정을 만들기 전에 랜딩 페이지 하위 도메인을 구성해야 합니다. Adobe에 이미 위임된 하위 도메인을 사용하거나 새 하위 도메인을 구성할 수 있습니다."

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_config_lp_subdomain"
>title="랜딩 페이지 사전 설정 만들기"
>abstract="랜딩 페이지 사전 설정을 만들려면 하위 도메인 이름 목록에서 선택할 랜딩 페이지 하위 도메인이 하나 이상 구성되어 있는지 확인합니다."

구성된 랜딩 페이지 하위 도메인을 검토하려면 **[!UICONTROL 관리]** > **[!UICONTROL 채널]**(으)로 이동하십시오. 탐색 창의 _[!UICONTROL 랜딩 페이지]_&#x200B;에서 **[!UICONTROL 랜딩 페이지 하위 도메인]**&#x200B;을 선택합니다.

<!-- ![Channel configurations - landing page subdomains](./assets/config-channels-landing-pages-subdomains.png){width="800" zoomable="yes"} -->

**Status** 열은 하위 도메인 만들기 및 위임 프로세스에 대한 정보를 제공합니다.

* _[!UICONTROL 초안]_: 하위 도메인 위임이 초안으로 저장됩니다. 생성 프로세스를 재개하려면 하위 도메인 이름을 클릭합니다.
* _[!UICONTROL 처리 중]_: 하위 도메인을 사용하려면 몇 가지 구성 검사가 필요합니다.
* _[!UICONTROL 성공]_: 하위 도메인이 검사를 통과했으며 메시지를 전달하는 데 사용할 수 있습니다.
* _[!UICONTROL 실패]_: 하위 도메인 위임을 제출한 후 하나 이상의 검사가 실패했습니다.

>[!NOTE]
>
>[랜딩 페이지 사전 설정을 만들기](#lp-presets)하려면 먼저 랜딩 페이지에 사용할 하위 도메인을 설정해야 합니다. 이미 Adobe에 위임된 하위 도메인을 사용하거나 다른 하위 도메인을 구성할 수 있습니다.

랜딩 페이지 하위 도메인 구성은 **모든 환경에 공통됩니다**. 그 결과는 다음과 같습니다.

* 랜딩 페이지 하위 도메인에 액세스하고 편집하려면 프로덕션 샌드박스에 대한 **[!UICONTROL 랜딩 페이지 하위 도메인 관리]** 권한이 있어야 합니다.

* 랜딩 페이지 하위 도메인을 수정하면 프로덕션 샌드박스에도 영향을 줍니다.

<!-- 
### Use an existing subdomain {#lp-existing-subdomain}

To use a subdomain that is already delegated to Adobe:

1. Click **[!UICONTROL Set up landing page subdomain]**.

    ![](assets/lp_set-up-subdomain.png)

1. For _[!UICONTROL Configuration type]_, choose **[!UICONTROL Use delegated domain]**.

    ![](assets/lp_use-delegated-subdomain.png)

1. Enter the prefix that you want to display in the landing page URL.

    Only alpha-numeric characters and hyphens are allowed.

    >[!CAUTION]
    >
    >Do not use `cdn` or `data` prefixes as these are reserved for internal use. You should also avoid other restricted or reserved prefixes, such as `dmarc` or `spf`.

1. Select a delegated subdomain from the list.

    You cannot select a subdomain that is already used as landing page subdomain.
    
    ![](assets/lp_prefix-and-subdomain.png)

    You cannot use multiple delegated subdomains of the same parent domain. For example, if 'marketing1.yourcompany.com' is already delegated to Adobe for your landing pages, you cannot use 'marketing2.yourcompany.com'. However, when multi-level subdomains are supported for landing pages, you may proceed using a subdomain of 'marketing1.yourcompany.com' (such as 'email.marketing1.yourcompany.com'), or a different parent domain.

    >[!CAUTION]
    >
    >If you select a domain that was delegated to Adobe using the [CNAME method](../configuration/delegate-subdomain.md#cname-subdomain-setup), you must create the DNS record on your hosting platform. To generate the DNS record, the process is the same as when you configure a new landing page subdomain.

1. Click **[!UICONTROL Submit]**.

   The subdomain is displayed in the list with the _[!UICONTROL Processing]_ status. For more on subdomains' statuses, see TBD.

    ![](assets/lp_subdomain-processing.png)

   >[!IMPORTANT]
   >
   >The subdomain is not ready for use until Adobe performs the required checks, which can take **_up to 4 hours_**.

   When the checks are successful, the subdomain is listed with the _[!UICONTROL Success]_ status and it is ready to use for creating landing page presets.
-->

### 새 하위 도메인 구성 {#lp-new-subdomain}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_lp_subdomain_dns"
>title="일치하는 DNS 레코드 생성"
>abstract="새 랜딩 페이지 하위 도메인을 구성하려면 Journey Optimizer B2B 인터페이스에 표시된 Adobe 이름 서버 정보를 복사한 다음 도메인 호스팅 솔루션에 붙여넣어 일치하는 DNS 레코드를 생성해야 합니다. 확인이 완료되면 이제 랜딩 페이지 사전 설정 만들기에 하위 도메인을 사용할 수 있습니다."

1. **[!UICONTROL 랜딩 페이지 하위 도메인 설정]**&#x200B;을 클릭합니다.

1. _[!UICONTROL 구성 유형]_&#x200B;의 경우 **[!UICONTROL 고유한 도메인 추가]**&#x200B;를 선택하세요.

1. 위임할 하위 도메인을 지정합니다.

   >[!IMPORTANT]
   >
   >* 기존 랜딩 페이지 하위 도메인은 사용할 수 없습니다.
   >
   >* 하위 도메인에서는 대문자가 허용되지 않습니다.

   <!-- ![Landing page subdomain set up](./assets/config-channels-landing-pages-subdomain-setup.png){width="500" zoomable="yes"} -->

   잘못된 하위 도메인을 Adobe에 위임할 수 없습니다. marketing.yourcompany.com과 같이 조직에서 소유한 올바른 하위 도메인을 입력해야 합니다.

   랜딩 페이지의 경우 다중 수준 하위 도메인이 지원됩니다. 예를 들어 `email.marketing.yourcompany.com`을(를) 사용할 수 있습니다.

1. 표시된 레코드를 복사하거나 CSV 파일을 다운로드한 다음 도메인 호스팅 솔루션으로 이동하여 일치하는 DNS 레코드를 생성합니다.

   DNS 서버에 배치할 레코드가 표시됩니다.

1. DNS 레코드가 도메인 호스팅 솔루션에 생성되었는지 확인합니다.

   모든 항목이 올바르게 구성된 경우 확인 확인란을 선택하고 **[!UICONTROL 제출]**&#x200B;을 클릭합니다.

   <!-- ![Landing page subdomain set up with DNS records](./assets/config-channels-landing-pages-subdomain-setup-dns.png){width="500" zoomable="yes"} -->

   새 랜딩 페이지 하위 도메인을 구성할 때 항상 CNAME 레코드를 가리킵니다.

   하위 도메인 위임을 제출하면 하위 도메인이 목록에 _[!UICONTROL 처리]_ 상태로 표시됩니다.

   >[!IMPORTANT]
   >
   >Adobe에서 필요한 검사를 수행할 때까지 하위 도메인을 사용할 준비가 되지 않았습니다. **_최대 4시간_**&#x200B;이 소요될 수 있습니다.

   검사가 완료되면 하위 도메인이 _[!UICONTROL 성공]_ 상태로 나열되며 랜딩 페이지 사전 설정을 만드는 데 사용할 수 있습니다.

   호스팅 솔루션에서 유효성 검사 레코드를 만들지 않은 경우 하위 도메인이 _[!UICONTROL 실패]_(으)로 표시됩니다.

### 하위 도메인 위임 취소 {#undelegate-subdomain}

1. [!DNL Journey Optimizer]에서 하위 도메인과 연결된 모든 랜딩 페이지의 게시를 취소합니다.

1. 랜딩 페이지 하위 도메인이 CNAME 레코드를 가리키고 있는 경우 호스팅 솔루션에서 CNAME 레코드를 삭제합니다(있는 경우 원래 이메일 하위 도메인을 삭제하지 마십시오).

   <!--
    >[!NOTE]
    >
    >A landing page subdomain can point to a CNAME record because it was either an [existing subdomain](#lp-use-existing-subdomain) delegated to Adobe using the [CNAME method](../configuration/delegate-subdomain.md#cname-subdomain-setup), or a [new landing page subdomain](#lp-configure-new-subdomain) that you configured. 
    -->

1. 위임을 해제할 하위 도메인을 사용하여 Adobe 담당자에게 문의하십시오.

Adobe이 요청을 처리한 후 하위 도메인 인벤토리 페이지에 더 이상 위임되지 않은 도메인이 표시되지 않습니다.

<!-- 
old marketo way for Prime?

A landing page subdomain should help to identify the content type, product name, or campaign, and reinforce the page authenticity. Before you configure the subdomains, define one or more CNAMEs to use for your landing pages. For example:

* **product**.[CompanyDomain].com
* **go**.[CompanyDomain].com
* **signup**.[CompanyDomain].com

In these examples, the first part (in bold) is the `LandingPageCNAME`.

Add a new subdomain for each unique brand URL that you want to host on Adobe Journey Optimizer B2B Edition. You can add a maximum number of 50 subdomains.

>[!IMPORTANT]
>
>Delegating an invalid subdomain to Adobe is not allowed. Make sure you enter a valid subdomain that your organization owns, such as _marketing.yourcompany.com_.

To review your subdomains and add new ones, go to **[!UICONTROL Administration]** > **[!UICONTROL Channels]**. Under _[!UICONTROL Landing Pages]_ in the navigation panel, select **[!UICONTROL Subdomains]**.

![Landing page subdomains](./assets/config-landing-pages-settings.png){width="800" zoomable="yes"}

_To add a landing page subdomain:_

1. Click **[!UICONTROL Add subdomain]** at the top right.

1. In the _[!UICONTROL Subdomain details]_, enter the subdomain information:

   * **[!UICONTROL Subdomain]** - The subdomain URL to use, such as `marketing.yourcompany.com`
   * **[!UICONTROL Default page]** - The URL for the default subdomain page, such as `marketing.yourcompany.com/products`
   * **[!UICONTROL Fallback page]** - The URL for the fallback page to be used if a landing page on the subdomain is not active, such as `marketing.yourcompany.com/expired`

   ![Add landing page subdomain](./assets/config-landing-pages-add-subdomain.png){width="700" zoomable="yes"}

1. Click **[!UICONTROL Save]**.

-->

## 사전 설정 {#lp-presets}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_config_lp_subdomain_header"
>title="랜딩 페이지 사전 설정 만들기"
>abstract="랜딩 페이지를 빌드하고 Journey Optimizer B2B Edition을 통해 활용하려면 사용할 하위 도메인이 포함된 랜딩 페이지 사전 설정을 만들어야 합니다."

마케터는 랜딩 페이지를 만들 때 랜딩 페이지를 빌드하고 [!DNL Journey Optimizer B2B Edition]을(를) 통해 활용할 수 있도록 랜딩 페이지 사전 설정을 선택해야 합니다. 사전 설정에는 랜딩 페이지에 사용할 하위 도메인이 포함됩니다.

사전 설정을 구성하기 전에 _[!UICONTROL 성공]_ 상태로 구성된 랜딩 페이지 하위 도메인이 하나 이상 있는지 확인하십시오.

구성된 랜딩 페이지 사전 설정을 검토하려면 **[!UICONTROL 관리]** > **[!UICONTROL 채널]**(으)로 이동하십시오. 탐색 창의 _[!UICONTROL 랜딩 페이지]_&#x200B;에서 **[!UICONTROL 랜딩 페이지 사전 설정]**&#x200B;을 선택합니다.

<!-- ![Channel configurations - landing page presets](./assets/config-channels-landing-pages-presets.png){width="800" zoomable="yes"} -->

사전 설정 이름을 클릭하여 랜딩 페이지 사전 설정 세부 정보에 액세스합니다.

### 랜딩 페이지 사전 설정 만들기 {#lp-create-preset}

1. **[!UICONTROL 랜딩 페이지 사전 설정 만들기]**&#x200B;를 클릭합니다.

1. 사전 설정의 이름과 설명을 입력합니다.

   이름은 문자(A-Z)로 시작해야 하며 영숫자, 밑줄 `_`, 점`.` 및 하이픈 `-`자만 포함할 수 있습니다.

1. 랜딩 페이지 하위 도메인을 선택합니다.

   <!-- ![Landing page preset with name, description, and subdomain](./assets/config-channels-landing-pages-preset-create.png){width="500" zoomable="yes"} -->

   >[!NOTE]
   >
   >하위 도메인을 선택하려면 최소 하나 이상의 랜딩 페이지 하위 도메인을 이전에 구성했는지 확인합니다.

   선택한 하위 도메인에 해당하는 설정이 표시됩니다.

1. **[!UICONTROL 랜딩 페이지 하위 도메인과 동일]** 옵션을 선택하여 **[!UICONTROL 추적 URL]**&#x200B;에 대한 랜딩 페이지 하위 도메인을 선택할 수 있습니다.

   <!-- [Learn more about tracking](../email/message-tracking.md) -->

   <!-- ![Landing page preset with subdomain settings](./assets/config-channels-landing-pages-preset-subdomain-settings.png){width="500" zoomable="yes"} -->

   예를 들어 랜딩 페이지 URL이 `pages.mail.luma.com`이고 추적 URL이 `data.mail.luma.com`인 경우 `pages.mail.luma.com`을(를) 추적 하위 도메인으로 사용하도록 선택할 수 있습니다.

   <!-- 
    >[!CAUTION]
    >
    >The selected landing page subdomain is used to specify the **[!UICONTROL Tracking URL]**and **[!UICONTROL Image Delivery URL]** if that subdomain was created using an [existing subdomain](#use-an-existing-subdomain).
    >
    >If the subdomain was created using the [Add your own domain](#configure-a-new-subdomain) option, the primary subdomain (such as the first delegated subdomain) is used instead. We don't have the existing option right now.
    -->

1. **[!UICONTROL 제출]**&#x200B;을 클릭하여 랜딩 페이지 사전 설정 만들기를 확인합니다.

   <!--You can also save the preset as draft and resume its configuration later on.-->

   랜딩 페이지 사전 설정이 만들어지면 목록에 _[!UICONTROL 활성]_ 상태로 표시되고 랜딩 페이지를 만드는 데 사용할 준비가 되었습니다.