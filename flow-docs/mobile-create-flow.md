---
title: 전화에서 흐름 만들기 | Microsoft Docs
description: 사용자가 지정한 주소에서 메일을 받으면 알림을 푸시하는 것처럼, 템플릿에서 흐름을 만들 수 있습니다.
services: ''
suite: flow
documentationcenter: na
author: adiregev
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/18/2016
ms.author: adiregev
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f87320c61427957c02ff75675e4e15b938ac99f4
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44688332"
---
# <a name="create-a-flow-from-your-phone-by-using-microsoft-flow"></a>Microsoft Flow를 사용하여 전화에서 흐름 만들기
서비스 목록 검색, 카테고리 탐색 또는 키워드 지정을 통해 찾을 수 있는 템플릿을 사용하여 전화에서 흐름을 만듭니다. 이 토픽의 단계에 따라, 상사에게 메일을 받으면 전화로 푸시 알림을 보내는 흐름을 만듭니다.

Microsoft Flow에 친숙하지 않은 경우 [개요를 살펴봅니다](getting-started.md).

## <a name="prerequisites"></a>사전준비
* [Microsoft Flow 계정](sign-up-sign-in.md)
* [지원되는 장치](getting-started.md#use-the-mobile-app)에 설치된 [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) 또는 [Windows Phone](https://aka.ms/flowmobilewindows)용 Microsoft Flow 모바일 앱. 이 토픽의 그래픽은 앱의 iPhone 버전이지만 Android 장치 또는 Windows Phone의 인터페이스도 비슷합니다.
* 이 토픽에서 설명한 템플릿을 사용하려면 다음도 필요합니다.
  
  * Office 365 자격 증명
  * 전화에서 푸시 알림 사용

## <a name="find-a-template"></a>템플릿 찾기
1. 모바일 앱을 연 다음 화면 아래쪽의 **찾아보기**를 누릅니다.
   
    ![찾아보기 아이콘](./media/mobile-create-flow/browse-icon.png)
   
    다음 방법 중 하나로 템플릿을 찾을 수 있습니다.
   
   * 화면 맨 위의 검색 상자에 키워드를 지정합니다.
   * 서비스 목록에서 옵션을 누릅니다.
   * 아래쪽으로 스크롤하여 여러 카테고리를 표시한 다음 카테고리의 템플릿을 누릅니다.
     
       ![찾아보기 탭](./media/mobile-create-flow/browse-tab.png)
     
     이 자습서에서는 상사로부터 메일을 받으면 푸시 알림을 보내는 템플릿을 엽니다.
2. 서비스 목록에서 **모두 보기**를 누립니다.
   
    ![서비스 목록 표시](./media/mobile-create-flow/list-services.png)
3. **푸시 알림**에 대한 아이콘을 누릅니다.
   
    ![푸시 알림](./media/mobile-create-flow/push-notifications.png)
4. 검색 표시줄에서 **전자 메일**을 입력한 다음 상사로부터 메시지를 받으면 푸시 알림을 보내는 템플릿을 누릅니다.
   
    ![템플릿 선택](./media/mobile-create-flow/choose-template.png)
5. 선택한 템플릿에 대한 상세 정보를 제공하는 화면에서 **이 템플릿 사용**을 누릅니다.
   
    ![템플릿 확인](./media/mobile-create-flow/confirm-template.png)

## <a name="finish-the-flow"></a>흐름 완료
1. 메시지가 표시되면 **로그인**을 누르고 Office 365 Outlook이나 Office 365 사용자 또는 두 가지 모두에 대한 자격 증명을 입력합니다.
   
    ![Office 365 로그인](./media/mobile-create-flow/office-signin.png)
   
    다른 흐름을 만들 때 동일한 연결을 사용할 수 있습니다.
2. 오른쪽 위 모서리에서 **다음**을 누릅니다.
   
    ![다음 누르기](./media/mobile-create-flow/next.png)
   
    다음 화면은 트리거 이벤트와 결과 동작을 보여 줍니다.
   
    ![트리거 이벤트 및 동작](./media/mobile-create-flow/flow-structure.png)
   
    이 템플릿에서 새 메일은 정보를 검색하고(상사 주소 포함) 해당 주소에서 메일을 받으면 푸시 알림을 보내는 흐름을 트리거합니다. 일부 템플릿은 제대로 사용하려면 몇 가지 사용자 지정이 필요하지만 이 템플릿은 그렇지 않습니다.
3. (선택 사항) 화면 맨 위에서 흐름에 대해 다른 이름을 지정합니다.
   
    ![흐름 이름 변경](./media/mobile-create-flow/rename-flow.png)
4. 오른쪽 위 모서리에서 **만들기**를 누릅니다.
   
    ![흐름 만들기](./media/mobile-create-flow/create-flow.png)
   
    흐름이 만들어지며 사용자가 해당 흐름을 일시 중지하거나 삭제할 때까지 상사가 보내는 메일을 확인합니다.

## <a name="next-steps"></a>다음 단계
* [흐름 활동을 모니터링](mobile-monitor-activity.md)합니다.
* [흐름을 관리](mobile-manage-flows.md)합니다.

