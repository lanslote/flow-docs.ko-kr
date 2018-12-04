---
title: 코드를 사용하여 비즈니스 프로세스 흐름 작업 | Microsoft Docs
description: 비즈니스 프로세스 흐름을 프로그래밍 방식으로 사용하여 더 효율적이고 간소화된 비즈니스 프로세스를 만드는 방법을 알아봅니다.
ms.custom: ''
ms.date: 07/09/2018
ms.reviewer: ''
ms.service: flow
ms.topic: article
ms.assetid: 67d8cf80-9f77-4804-97a1-cf9f61417e83
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: ae3633047bda556058c8e2ec94e6411e7f277e76
ms.sourcegitcommit: 50ea1cdd763863a2cbc88f9f965bdf9351f1059c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "44691069"
---
# <a name="work-with-business-process-flows-using-code"></a>코드를 사용하여 비즈니스 프로세스 흐름 작업

‘비즈니스 프로세스 흐름’을 사용하면 더 효율적이고 간소화된 영업, 서비스 및 기타 비즈니스 프로세스를 만들 수 있습니다. 엔터티 양식의 맨 위에 특수 컨트롤을 배치하여 비즈니스 프로세스의 시각화를 만듭니다. 사용자에게 완료될 때까지 영업, 마케팅 또는 서비스 프로세스의 다양한 스테이지를 안내합니다. 각 프로세스는 여러 스테이지 및 단계를 지원합니다. 단계를 추가 또는 제거하거나, 스테이지 순서를 변경하거나, 비즈니스 프로세스 흐름에 새 엔터티를 추가할 수 있습니다.  
  
여러 비즈니스 프로세스 흐름 인스턴스가 동일한 엔터티 레코드에서 동시에 실행될 수 있습니다. 사용자는 동시 비즈니스 프로세스 인스턴스 간에 전환하고 프로세스의 현재 스테이지에서 작업을 다시 시작할 수 있습니다. 

이 항목에서는 비즈니스 프로세스 흐름을 프로그래밍 방식으로 사용하는 방법을 설명합니다.

> [!NOTE]
> 비즈니스 프로세스 흐름을 사용하기 위해 코드를 작성할 필요는 없습니다. UI를 사용하여 비즈니스 프로세스 흐름을 만들고 관리하는 방법에 대한 자세한 내용은 [비즈니스 프로세스 흐름 개요](../business-process-flows-overview.md)를 참조하세요.  

<a name="PrereqsBPF"></a>   
## <a name="prerequisites-for-business-process-flow"></a>비즈니스 프로세스 흐름의 필수 구성 요소 

사용자 지정 엔터티 및 업데이트된 UI 양식이 있는 엔터티는 비즈니스 프로세스 흐름에 참여할 수 있습니다. 업데이트된 UI 엔터티의 경우 <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsAIRUpdated> 속성이 `true`로 설정됩니다. 

비즈니스 프로세스 흐름의 엔터티를 사용하도록 설정하려면 <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBusinessProcessEnabled> 속성을 `true`로 설정합니다.

> [!IMPORTANT]
>  비즈니스 프로세스 흐름의 엔터티를 사용하도록 설정하는 것은 단방향 프로세스입니다. 되돌릴 수 없습니다.

   
<a name="DefineBPF"></a>   
## <a name="define-business-process-flow"></a>비즈니스 프로세스 흐름 정의
  
시각적 비즈니스 프로세스 흐름 디자이너를 사용하여 비즈니스 프로세스 흐름을 정의합니다. 추가 정보: [비즈니스 프로세스 흐름 만들기](../create-business-process-flow.md)

기본적으로 비즈니스 프로세스 흐름 레코드는 `Draft` 상태로 만들어집니다.  

비즈니스 프로세스 흐름 정의는 <xref:Microsoft.Dynamics.CRM.workflow> 엔터티에 저장되고 비즈니스 프로세스 흐름의 스테이지 정보는 <xref:Microsoft.Dynamics.CRM.processstage> 엔터티에 저장됩니다.
  
<a name="ActivateBPF"></a>   
## <a name="activate-business-process-flow"></a>비즈니스 프로세스 흐름 활성화  
 프로세스 흐름을 사용하려면 먼저 프로세스 흐름을 활성화해야 합니다. 활성화하려면 `Workflow` 엔터티에 대한 `prvActivateBusinessProcessFlow` 권한이 있어야 합니다. <xref:Microsoft.Xrm.Sdk.Messages.UpdateRequest> 메시지를 사용하여 `Workflow` 엔터티 레코드의 상태를 `Activated`로 설정합니다. 추가 정보: [업데이트를 사용하여 특수화된 작업 수행](/dynamics365/customer-engagement/developer/org-service/perform-specialized-operations-using-update) 

 > [!NOTE]
 > 비즈니스 프로세스 흐름 디자이너를 사용하여 비즈니스 프로세스 흐름을 활성화할 수도 있습니다. 

<a name="BPFEntity"></a>   
## <a name="business-process-flow-entity"></a>비즈니스 프로세스 흐름 엔터티 
 해당 `Workflow` 엔터티 레코드의 상태를 변경하거나 비즈니스 프로세스 흐름 디자이너를 사용하여 비즈니스 프로세스 흐름 정의를 활성화하면, 활성화된 비즈니스 프로세스 흐름 인스턴스를 저장하기 위해 다음 이름의 사용자 지정 엔터티가 자동으로 만들어집니다. “*\<activesolutionprefix>*_*\<uniquename>*”. 여기서 uniquename은 사용자가 지정한 이름에서 파생됩니다.  
  
 예를 들어 “My Custom BPF”를 비즈니스 프로세스 흐름 정의의 이름으로 지정하고 활성 솔루션에 기본 게시자(new)를 사용하는 경우 프로세스 인스턴스를 저장하기 위해 만들어진 사용자 지정 엔터티의 이름은 “new_mycustombpf”가 됩니다.  
  
 비즈니스 프로세스 흐름 정의에 `uniquename` 값을 사용할 수 없는 경우(예: 이전 버전에서 솔루션의 일부로 비즈니스 프로세스 흐름을 가져온 경우) 사용자 지정 엔터티의 기본 이름은 “*\<activesolutionprefix>*\_bpf\_*<GUID_BPF_Definition>*”이 됩니다.  
  
> [!IMPORTANT]
>  샘플 비즈니스 프로세스 흐름 레코드는 시스템 엔터티를 사용하여 해당 비즈니스 프로세스 흐름 인스턴스 레코드를 저장합니다.  
>   
>  그러나 이전에 설명한 대로 사용자가 만드는 새 비즈니스 프로세스 흐름 정의는 사용자 지정 엔터티를 사용하여 해당 인스턴스 레코드를 저장합니다. 

다음 방법을 사용하여 비즈니스 프로세스 흐름 엔터티의 이름을 검색할 수 있습니다.

- **UI 사용**: 사용자 지정 UI를 사용하여 비즈니스 프로세스 흐름 엔터티를 찾아봅니다.

    ![](media/bpf-entity-name.png)
- **웹 API 사용**: 다음 요청을 사용합니다.

    **요청**

    ```
    GET [Organization URI]/api/data/v9.0/workflows?$filter=name eq 'My Custom BPF'&$select=uniquename HTTP/1.1
    ```

    **응답**
    ```
    {  
    "@odata.context":"[Organization URI]/api/data/v9.0/$metadata#workflows(uniquename)",
    "value":[  
         {  
             "@odata.etag":"W/\"1084677\"",
             "uniquename":"new_mycustombpf",
             "workflowid":"2669927e-8ad6-4f95-8a9a-f1008af6956f"
         }
      ]
    }

- **Using the Organization service**: Use the following code sample:

    ```c#
    QueryExpression query = new QueryExpression
    {
        EntityName = "workflow",
        ColumnSet = new ColumnSet("uniquename"),
        Criteria = new FilterExpression
        {
            Conditions =
            {
                new ConditionExpression
                {
                    AttributeName = "name",
                    Operator = ConditionOperator.Equal,
                    Values = { "My Custom BPF" }
                }
            }
        }
    };
    Workflow Bpf = (Workflow)_serviceProxy.RetrieveMultiple(query).Entities[0]; 

> [!NOTE]
> The <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBPFEntity> property is `true` for business process flow entities. You can retrieve all the business process flow entities in your instance by running the following Web API request:
> ```http
> GET [Organization URI]/api/data/v9.0/EntityDefinitions?$select=SchemaName,LogicalName,DisplayName&$filter=IsBPFEntity eq true HTTP/1.1
> ```

<a name="BPFSecurity"></a>   
## Manage security for business process flows

The custom entity that is automatically created on activating a business process flow to store business process flow instances adheres to the standard security model as for any other custom entity in Customer Engagement. This implies that privileges granted on these entities define the runtime permissions for users for business process flows.

The custom business process flow entity has organization scope. The regular create, retrieve, update and delete privileges on this entity define the permission the user would have based on his/her assigned roles. By default, when the business process flow custom entity is created, only **System Administrator** and **System Customizer** security roles are granted access to it, and you must explicitly grant permissions to the new business process flow entity (for example, **My Custom BPF**) for other security roles as required.

![](media/bpf-privileges.png)

<a name="ManageBPF"></a>   
## Create, retrieve, update, and delete business process flow entity records (process instances)  
 The custom entity that is automatically created on activating a business process flow definition stores all the process instances for the business process flow definition. The custom entity supports the standard programmatic creation and management of records (process instances) using Web API and CRM 2011 endpoint.

> [!IMPORTANT]
> Switching to another process instance for an entity record is only supported through UI (client) or programmatically using information available in this section. You can no longer use the `SetProcess` message (<xref href="Microsoft.Dynamics.CRM.SetProcess?text=SetProcess Action" /> or <xref:Microsoft.Crm.Sdk.Messages.SetProcessRequest>) to programmatically switch processes (set another business process flow as the active process instance) for the target entity record. 

 Lets consider the following example where we have a cross-entity business process flow, "My Custom BPF," with 3 stages: S1:Account, S2:Account, and S3:Contact. 

 ![](media/sample-bpf.png)
 
### Retrieve all the records (instances) for a business process flow entity
 If the name of your business process flow entity is "new_mycustombpf", use the following query to retrieve all the records (process instances) for your business process flow entity:  
  
```http
GET [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
```

이때 아무것도 없어서 응답으로 인스턴스를 가져오지 않을 수 있습니다. 이 항목의 뒷부분에서 비즈니스 프로세스 흐름 정의의 인스턴스를 만든 후 이 요청을 실행합니다.

> [!NOTE]
> 비즈니스 프로세스 흐름 엔터티의 이름을 검색하는 방법을 알아보려면 이전 섹션 [비즈니스 프로세스 흐름 엔터티](#business-process-flow-entity)를 참조하세요.
  
### <a name="create-a-business-process-flow-entity-record-process-instance"></a>비즈니스 프로세스 흐름 엔터티 레코드(프로세스 인스턴스) 만들기 

UI를 사용하지 않고 엔터티 레코드의 또 다른 비즈니스 프로세스 흐름으로 전환하려면 비즈니스 프로세스 흐름 엔터티 레코드(프로세스 인스턴스)를 프로그래밍 방식으로 만듭니다. 

비즈니스 프로세스 흐름 엔터티 레코드를 만들려면 다음 값을 지정해야 합니다. 
- `@odata.bind` 주석을 통해 단일 값 탐색 속성을 설정하여 기본 엔터티 레코드에 비즈니스 프로세스 흐름 엔터티 레코드를 연결합니다. 비즈니스 프로세스 흐름 정의의 기본 엔터티 레코드를 가리키는 탐색 속성 이름을 찾으려면 [CSDL $metadata 문서](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document)를 사용합니다. 
- `@odata.bind` 주석을 통해 단일 값 탐색 속성을 설정하여 비즈니스 프로세스 흐름 정의에 지정된 유효한 스테이지에 비즈니스 프로세스 흐름 엔터티 레코드를 연결합니다. 비즈니스 프로세스 흐름 정의의 스테이지 레코드를 가리키는 탐색 속성 이름(일반적으로 `activestageid`)을 찾으려면 [CSDL $metadata 문서](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document)를 사용합니다.

    또한 비즈니스 프로세스 흐름 정의의 ID가 2669927e-8ad6-4f95-8a9a-f1008af6956f인 경우 다음 웹 API 요청을 사용하여 비즈니스 프로세스 흐름 정의의 모든 스테이지 정보를 검색할 수 있습니다.

    **요청**

    ```http
    GET [Organization URI]/api/data/v9.0/processstages?$select=stagename&$filter=processid/workflowid eq 2669927e-8ad6-4f95-8a9a-f1008af6956f HTTP/1.1
    ```

    **응답**

    ```http
    {
        "@odata.context": "[Organization URI]/api/data/v9.0/$metadata#processstages(stagename)",
        "value": [
            {
                "@odata.etag": "W/\"858240\"",
                "stagename": "S1",
                "processstageid": "9a9185f5-b75b-4bbb-9c2b-a6626683b99b"
            },
            {
                "@odata.etag": "W/\"858239\"",
                "stagename": "S3",
                "processstageid": "a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a"
            },
            {
                "@odata.etag": "W/\"858238\"",
                "stagename": "S2",
                "processstageid": "19a11fc0-3398-4214-8522-cb2a97f66e4b"
            }
        ]
    }
    ```

그러고 나서 다음 요청을 사용하여 계정 레코드(ID=a176be9e-9a68-e711-80e7-00155d41e206)의 비즈니스 프로세스 흐름 정의 인스턴스 및 프로세스 인스턴스, S1(ID=9a9185f5-b75b-4bbb-9c2b-a6626683b99b)의 첫 번째 스테이지로 설정된 활성 스테이지를 만듭니다.

**요청**

```http
POST [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
Content-Type: application/json; charset=utf-8 
OData-MaxVersion: 4.0 
OData-Version: 4.0 
Accept: application/json 

{
    "bpf_accountid@odata.bind": "/accounts(a176be9e-9a68-e711-80e7-00155d41e206)",
    "activestageid@odata.bind": "/processstages(9a9185f5-b75b-4bbb-9c2b-a6626683b99b)"    
}
```

**응답**

```http
HTTP/1.1 204 No Content
OData-Version: 4.0
OData-EntityId: [Organization URI]/api/data/v9.0/new_mycustombpfs(cc3f721b-026e-e811-80ff-00155d513100)
```

활성 스테이지가 첫 번째 스테이지가 아닌 ***다른*** 단계로 설정된 비즈니스 프로세스 흐름 정의 인스턴스를 만들려면 요청에 `traversedpath`도 제공해야 합니다. 트래버스된 경로는 비즈니스 프로세스 흐름 인스턴스의 방문한 단계를 나타내는 프로세스 스테이지 ID의 쉼표로 구분된 문자열입니다. 다음 요청은 계정 레코드(ID가 679b2464-71b5-e711-80f5-00155d513100임)의 인스턴스 및 두 번째 스테이지, S2(19a11fc0-3398-4214-8522-cb2a97f66e4b)로 설정된 활성 스테이지를 만듭니다.

```http
POST [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
Content-Type: application/json; charset=utf-8 
OData-MaxVersion: 4.0 
OData-Version: 4.0 
Accept: application/json 

{
    "bpf_accountid@odata.bind": "/accounts(679b2464-71b5-e711-80f5-00155d513100)",
    "activestageid@odata.bind": "/processstages(19a11fc0-3398-4214-8522-cb2a97f66e4b)",
    "traversedpath":"9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b"   
}
```

### <a name="update-a-business-process-flow-entity-record-process-instance"></a>비즈니스 프로세스 흐름 엔터티 레코드(프로세스 인스턴스) 업데이트

프로세스 인스턴스를 업데이트하여 다음 또는 이전 단계로 이동하거나, 프로세스 인스턴스를 중단하거나, 프로세스 인스턴스를 다시 활성화하거나, 프로세스 인스턴스를 완료할 수 있습니다. 

#### <a name="stage-navigation"></a>스테이지 탐색

다른 스테이지로 이동하려면 프로세스 인스턴스 레코드를 업데이트하여 활성 스테이지 ID를 변경하고 이에 따라 트래버스된 경로를 업데이트해야 합니다. 비즈니스 프로세스 흐름 인스턴스를 업데이트하는 동안에는 다음 또는 이전 스테이지로만 이동해야 합니다.

스테이지 탐색을 수행하려면 업데이트할 비즈니스 프로세스 흐름 인스턴스의 ID가 필요합니다. 비즈니스 프로세스 흐름의 모든 인스턴스를 검색하려면 이전의 [비즈니스 프로세스 흐름 엔터티의 모든 레코드(인스턴스) 검색](#retrieve-all-the-records-instances-for-a-business-process-flow-entity)을 참조하세요.

업데이트하려는 프로세스 인스턴스의 ID가 dc2ab599-306d-e811-80ff-00155d513100이면 다음 요청을 사용하여 S1에서 S2로 활성 스테이지를 업데이트합니다.

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1
Content-Type: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0

{
    "activestageid@odata.bind": "/processstages(19a11fc0-3398-4214-8522-cb2a97f66e4b)",
    "traversedpath": "9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b"
}
```

#### <a name="change-the-state-of-a-process-instance-abort-reactivate-or-finish"></a>프로세스 인스턴스의 상태 변경: 중단, 다시 활성화 또는 완료 

프로세스 인스턴스의 상태는 **활성**, **완료** 또는 **중단됨** 중 하나일 수 있습니다. 상태는 프로세스 인스턴스 레코드의 다음 특성에 의해 결정됩니다.

- **statecode**: 프로세스 인스턴스의 상태를 표시합니다.

    |값|레이블|
    |-----|-----|
    |0    |활성|
    |1    |비활성|

- **statuscode**: 프로세스 인스턴스의 상태 정보를 표시합니다.

    |값|레이블|
    |-----|-----|
    |1    |활성|
    |2    |완료|
    |3    |중단됨|

따라서 프로세스 인스턴스를 **중단**하려면 다음 요청을 사용하여 `statecode` 및 `statuscode` 값을 적절하게 설정합니다.

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1   
Content-Type: application/json   
OData-MaxVersion: 4.0   
OData-Version: 4.0 
  
{ 
    "statecode" : "1", 
    "statuscode": "3" 
}
```
 
> [!NOTE]
> 모든 스테이지에서 프로세스 인스턴스를 중단할 수 있습니다.

마찬가지로 프로세스 인스턴스를 다시 활성화하려면 위 코드의 `statecode` 및 `statuscode` 값을 각각 **0** 및 **1**로 바꿉니다.

마지막으로 프로세스 인스턴스 상태를 프로세스 인스턴스의 마지막 스테이지에서만 가능한 **완료**로 설정하려면 위 코드의 `statecode` 및 `statuscode` 값을 각각 **0** 및 **2**로 바꿉니다.

#### <a name="cross-entity-navigation"></a>엔터티 간 탐색

이 예제에서 엔터티 간 탐색의 경우 프로세스 인스턴스의 활성 스테이지를 마지막 스테이지, S3(ID=a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a)으로 설정하고, 이에 따라 트래버스된 경로를 업데이트하고, 비즈니스 프로세스 흐름 정의에 따라 연락처 레코드를 기본 엔터티 레코드로 설정해야 합니다.

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1   
Content-Type: application/json   
OData-MaxVersion: 4.0   
OData-Version: 4.0 
  
{
    "activestageid@odata.bind": "/processstages(a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a)",
    "traversedpath":"9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b,a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a",
    "bpf_contactid@odata.bind": "/contacts(0e3f10b0-da33-e811-80fc-00155d513100)"
}
``` 

### <a name="delete-a-business-process-flow-entity-record-process-instance"></a>비즈니스 프로세스 흐름 엔터티 레코드(프로세스 인스턴스) 삭제

다음 웹 API 요청을 사용합니다.

**요청**

```http
DELETE [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1
```  

**응답**

레코드가 있는 경우 삭제가 성공했음을 나타내기 위해 상태 204가 포함된 정상 응답을 받게 됩니다. 엔터티를 찾을 수 없는 경우 상태 404가 포함된 응답을 받게 됩니다.

## <a name="use-retrieveprocessinstances-and-retrieveactivepath-messages"></a>RetrieveProcessInstances 및 RetrieveActivePath 메시지 사용

`RetrieveProcessInstances` 메시지(<xref href="Microsoft.Dynamics.CRM.RetrieveProcessInstances?text=RetrieveActivePath Function" /> 또는 <xref:Microsoft.Crm.Sdk.Messages.RetrieveProcessInstancesRequest>)를 사용하여 모든 비즈니스 프로세스 정의에서 엔터티 레코드의 모든 비즈니스 프로세스 흐름 인스턴스를 검색합니다. 엔터티에 대해 반환된 비즈니스 프로세스 흐름 인스턴스는 인스턴스의 `modifiedon` 특성에 따라 정렬됩니다. 예를 들어 가장 최근에 수정된 비즈니스 프로세스 흐름 인스턴스는 반환된 컬렉션의 ‘첫 번째’ 레코드입니다. 가장 최근에 수정된 비즈니스 프로세스 흐름 인스턴스는 엔터티 레코드의 UI에서 활성 상태인 인스턴스입니다.  
  
`RetrieveProcessInstances` 메시지 사용의 결과로 엔터티에 대해 반환된 각 비즈니스 프로세스 흐름 인스턴스 레코드는 활성 스테이지 ID를 `processstageid` 특성에 저장합니다. 이 특성을 사용하여 활성 스테이지를 찾은 후 이전 또는 다음 스테이지로 이동할 수 있습니다. 이를 수행하려면 먼저 `RetrieveActivePath` 메시지(<xref href="Microsoft.Dynamics.CRM.RetrieveActivePath?text=RetrieveActivePath Function" /> 또는 <xref:Microsoft.Crm.Sdk.Messages.RetrieveActivePathRequest>)를 사용하여 비즈니스 프로세스 흐름 인스턴스의 활성 경로 및 프로세스 흐름 인스턴스에서 사용할 수 있는 스테이지를 찾아야 합니다.   
  
 비즈니스 프로세스 흐름 인스턴스의 활성 스테이지 및 활성 경로 정보가 있으면 정보를 사용하여 활성 경로에서 이전 또는 다음 단계로 이동할 수 있습니다. 스테이지의 앞으로 탐색은 순서대로 수행되어야 합니다. 즉, 활성 경로에서 다음 스테이지로 앞으로만 이동해야 합니다.   
  
 코드가 이러한 두 메서드의 사용 및 [조직 서비스](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata)를 사용한 스테이지 탐색을 보여 주는 전체 샘플을 보려면 [샘플: 비즈니스 프로세스 흐름 작업](sample-work-business-process-flows.md)을 참조하세요. 

<a name="ApplyBPF"></a>   
## <a name="apply-business-process-flow-while-creating-an-entity-record"></a>엔터티 레코드를 만드는 동안 비즈니스 프로세스 흐름 적용

이 섹션에서는 고객 관계에서 만들어진 새 엔터티 레코드에 비즈니스 프로세스 흐름을 자동으로 적용하기 위한 기본 동작을 설명하고 기본 동작을 재정의하여 새 엔터티 레코드에 선택한 비즈니스 프로세스 흐름을 적용하는 방법을 제공합니다.

기본적으로 여러 비즈니스 프로세스 흐름이 정의되어 있는 엔터티의 경우 시스템은 다음 다단계 논리를 사용하여 새 엔터티 레코드에 비즈니스 프로세스 흐름을 적용합니다.
1. 비즈니스 프로세스 흐름 정의 레코드의 **Workflow.PrimaryEntity** 특성을 기반으로 새 엔터티 레코드에 적용할 수 있는 모든 비즈니스 프로세스 흐름을 식별합니다.
2. 현재 사용자가 액세스할 수 있는 비즈니스 프로세스 흐름 정의를 식별합니다. 비즈니스 프로세스 흐름의 액세스를 결정하고 관리하는 방법에 대한 자세한 내용은 이 항목의 앞부분에 나오는 [비즈니스 프로세스 흐름의 보안 관리](#BPFSecurity)를 참조하세요.<br/>  
3. 시스템의 모든 비즈니스 프로세스 흐름 정의에는 엔터티별 전역 순서가 적용됩니다. 비즈니스 프로세스 흐름의 순서는 **Workflow.ProcessOrder** 특성에 저장됩니다. 엔터티의 비즈니스 프로세스 흐름 정의는 이 순서에 따라 정렬되며 최소 순서 값이 포함된 정의가 선택됩니다.
4. 마지막으로 엔터티 레코드가 비즈니스 앱(앱 모듈)에서 만들어진 경우 새 엔터티 레코드에 자동으로 적용될 비즈니스 프로세스 흐름을 선택하기 위해 필터링 수준이 하나 더 적용됩니다. 앱에서 작업할 때 사용자는 비즈니스 앱에 할당된 보안 역할을 통해 액세스 권한을 가진 관련 엔터티, 비즈니스 프로세스 흐름, 보기 및 양식에만 액세스할 수 있습니다. 
    - 비즈니스 앱에 비즈니스 프로세스 흐름이 없는 경우 비즈니스 프로세스 흐름은 3단계까지 설명된 대로 적용됩니다.
    - 비즈니스 앱에 하나 이상의 비즈니스 프로세스 흐름이 있는 경우에는 앱에 있는 비즈니스 프로세스 흐름만 적용할 수 있습니다. 이 경우 사용자가 비즈니스 앱 컨텍스트 내에서 작업 중이면 3단계의 비즈니스 프로세스 흐름 목록은 앱 모듈 내부에 있는 비즈니스 앱의 일부인 비즈니스 프로세스 흐름으로 추가로 필터링되고 프로세스 순서에 따라 정렬됩니다. 
    - 엔터티용 비즈니스 앱 또는 사용자가 액세스할 수 있는 비즈니스 앱에서 비즈니스 프로세스 흐름을 사용할 수 없는 경우에는 새 엔터티 레코드에 비즈니스 프로세스 흐름이 적용되지 않습니다.

새 엔터티 레코드에 자동으로 적용되는 비즈니스 프로세스 흐름의 기본 논리를 재정의할 수 있습니다. 이를 수행하려면 새 엔터티 레코드를 만드는 동안 엔터티의 **ProcessId** 특성을 다음 값 중 하나로 설정합니다.
- 새 엔터티 레코드의 비즈니스 프로세스 흐름 설정을 건너뛰려면 **Guid.Empty**로 설정합니다. 엔터티 레코드를 대량으로 만들지만 비즈니스 프로세스 흐름을 엔터티 레코드에 적용하지 않으려는 경우 이렇게 설정할 수 있습니다.
- 특정 비즈니스 프로세스 흐름 엔터티(엔터티 참조)로 설정합니다. 이 경우 시스템은 기본 논리 대신 지정된 비즈니스 프로세스 흐름을 적용합니다.

새 엔터티 레코드를 만드는 동안 **ProcessId** 특성 값을 설정하지 않으면 시스템이 앞에서 설명한 대로 기본 논리를 적용합니다.

> [!NOTE]
> 새 엔터티 레코드에 자동으로 적용되는 비즈니스 프로세스 흐름의 기본 논리를 재정의하는 기능은 프로그래밍 방식으로만 지원됩니다. UI를 사용하여 이 작업을 수행할 수 없습니다.

## <a name="legacy-process-related-attributes-in-entities"></a>엔터티의 레거시 프로세스 관련 특성

비즈니스 프로세스 흐름에 사용할 수 있는 엔터티의 레거시 프로세스 관련 특성(예: **ProcessId**, **StageId** 및 **TraversedPath**)은 이미 사용되지 않습니다. 대상 엔터티 레코드의 이러한 레거시 프로세스 관련 특성을 조작하는 경우 비즈니스 프로세스 흐름 상태의 일관성이 보장되지 않고 이는 지원되는 시나리오가 ***아닙니다***. 권장되는 방법은 [비즈니스 프로세스 흐름 엔터티 레코드(프로세스 인스턴스) 만들기, 검색, 업데이트 및 삭제](#create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances) 섹션의 앞부분에서 설명한 대로 비즈니스 프로세스 흐름 엔터티의 특성을 사용하는 것입니다.

유일한 예외는 이전 섹션 [엔터티 레코드를 만드는 동안 비즈니스 프로세스 흐름 적용](#ApplyBPF)에 설명된 대로 엔터티 레코드를 만드는 동안 **ProcessId** 특성을 프로그래밍 방식으로 수정하여 비즈니스 프로세스 흐름의 기본 응용 프로그램을 새 레코드로 재정의하는 경우입니다.

<a name="BKMK_clientSideScript"></a>   
## <a name="client-side-programmability-support-for-business-process-flows"></a>비즈니스 프로세스 흐름의 클라이언트 쪽 프로그래밍 기능 지원  
 양식 스크립트에서 비즈니스 프로세스 흐름을 조작하는 데 사용할 수 있는 클라이언트 쪽 개체가 있습니다. 비즈니스 프로세스 흐름은 프로세스가 레코드에 적용되거나, 스테이지가 변경되거나, 상태가 `Active`, `Finished` 또는 `Aborted`로 변경될 때마다 클라이언트 쪽 이벤트를 트리거합니다. 추가 정보: [formContext.data.process(클라이언트 API 참조)](/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process.md)  
  
<a name="BKMK_MaxSettings"></a>   
## <a name="maximum-number-of-processes-stages-and-steps"></a>최대 프로세스, 스테이지 및 단계 수  
 엔터티당 최대 활성화된 비즈니스 프로세스 흐름 수의 기본값은 10개입니다. `Organization.MaximumActiveBusinessProcessFlowsAllowedPerEntity` 특성을 사용하여 다른 값을 지정할 수 있습니다. 그러나 값이 10보다 크면 프로세스를 전환하거나 할당된 비즈니스 프로세스 흐름이 있는 레코드를 열 때 시스템 성능이 저하될 수 있습니다. 이 문제는 프로세스가 여러 엔터티에 걸쳐 있는 경우 특히 두드러질 수 있습니다.  
  
 다음 설정은 사용자 지정할 수 없습니다.  
  
-   프로세스의 엔터티당 최대 스테이지 수는 30개입니다.  
  
-   각 단계의 최대 단계 수는 30개입니다.  
  
-   프로세스 흐름에 참여할 수 있는 최대 엔터티 수는 5개입니다.  

