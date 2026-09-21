---
title: 이메일 참여 보고서
description: 이메일 및 여정 별로 이메일 전달성 및 참여 지표를 보여 주는 Adobe Marketo Optimizer의 이메일 참여 보고서에 대해 알아봅니다.
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
source-git-commit: 6e919a66af259ea1f5facf7f5c3e811d76101e85
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 0%
---

# 이메일 참여 보고서

<!-- SPHR-32511: Filter by Program, Filter by Audience, and the program data point for the email performance table are not documented here pending delivery. -->

[!UICONTROL 전자 메일 참여] 보고서를 사용하여 전자 메일 및 여정으로 분류된 인스턴스 전체의 전자 메일 전달성 및 참여 성능을 검토하십시오.

보고서를 보려면(_T):_

1. 왼쪽 탐색에서 **[!UICONTROL 보고서]**&#x200B;를 선택합니다.
1. _목록_ 아이콘( ![목록 아이콘](../assets/do-not-localize/icon-table-of-contents.svg))을 클릭하고 _[!UICONTROL 목차]_ 패널에서 **[!UICONTROL 전자 메일 참여]**&#x200B;를 선택합니다.

![여정 이름 및 사용자 필터, 최근 30일 날짜 범위 및 전자 메일 활동 지표 표를 포함한 전자 메일 참여 보고서.](./assets/reports-email-engagement.png){width="700" zoomable="yes"}

다른 보고서 섹션에서 사용할 수 있는 것과 동일한 날짜 범위 선택기를 사용하여 [날짜 범위를 변경](./reports-overview.md#change-the-date-range)할 수 있습니다.

모든 보고서 데이터의 내보내기를 다운로드하거나 예약하려면 보고서 맨 위에서 **[!UICONTROL 공유]**&#x200B;를 선택하십시오. 보고서 개요에서 [_보고서 내보내기_](./reports-overview.md#export-a-report)&#x200B;를 참조하십시오.

## 보고서 테이블 {#report-table}

[!UICONTROL 전자 메일 참여] 보고서에는 각 전자 메일에 대해 다음 행 차원이 있는 하나의 행이 표시됩니다.

* **[!UICONTROL 전자 메일 이름]** - 전자 메일 이름입니다.
* **[!UICONTROL 여정 이름]** - 전자 메일을 보낸 여정의 이름입니다.

지표 열은 **[!UICONTROL 전자 메일 활동]** 아래에 그룹화되어 있습니다.

| 열 | 설명 |
| --- | --- |
| [!UICONTROL 전송됨] | 보낸 이메일 수. |
| [!UICONTROL 배달됨] | 게재된 이메일 수. |
| [!UICONTROL % 전달됨] | 게재된 이메일 중 게재된 이메일의 비율. |
| [!UICONTROL 하드 바운스됨] | 영구적으로 배달되지 않은 이메일 수입니다. |
| [!UICONTROL 소프트 바운스] | 일시적으로 게재에 실패한 이메일 수입니다. |
| [!UICONTROL 열림] | 수신자가 이메일을 연 횟수. |
| [!UICONTROL % 열림] | 열람한 게재된 이메일 비율. |
| [!UICONTROL 클릭됨] | 수신자가 이메일의 링크를 클릭한 횟수입니다. |
| [!UICONTROL % 클릭됨] | 클릭을 받은 게재된 이메일의 비율입니다. |
| [!UICONTROL 클릭하여 열기 비율] | 클릭을 받은 열린 이메일의 비율입니다. |
| [!UICONTROL 구독 취소됨] | 이메일 구독을 취소한 수신자 수입니다. |
| [!UICONTROL % 구독 취소됨] | 구독을 취소한 게재된 이메일 비율입니다. |

## 필터 {#filters}

필터를 사용하여 보고서의 범위를 특정 여정 또는 담당자로 좁힐 수 있습니다. 모든 필터를 지우고 기본 보기로 돌아가려면 **[!UICONTROL 모두 재설정]**&#x200B;을 선택하세요.

* **[!UICONTROL 여정 이름(이벤트)]** - 전자 메일을 보낸 여정으로 필터링합니다. 기본값은 [!UICONTROL 필터 없음]입니다.
* **[!UICONTROL 담당자(이벤트)]** - 전자 메일과 연결된 담당자로 필터링합니다. 기본값은 [!UICONTROL 필터 없음]입니다.