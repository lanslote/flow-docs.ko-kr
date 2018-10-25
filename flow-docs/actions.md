---
title: 작업 사용 | Microsoft Docs
description: 작업을 사용하여 작업 만들기, 업데이트, 삭제, 할당 또는 수행과 같은 작업을 수행할 수 있습니다. 내부적으로 작업은 사용자 지정 메시지를 만듭니다.
ms.custom: ''
ms.date: 08/07/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1475985f-d3c4-429d-beac-cb455965e792
caps.latest.revision: 20
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: aaa1d90368cbf513b46a939e7ea512a66b2c0a14
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44688954"
---
# <a name="use-actions"></a>작업 사용

작업을 사용하면 비즈니스 논리를 작성할 수 있는 다양한 가능성이 열립니다. 작업을 사용하여 작업 만들기, 업데이트, 삭제, 할당 또는 수행과 같은 작업을 수행할 수 있습니다. 내부적으로 작업은 사용자 지정 메시지를 만듭니다. 개발자는 이러한 작업을 “메시지”로 참조합니다. 이러한 각 메시지는 엔터티 레코드에서 수행된 작업을 기반으로 합니다. 프로세스의 목적이 레코드를 만들고, 업데이트한 후, 할당하는 것이면 3개의 개별 단계를 수행해야 합니다. 각 단계는 엔터티 기능으로 정의되는데, 반드시 비즈니스 프로세스일 필요는 없습니다.  
  
작업은 비즈니스에서 수행해야 하는 작업과 일치하는 단일 동사(또는 메시지)를 정의하는 기능을 제공합니다. 이러한 새 메시지는 엔터티로 수행할 수 있는 작업이 아닌 프로세스 또는 동작을 기반으로 합니다. 이러한 메시지는 에스컬레이션, 변환, 예약, 라우팅 또는 승인과 같이 무엇이든 필요한 동사에 해당할 수 있습니다. 이러한 동사를 추가하면 비즈니스 프로세스를 유창하게 정의하는 데 필요한 더 풍부한 어휘를 제공할 수 있습니다. 클라이언트 내에서 작업을 작성할 필요 없이 클라이언트 또는 통합의 이런 더 풍부한 어휘를 적용할 수 있습니다. 이 기능을 사용하면 전체 작업의 성공 또는 실패를 단일 단위로 관리하고 기록할 수 있기 때문에 더 쉽게 성공할 수 있습니다.  
  
<a name="BKMK_ConfigurableMessages"></a>   
## <a name="configurable-messages"></a>구성 가능한 메시지  
 작업이 정의되고 활성화되면 개발자는 플랫폼에서 제공하는 다른 메시지처럼 해당 메시지를 사용할 수 있습니다. 그러나 중요한 차이점은 개발자가 아닌 사용자가 해당 메시지를 사용할 때 수행해야 하는 작업에 변경 내용을 적용할 수 있는 것입니다. 비즈니스 프로세스가 변경될 때 단계를 수정하도록 작업을 구성할 수 있습니다. 프로세스 인수가 변경되지 않으면 해당 메시지를 사용하는 사용자 지정 코드를 변경할 필요가 없습니다.  
  
 워크플로 프로세스 및 플러그 인은 자동화를 정의하기 위한 유사한 기능을 계속 제공합니다. 워크플로 프로세스는 개발자가 아닌 사용자가 변경 내용을 적용하는 기능을 계속 제공합니다. 그러나 차이점은 비즈니스 프로세스가 작성되는 방법과 개발자가 코드를 작성하는 방법에 있습니다. 작업은 플랫폼에서 제공하는 메시지와 동일한 수준에서 작동하는 메시지입니다. 개발자는 작업의 플러그 인을 등록할 수 있습니다.  
  
<a name="BKMK_GlobalMessages"></a>   
## <a name="global-messages"></a>전역 메시지 
 
 앱용 CDS 워크플로 또는 [플러그 인](/powerapps/developer/common-data-service/apply-business-logic-with-code?branch=master#create-a-plug-in)과 달리 작업은 특정 엔터티와 연결할 필요가 없습니다. 단독으로 호출될 수 있는 “전역” 작업을 정의할 수 있습니다.

## <a name="next-steps"></a>다음 단계

[사용자 지정 작업 만들기](create-actions.md)  
  

