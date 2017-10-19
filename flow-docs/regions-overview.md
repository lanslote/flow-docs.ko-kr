---
title: "Microsoft Flow의 지역 개요 | Microsoft Docs"
description: "Microsoft Flow의 지역에 대한 질문 및 대답 개요"
services: 
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/28/2017
ms.author: deonhe
ms.openlocfilehash: ec9b72e570c562c091aefd370f73d6862ff56f18
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2017
---
# <a name="faq-for-regions-in-microsoft-flow"></a>Microsoft Flow의 지역에 대한 FAQ
이 문서에서는 Microsoft Flow에 대한 질문 및 대답 목록을 제공합니다.

## <a name="how-do-i-find-out-where-my-flow-is-deployed"></a>내 흐름이 어디로 배포되는지 어떻게 알 수 있습니까?
사용자의 흐름은 [환경](environments-overview-admin.md)을 호스트하는 [지역](https://azure.microsoft.com/regions/)에 배포됩니다. 예를 들어 사용자 환경이 유럽 지역에서 만들어진 경우 모든 흐름은 유럽 데이터 센터에 배포됩니다.

관리자는 사용자가 Microsoft Flow [관리자 센터](https://admin.flow.microsoft.com)에 로그인하면 지역을 식별할 수 있습니다. **환경** 탭은 모든 기존 환경 및 해당 지역을 나열합니다.

![환경 보기](media/regions-overview/environments-list.png)

## <a name="what-regions-are-available"></a>지원하는 지역은 어디인가요?
* 미국
* 유럽
* 아시아
* 오스트레일리아
* 인도
* 일본
* 캐나다

## <a name="what-features-are-specific-to-a-given-region"></a>지정된 지역의 특정 기능은 무엇입니까?
환경은 다양한 지역에서 만들 수 있으며 해당 지리적 위치에 바인딩됩니다. 환경에서 흐름을 만들면 이 흐름은 해당 지리적 위치의 모든 데이터 센터에 배포됩니다. 이 작업은 공통 데이터 모델, 흐름, 연결, 게이트웨이, 앱, 사용자 지정 커넥터 등을 포함하여 해당 환경에서 사용자가 만든 모든 항목에 적용됩니다.

성능을 최적화하기 위해 사용자에게 가장 가까운 지역에서 환경을 만듭니다. 예를 들어 사용자가 유럽에 있는 경우 유럽 지역에서 환경을 만듭니다. 사용자가 미국에 있는 경우 미국 지역에서 환경을 만듭니다.

## <a name="gateways"></a>게이트웨이
게이트웨이는 다음과 같습니다.

* 인도 지역에서는 사용할 수 없습니다.
* 사용자 지정 환경이 아닌 경우 기본 환경으로만 지원합니다.

## <a name="is-microsoft-flow-available-in-national-clouds"></a>국가 클라우드에서 Microsoft Flow를 사용할 수 있나요?
아니요, 국가 클라우드에서 Microsoft Flow를 사용할 수 없습니다. 국가 클라우드는 2018년부터 지원할 계획입니다.

## <a name="what-outbound-ip-addresses-are-used-in-each-region"></a>각 지역에서 사용되는 아웃바운드 IP 주소는 무엇인가요?
[제한 및 구성](limits-and-config.md)을 참조하세요.

