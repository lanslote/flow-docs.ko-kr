---
title: Dynamics 365(온라인)로 흐름 만들기 | Microsoft Docs
description: Dynamics 365 연결 및 Microsoft Flow를 사용하여 유용한 워크플로 만들기
services: ''
suite: flow
documentationcenter: na
author: Mattp123
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/06/2017
ms.author: matp
ms.openlocfilehash: ffce0a2fcc77d2bf2ff132e589410cc032bf63fd
ms.sourcegitcommit: cd3cdcff3accb9a54f002fdc33d33935b4276249
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39519896"
---
# <a name="create-a-flow-by-using-dynamics-365-online"></a>Dynamics 365(온라인)를 사용하여 흐름 만들기
Dynamics 365 커넥터를 사용하여 Dynamics 365 또는 몇몇 다른 서비스에 이벤트가 발생할 때 시작한 다음 Dynamics 365 또는 몇몇 다른 서비스에서 작업을 수행하는 흐름을 만들 수 있습니다. 

Microsoft Flow에서 자주 사용하는 앱과 서비스 사이에 자동화된 워크플로를 설정하여 파일 동기화, 알림 수신, 데이터 수집 등의 작업을 수행할 수 있습니다. 자세한 내용은 [Microsoft Flow 시작](getting-started.md)을 참조하세요.

> [!IMPORTANT] 
> 흐름 트리거를 호출하려면 흐름과 함께 사용되는 Dynamics 365 고객 참여 엔터티에 **변경 내용 추적**이 활성화되어 있어야 합니다. 자세한 내용: [변경 내용 추적을 활성화하여 데이터 동기화 제어](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization) 

## <a name="create-a-flow-from-a-template"></a>템플릿에서 흐름 만들기
다음 예제와 같이 사용 가능한 많은 템플릿 중 하나를 사용하여 흐름을 만들 수 있습니다.

* Dynamics 365에서 개체가 만들어질 때 SharePoint에서 목록 항목을 만듭니다.
* Excel 테이블에서 Dynamics 365 잠재 고객 레코드를 만듭니다.
* Dynamics 365 계정을 Dynamics 365 for Operations의 고객에 대해 복사합니다.

템플릿에서 흐름을 만들려면 다음 단계를 수행합니다.

1. [Microsoft Flow 웹 사이트](https://flow.microsoft.com/)에 로그인합니다.
2. **서비스**를 클릭하거나 누른 다음 **Dynamics 365**를 클릭하거나 누릅니다.
3. 여러 템플릿을 사용할 수 있습니다. 시작하려면 원하는 템플릿을 선택합니다.

## <a name="create-a-task-from-a-lead"></a>잠재 고객에서 작업 만들기
필요한 사항에 대한 템플릿을 사용할 수 없으면 처음부터 흐름을 만듭니다. 이 연습에서는 Dynamics 365에서 잠재 고객이 만들어질 때마다 Dynamics 365에서 작업을 만드는 방법을 보여 줍니다.

1. [Microsoft Flow 웹 사이트](https://flow.microsoft.com/)에 로그인합니다.
2. **내 흐름**을 클릭하거나 누른 다음 **처음부터 만들기**를 클릭하거나 누릅니다.
3. 흐름 트리거 목록에서 **Dynamics 365 - 레코드가 만들어질 때**를 클릭하거나 누릅니다.
4. 메시지가 표시되면 Dynamics 365에 로그인합니다.
5. **조직 이름** 아래에서 흐름이 대기하게 하려는 Dynamics 365 인스턴스를 선택합니다.
6. **엔터티 이름** 아래에서 대기하다가 흐름을 시작하는 트리거 역할을 하게 하려는 엔터티를 선택합니다.
   
     이 연습의 경우 **잠재 고객**을 선택합니다.
   
    ![흐름 세부 정보](./media/connection-dynamics365/flow-details.png)
    > [중요] 흐름을 Dynamics 365 엔터티에서 트리거하려면 엔터티 정의는 변경 추적을 사용하도록 설정되어야 합니다. [변경 내용 추적을 활성화하여 데이터 동기화 제어](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization)를 참조하세요.
    
7. **새 단계**를 클릭하거나 누른 다음 **동작 추가**를 클릭하거나 누릅니다.
8. **Dynamics 365 – 새 레코드 만들기**를 클릭하거나 누릅니다.
9. **조직 이름** 아래에서 흐름이 레코드를 만들게 하려는 Dynamics 365 인스턴스를 선택합니다. 참고로 이 인스턴스는 이벤트가 트리거되는 것과 같은 인스턴스일 필요가 없습니다.
10. **엔터티 이름** 아래에서 이벤트가 발생할 때 레코드를 만들 엔터티를 선택합니다.
    
     이 연습의 경우 **작업**을 선택합니다.
11. **제목** 상자가 나타납니다. 제목을 클릭하거나 누르면 이 필드 중 하나를 선택할 수 있는 동적 콘텐츠 창이 나타납니다.
    
    * **성**. 이 필드를 선택하면 작업이 만들어질 때 잠재 고객의 성이 **제목** 필드에 삽입됩니다.
    * **토픽**. 이 필드를 선택하면 작업이 만들어질 때 잠재 고객에 대한 **토픽** 필드가 **제목** 필드에 삽입됩니다.
    
    이 연습의 경우 **토픽**을 선택합니다.
    
    ![흐름 추가 토픽](./media/connection-dynamics365/flow-addtopic.png)
    
    > **팁:** 동적 콘텐츠 창에서 **더 보기**를 클릭하거나 눌러 엔터티와 연결된 필드를 더 표시합니다. 예를 들어 작업의 **주제** 필드를 잠재 고객의 **회사 이름**, **고객**, **설명** 또는 **전자 메일** 필드로 채울 수 있습니다.
    > 
    > 
12. **흐름 만들기**를 클릭하거나 누릅니다.

## <a name="create-a-wunderlist-task-from-a-dynamics-365-task"></a>Dynamics 365 작업에서 Wunderlist 작업 만들기
이 연습에서는 Dynamics 365에서 작업이 만들어질 때마다 [Wunderlist](https://www.wunderlist.com)에서 작업을 만드는 방법을 보여 줍니다. Wunderlist는 작업 목록 만들기, 알림 추가 또는 볼일 추적을 만드는 데 사용할 수 있는 인터넷 기반 서비스입니다.

1. [Microsoft Flow 웹 사이트](https://flow.microsoft.com/)에 로그인합니다.
2. **내 흐름**을 클릭하거나 누른 다음 **처음부터 만들기**를 클릭하거나 누릅니다.
3. 흐름 트리거 목록에서 **Dynamics 365 - 레코드가 만들어질 때**를 클릭하거나 누릅니다.
4. **조직 이름** 아래에서 흐름이 대기하게 하려는 Dynamics 365 인스턴스를 선택합니다.
5. **엔터티 이름** 아래에서 대기하다가 흐름을 시작하는 트리거 역할을 하게 하려는 엔터티를 선택합니다.
   
    이 연습의 경우 **작업**을 선택합니다.
6. **새 단계**를 클릭하거나 누른 다음 **동작 추가**를 클릭하거나 누릅니다.
7. 작업 만들기를 입력한 다음 **Wunderlist – 작업 만들기** 를 클릭하거나 누릅니다.
8. **목록 ID** 아래에서 **받은 편지함**을 선택합니다.
9. **제목** 아래에서 동적 콘텐츠 창의 **주제**를 선택합니다.
10. **흐름 만들기**를 클릭하거나 누릅니다.  

## <a name="trigger-based-logic"></a>트리거 기반 논리
**레코드를 만드는 경우**, **레코드를 업데이트하는 경우** 및 **레코드를 삭제하는 경우**와 같은 트리거는 이벤트가 발생하고 몇 분 안에 흐름을 시작합니다.  드물게 흐름을 트리거하는 데 최대 2시간이 걸릴 수 있습니다.

트리거가 발생하면 흐름은 알림을 받지만 흐름은 작업이 실행되는 시점에 존재하는 데이터에서 실행됩니다.  예를 들어 흐름이 새 레코드를 만들 때 트리거되고, 흐름이 실행되기 전에 두 번 레코드를 업데이트하는 경우 흐름은 최신 데이터를 사용하여 한 번만 실행됩니다.

## <a name="specify-advanced-options"></a>고급 옵션 지정
흐름에 단계를 추가할 때 **고급 옵션 표시**를 클릭하거나 눌러 흐름에서 데이터가 필터링되는 방법을 제어하는 필터 또는 order by 쿼리를 추가할 수 있습니다.

예를 들어 필터 쿼리를 사용하여 활성 연락처만 검색하고 성을 기준으로 이들을 정렬할 수 있습니다. 이렇게 하려면 OData 필터 쿼리 **statuscode eq 1**을 입력하고 동적 콘텐츠 창에서 **성**을 선택합니다. 필터 및 order by 쿼리에 대한 자세한 내용은 [MSDN: $filter](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_1) 및 [MSDN: $orderby](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_2)를 참조하세요.

  ![orderby 쿼리 흐름](./media/connection-dynamics365/flow-orderby-query.png)

### <a name="best-practices-when-using-advanced-options"></a>고급 옵션을 사용하는 경우의 모범 사례
필드에 값을 추가할 때 값을 입력하든 또는 동적 콘텐츠 창에서 선택하든 상관없이 필드 형식을 일치시켜야 합니다.

| 필드 형식 | 사용 방법 | 찾을 수 있는 위치 | 이름 | 데이터 형식 |
| --- | --- | --- | --- | --- |
| 텍스트 필드 |텍스트 필드에는 텍스트 한 줄 또는 텍스트 형식 필드인 동적 콘텐츠가 필요합니다. 예를 들어 **범주** 및 **하위 범주** 필드가 있습니다. |**설정** > **사용자 지정** > **시스템 사용자 지정** > **엔터티** > **작업** > **필드** |**범주** |**텍스트 한 줄** |
| 정수 필드 |일부 필드에는 정수 또는 정수 형식 필드인 동적 콘텐츠가 필요합니다. 예를 들어 **완료율** 및 **기간**이 있습니다. |**설정** > **사용자 지정** > **시스템 사용자 지정** > **엔터티** > **작업** > **필드** |**percentcomplete** |**자연수** |
| 날짜 필드 |일부 필드에는 mm/dd/yyyy 형식으로 입력한 데이터 또는 날짜 형식 필드인 동적 콘텐츠가 필요합니다. 예를 들어 **만든 날짜**, **시작 날짜**, **실제 시작**, **마지막 보류 시간**, **실제 종료** 및 **만기일**이 있습니다. |**설정** > **사용자 지정** > **시스템 사용자 지정** > **엔터티** > **작업** > **필드** |**createdon** |**날짜 및 시간** |
| 레코드 ID와 조회 유형이 모두 필요한 필드 |다른 엔터티 레코드를 참조하는 일부 필드에는 레코드 ID와 조회 유형이 모두 필요합니다. |**설정** > **사용자 지정** > **시스템 사용자 지정** > **엔터티** > **계정** > **필드** |**accountid** |**기본 키** |

### <a name="more-examples-of-fields-that-require-both-a-record-id-and-lookup-type"></a>레코드 ID와 조회 유형이 모두 필요한 필드의 더 많은 예
여기서는 이전 테이블을 확장하여 동적 콘텐츠 목록에서 선택한 값에 대해 동작하지 않는 필드의 더 많은 예를 보여 줍니다. 대신에 이러한 필드를 사용하려면 PowerApps의 필드에 레코드 ID와 조회 유형을 모두 입력해야 합니다.

* **소유자** 및 **소유자 유형**.
  
  * **소유자** 필드는 유효한 사용자 또는 팀 레코드 ID여야 합니다.
  * **소유자 유형**은 **systemusers** 또는 **teams**여야 합니다.
* **고객** 및 **고객 유형**.
  
  * **고객** 필드는 유효한 계정 또는 연락처 레코드 ID여야 합니다.
  * **고객 유형**은 **accounts** 또는 **contacts**여야 합니다.
* **관련 항목** 및 **관련 유형**.
  
  * **관련 항목** 필드는 계정 또는 연락처 레코드 ID 같은 유효한 레코드 ID여야 합니다.
  * **관련 유형**은 **계정** 또는**연락처** 같은 레코드 조회 유형이어야 합니다.

이 예에서는 레코드 ID에 해당하는 계정 레코드를 추가하여 작업의 **관련 항목** 필드에 추가합니다.

  ![흐름 레코드 ID 및 형식 계정](./media/connection-dynamics365/flow-recordid-account.png)

또한 이 예제에서는 사용자의 레코드 ID에 따라 특정 사용자에게 작업을 할당합니다.

  ![흐름 레코드 ID 및 형식 사용자](./media/connection-dynamics365/flow-recordid-user.png)

레코드의 ID를 찾으려면 이 토픽의 뒷부분에 나오는 [레코드 ID 찾기](#find-the-records-id)를 참조하세요.

> **중요:** 필드에 "내부 사용 전용"이라는 설명이 있는 경우 값을 포함하지 않아야 합니다. 이러한 필드는 **횡단 경로**, **추가 매개 변수** 및 **표준 시간대 규칙 버전 번호** 를 포함합니다.
> 
> 

## <a name="find-the-records-id"></a>레코드의 ID 찾기
1. Dynamics 365 웹 응용 프로그램에서 계정 레코드 같은 레코드를 엽니다.
2. 작업 도구 모음에서 **팝아웃**
   ![팝아웃 레코드](./media/connection-dynamics365/popout.png)를 클릭하거나 누릅니다. (또는 **전자 메일로 링크 보내기** 를 클릭하거나 눌러 전체 URL을 기본 전자 메일 프로그램에 복사합니다.)
   
    웹 브라우저의 주소 표시줄에서 URL은 레코드 ID %7b와 %7d 사이의 인코딩 문자를 포함합니다.
   
   ![RecordId](./media/connection-dynamics365/recordid.png)

## <a name="related-topics"></a>관련 토픽
[흐름 문제 해결](fix-flow-failures.md)

[조직의 Microsoft Flow 관련 Q & A](organization-q-and-a.md)

[질문과 대답](frequently-asked-questions.md)

