---
title: "Microsoft Flow를 만들 때 환경 전환 | Microsoft Docs"
description: "Microsoft Flow를 만들 때 작성자가 다양한 환경을 사용하는 방법"
services: 
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/27/2016
ms.author: sunayv
ms.openlocfilehash: bcbb566c20291da14881d771c538dd89689b6b1d
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2017
---
# <a name="choosing-an-environment"></a>환경 선택
Microsoft Flow로 다양한 환경에서 작업하고 환경을 쉽게 전환할 수 있습니다. 이 문서는 다음 환경의 토픽에 대해 설명합니다.

* 환경이 제공하는 내용의 배경
* 환경 전환
* 올바른 환경에서 흐름을 만드는 방법

## <a name="environments-overview"></a>환경 개요
환경은 흐름, 연결, 게이트웨이 및 기타 리소스에 대한 격리 경계를 제공합니다. 흐름을 만들 때 흐름을 호스트하는 환경과 흐름에서 사용할 리소스를 선택할 수 있습니다. 다양한 시나리오에 대한 다양한 환경을 사용할 수 있습니다.

예:

* Microsoft Common Data Service에 대한 연결을 사용하는 흐름을 만들게 됩니다. 이 시나리오에서는 흐름과 Common Data Service가 동일한 환경에 있습니다. 이렇게 하면 모든 데이터가 환경(격리 경계) 내에서 격리됩니다.
* 인적 자원 부서에 대한 흐름을 만들게 됩니다. 인적 자원 부서의 사용자에게만 흐름에 액세스할 권한이 있는지 확인하려고 합니다. 예를 들어 영업 그룹에서 흐름을 사용하지 않기를 바랄 수 있습니다. 이 시나리오에서는 HR 사용자에게만 권한이 부여되는 별도 환경을 사용하여 흐름을 호스팅하고 게이트웨이 또는 연결을 포함하여 흐름을 사용하는 모든 리소스 사용할 수 있습니다.
* 유럽에는 SharePoint 데이터를 표시하는 흐름을 사용하는 사용자가 있습니다. 이 시나리오에서는 흐름과 SharePoint 연결을 호스팅하는 유럽의 환경을 만듭니다. 이 유럽 환경은 모든 리소스를 유럽 지역에 최적화하여 유럽 사용자에게 최상의 성능을 제공합니다(데이터 지역성).

환경은 Microsoft Flow 관리자가 만듭니다. 또한 이 관리자는 다양한 환경에 액세스할 수 있는 사용자를 제어합니다.

이 토픽에서는 여러 환경 간에 탐색하는 방법을 보여 줍니다. 환경을 만들고 관리하는 방법에 대한 자세한 정보는 [관리 환경](environments-overview-admin.md)을 참조하십시오.

## <a name="switching-environments"></a>환경 전환
Microsoft Flow를 사용하면 손쉽게 환경 사이를 전환할 수 있습니다. 전환을 수행하면 해당 특정 환경의 모든 항목을 볼 수 있으며 다른 환경의 항목은 볼 수 없습니다.

예를 들면 다음과 같습니다.

NewEmployee라는 이름의 흐름을 인적 자원 환경에 생성합니다. [flow.microsoft.com](http://flow.microsoft.com)에서 *영업* 환경을 엽니다. *NewEmployee* 흐름은 표시되지 않습니다. *NewEmployee* 흐름을 보려면 *인적 자원* 환경을 엽니다. 이 작업은 연결, 게이트웨이, PowerApps 등을 포함하여 해당 환경에서 사용자가 만든 모든 항목에 적용됨에 유의합니다.

1. [flow.microsoft.com](http://flow.microsoft.com)을 엽니다.
2. 오른쪽 맨 위 모서리에 사용자의 이름과 사용자가 있는 환경이 표시됩니다.  
   ![](./media/environments-overview-maker/default-environment.png)
   
    이미지에서 알림을 확인할 수 있습니다. 이러한 알림은 이 기본 환경에서 내 흐름에 적용됩니다.
3. 사용자의 이름을 선택합니다. 드롭다운 목록에 사용자가 사용할 수 있는 모든 환경이 나열됩니다. 현재 환경을 선택합니다.  
   ![](./media/environments-overview-maker/all-environments.png)
4. 다른 환경으로 전환하려면 목록에서 원하는 환경을 선택합니다.  
   ![](./media/environments-overview-maker/select-europe.png)
5. Microsoft Flow가 자동으로 새 환경으로 전환합니다.  
   ![](./media/environments-overview-maker/europe-environment.png)
   
    이미지에는 알림이 없습니다. 새로운 유럽 환경에는 알림이 없습니다.

## <a name="create-flows-in-the-right-environment"></a>올바른 환경에서 흐름 만들기
흐름을 만들기 전에 항상 흐름을 포함시키려는 환경을 선택했는지 확인합니다. 그렇지 않은 경우 삭제하고 올바른 환경에서 흐름을 다시 만듭니다.

어떤 환경에서 흐름을 만들지 선택할 때 다음 요소를 고려합니다.

* 게이트웨이는 기본 환경에서 만들어집니다. 다른 환경에서 게이트웨이를 만들 수 없기 때문에 온-프레미스 데이터에 연결하려는 경우 기본 환경을 사용해야 합니다.
* 흐름은 연결과 동일한 환경 내의 다른 리소스만 사용할 수 있습니다. 다른 환경의 리소스를 사용할 수 없습니다. 예를 들어 사용자 지정 커넥터를 사용하는 흐름을 만듭니다. 이 사용자 지정 커넥터는 해당 흐름과 동일한 환경에 있어야 합니다.
* Microsoft Common Data Service 데이터베이스는 항상 단 하나의 환경에 연결됩니다. 즉, Common Data Service로 작업하려는 경우에 해당 데이터베이스가 있는 동일한 환경을 선택해야 합니다.
* 리소스를 편집할 수 있는 모든 환경이 표시됩니다. 그러나 모든 환경에서 새 리소스를 만들 수 있는 것은 아닙니다. 일부 환경에서는 새 흐름을 만들지 못할 수도 있습니다. 관리자에게 사용자를 해당 환경의 **작성자**로 추가하도록 요청하거나 흐름을 넣을 다른 환경을 선택해야 합니다(항상 기본 환경에서 흐름을 만들 수 있음).

## <a name="what-you-did"></a>수행한 작업
이 단계를 사용하여 사용 권한이 있는 환경을 전환합니다. 이제 흐름을 만들어 보십시오.

## <a name="next-steps"></a>다음 단계
[템플릿에서 흐름 만들기](get-started-logic-template.md)  
[흐름 만들기](get-started-logic-flow.md)  
[관리자를 위한 환경 개요](environments-overview-admin.md)

