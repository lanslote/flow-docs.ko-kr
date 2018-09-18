---
title: MSA(Microsoft 계정)에 대한 Microsoft Flow GDPR 데이터 주체 내보내기 요청 | Microsoft Docs
description: Microsoft Flow를 사용하여 MSA(Microsoft 계정)에 대한 GDPR 데이터 주체 내보내기 요청에 응답하는 방법을 알아봅니다.
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
ms.date: 5/25/2018
ms.author: keweare
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: d03b2fff23fc313ebb7f8c12ce2835687f589516
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690770"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-microsoft-flow"></a>Microsoft Flow에 대한 GDPR 데이터 주체 내보내기 요청에 응답

GDPR(일반 데이터 보호 규정) 준수 과정을 지원하기 위한 노력의 일환으로 Microsoft는 준비를 돕기 위해 이 설명서를 개발했습니다. 이 설명서에서는 GDPR에 대비하기 위해 수행할 작업을 설명하고, Microsoft Flow를 사용할 때 GDPR 준수를 지원하기 위해 지금 Microsoft와 함께 수행할 수 있는 단계의 예제를 공유합니다.

## <a name="manage-export-requests"></a>내보내기 요청 관리

*데이터 이식성 권한*을 사용하면 데이터 주체가 다른 데이터 컨트롤러에게 전송될 수 있는 자신의 개인 데이터 복사본을 전자 형식(구조화되고, 일반적으로 사용되고, 컴퓨터에서 읽을 수 있고, 상호 운용 가능한 형식)으로 요청할 수 있습니다.

[Microsoft 개인 정보 대시보드](https://account.microsoft.com/privacy/) 또는 [Microsoft Flow](https://flow.microsoft.com/)를 사용하여 특정 사용자에 대한 개인 데이터를 찾거나 내보냅니다.

|개인 데이터|위치|
|-----------------|-------------------|
|제품 및 서비스 작업|Microsoft 개인 정보 대시보드|
|흐름|Microsoft Flow 작성자 포털|
|실행 기록|Microsoft Flow 작성자 포털|
|작업 피드|Microsoft Flow 작성자 포털|
|연결|Microsoft Flow 작성자 포털|

## <a name="export-product-and-service-activity"></a>제품 및 서비스 작업 내보내기

1. MSA(Microsoft 계정)를 사용하여 [Microsoft 개인 정보 대시보드](https://account.microsoft.com/privacy/)에 로그인합니다.
1. **작업 기록**을 선택합니다.

    ![작업 기록](./media/gdpr-dsr-export-msa/activityhistory.png) 다른 Microsoft 응용 프로그램 및 사용하는 서비스에 대한 작업 기록을 찾아볼 수 있습니다.
1. **제품 및 서비스 작업** 데이터를 내보내려면 **데이터 다운로드**를 선택한 다음, **새 보관 만들기**를 선택합니다.

    ![데이터 다운로드](./media/gdpr-dsr-export-msa/downloaddata.png)

1. **앱 및 서비스 사용량**을 선택한 다음, **보관 만들기**를 선택합니다.

    ![데이터 다운로드](./media/gdpr-dsr-export-msa/create-archive.png)
1. 새 보관이 생성됩니다. **다운로드**를 선택하여 내보낸 제품 및 서비스 작업 데이터를 가져옵니다.

    ![다운로드](./media/gdpr-dsr-export-msa/download.png)

## <a name="export-a-flow"></a>흐름 내보내기

흐름에 대한 액세스 권한이 있는 최종 사용자는 다음과 같은 단계를 수행하여 흐름을 내보낼 수 있습니다.

1. [Microsoft Flow](https://flow.microsoft.com/)에 로그인합니다.

1. **내 흐름**을 선택한 다음, 내보낼 흐름을 선택합니다.

1. **... 더보기**를 선택한 다음, **내보내기**를 선택합니다.

    ![흐름 내보내기](./media/gdpr-dsr-export/export-flow.png)

1. **패키지(.zip)** 를 선택합니다.

이제 흐름을 압축된 패키지로 사용할 수 있습니다. 자세한 내용은 [흐름을 내보내기고 가져오는 방법](https://flow.microsoft.com/blog/import-export-bap-packages/)에 대한 블로그 게시물을 참조하세요.

## <a name="export-run-history"></a>실행 기록 내보내기

실행 기록에는 흐름에 대한 모든 실행 목록이 포함됩니다. 이 데이터에는 트리거 및 작업에 대한 흐름의 상태, 시작 시간, 기간 및 입력/출력 데이터가 포함됩니다.

흐름에 대한 액세스 권한이 있는 최종 사용자는 다음과 같은 단계를 수행하여 이 데이터를 내보낼 수 있습니다.

1. [Microsoft Flow](https://flow.microsoft.com/)에 로그인합니다.
1. **내 흐름** 링크를 선택한 다음, 실행 기록을 내보낼 흐름을 선택합니다.
1. **실행 기록** 창에서 **모두 보기**를 선택합니다.

    ![실행 기록](./media/gdpr-dsr-export/run-history.png)

1. **CSV 다운로드**를 선택합니다.

    ![CSV 다운로드](./media/gdpr-dsr-export/download-csv.png)

실행 기록은 .csv 파일로 다운로드되므로 Microsoft Excel 또는 텍스트 편집기에서 열고 결과를 분석할 수 있습니다.

## <a name="export-a-users-activity-feed"></a>사용자의 작업 피드 내보내기

[Microsoft Flow](https://flow.microsoft.com/)에서 작업 피드는 사용자의 작업, 실패 및 알림에 대한 기록을 표시합니다. 모든 사용자는 다음 단계에 따라 자신의 작업 피드를 볼 수 있습니다.

1. [Microsoft Flow](http://flow.microsoft.com/)에 로그인하고 오른쪽 위 모서리 근처의 벨 아이콘을 선택한 다음, **작업 피드로 이동**을 선택합니다.

    ![작업 피드 표시](./media/gdpr-dsr-export/show-activity-feed.png)

1. **작업** 화면에서 결과를 복사한 다음, Microsoft Word와 같은 텍스트 편집기에 붙여넣습니다.

    ![작업 피드 표시](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>사용자의 연결 내보내기

연결을 통해 흐름이 API, SaaS 응용 프로그램 및 기타 타사 시스템에 연결될 수 있습니다. 연결을 보려면 다음 단계를 수행합니다.

1. [Microsoft Flow](http://flow.microsoft.com/)에 로그인하고 오른쪽 위 모서리 근처의 기어 아이콘을 선택한 다음, **연결**을 선택합니다.

    ![연결 표시](./media/gdpr-dsr-export/show-connections.png)
1. 결과를 복사한 다음, Microsoft Word와 같은 텍스트 편집기에 붙여넣습니다.
