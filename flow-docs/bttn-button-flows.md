---
title: "bttns를 사용하여 흐름 시작 | Microsoft Docs"
description: "bttn을 사용하여 흐름을 시작하는 방법 알아보기"
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/30/2017
ms.author: deonhe
ms.openlocfilehash: c4010f95ad2db3c4f3b97b39f0b45934c7b69c48
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2017
---
# <a name="run-your-flows-with-physical-buttons-bttns-from-the-button-corporation-preview"></a>Button Corporation(미리 보기)에서 실제 단추(bttns)를 사용하여 흐름 실행
[Button Corporation](https://my.bt.tn/)에서 만든 실제 단추인 bttn을 눌러 흐름을 트리거합니다. 예를 들어 다음과 같은 작업을 수행하기 위해 흐름을 트리거하는 bttn을 누를 수 있습니다.

* 위치 정보를 사용하여 기술 지원팀에 연결
* 팀에 전자 메일 보내기
* 캘린더 차단
* 공급 다시 정렬

> [!IMPORTANT]
> 흐름에서 사용하기 전에 bttn을 [등록](https://my.bt.tn/)해야 합니다.
> 
> [!TIP]
> 흐름을 만들기 전에 [bttn 웹 사이트](https://my.bt.tn/)의 이름, 위치 및 전자 메일 주소 등의 모든 bttn 속성을 구성합니다.
> 
> 

[Flic 물리적 단추](flic-button-flows.md)를 사용하여 흐름을 트리거할 수도 있습니다.

## <a name="prerequisites"></a>필수 구성 요소
* [Microsoft Flow](https://flow.microsoft.com)에 액세스합니다.
* 하나 이상의 [등록된 bttn](https://my.bt.tn/)입니다.

## <a name="create-a-flow-thats-triggered-from-a-bttn"></a>bttn에서 트리거되는 흐름 만들기
이 연습에서는 [bttn](https://my.bt.tn/)을 한 번 눌러서 트리거할 수 있는 흐름을 만들기 위해 기술 지원팀 템플릿을 사용합니다. 흐름이 실행되는 경우 지원 요청을 생성한 다음 기술 지원팀에 보냅니다. 지원 요청은 도움말이 필요한 곳의 위치를 기술 지원팀에 제공합니다. 이 연습에서는 템플릿에서 이 흐름을 만드는 방법을 보여주지만 빈 템플릿에 사용할 수 있습니다. 여기서 흐름의 모든 측면에 대한 전체 권한을 제공합니다.

이러한 템플릿 중 하나를 사용하여 bttn에 대한 흐름을 신속하게 만들고 다른 항목에서 Zendesk, Google, SharePoint와 연결할 수 있습니다.

![bttn 템플릿](./media/bttn-button-flows/bttn-templates.png)

팁: 이 연습을 통해 사무실 건물에서 일반적인 회의실을 나타내는 이름을 bttn에 지정하려고 합니다.

bttn의 설정은 bttn 웹 사이트의 다음 예제와 비슷해야 합니다.

![bttn 템플릿](./media/bttn-button-flows/bttn-config.png)

이제 bttn을 등록하고 구성했으므로 흐름을 만들기 시작하겠습니다.

### <a name="sign-in-and-select-a-template"></a>로그인 및 템플릿 선택
1. [Microsoft Flow](https://flow.microsoft.com)에 로그인합니다.
   
    ![로그인](./media/bttn-button-flows/sign-into-flow.png)
   
    참고: 대안으로 [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) 또는 [Windows Phone](https://aka.ms/flowmobilewindows)용 Microsoft Flow 모바일 앱에서 흐름을 만들 수 있습니다.
2. 검색 상자에 **bttn**을 입력한 다음 검색 아이콘을 선택합니다.
   
    ![검색](./media/bttn-button-flows/bttn-search-template.png)
   
    검색 아이콘을 선택하면 bttns과 함께 사용할 수 있는 모든 템플릿이 표시됩니다.
3. **bttn을 사용하여 회의실에 기술 지원 호출** 템플릿을 선택합니다.
   
    ![지원 템플릿](./media/bttn-button-flows/bttn-select-template.png)

### <a name="authorize-microsoft-flow-to-connect-to-your-bttn"></a>Microsoft Flow에서 bttn에 연결할 권한 부여
1. 메시지가 표시되면 bttn 및 Office 365 Outlook 서비스에 로그인합니다. 그려면 **계속** 단추를 활성화합니다.
   
    ![자격 증명](./media/bttn-button-flows/bttn-provide-credentials.png)
2. bttn 서비스에 로그인할 때 Microsoft Flow에서 bttns를 사용할 권한을 부여합니다.
   
    **중요**: Microsoft Flow에서 bttns를 사용할 권한을 부여하지 않은 경우 Microsoft Flow에서 보거나 연결할 수 없습니다.
   
    ![권한 부여](./media/bttn-button-flows/authorize-bttn.png)
3. 두 서비스에 로그인한 후에 **계속**을 선택합니다.
   
    ![계속](./media/bttn-button-flows/continue.png)

### <a name="select-the-bttn-that-triggers-the-flow"></a>흐름을 트리거하는 bttn 선택
1. **bttn을 누를 경우** 카드에서 bttn ID 목록을 연 다음 사용하려는 bttn을 선택합니다.
   
    ![bttn 선택](./media/bttn-button-flows/bttn-id.png)
   
    흐름은 이 예제와 비슷해야 합니다.
   
    ![흐름의 개요](./media/bttn-button-flows/bttn-done.png)
2. 흐름에 이름을 지정한 다음 **흐름 만들기**를 선택하여 저장합니다.
   
    ![흐름 저장](./media/bttn-button-flows/save.png)

## <a name="test-your-flow-and-confirm-results"></a>흐름 테스트 및 결과 확인
1. bttn에서 단추를 누릅니다.
2. 흐름의 실행 기록을 보고 성공적으로 실행되었는지 확인합니다.
   
    Microsoft Flow 웹 사이트 또는 모바일 장치에서 실행 기록을 확인할 수 있습니다.
   
    참고: 지원 요청 전자 메일에서 **승인**을 선택할 때까지 실행 상태가 **실행 중**으로 설정됩니다.
3. 또한 지원 팀에 전자 메일을 보냈는지 확인할 수 있습니다.
   
    이를 따랐다면 지원 전자 메일은 다음 예제와 유사하게 표시됩니다.
   
    ![](./media/bttn-button-flows/support-request-email.png)

## <a name="troubleshooting"></a>문제 해결
* 흐름이 트리거되지 않은 경우 Button Corporation의 사이트에 로그인하고 단추 작업(누름)이 기록되는지 여부를 확인합니다.
* Microsoft Flow 사이트에서 실행 작업에 대해 자세히 알아보고 오류 메시지를 확인할 수도 있습니다.

## <a name="more-information"></a>자세한 내용
* [단추 흐름 공유](share-buttons.md)
* 단추 흐름이 실행될 때 현재 데이터를 보내기 위해 [단추 트리거 토큰](introduction-to-button-trigger-tokens.md)을 사용하는 방법에 대해 알아보세요.
* [Android용 Microsoft Flow 앱 설치](https://aka.ms/flowmobiledocsandroid)
* [iOS용 Microsoft Flow 앱 설치](https://aka.ms/flowmobiledocsios)

