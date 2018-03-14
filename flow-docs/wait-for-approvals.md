---
title: "흐름에서 승인 대기 | Microsoft Docs"
description: "흐름은 결정에 대한 알림을 보내는 등의 동작을 수행하기에 앞서, 사용자가 변경 내용 승인 또는 거부 등과 같은 외부 이벤트의 발생을 대기할 수 있습니다."
services: 
suite: flow
documentationcenter: na
author: merwanhade
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2018
ms.author: merwanhade
ms.openlocfilehash: b75cacf14da7d1b339e8a2f9e35eece389c2a6f7
ms.sourcegitcommit: 22a883c30c859b6193fc2a619e753d71247f5e15
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2018
---
# <a name="wait-for-approval-in-microsoft-flow"></a>Microsoft Flow에서 승인 대기

> [!VIDEO https://www.youtube.com/embed/W6oxcYRtW-8?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF]
>


SharePoint에서 항목을 만든 경우 승인 이메일을 보낸 다음, 항목의 승인 또는 거부 여부를 알리는 흐름을 만듭니다. 이 자습서를 정확하게 따라 하려면 트리거 동작처럼 간단한 SharePoint 목록을 만듭니다. 그러나 Dropbox나 OneDrive 같은 다른 데이터 원본도 사용할 수 있습니다.

**필수 구성 요소**

* 이름이 **프로젝트 추적기**로 지정된 간단한 SharePoint Online 목록을 만들고, 이름 **제목**으로 지정된 열을 추가한 다음, 이름이 **할당 대상**으로 지정된 개인 또는 그룹 열을 추가합니다.

   ![Project Tracker SPO 목록 이미지](./media/wait-for-approvals/project-tracker.png)

## <a name="add-an-event-to-trigger-the-flow"></a>흐름을 트리거하는 이벤트 추가

1. [Microsoft Flow](https://flow.microsoft.com)로 로그인하고, 위쪽 탐색 모음에서 **내 흐름**을 선택한 다음, **빈 페이지에서 만들기**를 선택합니다.

1. **수백 개의 커넥터 및 트리거 검색** 상자를 선택하고, **새 항목**을 입력한 다음, **SharePoint - 항목이 만들어질 때**로 이동합니다.

1. 메시지가 표시되면 SharePoint에 로그인합니다.
1. **사이트 주소** 아래에 목록에 포함된 SharePoint 사이트의 URL을 입력합니다.

1. **목록 이름** 아래에서 이전에 만든 목록을 선택합니다. 그러면 **프로젝트 추적기**라는 이름이 지정됩니다.

    ![SPO 목록 이름 이미지](./media/wait-for-approvals/SPO-list-name.png)

## <a name="add-the-resulting-action"></a>결과 동작 추가

1. **새 단계** 단추를 선택한 다음, **작업 추가**를 선택합니다.

1. **모든 커넥터 및 작업 검색** 상자에 **이메일 보내기**를 입력하거나 붙여 넣은 다음, **Office 365 Outlook - 옵션이 있는 이메일 보내기**를 선택합니다.

1. 메시지가 표시되면 Office 365 Outlook에 로그인합니다.

1. **받는 사람** 필드를 선택한 다음, **이메일에 할당**을 선택합니다.

    **할당 대상** 열의 사용자는 항목을 승인 또는 거부하는 이메일을 받게 됩니다. 흐름을 테스트하기 위해 항목을 만들 때 이 필드에 자기 자신을 지정합니다. 이렇게 하면 항목을 승인 또는 거부할 뿐 아니라 알림 이메일도 받게 됩니다.

    > [!NOTE]
    > **제목** 및 **사용자 옵션** 필드를 요구에 맞게 사용자 지정할 수 있습니다.

    ![승인 전자 메일 받는 사람 필드 이미지](./media/wait-for-approvals/send-approval-email-to.png)

## <a name="add-a-condition"></a>조건 추가

1. **새 단계** 단추를 선택한 다음, **조건 추가**를 선택합니다.

    ![조건 추가 이미지](./media/wait-for-approvals/add-a-condition.png)
1. 첫 번째 상자를 선택한 다음, **SelectedOption** 토큰을 선택합니다.
1. 마지막 상자를 선택한 다음, **승인**을 입력합니다.

    ![조건 카드의 이미지](./media/wait-for-approvals/condition-card-2.png)

1. **예인 경우** 영역에서 **동작 추가**를 선택합니다.

1. **모든 커넥터 및 작업 검색** 상자에 **이메일 보내기**를 입력하거나 붙여 넣은 다음, **Office 365 Outlook - 이메일 보내기**를 선택합니다.

1. **받는 사람** 필드에 **만든 사람 이메일**과 같은 받는 사람을 입력합니다.

1. **제목** 상자에서 제목을 지정합니다.

    예를 들어 **DisplayName에게 할당됨**을 선택하고 한 쪽마다 공백을 포함하여 **승인함**을 입력한 다음 **제목**을 선택합니다.

1. **본문** 상자에서 **프로젝트의 다음 단계를 진행할 수 있음**과 같은 전자 메일 본문을 지정합니다.

    > [!NOTE]
    > SharePoint 목록에서 항목을 만든 사람에게 프로젝트의 승인 또는 거부 여부를 알립니다.

    ![예-전자 메일-보내기 이미지](./media/wait-for-approvals/if-yes-send-email-card-3.png)

1. **아니요인 경우** **제목** 및 **본문**을 변경하는 단계를 제외한 마지막 다섯 단계를 수행하여 프로젝트 거부를 반영합니다. 

     ![아니요-전자 메일-보내기 이미지](./media/wait-for-approvals/no-send-email-2.png)

## <a name="finish-and-test-your-flow"></a>흐름 완료 및 테스트

1. 흐름에 이름을 지정한 다음 **흐름 만들기**를 선택합니다.

     ![흐름 만들기 이미지](./media/wait-for-approvals/create-flow.png)
1. SharePoint 목록에서 항목을 만듭니다.

    지정한 받는 사람에게 승인 이메일을 보냅니다. 받는 사람이 이메일에서 **승인** 또는 **거부**를 선택하면 응답을 나타내는 이메일을 받게 됩니다.

## <a name="learn-more"></a>자세한 정보

* [단일 승인자 최신 승인 연습](modern-approvals.md)
* [순차 승인](sequential-modern-approvals.md) 만들기
* [병렬 승인](parallel-modern-approvals.md) 만들기
* [실행 중인 요청](mobile-approvals.md) 승인
