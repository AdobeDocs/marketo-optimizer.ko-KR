---
title: Adobe Marketo Optimizer의 CX Enterprise Coworker 개요
description: CX Enterprise Coworker이 Marketo Optimizer 기술을 사용하여 프로그램을 제작 및 조정하고, AI 의사 결정 준비 상태를 확인하고, MCP 도구를 호출하는 방법에 대해 알아봅니다.
autotag-review: '2026-11-24T22:43:00.917Z'
TQID: https://experienceleague.adobe.com/V4Kww-NcdfbFxXqWrs7mPq7UYu8AREqDgyfvlMnlURM
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 1650dadf-b034-5ac9-a309-77ad1e2f5035
    internal-label: Chat Interface
  - id: 5229c72e-d79b-574f-a03e-5c4bf48172c3
    internal-label: AI Decisioning
  - id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
    internal-label: Programs
subfeature_v2:
  - id: b9e5c7f3-be30-563c-9e41-cc8ea76e2fee
    internal-label: Skills
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
    internal-label: Artificial intelligence
source-git-commit: 418b81a0a39eca0ca7b537c76da972df7eefd09f
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 2%
---

# [!DNL Adobe Marketo Optimizer]의 [!DNL CX Enterprise Coworker] {#coworker-overview}

[!DNL CX Enterprise Coworker] 채팅은 [!DNL Adobe Marketo Optimizer]에서 작업을 완료하기 위한 대화 인터페이스입니다. 목표를 일반 언어로 설명하십시오. [!DNL Coworker]은(는) 작업을 계획하고 [!DNL Marketo Optimizer]에서 실행하고 결과를 확인한 후 승인을 위해 완료된 작업을 제공합니다.

[!DNL Coworker]은(는) [!DNL Marketo Optimizer]용으로 구축된 기술을 사용하여 새 프로그램 만들기, 기존 [!DNL Marketo Engage] 프로그램 조정, 데이터가 AI 의사 결정에 적합한지 확인 등 일반적인 마케팅 작업을 안내합니다.

[!DNL Coworker]은(는) 조직의 기존 [[!DNL Marketo Optimizer] 권한](../start/permissions-reference.md)을 준수합니다. 이미 허용된 작업만 수행할 수 있으며, 관리자는 사용자가 쓰기 액세스 권한을 보유할 때 이를 제어합니다. [!DNL Coworker]은(는) Adobe 에코시스템의 일부이며 [!DNL Marketo Optimizer]&#x200B;(으)로 제한되지 않습니다.

자세한 내용은 다음 문서를 참조하십시오.

* [[!DNL Adobe CX Enterprise Coworker] 채팅 개요](https://experienceleague.adobe.com/en/docs/coworker/content/chat/overview)
* [ [!DNL Marketo Optimizer]의 채팅 인터페이스](./chat-interface.md)
* [ [!DNL Marketo Optimizer]의 [!DNL Coworker]개 스킬](./skills.md)

## [!DNL CX Enterprise Coworker]의 [!DNL Marketo Optimizer] 스킬 {#skills}

다음의 제품별 기술을 사용하여 프로그램을 제작 및 조정하거나 데이터 준비 상태를 평가합니다.

| 스킬 | 도움이 되는 작업 | 요청 예 |
| --- | --- | --- |
| `program-creation-marketo-optimizer` | [!DNL Marketo Optimizer] 마케팅 프로그램을 처음부터 끝까지 만듭니다. [!DNL Coworker]이(가) 목표에서 빌드된 프로그램으로 안내합니다. | 캠페인 브리핑을 업로드한 다음 다음과 같이 질문하십시오. _첨부된 브리핑을 사용하여 프로그램을 만드십시오._ |
| `adapt-program-marketo-optimizer` | 기존 [!DNL Marketo Engage] 프로그램을 [!DNL Marketo Optimizer] 프로그램으로 조정, 마이그레이션 또는 변환합니다. | _Q3 엔터프라이즈 웨비나 육성 프로그램을 [!DNL Marketo Engage]에서 [!DNL Marketo Optimizer]&#x200B;(으)로 조정_ |
| `ai-decisioning-health-marketo-optimizer` | 스토리 범위, 트레이트 풍부성 및 사용자 범위를 포함하여 테넌트의 데이터가 AI 의사 결정을 위해 준비되었는지 여부를 보고합니다. | _AI 의사 결정에 사용되는 데이터는 무엇입니까?_ |

### 프로그램 생성 프롬프트 예 {#program-creation-prompt}

간단한 내용을 업로드하거나 프로그램에 대해 직접 설명하십시오. [!DNL Coworker]에서 사용할 대상, 여정, 콘텐츠 및 설정을 포함합니다.

다이어그램은 아래 예제의 프롬프트 섹션을 요약합니다. 사람들이 여정을 이동하는 순서가 아니라 요청을 구성하는 방법을 보여 줍니다.

![프로그램 만들기 프롬프트 섹션에는 프로그램 목표, 대상자, 인텐트 기반 초대를 사용한 여정, 이메일 콘텐츠, LinkedIn 활성화, 등록 처리, 사후 이벤트 후속 작업 및 설정이 있습니다.](./assets/coworker-program-creation-prompts.svg){width="800" zoomable="yes"}

각 섹션을 확장하여 예제 프롬프트를 봅니다.

+++프로그램 목표

_이메일 및 LinkedIn을 사용하여 8월 3일부터 12월 3일까지 실행되는 Experience Cloud 리더십 포럼 - AI 기반 Experience Summit이라는 B2B 마케팅 프로그램을 만듭니다. 이 행사는 오전 9시에 베이 에어리어 이노베이션 센터에서 열립니다. 여정을 즉시 시작합니다._

+++

+++대상자

_Experience Cloud에 대한 제품 의도와 참여 점수가 1보다 큰 사용자를 타깃팅합니다. 구독 취소 및 마케팅 중단 프로필을 제외합니다._

+++

+++여정

_다음 최적 경로를 사용하여 Experience Cloud의 높음, Medium 및 낮음 인텐트로 대상을 분할합니다. 각 의도 수준에 맞게 개인화된 이메일 초대를 보냅니다. 경로를 병합하고 2일을 기다립니다. 이메일 열기, 클릭 수, 콘텐츠 참여 및 등록을 확인합니다. 참여 구성원에게 안건 미리 보기를 보내고, LinkedIn에서 참여하지 않은 구성원을 활성화한 후 이틀 동안 대기하십시오. 참여 경로를 병합하고 이벤트 10일 전에 최종 등록 미리 알림을 보냅니다. 모든 전자 메일에 대해 전송 시간 최적화를 사용하도록 설정합니다._

+++

+++이메일 콘텐츠

_경영진 초대(행사 6주 전), 안건 미리 보기(행사 6주 전), 최종 등록 미리 알림(행사 10일 전)의 세 가지 전자 메일을 만듭니다. 인물 스토리, 성향 분류, 업계, 솔루션 관심사, 최근 참여 및 Experience Cloud 의도를 사용하여 관련 제목 라인, 사전 머리글, 작업 호출(내 시트 예약, 의제 보기, 등록 완료) 및 AI 개인화된 콘텐츠를 포함합니다. 초대장에는 장소 이미지가 포함되지만 안건 미리 보기에는 배너가 없습니다._

+++

+++LinkedIn

_참여가 없는 회원은 고객 경험 변환 및 AI 개인화를 촉진하는 스폰서 콘텐츠를 이용합니다._

+++

+++등록

_등록된 구성원을 초대 여정에서 즉시 종료하고 AI가 생성한 토론 주제, 개인화된 주제, 장소 세부 정보, 추천 세션 및 일정 링크가 포함된 경영진 준비 이메일을 보냅니다._

+++

+++이벤트 후

_요약, 녹음, 리소스 및 영업 자격 검토를 통해 참석자를 Experience Cloud 리더십 후속 프로그램으로 보냅니다. 노쇼 추천, 온디맨드 콘텐츠 및 향후 이벤트 초대를 보냅니다._

+++

+++설정

_my.replyToEmail을 `events@example.com`(으)로 설정하고 my.senderName을 Experience Cloud 이벤트로 설정합니다. 구/군/시, 장소, 기조 주제 및 업계 초점도 변경되는 재사용 가능한 템플릿을 사용하십시오._

+++

개요 준비에 대한 자세한 내용은 [개요에서 프로그램 만들기](./program-from-brief.md)를 참조하세요.

## 사용 사례 예시 {#use-cases}

### 데이터 준비 상태 확인 후 프로그램 만들기 {#check-readiness-create-program}

마케팅 운영 리드는 새로운 계정 기반 프로그램을 구축하기 전에 테넌트가 AI 의사 결정을 내릴 준비가 되었는지 알고 싶어합니다.

1. 스토리 범위, 트레이트 풍부성 및 성향 범위를 검토하려면 [AI 의사 결정 상태 검사](./ai-decisioning-health.md)를 실행하십시오. 예를 들어, _AI 의사 결정에 활용하는 Marketo 데이터를 보여 주십시오._
1. 보고서에서 식별한 간격을 해결합니다.
1. 캠페인 개요 업로드 및 질문: _첨부된 개요로 프로그램을 만드세요._
1. [!DNL Coworker]이(가) 결과를 표시할 때 프로그램을 검토하고 승인합니다.

결과는 결함을 식별하는 준비 보고서이며, 이어서 AI 의사 결정을 지원할 수 있는 데이터를 기반으로 구축된 프로그램이 제공됩니다.

### 기존 [!DNL Marketo Engage] 프로그램을 [!DNL Marketo Optimizer]&#x200B;(으)로 이동 {#adapt-program}

수요 생성 팀이 수동으로 다시 빌드하지 않고 [!DNL Marketo Optimizer]에서 실행되는 검증된 프로그램을 원합니다.

1. 조정할 [!DNL Marketo Engage] 프로그램의 이름을 지정합니다. 예: _Q3 엔터프라이즈 웨비나 육성 프로그램을 [!DNL Marketo Engage]에서 [!DNL Marketo Optimizer]&#x200B;(으)로 조정_
1. [!DNL Coworker]은(는) 프로그램을 [!DNL Marketo Optimizer] 구문에 매핑하고 변환되지 않는 모든 구문에 플래그를 지정합니다.
1. 결과를 검토하고 승인합니다.

그 결과는 검토를 위해 변환된 프로그램과 수동 결정이 필요한 항목 목록입니다.

## [!DNL Marketo Optimizer] MCP 도구 {#mcp-tools}

[!DNL Coworker] 스킬은 [!DNL Marketo Optimizer] MCP(모델 컨텍스트 프로토콜) 서버에서 다음 37개의 도구를 호출합니다. 각 도구 이름에는 `marketo-optimizer__` 접두사가 붙습니다.

이 참조서에서는 워크플로우 중에 사용되는 지원 기술을 포함하여 등록된 기술별로 문서화된 도구를 다룹니다. 배포 상태나 사용 빈도는 표시되지 않습니다. 이 테이블의 스킬 이름은 도구 참조를 따르며 위에 나열된 제품별 스킬 이름과 다를 수 있습니다.

| 도구 | 스킬 | 용도 |
| --- | --- | --- |
| `marketo-optimizer__get_workspace_root_tree` | `program-creation-marketo-optimizer` | 새 프로그램의 작업 영역 영역 또는 명명된 하위 폴더를 찾습니다. |
| `marketo-optimizer__create_program` | `program-creation-marketo-optimizer` | 확인된 영역 또는 폴더에 프로그램을 만듭니다. |
| `marketo-optimizer__list_programs` | `program-creation-marketo-optimizer`, `landing-page-authoring` | 프로그램을 찾아보거나 랜딩 페이지를 작성할 위치를 찾습니다. |
| `marketo-optimizer__get_program` | `program-creation-marketo-optimizer` | ID로 프로그램을 읽습니다. |
| `marketo-optimizer__update_program` | `program-creation-marketo-optimizer` | 프로그램 메타데이터(예: 이름)를 업데이트합니다. |
| `marketo-optimizer__create_program_token` | `program-creation-marketo-optimizer` | 승인된 프로그램 토큰을 만들거나 수정합니다. |
| `marketo-optimizer__list_program_tokens` | `program-creation-marketo-optimizer` | 프로그램의 해결된 토큰을 읽습니다. |
| `marketo-optimizer__create_dynamic_people_list_with_rules` | `program-creation-marketo-optimizer` | 프로그램 연결된 사람 목록을 만들고 설명에서 대상 규칙을 생성합니다. |
| `marketo-optimizer__list_people_journeys` | `adapt-program`; 채널 플러그 인 공유 참조 | 대상 여정 이름 충돌을 확인하거나 불명확한 결과 후 기존 여정을 찾거나 여정 작업을 위해 채널을 찾아봅니다. |
| `marketo-optimizer__create_person_journey` | `program-creation-marketo-optimizer`, `adapt-program`, `channel-content-authoring` | 프로그램 연결 여정을 만들거나, 조정된 여정을 시작하거나, 이메일 채널에 대해 누락된 여정을 만듭니다. |
| `marketo-optimizer__get_person_journey` | `program-creation-marketo-optimizer`, `adapt-program`; 채널 플러그 인 공유 참조 | 여정 또는 해당 캔버스를 읽거나, 스테이징된 편집 내용을 확인하거나, 채널 작업에 대한 여정을 조회합니다. |
| `marketo-optimizer__update_person_journey` | `adapt-program` | 한 번에 하나의 승인된 빌드 단계를 대상 여정에 추가합니다. |
| `marketo-optimizer__run_person_journey_simulation` | `program-creation-marketo-optimizer` | 게시하지 않고 여정 플로우의 유효성을 검사합니다. |
| `marketo-optimizer__run_program_qa` | `program-creation-marketo-optimizer` | 프로그램 및 해당 여정에 대해 읽기 전용 준비 검사를 실행합니다. |
| `marketo-optimizer__create_channel` | 핸드오프를 통해 `channel-content-authoring`, `program-creation-marketo-optimizer` 및 `image-to-html` | 채널을 만들고 연결합니다. 이메일의 경우 첫 번째 호출에는 템플릿이 나열되고 두 번째 호출에서는 선택한 템플릿을 사용하여 이메일을 만들고 연결합니다. |
| `marketo-optimizer__get_channel` | `channel-content-authoring` | 선택적으로 이메일 제목과 HTML을 포함하는 채널을 읽어 보십시오. |
| `marketo-optimizer__list_channels` | `channel-content-authoring` | 유형별로 채널을 찾아보고, 선택적으로 이름별로 필터링합니다. |
| `marketo-optimizer__update_channel_content` | 핸드오프를 통해 `channel-content-authoring`; `image-to-html` | 변환된 HTML 적용을 포함하여 이메일 제목 또는 HTML을 업데이트합니다. |
| `marketo-optimizer__image_to_html` | `image-to-html` | 비동기 이메일 디자인 변환을 시작하고 편집 가능한 HTML을 검색합니다. |
| `marketo-optimizer__list_asset_library_images` | `landing-page-authoring` | 랜딩 페이지 슬롯에 대한 대체 이미지를 검색합니다. |
| `marketo-optimizer__add_asset_to_program_or_folder` | `landing-page-authoring` | 선택한 Optimizer 프로그램 또는 폴더에서 새 랜딩 페이지를 등록합니다. |
| `marketo-optimizer__get_person_story` | `personalization-engine-health` | 숫자 ID로 한 사람의 개인화 스토리를 읽습니다. |
| `marketo-optimizer__get_persona_story` | `personalization-engine-health` | 스토리를 읽고 정확한 성향을 확인합니다. |
| `marketo-optimizer__run_arbitration` | `personalization-engine-health` | 명시적 확인 후 자격 있는 사용자에 대한 여정을 다시 채점하고 선택합니다. |
| `marketo-optimizer__get_arbitration_summary` | `personalization-engine-health` | 최신 중재 실행에 대한 요약 통계를 읽어 보십시오. |
| `marketo-optimizer__get_arbitration_decisions` | `personalization-engine-health` | 최신 중재 실행에서 개인 단위 결정을 읽습니다. |
| `marketo-optimizer__get_ai_decisioning_health_summary` | `ai-decisioning-health` | 전체 테넌트 준비 보고서를 가져오십시오. |
| `marketo-optimizer__get_persona_distribution` | `ai-decisioning-health` | 사용자 수 및 비율을 보고합니다. |
| `marketo-optimizer__get_people_without_personas` | `ai-decisioning-health` | 성향이 없는 사람의 수 및 점유율을 보고합니다. |
| `marketo-optimizer__get_person_story_attribute_coverage` | `ai-decisioning-health` | 트레이트 범주 범위를 측정하고 채워진 필드를 식별합니다. |
| `marketo-optimizer__get_person_story_data_completeness` | `ai-decisioning-health` | 스토리 풍부성, 완성도 및 성향별 변화를 보고합니다. |
| `marketo-optimizer__get_person_story_coverage` | `ai-decisioning-health` | 기사 범위, 트렌드 및 보류 중인 생성을 보고합니다. |
| `marketo-optimizer__get_personalization_story_pipeline_status` | `ai-decisioning-health` | 파이프라인 상태, 실행 내역 및 보고된 기간을 읽습니다. |
| `marketo-optimizer__get_person_story_refresh_backlog` | `ai-decisioning-health` | 소스 데이터가 변경되어 새로 고침 대기 중인 스토리를 카운트합니다. |
| `marketo-optimizer__get_person_intent_signal_coverage` | `ai-decisioning-health` | 제품 의도, 키워드 의도 및 활동 범위를 측정합니다. |
| `marketo-optimizer__get_person_story_activity_coverage` | `ai-decisioning-health` | 캡처된 참여 필드 및 집계 활동 트렌드를 보고합니다. |
| `marketo-optimizer__get_person_audience_membership_distribution` | `ai-decisioning-health` | 1인당 대상자 멤버십의 평균 및 분포를 보고합니다. |
