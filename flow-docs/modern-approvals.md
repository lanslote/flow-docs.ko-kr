---
title: 간편하게 승인 워크플로를 자동화합니다. | Microsoft Docs
description: SharePoint, Dynamics CRM, Salesforce, 비즈니스용 OneDrive, Zendesk 또는 WordPress와 통합하는 승인 워크플로를 자동화합니다.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/20/2017
ms.author: deonhe
ms.openlocfilehash: bd89bca994a77072815a73ba1cbc7ba1db6955d3
ms.sourcegitcommit: 4a8d11e1768cd0ca96a60b6f5548a68c0c8999e5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38949726"
---
# <a name="create-and-test-an-approval-workflow-with-microsoft-flow"></a>Microsoft Flow를 사용하여 승인 워크플로를 만들고 테스트합니다.

Microsoft Flow에서는 SharePoint, Dynamics CRM, Salesforce, 비즈니스용 OneDrive, Zendesk 또는 WordPress를 포함한 여러 서비스에서 문서 또는 프로세스의 승인을 관리할 수 있습니다.

승인 워크플로를 만들려면 아무 흐름에 **승인 - 승인 시작** 작업을 추가합니다. 이 작업을 추가하면 흐름에서 문서 또는 프로세스의 승인을 관리할 수 있습니다. 예를 들어 송장, 작업 명령 또는 판매 견적을 승인하는 문서 승인 흐름을 만들 수 있습니다. 휴가 요청, 초과 근무 또는 여행 계획을 승인하는 프로세스 승인 흐름도 만들 수 있습니다.

승인자는 자신의 이메일 수신함, Microsoft Flow 웹 사이트의 [승인 센터](https://flow.microsoft.com/manage/approvals/received/) 또는 Microsoft Flow 앱에서 요청에 응답할 수 있습니다.

## <a name="create-an-approval-flow"></a>승인 흐름 만들기
다음은 우리가 만들고 테스트할 흐름의 개요입니다.

   ![흐름의 개요](./media/modern-approvals/create-flow-overview.png)

이 흐름은 다음 단계를 수행합니다.

1. 누군가가 SharePoint Online 목록에 휴가 요청을 만들면 시작됩니다.
2. 휴가 요청을 승인 센터에 추가한 후 그 요청을 승인자에게 전자 메일로 보냅니다.
3. 휴가를 요청한 사람에게 승인자의 결정 내용이 담긴 전자 메일을 보냅니다.
4. 승인자의 결정 내용을 SharePoint Online 목록에 업데이트합니다.

## <a name="prerequisites"></a>필수 구성 요소
이 연습을 완료하려면 다음에 액세스할 수 있어야 합니다.

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

SharePoint Online 목록에 다음 열을 만듭니다.

   ![SharePoint Online 목록 열](./media/modern-approvals/sharepoint-list-fields.png)

SharePoint Online 목록의 이름 및 URL을 기록해 둡니다. 이러한 항목은 나중에 **SharePoint - 항목이 만들어진 경우** 트리거를 구성할 때 필요합니다.

## <a name="create-your-flow-from-the-blank-template"></a>빈 템플릿으로 흐름 만들기
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>트리거 추가

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

**사이트 주소**와 **목록 이름**은 이 연습의 앞부분에서 언급한 항목입니다.

![SharePoint 정보](./media/modern-approvals/select-sharepoint-site-info.png)

## <a name="add-a-profile-action"></a>프로필 작업 추가

1. **+ 새 단계**를 선택한 다음 **작업 추가**를 선택합니다.
   
    ![새 단계](./media/modern-approvals/select-sharepoint-add-action.png)
2. **프로필**을 **작업 선택** 검색 상자에 입력합니다.
   
    ![프로필 검색](./media/modern-approvals/search-for-profile.png)
3. **Office 365 사용자-내 프로필 가져오기** 작업을 찾은 후 선택합니다.
   
    ![office 사용자 선택하기](./media/modern-approvals/select-my-profile.png)
4. 흐름에 대한 이름을 입력한 다음 지금까지 수행한 작업을 저장하기 위해 **흐름 만들기**를 선택합니다.
   
    ![흐름 저장](./media/modern-approvals/save.png)

## <a name="add-an-approval-action"></a>승인 작업 추가

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!NOTE]
> 이 작업은 승인 요청을 **할당 대상** 상자의 이메일 주소로 보냅니다.
>
>

## <a name="add-a-condition"></a>조건 추가

[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

## <a name="add-an-email-action-for-approvals"></a>승인을 위한 전자 메일 작업 추가

전자 메일을 보내 휴가 요청을 승인 받으려면 다음 단계를 따릅니다.

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![승인된 전자 메일 템플릿 구성](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-approved-requests"></a>승인된 요청에 대한 업데이트 작업 추가

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

> [!NOTE]
> **사이트 주소**, **목록 이름**, **Id** 및 **제목**이 필요합니다.
>
>

![항목 업데이트 구성](./media/modern-approvals/configure-update-item.png)

## <a name="add-an-email-action-for-rejections"></a>거부를 위한 전자 메일 작업 추가

[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

![거부된 요청에 대한 구성](./media/modern-approvals/configure-rejected-email.png)

## <a name="add-update-action-for-rejected-requests"></a>거부된 요청에 대한 업데이트 작업 추가

[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   > [!NOTE]
   > **사이트 주소**, **목록 이름**, **Id** 및 **제목**이 필요합니다.
   >
   >

![항목 업데이트 카드](./media/modern-approvals/configure-update-item-no.png)

1. 수행한 작업을 저장하려면 **흐름 업데이트**을 선택합니다.
   
    ![업데이트 작업 선별](./media/modern-approvals/update.png)

따라 했다면 사용자의 흐름이 이 스크린샷과 비슷해야 합니다.

![흐름의 개요](./media/modern-approvals/completed-flow.png)

이제 흐름을 만들었으니 테스트할 시간입니다!

## <a name="request-an-approval"></a>승인 요청

[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]

흐름을 만들고 테스트했으니, 다른 사람들에게 흐름 사용 방법을 알려주어야 합니다.

## <a name="learn-more"></a>자세한 정보

* [보류 중인 승인 요청](approve-reject-requests.md) 보기 및 관리
* [순차 승인 흐름](sequential-modern-approvals.md) 만들기.
* [병렬 승인 흐름](parallel-modern-approvals.md) 만들기.
* [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) 또는 [Windows Phone](https://aka.ms/flowmobilewindows)용 Microsoft Flow 모바일 앱 설치.
