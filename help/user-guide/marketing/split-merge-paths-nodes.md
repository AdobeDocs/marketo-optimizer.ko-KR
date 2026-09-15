---
title: 경로 노드 분할 및 병합
description: 개인 여정에서 분할 및 병합 경로 노드를 사용하여 정의된 조건을 기반으로 개인을 개별 경로로 세그먼트화한 다음 공통 지점 다운스트림에서 다시 통합하는 방법에 대해 알아봅니다.
TQID: 'https://experienceleague.adobe.com/XMN7lgb77bFlJkNXrmPf9ZSCV-GgIuybtr-O3AsqT2U'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
source-git-commit: 9d9f2ae1aafc5ffdc2bcc6546c7eb2ddcbaa4ab2
workflow-type: tm+mt
source-wordcount: '1064'
ht-degree: 6%
---
# 경로 노드 분할 및 병합

분할 및 병합 경로 노드를 사용자 여정에 사용하여 정의한 조건에 따라 사용자를 개별 경로로 분할한 다음 여정이 계속 진행될 수 있도록 이러한 경로를 병합합니다. 분할 경로를 사용하면 작업 및 이벤트를 특정 대상 세그먼트에 맞게 조정할 수 있으며, 병합 경로는 이러한 세그먼트를 공통 지점에서 결합합니다.

## 경로 노드 분할

정의한 조건에 따라 사람들을 세그먼트화하려면 분할 노드를 사용하십시오. 조건에 따라 대상 목록의 경로를 만들고, 세그먼트에 대한 작업 및 이벤트 노드로 각 경로를 정의한 다음, 경로를 결합하고 여정을 계속합니다.

분할된 경로 노드는 사람 필터에 따라 하나 이상의 분할된 경로를 정의합니다.

<!-- A split based on a people filter is automatically closed with a merge paths node so that all people can move forward to the next step. Split by people paths can include only people actions. These paths cannot be split again and automatically join back. _not currently true_ -->

_**분할 경로 노드가 작동하는 방식**_

* 각 경로의 평가는 위에서 아래로 내려옵니다. 한 사람이 첫 번째 및 두 번째 경로와 일치하는 경우 첫 번째 경로만 따라 진행합니다.
* 노드는 정의된 세그먼트/경로 중 하나와 일치하지 않는 사용자에 대해 작업 또는 이벤트를 추가할 수 있는 _기타 사용자_ 경로의 정의를 지원합니다.

### 일치하는 개인 필터

노드에 대해 정의하는 각 경로에 대해 다음 필터 유형을 사용하여 하나 이상의 조건에 따라 사람을 일치시킵니다.

| 필터 | 설명 |
| ------- | ----------- |
| 활동 기록 | 하나 이상의 선택한 항목을 사용하여 평가되는 조건에 따른 활동 |
| Brand Concierge | [!DNL Brand Concierge]과(와) 관련된 리드에 대한 활동입니다. |
| 회사 속성 | 다음을 포함한 회사/계정 프로필의 속성: <li>연간 수익 <li>회사 이름 <li>청구지 국가 <li>업종 <li>직원 수 <li>SIC 코드 <li>주 |
| 의도 데이터 | 개인 프로필과 연관된 의도 데이터를 기반으로 하는 속성입니다. |
| 기회 | 개인 프로필과 연관된 기회를 기반으로 하는 속성입니다. |
| 개인 속성 | 다음을 포함한 B2B 개인 프로필의 속성: <li>도시 <li>국가 <li>생년월일 <li>이메일 주소 <li>잘못된 이메일 <li>이메일 중단됨 <li>이름 <li>추정 주 지역<li>직위 <li>성 <li>휴대폰 번호 <li>개인 참여 점수 <li>전화번호 <li>우편번호 <li>주 <li>구독 취소 <li>구독 취소 이유 |
| 판매 앱 | [!DNL Sales Qualifier] 또는 [!DNL Marketo Sales Insights]과(와) 관련된 잠재 고객 활동. |
| 특수 필터 | 사전 정의된 범주에 속하지 않는 필터링 속성으로, 사용자 지정 또는 기타 필터 기준을 유연하게 해 줍니다. |

>[!BEGINSHADEBOX]

**조건 필터에 대해 지원되는 [!DNL Marketo Optimizer] 활동**

경로 조건의 경우 [!DNL Marketo Optimizer]은(는) 데이터 소스로 연결된 [!DNL Marketo Engage] 인스턴스의 활동을 지원합니다.

>[!NOTE]
>
>데이터 원본으로 [!DNL Marketo Engage] 인스턴스는 하나만 있을 수 있으며 [!DNL Marketo Optimizer] 인스턴스를 프로비저닝할 때 미리 구성되어 있습니다.

다음 [!DNL Marketo Engage]개 활동에 대해 조건을 만들 수 있습니다.

* [!UICONTROL Marketo Engage 양식을 채움] - 오래되지 않은 활동 로그의 어느 시점에서든 특정 [!DNL Marketo Engage] 양식을 완료한 잠재 고객과 일치합니다.
* [!UICONTROL 방문한 Marketo Engage 웹 페이지] - 웹 사이트 또는 [!DNL Marketo Engage] 랜딩 페이지에서 특정 URL을 본 리드와 일치합니다. 사이트에 설치된 Munchkin 추적 코드를 사용하여 직접 작동합니다.
* [!UICONTROL Marketo Engage 웹 페이지에서 링크를 클릭함] - 추적된 페이지에서 특정 링크 또는 자산을 클릭한 리드와 일치합니다.
* [!UICONTROL Marketo Engage 전자 메일을 보냈습니다] - 하드 바운스 또는 서버 수락 전 배포 작업을 고려하여 [!DNL Marketo Engage]에서 특정 전자 메일을 보내려고 시도한 잠재 고객과 일치합니다.
* [!UICONTROL Marketo Engage 전자 메일이 전달되었습니다] - MX(메일 서버)가 [!DNL Marketo Engage] 전송 서버에 성공 응답(250 OK 메시지)을 반환하는 리드와 일치합니다.
* [!UICONTROL 반송된 Marketo Engage 이메일] - 특정 이메일 전송 또는 일정 기간 내에 하드 바운스(영구 게재 실패)가 발생한 리드에 대해 일치합니다.
* [!UICONTROL Marketo Engage 전자 메일이 소프트 바운스됨] - 영구적인 하드 바운스가 아닌 임시 게재 실패(전체 받은 편지함 또는 오프라인 서버 등)가 발생한 리드와 일치합니다.
* [!UICONTROL Marketo Engage 이메일 구독 취소됨] - 비운영 마케팅 이메일을 옵트아웃한 잠재 고객과 일치합니다. 이 경우 [!DNL Marketo Engage]이(가) 잠재 고객의 `Unsubscribed` 필드 값을 `true`(으)로 자동 업데이트하여 향후 표준 전자 메일 전송에서 제외합니다.
* [!UICONTROL Marketo Engage 이메일을 열었습니다] - 추적된 [!DNL Marketo Engage] 이메일을 연 리드와 일치합니다.
* [!UICONTROL Marketo Engage 전자 메일에서 링크를 클릭함] - [!DNL Marketo Engage] 전자 메일 내에서 링크(또는 특정 링크)를 클릭한 리드와 일치합니다.

>[!ENDSHADEBOX]

### 분할 경로 노드 추가

1. 여정 캔버스로 이동합니다.

1. 경로에서 더하기(**+**) 아이콘을 클릭하고 **[!UICONTROL 경로 분할]**&#x200B;을 선택합니다.

   ![여정 경로에서 추가 아이콘 클릭](./assets/person-journey-canvas-add-node.png){width="200"}

1. _[!UICONTROL 경로 1]_&#x200B;에 적용할 수 있는 조건을 정의하려면 **[!UICONTROL 조건 적용]**&#x200B;을 클릭하십시오.

1. 분할 경로를 정의하려면 조건 편집기에 필터를 하나 이상 추가합니다.

   * 왼쪽 탐색에서 사람 필터를 끌어다 놓고 일치 정의를 완료합니다.

   * 필터 일치를 구체화하는 데 사용할 각 제약 조건에 대해 **[!UICONTROL 제약 조건 추가]**&#x200B;를 클릭합니다.

     ![경로 노드 분할 - 경로 조건에 일치하는 사용자 필터](./assets/journey-node-split-conditions-people.png){width="700" zoomable="yes"}

   * 맨 위에 있는 **[!UICONTROL 필터 논리]**&#x200B;를 적용하여 조건을 구체화합니다. 모든 조건 또는 하나의 조건을 일치시키도록 선택합니다.

   * **[!UICONTROL 완료]**&#x200B;를 클릭합니다.

1. 경로를 더 추가하려면 **[!UICONTROL 경로 추가]**&#x200B;를 클릭하고 이전 단계를 반복하여 경로에 적용할 수 있는 조건을 추가합니다.

   이러한 조건을 기반으로 각 경로에 레이블을 지정하거나 기본 레이블을 사용할 수도 있습니다.

1. 필요한 경우 분할에 대해 원하는 우선 순위에 따라 경로 순서를 변경합니다.

   경로 필터링은 하향식으로 평가됩니다. 각 사용자는 일치하는 첫 번째 경로를 따라 진행합니다.

   각 경로 카드의 오른쪽 상단에 있는 위쪽 및 아래쪽 화살표를 클릭하여 경로 목록에서 위쪽 또는 아래쪽으로 이동합니다.

   <!-- ![Split path node - reorder paths](./assets/node-split-reorder-paths-people.png){width="500" zoomable="yes"} -->

1. 정의된 경로와 일치하지 않는 사람에 대한 기본 경로를 추가하려면 **[!UICONTROL 다른 사람]** 옵션을 활성화하십시오.

   이 옵션이 활성화되지 않으면 정의된 세그먼트/경로와 일치하지 않는 사람들이 분할을 지나 여정의 다음 단계로 이동합니다.

각 경로에 대해 조건이 정의된 경우 경로의 사람들에게 적용할 작업 또는 이벤트 노드를 추가할 수 있습니다.

## 경로 노드 병합

1. 여정 캔버스로 이동하고 두 개 이상의 경로가 있는 분할된 경로 노드를 찾습니다.

   각 경로에는 작업과 이벤트 노드의 조합이 있어야 합니다.

1. 이러한 경로 중 하나의 끝에 있는 더하기(**+**) 아이콘을 클릭하고 표시된 옵션에서 **[!UICONTROL 경로 병합]**&#x200B;을 선택합니다.

1. 오른쪽의 노드 속성에서 병합할 경로를 선택합니다.

   <!-- ![Journey node - merge paths](./assets/node-merge-select-paths.png){width="600" zoomable="yes"} -->

   이때 선택한 경로의 사람들이 여정을 계속 진행할 수 있는 단일 경로로 결합되도록 경로가 병합됩니다.

1. 필요한 경우 경로 병합 노드 속성으로 다시 이동하고 제거할 경로에 대한 확인란을 선택 취소하여 경로 병합을 취소할 수 있습니다.