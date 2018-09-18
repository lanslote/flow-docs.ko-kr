---
title: Microsoft Flow GDPR 데이터 주체 요청 검색 | Microsoft Docs
description: Microsoft Flow를 사용하여 GDPR 데이터 주체 검색 요청에 응답하는 방법을 알아봅니다.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/17/2018
ms.author: keweare
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 9ec66eefdbf2f6b6a9047678e9c29cb66900eda2
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44688930"
---
# <a name="responding-to-gdpr-data-subject-discovery-requests-for-microsoft-flow"></a>Microsoft Flow에 대한 GDPR 데이터 주체 검색 요청에 응답

DSR에 응답하는 첫 번째 단계는 요청 대상인 개인 데이터를 찾는 것입니다. 이 첫 번째 단계에서는 DSR이 DSR 요청을 수락 또는 거부하기 위한 조직의 요구 사항을 충족하는지 확인할 수 있습니다. 예를 들어 해당하는 개인 데이터를 찾고 검토한 후 요청을 수락할 경우 다른 사용자의 권한과 자유에 부정적인 영향을 미칠 수 있으므로 해당 요청이 조직의 요구 사항을 충족하지 않는다고 결정할 수 있습니다.

다음은 특정 사용자에 대한 개인 데이터를 포함하는 Microsoft Flow 리소스의 유형에 대한 요약입니다.

|**개인 데이터를 포함하는 리소스**|**용도**|
|-----|-----|
|시스템 생성 로그|시스템 이벤트 및 기록을 캡처하는 원격 분석입니다.|
|실행 기록|지난 28일 동안 각 흐름 실행의 기록입니다. 이 데이터에는 흐름에 대한 시작 시간, 종료 시간, 상태 및 모든 입력/출력 정보가 포함됩니다. [자세히 알아보기](https://flow.microsoft.com/blog/download-history-recurrence/)|
|작업 피드| 실행 상태, 실패 및 알림을 포함하여 흐름 작업의 요약을 제공합니다.|
|사용자 작업|흐름을 실행하기 위해 사용자 대신 실행되는 시스템 작업으로, 사용자에게 표시되지 않습니다.|
|흐름|흐름에 대해 존재하는 워크플로 논리입니다. [자세히 알아보기](https://docs.microsoft.com/flow/get-started-logic-flow)|
|흐름 권한|흐름을 공유하고 다른 사용자에게 다시 할당할 수 있습니다. 모든 흐름에 대한 권한 목록이 존재합니다. [자세히 알아보기](https://docs.microsoft.com/flow/frequently-asked-questions#can-i-share-the-flows-i-create)|
|사용자 세부 정보|사용자에게 표시되지 않고 흐름 실행을 지원하는 세부 정보입니다.|
|연결|커넥터가 사용하고 API, 시스템, 데이터베이스 등에 대한 연결을 허용합니다. [자세히 알아보기](https://docs.microsoft.com/flow/add-manage-connections)|
|연결 권한|특정 연결에 대한 권한입니다. [자세히 알아보기](https://docs.microsoft.com/flow/add-manage-connections)|
|사용자 지정 커넥터|사용자 지정 또는 타사 시스템에 대한 연결을 허용하기 위해 사용자가 만들고 게시한 사용자 지정 커넥터입니다. [자세히 알아보기](https://docs.microsoft.com/connectors/custom-connectors/)|
|사용자 지정 커넥터 권한|사용자 지정 커넥터에 대한 권한 목록입니다. [자세히 알아보기](https://docs.microsoft.com/connectors/custom-connectors/share)|
|게이트웨이|게이트웨이는 Microsoft Flow와 클라우드에 없는 데이터 원본 간에 빠르고 안전하게 데이터를 전송하기 위해 사용자가 설치할 수 있는 온-프레미스 데이터 서비스입니다. [자세히 알아보기](https://docs.microsoft.com/flow/gateway-manage)|
|게이트웨이 권한|게이트웨이는 조직 내의 사용자와 공유할 수 있습니다. [자세히 알아보기](https://go.microsoft.com/fwlink/?linkid=872249)|
