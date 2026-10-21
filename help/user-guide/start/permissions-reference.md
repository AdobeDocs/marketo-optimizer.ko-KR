---
title: 제품 권한
description: 관리자, 모든 액세스 권한 및 읽기 전용 사용자에 대한 설명 및 권장 권한과 함께 Marketo Optimizer 기능에 대한 액세스를 제어하는 Experience Platform 권한 목록을 참조하십시오.
TQID: https://experienceleague.adobe.com/Q4HnGxPkiE0dsZUjIgPvVJHgs0dPwLJiOKVSL1edS4Y
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3cf5f37e-e87e-5179-812b-53ce05d7eebb
    internal-label: Setup
  - id: a659ad61-de21-559d-a901-02e2fb329ff5
    internal-label: Administration
subfeature_v2:
  - id: b6434e31-d7bb-5416-960c-1c77bb1a2e8d
    internal-label: User Access
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
autotag-review: '2026-10-20T17:03:48.312Z'
source-git-commit: a33f749c32631dcd77ecf2892bdc3b1a5e06cd66
workflow-type: tm+mt
source-wordcount: '1556'
ht-degree: 3%
---
# 제품 권한

다음 권한은 [!DNL Adobe Marketo Optimizer]의 기능에 대한 액세스를 제어합니다. [!DNL Adobe Experience Platform]의 _[!UICONTROL 권한]_ 영역에서 역할에 추가하세요. 역할을 만들고 사용자에게 할당하는 방법에 대한 자세한 내용은 [_사용자 액세스 및 권한_](./user-management.md)&#x200B;을 참조하세요.

마지막 세 열에는 [제안된 각 사용자 유형](#suggested-user-types)에 대해 권장되는 권한(관리자, 모든 액세스 사용자 및 읽기 전용 액세스 사용자)이 표시됩니다. 확인 표시(✔)는 해당 사용자 유형에 대한 권한이 권장됨을 의미하고 대시(-)는 권장되지 않음을 의미합니다. 조직에 맞게 권장 사항을 조정하십시오.

>[!IMPORTANT]
>
>[!DNL Marketo Optimizer] 액세스를 사용하려면 명명 규칙 `Mktoaep` + [!DNL Marketo Engage] 구독 접두사를 사용하여 프로비저닝된 특정 샌드박스를 활성화해야 합니다. 예를 들어 연결된 [!DNL Marketo Engage] 구독 접두사가 _AcmeAssoc_&#x200B;인 경우 [!DNL Marketo Optimizer] 액세스에 필요한 샌드박스는 _MktoaepAcmeAssoc_&#x200B;입니다. 모든 역할에 이 샌드박스를 추가합니다.

>[!NOTE]
>
>Experience Platform에서 _[!UICONTROL 권한]_ 타일을 보려면 시스템 관리자여야 합니다.

일부 권한은 제품에서 아직 사용할 수 없는 기능에 적용됩니다. 이제 관리자는 이러한 권한을 추가하여 기능을 사용할 수 있을 때 사용자가 해당 액세스 권한을 가질 수 있도록 할 수 있습니다.

## 제안된 사용자 유형 {#suggested-user-types}

이 페이지의 표에 나와 있는 권한 권장 사항을 생성하는 역할의 시작점으로 사용하십시오. 각 사용자 유형에 대한 제안입니다. 조직에 맞게 조정하십시오.

| 속성 | 관리 | 모든 액세스 사용자 | 읽기 전용 액세스 사용자 |
| --- | ----- | --------------- | --------------------- |
| **대상** | 귀하의 팀에 대해 [!DNL Marketo Optimizer]을(를) 설정하고 관리하는 사람입니다. | 매일 [!DNL Marketo Optimizer]에서 작업하는 마케터 및 운영자입니다. | [!DNL Marketo Optimizer]을(를) 보아야 하지만 경영진, 분석가 및 감사자와 같이 변경할 내용이 없는 사람. |
| **수행할 수 있는 작업** | 설정 및 관리자 설정을 포함한 모든 작업. | 여정, 프로그램, 콘텐츠, 목록, 보고서 및 길잡이 등의 모든 기능을 사용합니다. | 여정, 프로그램, 콘텐츠, 목록 및 보고서를 보고 길잡이에게 질문합니다. |
| **할당할 권한** | 이 페이지의 모든 권한(**[!UICONTROL 역할 편집기에서 모두 추가]** 선택). | 이 페이지에 있는 테이블의 _모든 액세스_ 열에 ✔이(가) 있는 권한입니다. | 이 페이지에 있는 테이블의 _읽기 전용_ 열에 ✔이(가) 있는 권한입니다. |
| **포함되지 않음** | – | <li>관리자 구성<li>이메일 설정, 양식 사전 설정, 랜딩 페이지 설정, WhatsApp 사전 설정 및 설정을 포함한 채널 구성<li>프로그램 유형(보기 및 관리) | <li>만들기, 편집, 삭제, 게시 또는 내보내기(채팅 액세스를 제외한 모든 _관리_ 및 _게시_ 권한)<li>대상에 대한 대상자 활성화<li>이메일 설정 및 양식 사전 설정 보기를 포함한 관리 구성 및 채널 구성<li>프로그램 유형 보기 |
| **추천 사용자 그룹** | Marketo Optimizer 관리자 그룹 | Marketo Optimizer 사용자 그룹 | Marketo Optimizer 읽기 전용 사용자 그룹 |
| **제안된 역할** | Marketo Optimizer 관리자 | Marketo Optimizer 모든 액세스 사용자 | Marketo Optimizer 읽기 전용 액세스 사용자 |

이러한 그룹 및 역할을 만드는 절차에 대해서는 [제안된 사용자 유형에 대한 사용자 그룹 및 역할 만들기](./user-management.md#create-suggested-roles)를 참조하십시오.

## 컨텐츠 및 자산 {#content-assets}

| 카테고리 | 사용 권한 | 설명 | 관리 | 모든 액세스 | 읽기 전용 |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B Assets | B2B Assets 관리 | 에셋 파일을 만들고, 편집하고, 삭제합니다. | ✔ | ✔ | – |
| | B2B 이메일 관리 | 이메일 메시지 작성, 편집 및 삭제 | ✔ | ✔ | – |
| | B2B Forms 관리 | 양식을 작성, 편집 및 삭제합니다. | ✔ | ✔ | – |
| | B2B 조각 관리 | 콘텐츠 조각을 만들고, 편집하고, 삭제합니다. | ✔ | ✔ | – |
| | B2B 랜딩 페이지 관리 | 랜딩 페이지 만들기, 편집 및 삭제 | ✔ | ✔ | – |
| | B2B 메시지 내보내기 관리 | _전자 메일_ 섹션에서 메시지 보고서를 내보냅니다. | ✔ | ✔ | – |
| | B2B 템플릿 관리 | 콘텐츠 템플릿을 만들고, 편집하고, 삭제합니다. | ✔ | ✔ | – |
| | B2B 웨비나 관리 | 대화형 웨비나 만들기, 편집 및 삭제 | ✔ | ✔ | – |
| | B2B Forms 게시 | 랜딩 페이지에서 사용할 양식을 게시합니다. | ✔ | ✔ | – |
| | B2B 조각 게시 | 템플릿, 이메일 및 랜딩 페이지에서 사용할 콘텐츠 조각을 게시합니다. | ✔ | ✔ | – |
| | B2B 랜딩 페이지 게시 | 랜딩 페이지를 게시합니다. | ✔ | ✔ | – |
| | B2B Assets 보기 | Assets 라이브러리 및 자산 파일 세부 사항을 봅니다. | ✔ | ✔ | ✔ |
| | B2B 이메일 보기 | 이메일 메시지를 봅니다. | ✔ | ✔ | ✔ |
| | B2B Forms 보기 | 양식 보기. | ✔ | ✔ | ✔ |
| | B2B 조각 보기 | 콘텐츠 조각 목록 및 세부 정보를 봅니다. | ✔ | ✔ | ✔ |
| | B2B 랜딩 페이지 보기 | 랜딩 페이지를 봅니다. | ✔ | ✔ | ✔ |
| | B2B 템플릿 보기 | 콘텐츠 템플릿 목록 및 세부 정보를 봅니다. | ✔ | ✔ | ✔ |
| | B2B 웨비나 보기 | 대화형 웨비나를 봅니다. | ✔ | ✔ | ✔ |

## 채널 구성 및 관리 {#channels-admin}

| 카테고리 | 사용 권한 | 설명 | 관리 | 모든 액세스 | 읽기 전용 |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B 관리 구성 | B2B 관리 구성 관리 | 디지털 자산 관리 연결, 자산 저장소 및 이벤트와 같은 관리 설정을 구성합니다. | ✔ | – | – |
| B2B 채널 구성 | B2B 채널 구성 관리 | 왼쪽 탐색 및 모든 채널 구성 작업에서 _채널_ 메뉴 항목에 액세스합니다. | ✔ | – | – |
| | B2B 이메일 설정 관리 | 이메일 설정을 구성합니다. 사용자가 이메일을 보낼 수 있으려면 이러한 설정이 필요합니다. | ✔ | – | – |
| | B2B Forms 사전 설정 관리 | 양식 사전 설정을 만들고, 편집하고, 삭제합니다. | ✔ | – | – |
| | B2B 랜딩 페이지 설정 관리 | 하위 도메인과 같은 랜딩 페이지 설정을 구성합니다. | ✔ | – | – |
| | B2B WhatsApp 사전 설정 관리 | WhatsApp 메시지 사전 설정 및 관련 SMS 설정을 만들고, 보고, 삭제합니다. | ✔ | – | – |
| | B2B WhatsApp 설정 관리 | WhatsApp 채널 설정을 구성합니다. | ✔ | – | – |
| | B2B Forms 사전 설정 게시 | 양식 사전 설정을 게시합니다. | ✔ | – | – |
| | B2B 이메일 설정 보기 | 이메일 설정(하위 도메인, PTR 레코드, IP 풀, 제외 목록, 시드 목록, IP 준비 계획) 보기. | ✔ | – | – |
| | B2B Forms 사전 설정 보기 | 양식 사전 설정을 봅니다. | ✔ | – | – |

## 여정, 프로그램 및 폴더 {#journeys-programs}

| 카테고리 | 사용 권한 | 설명 | 관리 | 모든 액세스 | 읽기 전용 |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B 폴더 토큰 | B2B 폴더 토큰 관리 | 폴더에서 토큰을 생성, 편집 및 삭제합니다. 변경 내용은 폴더의 모든 항목에 적용되므로 _B2B 폴더 관리_&#x200B;와 별도로 할당하십시오. | ✔ | ✔ | – |
| | B2B 폴더 토큰 보기 | 폴더에 정의된 토큰을 봅니다. | ✔ | ✔ | ✔ |
| B2B 폴더 | B2B 폴더 관리 | 폴더를 생성, 편집 및 삭제합니다. | ✔ | ✔ | – |
| | B2B 폴더 보기 | 폴더를 봅니다. | ✔ | ✔ | ✔ |
| B2B 여정 | B2B 여정 트래픽 제어 관리 | 효과 시뮬레이션을 포함하여 여정 트래픽 제어를 구성합니다. | ✔ | ✔ | – |
| | B2B 개인 여정 관리 | _개인 여정_ 목록 및 모든 개인 여정 작업에 액세스합니다. | ✔ | ✔ | – |
| | B2B 개인 여정 게시 | 사용자 여정 게시. | ✔ | ✔ | – |
| | B2B 여정 트래픽 제어 보기 | 여정 트래픽 제어 설정을 봅니다. | ✔ | ✔ | ✔ |
| | B2B 개인 여정 보고서 보기 | _개인 여정 개인_ 보고서를 포함한 개인 여정 보고서를 봅니다. | ✔ | ✔ | ✔ |
| | B2B 개인 여정 보기 | _개인 여정_ 목록 및 여정 세부 정보에 대한 읽기 전용 액세스 권한. | ✔ | ✔ | ✔ |
| B2B 프로그램 토큰 | B2B 프로그램 토큰 관리 | 프로그램 및 프로그램 유형에서 토큰을 생성, 편집 및 삭제합니다. | ✔ | ✔ | – |
| | B2B 프로그램 토큰 보기 | 프로그램 및 프로그램 유형에 정의된 토큰을 봅니다. | ✔ | ✔ | ✔ |
| B2B 프로그램 유형 | B2B 프로그램 유형 관리 | 마케팅 프로그램 유형을 작성, 편집 및 삭제합니다. | ✔ | – | – |
| | B2B 프로그램 유형 보기 | 마케팅 프로그램 유형을 봅니다. | ✔ | – | – |
| B2B 프로그램 | B2B 프로그램 관리 | 마케팅 프로그램을 만들고, 편집하고, 삭제합니다. | ✔ | ✔ | – |
| | B2B 프로그램 보기 | 마케팅 프로그램을 봅니다. | ✔ | ✔ | ✔ |

## 대상자, 의도 및 대상 {#audiences-intent}

| 카테고리 | 사용 권한 | 설명 | 관리 | 모든 액세스 | 읽기 전용 |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B 대상 | B2B 대상 활성화 | B2B 대상에 대상을 활성화합니다. | ✔ | ✔ | – |
| | B2B 대상 관리 | B2B 대상을 만들고, 편집하고, 삭제합니다. | ✔ | ✔ | – |
| | B2B 대상 보기 | B2B 대상에 대한 보기 전용 액세스입니다. | ✔ | ✔ | ✔ |
| B2B 의도 구성 | B2B 의도 구성 관리 | 의도 구성을 작성, 편집 및 삭제합니다. | ✔ | ✔ | – |
| | B2B 의도 구성 보기 | 의도 구성 보기(의도 가중치 모델). | ✔ | ✔ | ✔ |
| B2B 조직 규칙 | B2B 조직 규칙 관리 | 조직 규칙을 작성, 편집 및 삭제합니다. | ✔ | ✔ | – |
| | B2B 조직 규칙 보기 | 조직 규칙을 봅니다. | ✔ | ✔ | ✔ |
| B2B 개인 목록 | B2B 개인 목록 관리 | 개인 목록을 작성, 편집 및 삭제하고 목록 멤버십을 관리합니다. | ✔ | ✔ | – |
| | B2B 개인 목록 보기 | 정적 및 동적 사용자 목록을 봅니다. | ✔ | ✔ | ✔ |

## 보고서, Labs 및 채팅 {#reports-labs-chat}

| 카테고리 | 사용 권한 | 설명 | 관리 | 모든 액세스 | 읽기 전용 |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B 대화 경험 | B2B 대화 경험 관리 | 채팅 패널 및 도우미에 대한 액세스. 패널의 작업에는 일치하는 기능 권한도 필요합니다. 예를 들어 여정을 만들려면 _B2B 개인 여정 관리_&#x200B;가 필요합니다. [채팅 권한](#chat-permissions)을 참조하세요. | ✔ | ✔ | ✔ |
| B2B 랩 | B2B Labs 관리 | Labs 기능을 활성화하고 구성합니다. | ✔ | ✔ | – |
| | B2B Labs 보기 | 사용 가능하고 활성화된 Labs 기능을 봅니다. | ✔ | ✔ | ✔ |
| B2B 보고 | B2B 포함된 보고서 보기 | _보고서_ 탭에서 보고서를 봅니다. | ✔ | ✔ | ✔ |
| | B2B 의도 보고서 보기 | 의도 보고서를 봅니다. | ✔ | ✔ | ✔ |

## 채팅 권한 {#chat-permissions}

채팅 권한은 기능 수준 권한을 따릅니다. [!DNL Coworker for Marketo Optimizer]은(는) 채팅의 모든 스킬 또는 작업을 채팅 외부에서 기능에 필요한 권한과 동일한 권한으로 검사합니다. _관리_ 권한으로 만들기, 편집 또는 게시하고 _보기_ 권한으로 읽기 전용 스킬을 만듭니다. 사용자에게 기능 권한이 없는 경우 [!DNL Coworker]이(가) 해당 작업을 수행할 수 없습니다. 예를 들어, 여정을 만들려면 _B2B 개인 여정 관리_&#x200B;가 필요하며 목록 양식에는 _B2B Forms 보기_&#x200B;가 필요합니다.

<!--
_Manage B2B Conversational Experience_ gives access to the [!DNL CX Coworker] chat panel, but it does not grant access to any feature functions.

Per wiki: 
Update 10/02: We are no longer mapping b2b-conversational-experience read or write to any tools. It was decided that chat will be available for all users without permissions, but what they can do within the chat (i.e. tools they can use) will be defined by other permissions.
-->

## 외부 대상 권한 {#external-destinations-permissions}

[!DNL Marketo Optimizer]의 사용자에게 외부 대상에 대한 액세스 권한을 제공하려면 다음 권한이 필요합니다. 열은 [제안된 사용자 유형](#suggested-user-types)에 설명된 각 사용자 유형에 대한 동일한 권장 사항을 따릅니다.

| 카테고리 | 사용 권한 | 설명 | 관리 | 모든 액세스 | 읽기 전용 |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| 대시보드 | 표준 대시보드 관리 | Data Warehouse에 아직 없는 사용자 지정 특성을 추가합니다. | ✔ | ✔ | – |
| | 표준 대시보드 보기 | _프로필_, _대상_ 및 _세그먼트_ 대시보드에 대한 보기 전용 액세스입니다. 왼쪽 탐색에서 _대시보드_&#x200B;에 액세스할 수도 있습니다. | ✔ | ✔ | ✔ |
| 대상 | 대상 활성화 | 활성 대상에 데이터를 활성화합니다. _대상 보기_ 또는 _대상 관리_&#x200B;도 필요합니다. | ✔ | ✔ | – |
| | 매핑 없이 세그먼트 활성화 | 매핑 단계 없이 기존 대상에 대한 대상자를 활성화합니다. 사용자는 활성화 워크플로에서 대상을 추가하거나 제거할 수 있지만 매핑된 속성 또는 ID를 추가하거나 제거할 수 없습니다. _대상 보기_&#x200B;도 필요합니다. | ✔ | ✔ | – |
| | 대상 작성 | Experience Platform Destination SDK을 사용하여 대상을 작성합니다. | ✔ | ✔ | – |
| | 데이터 세트 대상 관리 및 활성화 | 데이터 세트 내보내기 흐름을 보고, 만들고, 편집하고, 비활성화하고, 데이터 세트로 데이터를 활성화합니다. _대상 보기_&#x200B;도 필요합니다. | ✔ | ✔ | – |
| | 대상 관리 | 대상 연결 및 대상 계정을 보고, 만들고, 삭제합니다. | ✔ | ✔ | – |
| | 대상 보기 | _카탈로그_ 탭에서 사용 가능한 대상을 보고 _찾아보기_ 탭에서 인증된 대상을 봅니다. | ✔ | ✔ | ✔ |
| 데이터 거버넌스 | B2B 관리 사용 레이블 삭제 | 데이터 세트 및 스키마에 적용된 DULE(데이터 사용 레이블)를 보고, 만들고, 삭제합니다. | ✔ | ✔ | – |
| | 데이터 사용 정책 관리 | 데이터 사용 정책을 보고, 만들고, 편집하고, 삭제합니다. | ✔ | ✔ | – |
| | 데이터 사용 정책 보기 | 조직에 속한 데이터 사용 정책에 대한 보기 전용 액세스입니다. | ✔ | ✔ | ✔ |
| 데이터 수집 | 소스 관리 | 소스를 보고 만들고 편집하고 비활성화합니다. | ✔ | ✔ | – |
| | 소스 보기 | _카탈로그_ 탭에서 사용 가능한 원본을 보고 _찾아보기_ 탭에서 인증된 원본을 봅니다. | ✔ | ✔ | ✔ |
| 프로필 관리 | 프로필 설정 관리 | 모든 프로필 설정을 보고 편집합니다. | ✔ | ✔ | – |
| | 프로필 설정 보기 | 모든 프로필 설정에 대한 보기 전용 액세스 권한. | ✔ | ✔ | ✔ |

<!-- 

## Planned permissions {#planned-permissions}

The following permissions are for features that are not yet available in [!DNL Marketo Optimizer]. Adobe Marketo Qualifier permissions are not currently enforced. The estimated enforcement date is November 2026. Accounts and buying groups are targeted for delivery in Q1 2027.

| Category | Permission | Description | Admin | All Access | Read Only |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| Marketo Qualifier Configurations | Manage Marketo Qualifier Configurations | Create, edit, and delete Marketo Qualifier configurations. | ✔ | – | – |
| | View Marketo Qualifier Configurations | View Marketo Qualifier configurations. | ✔ | ✔ | ✔ |
| Marketo Qualifier Outbound | View Marketo Qualifier Outbound | View Marketo Qualifier outbound workflows and outbound reporting. | ✔ | ✔ | ✔ |
| Marketo Qualifier Research | Manage Marketo Qualifier Research | Use and manage research capabilities. | ✔ | ✔ | – |
| | View Marketo Qualifier Research | View research: conversational interface, prospect view, and account and lead research. | ✔ | ✔ | ✔ |
| B2B Account Lists | Manage B2B Account Lists | Create, edit, and delete account lists, including adding, removing, and importing accounts. | ✔ | ✔ | – |
| B2B Buying Groups | Manage B2B Buying Groups | Create, edit, and delete buying groups. | ✔ | ✔ | – |
| | Manage B2B Role Templates | Manage the role templates used in buying groups. | ✔ | ✔ | – |
| | Manage B2B Solution Interests | Manage the solution interests used in buying groups. | ✔ | ✔ | – |
| | Manage B2B Stages | Manage buying group stages. | ✔ | ✔ | – |
| | View B2B Buying Groups | View buying groups. | ✔ | ✔ | ✔ |

-->
