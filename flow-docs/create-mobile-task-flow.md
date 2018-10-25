---
title: PowerApps에서 모바일 작업 흐름 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 06/11/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: 046480e6-f2ff-4c56-9e03-f642c982ff7d
caps.latest.revision: 12
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ba48fe37c0effe75f5dafec5e62a39ae21758c10
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689758"
---
# <a name="create-a-mobile-task-flow"></a>모바일 작업 흐름 만들기

사용자가 수행하는 일반적인 작업을 기반으로 휴대폰용 Dynamics 365 또는 태블릿용 Dynamics 365에서 흐름을 디자인합니다. 예를 들어 클라이언트 모임 후에 일련의 후속 단계를 정기적으로 수행해야 하는 경우 작업 흐름을 만듭니다. 사용자가 모바일 앱에서 새 작업을 탭하면 시작부터 완료까지 안내하므로 중요한 단계를 놓치지 않을 수 있습니다.  
  
 작업 흐름은 다중 엔터티 양식 및 논리를 사용할 수 있고 작업 흐름 페이지에서 실행되는 양식 논리를 포함할 수 있습니다.  
  
## <a name="create-a-task-flow"></a>작업 흐름 만들기
  
1. 시스템 관리자 또는 시스템 사용자 지정자 보안 역할이나 이와 동등한 권한이 있는지 확인합니다. Dynamics 365 고객 관계, 관리자, 부사장 또는 CEO 비즈니스 관리자를 사용하는 경우 보안 역할이 모바일 작업 흐름을 만들 수도 있습니다. 
  
2. [솔루션 탐색기](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer)를 열고 **프로세스**를 선택합니다.  
  
3.  **작업** 도구 모음에서 **새로 만들기**를 선택합니다.  
  
4.  **프로세스 만들기** 대화 상자에서 필수 필드를 완성합니다.  
  
    -   프로세스 이름을 입력합니다.  
  
    -   **범주** 목록에서 **비즈니스 프로세스 흐름**을 선택합니다.  
  
    -   **엔터티** 목록에서 원하는 엔터티를 선택합니다.  
  
5.  **Run process as a task flow (Mobile online)**(작업 흐름으로 프로세스 실행(모바일 온라인)) 옵션을 선택합니다.  
  
6.  **확인**을 선택합니다.
  
     작업 흐름 디자이너가 새 창에서 열립니다.  
  
     ![작업 흐름 디자이너 창](media/task-flow-designer-window.png "작업 흐름 디자이너 창") 
  
7.  사용자가 순서대로 한 페이지에서 다른 페이지로 진행하는 경우 화면의 오른쪽에 있는 **구성 요소** 탭에서 **페이지** 구성 요소를 끌어서 해당 지점에 있는 + 기호에 놓습니다. 페이지 이름을 추가하려면 페이지를 선택하고, **속성** 탭을 선택한 후, 새 이름을 입력하고, **적용**을 선택합니다.  
  
8.  작업 흐름에 분기를 추가하려면 **구성 요소** 탭에서 **조건** 구성 요소를 끌어서 해당 지점에 있는 + 기호에 놓습니다. 조건의 속성을 설정하려면 조건을 선택하고, **속성** 탭에서 속성을 설정한 후, **적용**을 선택합니다.  
  
    > [!NOTE]
    >  작업 흐름에 페이지 및 조건을 추가할 때 작업 흐름의 모든 페이지 및 조건을 표시하는 창의 왼쪽 아래 모서리에 미니맵이 표시됩니다.  
  
9. 필드, 레이블 또는 섹션 레이블을 페이지에 추가하려면 **구성 요소** 탭에서 해당 페이지로 **필드**, **레이블** 또는 **섹션 레이블**을 끌어옵니다. 이러한 항목 중 하나의 속성을 변경하려면 항목을 선택하고, **속성** 탭에서 속성을 설정한 후, **적용**을 선택합니다.  
  
10. 작업 흐름의 유효성을 검사하려면 작업 모음에서 **유효성 검사**를 선택합니다.  
  
11. 프로세스를 초안으로 저장하려면 화면 위쪽에 있는 **저장**을 선택합니다. 프로세스가 초안으로 있는 한 사용자는 이 프로세스를 사용할 수 없습니다.  
  
12. 사용자가 사용할 수 있도록 작업 흐름을 활성화하려면 **활성화**를 선택합니다.  
  
> [!TIP]
>  디자이너 창에서 작업 흐름을 수행할 때 유의해야 하는 몇 가지 팁은 다음과 같습니다.  
>   
> -  작업 흐름 창에 있는 모든 항목의 스냅숏을 만들려면 작업 모음에서 **스냅숏**을 선택합니다.  
> -  디자이너에서 유효한 구성 요소를 또 다른 유효한 구성 요소에 연결하려면 작업 모음에서 **커넥터**를 선택합니다.  
> -  화면의 오른쪽 위 모서리에 있는 **Increase the zoom level**(확대/축소 수준 늘리기) 또는 **Decrease the zoom level**(확대/축소 수준 줄이기) 단추를 선택하여 화면의 이미지를 더 크게 또는 더 작게 만들 수 있습니다. **Fit to canvas**(캔버스에 맞추기) 단추를 선택하여 이미지를 화면에 맞게 최대 크기로 확대합니다.  
  
## <a name="next-steps"></a>다음 단계  
 [비즈니스 프로세스 흐름 만들기](create-business-process-flow.md)   

