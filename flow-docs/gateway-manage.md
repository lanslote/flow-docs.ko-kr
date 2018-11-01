---
title: 온-프레미스 데이터 게이트웨이 관리에 대해 알아보기 | Microsoft Docs
description: Microsoft Flow에서 온-프레미스 데이터 게이트웨이 보기 및 설치
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
ms.date: 02/05/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b25f63a3980d21e60b26a0783ac4bf5eb6030cd3
ms.sourcegitcommit: 282059c82bfcf5896d06043476c34641906e20e3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/11/2018
ms.locfileid: "49087911"
---
# <a name="manage-an-on-premises-data-gateway-in-microsoft-flow"></a>Microsoft Flow에서 온-프레미스 데이터 게이트웨이 관리에 대해 알아보기

Microsoft Flow를 통해, 온-프레미스 데이터 게이트웨이를 설치 및 관리하여 여러 클라우드 기반 앱을 온-프레미스 데이터 및 앱과 완전하게 통합합니다.

게이트웨이로 이런한 연결을 통해 온-프레미스 데이터에 연결할 수 있습니다.

* Apache Impala
* 만들 사용자 지정 커넥터
* DB2
* 파일 시스템
* Azure AD를 사용한 Http
* Informix
* MySQL
* Oracle Database
* PostgreSQL
* SharePoint
* SQL Server
* Teradata(미리 보기)

> [!IMPORTANT]
> Microsoft SharePoint 데이터 게이트웨이는 이제 HTTP와 HTTPS 트래픽을 모두 지원합니다.

## <a name="prerequisites"></a>필수 구성 요소

* Microsoft Flow에 [가입](sign-up-sign-in.md)하는 데 사용한 사용자 이름과 암호
* 게이트웨이 관리 권한

  설치하는 각 게이트웨이에 대해 기본적으로 이러한 권한을 갖습니다. 또한 다른 게이트웨이의 관리자가 해당 게이트웨이에 대해 이러한 권한을 부여할 수 있습니다.
* 게이트웨이를 지원하는 라이선스 자세한 내용은 [가격 책정 페이지](https://flow.microsoft.com/pricing/)의 “연결” 섹션을 참조하세요.

> [!NOTE]
> [기본 환경](environments-overview-maker.md)에서만 게이트웨이 및 온-프레미스 연결을 만들 수 있습니다.



## <a name="view-your-gateways"></a>게이트웨이 보기

[Microsoft Flow 웹 사이트](https://flow.microsoft.com)의 오른쪽 위에서 기어 아이콘을 선택한 다음, **게이트웨이**를 선택합니다.

![관리 중인 게이트웨이][1]

> [!NOTE]
> PowerApps에서 게이트웨이를 만들거나 액세스 권한을 부여하면 해당 게이트웨이가 Microsoft Flow의 **내 게이트웨이** 목록에 나타납니다.



## <a name="install-a-gateway"></a>게이트웨이 설치

1. [게이트웨이 설치 마법사](https://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409)를 다운로드합니다.

1. 마법사를 실행하고 Microsoft Flow에 로그인하는 것과 같은 자격 증명을 제공합니다.

    게이트웨이 등록 및 구성을 마친 후에는 Microsoft Flow의 **게이트웨이** 목록에 표시됩니다.

자세한 내용은 [게이트웨이 이해](gateway-reference.md)를 참조하세요.

<!-- Image references -->
[1]: ./media/manage-gateway/view-gateways.png
