---
title: 사용자 지정 점수 모델 만들기
description: 동료 채팅 인터페이스의 Scoring Studio 스킬을 사용하여 Marketo Optimizer에서 사용자 정의 잠재 고객 점수 모델을 만들고, 미리 보고, 게시합니다.
source-git-commit: 75b481faf0d66210329f95c8afabdfa59e7bcb79
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 1%

---

# 사용자 정의 점수 모델 만들기

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_scoring_studio"
>title="Scoring Studio"
>abstract="Scoring Studio 기술을 사용하여 동료 채팅 인터페이스를 통해 사용자 정의 리드 점수 모델을 만들고, 구성하고, 게시합니다."

[!DNL Adobe Marketo Optimizer]의 [_Scoring Studio_ 스킬](./skills.md#scoring-signals)은(는) 잠재 고객 스코어링 모델을 만들고, 구성하고, 게시할 수 있도록 하는 AI 기반 잠재 고객 스코어링 솔루션을 제공합니다. Studio는 에이전트 기반 워크플로를 시각적 UI와 결합합니다. [동료 채팅 인터페이스](./chat-interface.md)에서 자연어 프롬프트를 통해 또는 UI 컨트롤과 직접 상호 작용하여 채점 모델을 만들 수 있습니다.

* **스킬** - `scoring-studio`
* **호출** - 슬래시 명령을 사용하여 Scoring Studio를 엽니다. 예: _&quot;Scoring Studio를 엽니다.&quot;_
* **읽기/쓰기 대상** - [!DNL Marketo Optimizer] 채점 서비스, [!DNL Marketo Engage] 리드 필드 및 활동 유형 읽기

시작 시 Coworker는 활동 유형, 리드 필드, 개인 목록 및 기존 점수 목록을 포함한 관련 컨텍스트를 자동으로 가져와서 데이터에 제안 사항을 반영합니다.

![동료 채팅 인터페이스에서 시작된 채점 스튜디오](./assets/scoring-studio.png){width="700" zoomable="yes"}

## 채점 모델 만들기 {#create-model}

Scoring Studio를 열면 Coworker는 정적 목록과 채점된 활동 세트로 미리 채워진 관련 예제 채점 모델을 제안합니다. 이 제안된 시작점을 수락하거나 사용자 정의 모델을 정의하라는 메시지를 제공할 수 있습니다.

### 모델 미리 보기 {#preview-model}

프롬프트를 제공한 후 Coworker는 변경하기 전에 모델 미리보기를 생성합니다. 미리보기 서피스:

* 사용 중인 채점 차원
* 채점 중인 속성 및 활동
* 세그먼트로 적용된 정적 목록 또는 스마트 목록
* 모델 목표, 타겟 세그먼트 및 기본 신호에 대한 요약

미리보기를 검토하고 이를 기반으로 모델을 만들도록 선택하거나, 채팅을 계속 세분화하여 최종적으로 완성할 수 있습니다.

### 모델 구조 {#model-structure}

만든 모델은 _차원_ 및 _신호_(으)로 구성됩니다. UI의 속성 패널을 사용하여 각 신호를 구성할 수 있습니다.

* **신호 형식** — 활동 기반 또는 특성 기반
* **활동 또는 특성** — 점수를 매길 특정 항목
* **신호 매개 변수** — 신호에 대한 조정 가능한 설정

자연어를 사용하여 Coworker를 통해 완전히 모델을 구축 및 구성하거나 UI 컨트롤과 직접 상호 작용할 수 있습니다.

## 채점 모델 게시 {#publish-model}

모델이 완성되면 Coworker에 게시하도록 지시합니다. 게시 프로세스는 다음을 자동으로 처리합니다.

| 단계 | 다음 단계 |
|---|---|
| **규칙 컴파일** | 모든 채점 규칙이 컴파일되고 검증됩니다 |
| **점수 작업 만들기** | 예약된 점수 작업이 매일 실행되도록 생성되고 구성됩니다. |

게시 후 수동 실행을 트리거하여 점수를 즉시 처리할 수도 있습니다.

## 채점 결과 보기 {#view-results}

채점 실행이 완료되면 잠재 고객 가져오기 프로세스를 통해 점수가 [!DNL Marketo Engage]에 다시 기록됩니다. 가져오기가 완료되면 업데이트된 점수를 [!DNL Marketo Engage]에서 직접 확인할 수 있습니다.

각 실행 후 다음을 보여주는 결과 요약을 볼 수 있습니다.

* 몇 명이 채점받았습니까
* 개인별 점수 변경

감사 로그는 추가 실행 세부 정보를 검토하는 데 사용할 수 있습니다.
