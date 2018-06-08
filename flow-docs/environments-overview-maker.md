---
title: Microsoft Flow 환경에 대해 알아보기| Microsoft Docs
description: 환경을 사용하여 흐름을 격리하는 방법 알아보기
services: ''
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/27/2017
ms.author: sunayv
ms.openlocfilehash: e6667c1c1999c36177d40d52fa657edadd063516
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "31008314"
---
# <a name="choosing-an-environment"></a>환경 선택

이 문서에서는 흐름, 게이트웨이, 연결 및 기타 리소스를 만들고 안전하게 격리할 수 있는 Microsoft Flow **환경**을 소개합니다.

다음에 대해 알아봅니다.

* 이 환경에서 제공하는 기능.
* 환경 간 전환.
* 올바른 환경에서 흐름을 만드는 방법.

## <a name="environments-overview"></a>환경 개요

흐름을 만들 때 흐름을 호스트하는 환경과 흐름에서 사용할 리소스를 선택합니다. 다양한 시나리오에 대한 별도의 환경을 사용할 수 있습니다.

## <a name="here-are-a-few-scenarios-for-using-environments"></a>환경 사용에 대한 몇 가지 시나리오는 다음과 같습니다.

시나리오|권장 사항
-----|-----
Microsoft Common Data Service에 대한 연결을 사용하는 흐름을 만드는 것이 좋습니다.|흐름과 Common Data Service를 동일한 환경에 배치하세요. 이렇게 하면 모든 데이터가 환경(격리 경계) 내에서 격리됩니다.
인적 자원 부서에 대한 흐름을 만들게 됩니다. 인적 자원 부서의 사용자에게만 흐름에 액세스할 권한이 있는지 확인하려고 합니다.|환경을 만들고 HR 사용자만 추가합니다. 이 환경에 흐름과 흐름에서 사용하는 다른 리소스를 배치합니다.
유럽에는 SharePoint 데이터를 표시하는 흐름을 사용하는 사용자가 있습니다.|유럽에서는 환경을 만든 후 그 안에 흐름과 SharePoint 연결을 만듭니다. 이 유럽 환경은 모든 리소스를 유럽 지역에 최적화하여 유럽 사용자에게 최상의 성능을 제공합니다(데이터 지역성).

환경을 만들려면 Microsoft Flow 관리자여야 합니다. 관리자는 환경에 액세스할 수 있는 사람을 제어합니다. 환경을 만들고 관리하는 방법에 대한 자세한 정보는 [환경 관리](environments-overview-admin.md) 항목을 참조하세요.

## <a name="switching-environments"></a>환경 전환

Microsoft Flow를 사용하면 손쉽게 환경 사이를 전환할 수 있습니다. 환경을 전환하면 해당 특정 환경에서 생성된 항목만 표시되며 다른 모든 환경의 항목은 보거나 액세스할 수 없게 됩니다.

예를 들면 다음과 같습니다.

*NewEmployee*라는 이름의 흐름을 *인적 자원* 환경에 생성했습니다. [Microsoft Flow](https://flow.microsoft.com)에서 *영업* 환경을 엽니다. *NewEmployee* 흐름은 나열되지 않습니다. *NewEmployee* 흐름을 보려면 *인적 자원* 환경을 엽니다. 이 규칙은 연결, 게이트웨이, 흐름 등을 포함하여 해당 환경에서 사용자가 만든 다른 모든 항목에 적용됨에 유의합니다.

환경을 전환하려면 다음 단계를 수행합니다.

1. [Microsoft Flow](https://flow.microsoft.com)에 로그인합니다.
1. 오른쪽 위 모서리에 프로필을 나타내는 이미지가 표시됩니다.

   ![프로필 이미지](./media/environments-overview-maker/default-environment.png)

1. 이미지를 선택합니다. 드롭다운 목록에 사용자가 사용할 수 있는 모든 환경이 표시됩니다. 현재 로그인된 환경을 확인합니다.

   ![환경 목록 이미지](./media/environments-overview-maker/all-environments.png)
1. 다른 환경으로 전환하려면 목록에서 원하는 환경을 선택합니다.

   ![전환할 환경 선택](./media/environments-overview-maker/select-europe.png)
1. Microsoft Flow가 새 환경으로 전환됩니다.

## <a name="create-flows-in-the-right-environment"></a>올바른 환경에서 흐름 만들기

흐름을 만들기 전에 흐름 및 해당 리소스를 추가할 환경을 선택합니다.

> [!NOTE]
> 잘못된 환경에 흐름을 만들 경우 삭제한 후 올바른 환경에 만들어야 합니다.

흐름을 호스팅할 환경을 선택할 때는 다음 요소를 고려합니다.

* 기본 환경에만 게이트웨이를 만들 수 있습니다. 따라서 게이트웨이를 사용하여 온-프레미스 데이터에 흐름을 연결하려는 경우 기본 환경을 사용해야 합니다.
* Microsoft Common Data Service 데이터베이스는 특정 환경에 연결됩니다. 따라서 Common Data Service를 사용하는 흐름을 만들려는 경우 데이터베이스를 호스팅하는 환경에서 흐름을 만들어야 합니다.
* 리소스를 편집할 수 있는 모든 환경이 표시됩니다. 그러나 흐름을 만들려는 모든 환경에 본인을 작성자로 추가해 달라고 관리자에게 요청해야 합니다.

> [!NOTE]
> 항상 기본 환경에 흐름을 만들 수 있습니다.

## <a name="next-steps"></a>다음 단계

* [템플릿에서 흐름 만들기](get-started-logic-template.md)
* [흐름 만들기](get-started-logic-flow.md)
* [관리자를 위한 환경 개요](environments-overview-admin.md)