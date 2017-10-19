---
title: "Microsoft Flow를 사용하여 승인 요청 | Microsoft Docs"
description: "Microsoft Flow를 사용하여 승인 워크플로를 관리하는 방법을 알아봅니다."
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: o-pgEBW3fOI
courseduration: 14m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2016
ms.author: deonhe
ms.openlocfilehash: 049b713ed653ab5555e5f48f63e46cce7f3207ee
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2017
---
# <a name="approval-requests"></a>승인 요청
Microsoft Flow는 **알림을 받고**, **파일을 복사**하고 **데이터를 수집**하는 데 도움이 될 뿐만 아니라 **승인 프로세스를 간소화**할 때에도 도움이 됩니다.

## <a name="vacation-scenario"></a>휴가 시나리오
팀의 **관리자**로서 사용자가 팀의 직원에게 **SharePoint 목록**에 **휴가 요청서**를 만들도록 요청한다고 가정해 보겠습니다. 이제 이러한 목록 항목과 관련하여 **승인 프로세스**를 만들면 새 휴가 요청은 **신속하게 처리되고** 요청자는 **자동으로 알림을 받습니다**.  

## <a name="sharepoint-and-microsoft-flow"></a>SharePoint 및 Microsoft Flow
**SharePoint**에서 Microsoft Flow가 **기본 제공**됩니다.  **SharePoint 목록**에서 드롭다운에서 **Flow**를 클릭한 다음 **흐름을 만듭니다**.

![흐름 만들기](./media/learning-approvals/new-flow.png)   

**오른쪽 메뉴**에서 이와 같이 **템플릿**을 찾습니다.

![승인 템플릿](./media/learning-approvals/approval-template.png)

## <a name="using-the-template"></a>템플릿 사용
템플릿에서 **SharePoint**를 트리거하면 항목 정보가 **미리 채워집니다**.  **승인자**를 위해 **전자 메일 주소**를 추가하기만 하면 됩니다.  이 과정에서 **원래 SharePoint 항목이 변경되지는 않습니다**.  따라서 **SharePoint-업데이트 항목** 작업을 추가해야 합니다.

![항목 업데이트](./media/learning-approvals/update-item.png)

emailScope 보내기의 분기가 **없는 경우**는 어떨까요?  기본적으로는 그런 일은 없습니다.  메시지 요청을 만든 사용자에게 요청이 거부되었음을 알리는 메시지를 보내는 작업을 추가할 수 있습니다. 

![없는 경우](./media/learning-approvals/if-no.png)

## <a name="next-lesson"></a>다음 단원
이제을 이 섹션에서 학습한 내용을 검토합시다.

