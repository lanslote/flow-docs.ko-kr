---
title: PowerApps에서 워크플로 스테이지 및 단계 구성 | Microsoft Docs
description: 워크플로 단계를 구성하는 방법 알아보기
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: Mattp123
ms.assetid: 0b47dfd5-76db-464f-90c0-c64a0173dcdd
caps.latest.revision: 18
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 8e34f8ef8847ab08e14c91ee6d7871697b0275ce
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690448"
---
# <a name="configure-workflow-stages-and-steps"></a>워크플로 스테이지 및 단계 구성

워크플로를 디자인할 때 수행할 논리를 스테이지 및 단계에 포함할 수 있습니다.  
  
 **스테이지**  
 스테이지는 워크플로 논리를 더 쉽게 읽을 수 있게 하며, 워크플로 논리를 설명합니다. 그러나 스테이지는 워크플로의 논리 또는 동작에 영향을 주지 않습니다. 프로세스에 스테이지가 있는 경우 프로세스 내의 모든 단계는 스테이지와 함께 포함되어야 합니다.  
  
 **단계**  
 단계는 워크플로 내의 비즈니스 논리 단위입니다. 단계에는 조건, 작업, 기타 단계 또는 이러한 요소의 조합이 포함될 수 있습니다.  
  
<a name="BKMK_ActionsWorkflowProcessesCanPerform"></a>  
 
## <a name="actions-that-workflow-processes-can-perform"></a>워크플로 프로세스가 수행할 수 있는 작업  

 워크플로 프로세스는 다음 표에 나열된 작업을 수행할 수 있습니다.  
  
|작업|설명|  
|------------|-----------------|  
|**레코드 만들기**|엔터티의 새 레코드를 만들고 특성에 선택한 값을 할당합니다.|  
|**레코드 업데이트**|워크플로가 실행 중인 레코드, N:1 관계로 해당 레코드에 연결된 레코드 또는 이전 단계에서 만든 레코드를 업데이트할 수 있습니다.|  
|**레코드 할당**|워크플로가 실행 중인 레코드, N:1 관계로 해당 레코드에 연결된 레코드 또는 이전 단계에서 만든 레코드를 할당할 수 있습니다.|  
|**메일 보내기**|메일을 보냅니다. 새 메일 메시지를 만들거나 워크플로가 실행 중인 레코드의 엔터티, 해당 엔터티와 N:1 관계가 있는 엔터티 또는 이전 단계에서 만든 레코드의 엔터티에 대해 구성된 메일 템플릿을 사용하도록 선택할 수 있습니다.|  
|**하위 워크플로 시작**|하위 워크플로로 구성된 워크플로 프로세스를 시작합니다.|  
|**상태 변경**|프로세스가 실행 중인 레코드, N:1 관계로 해당 레코드에 연결된 레코드 또는 이전 단계에서 만든 레코드의 상태를 변경합니다.|  
|**워크플로 중지**|현재 워크플로를 중지합니다. **성공** 또는 **취소됨** 상태를 설정하고 상태 메시지를 지정할 수 있습니다.<br /><br /> 이벤트에 실시간 워크플로가 구성된 경우 취소됨 상태의 워크플로를 중지하면 이벤트 작업이 완료되지 않습니다. 자세한 내용은 [실시간 워크플로 사용](configure-workflow-steps.md#BKMK_SynchronousWorkflows)을 참조하세요.|  
|**사용자 지정 단계**|개발자는 작업을 정의하는 사용자 지정 워크플로 단계를 만들 수 있습니다. 기본적으로 사용 가능한 사용자 지정 단계는 없습니다.|  
  
### <a name="setting-record-values"></a>레코드 값 설정  

 레코드를 만들 때 레코드의 값을 설정할 수 있습니다. 레코드를 업데이트할 때 값을 설정, 추가, 증분, 감소, 증대하거나 지울 수 있습니다.  
  
 **속성 설정**을 선택하면 엔터티의 기본 양식을 표시하는 대화 상자가 열립니다.  
  
 대화 상자 아래쪽에서 양식에 없는 추가 필드 목록을 볼 수 있습니다.  
  
 필드의 경우 사용자가 정적 값을 설정할 수 있고 해당 값은 워크플로에서 설정됩니다.  
  
 대화 상자 오른쪽에 있는 **양식 도우미**는 현재 레코드의 컨텍스트에서 동적 값을 설정하거나 추가하는 기능을 제공합니다. 여기에는 엔터티의 N:1(다대일) 관계에서 액세스할 수 있는 관련 레코드 값이 포함됩니다.  
  
 **양식 도우미**에서 사용 가능한 옵션은 양식에서 선택한 필드에 따라 다릅니다. 동적 값을 설정하면 동적 데이터가 포함될 위치를 보여 주는 ‘동적 필드’라는 노란색 자리 표시자가 표시됩니다. 값을 제거하려면 동적 필드를 선택하고 삭제합니다. 텍스트 필드의 경우 정적 및 동적 데이터의 조합을 사용할 수 있습니다.  
  
 동적 값을 사용하면 필드 또는 관련 엔터티에 설정할 값이 있는지 확실히 알 수 없습니다. 실제로 많은 필드를 설정하여 값을 설정해 보고 녹색 화살표를 사용하여 순서대로 정렬할 수 있습니다. 첫 번째 필드에 데이터가 없는 경우 두 번째 필드가 시도되는 방식으로 진행됩니다. 모든 필드에 데이터가 없는 경우에는 사용할 기본값을 지정할 수 있습니다.  
  
<a name="BKMK_SettingConditionsForWorkflowActions"></a>   

## <a name="setting-conditions-for-workflow-actions"></a>워크플로 작업의 조건 설정  

 적용할 작업은 조건에 따라 달라집니다. 워크플로 프로세스는 원하는 결과를 얻기 위해 조건을 설정하고 분기 논리를 만드는 여러 가지 방법을 제공합니다. 워크플로 프로세스가 실행 중인 대상 레코드의 값, N:1 관계로 해당 레코드에 연결된 레코드 또는 프로세스 자체 내의 값을 확인할 수 있습니다.  
  
|조건 형식|설명|  
|--------------------|-----------------|  
|**검사 조건**|논리 “if-\<조건> then” 문입니다.<br /><br /> 워크플로가 실행 중인 레코드의 현재 값, N:1 관계로 해당 레코드에 연결된 레코드 또는 이전 단계에서 만든 레코드를 확인할 수 있습니다. 이러한 값을 기준으로 조건이 true인 경우 수행할 추가 단계를 정의할 수 있습니다.<br /><br /> “if-\<조건> then” 문에서 연산자 **같음**, **같지 않음**, **데이터 포함**, **데이터를 포함하지 않음**, **다음에 속함** 및 **다음에 속하지 않음**을 사용할 수 있습니다. **참고:** **다음에 속함** 및 **다음에 속하지 않음**은 계층 구조 연산자입니다. 계층 구조 관계가 정의된 엔터티에서만 사용할 수 있습니다. 계층 구조 관계가 정의되지 않은 엔터티에서 이러한 연산자를 사용하면 다음 오류 메시지가 표시됩니다. “계층 구조 관계가 정의되지 않은 엔터티에 계층 구조 연산자를 사용하고 있습니다. 엔터티를 계층 구조로 설정하거나(관계를 계층 구조로 표시) 다른 연산자를 사용합니다.” 계층 구조 관계에 대한 자세한 내용은 [계층 구조 관련 데이터 정의 및 쿼리](/powerapps/maker/common-data-service/define-query-hierarchical-data)를 참조하세요. 표 다음에 나오는 스크린샷은 **다음에 속함** 및 **다음에 속하지 않음** 계층 구조 연산자를 사용하는 워크플로 프로세스 정의의 예제입니다.|  
|**조건부 분기**|논리 “else-if-then” 문입니다. 편집기에서는 “Otherwise, if \<조건> then:” 텍스트를 사용합니다.<br /><br /> 이전에 정의한 검사 조건을 선택하고, 조건부 분기를 추가하여 검사 조건이 false를 반환할 경우 수행할 추가 단계를 정의할 수 있습니다.|  
|**기본 작업**|논리 “else” 문입니다. 편집기에서는 “Otherwise:” 텍스트를 사용합니다.<br /><br /> 이전에 정의한 검사 조건, 조건부 분기, 대기 조건 또는 병렬 대기 분기를 선택하고, 기본 작업을 사용하여 조건 또는 분기 요소에 정의된 기준과 일치하지 않는 모든 경우에 대한 단계를 정의할 수 있습니다.|  
|**대기 조건**|조건에 따라 정의된 기준이 충족될 때까지 백그라운드 워크플로를 일시 중지할 수 있습니다. 대기 조건의 기준이 충족되면 워크플로가 자동으로 다시 시작됩니다.<br /><br /> 실시간 워크플로는 대기 조건을 사용할 수 없습니다.|  
|**병렬 대기 분기**|초기 기준이 충족되는 경우에만 수행되는 해당 추가 단계 집합이 있는 백그라운드 워크플로의 대체 대기 조건을 정의합니다. 병렬 대기 분기를 사용하여 워크플로 논리에 시간 제한을 만들 수 있습니다. 병렬 대기 분기는 대기 조건에 정의된 기준이 충족될 때까지 워크플로가 무기한 대기하는 것을 방지하는 데 도움이 됩니다.|  
|**사용자 지정 단계**|개발자는 조건을 정의하는 사용자 지정 워크플로 단계를 만들 수 있습니다. 기본적으로 사용 가능한 사용자 지정 단계는 없습니다.|  
  
 다음 스크린샷에는 **다음에 속함** 및 **다음에 속하지 않음** 계층 구조 연산자를 사용하는 워크플로 프로세스 정의의 예제가 있습니다. 이 예제에서는 두 개의 계정 그룹에 두 개의 서로 다른 할인을 적용합니다. **단계 추가**에서 **검사 조건**을 선택하여 **다음에 속함** 또는 **다음에 속하지 않음** 연산자를 포함하는 **if-then** 조건을 지정했습니다. 첫 번째 **if-then** 조건은 Alpine Ski House 계정**에 속하는(Under)** 모든 계정에 적용됩니다. 이러한 계정은 구매한 상품 및 서비스에 10% 할인을 받습니다. 두 번째 **if-then** 조건은 Alpine Ski House 계정**에 속하지 않는(Not Under)** 모든 계정에 적용되고 해당 계정은 5% 할인을 받습니다. 그런 다음, **레코드 업데이트**를 선택하여 조건에 따라 수행할 작업을 정의했습니다.  
  
 ![다음에 속함&#47;다음에 속하지 않음 연산자가 있는 워크플로 프로세스](media/wfp-under-not-under.PNG "다음에 속함/다음에 속하지 않음 연산자가 있는 워크플로 프로세스")  
  
<a name="BKMK_SynchronousWorkflows"></a>   

## <a name="using-real-time-workflows"></a>실시간 워크플로 사용  

 실시간 워크플로를 구성할 수 있지만 주의해서 사용해야 합니다. 백그라운드 워크플로를 사용하면 서버의 리소스를 사용할 수 있을 때 시스템이 해당 워크플로를 적용하므로 일반적으로 백그라운드 워크플로를 사용하는 것이 좋습니다. 이를 통해 서버에서 수행해야 하는 작업이 원활해지고 시스템을 사용하는 모든 사용자를 위한 최상의 성능을 유지할 수 있습니다. 단점은 백그라운드 워크플로에서 정의한 작업이 즉각적이지 않다는 것입니다. 적용될 시기를 예측할 수 없지만 일반적으로 몇 분이 걸립니다. 대부분 비즈니스 프로세스 자동화의 경우 시스템을 사용하는 사용자가 프로세스가 실행 중인 의식적으로 알고 있을 필요가 없으므로 사용하는 것이 좋습니다.  
  
 비즈니스 프로세스에서 사용자가 프로세스의 결과를 즉시 확인해야 하거나 작업을 취소하는 기능이 필요한 경우 실시간 워크플로를 사용합니다. 예를 들어 처음 저장할 때 레코드의 특정 기본값을 설정하거나 일부 레코드가 삭제되지 않도록 할 수 있습니다.  
  
### <a name="converting-between-real-time-and-background-workflows"></a>실시간 및 백그라운드 워크플로 간 변환  

 도구 모음에서 **백그라운드 워크플로로 변환**을 선택하여 실시간 워크플로를 백그라운드 워크플로로 변경할 수 있습니다.  
  
 도구 모음에서 **실시간 워크플로로 변환**을 선택하여 백그라운드 워크플로를 실시간 워크플로로 변경할 수 있습니다. 백그라운드 워크플로가 대기 조건을 사용하는 경우에는 해당 워크플로가 유효하지 않게 되고 대기 조건을 제거할 때까지 워크플로를 활성화할 수 없습니다.  
  
### <a name="initiating-real-time-workflows-before-or-after-status-changes"></a>상태 변경 이전 또는 이후 실시간 워크플로 시작  

 실시간 워크플로에 대한 **자동 프로세스 옵션**을 구성하면 상태 변경 이벤트의 **시작 시기** 옵션을 통해 상태 변경 시기로 **이후** 또는 **이전**을 선택할 수 있습니다. 기본 옵션은 **이후**입니다.  
  
 **이전**을 선택하면 상태를 변경하는 데이터가 저장되기 전에 워크플로의 논리가 적용됩니다. 이 옵션을 선택하면 작업 후 다른 논리가 적용되기 전에 값을 확인하고 추가 논리 수행을 방지할 수 있습니다. 예를 들어 플러그 인 또는 사용자 지정 워크플로 작업에 다른 시스템에서 작업을 시작할 수 있는 추가 논리가 있을 수 있습니다. 추가 처리를 중지하면 외부 시스템이 영향을 받는 경우를 방지할 수 있습니다. 이 이벤트 전에 실시간 워크플로를 적용하면 데이터를 저장했을 수 있는 다른 워크플로 또는 플러그 인 작업이 작업 취소 시 “롤백”될 필요가 없습니다.  
  
### <a name="using-the-stop-workflow-action-with-real-time-workflows"></a>실시간 워크플로와 함께 워크플로 중지 작업 사용  

 워크플로에서 **워크플로 중지** 작업을 적용하는 경우에는 상태 조건을 **성공** 또는 **취소됨**으로 지정할 수 있습니다. 상태를 취소됨으로 설정하면 작업이 수행되지 않습니다. 작업 중치 상태 메시지의 텍스트를 포함하는, 제목이 **비즈니스 프로세스 오류**인 오류 메시지가 사용자에게 표시됩니다.  
  
## <a name="next-steps"></a>다음 단계  
 [프로세스를 통해 사용자 지정 비즈니스 논리 만들기](guide-staff-through-common-tasks-processes.md)   
 [워크플로 프로세스 개요](workflow-processes.md)   
 [워크플로 프로세스 모니터링 및 관리](monitor-manage-processes.md)   
 [워크플로 프로세스의 모범 사례](best-practices-workflow-processes.md)
