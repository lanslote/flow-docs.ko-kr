---
title: "흐름에 조건 추가 | Microsoft Docs"
description: "특정 조건이 참인 경우에만 흐름이 하나 이상의 작업을 수행하도록 지정합니다."
services: 
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/22/2016
ms.author: stepsic
ms.openlocfilehash: 1291b32f001be211acddbf1c83f3b1bdf03f2ac3
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2017
---
# <a name="add-a-condition-to-a-flow"></a>흐름에 조건 추가
특정 조건이 참인 경우에만 흐름이 하나 이상의 작업을 수행하도록 지정합니다. 예를 들어, 트윗에 10회 이상 리트윗된 키워드가 포함된 경우에만 전자 메일을 받도록 지정합니다.

**필수 구성 요소**

* 템플릿에서 [흐름을 만듭니다](get-started-logic-template.md). 이 자습서는 예제로 [이 템플릿을 사용](https://flow.microsoft.com/galleries/public/templates/e78571e5c70e4806a18eeacba5a897c8/)합니다.

## <a name="add-a-condition"></a>조건 추가
1. [flow.microsoft.com](https://flow.microsoft.com)의 상단 탐색 모음에서 **내 흐름**을 선택합니다.
2. 흐름 목록에서 만든 흐름을 선택합니다. 이 자습서에서는 Twitter 트리거 및 SharePoint 작업을 예제로 사용합니다.
3. 마지막 작업에서 **새 단계** 단추를 선택합니다.
4. **조건 추가**를 선택합니다.
   
    ![조건 단추](./media/add-a-condition/add-condition.png)
5. **개체 이름**에서 빈 영역을 선택하고 **동적 콘텐츠 추가**를 선택하여 동적 콘텐츠 메뉴를 엽니다.
6. **개수 리트윗** 매개 변수를 선택하여 상자에 추가합니다.
7. **관계** 상자에서 **이상**을 선택합니다.
8. **값** 상자에 **10**을 입력합니다.
   
    ![안에 매개 변수가 있는 OBJECT NAME 상자](./media/add-a-condition/specify-condition.png)
9. 조건 내에서 원하는 작업의 머리글(예: **항목 만들기**)을 클릭하고 **예인 경우** 텍스트를 끕니다. 커서를 놓으면 해당 상자로 작업이 이동합니다.
   
    ![끌기 작업](./media/add-a-condition/drag-action.png)
10. 흐름을 저장합니다.

## <a name="edit-in-advanced-mode"></a>고급 모드에서 편집
**고급 모드에서 편집** 링크를 선택하여 추가 고급 조건을 쓸 수도 있습니다. 워크플로 정의 언어에 있는 모든 표현식을 사용할 수 있습니다.  사용 가능한 함수를 [자세히 살펴보세요](https://msdn.microsoft.com/library/azure/mt643789.aspx).

