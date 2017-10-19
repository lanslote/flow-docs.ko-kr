---
title: "API 커넥터로 인증을 위해 제출 | Microsoft Docs"
description: "커넥터를 인증하여 Microsoft Flow, PowerApps 및 Logic Apps의 모든 사용자가 사용할 수 있게 됩니다."
services: 
suite: flow
documentationcenter: na
author: asavaritayal
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/19/2017
ms.author: astay
ms.openlocfilehash: 7eb357458161ba398864604bfe8912636ddc4d39
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2017
---
# <a name="submit-your-connectors-for-microsoft-certification"></a>Microsoft 인증을 위한 커넥터 제출
Microsoft Flow, Azure Logic Apps 및 Microsoft PowerApps에서 모든 사용자가 사용자 지정 커넥터를 공개적으로 사용할 수 있게 하려면 검토, 유효성 검사 및 게시 승인을 위해 커넥터를 Microsoft에 제출합니다. 

## <a name="certification-criteria"></a>인증 조건
| 기능 | 세부 정보 | 필수 또는 권장 |
| --- | --- | --- |
| SaaS(Software-as-a-Service) 앱 |Logic Apps, Flow 및 PowerApps에 맞는 사용자 시나리오를 충족합니다. |필수 |
| 인증 유형 |사용자 API는 OAuth2, API 키 또는 기본 인증을 지원해야 합니다. |필수 |
| 지원 |고객이 도움말을 찾을 수 있도록 지원 연락처를 제공해야 합니다. |필수 |
| 가용성 및 작동 시간 |앱은 최소 99.9%의 작동 시간을 갖습니다. |권장 |
|  | | |

또한 Microsoft 파트너 또는 ISV(독립 소프트웨어 공급 업체)가 아니고 커넥터를 인증하고 공개적으로 해제하려는 경우 기본 서비스를 소유하거나 API를 사용할 명시적 권한이 나타나야 합니다.

인증되려면 커넥터를 두 단계로 검토합니다. 

1. 기능 유효성 검사
   
    사용자 지정 커넥터는 다음에 대해 평가됩니다.
   
   * 사용자 지정 커넥터 마법사의 정의 섹션에서 잘못된 swagger 또는 JSON 오류
   * 마법사의 테스트 섹션의 런타임 및 스키마 유효성 검사 오류
     
     따라서 각 작업은 Flow, Logic Apps 및 PowerApps에서 클라이언트 쪽 오류를 철저하게 테스트합니다.
2. 콘텐츠 유효성 검사
   
    잘 작성된 커넥터는 각 엔터티에 이름 및 설명을 사용합니다. 각 작업, 입력 매개 변수 및 응답 특성에 다음 항목이 포함되어 있는지 확인하기 위해 swagger를 평가합니다.
   
   * [요약](../logic-apps/custom-connector-openapi-extensions.md#summary)
   * [설명](../logic-apps/custom-connector-openapi-extensions.md#description)
   * [가시성 정보](../logic-apps/custom-connector-openapi-extensions.md#visibility)

## <a name="nominate-and-submit-your-connector-to-microsoft-for-certification"></a>인증을 위해 Microsoft에 커넥터 추천 및 제출
인증을 적용하려면 다음 단계를 수행합니다.

1. **추천**
   
   1. [추천을 제출합니다](https://go.microsoft.com/fwlink/?linkid=848754).
   2. 수신한 상호 비밀 유지 규약 및 파트너 규약에 서명합니다. 
      계속하기 전에 이러한 서명된 계약이 필요합니다. 
      그런 다음 커넥터가 인증 조건을 충족하는지를 확인할 수 있습니다. 
   3. 커넥터가 승인되면 Microsoft에서는 온보딩을 위한 지침을 알립니다.
2. **검토**
   
   1. 검토를 위해 추천 연락처에 이 정보를 전송합니다.
      
      * API를 설명하는 OpenAPI 파일
      * 커넥터를 나타내는 아이콘 파일(.png 또는 .jpg) (아이콘에 230픽셀 사각형 내에 160픽셀 이하인 로고가 있어야 합니다. 색이 지정된 배경의 흰색 로고인 것이 좋습니다.)
      * 아이콘의 브랜드 색은 16진수 형식이며 아이콘 파일에서 색이 지정된 배경과 일치해야 합니다.
      * 유효성 검사를 위한 테스트 계정
      * 지원 연락처
   2. 자세한 내용이 필요한 경우 연락드리겠습니다.
3. **게시**
   
    커넥터 기능 및 콘텐츠의 유효성을 검사한 후 모든 제품 및 지역에 걸친 배포를 위해 커넥터를 스테이징합니다. 일반적으로 인증 및 배포 프로세스에 최대 3주가 걸립니다.
   
    기본적으로 모든 커넥터는 "프리미엄"으로 게시됩니다. 
    Azure에서 앱을 빌드한 경우 커넥터를 Office 365 Enterprise 계획의 모든 사용자가 사용할 수 있는 "표준" 커넥터로 나열하도록 적용할 수 있습니다. 
    자세한 내용은 추천 담당자에게 문의하세요.

