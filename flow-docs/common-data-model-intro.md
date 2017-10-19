---
title: Common Data Service | Microsoft Docs
description: "Common Data Service로 데이터를 가져오거나, 내보내거나, 승인을 구성하는 흐름을 만듭니다."
services: 
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/22/2016
ms.author: stepsic
ms.openlocfilehash: a63ccacb1e6d9bd63d5a11a8db6ea01a9fc37333
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2017
---
# <a name="create-a-flow-that-uses-the-common-data-service"></a>Common Data Service를 사용하는 흐름 만들기
[Common Data Service](https://powerapps.microsoft.com/tutorials/data-platform-intro/)를 사용하는 흐름을 만들어 비즈니스 데이터의 통합 보기를 통해 운영 효율성을 증대합니다. 조직 내에 잘 구성된 표준 비즈니스 엔티티(예: 영업, 구매, 고객 서비스, 생산성 등)로 구성된 이 안전한 비즈니스 데이터베이스를 배치합니다. Microsoft Excel 및 Salesforce 등과 같은 외부 데이터 원본에서 여러 이점을 제공하는 하나 이상의 [사용자 지정 엔터티](https://powerapps.microsoft.com/tutorials/data-platform-create-entity/)에 조직 데이터를 저장합니다.

예를 들어, Microsoft Flow 내에서 Common Data Service를 활용하는 주요 방법은 다음과 같습니다.

* 데이터를 내보내거나, 가져오거나, 데이터를 기반으로 조치(예: 알림 보내기)를 취하기 위한 흐름을 만듭니다. 이 방법은 전체 동기화 서비스가 아니라, 단순히 데이터를 엔터티별로 이동하기 위한 것입니다.
  
    자세한 단계는 이 토픽의 뒷부분에 나오는 절차를 참조하세요.
* [전자 메일을 통해 승인 루프를 만드는](wait-for-approvals.md) 대신 엔터티에 승인 상태를 저장하는 흐름을 만들고, 사용자가 항목을 승인 또는 거부할 수 있는 사용자 지정 앱을 구성합니다.
  
    자세한 내용은 [Common Data Service로 승인 루프 작성](common-data-model-approve.md)을 참조하세요.

**필수 구성 요소**

* [Microsoft Flow](https://flow.microsoft.com)와 [PowerApps](https://web.powerapps.com)에 가입합니다.
  
    문제가 있는 경우 [Microsoft Flow](sign-up-sign-in.md) 및 [PowerApps](https://powerapps.microsoft.com/en-us/tutorials/signup-for-powerapps/)가 귀하 및 귀하의 조직이 가입을 차단하지 않은 계정 유형을 지원하는지 여부를 확인합니다.
* 이전에 Common Data Service를 사용하지 않은 경우 [powerapps.com](https://web.powerapps.com/#/entities)에서 **엔터티** 탭을 열고 **내 데이터베이스 만들기**를 클릭합니다.

## <a name="sign-in-to-your-environment"></a>사용자 환경에 로그인
1. [Microsoft Flow 포털](https://flow.microsoft.com)을 연 다음 오른쪽 위 모서리에서 **로그인**을 클릭하거나 누릅니다.
   
    **참고**: **로그인** 단추를 표시하려면 왼쪽 위 메뉴를 열어야 할 수 있습니다.
   
    ![로그인](./media/common-data-model-intro/signin-flow.png)
2. 오른쪽 위 메뉴에서 powerapps.com의 데이터베이스를 만든 환경을 선택합니다.
   
    **참고**: 동일한 환경을 선택하지 않을 경우 엔터티가 표시되지 않습니다.
   
    ![환경 선택](./media/common-data-model-intro/select-environment.png)

## <a name="open-a-template"></a>템플릿 열기
1. 화면 위쪽의 **템플릿 Search** 상자에서 **공통**을 입력한 다음 Enter를 누릅니다.
   
    ![템플릿 검색](./media/common-data-model-intro/template-search.png)
2. 템플릿 목록에서 원하는 엔터티(또는 *개체*)로 원본의 데이터를 가져오려는 템플릿을 클릭하거나 누릅니다.
   
    예를 들어, Dynamics 365의 연락처 정보를 Common Data Service로 복사하는 템플릿을 클릭하거나 누릅니다.
   
    ![템플릿 선택](./media/common-data-model-intro/choose-template.png)
3. **이 템플릿 사용**을 클릭하거나 누릅니다.
   
    ![템플릿 사용](./media/common-data-model-intro/use-template.png)
4. 이미 Microsoft Flow에서 Dynamics 365로의 연결을 만든 경우 **로그인**을 클릭하거나 누른 다음 메시지가 표시되면 자격 증명을 입력합니다.
   
    ![Dynamics 365에 로그인](./media/common-data-model-intro/dynamics-signin.png)
5. **계속**을 클릭하거나 누릅니다.
   
    ![계정 확인](./media/common-data-model-intro/confirm-accounts.png)

## <a name="build-your-flow"></a>흐름 작성
1. 첫 번째 카드에서는 흐름을 트리거할 이벤트를 지정합니다.
   
    예를 들어, Dynamics 365의 인스턴스에서 새 연락처를 Common Data Service로 복사하는 흐름을 작성합니다. **레코드를 만들 때** 아래에서 아래쪽 화살표를 클릭하거나 눌러 인스턴스를 지정한 다음 나타나는 목록에서 옵션을 클릭하거나 누릅니다.
   
    ![Dynamics 365의 인스턴스 지정](./media/common-data-model-intro/specify-instance.png)
2. (선택 사항) 화면 위쪽 근처에서 만드는 흐름에 대해 다른 이름을 지정합니다.
   
    **참고**: 브라우저 창을 최대화하지 않은 경우 UI가 약간 다르게 보일 수 있습니다.
   
    ![흐름 이름 지정](./media/common-data-model-intro/name-flow.png)
3. **흐름 만들기**를 클릭하거나 누릅니다.
   
    **참고**: 브라우저 창을 최대화하지 않은 경우 확인 표시만 나타날 수 있습니다.
   
    ![흐름 만들기](./media/common-data-model-intro/create-flow.png)

이제 개체가 원본 시스템에 생성될 때마다 Common Data Service로 가져옵니다. 필요한 작업을 수행하는 템플릿이 없는 경우, Common Data Service를 기반으로 작동하는 [흐름을 처음부터 새로 작성](get-started-logic-flow.md)할 수 있습니다.

데이터베이스의 변경 사항에 대해 작업을 수행할 수 있습니다. 예를 들어 데이터가 변경될 때마다 알림 메일을 보낼 수 있습니다.

