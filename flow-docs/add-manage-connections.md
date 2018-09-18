---
title: 연결 및 온-프레미스 데이터 게이트웨이를 사용하여 데이터에 연결하는 방법 알아보기 | Microsoft Docs
description: SharePoint, SQL Server, OneDrive for Business, Salesforce, Office 365, OneDrive, Dropbox, Twitter, Google Drive 등에 대한 연결 추가 또는 관리
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
ms.date: 02/15/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: bdfa1072bca2afc7c608a4dbf68b8f598dff89f1
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689114"
---
# <a name="manage-connections-in-microsoft-flow"></a>Microsoft Flow의 연결 관리
Microsoft Flow에서 연결을 만들면 흐름을 작성하는 동안 간편하게 데이터에 액세스할 수 있습니다. Microsoft Flow에는 SharePoint, SQL Server, Office 365, OneDrive for Business, Salesforce, Excel, Dropbox, Twitter 등, 일반적으로 사용되는 연결이 포함됩니다. 연결은 PowerApps와 공유하므로 한 제품에서 연결을 만들면 다른 제품에 해당 연결이 표시됩니다.

예를 들어 연결을 사용하여 다음과 같은 작업을 수행할 수 있습니다.

* SharePoint 목록을 업데이트합니다.
* OneDrive for Business 또는 Dropbox 계정의 Excel 파일에서 데이터를 가져옵니다.
* Office 365에서 전자 메일을 보냅니다.
* 트윗을 보냅니다.

다음과 같은 여러 시나리오에서 연결을 만들 수 있습니다.

* [템플릿에서 흐름](get-started-logic-template.md) 만들기
* [공백에서 흐름](get-started-logic-flow.md) 만들기 또는 기존 흐름 업데이트
* [Microsoft Flow 포털][1]에서 바로 연결 만들기

이 토픽에서는 [Microsoft Flow 웹 사이트][1]에서의 연결 관리 방법을 보여 줍니다.

## <a name="add-a-connection"></a>연결 추가
1. [Microsoft Flow 웹 사이트][1]에서 직장 또는 조직 계정으로 로그인합니다.
2. 오른쪽 위에서 기어 아이콘을 선택한 다음 **연결**을 선택합니다.
   
    ![연결 선택](./media/add-manage-connections/connections-menu.png)
3. **연결 만들기**를 선택합니다.
4. **사용 가능한 연결** 목록에서 SharePoint 등, 설정하려는 연결을 선택합니다.
5. **연결 만들기** 단추를 선택한 다음 연결을 설정할 자격 증명을 입력합니다.

연결이 설정되면 **내 연결** 목록에 나타납니다.

## <a name="connect-to-your-data-through-an-on-premises-data-gateway"></a>온-프레미스 데이터 게이트웨이를 통해 데이터에 연결
이 문서의 작성 시점인 현재 SQL Server와 SharePoint Server는 온-프레미스 데이터 게이트웨이를 지원합니다. 게이트웨이 사용하는 연결을 만들려면:

1. 이 토픽의 앞 부분의 단계에 따라 연결을 추가합니다.
2. **사용 가능한 연결** 목록에서 **SQL Server** 를 선택하고 **온-프레미스 데이터 게이트웨이 통해 연결** 확인란을 선택합니다.
   
    ![게이트웨이 선택 ](./media/add-manage-connections/select-gateway.png)
   
   > [!IMPORTANT]
   > Microsoft SharePoint 데이터 게이트웨이는 HTTP 트래픽을 지원하지만 HTTPS 트래픽은 지원하지 않습니다.
   > 
   > 
3. 연결의 자격 증명을 제공한 다음 사용할 게이트웨이를 선택합니다.
   
    자세한 내용은 [게이트웨이 관리](gateway-manage.md) 및 [게이트웨이 이해](gateway-reference.md)를 참조하세요.
   
    연결이 설정되면 **내 연결** 목록에 나타납니다.

## <a name="delete-a-connection"></a>연결 삭제
1. **내 연결** 페이지로 이동한 다음 삭제할 연결의 휴지통 아이콘을 선택합니다.
   
    ![연결 삭제](./media/add-manage-connections/delete-connection.png)
2. **확인** 을 선택하여 연결 삭제를 확인합니다.
   
    ![삭제 확인](./media/add-manage-connections/delete-confirmation.png)

연결을 삭제하면 PowerApps와 Microsoft Flow 둘 다에서 제거됩니다.

## <a name="update-a-connection"></a>연결 업데이트
계정 세부 정보 또는 암호가 변경되어 작동하지 않는 연결을 업데이트할 수 있습니다.

1. **내 연결** 페이지에서 업데이트할 연결의 **암호 확인** 링크를 선택합니다.
   
    ![암호 확인](./media/add-manage-connections/verify-password.png)
2. 대화 상자가 나타나면 새 자격 증명으로 연결을 업데이트합니다.

연결을 업데이트하면 PowerApps와 Microsoft Flow 모두에 대해 업데이트됩니다.

## <a name="troubleshoot-a-connection"></a>연결 문제 해결
조직의 정책에 따라 Microsoft Flow에 로그인 및 SharePoint, Office 365 또는 OneDrive for Business에 대한 연결 만들기에 동일한 계정을 사용해야 할 수 있습니다.

예를 들어 *yourname@outlook.com* 로 Microsoft Flow에 로그인하지만 *yourname@contoso.com* 으로 SharePoint에 연결을 시도하면 차단될 수 있습니다. 대신에 *yourname@contoso.com* 로 Microsoft Flow에 로그인하면 SharePoint에 연결할 수 있습니다.

<!--Reference links in article-->
[1]: https://flow.microsoft.com
