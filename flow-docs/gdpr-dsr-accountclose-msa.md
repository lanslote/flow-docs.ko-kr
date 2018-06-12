---
title: MSA(Microsoft 계정)에 대한 Microsoft Flow GDPR 데이터 주체 계정 종료 요청 | Microsoft Docs
description: Microsoft Flow를 사용하여 MSA(Microsoft 계정)에 대한 GDPR 데이터 주체 계정 종료 요청에 응답하는 방법을 알아봅니다.
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
ms.openlocfilehash: 268e6039b4f2dbb43522fd07b1120d8c4256e9af
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34563259"
---
# <a name="responding-to-gdpr-data-subject-account-close-requests-for-microsoft-flow"></a>Microsoft Flow에 대한 GDPR 데이터 주체 계정 종료 요청에 응답

개인 데이터를 **삭제할 권한**은 GDPR의 핵심 보호입니다. 이 권한에는 감사 로그 정보를 제외한 모든 개인 데이터를 제거하는 권한이 포함됩니다. 사용자가 자신의 MSA(Microsoft 계정)을 종료하도록 결정하는 경우 사용자의 기본 데이터도 삭제됩니다.

이러한 리소스에는 사용자가 MSA를 종료할 때 자동으로 삭제되는 개인 데이터가 포함됩니다.

|개인 데이터를 포함하는 리소스|
|------|
|제품 및 서비스 작업|
|실행 기록|
|흐름|
|작업 피드|
|사용자 세부 정보|
|연결|

## <a name="account-close-requests"></a>계정 종료 요청

이러한 단계에서는 GDPR에 대한 자체 계정 종료 요청을 처리하는 방법을 설명합니다.

1. Microsoft 계정을 사용하여 [Microsoft 계정 종료 포털](http://go.microsoft.com/fwlink/?LinkId=523898)에 로그인한 다음, **다음**을 선택합니다.

    > [!NOTE]
    > 기존 구독을 취소하거나 기존 서비스에서 구독하려는 서비스로 데이터를 내보내도록 알림을 수신합니다.
    >
    >

    ![구독 취소](./media/gdpr-dsr-delete-msa/accountclose.png)

1. MSA를 종료하는 경우 발생하는 영향을 이해한 다음, **종료할 계정 표시**를 선택합니다.

    계정이 30일 이내에 종료된다고 나타내는 알림이 표시됩니다. 30일 동안 언제든지 이 계정을 다시 시작할 수 있습니다.

    ![계정 종료](./media/gdpr-dsr-delete-msa/accountclosed.png)

    30일 기간이 끝나면 이 MSA에 대한 모든 Microsoft Flow 리소스를 삭제하는 프로세스가 시작됩니다.

## <a name="learn-more"></a>자세한 정보

* [Microsoft Flow](getting-started.md) 시작
* Microsoft Flow에서 [새로운 기능](release-notes.md) 알아보기
