---
title: 솔루션 인식 흐름을 만드는 방법 알아보기 | Microsoft Docs
description: 솔루션 인식 흐름을 만드는 방법을 알아봅니다.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/05/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: cbc6e3a8ffe50eb7ad27e80eba044957647a1da3
ms.sourcegitcommit: b41b45f6fa29a22e9a9a4d3c726a2321b2ff3cbf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51025774"
---
# <a name="create-a-flow-in-a-solution"></a>솔루션에서 흐름 만들기

솔루션에서 만드는 흐름을 ‘솔루션 인식’ 흐름이라고 합니다.  다음 단계에 따라 솔루션 인식 흐름을 만듭니다.

## <a name="prerequisites"></a>필수 구성 요소

솔루션 인식 흐름을 만들려면 솔루션이 하나 이상 있어야 합니다.

## <a name="create-the-flow"></a>흐름 만들기 

1. [Microsoft Flow](https://flow.microsoft.com)에 로그인합니다.
1. 탐색 모음에서 **솔루션**을 선택합니다.

   ![](./media/create-flow-solution/select-solutions-from-left-nav.png)

1. 흐름을 만들 솔루션을 선택합니다.

   ![](./media/create-flow-solution/new-solution-created.png)

1. **+ 새로 만들기**를 선택하고 **흐름**을 선택합니다.

   ![](./media/create-flow-solution/select-new-flow.png)

   Microsoft Flow가 열립니다.

1. 사용 가능한 커넥터 및 트리거를 사용하여 흐름을 만듭니다.

   이 예에서는 받은 편지함에 메일이 도착하면 알림을 보내는 간단한 흐름을 만듭니다.
1. **Office 365 Outlook**을 검색하고 선택합니다.
1. **새 메일이 도착하는 경우** 트리거를 선택합니다.
1. **+ 새 단계**를 선택합니다.
1. **Send me a mobile notification**(모바일 알림 보내기) 작업을 선택합니다.
1. **Send me a mobile notification**(모바일 알림 보내기) 상자의 **텍스트** 필드에 **제목** 동적 토큰을 추가합니다.
1. 흐름에 이름을 지정하고 흐름을 저장합니다.

   흐름이 다음과 같이 표시됩니다.

   ![](./media/create-flow-solution/new-email-notification-flow.png)
   
1. **솔루션**을 선택하여 솔루션의 흐름을 봅니다.

   ![](./media/create-flow-solution/new-flow-inside-solution.png)

## <a name="learn-more"></a>자세한 정보

* [솔루션 만들기](./overview-solution-flows.md)
* [솔루션 내보내기](./export-flow-solution.md)
* [솔루션 가져오기](./import-flow-solution.md)
* [솔루션 인식 흐름 편집](./edit-solution-aware-flow.md)
* [솔루션 인식 흐름 제거](./remove-solution-aware-flow.md)
