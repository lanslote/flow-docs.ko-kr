---
title: "Web API에 대한 사용자 지정 커넥터 빌드 | Microsoft Docs"
description: "Microsoft Flow에서 Azure Active Directory 인증으로 ASP.NET Web API를 만드는 방법에 대해 알아봅니다"
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
ms.date: 12/06/2016
ms.author: sunayv
ms.openlocfilehash: b151724aa27cb5cf5f85809a69bd6947258eaee1
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2017
---
# <a name="build-a-custom-connector-for-a-web-api-in-microsoft-flow"></a>Microsoft Flow에서 Web API에 대한 사용자 지정 커넥터 빌드
이 자습서에서는 ASP.NET Web API 빌드를 시작하고 Azure Web Apps에서 호스팅하며, Azure Active Directory 인증을 사용하도록 설정한 다음 Microsoft Flow에서 ASP.NET Web API를 등록하는 방법을 보여 줍니다. API가 등록된 후 연결하고 흐름에서 호출할 수 있습니다. 

## <a name="prerequisites"></a>필수 구성 요소
* [Azure 구독](https://azure.microsoft.com/free/)
* [PowerApps 계정](https://powerapps.microsoft.com)
* [Visual Studio](https://www.visualstudio.com/vs/) 2013 이상.

## <a name="create-an-aspnet-web-api-and-deploy-it-to-azure"></a>ASP.NET Web API 만들기 및 Azure에 배포
1. Visual Studio에서 **파일** > **새 프로젝트**를 클릭하여 새 C# ASP.NET 웹 응용 프로그램을 만듭니다.
   
    ![새 Web App](./media/customapi-web-api-tutorial/newwebapp.png)
2. **Web API** 템플릿을 선택합니다.  **클라우드에서 호스트**를 선택해 둡니다.  **인증 변경**을 클릭합니다.
   
    ![새 웹 프로젝트 템플릿](./media/customapi-web-api-tutorial/new-web-api.png)
3. **인증 안 함**을 선택한 다음 **확인**을 클릭합니다.
   
    ![인증 없음](./media/customapi-web-api-tutorial/noauth.png)
4. **새 ASP.NET 프로젝트** 대화 상자에서 **확인**을 클릭합니다.  Microsoft Azure Web App 구성 대화 상자가 나타납니다.
   
    ![Microsoft Azure Web App 구성](./media/customapi-web-api-tutorial/azure-publishing.png)]
   
    Azure 계정을 선택하고 **Web App 이름**을 입력(또는 기본값을 그대로 적용)하고 Azure **구독**을 선택합니다.  **App Service 계획**(구독 내에서 Web Apps의 컬렉션)을 선택하거나 만듭니다.  **리소스 그룹**(구독 내에서 Azure 리소스 그룹화)을 선택하거나 만듭니다.  Web App을 배포할 수 있는 지역을 선택합니다.  Web API에 필요한 경우 Azure **데이터베이스 서버**를 선택하거나 만듭니다.  마지막으로 **확인**을 클릭합니다.
5. Web API를 만듭니다.
   
   > [!NOTE]
   > Web API에 대해 준비된 코드가 없는 경우 자습서 [ASP.NET Web API 2(C#) 시작](http://www.asp.net/web-api/overview/getting-started-with-aspnet-web-api/tutorial-your-first-web-api)을 시도하세요.
   > 
   > 
6. Web API를 PowerApps에 연결하려면 해당 작업을 설명하는 [Swagger](http://swagger.io/) 파일이 필요합니다.  [온라인 편집기](http://editor.swagger.io/)를 직접 사용하여 OpenAPI를 작성할 수 있지만 이 자습서에서는 [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle/blob/master/README.md)이라는 오픈 소스 도구를 사용합니다.  **도구** > **NuGet 패키지 관리자** > **패키지 관리자 콘솔**을 클릭하여 Visual Studio 프로젝트에서 Swashbuckle Nuget 패키지를 설치한 다음 패키지 관리자 콘솔에서 `Install-Package Swashbuckle` 명령을 입력합니다.
   
    ![Swashbuckle 패키지 설치](./media/customapi-web-api-tutorial/swashbuckle-console.png)
   
   > [!TIP]
   > Swashbuckle을 설치한 후 Web API 응용 프로그램을 실행하면 URL `http://<your root URL>/swagger/docs/v1`에 OpenAPI 파일이 생성됩니다.  생성된 사용자 인터페이스는 `http://<your root URL>/swagger`에서 제공됩니다.
   > 
   > 
7. Web API가 준비되면 Azure에 게시합니다. Visual Studio에 게시하려면 솔루션 탐색기에서 웹 프로젝트를 마우스 오른쪽 단추로 클릭하고 **게시...**를 클릭한 다음 게시 대화 상자에 표시되는 메시지를 따릅니다.
8. `https://<azure-webapp-url>/swagger/docs/v1`으로 이동하여 OpenAPI JSON을 검색합니다.  콘텐츠를 JSON 파일로 저장합니다.  브라우저에 따라 텍스트를 복사하고 빈 텍스트 파일에 붙여 넣을 수 있습니다.   
   
   > [!IMPORTANT]
   > 작업 ID가 중복되는 OpenAPI 문서는 유효하지 않습니다. 샘플 C# 템플릿을 사용하는 경우 작업 ID `Values_Get`은 두 번 반복됩니다. 인스턴스 하나를 `Value_Get`로 변경하고 다시 게시하여 해결할 수 있습니다.
   > 
   > 또한 이 자습서에서 [OpenAPI 샘플](http://pwrappssamples.blob.core.windows.net/samples/webAPI.json)을 다운로드할 수 있습니다. 사용하기 전에 주석(`//`로 시작)을 제거해야 합니다.
   > 
   > 

## <a name="set-up-azure-active-directory-authentication"></a>Azure Active Directory 인증 설정
이제 Azure에서 두 개의 AAD(Azure Active Directory) 응용 프로그램을 만듭니다.  이 작업을 수행하는 방법의 예는 [Azure Resource Manager 자습서](customapi-azure-resource-manager-tutorial.md#enable-authentication-in-azure-active-directory)를 참조하세요.

> [!IMPORTANT]
> 두 앱은 동일한 디렉터리에 있어야 합니다.
> 
> 

### <a name="first-aad-application-securing-the-web-api"></a>첫 번째 AAD 응용 프로그램: Web API 보안 유지
첫 번째 AAD 응용 프로그램은 Web API의 보안을 유지하는 데 사용됩니다. 이름을 **webAPI**라고 지정합니다.  다음 값을 사용하여 위의 연결 자습서 단계("Azure Active Directory에서 인증 사용"이라는 섹션)에 따릅니다.

* 로그온 URL: `https://login.windows.net`
* 회신 URL: `https://<your-root-url>/.auth/login/aad/callback`
* 클라이언트 키가 필요하지 않습니다.
* 사용 권한을 위임할 필요가 없습니다.
* **중요!** 응용 프로그램 ID를 적어둡니다.  나중에 필요합니다.

### <a name="second-aad-application-securing-the-custom-connector-and-delegated-access"></a>두 번째 AAD 응용 프로그램: 사용자 지정 커넥터 및 위임된 액세스 보안 유지
두 번째 AAD 응용 프로그램은 사용자 지정 커넥터 등록의 보안을 유지하고 첫 번째 응용 프로그램에서 보호하는 Web API에 대한 위임된 액세스를 획득하는 데 사용됩니다. 이 항목의 이름을 **webAPI customAPI**라고 지정합니다.

* 로그온 URL: `https://login.windows.net`
* 회신 URL: `https://msmanaged-na.consent.azure-apim.net/redirect`
* Web API에 대한 위임된 액세스를 가지도록 사용 권한을 추가합니다.
* 나중에 이 응용 프로그램의 응용 프로그램 ID도 필요하므로 기록합니다.
* 클라이언트 키 및 저장소를 안전한 위치에서 생성합니다. 이 키는 나중에 필요합니다.

## <a name="add-authentication-to-your-azure-web-app"></a>Azure Web App에 인증 추가
1. [Azure Portal](https://portal.azure.com)에 로그인한 다음 첫 번째 섹션에서 배포된 Web App을 찾습니다.
2. **설정**을 클릭한 다음 **인증/권한 부여**를 선택합니다.
3. **App Service 인증**을 켜고 **Azure Active Directory**를 선택합니다.  다음 블레이드에서 **Express**를 선택합니다.  
4. **기존 AD 앱 선택**을 클릭하고 이전에 만든 **webAPI** AAD 응용 프로그램을 선택합니다.

이제 AAD를 사용하여 웹 응용 프로그램을 인증할 수 있습니다.

## <a name="add-the-custom-connector-to-microsoft-flow"></a>Microsoft Flow에 사용자 지정 커넥터 추가
1. OpenAPI를 수정하여 `securityDefintions` 개체 및 Web App에 사용되는 AAD 인증을 추가합니다. **host** 속성이 있는 OpenAPI 섹션은 다음과 같이 표시되어야 합니다.

```javascript
// File header should be above here...

"host": "<your-root-url>",
"schemes": [
    "https"         //Make sure this is https!
],
"securityDefinitions": {
    "AAD": {
        "type": "oauth2",
        "flow": "accessCode",
        "authorizationUrl": "https://login.windows.net/common/oauth2/authorize",
        "tokenUrl" : "https://login.windows.net/common/oauth2/token",
        "scopes": {}
    }
},

// The rest of the OpenAPI follows...
```

1. [Microsoft Flow](https://flow.powerapps.com)로 이동하고 [Microsoft Flow에서 사용자 지정 커넥터 등록 및 사용](register-custom-api.md)에 설명된 대로 사용자 지정 커넥터를 추가합니다.
2. 일단 OpenAPI를 업로드하면 마법사는 Web API에 AAD 인증을 사용하는지를 자동으로 검색합니다.
3. 사용자 지정 커넥터에 대한 AAD 인증을 구성합니다.  
   
   * **클라이언트 ID**: *webAPI-CustomAPI라는 클라이언트 ID*
   * **암호**: *webAPI-CustomAPI라는 클라이언트 키*
   * **로그인 URL**: `https://login.windows.net`
   * **ResourceUri**: *webAPI의 클라이언트 ID*
4. **만들기**를 클릭하고 사용자 지정 커넥터에 연결합니다.

## <a name="next-steps"></a>다음 단계
[Azure Resource Manager 사용자 지정 커넥터 자습서](customapi-azure-resource-manager-tutorial.md)를 살펴봅니다.

