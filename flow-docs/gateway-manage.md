---
title: "온-프레미스 데이터 게이트웨이 관리에 대해 알아보기 | Microsoft Docs"
description: "Microsoft Flow에서 온-프레미스 데이터 게이트웨이 보기 및 설치"
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2017
ms.author: deonhe
ms.openlocfilehash: 41f5d40ca2ad5fcce3a7967beef7104dd532b1d8
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2017
---
# <a name="manage-an-on-premises-data-gateway-in-microsoft-flow"></a>Microsoft Flow에서 온-프레미스 데이터 게이트웨이 관리에 대해 알아보기
Microsoft Flow를 통해, 온-프레미스 데이터 게이트웨이를 설치 및 관리하여 여러 클라우드 기반 앱을 온-프레미스 데이터 및 앱과 완전하게 통합합니다.

게이트웨이로 이런한 연결을 통해 온-프레미스 데이터에 연결할 수 있습니다.

* SharePoint
* SQL Server
* Oracle
* Informix
* Filesystem
* DB2

> [!IMPORTANT]
> Microsoft SharePoint 데이터 게이트웨이는 HTTP 트래픽을 지원하지만 HTTPS 트래픽은 지원하지 않습니다.
> 
> 

## <a name="prerequisites"></a>필수 구성 요소
* Microsoft Flow에 [가입](sign-up-sign-in.md)하는 데 사용한 사용자 이름과 암호
* 게이트웨이 관리 권한
  
  설치하는 각 게이트웨이에 대해 기본적으로 이 권한을 갖게 되며, 다른 게이트웨이의 관리자는 해당 게이트웨이에 대해 이러한 권한을 부여할 수 있습니다.
* 게이트웨이를 지원하는 라이선스 자세한 내용은 [가격 책정 페이지](https://flow.microsoft.com/pricing/)의 “연결” 섹션을 참조하세요.
* [기본 환경](environments-overview-maker.md)에서만 게이트웨이 및 온-프레미스 연결을 만들 수 있습니다.

## <a name="view-your-gateways"></a>게이트웨이 보기
[Microsoft Flow 웹 사이트](https://flow.microsoft.com)의 오른쪽 위에서 기어 아이콘을 클릭하거나 누른 다음 **게이트웨이**를 클릭하거나 누릅니다.

![관리 중인 게이트웨이][1]

**참고**: PowerApps에서 게이트웨이를 만들거나 액세스 권한을 부여하면 해당 게이트웨이가 Microsoft Flow의 **내 게이트웨이** 목록에 나타납니다.

## <a name="install-a-gateway"></a>게이트웨이 설치
1. [게이트웨이 설치 마법사](http://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409)를 다운로드합니다.
   
    [Microsoft Flow 웹 사이트](https://flow.microsoft.com)의 오른쪽 위에서 기어 아이콘을 클릭하거나 누르고 **게이트웨이**를 클릭하거나 누른 다음 **게이트웨이 만들기**를 클릭하거나 눌러 이 마법사를 다운로드할 수도 있습니다.
   
    ![게이트웨이 설치][2]
2. Microsoft Flow에 로그인하는 것과 같은 자격 증명을 제공하여 이 마법사를 실행합니다.
   
    게이트웨이 등록 및 구성을 마친 후에는 Microsoft Flow의 **내 게이트웨이** 목록에 표시됩니다.

자세한 내용은 [게이트웨이 이해](gateway-reference.md)를 참조하세요.

<!-- Image references -->
[1]: ./media/manage-gateway/view-gateways.png
[2]: ./media/manage-gateway/list-gateways.png
