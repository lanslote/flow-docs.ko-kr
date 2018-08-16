---
title: 이메일 속성에 따라 흐름 실행 | Microsoft Docs
description: 이메일의 제목, 보내는 사람 주소 또는 받는 사람 주소와 같은 속성에 따라 흐름을 시작합니다.
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
ms.date: 06/08/2017
ms.author: deonhe
ms.openlocfilehash: c021f4fee692863bdeaa71d2d49901fbb603aa31
ms.sourcegitcommit: cd3cdcff3accb9a54f002fdc33d33935b4276249
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39519965"
---
# <a name="trigger-a-flow-based-on-email-properties"></a>전자 메일 속성에 따라 흐름 트리거
**새 이메일이 도착하는 경우** 트리거를 사용하여 하나 이상의 이메일 속성이 제공한 조건과 일치할 때 실행되는 흐름을 만듭니다.

| 속성 | 사용하는 경우 |
| --- | --- |
| 폴더 |이메일이 특정 폴더에 도달할 때마다 흐름을 트리거합니다. 이 속성은 전자 메일을 다른 폴더에 라우팅하는 규칙이 있는 경우에 유용할 수 있습니다. |
| 받는 사람 |메일을 보낸 주소에 따라 흐름을 트리거합니다. 동일하게 받은 편지함에서 다른 전자 메일 주소로 전송된 메일을 수신하는 경우에 이 속성이 유용할 수 있습니다. |
| 보낸 사람 |보낸 사람의 전자 메일 주소에 따라 흐름을 트리거합니다. |
| 중요도 |전자 메일이 전송된 중요도에 따라 흐름을 트리거합니다. 높은, 보통, 또는 낮은 중요도로 전자 메일을 보낼 수 있습니다. |
| 첨부 포함 |들어오는 이메일에서 첨부 파일의 유무에 따라 흐름을 트리거합니다. |
| 제목 필터 |전자 메일의 제목에서 특정 단어의 존재를 검색합니다. 그런 다음, 흐름은 검색의 결과를 기반으로 *작업*을 실행합니다. |

> [!IMPORTANT]
> [Microsoft Flow 계획](https://flow.microsoft.com/pricing/)에는 각각 실행 할당량이 포함됩니다. 가능한 경우 항상 흐름의 트리거에서 속성을 확인합니다. 이렇게 하면 실행 할당량을 불필요하게 사용하지 않도록 방지합니다. 조건에 있는 속성을 확인하는 경우 정의한 필터 조건이 충족되지 않더라도 계획의 실행 할당량에 대한 실행이 각각 개수됩니다. 

예를 들어, 조건에서 전자 메일의 *보낸 사람* 주소를 확인하는 경우 관심있는 *보낸 사람* 주소가 아니더라도 계획의 실행 할당량에 대한 실행이 각각 개수됩니다.
> 
> 

다음 연습에서 **새 이메일이 도착하는 경우** 트리거에 있는 모든 속성을 확인합니다. [질문과 대답](billing-questions.md#what-counts-as-a-run) 및 [가격 책정](https://ms.flow.microsoft.com/pricing/) 페이지를 방문하여 자세히 알아봅니다.

## <a name="prerequisites"></a>필수 구성 요소
* [Microsoft Flow](https://flow.microsoft.com)에 액세스할 수 있는 계정
* Office 365 Outlook 계정
* [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) 또는 [Windows Phone](https://aka.ms/flowmobilewindows)용 Microsoft Flow 모바일 앱
* Office, Outlook 및 푸시 알림 서비스에 대한 연결

## <a name="trigger-a-flow-based-on-an-emails-subject"></a>전자 메일의 제목에 따라 흐름 트리거
이 연습에서는 새 전자 메일의 제목에 "복권"이라는 단어가 포함되는 경우 휴대폰에 푸시 알림을 보내는 흐름을 만듭니다. 흐름은 이러한 메일을 *읽기*  로 표시합니다.

>[!NOTE]
>이 연습에서 푸시 알림을 전송하는 동안 사용자의 워크플로 요구 사항에 적합한 다른 작업을 사용할 수 있습니다. 예를 들어 Dropbox에 저장된 Google 시트 또는 Microsoft Excel 파일 등 다른 리포지토리의 전자 메일 콘텐츠를 저장할 수 있습니다.

이제 시작해 보겠습니다.

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. **제목 필터** 상자에서 흐름이 들어오는 전자 메일을 필터링하는 데 사용하는 텍스트를 입력합니다.
   
     이 예제에서는 제목에 "복권"이라는 단어가 포함된 모든 이메일에 관심이 있습니다.
   
    ![고급 옵션](./media/email-triggers/email-triggers-subject-text.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. 앞에서 지정한 **제목 필터**와 일치하는 이메일을 수신할 때 받을 모바일 알림의 세부 정보를 입력합니다.
   
    ![알림 세부 정보](./media/email-triggers/email-triggers-4.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. 흐름에 이름을 지정합니다. 그런 다음, 페이지의 위쪽에서 **흐름 만들기**를 선택하여 저장합니다.
   
    ![흐름 저장](./media/email-triggers/email-triggers-subject-notification.png)

축하합니다! 이제 제목에 "복권"이라는 단어가 포함된 이메일을 받게 될 때마다 푸시 알림이 표시됩니다.

## <a name="trigger-a-flow-based-on-an-emails-sender"></a>전자 메일의 보낸 사람에 따라 흐름 트리거
이 연습에서는 특정한 보낸 사람(전자 메일 주소)에게서 새 전자 메일이 도착한 경우 휴대폰에 푸시 알림을 보내는 흐름을 만듭니다. 또한 흐름은 이러한 메일을 *읽기* 로 표시합니다.

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. **보낸 사람** 상자에 보낸 사람의 이메일 주소를 입력합니다. 
   
     흐름은 이 주소에서 보낸 모든 이메일에 대한 작업을 수행합니다.
   
    ![이메일 속성](./media/email-triggers/email-triggers-from.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. 이전에 입력한 이메일 주소에서 메시지가 도착할 때마다 수신할 모바일 알림의 세부 정보를 입력합니다.
   
    ![알림 세부 정보](./media/email-triggers/email-triggers-sender-notification.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. 흐름에 이름을 입력한 다음 페이지의 위쪽에서 **흐름 만들기**를 선택하여 저장합니다.
   
    ![흐름 저장](./media/email-triggers/email-triggers-sender-5.png)

## <a name="trigger-a-flow-when-emails-arrive-in-a-specific-folder"></a>전자 메일이 특정 폴더에 도달하는 경우 흐름 트리거
주소와 같은 특정 속성에 따라 전자 메일을 서로 다른 폴더로 라우팅하는 규칙이 있는 경우 이러한 종류의 흐름을 사용하려고 합니다.

이제 시작해 보겠습니다.

> [!NOTE]
> 받은 편지함이 아닌 폴더에 전자 메일을 라우팅하는 규칙이 아직 없는 경우 이러한 규칙을 만들고 테스트 전자 메일을 전송하여 작동하는지 확인합니다.
> 
> 

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-specific-folder](includes/sign-in-use-blank-select-email-trigger-and-specific-folder.md)]

1. 특정 이메일을 라우팅할 폴더를 선택합니다. 모든 전자 메일 폴더를 표시하려면 먼저 **새 전자 메일이 도착하는 경우** 카드의 **폴더** 상자 오른쪽에 있는 **선택 표시** 아이콘을 선택합니다.
   
    ![폴더 선택](./media/email-triggers/email-triggers-2.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. 앞에서 지정한 폴더에 이메일이 도착하는 경우 받을 모바일 알림의 세부 정보를 입력합니다. 아직 알림 서비스에 대한 자격 증명을 입력하지 않은 경우 입력합니다.
   
    ![알림 세부 정보](./media/email-triggers/email-triggers-folder-notification.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. 흐름에 이름을 입력한 다음 페이지의 위쪽에서 **흐름 만들기**를 선택하여 저장합니다.
   
    ![흐름 저장](./media/email-triggers/email-triggers-7.png)

이 연습의 앞부분에서 선택한 폴더에 라우팅되는 전자 메일을 전송하여 흐름을 테스트합니다.

