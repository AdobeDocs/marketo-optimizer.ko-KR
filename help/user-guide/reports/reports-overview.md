---
title: 보고서
description: 보고서 섹션, 내보내기 및 예약 옵션, 날짜 범위를 변경하는 방법을 포함하여 Adobe Marketo Optimizer의 보고서 탭을 이해합니다.
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
source-git-commit: 6e919a66af259ea1f5facf7f5c3e811d76101e85
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 2%
---

# 보고서

[!UICONTROL 보고서] 탭에서는 여정 참여, 전자 메일 성능 및 웹 활동을 포함하여 [!DNL Adobe Marketo Optimizer]의 성능 통찰력을 제공합니다. 왼쪽 탐색에서 **[!UICONTROL 보고서]**&#x200B;를 선택하여 엽니다.

각 보고서는 [!DNL Adobe Customer Journey Analytics]에 작성되고 [!DNL Marketo Optimizer]에 직접 포함됩니다. _목록_ 아이콘( ![목록 아이콘](../assets/do-not-localize/icon-table-of-contents.svg) )을 클릭하여 왼쪽의 **[!UICONTROL 목차]** 패널을 사용하여 섹션 사이를 이동합니다.

![개인 여정 개요, 참여, 전자 메일 참여 및 웹 참여 섹션을 나열하는 보고서 페이지](./assets/reports-table-of-contents.png){width="800" zoomable="yes"}

## 보고서 섹션 {#report-sections}

[!UICONTROL 보고서] 탭은 미리 작성된 보고서를 네 개의 섹션으로 구성합니다. 각 섹션에는 다운로드 가능한 항목이 하나 이상 있으며, 지표 및 시각화에 대한 세부 정보가 포함된 고유한 설명서 페이지가 있습니다.

| 섹션 | 다운로드 가능한 항목 | 보고서 페이지 |
| --- | --- | --- |
| [!UICONTROL 개인 여정 개요] | 활성 여정 수 | [개인 여정 개요 보고서](./person-journey-overview-report.md) |
| [!UICONTROL 참여] | 사람에 의한 참여, 시간 경과에 따른 개인 참여 | [참여도 보고](./engagement-report.md) |
| [!UICONTROL 전자 메일 참여] | 이메일 참여 | [전자 메일 참여 보고서](./email-engagement-report.md) |
| [!UICONTROL 웹 참여] | 상위 페이지 조회수 | [웹 참여 보고서](./web-engagement-report.md) |

## 개별 레코드 보고서 {#individual-record-reports}

일부 보고서는 섹션 전체 보기 대신 단일 레코드에 중점을 두며 애플리케이션의 다른 영역에서 액세스됩니다.

* 이메일 전송 시간 최적화 성능을 위해 [!UICONTROL 동료] 채팅 인터페이스에서 보고서를 엽니다. 단계는 [이메일 전송 시간 최적화](../marketing/email-send-time-optimization.md#reporting)를 참조하십시오.
* 단일 여정을 통해 진행 중인 개인의 경우 해당 여정 내에서 [개인 여정 개별 보고서](./person-journey-individual-report.md)를 여십시오.

## 보고서 내보내기 {#export-a-report}

보고서 페이지의 맨 위에서 **[!UICONTROL 공유]**&#x200B;를 선택하여 해당 데이터를 내보내거나 배달 일정을 예약합니다.

![CSV 다운로드, PDF 다운로드, 내보내기 예약 및 일정 관리 옵션이 있는 메뉴 공유](./assets/reports-share-menu.png){width="500"}

* **[!UICONTROL CSV 다운로드]** - 보고서 데이터를 일반 텍스트 값으로 내보냅니다.

* **[!UICONTROL PDF 다운로드]** - 보고서에 표시된 모든 테이블 및 시각화를 PDF 파일로 내보냅니다.

* **[!UICONTROL 내보내기 예약]** - 매주 또는 매월 CSV 또는 PDF 파일로 제공되는 보고서의 반복 내보내기를 설정합니다.

* **[!UICONTROL 일정 관리]** - 기존 예약된 내보내기를 검토하고 관리합니다. 옵션은 조직의 제한에 대해 사용된 일정(예: `3/10`)의 실행 수를 표시합니다.

>[!NOTE]
>
>조직은 모든 보고서에서 주별 또는 월별 주기로 최대 10개의 예약된 내보내기를 가질 수 있습니다. 관리자가 아닌 경우 예약된 자체 내보내기만 관리할 수 있습니다. 관리자는 조직의 모든 예약된 내보내기를 보고 관리할 수 있습니다.

## [!DNL Customer Journey Analytics]에서 보고서 분석 {#analyze-a-report-in-cja}

>[!AVAILABILITY]
>
>조직에서 [!DNL Adobe Customer Journey Analytics]에 대한 라이선스를 보유하고 사용자에게 제품 프로필이 할당된 경우 이 기능을 사용할 수 있습니다.

포함된 보고서에서 사용할 수 있는 항목 외에 사용자 지정 시각화를 만들 수 있는 보고서 섹션에서 **[!UICONTROL CJA에서 분석]**&#x200B;을 선택하여 [!DNL Adobe Customer Journey Analytics] Workspace에서 엽니다.

## 날짜 범위 변경 {#change-the-date-range}

각 보고서 섹션에는 섹션의 오른쪽 상단 모서리에 표시되는 특정 날짜 범위에 대한 데이터가 표시됩니다. 날짜 범위 필드를 클릭하여 날짜 선택 도구를 표시하고 날짜 범위를 선택합니다. 다른 사전 설정을 선택하거나 사용자 지정 범위를 정의할 수 있습니다.

![2개월 일정, 시작 및 종료 날짜 필드 및 사전 설정 옵션이 있는 날짜 범위 선택기](./assets/reports-date-range.png){width="600"}
