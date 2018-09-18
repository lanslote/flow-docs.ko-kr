---
title: MSA(Microsoft 계정)에 대한 Microsoft Flow GDPR 데이터 주체 검색 요청 | Microsoft Docs
description: Microsoft Flow를 사용하여 MSA(Microsoft 계정)에 대한 GDPR 데이터 주체 검색 요청에 응답하는 방법을 알아봅니다.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: KFile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/16/2018
ms.author: keweare
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 9a7031780ed6582d9f881571c3d07ce8aece074d
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690730"
---
# <a name="respond-to-gdpr-data-subject-discovery-requests"></a>GDPR 데이터 주체 검색 요청에 응답 

DSR 요청에 응답하는 첫 번째 단계는 요청 대상인 개인 데이터를 찾는 것입니다.
해당 MSA(Microsoft 계정)를 사용하여 인증하는 사용자의 개인 데이터를 포함하는 Microsoft Flow 리소스의 요약은 다음과 같습니다.

|리소스|용도|
|-----|-----|
|실행 기록|지난 28일 동안 각 흐름의 실행 기록을 제공합니다. 이 데이터에는 각 흐름 실행에 대한 시작 시간, 종료 시간, 상태 및 모든 입력/출력 정보가 포함됩니다. [흐름 실행 기록](https://flow.microsoft.com/blog/download-history-recurrence/)에 대해 자세히 알아봅니다.|
|작업 피드| 실행 상태, 오류 및 알림을 포함하여 각 흐름 작업의 요약을 제공합니다.|
|흐름|[흐름](https://docs.microsoft.com/flow/get-started-logic-flow)의 워크플로 논리입니다.|
|연결|커넥터에서 사용되고, API, 시스템, 데이터베이스 등에 대한 연결을 허용합니다. [연결](add-manage-connections.md)에 대해 자세히 알아봅니다.|

