---
title: 최신 병렬 승인 워크플로 만들기 | Microsoft Docs
description: 최신 병렬 승인 워크플로 만들기
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/09/2018
ms.author: deonhe
ms.openlocfilehash: 43b748332a649e5f8d8db5fbe11f53522ce8bb79
ms.sourcegitcommit: 4a8d11e1768cd0ca96a60b6f5548a68c0c8999e5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38949749"
---
# <a name="create-parallel-approval-workflows-with-microsoft-flow"></a>Microsoft Flow를 사용하여 병렬 승인 워크플로 만들기

병렬 승인 워크플로에서 송장, 구매 주문, 휴가 요청 등과 같은 항목을 승인하는 데 여러 사용자가 필요합니다. 각 사용자의 승인은 다른 모든 승인자와 무관합니다.

이 연습에서 Microsoft Flow를 사용하여 병렬 승인 워크플로를 자동화하는 흐름을 만듭니다. 이 흐름은 직원이 정기적으로 지원하는 모든 사용자(또는 팀)의 승인이 필요한 직원 휴가 요청 프로세스를 자동화합니다. 직원은 [SharePoint 목록](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7)을 사용하여 휴가를 요청합니다. 직원의 직속 관리자, 판매 팀 및 인사 팀의 휴가 승인이 필요합니다. 휴가 요청을 결정하기 위해 각 승인자에게 라우팅됩니다. 흐름은 상태를 변경한 전자 메일을 보낸 다음 결정을 SharePoint에 업데이트합니다.

## <a name="prerequisites"></a>필수 구성 요소

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

사용자는 SharePoint Online 목록을 만들 때 다음 열을 포함해야 합니다.

   ![SharePoint 목록 열](./media/parallel-modern-approvals/sharepoint-columns.png)

SharePoint Online 목록의 이름 및 URL을 기록해 둡니다. 나중에 이러한 항목을 사용하여 **SharePoint - 항목이 만들어진 경우** 트리거를 구성합니다.

## <a name="create-your-flow-from-the-blank-template"></a>빈 템플릿으로 흐름 만들기

[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>트리거 추가

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![SharePoint 정보](includes/media/parallel-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>휴가를 요청한 사용자에 대한 관리자를 가져옵니다.

[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

## <a name="name-and-save-your-flow"></a>흐름에 이름 지정 및 저장

1. 흐름에 대한 이름을 입력한 다음, **저장** 아이콘을 선택하여 지금까지 수행한 작업을 저장합니다.

   ![흐름 저장](./media/parallel-modern-approvals/save.png)

> [!NOTE]
> 주기적으로 **저장** 아이콘을 선택하여 변경 내용을 흐름에 저장합니다.
> 
> 


## <a name="add-an-approval-action-for-immediate-manager"></a>즉시 관리자에게 승인 작업 추가

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!IMPORTANT]
> 이 작업은 **할당 대상** 상자의 이메일 주소로 휴가 요청을 보내므로 **관리자(v2) 가져오기** 목록에서 **이메일** 토큰을 삽입합니다.
> 
> 

## <a name="insert-a-parallel-branch-approval-action-for-the-sales-team"></a>영업 팀에 병렬 분기 승인 작업 삽입

1. **관리자(v2) 가져오기** 및 **승인 시작** 카드 사이에 있는 아래쪽 화살표를 선택합니다.
2. 선택한 다음 아래쪽 화살표에 표시되는 더하기 기호를 선택합니다.
3. **병렬 분기 추가**를 선택합니다.
4. **작업 추가**를 선택합니다.

    ![관리자 구성 가져오기](./media/parallel-modern-approvals/add-parallel-branch.png)
5. 영업 팀에 휴가 요청을 보내는 **승인 시작** 작업을 검색하고 선택한 다음 구성합니다. **승인 시작** 작업을 추가하는 방법을 잘 모르는 경우 [즉시 관리자에게 승인 작업을 추가하는 데 사용한 단계](parallel-modern-approvals.md#add-an-approval-action-for-immediate-manager)를 참조하세요.

> [!IMPORTANT]
> **승인 2 시작** 작업의 **할당 대상** 상자에서 영업 팀의 이메일 주소를 사용합니다.
> 
> 

## <a name="insert-a-parallel-branch-approval-action-for-the-human-resources-team"></a>인사 팀에 병렬 분기 승인 작업 삽입

1. [영업 팀에 병렬 분기를 삽입하는](parallel-modern-approvals.md#insert-a-parallel-branch-approval-action-for-the-sales-team) 단계를 반복하여 인사 팀에 휴가 요청을 보내도록 **승인 시작** 작업을 추가한 다음 구성합니다.

> [!IMPORTANT]
> **승인 3 시작** 작업의 **할당 대상** 상자에서 인사 팀의 이메일 주소를 사용합니다.
> 
> 

따라 했다면 사용자의 흐름이 이 예제와 비슷해야 합니다.

   ![병렬 분기에서 흐름](./media/parallel-modern-approvals/flow-with-parallel-branches.png)

## <a name="options-after-adding-parallel-branches"></a>병렬 분기를 추가한 후의 옵션

병렬 분기에 작업을 추가한 후에 흐름에 더 많은 단계를 추가하는 데는 두 가지 옵션이 있습니다.

1. 작은 **새 단계 삽입** 단추를 사용합니다(분기의 공백 또는 분기 바로 아래의 영역을 선택한 경우 표시되는 원형 더하기 단추). 이 단추는 **특정 분기**에 단계를 추가합니다. 이 단추를 사용하여 추가한 단계는 이 특정 분기가 완료된 후에 실행됩니다.
1. 전체 워크플로의 맨 아래에서 더 큰 **새 단계** 단추를 사용합니다. 이 단추를 사용하여 추가한 단계는 모든 분기가 완료된 후에 실행됩니다.

다음 섹션에서는 작은 **새 단계 삽입** 단추를 사용하여 각 분기에서 다음 단계를 수행합니다.

* 휴가 요청이 승인되었는지 여부를 확인하는 조건을 추가합니다.
* 결정을 직원에게 알려주는 전자 메일을 보냅니다.
* 승인 결정을 SharePoint의 휴가 요청에 업데이트합니다.

그런 다음 큰 **새 단계** 단추를 사용하여 휴가 요청에 대한 모든 결정을 요약하는 전자 메일을 보냅니다.

계속 진행하겠습니다.

## <a name="add-a-condition-to-each-branch"></a>각 분기에 조건 추가

1. **승인 시작** 분기에서 공백을 선택합니다.
2. 작은 **새 단계 삽입** 단추를 선택합니다(이전 단계에서 공백을 선택한 후에 표시된 원형 더하기 단추).
3. 표시되는 메뉴에서 **조건 추가**를 선택합니다.
4. **조건** 카드에서 첫 번째 상자를 선택한 다음 동적 콘텐츠 목록의 **승인 시작** 범주에서 **응답** 토큰을 선택합니다.

    ![병렬 분기 조건에서 흐름](./media/parallel-modern-approvals/configure-approval-condition.png)
5. 목록이 **동등한 대상**으로 설정되었는지 확인합니다(**조건 카드** 가운데에서).
6. 마지막 상자에 **승인**을 입력합니다(이 텍스트는 대/소문자 구분).
7. 이제 조건 카드는 이 예제와 비슷해야 합니다.

    ![병렬 분기 조건에서 흐름](includes/media/parallel-modern-approvals/condition-card.png)

   > [!NOTE]
   > 이 상태는 직원의 관리자로 이동하는 **승인 시작** 작업에서 응답을 확인합니다.
   > 
   > 
8. **승인 시작 2**(판매 승인 요청) 및 **승인 시작 3**(인사 승인 요청) 분기에서 위의 단계를 반복합니다.

## <a name="add-email-actions-to-each-branch"></a>각 분기에 전자 메일 작업 추가

**조건** 분기의 **IF YES**(예인 경우) 쪽에서 다음 단계를 수행합니다.

   참고: 요청이 승인되면 흐름은 전자 메일을 보내는 다음과 같은 단계를 사용합니다.

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![사전 승인된 전자 메일 템플릿 구성](includes/media/parallel-modern-approvals/yes-email-config.png)

요청이 거부될 때 이메일을 보내려면 **조건** 분기의 **IF NO**(아니요인 경우) 쪽을 사용한 다음, 이전 단계를 반복하여 거부 이메일에 대한 템플릿을 추가합니다.

**승인 시작 2**(판매 승인 요청) 및 **승인 시작 3**(인사 승인 요청) 분기에서 위의 단계를 반복합니다.

## <a name="update-the-vacation-request-with-the-decision"></a>결정을 휴가 요청에 업데이트

결정을 내릴 때 SharePoint를 업데이트하는 다음 단계를 수행합니다.

   참고: 분기의 **그러한 경우** 및 **아닌 경우** 둘 다에서 이러한 단계를 수행해야 합니다.

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

   ![항목 업데이트 구성](./media/parallel-modern-approvals/configure-update-item.png)

**승인 시작 2** 및 **승인 시작 3** 분기에서 위의 단계를 반복합니다.

## <a name="complete-the-flow"></a>흐름 완료

1. **새 단계** > **작업 추가**를 선택합니다.

    ![항목 업데이트 구성](includes/media/parallel-modern-approvals/add-an-action-2-step.png)
1. 이전에 제공 하는 단계를 사용하여 각 승인의 결과를 요약하는 전자 메일을 보냅니다. 휴가를 요청한 직원에게 이 전자 메일을 보냅니다. 카드는 이 예제와 유사할 수 있습니다.

   ![항목 업데이트 구성](./media/parallel-modern-approvals/final-email-card.png)

## <a name="learn-more-about-modern-approvals"></a>최신 승인에 대한 자세한 정보

[최신 승인 소개](modern-approvals.md)

