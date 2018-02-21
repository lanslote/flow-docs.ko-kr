---
title: "엔터프라이즈 개발자, ISV 및 파트너를 위한 Microsoft Flow | Microsoft Docs"
description: "Microsoft Flow에 대한 솔루션 개발을 소개합니다."
services: 
suite: flow
documentationcenter: na
author: mgblythe
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2018
ms.author: mblythe
ms.openlocfilehash: d8886f0828ca3b8ccf7ae1ce9c46f6e9b8fcc766
ms.sourcegitcommit: f3261717768177e03e825c0dd2e3ba736dc9b94d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2018
---
# <a name="microsoft-flow-for-enterprise-developers-isvs-and-partners"></a>엔터프라이즈 개발자, ISV 및 파트너를 위한 Microsoft Flow

개발자는 Microsoft Flow를 확장하여 조직 및 고객에게 훨씬 더 강력한 솔루션을 제공할 수 있습니다.

## <a name="microsoft-flow-for-enterprise-developers"></a>엔터프라이즈 개발자를 위한 Microsoft Flow

엔터프라이즈 개발자로서 조직의 역량을 강화하여 Microsoft Flow에 맞게 조정된 강력한 솔루션을 구축합니다.

- **사용자 지정 커넥터 빌드**: Microsoft Flow를 통해 조직의 데이터 및 웹 서비스에 연결하는 사용자 지정 커넥터를 개발합니다. [자세히 알아보기](https://docs.microsoft.com/connectors/custom-connectors/)

- **Azure Functions 빌드**: Azure Functions를 만들어 사용자 지정 서버 쪽 논리로 앱을 확장합니다. [자세히 알아보기](https://docs.microsoft.com/azure/azure-functions/functions-flow-scenario)

- **Microsoft Flow 포함**: 조직의 사용자가 해당 작업을 수행하는 통합된 솔루션, 표면 워크플로 또는 프로세스를 만들려는 웹 사이트 경험에 직접 Microsoft Flow를 포함합니다. [자세히 알아보기](embed-flow-dev.md)

## <a name="microsoft-flow-for-isvs-and-microsoft-partners"></a>ISV 및 Microsoft 파트너를 위한 Microsoft Flow

Microsoft 파트너 또는 ISV(독립 소프트웨어 공급업체)로써 고객의 데이터 및 비즈니스 프로세스와 통합된 제품을 확장하여 도입을 가속화하고, 응용 프로그램의 일부로 비즈니스 프로세스를 자동화하도록 워크플로를 사용자 지정합니다. 아래의 7가지 단계를 완료한 후에 응용 프로그램에는 200개 이상의 다른 서비스에 연결할 수 있는 강력한 클라우드 규모의 워크플로 엔진을 활용할 수 있는 기능이 포함됩니다.

| 단계 | 단계 | 필요한 경우 |
| --- | --- | --- |
| 개발 | 1. 데이터에 대한 사용자 지정 커넥터 빌드 | PowerApps 또는 Microsoft Flow에 고유한 ISV 데이터를 노출하려는 경우 |
| 개발 | 2. Azure AD(Azure Active Directory)를 사용하여 사용자를 인증하도록 응용 프로그램에 대한 지원 추가 | Microsoft Flow UI에 포함하거나 Microsoft AppSource에 나열하려는 경우 | 
| 개발 | 3. 웹 기반 iframe을 사용하여 Microsoft Flow UI를 응용 프로그램에 포함 | 응용 프로그램에 흐름 생성 또는 관리를 포함하려는 경우 | 
| 개발 | 4. 흐름 템플릿 만들기 및 게시 | 고객에 대한 흐름을 미리 빌드하려는 경우 | 
| 개발 | 5. 프로그래밍 방식으로 흐름을 배포하는 응용 프로그램 논리 추가 | 고객에게 미리 빌드된 흐름을 자동으로 배포하려는 경우 | 
| 분포 | 6. Microsoft 클라우드 솔루션 공급자 프로그램을 통해 사용자에게 Microsoft Flow에 대한 라이선스 부여 | 고객에게 Office 365 또는 Dynamics 365 라이선스가 없는 경우 |
| 분포 | 7. Microsoft AppSource에 솔루션 나열 | ISV 솔루션의 가시성을 증가시키는 것이 좋습니다. |

### <a name="1-connecting-to-your-apis-or-enabling-customers-to-connect-to-your-apis"></a>1. API에 연결 또는 고객이 API에 연결하도록 설정

ISV에서는 고객이 흐름을 통해 액세스하는 소유 데이터가 있는 경우가 많습니다. 사용자 지정 커넥터를 통해 데이터에 대한 액세스 권한을 노출할 수 있습니다. [자세히 알아보기](https://docs.microsoft.com/connectors/custom-connectors/)

일단 커넥터를 만들면 고객이 사용할 수 있도록 하는 두 가지 방법이 있습니다.
- REST API 또는 PowerShell을 통해 고객의 테넌트에 커넥터를 배포할 수 있습니다.
- 모든 사용자가 사용자 지정 커넥터를 공개적으로 사용할 수 있도록 하려면 인증을 위해 커넥터를 제출할 수 있습니다. [자세히 알아보기](https://docs.microsoft.com/connectors/custom-connectors/submit-certification)

### <a name="2-authentication"></a>2. 인증 

REST API를 호출하고 인증된 UI를 포함하려면 응용 프로그램이 Azure AD 페더레이션 Single Sign-On을 사용하여 최종 사용자 및 고객을 인증해야 합니다. AAD 페더레이된 SSO를 사용하는 방법에 대한 정보는 [여기로 이동](https://identity.microsoft.com/)하세요. 인증되지 않은 액세스 및 Azure AD 이외의 ID 공급자를 사용하는 액세스를 지원하지 않습니다. 

### <a name="3-embedding-ui-components"></a>3. UI 구성 요소 포함

앱 내에 Microsoft Flow를 포함하여 앱과 Microsoft Flow가 지원하는 모든 다른 서비스 간에 심층적인 컨텍스트 통합을 활성화할 수 있습니다. [자세히 알아보기](embed-flow-dev.md)

### <a name="4-create-and-publish-flow-templates"></a>4. 흐름 템플릿 만들기 및 게시

커넥터를 만든 후 서비스를 사용하는 방법을 보여 주는 템플릿을 게시해야 합니다. 이러한 템플릿은 사용자가 학습한 다음 자신의 고유한 워크플로로 확장하는 데 사용할 수 있는 예제로 제공됩니다. [자세히 알아보기](publish-a-template.md)

### <a name="5-deployment"></a>5. 배포

최종 사용자에게 자동으로 사용할 수 있는 흐름에 대한 액세스 권한을 부여하려면 사용자의 Azure AD 테넌트에 흐름을 배포합니다. REST API 또는 PowerShell을 사용하여 배포하는 배포 패키지를 사용합니다. [자세히 알아보기](https://docs.microsoft.com/powerapps/export-import-packages)

### <a name="6-licensing"></a>6. 라이선스

고객에게 Office 365 또는 Dynamics 365가 이미 설치되어 있고 이러한 라이선스가 Azure AD에 로그인하는 사용자 ID와 연결되어 있는 경우 추가 라이선스가 요구되지 않습니다. 그러나 고객이 Office 365 또는 Dynamics 365를 사용하지 않는 경우 Microsoft Flow 대신 해당 프로그램에 대한 권한을 취득해야 합니다. 그러면 응용 프로그램에서 포함된 해당 구성 요소를 활용하도록 허가를 받게 됩니다.

[Microsoft 클라우드 솔루션 공급자](https://partner.microsoft.com/cloud-solution-provider) 프로그램을 제공하여 고객 대신 라이선스를 취득합니다. Microsoft Flow에 사용할 수 있는 두 개의 [가격 책정 계획](https://flow.microsoft.com/pricing/)이 있습니다. 여기서는 계획 및 기능 세부 정보를 확인해야 합니다.

### <a name="7-list-on-appsource"></a>7. AppSource에 등록

Microsoft Flow를 응용 프로그램에 통합하면 AppSource에 등록할 수 있습니다. AppSource를 사용하여 앱을 빌드하고 새 고객이 시험 사용할 수 있도록 AppSource에 게시하여 비즈니스에 대한 새 잠재 고객을 생성합니다. [자세히 알아보기](dev-appsource-test-drive.md)
