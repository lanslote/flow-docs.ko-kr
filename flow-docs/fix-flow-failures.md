---
title: 흐름 문제 해결 | Microsoft Docs
description: 흐름이 실패하는 가장 일반적인 일부 이유 해결
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/17/2017
ms.author: stepsic
ms.openlocfilehash: 7f4e41437fa19f58c08e2ecd1fb65a3a30092ef8
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "23439545"
---
# <a name="troubleshooting-a-flow"></a>흐름 문제 해결
## <a name="identify-the-error"></a>오류 식별
흐름을 수정하기 전에 실패한 이유를 식별해야 합니다. 웹 포털 맨 위에 있는 알림 아이콘을 클릭하거나 눌러서 또는 모바일 앱의 **작업** 탭을 열고 표시되는 목록에서 흐름을 클릭하거나 누릅니다.

![알림](./media/fix-flow-failures/notifications-toolbar.png)

흐름에 대한 자세한 세부 사항이 나타나면 하나 이상의 단계가 빨강색 느낌표 아이콘이 표시됩니다. 해당 단계를 열어 오류 메시지를 검토합니다.

![오류 메시지](./media/fix-flow-failures/flow-run-failure.png)

## <a name="authentication-failures"></a>인증 실패
대부분의 경우에 흐름은 인증 오류로 인해 실패합니다. 이러한 종류의 오류가 발생면 오류 메시지에는 **권한이 없음** 또는 **401** 또는 **403**이라는 오류 코드가 나타납니다. 일반적으로 연결을 업데이트하여 인증 오류를 수정할 수 있습니다.

1. 웹 포털의 맨위에서 기어 아이콘을 클릭하거나 눌러서 **설정** 메뉴를 열고 **연결**을 클릭하거나 누릅니다.
2. **권한이 없음** 오류 메시지가 표시된 연결로 스크롤합니다.
3. 연결 옆에 있는 인증되지 않은 연결에 대한 메시지에서 **암호 확인** 링크를 클릭하거나 누릅니다.
4. 표시되는 지침에 따라 자격 증명을 확인하고 흐름 실행 오류에 반환한 다음 **다시 제출**을 클릭하거나 누릅니다.
   
    이제 흐림이 예상대로 실행되어야 합니다.

## <a name="action-configuration"></a>작업 구성
흐름의 작업에서 설정이 예상대로 작동하지 않으면 흐름도 실패합니다. 이 경우에 오류 메시지에는 **잘못된 요청**이나 **찾을 수 없습니다** 또는 **400**이나 **404**이라는 오류 코드가 나타납니다.

오류 메시지는 오류를 해결하는 방법을 지정해야 합니다. **편집** 단추를 클릭하거나 누른 다음 흐름 정의 내에서 문제를 수정해야 합니다. 업데이트된 흐름을 저장한 다음 **다시 제출**을 클릭하거나 눌러서 업데이트된 구성을 다시 실행해 봅니다.

## <a name="other-failures"></a>기타 실패
오류 코드 **500** 또는 **502** 오류가 나타나는 경우 오류는 일시적입니다. **다시 제출**을 클릭하거나 눌러서 흐름을 다시 시도합니다.

다른 문제가 발생하면 다른 사람에게 비슷한 문제가 발생했을 수 있으므로 [커뮤니티에 문의하세요](https://go.microsoft.com/fwlink/?LinkID=787467).

