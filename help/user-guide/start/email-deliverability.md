---
title: 이메일 전달성 구성
description: Marketo Optimizer에 대한 하위 도메인 위임, DMARC, SPF, DKIM 및 IP 풀을 구성합니다.
source-git-commit: 81d9880cb37bb60301252b48bd89637b6656a993
workflow-type: tm+mt
source-wordcount: '2502'
ht-degree: 0%

---

# 이메일 전달성

다음 정보는 마케터 및 이메일 콘텐츠 작성자를 지원하기 위해 전송 인프라를 구성하는 관리자를 위한 것입니다. 게재 기능 및 하위 도메인, 인증 및 IP 풀을 구성하는 방법에 대해 설명합니다.

[!DNL Adobe Marketo Optimizer]의 전자 메일 게재 기능은 전자 메일 메시지가 스팸 폴더가 아니라 받는 사람의 받은 편지함에 도달하고 ISP(인터넷 서비스 공급자)에 의해 차단되지 않도록 하는 인프라 및 인증 구성 집합입니다.

일반적으로 다음 순서로 관리자가 구성한 다음 구성 요소를 사용합니다.

1. [하나 이상의 하위 도메인을 Adobe에 위임](#subdomain-delegation).
1. 각 하위 도메인에서 [DMARC, SPF 및 DKIM 레코드를 구성](#dmarc-spf-dkim)합니다.
1. [하위 도메인용 전자 메일을 보내는 데 사용되는 IP 풀을 확인](#ip-pools)합니다.
1. 하위 도메인, IP 풀 및 보낸 사람 ID를 바인딩하는 [하나 이상의 전자 메일 채널 구성을 만듭니다](../admin/email-channel-configuration.md#create-email-channel-configuration).

![Marketo Optimizer에 대한 전자 메일 게재 기능 설정](./assets/email-deliverability-diagram.svg){width="600"}

>[!TIP]
>
>게재 기능 및 채널 설정을 일회성 관리자 활동으로 처리합니다. 구성된 경우 마케터와 이메일 작성자는 다시 방문할 필요가 없습니다.
>
> 전자 메일 채널에 대한 자세한 내용은 다음 항목을 참조하십시오.
>
>* 전자 메일 채널 구성 - [전자 메일 채널 구성](../admin/email-channel-configuration.md)
>* 전자 메일 만들기 - [여정에 전자 메일 추가](../marketing/email-channel.md)
>* 전자 메일 콘텐츠 디자인 - [전자 메일 콘텐츠 작성](../content/email-authoring.md)

## 현재 제한 사항 {#limitations}

* 하위 도메인 위임에 대한 **사용자 지정 위임 방법**&#x200B;을 아직 사용할 수 없습니다. 완전히 위임되거나 CNAME을 사용합니다. 사용자 지정 위임은 GA 릴리스를 대상으로 합니다.
* Beta에서 **전용 IP 풀**&#x200B;을(를) 사용할 수 없습니다. 공유 IP 풀만 선택할 수 있습니다. 전용 IP는 IP 웜업 계획 및 PTR 기록 관리를 포함하여 GA 시점에 제공됩니다.

## 주요 개념 {#key-concepts}

이메일을 구성하기 전에 이메일 채널 전달성 기능에 적용되는 다음 개념을 검토하십시오.

| 개념 | [!DNL Marketo Optimizer]의 의미 |
| ------- | ---------------------- |
| **_하위 도메인_** | [!DNL Marketo Optimizer]을(를) 통해 전자 메일을 보내는 데 사용되는 전송 도메인(예: `mail.contoso.com`)의 위임된 부분. 하위 도메인은 B2B 마케팅 평판을 회사 또는 트랜잭션 메일로부터 격리합니다. |
| **_IP 풀_** | 하나 이상의 하위 도메인과 연관된 IP 주소 그룹입니다. [!DNL Marketo Optimizer]은(는) 이 릴리스에서 Adobe에서 관리하는 공유 IP 풀을 지원합니다. 전용 IP 풀은 GA 로드맵에 있습니다. |
| **_채널 구성_** | 여정의 이메일 작업에 첨부하는 재사용 가능한 이메일 전송 설정(발신자 ID, 회신 주소, 하위 도메인, IP 풀, 이메일 유형 및 추적) 세트입니다. 서로 다른 브랜드, 비즈니스 단위 또는 전송 유형에 대해 이름이 지정된 여러 채널 구성을 가질 수 있습니다. |

<!--

## Roles and permissions {#roles-permissions}

[!DNL Marketo Optimizer] uses role-based access control (RBAC) for email features. Permissions are managed in the Adobe Admin Console (IMS) and synced at login. Product administrators assign granular permissions to product profiles, and then attach those product profiles to users.

Access to email functionality in [!DNL Marketo Optimizer] is gated by two layers:

1. **Feature flag (LD).** A LaunchDarkly flag controls whether the entire feature is turned on for your organization. Email authoring and deliverability are gated by `dx_ajo_btob_channel_foundation`. Without this flag, the feature is hidden regardless of permissions.
2. **Functional permission.** A user-level permission that controls whether a specific user can read or write within a feature.

Most email features follow a `view-*` (read) and `manage-*` (write) pattern. A user needs the read permission to see a feature in the navigation, and the write permission to create, edit, or delete within it.

### Email authoring permissions {#email-authoring-permissions}

| Capability | Permission | What it allows |
| ---------- | ---------- | -------------- |
| **View emails** | `view-b2b-emails` | View the email list, open emails, view content (read-only). |
| **Create / edit / delete emails** | `manage-b2b-emails` | All read access plus create, edit, duplicate, and delete emails. Required to author email content within a journey. |
| **View templates** | `view-b2b-templates` | Browse and preview templates in the Templates gallery (read-only). |
| **Create / edit / delete templates** | `manage-b2b-templates` | All read access plus create, edit, and delete saved templates. |
| **View fragments** | `view-b2b-fragments` | Browse and preview visual fragments (read-only). |
| **Create / edit fragments** | `manage-b2b-fragments` | All read access plus create and edit visual fragments. |
| **Publish fragments** | `publish-b2b-fragments` | Publish a fragment so it becomes available to email authors across the organization. |
| **Manage shared assets and library items** | `manage-b2b-library-items` | Manage the underlying shared library used by templates, fragments, and emails. Often granted alongside the template/fragment manage permissions. |
| **Manage usage labels** | `manage-b2b-delete-usage-labels` | Manage data usage labels (DULE) attached to library items for governance. |
| **Manage packages** | `manage-b2b-packages` | Bundle and move templates, fragments, and emails between sandboxes. |
| **View assets (Marketo Design Studio assets in [!DNL Marketo Optimizer])** | `view-b2b-assets` | Browse the asset picker and preview images. Read-only. |
| **Manage assets** | `manage-b2b-assets` | All read access plus future asset-management actions (Beta scope). |
| **Export message data** | `manage-b2b-message-export` | Export email-level message data and reports. |

Within a person journey, the **Send email** action requires `manage-b2b-person-journeys` (to add the action and activate the journey). A user with only email permissions can author content but cannot add an email to a journey.

### Email deliverability permissions {#email-deliverability-permissions}

Deliverability features (subdomains, DMARC, IP pools, suppression lists, allowed lists, IP warmup plans, and seed lists) are administrator-level configuration. They are governed by two permissions covering the entire **[!UICONTROL Channels]** > **[!UICONTROL Email settings]** area:

| Capability | Permission | What it allows |
| ---------- | ---------- | -------------- |
| **View email settings** | `view-b2b-email-settings` | View subdomains, PTR records, IP pools, suppression list, allowed list, IP warmup plans, and seed lists (read-only). |
| **Manage email settings** | `manage-b2b-email-settings` | All read access plus delegate subdomains, configure DMARC, manage suppression and allowed lists, manage IP warmup plans and seed lists. |

Some sub-features within Email settings are gated by additional LaunchDarkly flags — Suppression list (`enable-suppression`), Allowed list (`enable-allow-list`), Seed lists (`enable-seedlist-ui`). If a sub-feature is not visible in your organization, check with your Adobe representative on flag enablement.

### Channel configuration permissions {#channel-configuration-permissions}

Channel configurations sit under **[!UICONTROL Channels]** → **[!UICONTROL General settings]**. They tie deliverability primitives (subdomain, IP pool, sender identity) to a reusable object that journey authors reference. They are governed by a single permission:

| Capability | Permission | What it allows |
| ---------- | ---------- | -------------- |
| **Manage channel configurations** | `manage-b2b-channels-configurations` | View, create, edit, and delete email channel configurations. |

-->

## 하위 도메인 위임 {#subdomain-delegation}

하위 도메인 위임은 Adobe에 도메인의 특정 하위 도메인(예: `mail.contoso.com`) 대신 전자 메일을 보낼 수 있는 권한이 있음을 인터넷에 알려줍니다. 루트 도메인이 아닌 전용 하위 도메인을 위임하면 기업 메일이 보호되며 다음과 같은 이점이 있습니다.

* **신뢰도 격리.** 마케팅 전송은 회사 메일과 별도로 유지됩니다. 마케팅 평판이 떨어지는 경우 트랜잭션 및 기업 메일은 영향을 받지 않습니다.
* **더 빠른 IP 준비** 전용 하위 도메인을 사용하면 ISP를 통해 긍정적인 발신자 평판을 보다 신속하게 구축할 수 있습니다.
* **최신 인증.** SPF, DKIM 및 DMARC은 다른 메일 흐름에 영향을 주지 않고 하위 도메인별로 깔끔하게 설정할 수 있습니다.
* **준수.** Gmail, Yahoo 및 기타 주요 ISP의 대량 발신자 요구 사항을 충족하도록 도와줍니다.

>[!NOTE]
>
>[!DNL Marketo Optimizer]의 각 하위 도메인은 하나의 Adobe 제품에서만 사용할 수 있습니다. [!DNL Marketo Optimizer]과(와) 다른 제품(예: Adobe Marketo Engage 또는 Adobe Campaign) 간에 동일한 전송 하위 도메인을 공유할 수 없습니다. 고유한 하위 도메인을 사용해야 합니다.

### 지원되는 메서드 {#supported-methods}

[!DNL Marketo Optimizer]은(는) 이 Beta 릴리스에서 세 가지 하위 도메인 위임 방법 중 두 가지를 지원합니다. 세 번째 방법(사용자 지정 위임)은 로드맵에 있습니다.

| 메서드 | 사용 시기 | 관련 항목 |
| ------ | ----------- | ---------------- |
| **완전히 위임됨** | 추천 | 하위 도메인에 대한 전체 DNS 권한을 Adobe에 위임합니다. Adobe은 MX, SPF, DKIM, DMARC, A 및 CNAME 레코드를 생성하고 유지 관리합니다. 운영 부담 최소화 Adobe은 DNS 변경 사항을 처리합니다. |
| **CNAME** | 제한된 정책의 경우 | DNS 권한을 사용자 측에 유지하고 Adobe 관리 레코드를 가리키는 CNAME 레코드를 만듭니다. 조직의 DNS 정책이 전체 위임을 허용하지 않을 때 사용합니다. DNS 레코드를 유지 관리할 책임이 있습니다. |
| **사용자 지정 위임** | 로드맵(GA) | DNS 및 SSL 인증서의 완전한 소유권을 유지합니다. 자체 인증서를 사용하는 기능을 포함하여 최대 제어 기능을 제공합니다. 이는 GA 릴리스를 대상으로 합니다. |

### 하위 도메인 위임(완전히 위임된 메서드) {#delegate-fully-delegated}

>[!PREREQUISITES]
>
>* 하위 도메인 명명 규칙을 결정합니다(예: 마케팅의 경우 `mail.contoso.com`, 트랜잭션의 경우 `alerts.contoso.com`).
>* 하위 도메인(NS 레코드)을 Adobe에 위임할 수 있는지 IT/DNS 팀에 확인합니다.
>* DNS 공급자에서 새 하위 도메인을 만든 다음 Adobe으로 위임하기 전에 DNS 전파가 시작될 때까지 24-48시간 대기합니다.
>* [!DNL Marketo Optimizer]에 관리자 역할이 있는지 확인하십시오.

1. [!DNL Marketo Optimizer] 왼쪽 탐색에서 **[!UICONTROL 관리]**&#x200B;를 확장하고 **[!UICONTROL 채널]**&#x200B;을 선택합니다.
1. 패널에서 **[!UICONTROL 전자 메일 설정]**&#x200B;을 확장하고 **[!UICONTROL 하위 도메인]**&#x200B;을 선택합니다.
1. **[!UICONTROL 하위 도메인 설정]**&#x200B;을 클릭합니다.
1. 전체 하위 도메인 이름을 입력하십시오(예: `mail.contoso.com`).
1. 위임 방법으로 **[!UICONTROL 완전히 위임됨]**&#x200B;을(를) 선택하십시오.
1. 하위 도메인용 DMARC을 구성합니다([DMARC, SPF 및 DKIM](#dmarc-spf-dkim) 참조).

   최소한 `none`의 시작 정책으로 DMARC 레코드를 설정하여 배달에 영향을 주지 않고 보고서를 모니터링할 수 있습니다.

1. Adobe에서 관리할 DNS 레코드 목록을 검토하십시오.

   여기에는 일반적으로 MX, SPF, DKIM, DMARC, A 및 CNAME 레코드(추적 및 미러 페이지 URL용)가 포함됩니다.

1. **[!UICONTROL 레코드 다운로드]** 단추를 사용하여 DNS 레코드를 CSV 파일로 다운로드합니다. 이 파일을 DNS 팀과 공유합니다.

1. DNS 팀은 도메인 호스팅 솔루션에 하위 도메인을 Adobe에 위임하는 NS 레코드를 추가합니다.

1. DNS 팀이 레코드가 있는 것을 확인한 후 [!DNL Marketo Optimizer]&#x200B;(으)로 돌아가서 호스팅 사이트에 필요한 레코드를 만들었음을 확인하는 상자를 선택합니다.

1. 일련의 유효성 검사(사전 유효성 검사, MX, SPF, DKIM, DMARC, FBL 등록)를 시작하려면 **[!UICONTROL 제출]**&#x200B;을 클릭하십시오.

1. 하위 도메인 상태가 **[!UICONTROL 성공]**(으)로 변경될 때까지 기다리십시오.

   일반적으로 DNS 전파가 완료된 후 몇 분 정도 소요됩니다.

>[!NOTE]
>
>유효성 검사가 실패하면 상태가 **[!UICONTROL 실패]**(으)로 변경되고 [!DNL Marketo Optimizer]에 이유가 표시됩니다(예: NS 레코드를 찾을 수 없음, MX 레코드가 누락됨 또는 DMARC이 잘못 구성됨). 기본 DNS 문제를 해결한 다음 제출을 다시 시도하십시오.

### 하위 도메인 위임(CNAME 메서드) {#delegate-cname}

조직의 DNS 정책이 전체 위임을 금지하는 경우에만 이 방법을 사용하십시오. CNAME을 사용하면 DNS 레코드를 사용자 측에서 유지 관리할 수 있습니다.

1. [!DNL Marketo Optimizer] 왼쪽 탐색에서 **[!UICONTROL 관리]**&#x200B;를 확장하고 **[!UICONTROL 채널]**&#x200B;을 선택합니다.
1. 패널에서 **[!UICONTROL 전자 메일 설정]**&#x200B;을 확장하고 **[!UICONTROL 하위 도메인]**&#x200B;을 선택합니다.
1. **[!UICONTROL 하위 도메인 설정]**&#x200B;을 클릭합니다.
1. 전체 하위 도메인 이름을 입력합니다.
1. 위임 방법으로 **[!UICONTROL CNAME]**&#x200B;을(를) 선택하십시오.
1. 하위 도메인([DMARC, SPF 및 DKIM](#dmarc-spf-dkim))에 대해 DMARC을 구성합니다.
1. 생성할 CNAME 레코드 목록을 검토합니다. 이렇게 하면 하위 도메인의 구성 요소가 Adobe 관리 레코드를 가리키게 됩니다.
1. 레코드를 CSV로 다운로드하고 DNS 팀과 공유합니다.
1. DNS 팀이 각 CNAME 레코드를 DNS 호스팅 솔루션에 추가합니다.
1. 레코드가 제자리에 있고 전파되면 [!DNL Marketo Optimizer]&#x200B;(으)로 돌아가서 확인하십시오.
1. **[!UICONTROL 제출을 클릭합니다]**.
1. 상태가 **[!UICONTROL 성공]**&#x200B;에 도달할 때까지 기다리십시오.

>[!IMPORTANT]
>
>Adobe은 CNAME을 사용하여 하위 도메인의 DNS를 변경, 유지 관리 또는 문제를 해결할 수 없습니다. 기능 업데이트를 위한 새 CNAME 추가와 같은 향후 변경 사항은 DNS 팀이 수행해야 합니다.

일반 DNS 공급자에 대한 단계별 지침은 다음 섹션을 검토하십시오.

### DNS 공급자별 CNAME 레코드 추가 {#add-cname-records-dns-provider}

[!DNL Marketo Optimizer]은(는) 하위 도메인에 대한 정확한 CNAME 및 TXT 레코드를 생성하여 CSV 파일로 다운로드할 수 있도록 합니다. 다음 공급자별 단계를 사용하여 DNS 팀이 올바른 설정 화면을 찾고 각 레코드를 추가할 수 있도록 합니다.

>[!NOTE]
>
>다운로드한 CSV의 호스트, 유형 및 대상 값은 하위 도메인 및 조직에 따라 다릅니다. 다른 하위 도메인의 값을 재사용하지 않고 정확하게 복사합니다.

#### AWS 루트 {#aws-route-53}

1. AWS 관리 콘솔에 로그인하고 **[!UICONTROL Route 53]**&#x200B;을 엽니다.
1. **[!UICONTROL 호스팅 영역]**&#x200B;을 선택한 다음 도메인의 호스팅 영역을 선택하십시오.
1. **[!UICONTROL 레코드 만들기]**&#x200B;를 클릭하고 라우팅 정책을 **[!UICONTROL 단순 라우팅]**(으)로 설정합니다.
1. CSV의 각 행에 대해:

   * **레코드 이름** — 영역 이름 앞에 부분만 입력하십시오. 예를 들어 `contoso.com` 영역의 `data.mail.contoso.com`에 대해 `data.mail`을(를) 입력합니다.
   * **레코드 종류** — CSV와 일치시키려면 `CNAME` 또는 `TXT`을(를) 선택하십시오.
   * **값** — CSV에서 대상을 붙여넣습니다. TXT 레코드의 경우 값을 큰따옴표로 묶습니다.
   * **TTL** — 300초면 충분합니다.

1. 모든 행을 입력한 후 **[!UICONTROL 다른 레코드 추가]**&#x200B;를 클릭하여 일괄 입력한 다음 **[!UICONTROL 레코드 만들기]**&#x200B;를 클릭합니다.

>[!NOTE]
>
>TXT 값은 큰따옴표로 묶어야 합니다. 그렇지 않으면 레코드 유효성 검사가 실패합니다. CNAME 레코드는 영역 끝점에 배치할 수 없지만 위임된 하위 도메인에는 영향을 주지 않습니다.

#### Cloudflare {#cloudflare}

1. Cloudflare 대시보드에 로그인하고 도메인을 선택합니다.
1. **[!UICONTROL DNS 레코드]**(으)로 이동하고 **[!UICONTROL 레코드 추가]**&#x200B;를 클릭합니다.
1. CSV의 각 행에 대해:

   * **유형** — `CNAME` 또는 `TXT`을(를) 선택합니다.
   * **이름** — 호스트 부분(예: `data.mail`)을 입력하십시오. Cloudflare 가 도메인을 자동으로 추가합니다.
   * **Target**(CNAME용) 또는 **Content**(TXT용) — CSV의 값을 붙여넣습니다.
   * **프록시 상태** — **[!UICONTROL DNS만]**(회색 클라우드 아이콘)으로 설정합니다.
   * **TTL** — **[!UICONTROL Auto]**(으)로 둡니다.

1. 각 행에 대해 **[!UICONTROL 저장]**&#x200B;을 클릭합니다.

>[!IMPORTANT]
>
>[!DNL Marketo Optimizer]에 추가하는 모든 레코드에는 주황색 클라우드(프록시화)가 아닌 회색 클라우드(DNS만)가 표시되어야 합니다. 프록시화된 레코드는 Adobe 대신 Cloudflare의 서버를 통해 트래픽을 라우팅하므로 DKIM 서명, 클릭 추적 및 바운스 처리가 중단됩니다. 레코드에 주황색이 표시되면 클라우드 아이콘을 클릭하여 회색으로 전환합니다.

#### AZURE DNS {#azure-dns}

1. Azure 포털에 로그인하고 **[!UICONTROL DNS 영역]**&#x200B;을 엽니다.
1. 도메인의 DNS 영역을 선택합니다.
1. **[!UICONTROL + 레코드 집합]**&#x200B;을(를) 클릭합니다.
1. CSV의 각 행에 대해:

   * **이름** — 호스트 부분(예: `data.mail`)을 입력하십시오. Azure이 영역 이름을 추가합니다.
   * **유형** — `CNAME` 또는 `TXT`을(를) 선택합니다.
   * CNAME 레코드의 경우 **[!UICONTROL 별칭]** 필드에 CSV의 대상을 입력하십시오.
   * TXT 레코드의 값을 **[!UICONTROL 값]** 필드에 붙여 넣으십시오. Azure에서 따옴표 대신 따옴표를 처리합니다.
   * **TTL** — 숫자와 단위를 입력합니다(예: 300초).

1. **[!UICONTROL 확인]**&#x200B;을 클릭하여 각 행에 설정된 레코드를 저장합니다.

>[!NOTE]
>
>외부 호스트 이름이 아닌 Azure 리소스만 가리키는 별칭 레코드 세트 옵션이 아닌 표준 CNAME 레코드 세트를 사용합니다. 각 CNAME 레코드 집합에는 정확히 하나의 대상이 있으며 [!DNL Marketo Optimizer]에서 레코드를 발행하는 방식과 일치합니다(호스트당 하나의 CNAME).

#### Google Cloud DNS {#google-cloud-dns}

1. Google 클라우드 콘솔을 열고 **[!UICONTROL 네트워크 서비스]** > **[!UICONTROL 클라우드 DNS]**(으)로 이동합니다.
1. 도메인의 영역을 선택합니다.
1. 레코드 집합을 추가하려면 **[!UICONTROL 표준 추가]**&#x200B;를 클릭하세요.
1. CSV의 각 행에 대해:

   * **DNS 이름** — 호스트 부분(예: `data.mail`)을 입력하십시오. Cloud DNS는 영역 접미사를 표시하며 사용자가 호스트 앞에 추가합니다.
   * **리소스 레코드 종류** — `CNAME` 또는 `TXT`을(를) 선택하십시오.
   * **TTL** — 300초면 충분합니다.
   * CNAME 레코드의 경우 **[!UICONTROL 정식 이름]**&#x200B;에 대상을 입력하고 후행 기간으로 끝냅니다.
   * TXT 레코드의 경우 값을 데이터 필드에 붙여넣습니다.

1. 각 행에 대해 **[!UICONTROL 만들기]**&#x200B;를 클릭합니다.

>[!NOTE]
>
>정식 이름은 정규화된 이름이어야 하며 후행 마침표로 끝나야 합니다. 그렇지 않으면 확인이 실패합니다. DNS 팀은 `gcloud dns record-sets create` 명령을 사용하여 각 레코드를 추가할 수도 있습니다.

### 하위 도메인 보호 기능 {#subdomain-guardrails}

* **기본 제한:** 조직당 하위 도메인 10개. 더 필요한 경우 Adobe 담당자에게 문의하십시오(계약에 따라 최대 100개).
* **DNS 전파:** 변경 내용이 전역적으로 전파되는 데 24-48시간을 허용합니다. DNS가 아직 전파되지 않았기 때문에 유효성 검사가 실패할 수 있습니다.
* **하위 도메인 재사용:** 다른 Adobe 제품(Marketo Engage, Adobe Campaign)에서 이미 사용하고 있는 하위 도메인은 [!DNL Marketo Optimizer]에서 재사용할 수 없습니다.

## DMARC, SPF 및 DKIM {#dmarc-spf-dkim}

DMARC, SPF 및 DKIM은 이메일 인증 표준입니다. 이 둘을 합치면 메시지가 도메인을 대신하여 실제로 전송되고 스푸핑되지 않았음을 메일 서버를 받는 것으로 입증됩니다. Gmail, Yahoo, Microsoft과 같은 최신 ISP는 대량 발송자를 위해 이러한 표준을 필요로 합니다.

| 레코드 | 의 스탠드 | 용도 |
| ------ | ---------- | ------- |
| **SPF** | 보낸 사람 정책 프레임워크 | 도메인에서 메일을 보낼 수 있는 메일 서버 IP를 나열합니다. 수신 서버가 이 목록에 없는 IP의 메일을 거부합니다. Adobe은 하위 도메인(완전히 위임됨)을 위임할 때 SPF 레코드를 자동으로 만들고 유지 관리합니다. |
| **DKIM** | 식별된 메일 도메인 키 | 모든 아웃바운드 이메일에 암호화 서명이 추가되었습니다. 수신 서버는 DNS에 게시된 공개 키에 대해 서명을 확인합니다. Adobe은 하위 도메인을 위임하는 동안 DKIM 키 및 DNS 레코드를 자동으로 생성합니다. |
| **DMARC** | 도메인 기반 메시지 인증, 보고 및 적합성 | SPF 또는 DKIM이 실패할 경우 수행할 작업을 수신 서버에 알려주고 인증 결과에 대한 보고서를 제공합니다. DMARC에는 없음, 격리 및 거부의 세 가지 정책 모드가 있습니다. |

### DMARC 정책 모드 {#dmarc-policy-modes}

| 정책 | 액션 | 사용 시기 |
| ------ | ------ | ----------- |
| `none` | 모니터 | DMARC이 실패하면 수신 서버는 아무 작업도 하지 않지만 보고서를 전송합니다. 메시지 손실의 위험 없이 인증이 작동하는지 확인하기 위해 하위 도메인을 처음 위임할 때 사용합니다. |
| `quarantine` | 격리 | 수신 서버가 실패한 메시지를 스팸/정크 폴더에 배치합니다. |
| `reject` | 거부 | 수신 서버는 인증에 실패한 메시지를 거부(반송)합니다. 가장 엄격한 모드. 인증 설정이 확실할 때 권장됩니다. |

### DMARC 구성 {#configure-dmarc}

DMARC은 하위 도메인 위임 시 구성되지만 이미 위임된 하위 도메인에 대해 DMARC을 추가하거나 업데이트할 수도 있습니다.

1. [!DNL Marketo Optimizer] 왼쪽 탐색에서 **[!UICONTROL 관리]**&#x200B;를 확장하고 **[!UICONTROL 채널]**&#x200B;을 선택합니다.

1. 패널에서 **[!UICONTROL 전자 메일 설정]**&#x200B;을 확장하고 **[!UICONTROL 하위 도메인]**&#x200B;을 선택합니다.

1. 하위 도메인 목록에서 하위 도메인을 찾아 DMARC 레코드 열을 확인합니다.

   레코드가 누락된 경우 경고가 표시됩니다.

1. 하위 도메인을 열고 DMARC 레코드 섹션으로 스크롤합니다.

   * 부모 도메인에 DMARC 레코드가 이미 있으면 [!DNL Marketo Optimizer]에서 값을 자동으로 가져옵니다. 유지하거나 재정의할 수 있습니다.
   * 레코드가 없으면 **[!UICONTROL Adobe으로 관리]**&#x200B;를 선택하면 Adobe에서 DMARC 레코드를 만들고 호스팅합니다.

1. 정책: `none`, `quarantine` 또는 `reject`을(를) 설정합니다. 부모 도메인에서 성숙한 DMARC 자세를 가지고 있지 않은 경우 `none`부터 시작하십시오.

1. (선택 사항) 추가 DMARC 태그를 구성합니다(하위 도메인 정책은 `sp`, 백분율은 `pct`, 보고서 주소는 `rua` 및 `ruf`).

1. 완전히 위임된 경우 **[!UICONTROL 저장]**&#x200B;을 클릭합니다.

   Adobe은 레코드를 자동으로 적용합니다. CNAME을 사용하는 경우 DNS 레코드를 복사하고 DNS 팀이 추가하도록 한 다음 [!DNL Marketo Optimizer]에서 확인합니다.

1. DNS 전파에 최대 48시간을 허용한 다음 하위 도메인 페이지의 DMARC 상태 표시기가 녹색/정상인지 확인합니다.

>[!TIP]
>
>`policy=none`(으)로 시작하여 인증 보고서를 모니터링한 다음 정상 SPF 및 DKIM 정렬을 보고서에 표시한 후 `quarantine`(으)로, 마지막으로 `reject`(으)로 진행합니다. 모니터링 없이 `reject`(으)로 바로 이동하면 합법적인 메일이 거부될 수 있습니다.

## IP 풀 {#ip-pools}

IP 풀은 이메일을 보내는 데 사용되는 명명된 IP 주소 그룹입니다. IP 풀은 보낸 사람의 신뢰도에 매우 중요합니다. 각 풀은 ISP에 대한 자체 신뢰도가 있으므로 한 풀의 문제(예: 스팸 불만을 트리거하는 마케팅 버스트)는 다른 풀을 오염시키지 않습니다(예: 트랜잭션 확인).

### 풀 유형 {#pool-types}

| 풀 유형 | 가용성 | 설명 |
| --------- | ------------ | ----------- |
| **공유 IP 풀** | Beta에서 사용 가능 | Adobe에서 관리하고 많은 고객이 공유하는 IP 주소 풀입니다. 평판은 풀 전체에서 Adobe에 의해 유지됩니다. IP 웜업을 관리하지 않으려는 중저가 이메일 볼륨 및 고객에게 적합합니다. |
| **전용 IP 풀** | 로드맵(GA) | 조직에 독점적으로 할당된 하나 이상의 IP 주소. 명성은 당신이 가지고 있습니다. 대량 발송자에게 권장됩니다. IP 준비 계획 및 PTR 기록 관리를 포함합니다. |

### IP 풀 검토 및 할당 {#review-ip-pool}

이 릴리스에서는 조직에 대해 IP 풀이 사전 프로비저닝됩니다. 이메일 채널 구성을 만들 때 IP 풀을 할당합니다.

1. [!DNL Marketo Optimizer] 왼쪽 탐색에서 **[!UICONTROL 관리]**&#x200B;를 확장하고 **[!UICONTROL 채널]**&#x200B;을 선택합니다.
1. 패널에서 **[!UICONTROL 전자 메일 설정]**&#x200B;을 확장하고 **[!UICONTROL IP 풀]**&#x200B;을 선택합니다.
1. 조직에서 **[!UICONTROL 활성]** 상태의 IP 풀을 사용할 수 있는지 확인하십시오.
1. 풀 위로 마우스를 가져가 IP 주소 및 해당 PTR 레코드를 확인합니다(역방향 DNS).
1. 조직에 여러 사업부나 브랜드가 있는 경우 채널 구성을 만들기 전에 IP 풀(예: 마케팅 풀과 웨비나 풀)을 사용하는 방법을 계획하십시오.

>[!IMPORTANT]
>
>공유 풀을 사용할 수 있는 경우에도 동일한 IP 풀에서 마케팅 및 트랜잭션 트래픽을 혼합하지 마십시오. 채널 구성(마케팅 및 트랜잭션)의 이메일 유형 설정이 억제 동작을 제어하지만 채널 구성은 가능한 경우 여전히 개별 풀을 사용해야 합니다.

<!--

### Frequently asked questions {#faq}

| Question | Answer |
| -------- | ------ |
| **Can I reuse the subdomain I already use in Marketo Engage?** | No. A subdomain can only be associated with one Adobe product at a time. Create a new subdomain (for example, mail2.contoso.com) for [!DNL Marketo Optimizer]. |
| **Why does my channel configuration show Failed?** | The most common reasons are: MX record validation failed (your subdomain DNS isn't fully configured); DMARC misalignment; or an IP pool that is in Processing and has never been associated with the selected subdomain. Open the configuration to see the specific reason. |
| **What happens if a personalization token has no value at send time?** | If you defined a fallback with the Handlebars `default` helper, the fallback is used. If not, the token resolves to an empty string. [!DNL Marketo Optimizer] warns you when a token has no fallback and the underlying attribute is not guaranteed by the audience definition. |
| **Can I personalize using account-level attributes?** | Not in this release. Personalization in [!DNL Marketo Optimizer] today supports profile attributes only. |
| **What's the maximum email size?** | 100 KB is the recommended best-practice cap for inbox rendering. [!DNL Marketo Optimizer] warns you in the editor if you exceed it. |
| **Can I migrate existing Marketo email templates into [!DNL Marketo Optimizer]?** | A guided self-serve migration tool — including Velocity-to-Handlebars conversion — is delivered at GA. In this release, you can manually rebuild templates or paste raw HTML. |
| **Will my updates to Marketo assets show up in [!DNL Marketo Optimizer]?** | No. Asset availability in [!DNL Marketo Optimizer] is based on a one-time copy from Marketo Design Studio. Re-uploaded or modified Marketo assets are not reflected in [!DNL Marketo Optimizer] today. Native asset upload and management within [!DNL Marketo Optimizer] is on the Beta roadmap. |

## Glossary {#glossary}

| Term | Definition |
| ---- | ---------- |
| **DKIM** | DomainKeys Identified Mail — cryptographic email signature. |
| **DMARC** | Domain-based Message Authentication, Reporting & Conformance. |
| **FBL** | Feedback Loop — a service ISPs offer to receive spam-complaint reports back to senders. |
| **Handlebars** | JavaScript templating language used in [!DNL Marketo Optimizer] for personalization expressions. |
| **IP pool** | Group of IP addresses used to send email. |
| **MX record** | Mail Exchange DNS record — directs incoming mail to the correct mail servers. |
| **NS record** | Name Server DNS record — used to delegate a subdomain. |
| **PTR record** | Pointer record — reverse DNS that maps an IP address back to a hostname. |
| **RBAC** | Role-Based Access Control. |
| **SPF** | Sender Policy Framework — DNS record listing authorized sending IPs. |
| **Subdomain delegation** | Granting Adobe authority over a portion of your domain (a subdomain) for sending email. |

-->


