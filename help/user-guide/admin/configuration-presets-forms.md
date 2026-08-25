---
title: Forms 구성
description: 플레이스홀더
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 16%

---

# Forms 구성

마케터가 랜딩 페이지에서 사용할 양식을 만들고 게시하려면 제품 관리자가 하나 이상의 전용 사전 설정을 만들어야 합니다. 각 사전 설정은 양식 제출 데이터를 전송하는 데 사용되는 연결 끝점과 캡처된 데이터를 저장하는 데 사용되는 데이터 세트를 정의합니다.

스트리밍 끝점에 데이터가 도달하면 데이터 세트 정보와 연결됩니다. 그런 다음 생성된 소스/타겟 연결 및 소스 흐름을 사용하여 데이터가 데이터 세트로 푸시됩니다.

>[!BEGINSHADEBOX]

## 사전 요구 사항

웹 양식을 사용하려면 Adobe Experience Platform에 하나 이상의 _&#x200B;**HTTP API 스트리밍 연결**&#x200B;_&#x200B;이 정의되어 있어야 합니다. 사용하려는 각 연결이 다음 요구 사항을 충족하는지 확인하십시오.

* 데이터 유형은 원시 데이터가 아닌 XDM으로 설정되어야 합니다.
* 인증을 사용하지 않도록 설정해야 합니다(인증되지 않은 연결).

스트리밍 소스 연결 만들기에 대한 자세한 내용은 [_Experience Platform 설명서_](https://experienceleague.adobe.com/ko/docs/experience-platform/sources/ui-tutorials/create/streaming/http)를 참조하세요.

<!-- 
permissions coming in GA

Forms channel configuration in Journey Optimizer B2B Edition requires the following [permissions](../start/user-management.md#b2b-product-permissions):

* _[!UICONTROL B2B Channel Configurations]_ > _[!UICONTROL View Forms Presets]_ - Required to view forms preset configurations.
* _[!UICONTROL B2B Channel Configurations]_ > _[!UICONTROL Manage Forms Presets]_ - Required to create, update, and delete forms preset configurations.
* _[!UICONTROL B2B Channel Configurations]_ > _[!UICONTROL Publish Forms Presets]_ - Required to publish forms preset configurations.
-->

>[!ENDSHADEBOX]

## 양식 사전 설정 구성 지침

사전 설정을 만들 때:

* 다양한 데이터 세트 조합과 스트리밍 연결을 사용하여 여러 사전 설정을 설정할 수 있습니다.

* 동일한 데이터 세트 또는 여러 사전 설정에서 스트리밍 연결을 재사용할 수 있습니다.

* 각 스트리밍 연결은 다음과 같은 리소스를 자동으로 생성합니다.

  * _Source 연결_ - 데이터가 생성되는 위치입니다.
  * _대상 연결_ - 데이터가 저장되거나 사용되는 위치입니다.
  * _Source 흐름_ - 소스 연결에서 Experience Platform으로 데이터를 이동하는 파이프라인입니다. 매핑, 변환 및 유효성 검사를 처리합니다.

## 양식 사전 설정 만들기 {#create-preset}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_form_connection"
>title="사용할 엔드포인트 선택"
>abstract="양식 제출 시 데이터가 전송되는 스트리밍 엔드포인트를 정의합니다."
>additional-url="https://experienceleague.adobe.com/ko/docs/experience-platform/sources/ui-tutorials/create/streaming/http" text="HTTP API 스트리밍 연결 만들기"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_form_dataset"
>title="데이터 세트 선택"
>abstract="양식 응답이 저장되고 반영될 데이터 세트를 정의합니다. 텍스트를 입력하여 특정 데이터 세트를 검색하거나 목록에서 선택할 수 있습니다."

1. 왼쪽 탐색에서 **[!UICONTROL 관리]** > **[!UICONTROL 채널]**(으)로 이동합니다.

1. 탐색 패널의 _[!UICONTROL 양식 설정]_&#x200B;에서 **[!UICONTROL 양식 사전 설정]**&#x200B;을 선택합니다.

   <!-- ![Access the form configurations](./assets/config-channels-forms.png){width="800" zoomable="yes"} -->

1. **[!UICONTROL 양식 사전 설정 만들기]**&#x200B;를 클릭합니다.

1. 구성에 고유한 **[!UICONTROL 이름]**(필수)과 **[!UICONTROL 설명]**(선택 사항)을 입력하십시오.

   >[!NOTE]
   >
   >이름은 문자(A-Z)로 시작해야 하며 영숫자만 포함할 수 있습니다. 밑줄 `_`, 점 `.` 및 하이픈 `-`자를 사용할 수도 있습니다.

1. **[!UICONTROL 스트리밍 연결]**&#x200B;을 선택합니다.

   이 연결은 웹 뷰어가 양식을 제출할 때 데이터를 전송하는 데 사용되는 스트리밍 끝점입니다. 필요한 스트리밍 연결이 목록에 표시되지 않으면 요구 사항이 충족되었는지 확인하십시오.

1. _데이터 집합 선택_( ![데이터 집합 선택 아이콘](../assets/do-not-localize/icon-select-data.svg) ) 아이콘을 클릭하여 데이터 집합을 양식과 연결합니다.

   데이터 집합은 양식 응답이 저장되고 반영되는 위치입니다. 텍스트 문자열을 입력하여 특정 데이터 세트를 검색하거나 목록에서 선택할 수 있습니다.

   <!-- ![Select datasets dialog](./assets/config-channel-forms-select-datasets.png){width="500" zoomable="yes"} -->

   >[!NOTE]
   >
   >현재 프로필이 활성화되고 프로필이 활성화되지 않은 [Adobe Experience Platform 데이터 세트](https://experienceleague.adobe.com/ko/docs/experience-platform/catalog/datasets/overview)만 선택할 수 있습니다. 한 번에 하나의 데이터 세트를 선택할 수 있습니다. 시스템 데이터 세트는 양식 데이터를 저장하는 데 사용할 수 없습니다.

   데이터 집합에 대한 확인란을 선택하고 **[!UICONTROL 선택]**&#x200B;을 클릭합니다.

1. **[!UICONTROL 초안으로 저장]**&#x200B;을 클릭합니다.

## 양식 사전 설정 게시

1. 양식 사전 설정 이름을 클릭하여 구성 페이지를 엽니다.

   필요한 경우 초안을 조정할 수 있습니다.

1. **[!UICONTROL 게시]**&#x200B;를 클릭합니다.

   양식 사전 설정이 _게시됨_ 상태로 나열되면 양식 만들기에 사용할 수 있습니다.
