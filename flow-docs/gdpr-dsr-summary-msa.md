---
title: MSA(Microsoft 계정)에 대한 GDPR 데이터 주체 요청 요약 | Microsoft Docs
description: Microsoft Flow에 대한 GDPR 데이터 주체 요청에 응답하는 방법을 알아봅니다.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: KFile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/16/2018
ms.author: keweare
ms.openlocfilehash: b6fdcd33fd657086a5d37919858eceefabd18934
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34563281"
---
# <a name="respond-to-gdpr-data-subject-rights-dsrs-requests"></a>GDPR DSR(데이터 주체 권한) 요청에 대한 응답

이 아티클에서는 유럽 연합의 GDPR(일반 데이터 보호 규정)에 대해 설명하고, MSA(Microsoft 계정)를 사용하여 인증하는 Microsoft Flow 사용자에게 GDPR 준수를 지원하기 위해 수행할 수 있는 단계를 제공합니다.

## <a name="prerequisites"></a>필수 구성 요소

이 아티클의 단계를 수행하려면 [무료 Microsoft Flow 라이선스](https://flow.microsoft.com/pricing/)를 포함한 MSA가 필요합니다.

>[!TIP]
> 또한 GDPR 준수 정보는 [Azure Active Directory 계정](gdpr-dsr-summary.md)을 사용하여 인증하는 사용자에게 지원됩니다.
>
>

## <a name="respond-to-dsrs-for-microsoft-flow-customer-data"></a>Microsoft Flow 고객 데이터에 대한 DSR에 응답

데이터 주체가 해당 개인 데이터에 대한 작업을 수행하도록 컨트롤러에 공식적으로 요청하는 것을 DSR(데이터 주체 권한) 요청이라고 합니다. GDPR은 개인 데이터를 **식별되거나 식별 가능한 자연인에 관련된 모든 데이터**로 정의합니다. GDPR은 사용자(GDPR에서 데이터 주체)에게 고용주, 에이전시 또는 조직(데이터 컨트롤러 또는 컨트롤러)에 의해 수집된 개인 데이터를 관리할 권한을 제공합니다. 이러한 권한은 다음과 같습니다.

* 개인 데이터의 복사본 가져오기
* 개인 데이터에 대한 수정 요청
* 개인 데이터의 처리 제한
* 개인 데이터 삭제
* 다른 컨트롤러에 이동할 수 있도록 전자 형식인 개인 데이터 수신

Microsoft에서는 컨트롤러가 클라우드에 위치한 데이터의 DSR에 응답할 때 개인 데이터를 찾고 이에 대한 조치를 취하도록 돕는 제품, 서비스 및 도구를 제공합니다.

이 가이드에 설명된 프로세스의 개요는 다음과 같습니다.

1. **검색**: 검색 및 검색 도구를 사용하여 DSR 요청의 대상이 될 수 있는 고객 데이터를 쉽게 찾을 수 있습니다. 수집한 문서가 작업을 수행하는 컨트롤러 지침에 맞는지를 결정하는 경우 다음 단계에 설명된 하나 이상의 DSR 작업을 수행할 수 있습니다. [Microsoft 계정에 대한 Microsoft Flow DSR 검색 설명서](gdpr-dsr-discovery-msa.md)에서 자세히 알아봅니다. 또는 요청이 DSR 요청에 응답하기 위한 컨트롤러 지침을 충족하지 않는다고 결정할 수 있습니다.

1. **액세스**: Microsoft 클라우드에 있는 개인 데이터를 검색하고 요청된 경우 데이터 주체에게 제공할 수 있도록 복사본을 만듭니다.

1. **수정**: 개인 데이터를 변경하고 개인 데이터에 대한 다른 요청된 작업을 구현합니다(해당하는 경우).

1. **제한**: 다양한 온라인 서비스에 대한 라이선스를 제거하거나 가능한 경우 원하는 서비스를 꺼서 개인 데이터의 처리를 제한합니다. Microsoft 클라우드에서 데이터를 제거하고 온-프레미스 또는 다른 위치에 보존할 수도 있습니다.

1. **삭제**: Microsoft 클라우드에 있는 개인 데이터를 영구적으로 제거합니다. [Microsoft 계정의 개인 데이터 삭제](gdpr-dsr-delete-msa.md)에 대해 자세히 알아봅니다. [Microsoft 계정 종료](gdpr-dsr-accountclose-msa.md)에 대해 자세히 알아봅니다.

1. **내보내기**: 개인 데이터의 전자 복사본(컴퓨터에서 읽을 수 있는 형식)을 제공합니다. [Microsoft 계정의 개인 데이터 내보내기에 대해 자세히 알아봅니다](gdpr-dsr-export-msa.md).