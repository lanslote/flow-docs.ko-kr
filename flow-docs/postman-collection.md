---
title: "Postman으로 사용자 지정 커넥터 설명 | Microsoft Docs"
description: "사용자 지정 커넥터를 등록하기 위한 Postman 컬렉션 만들기"
services: 
suite: flow
documentationcenter: 
author: sunaysv
manager: anneta
editor: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/28/2017
ms.author: sunayv
ms.openlocfilehash: fe98999ea307367c7f3b032974fef9be6ca3f388
ms.sourcegitcommit: f3236f9f1ec050cda0d9c3e2b9c356132b2a2594
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2018
---
# <a name="describe-a-custom-connector-with-postman"></a>Postman으로 사용자 지정 커넥터 설명
[Postman](https://www.getpostman.com/)은 API 개발을 보다 빠르고 쉽게 만들기 위한 도구입니다. 이 자습서는 Postman 컬렉션을 만드는 방법을 설명하고 이를 사용하여 Microsoft Flow에서 쉽게 [사용자 지정 커넥터](register-custom-api.md)를 만들 수 있습니다.

## <a name="prerequisites"></a>필수 구성 요소
* [Postman 앱](https://www.getpostman.com/apps) 설치.

## <a name="create-a-postman-collection"></a>Postman 컬렉션 만들기
Azure Cognitive Services [텍스트 분석 API](https://www.microsoft.com/cognitive-services/text-analytics-api)에 대한 Postman 컬렉션을 만들어 보겠습니다. 이 API는 전달하는 텍스트의 언어, 의향 및 핵심 문구를 식별합니다.

1. Postman 컬렉션 만들기의 첫 번째 단계는 요청을 만드는 것입니다. 요청을 만들 때 HTTP 동사, 요청 URL, 쿼리 또는 경로 매개 변수, 헤더 및 본문을 설정할 수 있습니다. 자세한 내용은 Postman 설명서의 [요청 보내기](https://www.getpostman.com/docs/requests)를 참조하세요. 검색 언어 API 끝점의 경우 다음과 같이 값을 설정합니다.
   
    ![Postman 요청](./media/postman-collection/request.png)
   
    사용되는 매개 변수 및 값의 세부 정보:
   
   | 매개 변수 | 값 |
   | --- | --- |
   | 동사 |올리기 |
   | 요청 URL |https://westus.api.cognitive.microsoft.com/text/analytics/v2.0/languages |
   | 매개 변수 |numberOfLanguagesToDetect |
   | 권한 부여 |"권한 없음" |
   | 헤더 |Ocp-Apim-Subscription-Key = <your subscription key> <br/>Content-Type = application/json |
   | 본문 |<code>{<br/>&nbsp;&nbsp;&nbsp;"documents": [<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"id": "1",<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"text": "Hello World"<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}<br/>&nbsp;&nbsp;]<br/>}<code> |
2. **전송**을 클릭하여 요청하고 응답을 다시 가져옵니다.
3. **저장**을 클릭하여 Postman 컬렉션에 요청을 저장합니다.
   
    ![Postman 응답](./media/postman-collection/request-response-save.png)
4. **요청 저장** 대화 상자에 **요청 이름** 및 **요청 설명**을 제공합니다. 사용자 지정 커넥터에서 이러한 값을 사용합니다.
   
    ![Postman 저장 컬렉션](./media/postman-collection/save-request-note.png)
   
    요청에 대한 응답을 저장할 수도 있습니다. 사용자 지정 커넥터는 현재 요청당 단일 응답만을 지원합니다. 요청당 여러 응답을 저장하는 경우 첫 번째 것만 사용됩니다.
   
    ![Postman 저장 응답](./media/postman-collection/save-response.png)
5. 다른 요청 및 응답을 만들고 저장하여 Postman 컬렉션 빌드를 계속합니다.
6. 모든 요청 및 응답에 대한 Postman 컬렉션 빌드를 완료한 후 컬렉션을 내보냅니다.
   
    ![Postman 내보내기](./media/postman-collection/export.png)
7. 내보내기 형식으로 **컬렉션 v1**을 선택합니다.
   
    ![Postman 내보내기](./media/postman-collection/export2.png)

이제 이 Postman 컬렉션을 사용하여 Microsoft Flow에서 사용자 지정 커넥터를 만들 수 있습니다.

> [!IMPORTANT]
> Postman 컬렉션에서 사용자 지정 커넥터를 만들 때 작업 및 트리거에서 `Content-type` 헤더를 제거해야 합니다. 이 헤더는 Microsoft Flow에 의해 자동으로 추가됩니다. 인증 헤더(예: `Ocp-Apim-Subscription-Key`)는 **보안** 섹션에서 정의해야 하며 작업 및 트리거에서 제거해야 합니다. 
> 
> 

자세한 내용은 [Microsoft Flow에서 사용자 지정 커넥터 등록 및 사용](register-custom-api.md)을 참조하세요.

