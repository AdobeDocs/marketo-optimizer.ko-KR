---
title: 이벤트 노드 수신
description: Marketo Optimizer에서 이벤트 노드 수신 대기를 구성 - 이벤트 트리거를 설정하고, 선택적 필터를 적용하고, 활동이나 데이터 변경이 발생할 때 인력을 배치합니다.
TQID: 'https://experienceleague.adobe.com/6v3i6M-Hhr2RAWrS68WaEVb8VJEzJZbD7vXOJOsjgc8'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
source-git-commit: bc370a501d3f8ff80ad846576b62504aca77f530
workflow-type: tm+mt
source-wordcount: '1158'
ht-degree: 2%
---
# 이벤트 노드 수신

이벤트가 발생할 때 대상을 여정의 다음 단계로 이동하려면 _이벤트 수신_ 노드를 추가하십시오.

## 이벤트 트리거 {#event-triggers}

여정 노드를 실행하고 대상 구성원을 앞으로 이동하는 이벤트 기준을 정의합니다.

| 트리거 | 설명 |
| -------- | ----------- |
| Brand Concierge | [!DNL Brand Concierge]과(와) 관련된 리드에 대한 활동입니다. |
| 이메일 | 전송, 게재 및 참여를 포함한 잠재 고객의 이메일 활동. |
| 이벤트 | 등록, 출석 및 상호 작용을 포함한 잠재 고객을 위한 대화형 웨비나 활동. |
| 기회 | 가망 고객 또는 계정과 연관된 기회 레코드와 관련된 활동. |
| 판매 앱 | [!DNL Sales Qualifier] 또는 [!DNL Marketo Sales Insights]과(와) 관련된 잠재 고객 활동. |
| 기타 | 사전 정의된 범주에 속하지 않는 활동으로, 사용자 지정 또는 기타 이벤트 트리거를 유연하게 사용할 수 있습니다. |

>[!BEGINSHADEBOX]

**트리거에 대해 지원되는 Marketo Engage 활동**

이벤트를 트리거할 때 [!DNL Marketo Optimizer]은(는) 데이터 소스로 연결된 [!DNL Marketo Engage] 인스턴스의 활동을 지원합니다.

>[!NOTE]
>
>데이터 원본으로 [!DNL Marketo Engage] 인스턴스는 하나만 있을 수 있으며 [!DNL Marketo Optimizer] 인스턴스를 프로비저닝할 때 미리 구성되어 있습니다.

다음 [!DNL Marketo Engage]개 활동에 대해 이벤트 트리거를 만들 수 있습니다.

* **[!UICONTROL Marketo Engage 양식을 작성합니다]** - 잠재 고객이 지정된 [!DNL Marketo Engage] 양식을 제출할 때 실행됩니다.
* **[!UICONTROL Marketo Engage 웹 페이지 방문]** - Munchkin 추적 쿠키를 사용하는 잠재 고객이 지정된 웹 페이지를 방문할 때 실행됩니다.
* **[!UICONTROL Marketo Engage 웹 페이지의 링크 클릭]** - 잠재 고객이 [!DNL Marketo Engage] Munchkin 추적 코드가 설치된 웹 페이지에서 추적된 하이퍼링크를 클릭할 때 실행됩니다.
* **[!UICONTROL Marketo Engage 전자 메일이 전달됨]** - 잠재 고객의 메일 서버(MX)가 [!DNL Marketo Engage] 전송 서버에 성공 응답(250 OK 메시지)을 반환할 때 실행됩니다.
* **[!UICONTROL Marketo Engage 전자 메일 바운스]** - 대상 메일 서버가 보낸 [!DNL Marketo Engage] 전자 메일 메시지를 잘못된 사용자 또는 알 수 없는 도메인과 같은 영구적인 오류로 거부할 때 발생합니다.
* **[!UICONTROL Marketo Engage 전자 메일이 소프트 바운스]** - 대상 메일 서버가 보낸 [!DNL Marketo Engage] 전자 메일 메시지를 일시적인 문제(예: 서버 사용 중 또는 사서함 가득 참)로 거부할 때 발생합니다. [!DNL Marketo Engage]에서 소프트 바운스를 MX 서버를 통해 최대 3회까지 자동으로 다시 시도한 후 문제를 플래그 지정합니다.
* **[!UICONTROL Marketo Engage 이메일 구독 취소]** - 잠재 고객이 비운영 마케팅 이메일을 거부하면 실행됩니다. 트리거되면 [!DNL Marketo Engage]이(가) 잠재 고객의 `Unsubscribed` 필드 값을 `true`(으)로 자동 업데이트하여 향후 표준 이메일 전송에서 제외합니다.
* **[!UICONTROL Marketo Engage 이메일을 엽니다]** - 잠재 고객이 추적된 [!DNL Marketo Engage] 이메일을 열 때 실행됩니다.
* **[!UICONTROL Marketo Engage 전자 메일의 링크 클릭]** - 잠재 고객이 [!DNL Marketo Engage] 전자 메일 내의 모든 링크(또는 특정 제한 링크)를 클릭할 때 실행됩니다.

>[!ENDSHADEBOX]

## 이벤트 필터 {#event-filters}

다양한 기준에 따라 일치하는 이벤트 트리거를 제한하는 필터링을 포함할 수 있습니다.

| 필터 | 설명 |
| ------- | ----------- |
| 활동 기록 | 하나 이상의 선택한 항목을 사용하여 평가되는 조건에 따른 활동 |
| Brand Concierge | [!DNL Brand Concierge]과(와) 관련된 리드에 대한 활동입니다. |
| 회사 속성 | 다음을 포함한 회사/계정 프로필의 속성: <li>[!UICONTROL 연간 매출] <li>[!UICONTROL 회사 이름] <li>[!UICONTROL 청구 국가] <li>[!UICONTROL 업계] <li>[!UICONTROL 직원 수] <li>[!UICONTROL SIC 코드] <li>[!UICONTROL 상태] |
| 의도 데이터 | 개인 프로필과 연관된 의도 데이터를 기반으로 하는 속성입니다. |
| 기회 | 다음을 포함하여 개인 프로필과 연관된 기회를 기반으로 하는 상태 및 속성. <li>[!UICONTROL 기회가 있음] <li>[!UICONTROL 기회 수] <li>[!UICONTROL 총 영업 기회 금액] <li>[!UICONTROL 영업 기회에 추가됨] <li>[!UICONTROL 영업 기회에서 제거됨] |
| 개인 속성 | 다음을 포함한 B2B 개인 프로필의 속성: <li>[!UICONTROL 구/군/시] <li>[!UICONTROL 국가] <li>[!UICONTROL 생년월일] <li>[!UICONTROL 전자 메일 주소] <li>[!UICONTROL 전자 메일이 잘못됨] <li>[!UICONTROL 전자 메일 일시 중단] <li>[!UICONTROL 이름] <li>[!UICONTROL 상태 지역 유추] <li>[!UICONTROL 직책] <li>[!UICONTROL 성] <li>[!UICONTROL 휴대폰 번호] <li>[!UICONTROL 개인 참여 점수] <li>[!UICONTROL 전화 번호] <li>[!UICONTROL 우편 번호] <li>[!UICONTROL 상태] <li>[!UICONTROL 구독 취소됨] <li>[!UICONTROL 구독 취소 이유] |
| 판매 앱 | [!DNL Sales Qualifier] 또는 [!DNL Marketo Sales Insights]과(와) 관련된 잠재 고객 활동. |
| 특수 필터 | 사전 정의된 범주에 속하지 않는 필터링 속성으로, 사용자 지정 또는 기타 필터 기준을 유연하게 해 줍니다. |

>[!BEGINSHADEBOX]

**필터에 대해 지원되는 Marketo Engage 활동**

트리거된 이벤트를 필터링할 때 [!DNL Marketo Optimizer]은(는) 데이터 소스로 연결된 [!DNL Marketo Engage] 인스턴스의 활동을 지원합니다.

>[!NOTE]
>
>데이터 원본으로 [!DNL Marketo Engage] 인스턴스는 하나만 있을 수 있으며 [!DNL Marketo Optimizer] 인스턴스를 프로비저닝할 때 미리 구성되어 있습니다.

다음 [!DNL Marketo Engage]개 활동에 대해 이벤트 필터를 빌드할 수 있습니다.

* **[!UICONTROL Marketo Engage 양식을 채움]** - 오래되지 않은 활동 로그의 어느 시점에서든 특정 [!DNL Marketo Engage] 양식을 완료한 잠재 고객과 일치합니다.
* **[!UICONTROL 방문한 Marketo Engage 웹 페이지]** - 웹 사이트 또는 [!DNL Marketo Engage] 랜딩 페이지에서 특정 URL을 본 리드와 일치합니다. 사이트에 설치된 Munchkin 추적 코드를 직접 사용합니다.
* **[!UICONTROL Marketo Engage 웹 페이지에서 링크를 클릭함]** - 추적된 페이지에서 특정 링크 또는 자산을 클릭한 리드와 일치합니다.
* **[!UICONTROL Marketo Engage 전자 메일을 보냈습니다]** - 하드 바운스 또는 서버 수락 전 배포 작업을 고려하여 [!DNL Marketo Engage]에서 특정 전자 메일을 보내려고 시도한 잠재 고객과 일치합니다.
* **[!UICONTROL Marketo Engage 전자 메일이 전달되었습니다]** - MX(메일 서버)가 [!DNL Marketo Engage] 전송 서버에 성공 응답(250 OK 메시지)을 반환하는 리드와 일치합니다.
* **[!UICONTROL 반송된 Marketo Engage 이메일]** - 특정 이메일 전송 또는 일정 기간 내에 하드 바운스(영구 게재 실패)가 발생한 리드와 일치합니다.
* **[!UICONTROL Marketo Engage 전자 메일이 소프트 바운스됨]** - 영구적인 하드 바운스가 아닌 임시 게재 실패(전체 받은 편지함 또는 오프라인 서버 등)가 발생한 리드와 일치합니다.
* **[!UICONTROL Marketo Engage 이메일 구독 취소됨]** - 비운영 마케팅 이메일을 옵트아웃한 잠재 고객과 일치합니다. 이 경우 [!DNL Marketo Engage]이(가) 잠재 고객의 `Unsubscribed` 필드 값을 `true`(으)로 자동 업데이트하여 향후 표준 전자 메일 전송에서 제외합니다.
* **[!UICONTROL Marketo Engage 이메일을 열었습니다]** - 추적된 [!DNL Marketo Engage] 이메일을 연 리드와 일치합니다.
* **[!UICONTROL Marketo Engage 전자 메일에서 링크를 클릭함]** - [!DNL Marketo Engage] 전자 메일 내에서 링크(또는 특정 링크)를 클릭한 리드와 일치합니다.

>[!ENDSHADEBOX]

## 이벤트 노드 추가 {#add-event-node}

1. 여정 캔버스로 이동합니다.

1. 경로에서 더하기(**+**) 아이콘을 클릭하고 **[!UICONTROL 이벤트 수신]**&#x200B;을 선택합니다.

   ![여정 경로에서 추가 아이콘 클릭](./assets/person-journey-canvas-add-node.png){width="200"}

1. 오른쪽의 노드 속성에서 **[!UICONTROL 이벤트 조건 추가]**&#x200B;를 클릭합니다.

1. _[!UICONTROL 이벤트 편집]_ 대화 상자에서 이벤트를 추가하고 트리거에 대해 일치시킬 제약 조건을 설정합니다.

   이벤트 트리거를 빌더 공간으로 끌어서 놓고 정의를 설정합니다. 이벤트 일치를 구체화하는 데 사용할 각 제약 조건에 대해 **[!UICONTROL 제약 조건 추가]**&#x200B;를 클릭합니다.

   ![이벤트 편집 - 이벤트 트리거](./assets/edit-event-triggers.png){width="700" zoomable="yes"}

   일치시킬 여러 이벤트를 추가할 수 있습니다. 첫 번째 자격 이벤트는 여정에서 개인 프로필을 앞으로 진행합니다.

1. (선택 사항) **[!UICONTROL 필터]** 탭을 선택하고 트리거에 대한 필터링 기준을 추가합니다.

   필터를 빌더 공간으로 끌어서 놓고 정의를 설정합니다. 필터 일치를 구체화하는 데 사용할 각 제약 조건에 대해 **[!UICONTROL 제약 조건 추가]**&#x200B;를 클릭합니다.

   ![이벤트 편집 - 이벤트 필터링](./assets/edit-event-filters.png){width="700" zoomable="yes"}

1. **[!UICONTROL 저장]**&#x200B;을 클릭합니다.

   언제든지 **[!UICONTROL 이벤트 편집]**&#x200B;을 클릭하여 노드의 이벤트 조건을 변경할 수 있습니다.

1. 필요한 경우 **[!UICONTROL 시간 초과]** 옵션을 설정하여 이벤트를 수신할 기간을 제한하십시오.

   >[!NOTE]
   >
   >다른 노드를 추가할 수 있는 시간 제한 경로를 정의하지 않는 한 시간 제한 후 여정이 종료됩니다.

   **[!UICONTROL 시간 초과]** 옵션을 활성화하고 이벤트가 시간 초과되기 전에 발생할 때까지 여정이 대기하는 기간을 선택하십시오.

   ![이벤트 여정 수신 노드에 대해 시간 제한 옵션이 활성화됨](./assets/person-journey-event-node-timeout.png){width="550" zoomable="yes"}

   여기서 경로를 종료하거나 다른 경로를 설정하여 다른 작업을 수행할 수 있습니다. 여정에서 이벤트가 발생하지 않을 때 프로필에 적용할 수 있는 작업 및 이벤트를 추가할 수 있는 새 경로를 만들려면 **[!UICONTROL 시간 제한 경로 설정]** 확인란을 선택하십시오.
