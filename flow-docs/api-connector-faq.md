---
title: "API 커넥터 FAQ | Microsoft Docs"
description: "요구 사항, 트리거 및 다른 영역에 대한 질문에 대해 답변을 찾습니다."
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
ms.openlocfilehash: 1715700fa6a94bb35733865556a2c9be0ba3ce9f
ms.sourcegitcommit: f3236f9f1ec050cda0d9c3e2b9c356132b2a2594
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2018
---
# <a name="api-connector-faq-microsoft-flow"></a>API 커넥터 FAQ(Microsoft Flow)
## <a name="requirements"></a>요구 사항
**Q:** REST API 없이 커넥터를 빌드할 수 있습니까? </br>
**A:** 아니요, 커넥터를 빌드하려면 서비스에 대한 안정적인 HTTP REST API를 지원해야 합니다. 

**Q:** 커넥터를 만드는 데 사용할 수 있는 도구는 무엇입니까? </br>
**A:** Azure에는 호스팅용 Azure App Service, API Management 등 모든 서비스를 API로 노출하는 데 사용할 수 있는 기능 및 서비스가 있습니다.

**Q:** 지원되는 인증 유형은 무엇입니까? </br>
**A:** 다음과 같이 지원되는 인증 표준을 사용할 수 있습니다.

* [Azure Active Directory](https://azure.microsoft.com/develop/identity/) 또는 Dropbox, GitHub 및 SalesForce 등의 특정 서비스를 비롯한 [OAuth 2.0](https://oauth.net/2/)
* 일반 OAuth 2.0
* [기본 인증](https://swagger.io/docs/specification/authentication/basic-authentication/)
* [API 키](https://swagger.io/docs/specification/authentication/api-keys/)

## <a name="triggers"></a>트리거
**Q:** 웹후크 없이 트리거를 빌드할 수 있습니까? </br>
**A:** 아니요, Azure Logic Apps 및 Microsoft Flow용 사용자 지정 커넥터는 웹후크 기반 트리거만을 지원합니다. 구현에 대한 다른 패턴을 요청하려는 경우 API에 대한 자세한 정보를 사용하여 [condevhelp@microsoft.com](mailto:condevhelp@microsoft.com)에 문의하세요.

## <a name="certification"></a>인증
**Q:**: Microsoft 파트너 또는 ISV(독립 소프트웨어 공급 업체)가 아닌 경우 여전히 커넥터를 만들 수 있습니까? </br>
**A**: 예, 조직의 내부에서 사용하기 위해 이러한 커넥터를 등록할 수 있지만, 커넥터를 인증하고 공개적으로 해제하려는 경우 기본 서비스를 소유하거나 API를 사용할 명시적 권한이 나타나야 합니다.

## <a name="other"></a>기타
**Q:** 내 API가 동적 호스트를 사용합니다. OpenAPI에서 구현하려면 어떻게 할까요? </br>
**A:** 사용자 지정 커넥터는 동적 호스트를 지원하지 않습니다. 대신 개발 및 테스트 목적으로 고정 호스트를 사용합니다. 커넥터를 인증하려면 동적 구현에 대해 Microsoft 담당자에게 문의하세요.

**Q:** Postman 컬렉션 V2를 지원합니까? </br>
**A:** 아니요, 현재 Postman Collection V1만 지원됩니다.

**Q:** OpenAPI 3.0을 지원합니까? </br>
**A:** 아니요, 현재 OpenAPI 2.0만 지원됩니다.

