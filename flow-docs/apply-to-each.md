---
title: 항목의 배열을 통해 반복하도록 각 작업에 적용을 사용합니다. | Microsoft Docs
description: 항목의 배열을 통해 반복하도록 Microsoft Flow를 사용하여 여러 조건을 확인하고 해당 조건에 따라 작업을 수행합니다.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/16/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 914fe6d84bb63e1f3e184794d34fbfd58ad30963
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690172"
---
# <a name="use-the-apply-to-each-action-in-microsoft-flow-to-process-a-list-of-items-periodically"></a>Microsoft Flow에서 각 작업에 적용을 사용하여 항목의 목록을 주기적으로 처리
많은 트리거는 새 전자 메일이 받은 편지함에 도착하는 경우와 같은 이벤트에 따라 흐름을 바로 시작할 수 있습니다. 이러한 트리거는 유용하지만 때로는 데이터 원본에 있는 항목의 속성에 따라 특정 작업을 수행하는, 미리 정의된 일정에 따라 데이터 원본을 쿼리하는 흐름을 실행하려고 합니다. 이를 수행하기 위해 흐름은 일정(예: 하루에 한 번)에 따라 시작될 수 있으며 **각각에 적용**과 같은 루프 작업을 사용하여 항목의 목록을 처리할 수 있습니다. 예를 들어 **각각에 적용**을 사용하여 데이터베이스의 레코드 또는 Microsoft SharePoint에서 항목의 목록을 업데이트합니다.

이 연습에서 15분마다 실행되고 다음을 수행하는 흐름을 만듭니다.

1. Office 365 Outlook 받은 편지함에 최근 10개의 읽지 않은 메시지를 가져옵니다.
2. 10개의 메시지 각각을 확인하여 제목에 **모임 시작**이 있는지 확인합니다.
3. 상사가 전송한 전자 메일인지 높은 중요도로 전송된 전자 메일인지 확인합니다.
4. 푸시 알림을 전송하고 제목에 **모임 시작**이 있고 상사가 전송한 전자 메일이거나 높은 중요도로 전송된 모든 전자 메일을 읽음으로 표시합니다.

이 다이어그램에서는 이 연습에서 만들 흐름의 세부 정보를 보여 줍니다.

![빌드되는 흐름의 개요](./media/apply-to-each/foreach-flow-visio.png)

## <a name="prerequisites"></a>필수 구성 요소
이 연습에서 단계를 성공적으로 수행하기 위한 요구 사항은 다음과 같습니다.

* [Microsoft Flow](https://flow.microsoft.com)를 사용하도록 등록된 계정.
* Office 365 Outlook 계정.
* [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) 또는 [Windows Phone](https://aka.ms/flowmobilewindows)용 Microsoft Flow 모바일 앱.
* Office 365 Outlook 및 푸시 알림 서비스에 대한 연결.

## <a name="create-a-flow"></a>흐름 만들기
1. [Microsoft Flow](https://flow.microsoft.com)에 로그인합니다.
2. **내 흐름** 탭을 선택한 다음 빈 값에서 흐름을 만듭니다.
   
    ![빈 값에서 만들기](./media/apply-to-each/foreach-1.png)
3. 검색 상자에 “일정"을 입력하여 모든 서비스 및 일정에 관련된 트리거를 검색합니다.
4. **일정 - 되풀이**를 선택하여 흐름이 다음에 제공할 일정에서 실행함을 나타냅니다.
   
    ![일정 되풀이 작업](./media/apply-to-each/foreach-2.png)
5. 15분마다 실행되도록 일정을 설정합니다.
   
    ![일정 실행](./media/apply-to-each/foreach-3.png)
6. **+ 새 단계**, **작업 추가**를 선택한 다음 검색 상자에 **outlook**을 입력하여 Microsoft Outlook에 관련된 모든 작업에 대해 검색합니다.
7. **Office 365 Outlook - 전자 메일 가져오기** 작업을 선택합니다.
   
    ![전자 메일 가져오기 작업 선택](./media/apply-to-each/foreach-4.png)
8. **전자 메일 가져오기** 카드가 열립니다. **전자 메일 가져오기** 카드를 구성하여 받은 편지함 폴더에서 상위 10개의 읽지 않은 전자 메일을 선택합니다. 첨부 파일은 흐름에서 사용되지 않으므로 첨부 파일을 포함하지 마십시오.
   
    ![전자 메일 카드 구성](./media/apply-to-each/foreach-5.png)
   
   > [!NOTE]
   > 지금까지 받은 편지함에서 일부 전자 메일을 가져오는 간단한 흐름을 만들었습니다. 이러한 전자 메일은 배열로 반환되고 **각각에 적용** 작업은 배열이 필요하므로 이것이 정확하게 필요한 것입니다.
   > 
   > 

## <a name="add-actions-and-conditions"></a>작업 및 조건 추가
1. **+ 새 단계**, **자세히**를 선택한 다음 **각각에 적용 추가** 작업을 선택합니다.
   
    ![각각에 적용 선택](./media/apply-to-each/foreach-6.png)
2. **각각에 적용** 카드의 **이전 단계에서 출력 선택** 상자에 **본문** 토큰을 삽입합니다. **각각에 적용** 작업에 사용될 전자 메일의 본문을 가져옵니다.
   
    ![본문 토큰 추가](./media/apply-to-each/foreach-7.png)
3. **조건 추가**를 선택합니다.
   
    ![조건 추가](./media/apply-to-each/foreach-8.png)
4. **조건** 카드를 구성하여 "모임 시작" 단어에 대해 각 전자 메일의 제목을 검색합니다.
   
   * **개체 이름** 상자에 **제목** 토큰을 삽입합니다.
   * **관계** 목록에서 **포함**을 선택합니다.
   * **값** 상자에 **모임 시작**을 입력합니다.
     
     ![조건 구성](./media/apply-to-each/foreach-subject-condition.png)
5. **자세히**를 선택한 다음 **예이면 아무 것도 안 함** 분기에서 **조건 추가**를 선택합니다. **조건 2** 카드가 열립니다. 다음과 같이 해당 카드를 구성합니다.
   
   * **개체 이름** 상자에 **중요도** 토큰을 삽입합니다.
   * **관계** 목록에서 **같음**을 선택합니다.
   * **값** 상자에 **높음**을 입력합니다.
     
     ![조건 추가](./media/apply-to-each/foreach-importance-condition.png)
6. **예이면 아무 것도 안 함** 섹션에서 **작업 추가**를 선택합니다. **작업 선택** 카드가 열리고 여기에서 검색 조건(**모임 시작** 전자 메일이 높은 중요도로 전송됨)이 true인 경우 수행할 동작을 정의합니다.
   
    ![작업 추가](./media/apply-to-each/foreach-9.png)
7. **알림**을 검색한 다음 **알림 - 나에게 모바일 알림 전송** 작업을 선택합니다.
   
    ![알림 검색 및 선택](./media/apply-to-each/foreach-10.png)
8. **나에게 모바일 알림 전송** 카드에서 전자 메일의 제목이 "모임 시작"을 포함하는 경우 전송될 푸시 알림에 대한 세부 정보를 제공한 다음 **작업 추가**를 선택합니다.
   
    ![알림 구성](./media/apply-to-each/foreach-11.png)
9. 검색 용어로 **읽기**를 입력한 다음 **Office 365 Outlook - 읽은 상태로 표시** 작업을 선택합니다. 푸시 알림이 전송된 후 각 전자 메일을 읽은 상태로 표시합니다.
   
    ![읽은 상태로 표시 작업 추가](./media/apply-to-each/foreach-12.png)
10. **읽은 상태로 표시** 카드의 **메시지 ID** 상자에 **메시지 ID** 토큰을 추가합니다. **메시지 ID** 토큰을 찾기 위해 **더 보기**를 선택해야 할 수도 있습니다. 읽은 상태로 표시될 메시지의 ID를 나타냅니다.
    
     ![메시지 ID 추가](./media/apply-to-each/foreach-13.png)
11. **아니요이면 아무 것도 안 함** 분기에서 **조건 2** 카드로 돌아갑니다.
    
    * **작업 추가**를 선택한 다음 검색 상자에 **관리자 가져오기**를 입력합니다.
    * 검색 결과 목록에서 **Office 365 사용자 - 관리자 가져오기** 작업을 선택합니다.
    * **관리자 가져오기** 카드의 **사용자** 상자에 *전체* 전자 메일 주소를 입력합니다.
      
      ![관리자 가져오기 작업 추가 및 구성](./media/apply-to-each/foreach-get-manager.png)
12. **자세히**를 선택한 다음 **아니요인 경우** 분기에서 **조건 추가**를 선택합니다. **조건 3** 카드가 열립니다. 전자 메일 보낸 사람의 전자 메일 주소(보낸 사람 토큰)가 상사의 전자 메일 주소(전자 메일 토큰)와 동일한지 여부를 확인하도록 카드를 구성합니다.
    
    * **개체 이름** 상자에 **보낸 사람** 토큰을 삽입합니다.
    * **관계** 목록에서 **포함**을 선택합니다.
    * **값** 상자에 **전자 메일** 토큰을 입력합니다.
      
      ![검색 조건 구성](./media/apply-to-each/foreach-condition3-card.png)
13. **조건 3** 카드의 **예이면 아무 것도 안 함** 섹션에서 **작업 추가**를 선택합니다. **예인 경우** 카드가 열리고 여기에서 검색 조건(상사가 전송한 전자 메일)이 true인 경우 수행할 동작을 정의합니다.
    
     ![조건 구성](./media/apply-to-each/foreah-condition3-add-action.png)
14. **알림**을 검색한 다음 **알림 - 나에게 모바일 알림 전송** 작업을 선택합니다.
    
     ![알림 검색 작업](./media/apply-to-each/foreach-10.png)
15. **나에게 모바일 알림 전송 2** 카드에서 전자 메일이 상사로부터 전송된 경우 전송될 푸시 알림에 대한 세부 정보를 제공한 다음 **작업 추가**를 선택합니다.
    
     ![알림 카드 구성](./media/apply-to-each/foreach-boss-notification.png)
16. **Office 365 Outlook - 읽은 상태로 표시** 작업을 추가합니다. 푸시 알림이 전송된 후 각 전자 메일을 읽은 상태로 표시합니다.
    
     ![읽은 상태로 표시 작업 추가](./media/apply-to-each/foreach-12.png)
17. **읽은 상태로 표시 2** 카드에 **메시지 ID** 토큰을 추가합니다. **메시지 ID** 토큰을 찾기 위해 **더 보기**를 선택해야 할 수도 있습니다. 읽은 상태로 표시될 메시지의 ID를 나타냅니다.
    
     ![읽은 상태로 표시 작업 구성](./media/apply-to-each/foreach-mark-as-read2.png)
18. 흐름에 이름을 지정한 다음 만듭니다.
    
     ![흐름에 이름을 지정하고 저장](./media/apply-to-each/foreach-14.png)

따라서 수행한 경우 흐름은 이 다이어그램과 비슷해야 합니다.

![만든 흐름의 개요](./media/apply-to-each/foreach-flow-finished.png)

## <a name="run-the-flow"></a>흐름 실행
1. 제목에 **모임 시작**을 포함하는 높은 중요도의 전자 메일을 자신에게 보냅니다(또는 조직의 구성원이 해당 전자 메일을 보내도록 합니다).
2. 전자 메일이 받은 편지함에 있고 읽지 않은 상태인지 확인합니다.
3. Microsoft Flow에 로그인하고 **내 흐름**을 선택한 다음 **지금 실행**을 선택합니다.
   
    ![지금 실행](./media/apply-to-each/foreach-run-1.png)
4. **흐름 실행**을 선택하여 흐름을 정말로 실행하려는지 확인합니다.
   
    ![실행 확인](./media/apply-to-each/foreach-run-2.png)
5. 몇 분 후에 성공적인 실행 결과가 표시됩니다.
   
    ![실행 결과](./media/apply-to-each/foreach-run-3.png)

## <a name="view-results-of-the-run"></a>실행 결과 보기
이제 흐름을 성공적으로 실행했으므로 모바일 장치에서 푸시 알림을 받게 됩니다.

1. 모바일 장치에서 Microsoft Flow 앱을 연 다음 **작업** 탭을 선택합니다. 모임에 대한 푸시 알림을 볼 수 있습니다.
   
    ![작업 탭 선택](./media/apply-to-each/foreach-notification-1.png)
2. 알림의 전체 콘텐츠를 보려면 알림을 선택해야 합니다. 전체 알림이 다음과 유사하게 표시됩니다.
   
    ![알림 세부 정보](./media/apply-to-each/foreach-notification-2.png)
   
   > [!NOTE]
   > 푸시 알림을 수신하지 않는 경우 모바일 장치에 작업 데이터 연결이 있는지 확인합니다.
   > 
   > 

