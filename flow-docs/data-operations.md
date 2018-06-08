---
title: 데이터 작업 이해 | Microsoft Docs
description: HTML 테이블 만들기, CSV 테이블 만들기, Microsoft Flow로 배열 작성, 조인, 선택 및 필터링하기 등과 같은 작업 수행에 대해 알아봅니다.
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/02/2017
ms.author: deonhe
ms.openlocfilehash: aa3f61d09cb5e9b8d07124838883da9b5b9794ab
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "23440913"
---
# <a name="use-data-operations-with-microsoft-flow"></a>Microsoft Flow로 데이터 작업 사용하기
이 연습에서는 배열 작성, 조인, 선택, 필터링, 테이블 만들기, 흐름을 만들 때 데이터를 조작하기 위해 사용할 수 있는 JSON 구문 분석과 같이 많이 사용하는 Microsoft Flow의 일부 데이터 작업에 대해 알아봅니다.

## <a name="prerequisites"></a>필수 구성 요소
* Microsoft Flow에 액세스합니다.
* JSON 배열을 사용하여 HTTP POST 요청을 흐름에 보내는 [PostMan](https://www.getpostman.com/postman)과 같은 도구.

## <a name="use-the-compose-action"></a>작성 작업 사용하기
**데이터 작업 ‑ 작성**(작성) 작업을 사용하면 흐름을 디자인할 때 동일한 데이터를 여러 번 입력해야 하는 번거러움을 피할 수 있습니다. 예를 들어, 숫자 배열을 입력해야 하는 경우: 흐름을 디자인하는 동안 여러 차례 ````[0,1,2,3,4,5,6,7,8,9]````을 하면, 이 같은 배열을 저장하기 위해 작성 작업을 사용할 수 있습니다.

1. **작성**을 검색한 후 **데이터 작업 - 작성** (작성) 작업을 선택합니다.
   
    ![작성 작업 검색 및 선택](./media/data-operations/search-select-compose.png)
2. 나중에 참조할 **입력** 상자에 배열을 입력합니다.
   
    ![작성 작업 구성](./media/data-operations/add-array-compose.png)

> [!TIP]
> 나중에 보다 쉽게 참조할 수 있도록 **작성** 카드의 제목 표시줄에서 "작성" 텍스트를 클릭하여 **작성** 카드의 이름을 변경합니다.
> 
> 

작성 작업의 콘텐츠에 액세스해야 할 경우 다음 단계를 따라 **이 흐름에서 사용된 앱과 커넥터에서 동적 콘텐츠 추가**에 있는 **출력** 토큰을 통해 수행합니다.

1. **데이터 작업 – 조인**과 같은 작업을 추가합니다.
2. 작성 작업에서 저장한 콘텐츠를 추가하려는 컨트롤을 선택합니다.
   
    **이 흐름에서 사용된 앱과 커넥터에서 동적 콘텐츠 추가**가 열립니다.
3. **이 흐름에서 사용된 앱과 커넥터에서 동적 콘텐츠 추가**에서 **동적 콘텐츠** 탭의 **작성** 범주 아래에 있는 **출력** 토큰을 선택합니다.
   
    ![작성 작업의 출력 사용](./media/data-operations/use-compose-output.png)

## <a name="use-the-join-action"></a>조인 작업 사용
**데이터 작업 - 조인** 작업 (조인)을 사용하여 사용자가 선택한 구분 기호로 배열을 구분합니다. 예를 들어, 사용자의 흐름이 이메일 주소: ````["d@example.com", "k@example.com", "dal@example.com"]````의 다음 배열을 포함하는 웹 요청을 받는다고 가정합니다. 그러나 전자 메일 프로그램의 주소는 세미콜론으로 구분되는 단일 문자열이어야 합니다. 이렇게 하려면 **데이터 작업 - 조인**(조인) 작업을 사용하여 다음 단계를 따라 쉼표 구분 기호를 세미콜론 ";"으로 변경합니다.

1. 새 동작을 추가하고, **조인**을 검색한 후 **데이터 작업-조인** (조인)을 선택합니다.
   
    ![조인 작업을 검색하고 선택합니다](./media/data-operations/search-select-join.png)
2. 배열을 **에서** 상자에 입력한 후 **결합에 사용할 구분 기호** 상자에 사용하려는 새 구분 기호를 입력합니다.
   
    여기서는 세미콜론 (;)을 새 구분 기호로 사용했습니다.
   
    ![조인 작업 구성](./media/data-operations/add-array-join.png)
3. 흐름을 저장하고 실행합니다.
4. 흐름을 실행한 후 **데이터 작업 – 조인** 동작의 출력은 다음과 같습니다.
   
    ![조인 출력](./media/data-operations/join-output.png)

## <a name="use-the-select-action"></a>선택 작업 사용
**데이터 작업 – 선택** (선택)을 사용하여 배열에 있는 개체의 모양을 변형합니다. 예를 들어 배열에 있는 각 개체의 요소를 추가하거나, 제거하거나, 이름을 바꿀 수 있습니다.

> [!NOTE]
> 선택 작업을 사용하여 요소를 추가하거나 제거할 수는 있는 반면에 배열에 있는 개체 수를 변경할 수는 없습니다.
> 
> 

예를 들어 선택 작업을 사용할 수 있는 경우는 데이터가 이 형식으로 웹 요청을 통해 흐름에 들어가고

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

들어오는 데이터의 형태를 변경하기 위해 "first"를 "FirstName"으로 "last"를 "LastName"으로 이름을 변경하고 "first"와 "last"를 결합한 "FamilyName"이란 이름의 새 멤버를 추가할 때입니다.

````[ { "FirstName": "Deon", "FamilyName": "Herb", "FullName": "Deon Herb" }, { "FirstName": "K", "FamilyName": "Herb", "FullName": "K Herb" } ]````.

이를 수행하려면 다음을 따라주세요.

1. **요청 / 응답 – 응답** (요청) 작업을 흐름에 추가합니다.
2. **요청** 카드에서 **샘플 페이로드를 사용하여 스키마 생성**을 선택합니다.
3. 나타나는 상자에 원본 데이터 배열 샘플을 붙여 넣은 후 **완료** 단추를 선택합니다.
4. **데이터 작업 – 선택** (선택)을 추가한 후 다음 이미지와 같이 구성합니다.
   
    ![선택 작업 구성](./media/data-operations/select-card.png)
   
   > [!TIP]
   > 선택 작업의 출력은 새로 형태를 갖춘 개체를 포함하는 배열입니다. 그런 후 앞에서 설명한 **작성**과 같은 다른 어떤 작업에서나 이 배열을 사용할 수 있습니다.
   > 
   > 

## <a name="use-the-filter-array-action"></a>필터 배열 작업 사용
배열 내의 개체 수를 사용자가 제공한 범주와 일치하는 하위 집합으로 줄이려면 **데이터 작업-필터 배열** (필터 배열)을 사용합니다.

> [!NOTE]
> 필터 배열은 배열 내의 개체 모양을 변환하는 데 사용할 수 없습니다. 또한 필터링할 텍스트는 대소문자를 구분합니다.
> 
> 

예를 들어 이 배열에서 필터 배열을 사용할 수 있습니다.

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

*첫 번째*가 "Deon"으로 설정된 개체 만을 포함한 새 배열을 만들려면.

이렇게 해 봅니다.

1. **데이터 작업-필터 배열** (필터 배열) 작업을 찾아 흐름에 추가합니다.
2. 필터 배열 작업을 다음 이미지와 같이 구성합니다.
   
    ![필터 배열 작업 구성](./media/data-operations/add-configure-filter-array.png)
3. 흐름을 저장한 후 실행합니다.
   
    JSON 배열을 흐름에 전송하는 웹 요청을 생성하기 위해 [PostMan](https://www.getpostman.com/postman)을 사용할 수 있습니다.
4. 흐름이 실행될 때 JSON 입력은 이 배열과 같다고 가정합니다.
   
    ````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````,
   
    출력은 이 배열과 같습니다. (*첫 번째*가 "Deon"으로 설정된 개체만 작업의 출력에 포함됩니다.)
   
    ````[ { "first": "Deon", "last": "Herb" } ]````

## <a name="use-the-create-csv-table-action"></a>csv 테이블 만들기 작업 사용
**데이터 작업-CSV 테이블 만들기** (csv 테이블 만들기)를 사용하여 JSON 배열 입력을 쉼표로 구분된 값(CSV) 테이블로 변환합니다. 선택적으로 CSV 출력에 헤더가 표시되게 할 수 있습니다. 예를 들어 **CSV 테이블 만들기** 작업을 사용하여 다음 배열을 CSV 테이블로 변환할 수 있습니다.

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

1. **데이터 작업 - CSV 테이블 만들기** 작업이 다음 이미지와 같아지도록 찾고, 추가한 다음 구성합니다.
   
    ![csv 테이블 만들기 작업 구성](./media/data-operations/create-csv-table.png)
   
    참고: 이 이미지의 **본문** 토큰은 **요청/응답 - 응답** 작업에서 가져옵니다. 하지만 **CSV 테이블 만들기** 작업에 대한 입력은 사용자 흐름에 있는 이전 작업 출력에서 가져오거나 **에서** 상자에서 직접 입력할 수도 있습니다.
2. 흐름을 저장한 후 실행합니다.
   
    흐름 실행 시, **CSV 테이블 만들기** 출력은 이 이미지와 같습니다.
   
    ![Csv 테이블 출력 만들기](./media/data-operations/create-csv-table-output.png)

## <a name="use-the-create-html-table-action"></a>html 테이블 만들기 작업을 사용합니다
**데이터 작업 - HTML 테이블 만들기**를 사용하여 JSON 배열 입력을 HTML 테이블로 변경합니다. 선택적으로 HTML 출력에 헤더가 표시되게 할 수 있습니다.

이렇게 하려면 자세한 예시로 [csv 테이블 섹션 만들기](#use-the-create-csv-table-action)에 나오는 단계를 따라야 합니다. **데이터 작업 - HTML 테이블 만들기** 작업을 **데이터 작업 - CSV 테이블 만들기** 작업 대신에 사용해야 합니다.

> [!TIP]
> 전자 메일을 통해 HTML 테이블 전송하려는 경우 전자 메일 작업에서 "IsHtml"을 선택해야 합니다.
> 
> 

