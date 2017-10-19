---
title: "여러 승인자를 사용하여 최신 승인 워크플로 만들기 | Microsoft Docs"
description: "여러 승인자를 사용하여 최신 승인 워크플로 만들기 "
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
ms.date: 06/08/2017
ms.author: deonhe
ms.openlocfilehash: 8620cd49f9e19f6641909fcab3103568d148e565
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2017
---
# <a name="manage-sequential-approvals-with-microsoft-flow"></a>Microsoft Flow를 사용하여 순차적 승인 관리
일부 워크플로는 최종 승인자를 로그오프하기 전에 사전 승인이 필요합니다. 예를 들어 재무 부서에서 $1000.00가 넘는 송장을 승인하기 전에 회사에는 이에 대한 사전 승인이 필요한 순차적 승인 정책이 있을 수 있습니다.

이 연습에서는 직원 휴가 요청을 관리하는 순차적 승인 흐름을 만듭니다.

## <a name="detailed-steps-in-the-flow"></a>흐름의 자세한 단계
흐름은 다음과 같이 작동합니다.

1. [SharePoint Online 목록](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7)에 휴가 요청이 만들어질 때 시작됩니다.
2. 휴가 요청을 승인 센터에 추가한 후 그 요청을 사전 승인자에게 전자 메일로 보냅니다.
3. 직원에게 사전 승인 결정을 전자 메일로 보냅니다.
4. 사전 승인자의 결정과 의견을 SharePoint Online 목록에 업데이트합니다.
   
   참고: 요청이 사전 승인된 경우 흐름은 다음과 같은 단계를 진행합니다.
5. 최종 승인자에 요청을 보냅니다.
6. 직원에게 최종 결정을 전자 메일로 보냅니다.
7. 최종 의사 결정을 SharePoint 목록에 업데이트합니다.

이 이미지에서는 앞의 단계를 요약합니다.

   ![흐름의 visio 다이어그램](./media/sequential-modern-approvals/visio-overview.png)

## <a name="prerequisites"></a>필수 구성 요소
[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

사용자는 SharePoint Online 목록을 만들 때 다음 열을 포함해야 합니다.

   ![SharePoint 목록 열](./media/sequential-modern-approvals/sharepoint-columns.png)

SharePoint Online 목록의 이름 및 URL을 기록해 둡니다. 나중에 **SharePoint-새 항목이 만들어진 경우** 트리거를 구성할 때 이러한 항목을 사용합니다.

## <a name="create-your-flow-from-the-blank-template"></a>빈 템플릿으로 흐름 만들기
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>트리거 추가
[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![sharepoint 정보](./media/sequential-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>휴가를 요청한 사용자에 대한 관리자를 가져옵니다.
[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

1. 흐름에 대한 이름을 입력한 다음 지금까지 수행한 작업을 저장하기 위해 **흐름 만들기**를 선택합니다.
   
    ![흐름 저장](./media/sequential-modern-approvals/save.png)
   
   > [!NOTE]
   > 정기적으로 화면 맨 위에서 **흐름 업데이트**를 선택하고 흐름에 변경 내용을 저장합니다.
   > 
   > 
   
    ![업데이트 작업 선별](./media/sequential-modern-approvals/update.png)

각 작업을 저장한 후에 화면 위쪽에서 **흐름 편집**을 선택한 다음 계속 변경합니다.

## <a name="add-an-approval-action-for-pre-approvals"></a>사전 승인을 위한 승인 작업 추가
[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

참고: 이 작업은 사전 승인 요청을 **할당 대상** 상자의 전자 메일 주소로 보냅니다.

## <a name="add-a-condition"></a>조건 추가
[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

> [!NOTE]
> 이 상태는 **승인 시작** 작업에서 응답을 확인합니다.
> 
> 

## <a name="add-an-email-action-for-pre-approvals"></a>사전 승인을 위한 전자 메일 작업 추가
[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![사전 승인된 전자 메일 템플릿 구성](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-pre-approved-requests"></a>사전 승인된 요청에 업데이트 작업 추가
[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

   ![항목 업데이트 구성](./media/sequential-modern-approvals/configure-update-item.png)

## <a name="get-the-pre-approvers-manager"></a>사전 승인자의 관리자 가져오기
1. 앞서 수행한 [휴가를 요청한 사람에게 관리자 가져오기](sequential-modern-approvals.md#get-the-manager-for-the-person-who-created-the-vacation-request) 단계를 사용하여 다른 **관리자 가져오기** 작업을 추가하고 구성합니다. 이번에는 사전 승인자의 관리자를 가져옵니다.
2. 작업을 완료하면 **관리자 가져오기 2** 카드가 이 이미지와 유사하게 표시됩니다. **이 흐름에서 사용되는 앱 및 서비스에서 동적 콘텐츠 추가** 카드의 **관리자 가져오기** 범주에서 **전자 메일** 토큰을 사용해야 합니다.
   
   ![사전 승인자의 관리자 가져오기](includes/media/modern-approvals/get-pre-approver-manager.png)

## <a name="add-the-final-approval-action"></a>최종 승인 작업 추가
1. 이전에 수행한 [사전 승인을 위한 승인 작업 추가](sequential-modern-approvals.md#add-an-approval-action-for-pre-approvals) 단계를 사용하여 다른 **승인 시작** 작업을 추가한 다음 구성합니다. 이 작업은 최종 승인을 위한 전자 메일 요청을 보냅니다.
2. 작업을 완료하면 카드가 이 이미지와 비슷하게 표시됩니다.
   
    ![승인 구성](./media/sequential-modern-approvals/provide-approval-config-info.png)

## <a name="add-the-final-approval-condition"></a>최종 승인 조건 추가
1. [조건 추가](sequential-modern-approvals.md#add-a-condition) 단계를 반복하여 최종 승인자의 결정을 확인하는 **조건**을 추가하고 구성합니다.

## <a name="send-email-with-final-approval"></a>최종 승인을 포함한 전자 메일 보내기
1. [사전 승인을 위한 전자 메일 작업 추가](sequential-modern-approvals.md#add-an-email-action-for-pre-approvals) 단계를 사용하여 휴가 요청이 승인될 때 전자 메일을 보내는 작업을 추가하고 구성합니다.
2. 작업을 완료하면 카드가 이 이미지와 비슷하게 표시됩니다.
   
   ![최종 승인 전자 메일 템플릿](./media/sequential-modern-approvals/vacatioin-request-approved-email-template.png)

## <a name="update-sharepoint-with-approval"></a>승인을 SharePoint에 업데이트
1. [사전 승인된 요청에 업데이트 작업 추가](sequential-modern-approvals.md#add-an-update-action-for-pre-approved-requests) 단계를 사용하여 휴가 요청이 승인될 때 SharePoint를 업데이트하는 동작을 추가하고 구성합니다.
2. 작업을 완료하면 카드가 이 이미지와 비슷하게 표시됩니다.
   
    ![항목 업데이트 구성](./media/sequential-modern-approvals/configure-update-item-approved.png)

## <a name="send-email-with-pre-approval-rejection"></a>사전 승인 거부를 포함한 전자 메일 보내기
[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

   ![거부된 요청에 대한 구성](./media/sequential-modern-approvals/configure-rejected-email.png)

참고: 이 작업 **조건** 카드 아래에서 **아니면 아무 작업도 수행하지 않음** 분기에 추가되어야 합니다.

## <a name="update-sharepoint-with-pre-approval-rejection"></a>사전 승인 거부를 SharePoint에 업데이트
[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   ![거부된 요청에 대한 SharePoint 업데이트](./media/sequential-modern-approvals/update-sharepoint-with-rejection.png)

## <a name="send-email-with-final-rejection"></a>최종 거부를 포함한 전자 메일 보내기
1. [사전 승인 거부를 포함한 전자 메일 보내기](sequential-modern-approvals.md#send-email-with-pre-approval-rejection) 단계를 사용하여 최종 승인자가 휴가 요청을 거부하는 경우 전자 메일을 보내는 작업을 추가하고 구성합니다.
   
    참고: 이 작업 **조건 2** 카드 아래에서 **아니면 아무 작업도 수행하지 않음** 분기에 추가되어야 합니다.
2. 작업을 완료하면 카드가 이 이미지와 비슷하게 표시됩니다.
   
   ![거부된 요청에 대한 구성](./media/sequential-modern-approvals/final-rejection-email-card.png)

## <a name="update-sharepoint-with-final-rejection"></a>최종 거부를 SharePoint에 업데이트
1. [사전 승인 거부를 포함한 SharePoint 업데이트](sequential-modern-approvals.md#update-sharepoint-with-pre-approval-rejection) 단계를 사용하여 최종 승인자가 휴가 요청을 거부하는 경우 SharePoint를 업데이트하는 작업을 추가하고 구성합니다.
2. 작업을 완료하면 카드가 이 이미지와 비슷하게 표시됩니다.
   
   ![항목 업데이트 카드](./media/sequential-modern-approvals/final-rejection-update-sharepoint.png)
3. 수행한 작업을 저장하려면 **흐름 업데이트**을 선택합니다.
   
   ![업데이트 작업 선별](./media/sequential-modern-approvals/update.png)

따라 했다면 사용자의 흐름이 이 이미지 비슷해야 합니다.

![흐름의 개요](./media/sequential-modern-approvals/completed-flow.png)

흐름을 만들었으므로 이제 작동하는지 확인합니다.

## <a name="request-an-approval"></a>승인 요청
[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]

사용자 요청은 이 이미지와 비슷해야 합니다.

![휴가 요청](./media/sequential-modern-approvals/vacation-request.png)

## <a name="view-pending-approval-requests"></a>보류 중인 승인 요청 보기
[!INCLUDE [view-pending-approvals](includes/view-pending-approvals.md)]

## <a name="pre-approve-a-request"></a>요청 사전 승인
[!INCLUDE [approve-request-from-different-locations](includes/approve-request-from-different-locations.md)]

## <a name="approve-the-request"></a>요청 승인
요청을 승인하는 단계는 [요청을 사전 승인](sequential-modern-approvals.md#pre-approve-a-request)하는 단계와 동일합니다.

참고: 최종 승인자는 요청이 사전 승인된 후에만 휴가 요청을 가져옵니다.

## <a name="reject-a-request"></a>요청 거부
[!INCLUDE [reject-a-request](includes/reject-a-request.md)]

## <a name="more-information"></a>자세한 내용
[단일 승인자 최신 승인 연습](modern-approvals.md)

