---
title: 대화형 웨비나
description: 웨비나 자산 모델, 멤버 상태, 토큰 및 활동을 포함하여 Marketo Optimizer에서 대화형 웨비나에 포함된 개념을 알아봅니다.
keywords: 
role: User
feature: Channels
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 75b481faf0d66210329f95c8afabdfa59e7bcb79
workflow-type: tm+mt
source-wordcount: 1085
ht-degree: 2%

---


# 대화형 웨비나

대화형 웨비나를 사용하면 [!DNL Adobe Marketo Optimizer]을(를) 종료하지 않고도 라이브 또는 시뮬레이션된 라이브 웨비나를 계획, 승격, 게재 및 후속 작업을 수행할 수 있습니다. 게재는 [!DNL Adobe Connect]에서 자동으로 실행되므로 제품을 전환하여 등록 페이지를 디자인하거나, 실시간 세션을 호스팅하거나, 참석 데이터를 가져올 필요가 없습니다.

>[!NOTE]
>
>이 기능을 사용하려면 라이센스가 필요하며 추가 약관이 적용됩니다. 추가 약관에 대해 문의하려면 계약을 검토하거나 Adobe에 문의하십시오.

웨비나는 다음 두 가지 방법으로 만들 수 있습니다.

* **대화 경험** - 동료에게 자연어로 웨비나를 예약, 승격 및 보고하도록 요청합니다. [동료와 웨비나 만들기](../agents/webinar-creation.md)를 참조하십시오.

* **가리키고 클릭** - _[!UICONTROL 프로그램]_ 작업 영역을 사용하여 웨비나 에셋을 추가하고, 디자인하고, 공동 호스트 및 발표자를 추가하고, 승격 및 후속 여정을 빌드하고, 보고를 검토할 수 있습니다. [웨비나 만들기 및 디자인](create-webinar.md) 및 [웨비나 홍보 및 후속 여정](webinar-journeys.md)을 참조하세요.

## 자산으로서의 웨비나

웨비나는 전자 메일 또는 랜딩 페이지와 같은 방식으로 [program](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/prime/marketing-management/programs/programs)이(가) 소유한 자산입니다. 프로그램에 웨비나를 추가하면 해당 프로그램에 웨비나가 등록되고 해당 프로그램의 모든 여정 및 에셋에서 토큰, 속성 및 활동을 사용할 수 있습니다.

>[!IMPORTANT]
>
>프로그램은 현재 하나의 웨비나 자산을 소유할 수 있습니다. 향후 릴리스를 위해 프로그램당 여러 웨비나에 대한 지원이 계획되어 있습니다.

## 회원국

웨비나를 포함하는 프로그램의 구성원인 사람에게는 세 개의 독립국이 동시에 적용된다. 각각은 대상 및 여정 조건에서 별도로 참조할 수 있습니다.

| 주 | 소유자 | 값 |
|---|---|---|
| 프로그램 구성원 상태 | 프로그램 | [프로그램 유형](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/prime/admin/program-types)별 구성 가능 |
| 웨비나 상태 | 웨비나 자산 | 초대됨, 등록됨, 참석됨, 표시 안 함, 온디맨드로 참석함 |
| 여정 상태 | 여정 | 현재 노드, 일시 중지, 완료 및 기타 여정 런타임 상태 |

### 웨비나 상태

웨비나 상태에는 5개의 값이 있습니다. [!DNL Adobe Connect]은(는) 일반적으로 값을 자동으로 설정하지만, 재정의해야 하는 경우 여정 작업으로 상태를 설정할 수도 있습니다. 예를 들어 다른 시스템에 기록된 출석을 반영하기 위해 여정에서 상태를 설정할 수 있습니다.

| 상태 | 설정 방법 | 소스 |
|---|---|---|
| 초대됨 | 일반적으로 초대 이메일을 보낼 때 _동작 수행_ 여정 노드 | 작성자 제어 |
| 등록됨 | 등록 시 _작업 수행_ 여정 노드입니다. [!DNL Adobe Connect]을(를) 트리거하여 해당 사용자의 가입 URL을 생성합니다. | 작성자 제어 |
| 출석함 | 라이브 웨비나가 실행된 후 [!DNL Adobe Connect]의 이벤트 | 시스템 제어, 여정을 통해 사용 가능한 작성자 재정의 |
| 표시 안 함 | 라이브 웨비나가 실행된 후 [!DNL Adobe Connect]의 이벤트 | 시스템 제어, 여정을 통해 사용 가능한 작성자 재정의 |
| 온디맨드 출석 | [!DNL Adobe Connect]의 이벤트(참석하지 않은 사용자가 나중에 녹화를 실시간으로 시청하는 경우) | 시스템 제어, 여정을 통해 사용 가능한 작성자 재정의 |

>[!IMPORTANT]
>
>자동으로 설정하든 여정에서 설정하든 간에 웨비나 상태는 [프로그램 상태](./programs.md#statuses)와 같은 방식으로 한 방향으로만 이동합니다. 사용자는 이후 상태(예: _등록됨_ ~ _참석됨_)로 이동할 수 있지만 이전 상태로 돌아갈 수는 없습니다. 이 선형 진행을 염두에 두고 작성자 재정의를 계획합니다.

여정의 상태 간에 개인을 이동하려면 **[!UICONTROL 웨비나 멤버 상태 변경]** 액션을 사용하십시오. [웨비나 홍보 및 후속 여정](webinar-journeys.md)을 참조하세요.

## 웨비나 토큰

웨비나 토큰은 이메일 콘텐츠(제목, 본문, 사전 헤더 및 발신자)를 개인화하는 모든 곳에서 사용할 수 있습니다. **_컨텍스트 > 웨비나_** 아래의 개인화 편집기에서 찾으십시오.

자산 수준 토큰은 웨비나 폴더에 직접 배치됩니다.

- 직함
- 설명
- 시작 날짜/시간, 종료 날짜/시간
- 기간
- 시간대
- 발표자
- 레코딩 URL

>[!NOTE]
>
>공동 호스트는 웨비나 페이지의 웨비나 팀 섹션에 표시되지만 개인화 토큰으로 사용할 수 없습니다.

**구성원** 하위 폴더에 있는 받는 사람당 토큰:

- **상태** - 받는 사람의 현재 웨비나 상태(초대됨, 등록됨, 참석함, 표시 안 함 또는 요청 시 참석함)입니다. [웨비나 상태](#webinar-status)를 참조하세요.
- **URL 가입** - 수신자의 개인 [!DNL Adobe Connect] 링크입니다. 수신자의 웨비나 상태가 등록됨 또는 이후 버전인 경우에만 확인됩니다. 이전 단계에서 모든 사용자가 비어 있게 해결됩니다.
- **녹화 URL** - 라이브 세션 후에 녹화가 게시된 후 확인되며, 그 때까지 비어 있습니다. 표시할 녹화가 있기 전에 링크가 표시되지 않도록 포스트 웨비나 이메일에서 조건부로 사용하십시오.

>[!NOTE]
>
>웨비나 토큰은 현재 이메일 콘텐츠에서만 렌더링됩니다(제목, 본문, 사전 헤더 및 발신자). 랜딩 페이지 및 양식의 웨비나 토큰에 대한 지원은 향후 릴리스에서 제공될 예정입니다.
>
>이러한 토큰은 오류를 발생하는 대신 비어 있는 것으로 확인되므로 이를 참조하는 이메일 또는 페이지가 웨비나 라이프사이클의 어느 시점에서든 안전하게 렌더링됩니다. 값을 사용하기 전후의 콘텐츠를 미리 보면 어느 방식으로든 레이아웃이 올바르게 보이는지 확인할 수 있습니다.

## 웨비나 활동

모든 웨비나는 _이벤트 수신_ 트리거, _경로 분할_ 조건, 대상 필터 및 보고 지표로 사용할 수 있는 활동을 자동으로 보고합니다.

* 질문하기
* 폴에 응답
* 링크 클릭
* 에셋 다운로드
* 손 올리기

>[!NOTE]
>
>웨비나 상태 변경(초대됨, 등록됨, 참석됨, 표시 안 함, 필요 시 참석됨)은 현재 고유한 _이벤트 수신_ 트리거 또는 활동 필터로 사용할 수 없습니다. 웨비나 상태에서 여정을 분기하려면 상태 변경 활동을 수신하는 대신 웨비나 상태에서 직접 _경로 분할_ 조건([_후 웨비나 여정 빌드_](webinar-journeys.md#build-post-webinar-journey)&#x200B;에 설명되어 있음)을 사용합니다.

라이브 이벤트 후 녹화를 시청하는 사람들의 참여가 온디맨드 모드로 태그가 지정된 동일한 활동으로 수집됩니다. 활동과 달리, 온디맨드 참여는 별도의 웨비나 상태를 만듭니다. 라이브로 참여하지 않았으며 나중에 녹화를 시청하는 사람은 **표시 안 함**&#x200B;에서 **온디맨드 참석**(으)로 이동합니다.

## 사전 요구 사항

웨비나 빌드를 시작하기 전에 다음 사항이 준비되었는지 확인하십시오.

| 사전 요구 사항 | 세부 사항 |
|---|---|
| 프로그램 | 웨비나는 기존 프로그램 내에 추가됩니다. 마케팅 운영 분석가는 일반적으로 프로그램을 먼저 만듭니다. |
| 웨비나 라이선스(용량) | 웨비나를 예약하려면 먼저 용량 자격이라고도 하는 웨비나 라이선스를 사용할 수 있어야 합니다. 설치 시 용량을 선택하면 더 많은 용량을 추가할 수 있습니다. 가용 용량을 늘리려면 Adobe 계정 팀에 문의하십시오. |
| [!DNL Adobe Connect] | 게재가 [!DNL Adobe Connect]에서 실행됩니다. 백그라운드에서 프로비저닝이 자동으로 수행됩니다. 웨비나를 작성하거나 호스팅하기 위해 [!DNL Marketo Optimizer]에서 나갈 필요가 없습니다. |

### 권한

웨비나 기능에 대한 액세스 권한은 웨비나에 할당된 권한에 따라 다릅니다.

| 역할 | 부여 내용 |
|---|---|
| B2B 웨비나 보기 | 웨비나 목록과 웨비나 구성, 세부 정보 및 보고서를 봅니다. 이 권한을 통해서는 만들기, 디자인, 편집 및 입력 컨트롤을 사용할 수 없으며 웨비나에 공동 호스트 또는 발표자로 할당할 수 없습니다. |

<!-- 
| Manage B2B webinars | Full lifecycle access: create, design, configure, schedule, edit, deliver, host, and delete a webinar. The Create, Design, Edit, and Manage controls are available only for users with this role. |
| Webinar co-host | After you are added as a co-host, this permission enables you to design and enter that webinar with co-host controls. |
| Webinar presenter | After you are added as a presenter, this permission enables you to view and enter that webinar with presenter capabilities. It grants no authoring or design access on its own. |

>[!NOTE]
>
>Co-hosts and presenters are currently defined by entering a name and email rather than selected from a picker of role-eligible users — see [Add co-hosts and presenters](create-webinar.md#add-co-hosts-and-presenters). The _Webinar co-host_ and _Webinar presenter_**_ roles still govern what that person can do when they are added as a co-host or presenter.

-->
