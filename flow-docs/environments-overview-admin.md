---
title: "관리자를 위한 환경 개요 | Microsoft Docs"
description: "Microsoft Flow에서 환경 사용, 만들기 및 관리"
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
ms.openlocfilehash: f1c50e5d16d5b9fbbd3e6db3128947b0554e9a85
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2017
---
# <a name="using-environments-within-microsoft-flow"></a>Microsoft Flow 내에서 환경 사용
## <a name="benefits"></a>이점
환경은 Microsoft Flow의 새로운 기능이며 다음과 같은 이점이 있습니다. 

* **데이터 지역성**: 환경은 다양한 지역에서 만들 수 있으며 해당 지리적 위치에 바인딩됩니다. 환경에서 흐름을 만들면 이 흐름은 해당 지리적 위치의 모든 데이터 센터에 라우팅됩니다. 이는 성능상의 이점도 제공합니다. 
  
    사용자가 유럽에 있는 경우 유럽 지역에서 환경을 만들어 사용합니다. 사용자가 미국에 있는 경우 미국에서 환경을 만들어 사용합니다. 
  
    환경을 삭제하면 이 환경 내의 모든 흐름도 삭제됩니다. 이 작업은 연결, 게이트웨이, PowerApps 등을 포함하여 해당 환경에서 사용자가 만든 모든 항목에 적용됩니다.
* **데이터 손실 방지**: 관리자로서 내부 위치에서 데이터를 가져오는 흐름을 원하지 않고(예: *비즈니스용 OneDrive*) 해당 데이터를 공개적으로 게시합니다(예: *Twitter*). 데이터 손실 방지를 사용하여 비즈니스 데이터 전용 정책에서 어떤 서비스를 사용할 수 있는지 제어합니다. 
  
    예를 들어, *SharePoint* 및 *비즈니스용 OneDrive* 서비스를 비즈니스 데이터 전용 정책에 추가할 수 있습니다. 이 환경에서 만든 모든 흐름은 *SharePoint* 및 *비즈니스용 OneDrive* 서비스를 사용할 수 있습니다. 추가한 서비스만 사용할 수 있습니다. 
  
  > [!NOTE]
  > 데이터 손실 방지는 P2 라이선스를 비롯한 일부 라이선스 SKU에서 사용할 수 있습니다. 
  > 
  > 
* **모든 리소스에 대한 격리 경계**: 모든 흐름, 게이트웨이, 연결, 사용자 지정 커넥터 등이 해당 특정 환경에 있습니다. 다른 환경에는 존재하지 않습니다. 
* **공통 데이터 서비스**: 특정 위치에 데이터를 삽입하는 흐름을 만들고자 합니다. 사용 가능한 옵션은 다음과 같습니다.
  
  * Excel 파일에 데이터를 삽입하고 OneDrive와 같은 클라우드 저장소 계정에 Excel 파일을 저장합니다.
  * 사용자 고유의 SQL 데이터베이스를 만들고 그 안에 데이터를 저장합니다.
  * Common Data Service를 사용하여 데이터를 저장합니다.
    
    모든 환경은 Common Data Service에서 흐름을 위해 0개 또는 하나의 데이터베이스 저장소를 가질 수 있습니다. Common Data Service에 대한 액세스 권한은 구입한 라이선스에 따라 다르며, 무료 라이선스에는 포함되지 않습니다.

## <a name="limitations"></a>제한 사항
환경은 많은 혜택을 제공하지만 새로운 제한 사항이 생겨날 수 있습니다. 환경이 격리 경계라는 사실은 환경 *간에* 다른 리소스를 참조하는 리소스는 가질 수 없다는 의미입니다. 예를 들어, 한 환경에서 사용자 지정 커넥터를 만들고 다른 환경에서 이 사용자 지정 커넥터와 게이트웨이를 모두 사용하는 흐름을 만들 수 없습니다.

따라서 환경은 필요한 경우에만 만들어야 합니다. 너무 많은 환경을 만들면 사용자가 조직 간에 리소스를 공유하기 매우 어렵습니다.

## <a name="use-the-default-environment"></a>기본 환경 사용
**기본** 환경은 모든 사용자가 사용할 수 있으며 모든 사용자가 공유합니다. 모든 사용자는 이 환경에서 흐름을 만들 수 있습니다.

> [!TIP]
> 미리 보기 사용자인 경우 모든 기존 흐름이 기본 환경에 있습니다. 미리 보기 사용자는 GA(일반 공급) 전에 Microsoft Flow를 사용 중이었던 사용자입니다. 
> 
> 

## <a name="use-the-administrator-center"></a>관리자 센터 사용
관리자는 관리자 센터를 사용하여 환경을 만들고 사용자를 이러한 환경과 기타 유사한 작업에 추가합니다. 관리자 센터를 여는 방법은 다음과 같이 두 가지가 있습니다.

#### <a name="option-1-select-settings"></a>옵션 1: 설정 선택
1. [flow.microsoft.com](https://flow.microsoft.com)에 로그인합니다.
2. 설정 기어를 선택하고 목록에서 **관리자 센터**를 선택합니다.  
   ![설정 및 관리자 포털](./media/environments-overview-admin/settings.png)
3. 관리자 센터를 엽니다.

#### <a name="option-2-open-adminflowmicrosoftcom"></a>옵션 2: admin.flow.microsoft.com 열기
[admin.flow.microsoft.com](https://admin.flow.microsoft.com)으로 이동하고 회사 계정으로 로그인합니다. 관리자 센터를 엽니다.

## <a name="create-an-environment"></a>환경 만들기
1. [Microsoft Flow 관리자 센터](https://admin.flow.microsoft.com)에서 **환경**을 선택합니다. 모든 기존 환경이 표시됩니다.  
   ![](./media/environments-overview-admin/environments-list.png)
2. **새 환경**을 선택합니다. 다음 정보를 입력합니다.
   
   | 속성 | 설명 |
   | --- | --- |
   | 환경 이름 |환경의 이름을 `Human Resources` 또는 `Europe flows` 등과 같이 입력합니다. |
   | 지역 |사용자의 환경을 호스트할 위치를 선택합니다. 최고의 성능을 위해 사용자와 가장 가까운 지역을 사용합니다. 예를 들어 흐름 사용자가 런던에 있는 경우 유럽 지역을 선택합니다. 흐름 사용자가 뉴욕에 있는 경우 미국 지역을 선택합니다. |
3. **환경 만들기**를 선택합니다. 새 환경이 나열됩니다. 

다음으로, 환경에 사용자를 추가합니다.

## <a name="manage-your-existing-environments"></a>기존 환경 관리
1. [Microsoft Flow 관리자 센터](https://admin.flow.microsoft.com)에서 **환경**을 선택합니다.  
   ![](./media/environments-overview-admin/select-environments.png)  
2. 속성을 열 환경을 선택합니다. 
3. **세부 정보**에는 환경을 만든 사람, 지리적 위치, 기타 속성 등을 비롯하여 환경에 대한 추가 정보가 표시됩니다.  
   ![](./media/environments-overview-admin/open-environment.png)
4. **보안**을 선택합니다. **환경 역할**에는 **관리자** 및 **작성자**의 두 가지 옵션이 있습니다.  
   
    ![](./media/environments-overview-admin/environment-roles.png)
   
    **작성자**는 흐름, 데이터 연결, 게이트웨이 등의 새로운 리소스를 환경에서 만들 수 있습니다. 
   
   > [!NOTE]
   > 사용자가 환경 내의 리소스를 편집하고 순 신규 리소스만 만들기 위해 **작성자**가 될 필요는 없습니다.  각 리소스 생성자는 해당 리소스를 편집할 수 있는 사람을 결정하고 환경 작성자가 아닌 사용자에게 편집 권한을 부여할 수 있습니다.
   > 
   > 
   
    **관리자**는 데이터 손실 방지 정책을 만들고 환경 만들기, 환경에 사용자 추가, 관리자/작성자 권한 할당 등의 관리 작업을 수행할 수도 있습니다.  
   
   1. **환경 작성자** 역할을 선택한 다음, **사용자**를 선택합니다.  
      ![](./media/environments-overview-admin/add-environment-maker.png)
   2. 이름, 전자 메일 주소 또는 작성자 역할을 부여하려는 사용자 그룹을 입력합니다. 입력을 시작하면 IntelliSense에서 텍스트와 일치하는 사용자/그룹을 나열하기 시작합니다. 
   3. **저장**을 선택하여 사용자 추가를 완료합니다. 
5. **보안** 내에서 **사용자 역할**을 선택합니다.  
    ![](./media/environments-overview-admin/security-user-roles.png)
   
    역할을 편집하거나 삭제하는 옵션을 비롯하여 모든 기존 역할이 나열됩니다. 
   
    **새 역할**을 선택하여 새 역할을 만듭니다. 
6. **보안** 내에서 **권한 집합**을 선택합니다.  
    ![](./media/environments-overview-admin/security-permission-set.png)
   
    역할을 편집하거나 삭제하는 옵션을 비롯하여 모든 기존 사용 권한이 나열됩니다. 
   
    **새 권한 집합**을 선택하여 새 집합을 만듭니다. 
7. **데이터베이스**에서 데이터를 저장할 데이터베이스 만들기를 선택할 수 있습니다. 이 데이터베이스는 Common Data Service의 일부입니다.

## <a name="commonly-asked-questions"></a>질문과 대답
##### <a name="can-i-migrate-a-microsoft-flow-in-my-us-environment-to-a-europe-environment"></a>미국 환경의 Microsoft Flow를 유럽 환경으로 마이그레이션할 수 있습니까?
아니요. 흐름은 환경 간에 이동할 수 없습니다. 다른 환경에서 흐름을 다시 만드십시오.

##### <a name="which-license-includes-the-common-data-service"></a>Common Data Service를 포함하는 라이선스는 무엇입니까?
Microsoft PowerApps 플랜 2에만 Common Data Service와 데이터베이스를 만들 수 있는 권한이 있습니다. 그러나 모든 유료 플랜(Microsoft Flow 플랜 1, 2 및 Microsoft PowerApps 플랜 1, 2)에는 Common Data Service를 사용할 수 있는 권한이 있습니다.

[흐름 가격 책정](https://flow.microsoft.com/pricing/)은 자신에게 알맞은 계획을 선택하는 데 유용할 수 있습니다.  

[청구 관련 질문](billing-questions.md)은 또한 우리가 받은 일반적인 질문 일부를 탐색하는 데 도움이 됩니다. 

##### <a name="can-the-common-data-service-be-used-outside-of-an-environment"></a>환경 외부에서 Common Data Service를 사용할 수 있습니까?
아니요. Common Data Service를 사용하려면 환경이 필요합니다. 그것에 관해 [자세히 알아봅니다](common-data-model-intro.md).

##### <a name="what-regions-include-microsoft-flow"></a>Microsoft Flow를 포함하는 지역은 어디입니까?
Microsoft Flow은 Office 365를 지원하는 대부분의 지역을 지원합니다. 자세한 내용은 [지역 개요](regions-overview.md)를 참조하세요.

##### <a name="what-is-needed-to-create-my-own-custom-environment"></a>나만의 사용자 지정 환경을 만들려면 무엇이 필요하나요?
Microsoft Flow 플랜 2 라이선스가 있는 모든 사용자는 기본 환경 외에도 자신만의 환경을 만들 수 있습니다. Office 365 및 무료를 비롯한 모든 Microsoft Flow 사용자는 플랜 2 관리자가 만든 환경을 사용할 수 있지만 자신만의 환경을 만들 수는 없습니다. 

