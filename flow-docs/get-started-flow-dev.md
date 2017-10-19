---
title: "작성 시작 | Microsoft Docs"
description: "사용자 지정 커넥터를 만들고, 공유하고, 흐름을 포함하여 다양한 작업을 수행합니다."
services: 
suite: flow
documentationcenter: na
author: bbarath
manager: erikre
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/22/2016
ms.author: barathb
ms.openlocfilehash: d22193ac40b6eb8f90abf2ae5ced91b39c2faad9
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2017
---
# <a name="start-to-build-with-microsoft-flow"></a>Microsoft Flow를 통한 작성 시작
그 중에서도 다음과 같은 방법으로 Microsoft Flow를 통해 응용 프로그램을 확장합니다. 

* 만들기 및 사용자 지정 커넥터 연결
* Microsoft Flow의 모든 사용자와 해당 API 공유
* 앱 내부로부터 흐름 환경 포함
* 사용자가 가장 적합한 형태로 Microsoft Flow와 상호 작용할 수 있게 모든 개발자 API 활용

## <a name="prerequisites"></a>필수 구성 요소
* [flow.microsoft.com](https://flow.microsoft.com) 계정

## <a name="create-a-custom-connector"></a>사용자 지정 커넥터 만들기
Microsoft Flow를 통해 자동화하려는 웹 서비스가 있는 경우 먼저 사용자 지정 커넥터가 필요합니다. 사용자 지정 커넥터를 등록하면 필요한 인증, 지원하는 트리거 및 동작, 각 동작의 매개 변수 및 출력 등, Microsoft Flow에게 웹 API의 특징에 대해 알리게 됩니다.

[이 자습서](https://powerapps.microsoft.com/tutorials/register-custom-api/)에 따라 사용자 지정 커넥터를 등록합니다. 등록한 후에는 조직 내부에서 공유하여 다른 사용자들이 테스트를 지원하도록 할 수 있습니다.

## <a name="share-a-custom-connector-with-all-microsoft-flow-users"></a>모든 Microsoft Flow 사용자와 사용자 지정 커넥터 공유
사용자 지정 커넥터를 완전히 테스트한 후에는 [이 블로그 게시물](https://flow.microsoft.com/blog/calling-all-saas-apps-now-you-can-build-your-own-connector-for-flow-and-logic-apps/)에 정립되어 있는 검토 프로세스를 시작합니다.

* API 및 인증 정보를 표시하는 OpenAPI 파일
* 커넥터에 대한 아이콘
* API 설명
* 템플릿을 통해 API가 다른 사용자에게 도움이 될 수 있는 약 10가지 방법

이 정보를 제출한 후에는 Microsoft가 Microsoft Flow 및 Microsoft PowerApps에서 API 기능을 평가할 수 있습니다.

## <a name="embed-the-flow-experience-in-your-website-or-app"></a>웹 사이트 또는 앱에 흐름 환경 포함
마지막으로 앱 내부로부터 Microsoft Flow를 포함하여 사용자의 앱과 Microsoft Flow가 지원하는 모든 다른 서비스 간의 심층적인 컨텍스트 통합을 활성화할 수 있습니다. 예를 들어, 다음을 수행할 수 있습니다.

* 서비스와 관련한 모든 템플릿을 탐색하고 사용자가 템플릿을 선택하게 합니다.
* 사용자가 앱과 연결한 흐름을 관리합니다.

앱 안에 Microsoft Flow를 포함하는 방법에 대한 자세한 내용은 [이 자습서](embed-flow-dev.md)를 확인합니다.

