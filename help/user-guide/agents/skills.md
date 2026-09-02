---
title: 동료 기술
description: Marketo Optimizer에서 프로그램, 여정, 대상, 채점, 콘텐츠 및 전송 시간 최적화를 위한 패키지화된 워크플로우인 CX Enterprise Coworker 기술을 검토합니다.
source-git-commit: ef30aa7a901c18c7b9b0919d537ad59db9a6c481
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 5%

---

# 동료 기술

_스킬_&#x200B;은(는) Coworker가 실행 방법을 알고 있는 패키지된 워크플로우입니다. `/` 메뉴와 자연어 요청 모두의 뒤에 기본 요소가 있습니다. 각 스킬은 단계별 지침 및 한 작업에 필요한 특정 도구(예: &quot;여정 게시&quot;, &quot;두 사람 목록 비교&quot;, &quot;채점 모델 구축&quot;)를 번들로 제공합니다.

>[!NOTE]
>
>각 스킬은 해당 스킬이 [!DNL Marketo Optimizer] 또는 [!DNL Marketo Engage] 상태(**쓰기**)를 변경하는지, 쿼리/분석/생성(**읽기**)만 하는지 또는 동일한 쿼리 + 돌연변이 함수(**읽기+쓰기**)를 가지는지에 따라 분류됩니다.

## 프로그램 및 계획 {#programs-planning}

| 스킬 | 기능 | 액세스 | 제품 표면 | 영향 / 데이터 흐름 |
|---|---|---|---|---|
| `falco-program-creation` | 프로그램, 하위 폴더, 토큰, 목록, 여정 등 전체 [!DNL Marketo Optimizer] 프로그램 만들기. <p>_[개요에서 프로그램 만들기](./program-from-brief.md)_&#x200B;를 참조하세요. | 쓰기 | [!DNL Marketo Optimizer] | [!DNL Marketo Optimizer]을(를) 읽고 씁니다. |
| `adapt-program` | [!DNL Marketo Optimizer] 적응을 위해 [!DNL Marketo Engage] 프로그램에서 마이그레이션 스토리를 생성합니다. | 읽기 | [!DNL Marketo Optimizer] | 읽기 [!DNL Marketo Engage], 쓰기 [!DNL Marketo Optimizer] |
| `folder-creation` | 자산 트리에 조직 폴더를 만듭니다. | 쓰기 | [!DNL Marketo Optimizer] | 읽기 + 쓰기 [!DNL Marketo Optimizer] |
| `program-creation` *(프로그램 빌드)* | 캠페인 개요에서 Marketo 프로그램을 만듭니다. | 쓰기 | [!DNL Marketo Engage] | 읽기 + 쓰기 [!DNL Marketo Engage] |
| `program-planning` *(플랜 캠페인)* | 브리프를 설정/구현 문서로 변환합니다. | 읽기 | [!DNL Marketo Engage] | [!DNL Marketo Engage] 읽기 |
| `program-qa` *(프로그램 유효성 검사)* | 프로그램 검증/감사(규칙 전용, 테스트 계획 또는 개요) | 읽기 | [!DNL Marketo Engage] | [!DNL Marketo Engage] 읽기 |

## 여정 {#journeys}

| 스킬 | 기능 | 액세스 | 제품 | 백엔드(데이터 흐름) |
|---|---|---|---|---|
| `journey-creation` | 자연어에서 개인 여정을 만들고 편집합니다. | 쓰기 | [!DNL Marketo Optimizer] | 읽기 + 쓰기 [!DNL Marketo Optimizer] |
| `journey-edit-dates` | 게시하지 않고 여정의 시작/종료 날짜를 변경합니다. | 쓰기 | [!DNL Marketo Optimizer] | 읽기 + 쓰기 [!DNL Marketo Optimizer] |
| `journey-publish` | 사람 여정 게시/실행/예약 | 쓰기 | [!DNL Marketo Optimizer] | 읽기 + 쓰기 [!DNL Marketo Optimizer] |
| `journey-stop` | 여정 중단, 닫기, 중지, 중지 또는 종료 | 쓰기 | [!DNL Marketo Optimizer] | 읽기 + 쓰기 [!DNL Marketo Optimizer] |
| `journey-reentry` | 재입력 구성: 허용/허용 안 함, 쿨다운, 최대 항목 수. | 쓰기 | [!DNL Marketo Optimizer] | 읽기 + 쓰기 [!DNL Marketo Optimizer] |
| `journey-trafficcontrol` | 프로필 라우팅을 보여주는 트래픽 제어 시뮬레이션을 실행합니다. | 읽기 | [!DNL Marketo Optimizer] | 읽기 [!DNL Marketo Optimizer]&#x200B;(시뮬레이션) |
| `journey-observability` | 진행 상황 디버그/모니터링 — 경로, 타이밍, 분할, 정지, 유지 | 읽기 | [!DNL Marketo Optimizer] | [!DNL Marketo Optimizer] + [!DNL Marketo Engage]을(를) 읽습니다(정적 목록 확인). |

## 대상자 및 사람 {#audiences-people}

| 스킬 | 기능 | 액세스 | 제품 | 백엔드(데이터 흐름) |
|---|---|---|---|---|
| `audience-creation` | [!DNL Marketo Engage] 스마트 목록을 조정하거나 사람 목록을 만들거나 규칙을 추가/업데이트합니다. <p>_[프로그램에 대한 대상 만들기](./audience-creation.md)_&#x200B;를 참조하십시오. | 쓰기 | [!DNL Marketo Optimizer] | 읽기 [!DNL Marketo Engage] + 읽기/쓰기 [!DNL Marketo Optimizer]. |
| `people-list-comparison` | 두 사람 목록을 비교하고 중복되는 구성원을 표시합니다. | 읽기 | [!DNL Marketo Optimizer] | [!DNL Marketo Optimizer] 읽기 |
| `import-leads` | CSV 데이터 품질을 검사하고 [!DNL Marketo Engage]에 가져오기를 커밋합니다. | 읽기+쓰기 | 모두 | 읽기 + 쓰기 [!DNL Marketo Engage] |
| `lead-investigation` *(리드 조사)* | 잠재 고객의 활동, 점수, 자격, 라이프사이클을 조사합니다. | 읽기 | [!DNL Marketo Engage] | [!DNL Marketo Engage] 읽기 |

## 컨텐츠 및 채널 {#content-channels}

| 스킬 | 기능 | 액세스 | 제품 | 백엔드(데이터 흐름) |
|---|---|---|---|---|
| `content-personalization` | 템플릿을 검색/미리 보고 컨텐츠를 편집하거나 변형을 생성할 수 있습니다. | 읽기+쓰기 | [!DNL Marketo Optimizer] | [!DNL Marketo Optimizer]을(를) 읽고 씁니다. _[사용자별 전자 메일 콘텐츠 개인화](./personalize-content.md)_&#x200B;를 참조하십시오. |
| `asset-tokens` | 프로그램/폴더/여정에 대한 전체 토큰 CRUD. | 읽기+쓰기 | [!DNL Marketo Optimizer] | 읽기 + 쓰기 [!DNL Marketo Optimizer] |
| `fcs-channels` | 채널 조회 및 CRUD + 게시/중지/삭제. | 읽기+쓰기 | [!DNL Marketo Optimizer] | 읽기 + 쓰기 [!DNL Marketo Optimizer] |

## 채점 및 신호 {#scoring-signals}

| 스킬 | 기능 | 액세스 | 제품 | 백엔드(데이터 흐름) |
|---|---|---|---|---|
| `scoring-studio` | 채점 모델을 나열/가져오고 빌드/게시합니다. <p>_[사용자 지정 점수 모델 만들기](./lead-scoring-model.md)_&#x200B;를 참조하십시오. | 읽기+쓰기 | [!DNL Marketo Optimizer] | [!DNL Marketo Optimizer]&#x200B;(채점 서비스)을(를) 읽고 씁니다; [!DNL Marketo Engage] 리드 필드/활동 유형을 읽습니다. |
| `engagementconfiguration` | 참여 구성 및 가중치 편집/업데이트 표시 | 읽기+쓰기 | [!DNL Marketo Optimizer] | 읽기 + 쓰기 [!DNL Marketo Optimizer] |
| `intentconfiguration` | 의도 구성 및 가중치 설정/업데이트. | 읽기+쓰기 | [!DNL Marketo Optimizer] | 읽기 + 쓰기 [!DNL Marketo Optimizer] |
| `intent-query` | 개인/세그먼트/목록별로 의도 점수를 쿼리하고 설명합니다. | 읽기 | [!DNL Marketo Optimizer] | [!DNL Marketo Optimizer] 읽기 |

## 전송 시간 최적화 {#sto}

| 스킬 | 기능 | 액세스 | 제품 | 백엔드(데이터 흐름) |
|---|---|---|---|---|
| `send-time-optimization` | 이메일 노드에서 STO 상태 및 활성화/비활성화로 확인합니다. | 읽기+쓰기 | [!DNL Marketo Optimizer] | 읽기 + 쓰기 [!DNL Marketo Optimizer] |
| `send-time-report` | STO 성능 보고서를 가져오거나 표시합니다. | 읽기 | [!DNL Marketo Optimizer] | [!DNL Marketo Optimizer] 읽기 |

## 지식 {#knowledge}

| 스킬 | 기능 | 액세스 | 제품 | 백엔드(데이터 흐름) |
|---|---|---|---|---|
| `product-knowledge` | Experience League의 [!DNL Marketo Optimizer] 설명서에서 방법/개념 질문에 답변합니다. | 읽기 | 모두 | 외부 문서 읽기 — 제품 데이터 없음 |

## 크로스 백엔드 {#cross-backend}

이러한 기술은 두 개 이상의 백엔드에 걸쳐 있습니다.

- **`adapt-program`** — `gather_program_assets`이(가) [!DNL Marketo Engage]&#x200B;(`get_program`, `get_smart_campaign`, `list_emails`)을(를) 읽은 다음 `falcomcp_create_journey` — 클래식 크로스 백엔드를 통해 씁니다.
- **`audience-creation`** — [!DNL Marketo Engage]개의 스마트 목록(`get_smart_list`/`get_smart_campaign`)을 읽은 다음 [!DNL Marketo Optimizer]개의 사용자 목록을 씁니다.
- **`journey-observability`** — [!DNL Marketo Optimizer] 읽기와 `check_lead_in_marketo_static_list` [!DNL Marketo Engage] 읽기를 더한 값입니다.
- **`scoring-studio`** — [!DNL Marketo Optimizer] 채점 서비스와 함께 [!DNL Marketo Engage] 리드 필드/활동 유형을 읽습니다.

모든 `falco-mcp_*` 및 여정/토큰/채점/STO/FCS 도구는 [!DNL Marketo Optimizer] 서비스를 히트하고 CSV/프로그램/리드 도구는 [!DNL Marketo Engage]을 히트합니다.
