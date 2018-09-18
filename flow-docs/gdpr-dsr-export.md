---
title: Microsoft Flow GDPR 데이터 주체 내보내기 요청 | Microsoft Docs
description: Microsoft Flow를 사용하여 GDPR 데이터 주체 내보내기 요청에 응답하는 방법을 알아봅니다.
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
ms.date: 4/24/2018
ms.author: keweare
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: e0f9b8e5b345b4dbc226cff2f42850bb126c09b3
ms.sourcegitcommit: 44bc9de9f06b64615731ceb60a4f46cfcd45b167
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45727139"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-microsoft-flow"></a>Microsoft Flow에 대한 GDPR 데이터 주체 내보내기 요청에 응답

GDPR(일반 데이터 보호 규정) 준수 과정을 지원하기 위한 노력의 일환으로 Microsoft는 준비를 돕기 위해 이 설명서를 개발했습니다. 이 설명서에서는 GDPR에 대비하기 위해 수행할 작업을 설명하고, Microsoft Flow를 사용할 때 GDPR 준수를 지원하기 위해 지금 Microsoft와 함께 수행할 수 있는 단계의 예제를 공유합니다.

## <a name="manage-export-requests"></a>내보내기 요청 관리

‘데이터 이식성 권한’을 사용하면 데이터 주체가 다른 데이터 컨트롤러에게 전송될 수 있는 자신의 개인 데이터 복사본을 전자 형식(구조화되고, 일반적으로 사용되고, 컴퓨터에서 읽을 수 있고, 상호 운용 가능한 형식)으로 요청할 수 있습니다.

Microsoft Flow는 특정 사용자에 대한 개인 데이터를 찾거나 내보내기 위한 다음과 같은 환경을 제공합니다.

* **웹 사이트 액세스:** [PowerApps 관리 센터](https://admin.powerapps.com/) 또는 [Microsoft Flow 관리 센터](https://admin.flow.microsoft.com/)에 로그인.

* **PowerShell 액세스:** [PowerApps 관리자 PowerShell cdmlet](https://go.microsoft.com/fwlink/?linkid=871804).

|**고객 데이터**|**웹 사이트 액세스**|**PowerShell 액세스**|
|-----------------|------------------|-------------------|
|시스템 생성 로그|[Office 365 Service Trust Portal](https://servicetrust.microsoft.com/)|
|실행 기록|Microsoft Flow 작성자 포털||
|흐름|Microsoft Flow 작성자 포털||
|흐름 권한| Microsoft Flow 작성자 포털 및 Microsoft Flow 관리 센터||
|사용자 세부 정보||PowerApps cmdlet|
|연결|Microsoft Flow 작성자 포털|PowerApps cmdlet |
|연결 권한|Microsoft Flow 작성자 포털|PowerApps cmdlet |
|사용자 지정 커넥터|Microsoft Flow 작성자 포털|PowerApps cmdlet |
|사용자 지정 커넥터 권한|Microsoft Flow 작성자 포털|PowerApps cmdlet |
|게이트웨이|Microsoft Flow 작성자 포털|온-프레미스 데이터 게이트웨이 PowerShell cmdlet|
|게이트웨이 권한|Microsoft Flow 작성자 포털|온-프레미스 데이터 게이트웨이 PowerShell cmdlet|

## <a name="export-a-flow"></a>흐름 내보내기

흐름에 대한 액세스 권한이 부여된 최종 사용자 또는 관리자는 다음 단계에 따라 흐름을 내보낼 수 있습니다.

1. [Microsoft Flow](https://flow.microsoft.com/)에 로그인합니다.

1. **내 흐름** 링크를 선택한 다음, 내보낼 흐름을 선택합니다.

1. **... 더보기**를 선택한 다음, **내보내기**를 선택합니다.

    ![흐름 내보내기](./media/gdpr-dsr-export/export-flow.png)

1. **패키지(.zip)** 를 선택합니다.

이제 흐름을 압축된 패키지로 사용할 수 있습니다. 자세한 내용은 [흐름을 내보내기고 가져오는 방법](https://flow.microsoft.com/blog/import-export-bap-packages/)에 대한 블로그 게시물을 참조하세요.

## <a name="export-run-history"></a>실행 기록 내보내기

실행 기록에는 흐름에 대해 발생한 모든 실행 목록이 포함됩니다. 이 데이터에는 트리거 및 작업에 대한 흐름의 상태, 시작 시간, 기간 및 입력/출력 데이터가 포함됩니다.

Microsoft Flow 관리 센터를 통해 흐름에 대한 액세스 권한이 부여된 최종 사용자 또는 관리자는 다음 단계에 따라 이 데이터를 내보낼 수 있습니다.

1. [Microsoft Flow](https://flow.microsoft.com/)에 로그인합니다.
1. **내 흐름** 링크를 선택한 다음, 실행 기록을 내보낼 흐름을 선택합니다.
1. **실행 기록** 창에서 **모두 보기**를 선택합니다.

    ![실행 기록](./media/gdpr-dsr-export/run-history.png)

1. **CSV 다운로드**를 선택합니다.

    ![CSV 다운로드](./media/gdpr-dsr-export/download-csv.png)

실행 기록은 .csv 파일로 다운로드되므로 Microsoft Excel 또는 텍스트 편집기에서 열고 결과를 추가로 분석할 수 있습니다.

## <a name="export-a-users-activity-feed"></a>사용자의 작업 피드 내보내기

[Microsoft Flow](https://flow.microsoft.com/)에서 작업 피드는 사용자의 작업, 실패 및 알림에 대한 기록을 표시합니다. 모든 사용자는 다음 단계에 따라 작업 피드를 볼 수 있습니다.

1. [Microsoft Flow](http://flow.microsoft.com/)에 로그인하고 오른쪽 위 모서리 근처의 벨 아이콘을 선택한 다음, **작업 피드로 이동**을 선택합니다.

    ![작업 피드 표시](./media/gdpr-dsr-export/show-activity-feed.png)

1. **작업** 화면에서 결과를 복사한 다음, Microsoft Word 같은 문서 편집기에 붙여넣습니다.

    ![작업 피드 표시](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>사용자의 연결 내보내기

연결을 통해 흐름이 API, SaaS 응용 프로그램 및 기타 타사 시스템에 연결될 수 있습니다. 연결을 보려면 다음 단계를 수행합니다.

1. [Microsoft Flow](http://flow.microsoft.com/)에 로그인하고 오른쪽 위 모서리 근처의 기어 아이콘을 선택한 다음, **연결**을 선택합니다.

    ![연결 표시](./media/gdpr-dsr-export/show-connections.png)
1. 결과를 복사한 다음, Microsoft Word 같은 문서 편집기에 붙여넣습니다.

PowerApps 관리자 PowerShell cmdlet

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnection -CreateBy $userId | ConvertTo-Json |Out-File -FilePath "UserConnections.txt"
```

## <a name="export-a-list-of-a-users-connection-permissions"></a>사용자의 연결 권한 목록 내보내기

사용자는 [PowerApps PowerShell cdmlet](https://go.microsoft.com/fwlink/?linkid=871804)의 Get-ConnectionRoleAssignment 함수를 통해 액세스 권한이 있는 모든 연결에 대한 연결 역할 할당을 내보낼 수 있습니다.

```PowerShell
Add-PowerAppsAccount
Get-ConnectionRoleAssignment | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt"
```
PowerApps 관리자 PowerShell cmdlet

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectionRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt" 
```

## <a name="export-a-users-custom-connectors"></a>사용자의 사용자 지정 커넥터 내보내기

사용자 지정 커넥터는 기본 제공 커넥터를 보완하고 다른 API, SaaS 및 사용자 지정 개발 시스템에 대한 연결을 허용합니다. 사용자 지정 커넥터의 소유권을 이전하거나 삭제할 수 있습니다.

다음 단계에 따라 고객 커넥터 목록을 내보냅니다.

1. [Microsoft Flow](https://flow.microsoft.com)로 이동합니다.
1. 설정 **기어** 아이콘을 선택합니다.
1. **사용자 지정 커넥터**를 선택합니다.
1. 사용자 지정 커넥터 목록을 복사하여 Microsoft Word와 같은 텍스트 편집기에 붙여넣습니다.

    ![사용자 지정 커넥터 내보내기](./media/gdpr-dsr-export/export-custom-connectors.png)

Microsoft Flow에서 제공하는 환경 외에도 [PowerApps PowerShell cmdlet](https://go.microsoft.com/fwlink/?linkid=871804)의 Get-Connector 함수를 사용하여 모든 사용자 지정 커넥터를 내보낼 수 있습니다.

~~~~
Add-PowerAppsAccount
Get-Connector -FilterNonCustomConnectors | ConvertTo-Json | Out-File -FilePath "CustomConnectors.txt"
~~~~

PowerApps 관리자 PowerShell cmdlet

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnector -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserCustomConnectors.txt"  
```

## <a name="export-a-users-custom-connector-permissions"></a>사용자의 사용자 지정 커넥터 권한 내보내기

사용자는 [PowerApps PowerShell cdmlet](https://go.microsoft.com/fwlink/?linkid=871804)의 Get-ConnectorRoleAssignment 함수를 통해 자신이 만든 모든 사용자 지정 커넥터 권한을 내보낼 수 있습니다.

```PowerShell
Add-PowerAppsAccount
Get-ConnectorRoleAssignment | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"
```

PowerApps 관리자 PowerShell cmdlet

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectorRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"   
```

## <a name="export-approval-history"></a>승인 기록 내보내기

Microsoft Flow 승인 기록은 사용자에 대해 받거나 보낸 승인의 기록 레코드를 캡처합니다. 모든 사용자는 다음을 통해 승인 기록을 볼 수 있습니다.

1. [Microsoft Flow](http://flow.microsoft.com/)에 로그인하고 **승인**을 선택한 다음, **기록**을 선택합니다.

    ![승인 기록 보기](./media/gdpr-dsr-export/view-approval-history.png)

1. 목록에는 사용자가 받은 승인이 표시됩니다. 사용자는 **받음** 옆에 있는 아래쪽 화살표를 선택한 다음, **보냄**을 선택하여 보낸 승인을 표시할 수 있습니다.

    ![받은 승인 보기](./media/gdpr-dsr-export/view-received-approvals.png)

## <a name="export-user-details"></a>사용자 세부 정보 내보내기
사용자 세부 정보는 사용자와 특정 테넌트 간의 연결을 제공합니다. 관리자는 **Get-AdminFlowUserDetails** cmdlet을 호출하고 사용자의 개체 ID를 전달하여 이 정보를 내보낼 수 있습니다.

PowerApps 관리자 PowerShell cmdlet

```PowerShell
Add-PowerAppsAccount

Get-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

## <a name="export-gateway-settings"></a>게이트웨이 설정 내보내기
온-프레미스 데이터 게이트웨이의 데이터 주체 내보내기 요청에 응답하는 작업은 [여기](https://docs.microsoft.com/power-bi/service-gateway-onprem#tenant-level-administration)에서 찾을 수 있습니다.

