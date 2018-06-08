---
title: 고급 옵션 및 여러 동작 추가 | Microsoft Docs
description: 전자 메일을 높은 우선 순위로 설정하고 같은 이벤트에 다른 작업을 추가하는 등, 흐름을 확장하여 고급 옵션을 포함합니다.
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
ms.date: 04/20/2017
ms.author: stepsic
ms.openlocfilehash: f6c936cbf5a2bd481adb52ec9b01545fb9ba7b0b
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "23442119"
---
# <a name="add-multiple-actions-and-advanced-options-to-a-flow"></a>흐름에 여러 동작 및 고급 옵션 추가
동일한 트리거에 대해 하나 이상의 고급 옵션과 여러 동작을 추가하여 흐름을 사용자 지정합니다. 예를 들어, 전자 메일 메시지를 높은 우선 순위로 보내는 고급 옵션을 추가합니다. 항목이 SharePoint 목록에 추가되면 메일을 보내는 것 외에도 Dropbox에 동일한 정보가 담긴 파일을 만듭니다.

## <a name="prerequisites"></a>필수 구성 요소
* [흐름 만들기](get-started-logic-flow.md)

## <a name="add-another-action"></a>다른 동작 추가
이 절차에서는 흐름 중간에 동작을 추가합니다. 이 동작에서는 Dropbox에 파일을 저장하고 목록에 해당 항목을 보관합니다.

1. [flow.microsoft.com](https://flow.microsoft.com)의 상단 탐색 모음에서 **내 흐름**을 선택합니다.
2. 흐름 목록에서 편집하려는 흐름을 선택합니다.
3. **+ 새 단계**를 선택한 다음 **작업 추가**를 선택합니다.
   
    ![축소된 추가](./media/multi-step-logic-flow/add-action.png)
4. 가능한 동작 목록에서 **파일 만들기**를 클릭한 다음 **Dropbox - 파일 만들기**를 선택합니다.
   
    ![파일 만들기 검색](./media/multi-step-logic-flow/create-file-search.png)
5. 메시지가 표시되면 Dropbox 자격 증명을 입력합니다.
6. **폴더 경로** 상자의 오른쪽에 있는 폴더 아이콘을 선택합니다.
7. 새 파일을 두려는 폴더를 찾아 선택합니다.
   
    ![파일 만들기 검색](./media/multi-step-logic-flow/create-file-folder.png)
8. 새 파일의 이름을 **파일 이름** 상자에 입력합니다. 파일 이름에 ".txt"와 같은 확장명을 덧붙여야 합니다. 여기서 파일의 고유성이 확립되도록 파일 이름에 **TweetId**를 사용하도록 합니다. **TweetId** 토큰을 찾기 위해 **더 보기**를 선택해야 할 수도 있습니다.
9. 파일에 넣어 두려는 텍스트를 추가하려면 **파일 콘텐츠** 상자에 입력합니다. **콘텐츠 파일** 상자에 토큰을 추가할 수도 있습니다.
   
    ![파일 이름 및 내용](./media/multi-step-logic-flow/create-file-name-and-contents.png)
   
   > [!IMPORTANT]
   > 파일에 (선택한 폴더에 있는) 기존 파일의 이름과 일치하는 이름을 줄 경우 기존 파일이 덮어쓰여집니다.
   > 
   > 
10. 화면 상단의 메뉴에 보이는 **흐름 업데이트**를 선택합니다.
11. 지정한 키워드를 포함하는 트윗을 보냅니다.
    
     1분 안에 파일이 Dropbox 계정에 만들어집니다.

## <a name="reorder-or-delete-an-action"></a>동작 순서 변경 또는 삭제
* Dropbox에서 파일이 만들어진 후 전자 메일을 받으려면 그 제목 표시줄을 전자 메일 작업 위로 드래그하여 Dropbox 동작을 옮깁니다. (**새로운 트윗이 게시될 때**) 트리거와 전자 메일 동작 사이에 있는 화살표 위로 Dropbox 동작을 해제합니다. (커서는 작업이 정확하게 위치했는지 나타냅니다.)
  
  > [!NOTE]
  > 해당 단계에서의 출력을 사용할 경우 단계를 다른 단계 앞으로 이동할 수 없습니다.
  > 
  > 
  
    ![메뉴 삭제](./media/multi-step-logic-flow/draggingaction.png)
* 동작을 삭제하려면 삭제할 동작의 제목 표시줄 오른쪽 가장자리에 있는 말줄임표(...)를 선택하고 **삭제**를 선택한 다음 **확인**을 선택합니다.
  
    ![메뉴 삭제](./media/multi-step-logic-flow/deletemenu.png)
  
     **참고:** 흐름의 어느 부분에서의 출력을 사용하는 경우 작업을 삭제할 수 없습니다. 먼저 필드에서 해당 출력을 제거한 다음 동작을 삭제할 수 있습니다.

## <a name="add-advanced-options"></a>고급 옵션 추가
**전자 메일 보내기** 작업이 있는 흐름에서 시작합니다.

1. **전자 메일 보내기** 카드 하단에 있는 **고급 옵션 표시**를 선택합니다.
   
     그러면 전자 메일 보내기 고급 옵션이 나타납니다.
   
    ![Sharepoint 트리거](./media/multi-step-logic-flow/advanced.png)
2. **중요도** 목록에서 **높음**을 선택한 다음 **고급 옵션 숨기기**를 선택해 고급 옵션을 숨깁니다.
3. 화면 상단의 메뉴에 보이는 **흐름 업데이트**를 선택합니다.
   
     이 단계를 거쳐 변경 내용이 저장됩니다.

