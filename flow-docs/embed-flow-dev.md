---
title: "웹 사이트 및 앱과 Microsoft Flow 통합 | Microsoft Docs"
description: "웹 사이트나 앱에 Microsoft Flow 경험을 포함합니다."
services: 
suite: flow
documentationcenter: na
author: bbarath
manager: erikre
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/09/2017
ms.author: barathb
ms.openlocfilehash: 12664286a9e7d88fb5e24607d600b42f95398cee
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2017
---
# <a name="integrate-microsoft-flow-with-websites-and-apps"></a>웹 사이트 및 앱과 Microsoft Flow 통합
Microsoft Flow를 올바르게 앱이나 웹 사이트에 포함하면 사용자가 개인 또는 업무 작업을 간단히 자동화하게 할 수 있습니다.

흐름을 만들려면 **Azure Active Directory**에서 사용자의 **Microsoft 계정** 또는 회사나 학교 계정이 필요합니다. Microsoft Flow는 시스템이 사용하는 모든 ID를 지원하는 화이트라벨 솔루션 등을 지원하지 않습니다(이미 Microsoft 계정 또는 AAD를 사용하지 않는 한).

## <a name="prerequisites"></a>필수 구성 요소
* 서비스를 Microsoft Flow에 연결하는 [사용자 지정 커넥터를 빌드](register-custom-api.md)합니다.
* API를 사용하는 [하나 이상의 템플릿을 만들고 게시합니다](publish-a-template.md).

## <a name="show-templates-for-your-scenarios"></a>시나리오에 대한 템플릿 표시
시작하려면 이 코드를 추가하여 웹 사이트에 직접 흐름 템플릿을 표시합니다.

```
<iframe src="https://flow.microsoft.com/{locale}/widgets/templates/?q={search term}
&pagesize={number of templates}&destination={destination}"></iframe>
```

**참고**: 코드가 페이지에 더 잘 표시되도록 줄 바꿈을 추가했습니다.

| 매개 변수 | 설명 |
| --- | --- |
| 로캘 |템플릿 보기에 대한 4자리 문자와 지역 코드. 예를 들어 `en-us`는 미국 영어를, `de-de`는 독일어를 나타냅니다. |
| 검색어 |보기에 표시하려는 템플릿에 대한 검색어. 예를 들어, `wunderlist`를 검색하면 Wunderlist에 대한 템플릿을 표시합니다. |
| 템플릿 수 |보기에 표시하려는 템플릿의 수 |
| 대상 |사용자가 템플릿을 클릭하면 열리는 페이지. 템플릿에 대한 세부 정보를 표시하려면 `details`를, Microsoft Flow 디자이너를 열려면 `new`를 지정합니다. |
| parameters.{name} |흐름에 전달할 추가 컨텍스트. |

대상 매개 변수가 `new`이면 사용자가 템플릿을 클릭했을 때 Microsoft Flow가 열리고 사용자가 디자이너에서 흐름을 만들 수 있습니다. 앱 안에서의 전체 작업 경험은 다음 섹션을 참조하세요.

### <a name="passing-additional-parameters-to-the-flow"></a>흐름에 추가 매개 변수 전달
사용자가 웹 사이트나 앱에서 특정 컨텍스트에 있는 경우 이 컨텍스트를 흐름에 전달하려 할 수 있습니다. 예를 들어 사용자가 Wunderlist의 특정 목록을 살피는 동안 항목이 목록에 추가되면 알림에 대한 템플릿을 열 수 있습니다. 이 단계에 따라 목록 ID를 매개 변수 형태로 흐름에 전달할 수 있습니다.

1. 게시하기 전에 흐름 템플릿의 매개 변수를 정의합니다. 매개 변수는 `@{parameters('parameter_name')}`같은 형태입니다.
2. Iframe src에서 매개 변수를 전달합니다. 예를 들어 **listName**이라는 매개 변수가 있으면 `&parameters.listName={the name of the list}`를 추가합니다.

### <a name="full-sample"></a>전체 샘플
독일어로 Wunderlist에 대한 상위 4개 템플릿을 표시하고 **myCoolList**로 사용자를 시작하려면:

```
<iframe src="https://flow.microsoft.com/de-de/widgets/templates/?q=wunderlist
&pagesize=4&destination=details&parameters.listName=myCoolList"></iframe>
```

## <a name="embed-the-management-of-flows"></a>흐름 관리 포함
인증된 흐름 SDK를 사용하여 사용자가 웹 사이트나 앱에서 직접 흐름을 만들고 관리할 수 있게 합니다(Microsoft Flow 포털을 탐색하는 대신). 인증된 SDK를 사용하려면 사용자가 Microsoft 계정이나 Azure Active Directory에 로그인해야 합니다.

> [!NOTE]
> 응용 프로그램에서 Microsoft Flow를 사용하는 모든 사용자는 Microsoft Flow 사용자가 됩니다. Microsoft Flow 브랜딩을 숨기는 방법은 없습니다.
> 
> 

### <a name="include-the-javascript-for-the-authenticated-sdk"></a>인증된 SDK에 대한 JavaScript 포함
이 예제에 따라 HTML 코드에 SDK를 포함합니다. SDK를 다운로드 및 축소하여 제품과 함께 패키징할 수도 있습니다.

```
<script src="https://flow.microsoft.com/content/msflowsdk-1.1.js" async defer></script>
```

### <a name="create-a-container-to-contain-the-view"></a>보기를 포함하는 컨테이너 만들기
HTML div 추가:

```
<div id="flowDiv" class="flowContainer"></div>
```

환경에서 적합한 치수로 표시될 수 있게 이 컨테이너의 스타일을 권장합니다.

```
<head>
    <style>
        .flowContainer iframe {
            width: 400px;
            height: 1000px;
            border: none;
            overflow: hidden;
    }
    </style>
</head>
```

너비가 320픽셀 이하이면 frame이 제대로 렌더링하지 못하며 너비가 1200픽셀 이상이면 콘텐츠가 채워지지 않습니다. 모든 높이에서 작동합니다.

### <a name="authentication-against-the-sdk"></a>SDK에 대한 인증
사용자에게 이미 권한이 있는 흐름을 열거하고 템플릿에서 흐름을 만들려면 AAD에서 authToken을 제공합니다.

```
<script>
    window.msFlowSdkLoaded = function() {
        var sdk = new MsFlowSdk({
            hostName:'https:/flow.microsoft.com'
        });
        var widget = sdk.renderWidget('flows', {
            container: 'flowDiv'
            environmentId: '[environmentId]'    // find environment id from browser URL when you 
                                                // click on 'my flows'
                                                //ex: https://flow.microsoft.com/manage/environments/[environmentId]/flows
        });
        widget.callbacks.GET_ACCESS_TOKEN = function(requestParam, widgetDoneCallback)
       {
            var authCallback = function(token) {
                widgetDoneCallback(null, {
                    token: token // Get AAD access token from your backend system
                });
            };
        }
    }
</script>
```

액세스를 갖는 환경 사용자 목록을 반환하는 다음 API를 호출하여 `environmentId`를 찾을 수 있습니다.

```
GET https://management.azure.com/providers/Microsoft.ProcessSimple/environments
?api-version=2016-11-01 
```

모든 환경을 선택할 수 있는 환경 목록으로 JSON 응답을 반환합니다. `properties.isDefault=true` 속성을 선택하여 기본 사용자 환경을 찾을 수 있습니다.

이 예제에서는 `requestParam`이 다음과 같이 정의됩니다.

```
export interface IRpcRequestParam {
    callInfo: IRpcCallInfo,
    data?: any;
}
```

다음으로, `widgetDoneCallback`은 호스트에 토큰이 있을 때 호출해야 하는 콜백 함수입니다. 토큰 획득은 비동기 프로세스일 가능성이 크므로 이 작업이 수행됩니다. 이 함수를 호출하는 경우에 전달되어야 하는 매개 변수는 `(errorResult: any, successResult: any)`입니다. successResult는 콜백 유형에 따라 달라집니다. `GetAccessToken`의 경우 유형은 다음과 같습니다.

```
export interface IGetAccessTokenResult {
    token: string;
}
```
