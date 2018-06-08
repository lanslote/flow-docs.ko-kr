---
title: 사용자 지정 커넥터 만들기 및 흐름 포함 | Microsoft Docs
description: 사용자 지정 커넥터를 만들고, 공유하고, 흐름을 포함하여 다양한 작업을 수행합니다.
services: ''
suite: flow
documentationcenter: na
author: bbarath
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2017
ms.author: barathb
ms.openlocfilehash: a3f1e21cfbf00749a0ef09c0363da162f0419f42
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "23439707"
---
# <a name="start-to-build-with-microsoft-flow"></a>Microsoft Flow를 통한 작성 시작

Microsoft Flow를 통해 응용 프로그램을 확장할 수 있는 몇 가지 방법은 다음과 같습니다.

* 만들기 및 사용자 지정 커넥터 연결
* 모든 Microsoft Flow 사용자와 사용자 지정 커넥터 공유
* 앱 내부에 흐름 환경 포함
* 사용자가 가장 적합한 방식으로 Microsoft Flow와 상호 작용할 수 있게 모든 사용자 지정 커넥터 강조 표시

## <a name="prerequisites"></a>필수 구성 요소

* [Microsoft Flow](https://flow.microsoft.com) 계정

## <a name="create-a-custom-connector"></a>사용자 지정 커넥터 만들기

Microsoft Flow에서 연결하려는 웹 서비스가 있는 경우 먼저 사용자 지정 커넥터를 만들어야 합니다. 사용자 지정 커넥터를 등록하면 필요한 인증, 지원하는 트리거 및 동작, 각 동작의 매개 변수 및 출력 등, Microsoft Flow에게 웹 서비스의 특징에 대해 알리게 됩니다.

이 자습서에 따라 [사용자 지정 커넥터 등록 및 사용](https://powerapps.microsoft.com/tutorials/register-custom-api/) 방법을 알아보세요. 사용자 지정 커넥터를 등록한 후 테스트를 위해 조직 내에서 공유할 수 있습니다.

## <a name="share-a-custom-connector-with-all-microsoft-flow-users"></a>모든 Microsoft Flow 사용자와 사용자 지정 커넥터 공유

사용자 지정 커넥터를 완벽하게 테스트한 후 모든 다른 Microsoft Flow 사용자와 공유하기 위해 Microsoft에서 승인하도록 [검토 프로세스](https://flow.microsoft.com/blog/calling-all-saas-apps-now-you-can-build-your-own-connector-for-flow-and-logic-apps/)를 시작합니다.

다음은 검토 프로세스에서 필요한 사항입니다.

* API 및 인증 정보를 표시하는 OpenAPI 파일
* 커넥터에 대한 아이콘
* 커넥터에 대한 설명
* 템플릿을 통해 커넥터가 다른 사용자에게 도움이 될 수 있는 약 10가지 방법

이 정보를 제출한 후에는 Microsoft가 Microsoft Flow 및 Microsoft PowerApps에서 API 기능의 평가를 시작합니다.

## <a name="embed-the-flow-experience-into-your-website-or-app"></a>웹 사이트 또는 앱에 흐름 환경 포함

앱 내에 Microsoft Flow를 [포함](embed-flow-dev.md)하여 앱과 Microsoft Flow가 지원하는 모든 다른 서비스 간에 심층적인 컨텍스트 통합을 활성화할 수 있습니다. 예를 들어, 다음을 수행할 수 있습니다.

* 서비스와 관련한 모든 템플릿을 탐색하고 사용자가 템플릿을 선택하게 합니다.
* 사용자가 앱과 연결한 흐름을 관리합니다.

## <a name="next-steps"></a>다음 단계

앱에 Microsoft Flow를 [포함](embed-flow-dev.md)하는 방법을 알아보세요.
