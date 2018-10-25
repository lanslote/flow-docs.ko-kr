---
title: 워크플로에서 사용자 지정 작업 호출 | Microsoft Docs
description: 워크플로에서 사용자 지정 작업을 호출하는 방법 알아보기
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 1fd5d39e-3dc8-4d1a-8b4b-ccaa303f4bbb
caps.latest.revision: 12
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 8b2904632f4b3bf097275906d917e686cace67ba
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44688519"
---
# <a name="invoke-custom-actions-from-a-workflow"></a>워크플로에서 사용자 지정 작업 호출

워크플로에는 비즈니스 시나리오를 지원하는 많은 기능이 있습니다. 워크플로 내에서 만들기, 업데이트, 삭제와 같은 레코드의 기본 SDK 작업을 호출하면 상당히 많은 비즈니스 시나리오가 해결됩니다. 그러나 워크플로 내에서 직접 호출되는 사용자 지정 작업의 기능과 워크플로의 기능을 결합하면 코드를 작성하지 않고도 완전히 새로운 범위의 비즈니스 시나리오를 응용 프로그램에 추가할 수 있습니다.  
  
 사용자 지정 작업이 워크플로에서 호출되는 시나리오를 살펴보겠습니다. 특정 영업 기회의 할인이 20%를 초과하면 관리자의 승인을 요청하는 사용자 지정 작업을 호출하겠습니다.  
  
<a name="action"></a>   
## <a name="dynamics-365-customer-engagement-example-create-a-custom-action-using-the-opportunity-entity"></a>Dynamics 365 고객 관계 예제: 영업 기회 엔터티를 사용하여 사용자 지정 작업 만들기
  
1. [솔루션 탐색기](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer)에서 **프로세스**를 선택합니다.  
  
2.  탐색 모음에서 **새로 만들기**를 선택합니다. 프로세스에 이름을 지정하고 **작업** 범주를 선택합니다.  
  
 할인 승인을 요청하기 위해 **승인 프로세스**라는 사용자 지정 작업을 사용하고 있습니다. 여기에 표시된 대로 새 메시지를 만들고 관리자 승인을 위한 요청을 보내기 위해 입력 매개 변수 **SpecialNotes** 및 **메일 보내기** 단계를 추가했습니다.  
  
 ![단계 추가 &#45; 메일 보내기](media/enable-custom-action-approval-proces-sadd-email.png "단계 추가 - 메일 보내기")  
  
 메일 메시지를 구성하려면 **속성 설정**을 선택합니다. 양식이 열리면 **양식 도우미**를 사용하여 스크린샷에 강조 표시된 대로 특별 메모와 기타 정보를 메일에 추가합니다. 특별 메모를 추가하려면 메시지에서 메모를 표시할 위치에 커서를 놓은 다음, **양식 도우미**의 **찾을 대상** 아래 첫 번째 드롭다운 목록에서 **인수**를 선택하고, 두 번째 드롭다운 목록에서 **SpecialNotes**를 선택한 후 **확인**을 선택합니다.  
  
 ![메일 설정](media/enable-custom-action-approval-process-setup-email.png "메일 설정")  
  
 워크플로에서 작업을 호출하려면 먼저 작업을 활성화해야 합니다. 작업을 활성화한 후에는 **속성 보기**를 선택하여 해당 속성을 볼 수 있습니다.  
  
 ![사용자 지정 작업 활성화 &#45; 승인 프로세스](media/enable-custom-action-approval-process-activate-action.png "사용자 지정 작업 활성화 - 승인 프로세스")  
  
<a name="workflow"></a>   
## <a name="invoke-a-custom-action-from-a-workflow"></a>워크플로에서 사용자 지정 작업 호출  
  
1. [솔루션 탐색기](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer)에서 **프로세스**를 선택합니다.   
  
2.  탐색 모음에서 **새로 만들기**를 선택합니다. 프로세스에 이름을 지정하고 **워크플로** 범주를 선택합니다.  
  
 영업 기회의 할인이 20%를 초과할 경우 관리자 승인이 필요할 때마다 **승인 프로세스** 사용자 지정 작업을 호출하는 워크플로를 만들었습니다.  
  
 ![워크플로의 작업 속성 설정](media/enable-custom-action-from-workflow.png "워크플로의 작업 속성 설정")  
  
 **속성 설정**을 선택하여 작업의 입력 속성을 설정할 수 있습니다. 특별 메모에 영업 기회와 관련된 계정의 이름을 추가했습니다. **양식 도우미**의 **찾을 대상** 아래 첫 번째 드롭다운 목록에서 **계정**을 선택하고, 두 번째 드롭다운 목록에서 **계정 이름**을 선택한 후, **확인**을 선택합니다. **대상** 속성이 필요하고 이 속성은 시스템에 의해 채워집니다. **대상** 속성의 **{영업 기회(영업 기회)}** 는 호출하는 워크플로가 실행되고 있는 동일한 영업 기회입니다. 또는 조회를 사용하여 대상 속성의 특정 영업 기회를 선택할 수 있습니다.  
  
 ![ApprovalProcess 작업의 입력 매개 변수 설정](media/enable-customaction-workflow-set-properties.png "ApprovalProcess 작업의 입력 매개 변수 설정")  
  



