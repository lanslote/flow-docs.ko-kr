---
title: GDPR 데이터 주체 요청 요약 | Microsoft Docs
description: Microsoft Flow에 대한 GDPR 데이터 주체 요청에 응답하는 방법을 알아봅니다.
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
ms.openlocfilehash: 6e4763fd3851276d647a302747342a6980293c33
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690798"
---
# <a name="responding-to-gdpr-data-subject-requests-for-microsoft-flow"></a>Microsoft Flow에 대한 GDPR 데이터 주체 요청에 응답

이 문서를 통해 본인과 조직이 유럽 연합의 GDPR(일반 데이터 보호 규정)에 대비할 수 있습니다. 이 문서에서는 GDPR에 대비하기 위해 Microsoft에서 수행 중인 작업을 설명하고, PowerApps, Microsoft Flow 및 앱용 Common Data Service를 사용할 때 GDPR 준수를 지원하기 위해 지금 수행할 수 있는 단계의 예제를 공유합니다.

## <a name="prerequisites"></a>필수 구성 요소

사용자 및 관리자는 이 문서에 설명된 작업을 수행할 수 있습니다.

### <a name="users"></a>사용자

사용자에게 [Microsoft Flow 라이선스](https://preview.flow.microsoft.com/pricing/)가 포함된 활성 Azure Active Directory 계정이 있어야 합니다. 이 요구 사항을 충족하지 않는 사용자는 관리자에게 이러한 작업을 수행하도록 요청해야 합니다.

### <a name="administrators"></a>관리자

다음 권한이 둘 다 포함된 계정으로 [Microsoft Flow 관리 센터](https://admin.flow.microsoft.com/) 또는 [PowerApps 관리자 PowerShell](https://go.microsoft.com/fwlink/?linkid=871804)에 로그인할 경우 이 문서에 설명된 관리 권한이 필요한 작업을 수행할 수 있습니다.

- PowerApps 요금제 2에 대한 유료 또는 평가판 라이선스.

    [평가판 라이선스](http://web.powerapps.com/trial)는 30일 후에 만료됩니다.

- [Office 365 전역 관리자](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) 또는 [Azure Active Directory 전역 관리자](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal).

### <a name="unmanaged-tenants"></a>관리되지 않는 테넌트
[관리되지 않는 테넌트](https://docs.microsoft.com/azure/active-directory/domains-admin-takeover)의 멤버인 경우 Azure AD 테넌트에 전역 관리자가 없습니다. 그러면 고유한 개인 데이터를 내보내고 제거하기 위해 이 아티클에 설명된 단계를 수행할 수 있습니다. 

## <a name="responding-to-dsrs-for-microsoft-flow-customer-data"></a>Microsoft Flow 고객 데이터에 대한 DSR에 응답

GDPR은 사람들(GDPR에서 데이터 주체)에게 고용주 또는 다른 유형의 기관이나 조직(데이터 컨트롤러 또는 간단하게 컨트롤러)에 의해 수집된 개인 데이터를 관리할 권한을 제공합니다. GDPR에서 개인 데이터는 식별되거나 식별 가능한 자연인에 관련된 모든 데이터로 매우 광범위하게 정의됩니다. GDPR은 데이터 주체에게 개인 데이터에 대한 특정 권한을 제공합니다. 이러한 권한에는 개인 데이터의 복사본을 얻거나, 개인 데이터에 대한 수정을 요청하거나, 개인 데이터의 처리를 제한하거나, 개인 데이터를 삭제하거나, 다른 컨트롤러에게 이동할 수 있도록 전자 형식으로 개인 데이터를 수신할 권한이 포함됩니다. 데이터 주체가 개인 데이터에 대한 작업을 수행하도록 컨트롤러에게 공식적으로 요청하는 것을 DSR(데이터 주체 권한) 요청이라고 합니다.

이 문서에서는 Microsoft 제품, 서비스 및 관리 도구를 사용하여 컨트롤러가 DSR에 응답할 때 개인 데이터를 찾고 이에 대한 조치를 취하도록 돕는 방법을 설명합니다. 특히 이 문서에는 Microsoft 클라우드에 있는 개인 데이터를 찾고, 액세스하고, 조치를 취하는 방법이 포함됩니다. 이 가이드에 설명된 프로세스에 대한 간략한 개요는 다음과 같습니다.

1. 검색: 검색 및 검색 도구를 사용하여 DSR의 대상이 될 수 있는 고객 데이터를 더 쉽게 찾을 수 있습니다. 잠재적으로 반응형 문서가 수집되면 다음 단계에 설명된 하나 이상의 DSR 작업을 수행하여 요청에 응답할 수 있습니다. 또는 요청이 DSR 요청에 응답하기 위한 조직의 지침을 충족하지 않는다고 판단할 수 있습니다. [Microsoft Flow DSR 검색 설명서](gdpr-dsr-discovery.md)

1. 액세스: Microsoft 클라우드에 있는 개인 데이터를 검색하고 요청된 경우 데이터 주체에게 제공할 수 있는 복사본을 만듭니다.

1. 수정: 개인 데이터를 변경하고 개인 데이터에 대한 다른 요청된 작업을 구현합니다(해당하는 경우).

    데이터 주체가 조직에 있는 개인 데이터를 수정하도록 요청하는 경우 본인과 조직은 요청을 수용하는 것이 적절한지 결정해야 합니다.  데이터 수정에는 개인 데이터를 편집, 수정 또는 제거하는 등의 작업 수행이 포함될 수 있습니다.

    Azure Active Directory를 사용하여 Microsoft Flow 사용자의 ID를 관리할 수 있습니다. 엔터프라이즈 고객은 제공된 Microsoft 서비스의 특성에 따른 제한된 편집 기능을 포함하여 DSR 수정 요청을 관리할 수 있습니다.  Microsoft는 데이터 프로세서로서 시스템에서 생성된 로그가 Microsoft 서비스 내에서 실제 활동을 반영하고 이벤트 기록 레코드를 구성하기 때문에 이 로그를 수정하는 기능을 제공하지 않습니다.  [DSR에 대해 자세히 알아보세요](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure).

1. 제한: 다양한 온라인 서비스에 대한 라이선스를 제거하거나 가능한 경우 원하는 서비스를 꺼서 개인 데이터의 처리를 제한합니다. Microsoft 클라우드에서 데이터를 제거하고 온-프레미스 또는 다른 위치에 보존할 수도 있습니다.

    데이터 주체는 개인 데이터 처리를 제한하도록 요청할 수 있습니다.  Microsoft는 이 목적으로 API(응용 프로그래밍 인터페이스)와 UI(사용자 인터페이스)를 제공합니다.  이러한 인터페이스를 사용하여 엔터프라이즈 고객의 테넌트 관리자는 데이터 내보내기 및 데이터 삭제의 조합을 통해 DSR을 관리할 수 있습니다. 고객은 (1) 계정, 시스템 생성 로그 및 연결된 로그를 포함한 사용자 개인 데이터의 전자 복사본을 내보낸 다음, (2) Microsoft 시스템 내에 있는 계정 및 연결된 데이터를 삭제할 수 있습니다.

1. 삭제: Microsoft 클라우드에 있는 개인 데이터를 영구적으로 제거합니다. [개인 데이터 삭제에 대해 자세히 알아보세요](gdpr-dsr-delete.md).

1. 내보내기: 개인 데이터의 전자 복사본(컴퓨터에서 읽을 수 있는 형식으로)을 데이터 주체에게 제공합니다. 이 문서의 각 섹션에서는 데이터 컨트롤러 조직이 Microsoft 클라우드의 개인 데이터에 대한 DSR 요청에 응답하기 위해 수행할 수 있는 기술적인 절차를 설명합니다. [개인 데이터 내보내기에 대해 자세히 알아보세요](gdpr-dsr-export.md).

## <a name="system-generated-logs"></a>시스템 생성 로그

Microsoft Flow의 시스템 생성 로그에 대한 자세한 내용은 이 [가이드](https://docs.microsoft.com/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs)를 참조하세요.
