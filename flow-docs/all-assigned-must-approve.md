---
title: "모든 사용자가 승인해야 하는 승인 흐름 만들기 | Microsoft Docs"
description: "모든 사용자가 승인해야 하거나 한 명의 사용자가 요청을 거부해야 하는 승인 흐름을 만듭니다."
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/27/2018
ms.author: deonhe
ms.openlocfilehash: b7cf57ad343433f50a918e3a09710fbb1e3325de
ms.sourcegitcommit: 79fc1e439640c6329bac884085eb66e71f63ab63
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2018
---
# <a name="create-an-approval-flow-that-requires-everyone-to-approve"></a>모든 사용자가 승인해야 하는 승인 흐름 만들기

이 연습에서는 모든 사용자(할당된 모든 승인자)가 휴가 요청을 승인하도록 동의해야 하는 승인 워크플로를 만드는 방법을 보여줍니다. 하지만 승인자는 전체 요청을 거부할 수 있습니다.

이 유형의 승인 워크플로는 사용자의 관리자와 관리자의 관리자 모두가 휴가 요청을 승인하도록 동의해야 하는 조직에서 유용합니다. 그러나 다른 사용자가 입력하지 않아도 둘 중 하나의 관리자가 요청을 거부할 수 있습니다.

> [!NOTE]
> 이 연습에서는 휴가 승인 시나리오를 강조 표시하는 동안 여러 승인자가 요청을 승인하는 데 필요한 경우에 이 형식의 승인 흐름을 사용할 수 있습니다.
>
>

## <a name="prerequisites"></a>필수 구성 요소

* [Microsoft Flow](https://flow.microsoft.com), Microsoft Office 365 Outlook 및 Microsoft Office 365 사용에 대한 액세스 권한
* SharePoint [목록](https://support.office.com/article/SharePoint-lists-I-An-introduction-f11cd5fe-bc87-4f9e-9bfe-bbd87a22a194)

    이 연습에서는 휴가를 요청하는 데 사용되는 SharePoint 목록을 만들었다고 가정합니다. SharePoint 목록 모양을 설명하는 심층 예제는 [병렬 승인](parallel-modern-approvals.md) 연습을 참조하세요.
* 흐름을 만드는 기본 사항에 익숙해야 합니다.

    [작업, 트리거](multi-step-logic-flow.md#add-another-action) 및 [조건](add-condition.md)을 추가하는 방법을 검토할 수 있습니다. 다음 단계에서는 이러한 작업을 수행하는 방법을 알고 있다고 가정합니다.

> [!NOTE]
> 이 연습에서 SharePoint 및 Office 365 Outlook을 사용하는 동안 Zendesk, Salesforce, Gmail 또는 Microsoft Flow에서 지원하는 [200개 이상의 서비스](https://flow.microsoft.com/connectors/)와 같은 다른 서비스를 사용할 수 있습니다.
>
>

## <a name="create-the-flow"></a>흐름 만들기

> [!NOTE]
> SharePoint 또는 Office 365에 대한 연결을 이전에 만들지 않은 경우 로그인하라는 메시지가 나타나면 지침을 따릅니다.
>
>

이 연습에서는 토큰을 사용합니다. 토큰의 목록을 표시하려면 입력 컨트롤을 누르거나 클릭하고 열린 **동적 콘텐츠** 목록에서 토큰을 검색합니다.

[Microsoft Flow](https://flow.microsoft.com)에 로그인하고 다음 단계를 수행하여 흐름을 만듭니다.

1. 화면의 오른쪽 위에서 **내 흐름** > **빈 항목에서 만들기**를 선택합니다.
1. **SharePoint - 항목을 만들거나 수정하는 경우** 트리거를 추가합니다.
1. 휴가 요청 목록을 호스트하는 SharePoint 사이트의 **사이트 주소**를 입력한 다음, **이름 나열** 목록을 선택합니다.
1. **Office 365 사용자 - 관리자 가져오기 V2** 작업을 추가하고, **사용자(UPN)** 상자를 선택한 다음, **이메일에서 만듬** 토큰을 여기에 추가합니다.

    **전자 메일에서 만듬** 토큰은 **동적 콘텐츠** 목록의 **항목을 만들거나 수정하는 경우** 범주 아래에 위치합니다. 이 토큰은 동적으로 SharePoint에서 항목을 만든 사용자의 관리자에게 데이터에 대한 액세스 권한을 제공합니다.

1. 다른 **Office 365 사용자 - 관리자 가져오기 V2** 작업을 추가한 다음, **이메일** 토큰을 **사용자(UPN)** 상자에 추가합니다.

    **이메일** 토큰은 **동적 콘텐츠** 목록의 **관리자 가져오기 V2 2** 범주 아래에 위치합니다. 이 토큰은 동적으로 관리자의 관리자에게 이메일 주소에 대한 액세스 권한을 제공합니다.

    **관리자 가져오기 V2 2** 카드의 이름을 "수준 관리자 건너뛰기"와 같이 변경할 수 있습니다.
1. **승인 시작** 작업을 추가하고 **승인 유형** 목록에서 **할당된 목록의 모든 사용자**를 선택합니다.

   > [!IMPORTANT]
   > 승인자가 거부하는 경우 승인 요청은 모든 승인자에 대해 거부된 것으로 간주됩니다.
   >
   >
1. 다음 표를 가이드로 사용하여 **승인 시작** 카드를 완료합니다.

   | 필드 | 설명 |
   | --- | --- |
   |  승인 유형 |**할당된 목록의 모든 사용자**를 사용하여 승인자 중 하나가 요청을 승인하거나 거부할 수 있는지를 나타냅니다. </p>**할당된 목록의 모든 사용자**를 사용하여 모든 사용자가 동의한 경우에만 요청이 승인되고 한 사람이 거부한 경우 요청이 거부된다는 점을 나타냅니다. |
   |  제목 |승인 요청의 제목입니다. |
   |  할당 대상 |승인자의 전자 메일 주소입니다. |
   |  세부 정보 |**할당 대상** 필드에서 나열된 승인자에게 전송하려는 추가 정보입니다. |
   |  항목 링크 |승인 항목에 대한 URL입니다. 이 예제에는 SharePoint에 있는 항목에 대한 링크가 있습니다. |
   |  항목 링크 설명 |**항목 링크**에 대한 텍스트 설명입니다. |

   > [!TIP]
   > **승인 시작** 작업은 **응답** 및 **응답 요약**을 비롯한 여러 토큰을 제공합니다. 흐름에서 해당 토큰을 사용하여 승인 요청 흐름을 실행한 결과를 다양하게 보고합니다.
   >
   >

    **승인 시작** 카드는 승인자에게 전송된 승인 요청의 템플릿입니다. 조직에 유용한 방식으로 구성합니다. 예를 들면 다음과 같습니다.

    ![승인 시작](media/all-assigned-must-approve/start-an-approval-card.png)

1. **Office 365 Outlook - 전자 메일 보내기** 작업을 추가한 후 요청의 결과가 포함된 전자 메일을 보내도록 구성합니다.

    **전자 메일 보내기** 카드의 모양을 보여주는 예제는 다음과 같습니다.

    ![전자 메일 보내기](media/all-assigned-must-approve/send-an-email-card.png)

> [!NOTE]
> **승인 시작** 작업 뒤에 오는 모든 작업은 **승인 시작** 카드의 **승인 유형** 목록에서 선택에 따라 실행됩니다. 다음 표에서 선택에 따른 동작을 보여줍니다.
>
>

| 승인 유형 | 동작 |
| --- | --- |
| 할당된 목록의 모든 사용자 |승인자 중 하나가 결정한 후에 **승인 시작** 작업 뒤에 오는 작업을 실행합니다. |
| 할당된 목록의 모든 사용자 |승인자가 요청을 거절하거나 모든 승인자가 승인한 후에 **승인 시작** 작업 뒤에 오는 작업을 실행합니다. |

화면 맨 위에 있는 **흐름 이름** 상자에서 흐름에 이름을 입력한 후 **흐름 만들기**를 선택하여 저장합니다.

축하합니다. 흐름이 완료되었습니다. 제대로 따라 했다면 흐름은 이 이미지와 유사합니다.

![전체 흐름 이미지](media/all-assigned-must-approve/overall-flow.png)

이제 SharePoint 목록에 항목이 추가될 때마다 또는 항목이 변경되는 경우 흐름은 승인 요청을 트리거하고 **승인 시작** 카드의 **할당 대상** 상자에 나열된 모든 승인자에게 전송합니다. 흐름은 Microsoft Flow 모바일 앱 및 전자 메일을 통해 승인 요청을 보냅니다. SharePoint에서 항목을 만드는 사용자는 결과를 요약하는 전자 메일을 가져오고 요청을 승인했는지 아니면 거부했는지를 명확하게 나타냅니다.

각 승인자에게 전송된 승인 요청의 예제는 다음과 같습니다.

![승인 요청](media/all-assigned-must-approve/approval-request.png)

흐름을 실행한 후 응답 및 응답 요약의 예제는 다음과 같습니다.

![응답 토큰](media/all-assigned-must-approve/response-output.png)

## <a name="learn-more-about-approvals"></a>승인에 대한 자세한 정보

* [단일 승인자 최신 승인](modern-approvals.md)
* [순차적 최신 승인](sequential-modern-approvals.md)
* [병렬 최신 승인](parallel-modern-approvals.md)
* [승인 및 Microsoft Common Data Service](common-data-model-approve.md)
* [실행 중인 요청 승인](mobile-approvals.md)
