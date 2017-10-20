---
title: "흐름에 조건 추가 | Microsoft Docs"
description: "조건이 참인 경우에만 흐름이 하나 이상의 작업을 수행하도록 지정합니다."
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
ms.date: 10/17/2017
ms.author: stepsic
ms.openlocfilehash: 135b3509a9412f7674a1e9cb2ada86ebd2bb9f4f
ms.sourcegitcommit: 122870842a07183ab3b90e07d99b60d822d6c5ae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="add-a-condition-to-a-flow"></a>흐름에 조건 추가

조건이 참인 경우에만 흐름이 하나 이상의 작업을 수행하도록 지정합니다. 예를 들어, 트윗에 10회 이상 리트윗된 키워드가 포함된 경우에만 전자 메일을 받도록 지정합니다.

## <a name="prerequisites"></a>필수 구성 요소

* 템플릿에서 [흐름 만들기](get-started-logic-template.md) - 이 자습서에서는 예제로 [이 템플릿을 사용](https://flow.microsoft.com/galleries/public/templates/e78571e5c70e4806a18eeacba5a897c8/)합니다.

## <a name="add-a-condition"></a>조건 추가

1. [Microsoft Flow](https://flow.microsoft.com)의 상단 탐색 모음에서 **내 흐름**을 선택합니다.

    로그인되어 있지 않다면 로그인해야 합니다.

1. 흐름 목록에서 사용자가 만든 흐름 중 하나를 선택합니다.

    이 자습서에서는 Twitter 트리거 및 SharePoint 작업을 예제로 사용합니다.

1. **흐름 편집**을 선택합니다.

1. 마지막 작업에서 **새 단계**를 선택합니다.

1. **조건 추가**를 선택합니다.

    ![조건 단추](./media/add-condition/add-condition.png)

1. **조건** 카드의 왼쪽 상자에서 빈 영역을 선택합니다.

    **동적 콘텐츠** 목록이 열립니다.

1. **개수 리트윗** 매개 변수를 선택하여 상자에 추가합니다.

1. **조건** 카드의 가운데 상자에서 **보다 크거나 같음**을 선택합니다.

1. 오른쪽의 상자에서 **10**을 입력합니다.

    ![안에 매개 변수가 있는 OBJECT NAME 상자](./media/add-condition/specify-condition.png)

1. 조건 내에서 사용하려는 작업의 헤더(예: **항목 만들기**)를 선택하고 **예인 경우**라는 텍스트 아래로 끌어옵니다.

    커서를 놓으면 해당 상자로 작업이 이동합니다.

    ![끌기 작업](./media/add-condition/drag-action.png)

1. 필요에 따라 작업을 구성합니다.

1. 흐름을 저장합니다.

## <a name="edit-in-advanced-mode"></a>고급 모드에서 편집

**고급 모드에서 편집**을 선택하여 추가 고급 조건을 쓸 수도 있습니다. 고급 모드에서 *워크플로 정의 언어*의 모든 식을 사용할 수 있습니다. 사용 가능한 모든 [식](https://msdn.microsoft.com/library/azure/mt643789.aspx)에 대해 알아봅니다.

## <a name="next-steps"></a>다음 단계

고급 모드로 조건에서 [식을 사용](use-expressions-in-conditions.md)하는 방법을 알아봅니다.
