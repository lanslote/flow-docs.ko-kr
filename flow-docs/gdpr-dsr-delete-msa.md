---
title: MSA(Microsoft 계정)에 대한 Microsoft Flow GDPR 데이터 주체 삭제 요청 | Microsoft Docs
description: Microsoft Flow를 사용하여 MSA(Microsoft 계정)에 대한 GDPR 데이터 주체 삭제 요청에 응답하는 방법을 알아봅니다.
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
ms.date: 5/25/2018
ms.author: keweare
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: e42da775d5c004bfbe0d6bb8923e6d05aaa5e976
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44688976"
---
# <a name="respond-to-gdpr-data-subject-delete-requests"></a>GDPR 데이터 주체 삭제 요청에 응답

개인 데이터의 삭제에서 **삭제할 권한**은 GDPR의 핵심 보호입니다. 개인 데이터 삭제에는 감사 로그 정보를 제외한 모든 개인 데이터 제거가 포함됩니다.

Microsoft Flow를 사용하면 사용자가 자동화된 워크플로를 작성할 수 있습니다. 사용자가 Microsoft Flow에서 해당 개인 데이터를 삭제하도록 결정할 때 사용자는 해당 개인 데이터를 검토하고 전부 또는 일부를 삭제할지를 결정합니다.

다음 표에서는 자동으로 삭제되는 개인 데이터 및 MSA(Microsoft 계정) 사용자가 검토하고 삭제해야 하는 데이터를 보여줍니다.

|MSA 사용자 검토 및 삭제 요구|자동으로 삭제|
|------|------|
|제품 및 서비스 작업|실행 기록|
|흐름|작업 피드|
|연결||

Microsoft Flow는 사용자가 자동으로 삭제되지 않은 개인 데이터 및 리소스를 찾거나, 검토하거나, 변경할 수 있도록 다음과 같은 환경을 제공합니다.

## <a name="manage-delete-requests"></a>삭제 요청 관리

아래의 단계에서는 GDPR에 대한 자체 삭제 요청을 수행하는 방법을 설명합니다.

### <a name="delete-product-and-service-activity"></a>제품 및 서비스 작업 삭제

1. MSA를 사용하여 [Microsoft 개인 정보 대시보드](https://account.microsoft.com/privacy/)에 로그인합니다.
1. **작업 기록** 링크를 선택합니다.

    ![작업 기록](./media/gdpr-dsr-export-msa/activityhistory.png)

1. Microsoft Flow를 비롯하여 다른 Microsoft 응용 프로그램 및 사용하는 서비스에 대한 작업 기록을 검색하거나 찾아볼 수 있습니다. **삭제**를 선택하여 특정 제품 또는 서비스 작업 이벤트를 제거합니다.

    ![이벤트 삭제](./media/gdpr-dsr-delete-msa/deleteevent.png)

1. 몇 분 안에 개인 정보 대시보드에서 항목이 삭제되고 제거됩니다.

### <a name="list-and-delete-flows"></a>흐름 나열 및 삭제

사용자는 다음과 같은 단계를 수행하여 [Microsoft Flow](https://flow.microsoft.com)에서 해당 흐름을 나열하고 삭제할 수 있습니다.

1. [Microsoft Flow](https://flow.microsoft.com)에 로그인한 다음, **내 흐름**을 선택합니다.

1. 삭제 중인 흐름 옆에 있는 **...** 를 선택한 다음, **삭제**를 선택합니다.

    ![이벤트 삭제](./media/gdpr-dsr-delete-msa/deleteflow.png)

### <a name="delete-connections"></a>연결 삭제

커넥터는 API 및 SaaS 시스템과 통신하는 연결을 사용합니다. 연결에는 만든 사용자에 대한 참조가 포함됩니다. 사용자는 다음과 같은 단계를 사용하여 언제든지 이러한 참조를 삭제할 수 있습니다.

1. [Microsoft Flow](https://flow.microsoft.com)에 로그인하고, 기어 아이콘을 선택한 다음, **연결**을 선택합니다.

    ![이벤트 삭제](./media/gdpr-dsr-delete-msa/deleteconnections.png)

1. 삭제하려는 연결을 선택하고, **...** 를 선택한 다음, **삭제**를 선택합니다.

    ![이벤트 삭제](./media/gdpr-dsr-delete-msa/delete-connection.png)

1. 확인 프롬프트에서 **삭제** 아이콘을 선택합니다.

    ![이벤트 삭제](./media/gdpr-dsr-delete-msa/confirmdelete.png)

> [!NOTE]
> 다른 흐름에서 삭제할 연결을 사용하는 경우 새 연결이 필요하다는 알림이 수신됩니다. 그렇지 않은 경우 **삭제**를 선택하여 계속합니다.
>
>

## <a name="learn-more"></a>자세한 정보

* [Microsoft Flow](getting-started.md) 시작
* Microsoft Flow에서 [새로운 기능](release-notes.md) 알아보기
