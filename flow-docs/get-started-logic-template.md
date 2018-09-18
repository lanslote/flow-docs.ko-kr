---
title: 템플릿에서 흐름 만들기 | Microsoft Docs
description: 여러 기본 제공 템플릿으로부터 흐름을 만듭니다.
services: ''
suite: flow
documentationcenter: na
author: aftowen
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/07/2017
ms.author: anneta
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 52aae570f65eaae537f548e686f437592eb5ef03
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689459"
---
# <a name="create-a-flow-from-a-template-in-microsoft-flow"></a>Microsoft Flow 템플릿에서 흐름 만들기
상사가 Office 365에서 전자 메일을 보내면 Slack 메시지를 보내는 것과 같이, 여러 기본 제공 템플릿에서 흐름을 만들 수 있습니다.

**참고:** 이미 정한 프로세스가 있으나 그에 대한 템플릿이 없는 경우 [처음부터 새로 흐름을 만듭니다](get-started-logic-flow.md).

**필수 구성 요소**

* [flow.microsoft.com](https://flow.microsoft.com) 계정
* Slack 계정
* Office 365 자격 증명

## <a name="choose-a-template"></a>템플릿 선택
<iframe width="560" height="315" src="https://www.youtube.com/embed/ZJK8cYdjAic?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. [flow.microsoft.com](https://flow.microsoft.com)의 상단 탐색 모음에서 **템플릿**을 선택합니다.
2. 검색 막대에 **Slack**을 입력한 다음 검색 아이콘을 선택합니다.
3. Slack과 관련한 템플릿만 표시되므로 **상사가 전자 메일을 보내면 Slack 메시지 보내기**를 선택할 수 있습니다.
   
    ![왼쪽 탐색 모음의 새 옵션 ](./media/get-started-logic-template/select-template.png)
4. 이 템플릿이 원하는 작업에 적합한지 확인한 다음 **이 템플릿 사용**을 선택합니다.
5. Office 또는 Slack에 로그인하지 않은 경우 **로그인**을 선택한 다음 지시를 따릅니다.
   
    ![템플릿에 필요한 연결 목록](./media/get-started-logic-template/confirm-connections.png)
6. 연결을 확인한 후 **계속**을 선택합니다.
   
    주황 제목 표시줄로 각 작업을 보여주는 흐름이 표시됩니다.
   
    ![템플릿의 기본 이벤트 및 동작](./media/get-started-logic-template/template-default.png)

## <a name="customize-your-flow"></a>흐름 사용자 지정
1. 이벤트의 제목 표시줄을 선택하여 확장한 다음 사용자 지정합니다(예: 나와 관련이 있는 전자 메일에 대해 필터 지정).
2. 사용자 입력이 필요한 동작은 자동으로 확장됩니다.
   
    예를 들어 **메시지 게시** 동작은 *\@username* 등의 채널을 입력해야 하므로 확장됩니다. 메시지 콘텐츠를 사용자 지정할 수도 있습니다. 기본적으로 메시지는 제목만 포함하지만 다른 정보도 넣을 수 있습니다.
   
    ![Slack에 대한 채널 지정](./media/get-started-logic-template/specify-keyword.png)
3. 화면 상단에서 흐름의 이름을 지정한 다음 **흐름 만들기**를 선택합니다.
4. 마지막으로 흐름이 만족스러우면 **완료**를 선택합니다.
   
    ![완료 단추](./media/get-started-logic-template/done.png)

이제 상사가 전자 메일을 보냈을 때, 사용자가 지정한 정보가 담긴 Slack 메시지를 받을 수 있습니다.

## <a name="next-steps"></a>다음 단계
* [작동 중인 흐름 보기](see-a-flow-run.md)
* [자체 템플릿 게시](publish-a-template.md)
* [Microsoft Common Data Service에 템플릿 사용](common-data-model-intro.md)
* [팀 흐름을 시작](create-team-flows.md)하고 사용자와 공동으로 작업할 다른 사람을 초대하여 흐름을 디자인합니다.

