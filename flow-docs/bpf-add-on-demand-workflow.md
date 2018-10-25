---
title: 비즈니스 프로세스 흐름에 주문형 워크플로 추가
description: ''
author: Mattp123
ms.author: matp
manager: kvivek
ms.date: 07/12/2018
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
ms.assetid: 26c79c20-2987-476e-983a-406e0db13034
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: aa061d5e2f668e8950a6cdab89992996f64c6fe8
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689620"
---
# <a name="add-an-on-demand-workflow-to-a-business-process-flow"></a>비즈니스 프로세스 흐름에 주문형 워크플로 추가

비즈니스 프로세스 흐름 내부에서 주문형 워크플로를 트리거할 수 있습니다. 예를 들어 스테이지가 완료될 때마다 작업 또는 메일과 같은 활동이 만들어지도록 비즈니스 프로세스 흐름에 주문형 워크플로를 추가할 수 있습니다. 

워크플로는 비즈니스 프로세스 흐름 디자이너에 워크플로를 놓는 위치를 기준으로 활성화됩니다.
- 주문형 스테이지 프로세스. 워크플로가 비즈니스 프로세스 흐름 스테이지에 놓이면 워크플로는 스테이지 시작 또는 종료 시 트리거됩니다. 
- 주문형 전역 프로세스. 워크플로가 **전역 워크플로** 영역에 놓이면 워크플로는 프로세스 활성화 또는 프로세스 보관 시(상태가 적용됨, 완료됨, 다시 활성화됨 또는 중단됨 상태로 전환될 때) 트리거됩니다. 

비즈니스 프로세스 흐름에 워크플로를 추가할 때 다음 요구 사항을 확인합니다.
- 스테이지에 추가된 워크플로의 경우: 워크플로를 추가하는 스테이지의 동일한 엔터티용으로 만들어진 활성 주문형 워크플로만 사용할 수 있습니다.  
- 전역 워크플로의 경우: 비즈니스 프로세스 흐름의 기본 엔터티용으로 만들어진 활성 주문형 워크플로만 사용할 수 있습니다.

## <a name="add-an-on-demand-workflow-to-a-business-process-flow-stage"></a>비즈니스 프로세스 흐름 스테이지에 주문형 워크플로 추가

워크플로 구성 요소를 프로세스 스테이지 또는 전역 워크플로 섹션으로 끌어서 비즈니스 프로세스 흐름 디자이너의 주문형 워크플로를 추가합니다. 

[PowerApps](https://web.powerapps.com) 사이트에서 **모델 기반**(탐색 창의 왼쪽 아래)을 선택합니다. 

비즈니스 프로세스 흐름 디자이너를 엽니다. 다음 두 가지 방법 중 하나를 사용합니다.
- 비즈니스 프로세스 흐름이 이미 앱에 추가된 경우 **앱**으로 이동하고, 선택할 앱 옆에 있는 **...** 를 선택한 다음, **편집**을 선택합니다. 앱 디자이너에서 비즈니스 프로세스 흐름을 선택한 다음, ![비즈니스 프로세스 흐름 디자이너 열기](media/dynamics365-open-designer.PNG)를 선택합니다.  
- 또는 왼쪽 탐색 창에서 [솔루션 탐색기](/powerapps/maker/model-driven-apps/advanced-navigation.md#solution-explorer)를 열고, **프로세스**를 선택한 다음, 원하는 비즈니스 프로세스 흐름을 선택합니다. 

다음 비즈니스 프로세스 흐름 이벤트 중 하나에서 주문형 워크플로를 트리거할지 결정합니다. 
- 주문형 스테이지 프로세스. 스테이지 시작 또는 종료 시 워크플로를 트리거합니다. 
- 주문형 전역 프로세스. 프로세스 활성화 또는 프로세스 보관 시(상태가 적용됨, 완료됨, 다시 활성화됨 또는 중단됨 상태로 전환될 때) 워크플로를 트리거합니다. 

아래 예제에서는 **내 주문형 워크플로**라는 주문형 워크플로가 비즈니스 프로세스 흐름의 **스테이지 1**에 추가됩니다. 

1. 스테이지 1을 확장하여 **트리거된 프로세스** 섹션을 표시합니다. 
2. **구성 요소** 탭을 선택하고 **워크플로**를 **트리거된 프로세스** 섹션으로 끌어옵니다.
    ![스테이지에 워크플로 추가](media/add-workflow-to-bpf-1.png) 또는 **워크플로**를 **전역 워크플로** 섹션으로 끌어올 수 있습니다. 그러면 프로세스 활성화 또는 프로세스 보관 시 워크플로가 트리거됩니다.
 ![프로세스 활성화 또는 보관에 워크플로 추가](media/add-workflow-to-bpf-global.png)
3. **속성** 탭의 검색 상자에서 비즈니스 프로세스 흐름 스테이지에 추가할 주문형 워크플로의 이름을 입력하고 검색한 후 **적용**을 선택합니다.
    ![이름 입력 및 적용 선택](media/add-workflow-to-bpf-2.png)
4. **트리거** 아래 **속성** 탭에서 **Stage Entry**(스테이지 시작) 또는 **Stage Exit**(스테이지 종료)를 선택합니다.  
    ![워크플로 트리거 선택](media/workflow-trigger.png)
   
    또는 **전역 워크플로** 섹션에 워크플로를 놓으면 표시되는 트리거 옵션은 **프로세스 적용**, **프로세스 다시 활성화**, **프로세스 중단** 또는 **프로세스 완료**입니다.

5. 비즈니스 프로세스 흐름 디자이너 도구 모음에서 **업데이트**를 선택합니다.
 
## <a name="next-steps"></a>다음 단계
[워크플로 프로세스를 사용하여 사용자 조작이 필요하지 않은 프로세스 자동화](workflow-processes.md) <br/>
[자습서: 프로세스를 표준화하는 비즈니스 프로세스 흐름 만들기](create-business-process-flow.md) <br/>
[Dynamics 365의 비즈니스 프로세스 흐름 자동화](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/)
