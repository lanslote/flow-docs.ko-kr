---
title: "흐름 만들기를 통한 작업 자동화 | Microsoft Docs"
description: "누군가 SharePoint 목록에 행을 추가하는 등의 이벤트 발생 시 메일 보내기 같은 하나 이상의 작업을 자동으로 수행하는 흐름을 만듭니다."
services: 
suite: flow
documentationcenter: na
author: aftowen
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/28/2017
ms.author: deonhe
ms.openlocfilehash: fd6ed3973ed09442108bf780f76b750deea20eeb
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2017
---
# <a name="create-a-flow-in-microsoft-flow"></a>Microsoft Flow에서 흐름 만들기
<iframe width="560" height="315" src="https://www.youtube.com/embed/Gt3CMhLAQqE?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

이벤트에 의해 트리거된 후 하나 이상의 작업을 자동으로 수행하는 흐름을 만듭니다. 예를 들어, 누군가 사용자가 지정한 키워드가 포함된 트윗을 보내면 메일로 알리는 흐름을 만듭니다. 이 예제에서 트윗을 보내는 것은 이벤트이고, 메일을 보내는 것은 동작입니다.

## <a name="prerequisites"></a>필수 구성 요소
* [flow.microsoft.com](https://flow.microsoft.com) 계정
* Twitter 계정
* Office 365 자격 증명

## <a name="specify-an-event-to-start-the-flow"></a>흐름을 시작할 이벤트를 지정합니다.
첫째, 어떤 이벤트, 또는 *트리거*가 흐름을 시작할지 선택해야 합니다.

1. [flow.microsoft.com](https://flow.microsoft.com)의 위쪽 탐색 모음에서 **내 흐름**을 선택하고 **빈 페이지에서 만들기**를 선택합니다.
   
    ![왼쪽 탐색 모음의 흐름 옵션](./media/get-started-logic-flow/create-logic-flow.png)
2. **모든 커넥터 및 트리거 검색** 상자에 **Twitter**를 입력하거나 붙여 넣고 **Twitter - 새 트윗이 게시되었을 때**를 선택합니다.
   
    ![Twitter 이벤트](./media/get-started-logic-flow/twitter-search.png)
3. Twitter 계정을 Microsoft Flow에 아직 연결하지 않은 경우 **Twitter 로그인**을 선택하고 자격 증명을 입력합니다.
   
    ![Twitter 로그인](./media/get-started-logic-flow/twitter-signin.png)
4. **검색 텍스트** 상자에 찾으려는 키워드를 입력합니다.
   
    ![Twitter 키워드](./media/get-started-logic-flow/twitter-keyword.png)

## <a name="specify-an-action"></a>작업 지정
1. **+ 새 단계**를 선택한 다음 **작업 추가**를 선택합니다.
   
    ![작업 추가](./media/get-started-logic-flow/add-action-icon.png)
2. **모든 커넥터 및 작업 검색** 상자에 **메일 보내기**를 입력하거나 붙여 넣은 다음 **Office 365 Outlook - 메일 보내기**를 선택합니다.
   
    ![작업 목록](./media/get-started-logic-flow/send-email.png)
3. 메시지가 표시되면 로그인 단추를 선택하고 자격 증명을 입력합니다.
4. 표시되는 양식에서 전자 메일 주소를 **받는 사람** 상자에 입력 또는 붙여 넣은 다음, 표시되는 연락처 목록에서 이름을 선택합니다.
   
    ![빈 전자 메일 메시지](./media/get-started-logic-flow/blank-email.png)
5. **제목** 입력란에서 **새 트윗 출처:**를 입력하거나 붙여 넣은 다음, 공백을 입력합니다.
   
    ![자리 표시자가 있는 제목줄](./media/get-started-logic-flow/message-token.png)
6. 토큰 목록에서 **트윗됨** 토큰을 선택하여 해당 자리 표시자를 추가합니다.
   
    ![매개 변수 추가](./media/get-started-logic-flow/add-parameter.png)
7. **본문** 상자를 클릭하거나 탭한 다음 **텍스트 트윗** 토큰을 클릭하거나 탭하여 해당 자리 표시자를 추가합니다.
8. (선택 사항) 전자 메일 본문에 더 많은 토큰, 기타 콘텐츠 또는 둘 다를 추가합니다.
9. 화면 상단에서 흐름 이름을 지정한 다음 **흐름 만들기**를 선택합니다.
   
    ![흐름 만들기 단추를 선택합니다.](./media/get-started-logic-flow/create-button.png)
10. **완료**를 선택하여 흐름 목록을 업데이트합니다.
    
     ![완료 단추 선택](./media/get-started-logic-flow/done-button.png)
11. 표시한 키워드가 있는 트윗을 보냅니다.
    
     1분 안에 새 트윗을 알리는 이메일 메시지가 보내집니다.

## <a name="manage-a-flow"></a>흐름 관리
1. [flow.microsoft.com](https://flow.microsoft.com)의 상단 탐색 모음에서 **내 흐름**을 선택합니다.
2. 흐름 목록에서 다음 중 하나를 수행합니다.
   
   * 흐름을 일시 중지하려면 해당 토글을 **끄기**로 설정합니다.
     
       ![흐름 일시 중지](./media/get-started-logic-flow/pause-flow.png)
   * 흐름을 다시 시작하려면 해당 토글을 **켜기**로 설정합니다.
     
       ![흐름 다시 시작](./media/get-started-logic-flow/resume-flow.png)
   * 흐름을 편집하려면 편집하려는 흐름에 해당하는 연필 아이콘을 선택합니다.
     
       ![흐름 선택](./media/get-started-logic-flow/select-flow.png)
   * 흐름을 삭제하려면 **...** 아이콘을 선택하고, **삭제**를 선택한 후, 나타나는 메시지 상자에서 **삭제**를 선택합니다.
     
       ![삭제 아이콘](./media/get-started-logic-flow/delete-icon.png)
   * 흐름의 실행 기록을 보려면 **내 흐름** 페이지에서 흐름을 선택한 후 열리는 페이지의 **실행 기록** 섹션 아래에 있는 기록을 봅니다.
     
       ![실행 기록](./media/get-started-logic-flow/run-history.png)
     
     각 단계의 입출력을 확인하려면 실행 목록에서 흐름 실행을 선택합니다.

**참고**: 계정은 최대 50개의 흐름을 포함할 수 있습니다. 이미 50개가 있으면 다른 흐름을 만들기 전에 하나를 삭제합니다.

## <a name="next-steps"></a>다음 단계
* 흐름에 다른 알림 방법 등, [단계를 추가](multi-step-logic-flow.md)합니다.
* 동작을 매일, 특정 날짜 또는 일정 시간(분) 후에 발생하게 하려면 [일정에 따라 작업을 실행합니다](run-tasks-on-a-schedule.md).
* 앱이 클라우드에서 논리를 시작하게 하려면 [앱에 흐름을 추가합니다](https://powerapps.microsoft.com/tutorials/using-logic-flows/).
* [팀 흐름을 시작](create-team-flows.md)하고 사용자와 공동으로 작업할 다른 사람을 초대하여 흐름을 디자인합니다.

