---
title: C2PA 메타데이터
description: Adobe Marketo Optimizer에서 생성 AI로 생성된 이미지에 C2PA 메타데이터를 자동으로 적용하는 방법과 이 방법이 콘텐츠에 미치는 영향에 대해 알아봅니다.
feature: Assets, Content
role: User
source-git-commit: d1268dd4fadec58b5adedeaa295ca0624c2c2dcd
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 0%

---

# C2PA 메타데이터

마케팅 조직들은 콘텐츠 투명성, AI 공시, 자산 변조 방지에 어느 때보다 신경을 곤두세우고 있다. Adobe의 Content Authenticity Initiative(CAI)는 [콘텐츠 증명 및 인증을 위한 연합](https://c2pa.org/specifications/specifications/1.1/specs/C2PA_Specification.html#_trust_model)&#x200B;(C2PA) 기술 표준을 준수하는 도구를 빌드합니다. _C2PA 메타데이터_&#x200B;은(는) 시청자가 콘텐츠 계보를 이해하고 브랜드 자산의 무결성을 확인하는 데 도움이 되는 변조 가능한 암호화된 정보입니다. 이 정보에는 다음이 포함됩니다.

* 발행자 또는 서명자 — 자산을 인증하거나 서명하기 위해 디지털 서명을 발행한 법인 또는 회사에 대한 정보입니다.
* 발행 날짜 — C2PA 메타데이터가 에셋에 적용된 날짜입니다.
* 신용 및 사용 - 이름, 소셜 미디어 핸들 또는 기타 ID 관련 정보를 포함하여 에셋 제작자에 대한 정보입니다.
* 프로세스 — 에셋에 대한 편집 또는 수정 사항의 기록입니다.
* 장치 세부 정보 — 에셋을 만들거나 편집하는 데 사용되는 앱 또는 장치에 대한 정보입니다.
* 사용된 AI 도구 — 생성 AI를 사용하여 에셋을 만든 경우 사용된 모델의 이름이 포함될 수 있습니다.
* 기타 관련 정보 — 에셋 기록에 대한 추가 컨텍스트를 제공하는 데 도움이 되는 추가 데이터도 포함되어 있습니다.

자산 내역에 대한 포괄적인 정보를 보려면 Adobe Content Authenticity [검사 도구](https://contentauthenticity.adobe.com/inspect)를 사용할 수 있습니다.

C2PA 메타데이터는 이미지 파일과 함께 유지됩니다. 생성 AI로 생성 또는 편집한 이미지를 [!DNL Adobe Marketo Optimizer]에 업로드하거나 내보내면 해당 C2PA 메타데이터가 유지됩니다.

Adobe CX 엔터프라이즈 애플리케이션 전반에 걸쳐 C2PA 메타데이터를 자동으로 첨부하는 방법에 대한 자세한 내용은 CX 엔터프라이즈 안내서의 [_생성 AI 콘텐츠 투명도_](https://experienceleague.adobe.com/ko/docs/cx-enterprise-ai/experience-cloud-ai/overview/content-transparency){target="_blank"}를 참조하십시오.

>[!NOTE]
>
>PDF 또는 임베드된(base64) 소스에서 이미지를 추출하는 것과 같이 이미지를 콘텐츠로 가져오는 일부 방법에서는 원본 C2PA 메타데이터를 보존하지 않을 수 있습니다. 이러한 경우 소스에서 C2PA 메타데이터를 읽을 수 없으며 결과에 대해 아무것도 만들어지지 않습니다.

>[!BEGINSHADEBOX]

## 채널을 통한 C2PA 메타데이터 지속성 {#channels}

이메일 또는 WhatsApp 메시지에 이미지를 포함하면 게재된 이미지에 대한 C2PA 메타데이터도 유지됩니다.

* **전자 메일** - _전자 메일 보내기_ 여정 작업을 사용하는 경우 _Assets_ 라이브러리의 전자 메일 콘텐츠에 이미지를 추가하십시오. 이메일이 전달되면 수신자는 메시지에서 이미지를 다운로드할 수 있고 C2PA 메타데이터는 그대로 유지됩니다.
* **WhatsApp** - Meta 비즈니스 계정의 WhatsApp 메시지 템플릿에 이미지를 추가합니다. 시스템에서 바로 추가하거나 _Assets_ 라이브러리에서 이미지 파일을 다운로드할 수 있습니다. _WhatsApp 보내기_ 여정 작업에 템플릿을 사용합니다. WhatsApp 메시지가 전달되면 수신자는 메시지에서 이미지를 다운로드할 수 있으며 C2PA 메타데이터가 그대로 유지됩니다.

>[!ENDSHADEBOX]

## 이미지 생성 {#generate}

>[!INFO]
>
>생성 AI 투명성을 중심으로 새로운 법이 등장하고 있으며, Adobe은 관할권 전반에서 적용 가능한 요구 사항을 충족하기 위해 노력하고 있습니다. C2PA 메타데이터는 Adobe이 이러한 법률의 요구 사항을 충족하기 위해 사용하는 증명 도구입니다.

생성 AI를 사용하여 [!DNL Marketo Optimizer]에서 이메일 콘텐츠에 대한 이미지를 만들면 C2PA 메타데이터가 자동으로 생성된 이미지에 첨부되며 별도의 작업이 필요하지 않습니다. 생성 AI 도구는 원본 소스를 포함하여 기존 메타데이터와 함께 이미지의 변형에 대한 결합된 C2PA 메타데이터 요소를 생성합니다.

>[!NOTE]
>
>[!DNL Marketo Optimizer]은(는) 현재 수동 이미지 편집 작업을 지원하지 않습니다. 이러한 작업에 대한 C2PA 메타데이터 워크플로우는 현재 적용할 수 없습니다.
