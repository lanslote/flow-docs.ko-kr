---
title: 대화를 비즈니스 프로세스 흐름 또는 캔버스 앱으로 바꾸기 | MicrosoftDocs
ms.custom: ''
ms.date: 08/02/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- flow
ms.assetid: 046480e6-f2ff-4c56-9e03-f642c982ff7d
caps.latest.revision: 12
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 87a12345c72fd3dd3e93c1afecd282a688e4d4d1
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44691092"
---
# <a name="replace-dialogs-with-business-process-flows-or-canvas-apps"></a>대화를 비즈니스 프로세스 흐름 또는 캔버스 앱으로 바꾸기

[대화는 더 이상 사용되지 않으며](https://docs.microsoft.com/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated) 비즈니스 프로세스 흐름 또는 캔버스 앱으로 바꿔야 합니다. 이 항목에서는 이러한 옵션의 다양한 기능 및 모델 기반 양식에 포함된 비즈니스 프로세스 흐름 또는 캔버스 앱을 사용하여 기존 대화를 바꿀 수 있는 경우에 대해 설명합니다.

## <a name="feature-capability-comparison"></a>기능 비교

다음 표에는 일단의 대화 기능과 이와 동등한 비즈니스 프로세스 흐름 및 캔버스 앱의 기능이 나와 있습니다.


|대화 기능  | 비즈니스 프로세스 흐름의 기능  | 캔버스 앱의 기능  |
|---------|---------|---------|
|페이지     | 예 <br/> (비즈니스 프로세스 스테이지)    | 예 <br/> (앱 화면)        |
|프롬프트만   |  아니요    |  예 <br/> (레이블)        |
|프롬프트 및 응답     |  예 <br/> (엔터티 특성만)    | 예 <br/> (레이블 및 입력 필드)    |
|입력 인수     |  제한됨 <br/> (비즈니스 프로세스 스테이지의 단계)    | 예 <br/> (쿼리 문자열 매개 변수)     |
|변수   |  아니요     |  예       |
|쿼리 변수    |  아니요     |  예     |
|조건부 분기 논리    |  예     | 예 <br/>  (앱 내의 화면으로 이동)    |
|재사용 <br/> (자식 대화로 시작)   |  아니요     | 예 <br/> (앱 내의 화면으로 이동, 새 창에서 다른 앱 시작)     |
|시작/종료 시 워크플로 실행    |   예      |  아니요 <br/> (대신 흐름 사용)  |
|입력 시 워크플로 실행    | 예    | 아니요 <br/> (대신 흐름 사용)   |
|페이지 전환 시 워크플로 실행   |  예       | 아니요 <br/> (대신 흐름 사용)    |
|URL을 사용하여 시작  |   아니요      |  예     |
|세션 로깅    |  예       |  아니요     |
|SDK 지원   |  예     |  예     |

### <a name="additional-capabilities-with-business-process-flows"></a>비즈니스 프로세스 흐름의 추가 기능
- 프로세스 분석(스테이지에서 사용된 보기, 차트 및 시간)
- 사용자 지정 컨트롤

### <a name="additional-capabilities-with-canvas-apps"></a>캔버스 앱의 추가 기능
- 앱 분석(앱 사용량 및 성능)
- 다중 엔터티 페이지 구성
- 흐름 실행
- 데이터 커넥터(표준 및 사용자 지정)
- 독립 실행형 앱으로 시작
- 구성 가능한 레이아웃

## <a name="choosing-between-a-business-process-flow-or-canvas-app"></a>비즈니스 프로세스 흐름 또는 캔버스 앱 중에서 선택
대화 바꾸기를 선택하는 경우 제공하려는 사용자 환경을 고려해야 합니다. 또한 캔버스 앱을 사용하여 거의 모든 대화를 모델링할 수 있습니다.

비즈니스 프로세스 흐름은 개별 그룹 및 Dynamics 365 앱 컨텍스트 간의 공동 작업이 필요한 매우 중요한 작업 흐름 전반에 대한 지침을 제공하는 프로세스를 모델링하는 대화를 바꾸는 데 가장 적합합니다. 예를 들어 견적 검토와 라우팅이 있습니다. 

또는 캔버스 앱은 잠재 고객 탐색을 위한 호출 스크립트와 같은 규범 작업을 모델링하는 대화를 바꾸거나, 기회 업데이트와 같은 다른 작업에 대한 사용자 환경을 간소화하는 데 사용할 수 있습니다. 이러한 시나리오에서 독립 실행형 캔버스 앱을 사용하는 경우에도 도움이 될 수 있습니다. 

## <a name="dialog-replacement-using-business-process-flow-scenario"></a>비즈니스 프로세스 흐름 시나리오를 사용하여 대화 바꾸기
고객에게 이메일을 보내기 전에 일련의 페이지를 통해 사용자에게 주요 정보를 요청하고, 견적을 생성하고, 검토자에게 이메일을 보내 견적을 수락하거나 거절하도록 하는 이메일이 있다고 가정합니다. 이러한 유형의 프로세스는 비즈니스 프로세스 흐름을 사용하여 더 효과적으로 모델링됩니다. 

대화를 바꾸려면 먼저 프로세스의 주요 스테이지를 식별하는 것으로 시작합니다. 여기에는 모든 제품이 나열되고 할인이 적용되도록 하는 *콘텐츠 준비* 스테이지, 견적을 만들고 형식의 정확성을 검토하는 *견적 생성* 스테이지, 검토와 승인을 위해 견적을 보내는 *기본 검토* 스테이지, 특정 상황에서 견적을 검토하는 *보조 검토* 스테이지, 마지막으로 고객에게 견적을 보내는 *견적 배달* 스테이지가 포함될 수 있습니다.

그런 다음, 사용자가 프로세스에서 따라야 하는 주요 단계를 식별합니다. 예를 들어 *콘텐츠 준비* 스테이지에는 사용자가 견적될 제품을 다시 확인할 수 있는 간단한 참 또는 거짓 단계, 가격 목록을 선택하는 필수 조회 단계 및 다음 스테이지로 넘어가기 전에 할인을 입력하는 숫자 단계가 포함될 수 있습니다. *견적 생성* 스테이지에는 *콘텐츠 준비* 스테이지 및 관련 Dynamics 365 레코드에서 이전에 캡처한 모든 정보를 기반으로 하여 견적을 만드는 [작업 단계](create-business-process-flow.md#add-an-on-demand-action-to-a-business-process-flow)가 있을 수 있습니다. *기본 검토* 및 *보조 검토* 스테이지에는 승인 상태를 캡처하는 데 필요한 단계에 따라 견적 검토를 안내하는 몇 가지 참 또는 거짓 단계가 있을 수 있으며, 승인을 받은 후에만 프로세스를 다음 스테이지로 이동할 수 있습니다. 이 단계에서 권한 있는 검토자만 견적에 대한 승인을 제공할 수 있도록 [필드 수준 보안](/customer-engagement/admin/field-level-security)을 구성합니다.  또한 입력 시 모든 검토자에게 이메일 알림을 보내는 것과 같은 워크플로를 *기본 검토* 및 *보조 검토* 스테이지에 추가할 수 있습니다. 

마지막으로, 프로세스 흐름을 안내하는 조건부 논리에 따라 비즈니스 프로세스 흐름 스테이지 및 단계를 구성합니다. 이 예에서는 *기본 검토* 스테이지 뒤에 [조건부 분기](enhance-business-process-flows-branching.md)를 추가할 수 있습니다. 즉 한 단계에서 두 번째 수준의 검토가 필요한 경우 프로세스의 다음 스테이지는 *보조 검토* 스테이지가 되며, 그렇지 않으면 *견적 배달* 스테이지가 됩니다.

사용자가 이 비즈니스 프로세스 흐름을 사용할 수 있게 하려면 적합한 사용자에게 비즈니스 프로세스 흐름에 대한 권한이 있는지 확인한 후에 해당 흐름을 활성화합니다.

비즈니스 프로세스 흐름을 만드는 방법에 대한 자세한 내용은 [자습서: 프로세스를 표준화하는 비즈니스 프로세스 흐름 만들기](create-business-process-flow.md)를 참조하세요.

## <a name="dialog-replacement-using-canvas-app-scenario"></a>캔버스 앱 시나리오를 사용하여 대화 바꾸기

냉정하게 호출하는 잠재 고객을 통해 영업 담당자를 안내하는 호출 스크립트를 따르는 대화가 있다고 가정합니다. 이 프로세스는 캔버스 앱을 사용하여 쉽게 캡처할 수 있습니다.

데이터를 읽고 써야 하는 데이터 원본에 연결하는 것으로 시작합니다. 이 예에서는 [Dynamics 365 연결](/powerapps/maker/canvas-apps/connections/connection-dynamics-crmonline)이 잠재 고객, 계정 및 연락처 정보에 사용됩니다.

필요한 화면 수를 식별하면서 시작합니다. 이 예에서는 다섯 개의 화면을 사용하도록 결정할 수 있습니다. 
-   화면 1. 목록에서 호출할 잠재 고객을 선택합니다.
-   화면 2. 소개하고, 대화 가능 여부를 확인하고, 나중의 콜백을 예약합니다. 
-   화면 3. BANT(예산, 기관, 요구 사항 및 타임라인)를 결정합니다. 
-   화면 4. 다음 단계를 포착하고 후속 호출을 예약합니다. 
-   화면 5. 호출 종료 시 시간을 내어 준 것에 대해 잠재 고객에게 감사드립니다.

다음으로, 각 화면을 작성합니다. 첫 번째 화면에서 호출해야 하는 잠재 고객의 [갤러리를 작성합니다](/powerapps/maker/canvas-apps/customize-layout-sharepoint). 두 번째 화면에서는 레이블을 사용하여 화면의 제목을 지정하고 호출 스크립트를 제공하는 한편, 라디오 단추와 같은 컨트롤을 사용하여 대화하기에 적합한 시간인지 여부를 캡처합니다. 그렇다면 조건부 논리를 사용하여 단추를 통해 다음 화면으로 이동할 수 있도록 하고, 그렇지 않으면 동일한 화면에 스크립트를 표시하여 고객과의 호출을 다시 예약합니다. 마찬가지로 다음 화면에서 호출 스크립트를 정의합니다.

마지막으로, [화면 간의 이동을 정의합니다](/powerapps/maker/canvas-apps/functions/function-navigate). 이 예에서는 화면을 순차적으로 이동하는 것 외에도 잠재 고객이 대화하는 데 관심이 없는 경우, 사용자가 두 번째 화면에서 마지막 화면(시간을 내어 준 것에 대해 잠재 고객에게 감사 인사를 하는 스크립트의 끝)으로 이동할 수 있도록 합니다.

사용자가 이 앱을 사용할 수 있게 하려면 앱을 게시합니다. 호출 스크립트를 제공하고 빠른 데이터 입력을 지원하는 독립 실행형 앱의 가용성을 통해 이러한 시나리오가 변환될 수 있는 방법을 고려합니다.

이 환경이 Dynamics 365 for Sales에 포함되도록 한다고 가정합니다. 이렇게 하려면 Dynamics 365 for Sales 양식에서 iframe을 만드는 것으로 시작합니다. 그런 다음, PowerApps 메뉴에서 **앱** 섹션으로 이동하고, 방금 게시한 앱을 선택하고, **세부 정보** 탭 아래에 있는 웹 링크를 복사하여 iframe에 대한 URL로 붙여넣습니다. 

여기서 한 단계 더 나아가, 이 앱을 잠재 고객 기본 양식 내에서 바로 사용할 수 있고, 사용자가 앱의 첫 번째 화면에서 잠재 고객을 선택할 필요가 없도록 앱이 잠재 고객의 컨텍스트에 있도록 가정합니다. 관련 정보를 앱에 전달하려면 양식 로드와 같이 특정 이벤트에서 실행되는 JavaScript를 사용하여 잠재 고객 또는 계정 ID와 같은 정보가 포함된 쿼리 문자열을 추가하도록 iframe URL을 수정하기만 하면 됩니다. 다음으로, 앱을 업데이트하여 첫 번째 화면(잠재 고객 선택용)을 제거하고, 그 대신에 [Param 함수](/powerapps/maker/canvas-apps/functions/function-param)를 사용하여 쿼리 문자열을 통해 앱에 전달된 값에 액세스합니다.

## <a name="dialog-replacement-faq"></a>대화 바꾸기 FAQ

캔버스 앱에 대한 종속성이 추적되나요? 
- 캔버스 앱에 대한 종속성은 Dynamics 365 고객 관계의 종속성과 동일한 방식으로 추적됩니다.

명령 모음의 단추를 사용하여 캔버스 앱을 팝업으로 시작할 수 있나요?
- 예. 이렇게 하려면 앞에서 설명한 대로 대상 URL을 앱의 **세부 정보** 섹션에서 가져온 캔버스 앱의 URL로 설정하면 됩니다.

캔버스 앱에서 워크플로를 호출할 수 있나요?
- 이는 지원되지 않습니다. 그 대신 흐름을 사용하는 것이 좋습니다. 자세한 정보: [사용자 입력을 사용하는 단추 흐름 소개](button-flow-with-user-input-tokens.md)

대화를 비즈니스 프로세스 흐름 또는 캔버스 앱으로 자동으로 변환할 수 있나요?
- 대화를 비즈니스 프로세스 흐름 또는 캔버스 앱으로 자동으로 변환하는 방법은 없습니다.


## <a name="see-also"></a>참고 항목
[자습서: 프로세스를 표준화하는 비즈니스 프로세스 흐름 만들기](create-business-process-flow.md) </br>
[PowerApps의 캔버스 앱이란 무엇인가요?](/powerapps/maker/canvas-apps/getting-started)

