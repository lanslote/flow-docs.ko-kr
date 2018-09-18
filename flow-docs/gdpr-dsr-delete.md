---
title: Microsoft Flow GDPR 데이터 주체 삭제 요청 | Microsoft Docs
description: Microsoft Flow를 사용하여 GDPR 데이터 주체 삭제 요청에 응답하는 방법을 알아봅니다.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/17/2018
ms.author: keweare
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 77ce6e368c8cb54d360ebeaa32f1f649e30aa297
ms.sourcegitcommit: 44bc9de9f06b64615731ceb60a4f46cfcd45b167
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45727185"
---
# <a name="responding-to-gdpr-data-subject-delete-requests-for-microsoft-flow"></a>Microsoft Flow에 대한 GDPR 데이터 주체 삭제 요청에 응답

조직의 고객 데이터에서 개인 데이터 제거를 통한 “삭제 권한”은 GDPR의 주요 보호 방법입니다. 개인 데이터 제거에는 감사 로그 정보를 제외한 모든 개인 데이터 및 시스템 생성 로그 제거가 포함됩니다.

Microsoft Flow를 통해 사용자는 조직의 일상 업무에 중요한 부분인 자동화 워크플로를 빌드할 수 있습니다. 사용자가 조직을 떠나면 관리자는 사용자가 만든 특정 데이터 및 리소스를 삭제할지 여부를 수동으로 검토하고 결정해야 합니다. 사용자 계정이 Azure Active Directory에서 삭제될 때마다 자동으로 삭제되는 다른 개인 데이터가 있습니다.

다음 표에서는 자동으로 삭제되는 개인 데이터와 관리자가 수동으로 검토 및 삭제해야 하는 데이터를 보여줍니다.

|수동 검토 및 삭제 필요|사용자가 Azure Active Directory에서 삭제될 때 자동으로 삭제됨|
|------|------|
|환경*|시스템 생성 로그|
|환경 권한**|실행 기록|
|흐름|작업 피드|
|흐름 권한|게이트웨이 |
|사용자 세부 정보|게이트웨이 권한|
|연결*||
|연결 권한||
|사용자 지정 커넥터*||
|사용자 지정 커넥터 권한||

이러한 각 리소스에는 개인 데이터를 포함하는 “만든 사람” 및 “수정한 사람” 레코드가 있습니다. 보안상의 이유로 이러한 레코드는 리소스가 삭제될 때까지 보존됩니다.

**앱용 Common Data Service 데이터베이스를 포함하는 환경의 경우 환경 권한(예: 환경 작성자 및 관리자 역할에 할당된 사용자)은 Common Data Service 데이터베이스에 레코드로 저장됩니다. Common Data Service를 사용하는 사용자의 DSR에 응답하는 방법에 대한 자세한 내용은 [Executing DSRs against Common Data Service Customer Data](https://go.microsoft.com/fwlink/?linkid=872251)(Common Data Service 고객 데이터에 대해 DSR 실행)를 참조하세요.

수동 검토가 필요한 데이터 및 리소스의 경우 Microsoft Flow는 특정 사용자에 대한 개인 데이터를 찾거나 변경하기 위한 다음과 같은 환경을 제공합니다.

* **웹 사이트 액세스:** [PowerApps 관리 센터](https://admin.powerapps.com/) 또는 [Microsoft Flow 관리 센터](https://admin.flow.microsoft.com/)에 로그인

* **PowerShell 액세스:** [PowerApps 관리자 PowerShell cdmlet](https://go.microsoft.com/fwlink/?linkid=871804) 

다음은 관리자가 각 리소스 유형 내에서 각 개인 데이터 유형을 삭제하는 데 사용할 수 있는 환경에 대한 분석입니다.

|개인 데이터를 포함하는 리소스|웹 사이트 액세스|PowerShell 액세스|자동화된 삭제|
|-----|----|----|----|
|시스템 생성 로그|[Office 365 Service Trust Portal](https://servicetrust.microsoft.com/)|||
|환경|Microsoft Flow 관리 센터|PowerApps cmdlet||
|환경 권한*|Microsoft Flow 관리 센터|PowerApps cmdlet||
|실행 기록||| 28일 보존 정책을 통해 삭제됨|
|작업 피드 |||28일 보존 정책을 통해 삭제됨|
|사용자 작업|| ||
|흐름|Microsoft Flow 작성자 포털**|||
|흐름 권한|Microsoft Flow 작성자 포털|||
|사용자 세부 정보||PowerApps cmdlet||
|연결|Microsoft Flow 작성자 포털| ||
|연결 권한|Microsoft Flow 작성자 포털| ||
|사용자 지정 커넥터|Microsoft Flow 작성자 포털| ||
|사용자 지정 커넥터 권한|Microsoft Flow 작성자 포털| ||
|승인 기록|Microsoft PowerApps 작성자 포털*|||

* 앱용 Common Data Service가 소개되면서 데이터베이스가 환경 내에서 만들어지는 경우 환경 권한 및 모델 기반 앱 권한은 앱용 Common Data Service 데이터베이스 인스턴스 내에 레코드로 저장됩니다. Common Data Service를 사용하는 사용자의 DSR에 응답하는 방법에 대한 자세한 내용은 [Executing DSRs against Common Data Service Customer Data](https://go.microsoft.com/fwlink/?linkid=872251)(Common Data Service 고객 데이터에 대해 DSR 실행)를 참조하세요.

\*\* 관리자는 Microsoft Flow 관리 센터에서 액세스 권한을 할당받은 경우에만 Microsoft Flow 작성자 포털에서 이러한 리소스에 액세스할 수 있습니다.

## <a name="manage-delete-requests"></a>삭제 요청 관리

아래 단계에서는 GDPR에 대한 삭제 요청을 처리하기 위해 관리 기능이 존재하는 방식을 설명합니다. 이러한 단계는 아래에 설명한 순서로 수행되어야 합니다.

> [!IMPORTANT]
> 데이터 손상을 방지하려면 다음 단계를 순서대로 수행합니다.
>
>

## <a name="list-and-re-assign-flows"></a>흐름 나열 및 다시 할당

이러한 단계에서는 떠나는 사용자에 대한 기존 흐름을 복사합니다. 새 소유권을 복사본에 할당하면 이러한 흐름이 기존 비즈니스 프로세스를 계속 지원할 수 있습니다. 떠나는 사용자에 대한 개인 식별자 링크를 삭제하려면 이러한 흐름을 복사하는 것이 중요하고 다른 API 및 SaaS 응용 프로그램과 연결하려면 흐름에 대한 새 연결을 설정해야 합니다.

1. [Microsoft Flow 관리 센터](https://admin.flow.microsoft.com/)에 로그인한 다음, 삭제된 사용자가 소유한 흐름이 포함된 환경을 선택합니다.

    ![환경 보기](./media/gdpr-dsr-delete/view-environments.png)

1. **리소스** > **흐름**을 선택한 후 다시 할당할 흐름의 제목을 선택합니다.

    ![흐름 보기](./media/gdpr-dsr-delete/admin-view-flows.png)

1. **공유 관리**를 선택합니다.

    ![공유 관리](./media/gdpr-dsr-delete/admin-manage-sharing.png)

1. 오른쪽 가장자리 근처에 나타나는 **공유** 패널에서 자신을 소유자로 추가한 다음, **저장**을 선택합니다.

    ![흐름 공유](./media/gdpr-dsr-delete/flow-sharing-save.png)

1. [Microsoft Flow](https://flow.microsoft.com/)에 로그인하고 **내 흐름**을 선택한 다음, **팀 흐름**을 선택합니다.

1. 복사할 흐름에 대한 줄임표 **(...)** 를 선택한 다음, **다른 이름으로 저장**을 선택합니다.

    ![흐름 다른 이름으로 저장](./media/gdpr-dsr-delete/flow-save-as.png)

1. 필요에 따라 연결을 구성한 다음, **계속**을 선택합니다.

1. 새 이름을 입력한 다음, **저장**을 선택합니다.

    ![흐름 복사본 만들기](./media/gdpr-dsr-delete/create-copy-flow.png)

1. 이 새로운 흐름 버전이 **내 흐름**에 나타나고, 여기서 원하는 경우 추가 사용자와 흐름을 공유할 수 있습니다.

    ![팀 흐름](./media/gdpr-dsr-delete/team-flows.png)

1. 원래 흐름에 대한 줄임표 **(…)** 를 선택하고 **삭제**를 선택하여 해당 흐름을 삭제한 다음, 메시지가 표시되면 **삭제**를 다시 선택합니다. 이 단계에서는 사용자와 Microsoft Flow 간의 시스템 종속성에 포함된 기본 개인 식별자도 제거합니다.

    ![흐름 삭제 확인](./media/gdpr-dsr-delete/delete-flow-confirmation.png)

1. **내 흐름**를 연 다음, 토글 컨트롤을 **켜기**로 전환하여 흐름 복사본을 사용하도록 설정합니다.

    ![흐름 사용](./media/gdpr-dsr-delete/toggle-on.png)

1. 이제 복사본이 원래 버전과 동일한 워크플로 논리를 수행합니다.

## <a name="delete-approval-history-from-microsoft-flow"></a>Microsoft Flow에서 승인 기록 삭제

 Microsoft Flow에 대한 승인 데이터는 앱용 Common Data Service의 현재 또는 이전 버전 내에 저장됩니다. 승인 내에서 개인 정보는 승인 응답에 포함된 승인 할당 및 설명 형식으로 존재합니다. 관리자는 다음 단계에 따라 해당 데이터에 액세스할 수 있습니다.

1. [PowerApps](https://web.powerapps.com/)에 로그인합니다.

1. **데이터**를 선택한 다음, **엔터티**를 선택합니다.

1. **흐름 승인** 엔터티에 대한 줄임표 **(...)** 를 선택한 다음, Microsoft Excel에서 데이터를 엽니다.

1. Microsoft Excel에서 필요에 따라 승인 데이터를 검색, 필터링 및 삭제합니다.

Common Data Service를 사용하는 사용자의 DSR에 응답하는 방법에 대한 자세한 내용은 [Executing DSRs against Common Data Service Customer Data](https://go.microsoft.com/fwlink/?linkid=872251)(Common Data Service 고객 데이터에 대해 DSR 실행)를 참조하세요.


## <a name="delete-connections-created-by-a-user"></a>사용자가 만든 연결 삭제

연결을 커넥터와 함께 사용하여 다른 API 및 SaaS 시스템에 대한 연결을 설정합니다.  연결에는 연결을 만든 사용자에 대한 참조가 포함되므로 연결을 삭제하면 사용자에 대한 모든 참조를 제거할 수 있습니다.

PowerApps 작성자 PowerShell cmdlet

사용자는 [PowerApps 작성자 PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871448)의 Remove-Connection 함수를 사용하여 모든 연결을 삭제할 수 있습니다.

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the calling user and deletes them
Get-Connection | Remove-Connection
```

PowerApps 관리자 PowerShell cmdlet

```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all connections for the DSR user and deletes them 
Get-AdminConnection -CreatedBy $deleteDsrUserId | Remove-AdminConnection 

```
## <a name="delete-the-users-permissions-to-shared-connections"></a>공유 연결에 대한 사용자 권한 삭제

PowerApps 작성자 PowerShell cmdlet

사용자는 [PowerApps 작성자 PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871448)의 Remove-ConnectionRoleAssignment 함수를 사용하여 공유 연결에 대한 모든 연결 역할 할당을 삭제할 수 있습니다.

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection role assignments for the calling users and deletes them
Get-ConnectionRoleAssignment | Remove-ConnectionRoleAssignment
```

PowerApps 관리자 PowerShell cmdlet

```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all shared connections for the DSR user and deletes their permissions 
Get-AdminConnectionRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectionRoleAssignment  

```
> [!NOTE]
> 소유자 역할 할당을 삭제하려면 연결 리소스를 삭제해야 합니다.
>
>

## <a name="delete-custom-connectors-created-by-the-user"></a>사용자가 만든 사용자 지정 커넥터 삭제

사용자 지정 커넥터는 기존의 기본 제공 커넥터를 보완하고 다른 API, SaaS 및 사용자 지정 개발 시스템에 대한 연결을 허용합니다. 사용자 지정 커넥터에는 연결을 만든 사용자에 대한 참조가 포함되므로 연결을 삭제하면 사용자에 대한 모든 참조를 제거할 수 있습니다.

PowerApps 작성자 PowerShell cmdlet

사용자는 [PowerApps 작성자 PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871448)의 Remove-Connector 함수를 사용하여 모든 사용자 지정 커넥터를 삭제할 수 있습니다.

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for the calling user and deletes them
Get-Connector -FilterNonCustomConnectors | Remove-Connector
```

PowerApps 관리자 PowerShell cmdlet
```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all custom connectors created by the DSR user and deletes them 
Get-AdminConnector -CreatedBy $deleteDsrUserId | Remove-AdminConnector  

```

## <a name="delete-the-users-permissions-to-shared-custom-connectors"></a>공유된 사용자 지정 커넥터에 대한 사용자 권한 삭제

PowerApps 작성자 PowerShell cmdlet

사용자는 [PowerApps 작성자 PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871448)의 Remove-ConnectorRoleAssignment 함수를 사용하여 공유된 사용자 지정 커넥터에 대한 모든 커넥터 역할 할당을 삭제할 수 있습니다.

```PowerShell
Add-PowerAppsAccount

#Retrieves all connector role assignments for the calling users and deletes them
Get-ConnectorRoleAssignment | Remove-ConnectorRoleAssignment
```

PowerApps 관리자 PowerShell cmdlet
```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all custom connector role assignments for the DSR user and deletes them 
Get-AdminConnectorRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectorRoleAssignment  

```

> [!NOTE]
> 소유자 역할 할당을 삭제하려면 연결 리소스를 삭제해야 합니다.
>
>


## <a name="delete-or-reassign-all-environments-created-by-the-user"></a>사용자가 만든 모든 환경 삭제 또는 다시 할당

관리자로서 사용자가 만든 각 환경에 대한 사용자의 DSR 삭제 요청을 처리할 때 두 가지 의사 결정을 수행해야 합니다.

1. 조직의 다른 사용자가 환경을 사용하고 있지 않음을 확인하면 해당 환경을 삭제할 수 있습니다.
1. 환경이 여전히 필요하다고 판단되는 경우 환경을 삭제하지 않도록 선택하고 자신(또는 조직의 다른 사용자)을 환경 관리자로 추가할 수 있습니다.
> [!IMPORTANT]
> 환경을 삭제하면 모든 앱, 흐름, 연결 등을 포함한 환경 내의 모든 리소스가 영구적으로 삭제되므로 삭제하기 전에 환경의 콘텐츠를 검토하세요.
>
>

## <a name="give-access-to-a-users-environments-from-the-microsoft-flow-admin-center"></a>Microsoft Flow 관리 센터에서 사용자 환경에 대한 액세스 권한 부여

관리자는 [Microsoft Flow 관리 센터](https://admin.flow.microsoft.com/)에서 특정 사용자가 만든 환경에 관리자 액세스 권한을 부여할 수 있습니다. 환경 관리에 대한 자세한 내용은 [Microsoft Flow 내에서 환경 사용](https://docs.microsoft.com/flow/environments-overview-admin)을 참조하세요.

## <a name="delete-the-users-permissions-to-all-other-environments"></a>다른 모든 환경에 대한 사용자 권한 삭제

Microsoft Flow 서비스에 “역할 할당”으로 저장된 특정 환경의 권한을 사용자에게 할당할 수 있습니다(예: 환경 관리자, 환경 작성자 등).

앱용 Common Data Service가 소개되면서 데이터베이스가 환경 내에서 만들어지는 경우 이러한 “역할 할당”은 앱용 Common Data Service 데이터베이스 인스턴스 내에 레코드로 저장됩니다.

환경에서 사용자 권한을 제거하는 방법에 대한 자세한 내용은 [Microsoft Flow 내에서 환경 사용](https://docs.microsoft.com/flow/environments-overview-admin)을 참조하세요.

## <a name="delete-gateway-settings"></a>게이트웨이 설정 삭제
온-프레미스 데이터 게이트웨이의 데이터 주체 삭제 요청에 응답하는 작업은 [여기](https://docs.microsoft.com/power-bi/service-gateway-onprem#tenant-level-administration)에서 찾을 수 있습니다.

## <a name="delete-user-details"></a>사용자 세부 정보 삭제
사용자 세부 정보는 사용자와 특정 테넌트 간의 연결을 제공합니다. 이 명령을 실행하기 전에 이 사용자에 대한 모든 흐름이 다시 할당되거나 삭제되었는지를 확인합니다. 작업이 완료되면 관리자는 **Remove-AdminFlowUserDetails** cmdlet을 호출하고 사용자에 대한 개체 ID를 전달하여 사용자 세부 정보를 삭제할 수 있습니다.


PowerApps 관리자 PowerShell cmdlet
```PowerShell
Add-PowerAppsAccount
Remove-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

> [!IMPORTANT]
> 사용자가 개인 또는 팀 흐름을 소유하는 경우 이 명령은 오류를 반환합니다. 이를 해결하려면 이 사용자에 대한 나머지 모든 흐름 또는 팀 흐름을 삭제하고 명령을 다시 실행합니다.
>
>
## <a name="delete-the-user-from-azure-active-directory"></a>Azure Active Directory에서 사용자 삭제
위의 단계를 모두 완료하면 마지막 단계는 [Office 365 서비스 신뢰 포털](https://servicetrust.microsoft.com/ViewPage/GDPRDSR)에서 찾을 수 있는 Azure 데이터 주체 요청 GDPR 설명서에 설명한 단계를 수행하여 Azure Active Directory에 대한 사용자의 계정을 삭제하는 것입니다.

## <a name="delete-the-user-from-unmanaged-tenant"></a>관리되지 않는 테넌트에서 사용자 삭제
관리되지 않는 테넌트의 멤버인 경우 [직장 및 학교 개인 정보 포털](https://go.microsoft.com/fwlink/?linkid=873123)에서 **계정 종료** 작업을 수행해야 합니다.

관리 또는 관리되지 않는 테넌트의 사용자인지를 확인하려면 다음 작업을 수행합니다.
1. 브라우저에서 다음과 같은 URL([ https://login.windows.net/common/userrealm/foobar@contoso.com?api-version=2.1](https://login.windows.net/common/userrealm/foobar@contoso.com?api-version=2.1))을 열고, URL에서 이메일 주소를 바꿉니다.
1. **관리되지 않는 테넌트**의 멤버인 경우 응답에서 `"IsViral": true`이 표시됩니다.

    {

     "Login": "foobar@unmanagedcontoso.com",

    "DomainName": "unmanagedcontoso.com",

    "IsViral": **true**,
    
    }

1. 그렇지 않은 경우 관리 테넌트에 속해 있습니다.

