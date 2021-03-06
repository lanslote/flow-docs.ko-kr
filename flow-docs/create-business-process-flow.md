---
title: PowerApps에서 비즈니스 프로세스 흐름 만들기 | MicrosoftDocs
description: 비즈니스 프로세스 흐름을 만드는 방법을 알아봅니다.
ms.custom: ''
ms.date: 08/17/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: efe86ab3-430f-485a-b924-6ed82cfbb449
caps.latest.revision: 39
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 1e765d4c7c11354e382c3ff74ac66103345ff39f
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44691038"
---
# <a name="tutorial-create-a-business-process-flow-to-standardize-processes"></a>자습서: 프로세스를 표준화하는 비즈니스 프로세스 흐름 만들기

이 자습서에서는 PowerApps를 사용하여 비즈니스 프로세스 흐름을 만드는 방법을 보여 줍니다. 비즈니스 프로세스 흐름을 사용하는 이유에 대한 자세한 내용은 [비즈니스 프로세스 흐름 개요](business-process-flows-overview.md)를 참조하세요. 모바일 작업 흐름을 만드는 방법에 대한 내용은 [모바일 작업 흐름 만들기](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-mobile-task-flow)를 참조하세요.  
  
 사용자가 비즈니스 프로세스 흐름을 시작하면 프로세스의 스테이지와 단계가 양식의 위쪽에 있는 프로세스 표시줄에 표시됩니다.  
  
 ![스테이지가 있는 비즈니스 프로세스](media/business-process-stages.png "스테이지가 있는 비즈니스 프로세스")  
  
 > [!TIP]
 >  비즈니스 프로세스 흐름 정의를 만든 후에는 비즈니스 프로세스 흐름 인스턴스의 만들기, 읽기, 업데이트 또는 삭제를 수행할 수 있는 사용자를 제어할 수 있습니다. 예를 들어 서비스 관련 프로세스의 경우 고객 서비스 담당자에게 비즈니스 프로세스 흐름 인스턴스를 변경하기 위한 모든 액세스 권한을 제공할 수 있지만, 판매 담당자에게는 고객에 대한 판매 후 활동을 모니터링할 수 있도록 인스턴스에 대한 읽기 전용 액세스 권한을 제공할 수 있습니다. 만든 비즈니스 프로세스 흐름 정의에 대한 보안을 설정하려면 작업 모음에서 **보안 역할 사용**을 선택합니다.  
  
<a name="BKMK_Createbusinessprocessflows"></a>   
## <a name="create-a-business-process-flow"></a>비즈니스 프로세스 흐름 만들기  
  
1. [솔루션 탐색기](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer)를 엽니다.
  
2. 왼쪽 탐색 창에서 **프로세스**를 선택합니다. 
  
3.  **작업** 도구 모음에서 **새로 만들기**를 선택합니다.  
  
4.  **프로세스 만들기** 대화 상자에서 필수 필드를 완성합니다.  
  
    -   프로세스 이름을 입력합니다. 프로세스의 이름은 고유할 필요가 없지만 프로세스를 선택해야 하는 사람들에게는 의미가 있어야 합니다. 이 이름은 나중에 변경할 수 있습니다.  
  
    -   **범주** 목록에서 **비즈니스 프로세스 흐름**을 선택합니다.  
  
         프로세스를 만든 후에는 이 범주를 변경할 수 없습니다.  
  
    -   **엔터티** 목록에서 프로세스의 기반으로 사용할 엔터티를 선택합니다.  
  
         선택한 엔터티는 프로세스 흐름의 첫 번째 스테이지에 추가할 수 있는 단계에 사용할 수 있는 필드에 영향을 줍니다. 원하는 엔터티를 찾을 수 없으면 엔터티 정의에 비즈니스 프로세스 흐름(필드가 만들어짐) 옵션이 설정되어 있는지 확인합니다. 프로세스를 저장한 후에는 이 엔터티를 변경할 수 없습니다.  
  
5. **확인**을 선택합니다.  
  
     새 프로세스가 만들어지고, 이미 만들어진 단일 스테이지가 있는 비즈니스 프로세스 흐름 디자이너가 열립니다.  
  
 ![기본 요소를 보여 주는 비즈니스 프로세스 흐름 창](media/business-process-flow-window-showing-main-elements.png "기본 요소를 보여 주는 비즈니스 프로세스 흐름 창")  
  
6. **스테이지를 추가합니다.** 프로세스에서 사용자가 한 비즈니스 스테이지에서 다른 스테이지로 진행하는 경우 다음을 수행합니다.  
  
    1.  **구성 요소** 탭에서 **스테이지** 구성 요소를 끌어 디자이너의 + 기호 위에 놓습니다.  
  
        ![비즈니스 프로세스 스테이지 끌기](media/drag-business-process-stage.png "비즈니스 프로세스 스테이지 끌기")  
  
    2.  스테이지에 대한 속성을 설정하려면 스테이지를 선택한 다음, 화면의 오른쪽에 있는 **속성** 탭에서 속성을 설정합니다.  
  
        -   표시 이름을 입력합니다.  
  
        -   원하는 경우 스테이지에 대한 범주를 선택합니다.  범주(예: **자격** 또는 **개발**)는 프로세스 표시줄에서 갈매기형 수장으로 표시됩니다.  
  
            ![프로세스 표시줄 갈매기형 수장](media/business-process-bar-chevron.png "프로세스 표시줄 갈매기형 수장")  
  
        -   속성 변경이 완료되면 **적용** 단추를 선택합니다.  
  
7. **스테이지에 단계를 추가합니다.** 스테이지의 단계를 보려면 스테이지의 오른쪽 아래 모서리에 있는 **세부 정보**를 선택합니다. 단계를 추가하려면 다음을 수행합니다.  
  
    1.  **단계** 구성 요소를 **구성 요소** 탭에서 스테이지로 끌어갑니다.  
  
        ![비즈니스 프로세스의 스테이지에 단계 추가](media/add-step-stage-business-process.png "비즈니스 프로세스의 스테이지에 단계 추가")  
  
    2.  단계를 선택한 다음, **속성** 탭에서 속성을 설정합니다.  
  
        1.  단계에 대한 표시 이름을 입력합니다.  
  
        2.  사용자가 데이터를 입력하여 단계를 완성하도록 하려면 드롭다운 목록에서 해당 필드를 선택합니다.  
  
        3.  프로세스의 다음 스테이지로 이동하기 전에 사용자가 필드를 채워 단계를 완성해야 하는 경우 **필수**를 선택합니다.  
  
        4.  완료되면 **적용**을 선택합니다.  
  
8. **프로세스에 분기(조건)를 추가합니다.** 분기 조건을 추가하려면 다음을 수행합니다.  
  
    1.  **조건** 구성 요소를 **구성 요소** 탭에서 두 스테이지 사이의 + 기호로 끌어갑니다.  
  
        ![비즈니스 프로세스 흐름에 조건 추가](media/add-condition-business-process-flow.png "비즈니스 프로세스 흐름에 조건 추가")  
  
    2.  조건을 선택한 다음, **속성** 탭에서 속성을 설정합니다. 분기 속성에 대한 자세한 내용은 [분기를 사용하여 비즈니스 프로세스 흐름 향상](enhance-business-process-flows-branching.md)을 참조하세요. 조건에 대한 속성 설정이 완료되면 **적용**을 선택합니다.  
  
9. **워크플로를 추가합니다.** 워크플로를 호출하려면 다음을 수행합니다.  
  
    1.  **워크플로** 구성 요소를 **구성 요소** 탭에서 스테이지 또는 디자이너의 **글로벌 워크플로** 항목으로 끌어갑니다.   추가할 워크플로는 다음에 따라 달라집니다.  
  
       - 스테이지를 시작하거나 종료할 때 워크플로를 시작하려면 **스테이지로 끌어갑니다**. 워크플로 구성 요소는 스테이지와 동일한 기본 엔터티를 기반으로 해야 합니다.  
  
       - 프로세스가 활성화되거나 프로세스가 보관될 때(상태가 **완료됨** 또는 **중단됨**으로 바뀌는 경우) 워크플로를 트리거하려면 **글로벌 워크플로 항목으로 끌어갑니다**. 워크플로 구성 요소는 프로세스와 동일한 기본 엔터티를 기반으로 해야 합니다.  
  
    2.  워크플로를 선택한 다음, **속성** 탭에서 속성을 설정합니다.  
  
       1.  표시 이름을 입력합니다.  
  
       2.  워크플로가 트리거되도록 하는 경우를 선택합니다.  
  
       3.  스테이지 엔터티와 일치하는 기존 요청 시 활성 워크플로를 검색하거나 **새로 만들기**를 선택하여 새 워크플로를 만듭니다.  
  
       4.  완료되면 **적용**을 선택합니다.  
  
       워크플로에 대한 자세한 내용은 [워크플로 프로세스](../common-data-service/workflow-processes.md)를 참조하세요.  
  
10. 비즈니스 프로세스 흐름의 유효성을 검사하려면 작업 모음에서 **유효성 검사**를 선택합니다.  
  
11. 작업을 계속 수행하면서 프로세스를 초안으로 저장하려면 작업 모음에서 **저장**을 선택합니다.  
  
    > [!IMPORTANT]
    >  프로세스가 초안으로 있는 한 사용자는 이 프로세스를 사용할 수 없습니다.  
  
12. 프로세스를 활성화하고 팀에서 사용할 수 있게 하려면 작업 모음에서 **활성화**를 선택합니다.  

13. 비즈니스 프로세스 흐름 인스턴스의 만들기, 읽기, 업데이트 또는 삭제를 수행할 수 있는 사용자를 제어하려면 디자이너의 명령 모음에서 **보안 역할 편집**을 선택합니다. 예를 들어 서비스 관련 프로세스의 경우 고객 서비스 담당자에게 비즈니스 프로세스 흐름 인스턴스를 변경하기 위한 모든 액세스 권한을 제공할 수 있지만, 판매 담당자에게는 고객에 대한 판매 후 활동을 모니터링할 수 있도록 인스턴스에 대한 읽기 전용 액세스 권한을 제공할 수 있습니다.

  **보안 역할** 화면에서 역할 이름을 선택하여 보안 역할 정보 페이지를 엽니다. [비즈니스 프로세스 흐름] 탭을 선택한 다음, 비즈니스 프로세스 흐름에 보안 역할에 대한 적절한 권한을 할당합니다.

  > [!NOTE]
  > 시스템 관리자 및 시스템 사용자 지정자 보안 역할에는 기본적으로 새 비즈니스 프로세스 흐름에 대한 액세스 권한이 있습니다.

   ![비즈니스 프로세스 흐름에 권한 할당](media/bpf-assign-privileges.png)

  적절한 단일 라디오 단추를 선택하여 권한을 지정하고 [저장]을 클릭합니다. 권한에 대한 자세한 내용은 [비즈니스 프로세스 흐름 권한](business-process-flows-overview.md#BKMK_MultipleBPF)을 참조하세요.

  다음으로, 조직의 적절한 사용자에게 보안 역할을 할당해야 합니다.

> [!TIP] 
>  디자이너 창에서 작업 흐름을 수행할 때 유의해야 하는 몇 가지 팁은 다음과 같습니다.  
>   
> - 비즈니스 프로세스 흐름 창의 모든 항목에 대한 스냅숏을 만들려면 작업 모음에서 **스냅숏**을 선택합니다. 예를 들어 이는 팀 멤버로부터 프로세스에 대한 의견을 공유하고 가져오려는 경우에 유용합니다.  
> - 미니 맵을 사용하여 프로세스의 다른 부분으로 빠르게 이동할 수 있습니다. 이는 화면에서 스크롤되는 복잡한 프로세스가 있는 경우에 유용합니다.  
> - 비즈니스 프로세스에 대한 설명을 추가하려면 비즈니스 프로세스 흐름 창의 왼쪽 모서리에 있는 프로세스 이름 아래에서 **세부 정보**를 선택합니다. 최대 2,000자까지 사용할 수 있습니다.  
  
<a name="BKMK_Editbusinessprocessflows"></a>   
## <a name="edit-a-business-process-flow"></a>비즈니스 프로세스 흐름 편집  
 비즈니스 프로세스 흐름을 편집하려면 솔루션 탐색기를 열고, **프로세스**를 선택한 다음, 편집할 프로세스 목록에서 **비즈니스 프로세스 흐름**을 선택합니다.  
  
 프로세스 목록에서 편집할 비즈니스 프로세스 흐름의 이름을 선택하면 디자이너에서 해당 비즈니스 프로세스 흐름이 열리고 원하는 업데이트를 수행할 수 있습니다. 프로세스 이름 아래에 있는 **세부 정보**를 펼쳐 이름을 변경하거나 설명을 추가하고 추가 정보를 확인합니다.  
  
 ![펼쳐진 비즈니스 프로세스 흐름의 세부 정보 섹션](media/business-process-flow-details.png "펼쳐진 비즈니스 프로세스 흐름의 세부 정보 섹션")  
  
  
## <a name="other-things-to-know-about-business-process-flows"></a>비즈니스 프로세스 흐름에 대해 알아야 할 기타 사항
 **스테이지 편집**  
비즈니스 프로세스 흐름에는 최대 30개의 스테이지가 포함될 수 있습니다.    
  
추가하거나 변경할 수 있는 스테이지 속성은 다음과 같습니다.  
  
- **스테이지 이름**  
  
- **엔터티**. 첫 번째 스테이지를 제외한 모든 스테이지의 엔터티를 변경할 수 있습니다.  
  
- **스테이지 범주**. 범주를 사용하면 작업 유형별로 스테이지를 그룹화할 수 있습니다. 이는 레코드가 있는 스테이지별로 레코드를 그룹화하는 보고서에 유용합니다. 스테이지 범주에 대한 옵션은 [스테이지 범주] 글로벌 옵션 집합에서 제공됩니다. 이 글로벌 옵션 집합에 추가 옵션을 추가하고, 원하는 경우 기존 옵션의 레이블을 변경할 수 있습니다. 또한 원하는 경우 이러한 옵션을 삭제할 수도 있지만 기존 옵션을 유지하는 것이 좋습니다. 정확히 동일한 옵션을 삭제하면 해당 옵션을 다시 추가할 수 없습니다. 옵션을 사용하지 않도록 하려면 레이블을 "사용하지 않음"으로 변경합니다.  
  
- **관계**. 프로세스의 이전 스테이지가 다른 엔터티를 기반으로 하는 경우 관계를 입력합니다. 현재 정의되고 있는 스테이지에 대해 **관계 선택**을 선택하여 두 스테이지 사이를 이동할 때 사용하는 관계를 식별합니다. 다음과 같은 이점이 있는 관계를 선택하는 것이 좋습니다.  
  
    -   관계에는 레코드 간에 데이터를 자동으로 전달하는 특성 맵이 정의되어 데이터 입력을 최소화하는 경우가 많습니다.  
  
    -   프로세스 표시줄에서 레코드에 대한 **다음 스테이지**를 선택하면 관계를 사용하는 모든 레코드가 프로세스 흐름에 나열되므로 프로세스의 레코드 재사용이 촉진됩니다. 또한 워크플로를 사용하여 레코드 만들기를 자동화하면 사용자가 레코드를 만드는 대신 레코드를 간단히 선택할 수 있도록 프로세스를 간소화할 수 있습니다.  
  
**단계 편집**  
 각 스테이지에는 최대 30개의 단계가 포함될 수 있습니다.    
  
**분기 추가**  
스테이지에 분기를 추가하는 방법에 대한 내용은 [분기를 사용하여 비즈니스 프로세스 흐름 향상](enhance-business-process-flows-branching.md)을 참조하세요.  
  
사람들이 사용할 수 있는 비즈니스 프로세스 흐름을 만들려면 프로세스 흐름의 순서를 지정하고, 보안 역할을 사용하도록 설정하고, 해당 흐름을 활성화해야 합니다.  
  
**프로세스 흐름 순서 지정**  
 엔터티(레코드 종류)에 대해 둘 이상의 비즈니스 프로세스 흐름이 있는 경우 새 레코드에 자동으로 할당되는 프로세스를 설정해야 합니다. 명령 모음에서 **프로세스 흐름 순서 지정**을 선택합니다. 프로세스 흐름이 아직 연결되지 않은 새 레코드 또는 레코드의 경우 사용자가 액세스할 수 있는 첫 번째 비즈니스 프로세스 흐름이 사용됩니다.  
  
**보안 역할 사용**  
사용자는 자신에게 할당된 보안 역할의 비즈니스 프로세스 흐름에 정의된 권한에 따라 비즈니스 프로세스 흐름에 액세스할 수 있습니다. 

기본적으로 **시스템 관리자** 및 **시스템 사용자 지정자** 보안 역할만 새 비즈니스 프로세스 흐름을 볼 수 있습니다. 

비즈니스 프로세스 흐름에 대한 권한을 지정하려면 편집할 비즈니스 프로세스 흐름을 연 다음, 비즈니스 프로세스 흐름 디자이너의 명령 모음에서 **보안 역할 편집**을 선택합니다. 이 항목의 앞부분에 나와 있는 [비즈니스 프로세스 흐름 만들기](#create-a-business-process-flow)의 13단계를 참조하세요.
  
**활성화**  
비즈니스 프로세스 흐름을 사용하려면 먼저 비즈니스 프로세스 흐름을 활성화해야 합니다. 명령 모음에서 **활성화**를 선택합니다. 활성화가 확인되면 비즈니스 프로세스 흐름을 사용할 준비가 됩니다. 비즈니스 프로세스 흐름에 오류가 있으면 해당 오류가 해결될 때까지 활성화할 수 없습니다.  

## <a name="add-an-on-demand-action-to-a-business-process-flow"></a>주문형 작업을 비즈니스 프로세스 흐름에 추가
Dynamics 365(온라인) 버전 9.0 업데이트에는 비즈니스 프로세스 흐름 기능인 [작업 단계]를 통한 비즈니스 프로세스 흐름 자동화가 도입되었습니다. 비즈니스 프로세스 흐름에 작업 또는 워크플로를 트리거하는 단추를 추가할 수 있습니다.

### <a name="add-on-demand-workflows-or-actions-using-an-action-step"></a>[작업 단계]를 사용하여 주문형 워크플로 또는 작업 추가
Contoso 조직에서 고객 선별 프로세스의 일환으로 지정된 검토자가 모든 기회를 검토해야 한다고 가정합니다. 이어서 Contoso 조직에서 만든 작업은 다음과 같습니다. 

- 기회 검토자에게 할당된 작업 레코드를 만듭니다. 
- 기회 항목에 "검토 준비 완료"를 추가합니다. 

또한 Contoso는 필요에 따라 이러한 작업을 실행할 수 있어야 합니다. 이러한 작업을 기회 선별 프로세스에 통합하려면 해당 작업이 기회 비즈니스 프로세스 흐름에 표시되어야 합니다. 이 기능을 사용하도록 설정하려면 **비즈니스 프로세스 흐름 작업 단계로**를 선택합니다.
![비즈니스 프로세스 흐름으로 실행 가능](media/action-available-to-run.png)

다음으로, 작업 단계를 Contoso의 기회 비즈니스 프로세스 흐름에 추가합니다. 그런 다음, 프로세스 흐름의 유효성을 검사하고 해당 흐름을 업데이트합니다.

![기회 비즈니스 프로세스 흐름에 추가된 작업](media/add-action-to-bpf.png)

이제 Contoso의 영업 인력 담당자는 필요에 따라 **실행**을 선택하여 **기회 식별** 비즈니스 프로세스 단계에서 작업을 시작할 수 있습니다.

![작업 실행](media/action-execute.png)

> [!IMPORTANT]
> - 필요에 따라 작업 또는 워크플로를 실행하려면 비즈니스 프로세스 흐름에 [작업 단계]가 포함되어야 합니다. [작업 단계]에서 워크플로를 실행하는 경우 요청 시 실행되도록 워크플로를 구성해야 합니다.
> - 작업 또는 워크플로와 연결된 엔터티는 비즈니스 프로세스 흐름과 연결된 엔터티와 동일해야 합니다.

### <a name="limitation-of-using-action-steps-in-a-business-process-flow"></a>비즈니스 프로세스 흐름에서 작업 단계 사용 시의 제한 사항

- 입력 또는 출력 매개 변수가 Entity, EntityCollection 또는 OptionSet(Picklist) 형식인 경우 해당 작업은 [작업 단계]로 사용할 수 없습니다. 둘 이상의 EntityReference 출력 매개 변수 또는 임의 개수의 EntityReference 입력 매개 변수가 있는 작업은 [작업 단계]로 사용할 수 없습니다. 기본 엔터티와 연결되지 않은 작업(글로벌 작업)은 [작업 단계]로 사용할 수 없습니다.

  
## <a name="next-steps"></a>다음 단계  
 [비즈니스 프로세스 흐름 개요](business-process-flows-overview.md) </br>   
 [분기를 사용하여 비즈니스 프로세스 흐름 향상](enhance-business-process-flows-branching.md)

