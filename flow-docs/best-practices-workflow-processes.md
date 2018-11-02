---
title: PowerApps 워크플로 프로세스의 모범 사례 | Microsoft Docs
description: 워크플로를 사용하는 권장 방법 이해
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
ms.assetid: 34e34c33-003a-494f-858c-3d34aacb308c
caps.latest.revision: 10
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 94c38a54fec91e6a480cd90d0a72f19ca56ae51c
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689528"
---
# <a name="best-practices-for-workflow-processes"></a>워크플로 프로세스의 모범 사례

이 항목에는 워크플로 프로세스를 만들고 관리하기 위한 모범 사례가 포함됩니다.  
  
<a name="BKMK_AvoidInfiniteLoops"></a>   
## <a name="avoid-infinite-loops"></a>무한 루프 방지  
 서버 리소스를 사용하고 성능에 영향을 주는 무한 루프를 시작하는 워크플로의 논리를 만들 수 있습니다. 무한 루프가 발생할 수 있는 일반적인 상황은 특성이 업데이트된 후 워크플로의 논리에서 해당 특성을 업데이트할 때 시작되도록 워크플로를 구성하는 경우입니다. 업데이트 작업은 레코드를 업데이트하는 동일한 워크플로를 트리거하고 되풀이해서 워크플로를 트리거합니다.  
  
 사용자가 만든 워크플로에는 무한 루프를 감지하고 중지하는 논리가 포함됩니다. 워크플로 프로세스가 짧은 기간 동안 특정 레코드에서 특정 횟수 이상 실행되면 다음 오류로 인해 프로세스가 실패합니다. **워크플로 작업을 시작한 워크플로에 무한 루프가 포함되어 이 워크플로 작업이 취소되었습니다. 워크플로 논리를 수정하고 다시 시도하세요.** 횟수 제한은 16회입니다.  
  
<a name="BKMK_UseWorkflowTemplates"></a>   
## <a name="use-workflow-templates"></a>워크플로 템플릿 사용  
 유사한 워크플로가 있고 동일한 패턴을 따르는 워크플로를 추가로 만들 것으로 예상하는 경우 워크플로를 워크플로 템플릿으로 저장합니다. 이 방식으로, 다음에 비슷한 워크플로를 만들어야 할 때 템플릿을 사용하여 워크플로를 만들 수 있고 처음부터 모든 조건과 작업을 입력할 필요가 없습니다.  
  
 **프로세스 만들기** 대화 상자에서 **New process from an existing template (select from list)**(기존 템플릿에서 프로세스 새로 만들기(목록에서 선택))을 선택합니다.  
  
<a name="BKMK_UseChildWorkflows"></a>   
## <a name="use-child-workflows"></a>하위 워크플로 사용  
 다른 워크플로 또는 조건부 분기에서 동일한 논리를 적용하는 경우 해당 논리를 하위 워크플로로 정의하면 각 워크플로 또는 조건부 분기에서 수동으로 해당 워크플로를 복제할 필요가 없습니다. 이렇게 하면 워크플로를 더 쉽게 유지 관리할 수 있습니다. 동일한 논리를 적용할 수 있는 많은 워크플로를 검사하는 대신 하나의 워크플로만 업데이트하면 됩니다.  
  
## <a name="automatically-delete-completed-workflow-jobs"></a>완료된 워크플로 작업 자동으로 삭제
백그라운드(비동기) 워크플로의 경우 워크플로 정의에서 **Automatically delete completed workflow jobs (to save disk space)**(완료된 워크플로 작업을 자동으로 삭제(디스크 공간 절약)) 옵션을 선택하는 것이 좋습니다. 이 상자를 선택하면 시스템이 성공한 실행의 워크플로 로그를 삭제하여 공간을 절약할 수 있습니다. 실패한 워크플로 실행의 로그는 문제 해결을 위해 항상 저장됩니다.  

![워크플로 작업 보존](media/workflow-job-retention.png)

<a name="BKMK_AutoDeleteCompletedWorkflowJobs"></a>   
## <a name="keep-logs-for-workflow-jobs-that-encountered-errors"></a>오류가 발생한 워크플로 작업의 로그 유지  
백그라운드(동기)에서 실행되지 않는 워크플로의 경우 워크플로 정의에서 **Keep logs for workflow jobs that encountered errors**(오류가 발생한 워크플로 작업의 로그 유지) 옵션을 선택하는 것이 좋습니다. 이 옵션을 선택하면 문제 해결을 위해 실패한 워크플로 실행의 로그를 저장할 수 있습니다. 성공한 동기 워크플로 실행의 로그는 공간을 절약하기 위해 항상 삭제됩니다.   

![실패한 워크플로의 로드 유지 옵션](media/keep-logs-for-workflows.png)

## <a name="limit-the-number-of-workflows-that-update-the-same-entity"></a>동일한 엔터티를 업데이트하는 워크플로 수 제한
동일한 엔터티를 업데이트하는 둘 이상의 워크플로를 실행하면 리소스 잠금 문제가 발생할 수 있습니다. 모든 영업 기회 업데이트가 연결된 계정의 업데이트를 트리거하는 여러 워크플로가 실행 중인 경우를 살펴봅니다. 이러한 워크플로의 여러 인스턴스가 실행 중이고 동일한 계정 레코드를 동시에 업데이트하려고 하면 리소스 잠금 문제가 발생할 수 있습니다. 워크플로 실패가 발생하고 **SQL 시간 제한: 리소스 *resource name*의 잠금을 가져올 수 없음**과 같은 오류 메시지가 기록됩니다. 

  
<a name="BKMK_DocumentChangesUsingNotes"></a>   
## <a name="use-notes-to-keep-track-of-changes"></a>메모를 사용하여 변경 내용 추적  
 워크플로를 편집할 때 [메모] 탭을 사용하고 사용자가 수행한 작업과 작업을 수행한 이유를 입력해야 합니다. 이렇게 하면 사용자가 적용한 변경 내용을 다른 사용자가 이해할 수 있습니다.  
  
## <a name="next-steps"></a>다음 단계  
 [워크플로 프로세스 개요](workflow-processes.md)   
 [워크플로 프로세스 구성](configure-workflow-steps.md)   
 [워크플로 프로세스 모니터링 및 관리](monitor-manage-processes.md)
   
