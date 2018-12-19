---
title: 흐름에 다른 소유자를 추가하고 팀 흐름을 만드는 방법 알아보기 | Microsoft Docs
description: Microsoft Flow를 사용하면 반복적인 작업을 쉽게 자동화할 수 있습니다. 사용자 또는 그룹을 소유자로 추가하고 공동 작업을 수행하여 흐름을 디자인하고 관리할 수 있습니다.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/21/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 238ef8eac80d3259981cb11cc21e3b05eb83e0ec
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689735"
---
# <a name="create-team-flows"></a>팀 흐름 만들기
조직의 다른 사용자를 소유자로 추가하여 팀 흐름을 만듭니다. 팀 흐름의 모든 소유자는 다음 작업을 수행할 수 있습니다.

* 흐름의 기록(즉, 각 실행)을 확인합니다.
* 흐름의 속성을 관리합니다(예: 흐름 시작 또는 중지, 소유자 추가 또는 연결에 대한 자격 증명 업데이트).
* 흐름의 정의를 편집합니다(예: 작업이나 조건 추가 또는 제거).
* 흐름의 작성자가 아닌 다른 소유자를 추가하고 제거합니다.
* 흐름을 삭제합니다.

팀 흐름의 작성자나 소유자인 경우 [Microsoft Flow](https://flow.microsoft.com)의 **팀 흐름** 탭에 나열됩니다.

![팀 흐름 탭](./media/create-team-flows/addowner5.png)

> [!NOTE]
> 공유 연결을 만든 흐름에서**만** 해당 공유 연결을 사용할 수 있습니다.
> 
> 

소유자는 흐름에서 서비스를 사용할 수 있지만 다른 소유자가 만든 연결에 대한 자격 증명을 수정할 수 없습니다.

## <a name="prerequisites"></a>필수 구성 요소
팀 흐름을 만들려면 [유료 Microsoft Flow 플랜](https://flow.microsoft.com/pricing/)이 있어야 합니다. 또한 작성자 또는 소유자만 팀 흐름에서 소유자를 추가/제거할 수 있습니다.

## <a name="create-a-team-flow"></a>팀 흐름 만들기
이러한 단계를 따라 팀 흐름을 만들거나 팀 흐름에 더 많은 소유자를 추가합니다.

1. [Microsoft Flow](https://flow.microsoft.com)에 로그인한 다음 **내 흐름**을 선택합니다.
2. 수정하려는 흐름에 대한 사용자 아이콘을 선택합니다.
   
    ![팀 아이콘](./media/create-team-flows/addowner1.png)
3. 소유자로 추가할 사용자나 그룹의 이름, 전자 메일 주소 또는 그룹 이름을 입력합니다.
   
    ![사용자 검색](./media/create-team-flows/addowner2.png)
4. 표시되는 목록에서 소유자로 만들려는 사용자를 선택합니다.
   
    ![사용자 선택](./media/create-team-flows/addowner3.png)
   
     선택한 사용자 또는 그룹이 흐름의 소유자가 됩니다.
   
    ![새 소유자](./media/create-team-flows/addowner4.png)
   
     &mdash;, 축하합니다. 팀 흐름을 만들었습니다.

##<a name="add-a-list-as-a-co-owner"></a>목록을 공동 소유자로 추가

목록에 대한 편집 액세스 권한이 있는 모든 사용자가 자동으로 흐름에 대한 편집 액세스 권한을 갖도록 SharePoint 목록을 흐름에 대한 공동 소유자로 추가할 수 있습니다. 흐름이 공유되면 이에 대한 링크를 간단히 배포할 수 있습니다.

## <a name="remove-an-owner"></a>소유자 제거
> [!IMPORTANT]
> Microsoft Flow 서비스에 액세스하는 데 사용되는 자격 증명의 소유자를 제거하는 경우, 흐름을 계속 제대로 실행할 수 있도록 해당 연결에 대한 자격 증명을 업데이트해야 합니다.
> 
> 

1. 수정하려는 흐름에 대한 사용자 아이콘을 선택합니다.
   
    ![사용자 아이콘 선택](./media/create-team-flows/removeowner1.png)
2. 제거하려는 소유자에 대한 **삭제** 아이콘을 선택합니다.
   
    ![삭제 선택](./media/create-team-flows/removeowner2.png)
3. 확인 대화 상자에서 **이 소유자 제거**를 선택합니다.
   
    ![제거 확인](./media/create-team-flows/removeowner3.png)
4. &mdash;, 축하합니다. 제거하려는 사용자 또는 그룹이 더 이상 흐름의 소유자로 나열되지 않습니다.
   
    ![사용자 제거됨](./media/create-team-flows/removeowner4.png)

## <a name="embedded-and-other-connections"></a>포함 및 기타 연결
흐름에 사용되는 연결은 두 가지 범주로 구분됩니다.

* **포함** &mdash; 이러한 연결은 흐름에서 사용됩니다.
* **기타** &mdash; 이러한 연결은 흐름에 정의되어 있지만 거기서 사용되지 않습니다.

흐름에서 연결 사용을 중지하면 해당 연결은 **기타** 연결 목록에 표시됩니다. 소유자가 해당 연결을 흐름에 다시 포함할 때까지 거기에서 연결이 표시됩니다.

흐름의 속성에 있는 소유자 목록에서 연결 목록이 표시됩니다.

![포함된 연결](./media/create-team-flows/embeddedconnections.png)

