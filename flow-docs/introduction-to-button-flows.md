---
title: 단추 흐름을 사용하여 반복적인 작업을 자동화하고 실행하는 방법 알아보기 | Microsoft Docs
description: 단추 흐름 소개입니다.
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
ms.date: 01/30/2017
ms.author: deonhe
ms.openlocfilehash: 558570733819e1fde6c1845ed5ca9debe9232c88
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "23440517"
---
# <a name="introducing-button-flows"></a>단추 흐름 소개
## <a name="what-are-button-flows"></a>단추 흐름이란?
여러 반복 작업을 단추 탭 한 번으로 실행할 수 있다면 참 좋을 것입니다. 예를 들어 팀에게 팀 동기화에 매일 참여하도록 알리는 전자 메일을 신속하게 전송할 수 있습니다. 당일에 계획된 확인 항목이 없다는 것을 통보받은 후에 사용자 코드를 기반으로 한 새로운 Visual Studio Online 빌드를 시작하게 될 것입니다. 단추 흐름을 통해 모바일 장치의 단추를 눌러서 이러한 작업 및 기타 다양한 작업을 간단히 수행할 수 있습니다.

**참고** Flow 포털 또는 모바일 장치에서 단추 흐름을 만들 수 있습니다.  
  ![개요 이미지](./media/introduction-to-button-flows/buttons-montage.png)  

## <a name="why-create-buttons"></a>단추를 만드는 이유
언제든지 모바일 장치를 통해 반복 작업을 쉽게 실행할 수 있도록 단추를 만듭니다. 단추를 실행하면 시간이 절약되고 실행한 작업이 자동화되었기 때문에 수동으로 수행하는 것보다 오류가 적어집니다.  

## <a name="create-a-button"></a>단추 만들기
### <a name="prerequisites"></a>필수 구성 요소
* Flow에 액세스합니다. 관리자는 액세스를 제공할 수 있습니다.
* 단추를 만드는 커넥터를 사용할 수 있는 권한이 있는 계정입니다. 예를 들어 Dropbox에 액세스하는 단추를 만들기 위해 Dropbox 계정이 필요합니다.

### <a name="from-the-portal"></a>포털에서
이 연습에서 VSO(Visual Studio Online) 빌드를 시작하고 빌드를 시작할 때 알 수 있도록 알림을 전송하는 단추를 만들어 봅니다.  

1. **보여 주기** 드롭다운 목록을 선택하고 **단추** 범주를 선택합니다. 그러면 단추 흐름에서 사용할 수 있는 템플릿의 목록을 필터링합니다.  
   ![개요 이미지](./media/introduction-to-button-flows/create-button-1.png)   
2. 템플릿 목록에서 **VSO에서 새 빌드 트리거** 템플릿을 선택합니다.  
   ![개요 이미지](./media/introduction-to-button-flows/create-button-2.png)  
3. **VSO에서 새 빌드 트리거** 페이지에서 **이 템플릿 사용** 단추를 선택합니다.   
   ![개요 이미지](./media/introduction-to-button-flows/create-button-3.png)  
4. 서명하지 않은 경우 이 시점에서 서명하라는 메시지가 표시됩니다.  
   ![개요 이미지](./media/introduction-to-button-flows/create-button-4.png)  
5. Flow에 등록한 후에 선택한 템플릿에 사용되는 커넥터에 로그인하라는 메시지가 표시됩니다. 이 예제 윗부분의 2 단계에서 **VSO에서 새 빌드 트리거** 템플릿을 선택했으므로 로그인되어 있지 않은 경우 VSO 및 사용하는 기타 커넥터에 로그인해야 합니다.  
   ![개요 이미지](./media/introduction-to-button-flows/create-button-pre-req-1.png)    
6. VSO 계정에 액세스할 수 있는 권한을 Flow에 부여하는 데 동의하는 경우 **허용** 단추를 선택합니다.  
   ![개요 이미지](./media/introduction-to-button-flows/create-button-5.png)   
   **참고** 마찬가지로 각 커넥터에 권한을 부여하기 위해 필요합니다. 다음 단계로 이동할 준비가 되면 디자이너는 다음과 같이 표시됩니다. **계속** 단추를 선택하여 진행합니다.  
   ![개요 이미지](./media/introduction-to-button-flows/create-button-6.png)   
7. 이제 시작하려는 빌드에 대한 속성을 구성할 준비가 되었습니다.    
   ![개요 이미지](./media/introduction-to-button-flows/create-button-7.png)  
8. **계정 이름**, **프로젝트 이름**, **빌드 정의 ID**, **원본 분기** 및 필요에 따라 **새 빌드 큐에 대기** 카드에서 **매개 변수**를 선택 또는 입력합니다.    
   ![개요 이미지](./media/introduction-to-button-flows/create-button-8.png)  
9. 다음으로 **푸시 알림 보내기** 카드에 푸시 알림의 속성을 구성합니다. 기본적으로 이 푸시 알림은 빌드의 상태를 표시하는 웹 페이지에 HTML 링크를 보내도록 구성됩니다.  
   ![개요 이미지](./media/introduction-to-button-flows/create-button-9.png)  
10. **흐름 만들기** 단추를 선택하여 단추 흐름을 저장합니다. ![개요 이미지](./media/introduction-to-button-flows/create-button-10.png)  
11. 잠시 후에 이 성공 메시지가 표시되어야 합니다.  
    ![개요 이미지](./media/introduction-to-button-flows/create-button-11.png)  

축하합니다. 단추 흐름을 만들었습니다. 이제 언제 어디서나 흐름 앱의 **단추** 탭에서 이 단추 흐름을 실행할 수 있습니다. 그저 "단추"를 누르면 실행됩니다. Microsoft Flow 모바일 앱은 [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) 또는 [Windows Phone](https://aka.ms/flowmobilewindows)에서 사용할 수 있습니다.

### <a name="from-your-mobile-device"></a>모바일 장치에서
**참고**: 이 연습이 Android 장치의 화면을 표시하지만 iOS 장치의 화면 및 환경도 비슷합니다.

흐름 앱에서

1. **찾아보기** 탭을 선택하여 **단추** 범주로 스크롤합니다.  
   ![개요 이미지](./media/introduction-to-button-flows/create-button-from-mobile-1.png)  
2. **모두 보기** 링크를 선택합니다. 모든 준비된 단추 템플릿이 표시됩니다.     
   ![개요 이미지](./media/introduction-to-button-flows/create-button-from-mobile-2.png)  
3. **모임에 참석하도록 팀에 전자 메일 보내기** 템플릿을 선택합니다.    
   ![개요 이미지](./media/introduction-to-button-flows/create-button-from-mobile-3.png)  
4. 페이지의 맨 아래에 있는 **이 템플릿 사용** 링크를 선택합니다.    
   ![개요 이미지](./media/introduction-to-button-flows/create-button-from-mobile-4.png)  
5. 이 템플릿에서 사용하는 모든 서비스에 로그인해야 합니다.    
   ![개요 이미지](./media/introduction-to-button-flows/create-button-from-mobile-5.png)  
6. 모든 서비스에 로그인한 후에 **다음** 링크를 선택합니다.      
   ![개요 이미지](./media/introduction-to-button-flows/create-button-from-mobile-6.png)  
7. **만들기** 링크를 선택합니다. 예를 들어 여기에서 흐름을 검토하고 전자 메일을 개인 설정하는 데 필요한 항목을 변경할 수 있습니다.        
   ![개요 이미지](./media/introduction-to-button-flows/create-button-from-mobile-7.png)  
8. 몇 분 후에 단추 흐름이 만들어집니다. **내 흐름 보기**를 선택합니다.   
   ![개요 이미지](./media/introduction-to-button-flows/create-button-from-mobile-8.png)  
9. **내 흐름** 탭의 모든 흐름 보기  
   ![개요 이미지](./media/introduction-to-button-flows/create-button-from-mobile-9.png)  

축하합니다. 단추 흐름을 만들었습니다. 이제 언제 어디서나 흐름 앱의 **단추** 탭에서 이 단추 흐름을 실행할 수 있습니다. 그저 "단추"를 누르면 실행됩니다. 현재 Android 및 iOS 모바일 장치에서 Flow 앱을 사용할 수 있습니다.  

![개요 이미지](./media/introduction-to-button-flows/create-button-from-mobile-10.png)  

## <a name="trigger-a-button-flow"></a>단추 흐름 트리거
이제 단추 흐름을 만들었으므로 실행해 봅니다. Flow 앱에서만 단추 흐름을 실행할 수 있기 때문에 반드시 Android 또는 iOS 모바일 장치에서 Flow를 설치하도록 합니다.  

1. 이제 Flow 앱을 시작하고 페이지 맨 아래에 있는 **단추** 탭을 누르고 트리거할 단추 흐름을 나타내는 *단추* 를 누릅니다.  
   ![개요 이미지](./media/introduction-to-button-flows/trigger-button-1.png)   
2. 흐름이 실행되는 동안 진행률을 참조하세요.  
   ![개요 이미지](./media/introduction-to-button-flows/trigger-button-2.png)   
3. 마지막으로, 페이지가 업데이트되면 단추 흐름이 완료되었음을 나타냅니다.  
   ![개요 이미지](./media/introduction-to-button-flows/trigger-button-3.png)   

흐름을 실행하는 방법은 여기까지입니다. 

이제 전자 메일이 전송되었음을 나타내는 푸시 알림이 표시되어야 합니다.  

## <a name="monitor-your-button-flow-runs"></a>단추 흐름 실행 모니터링
Flow 앱의 **작업** 탭에서 단추 흐름을 모니터링할 수 있습니다.   
![개요 이미지](./media/introduction-to-button-flows/create-button-from-mobile-13.png)  

**참고**: 실행의 결과에 대해 자세히 알아보려는 작업을 눌러서 실행에 대해 알아봅니다.  

![개요 이미지](./media/introduction-to-button-flows/activity-details-1.png)  

## <a name="manage-button-flows"></a>단추 흐름 관리
단추 흐름을 완전히 제어할 수 있으므로 언제든지 단추를 활성화/비활성화, 편집 또는 삭제할 수 있습니다. 모바일 앱 또는 Flow 포털에서 **내 흐름**을 선택하여 흐름을 관리하기 시작합니다.    

Flow 앱의 **내 흐름** 탭에서

1. 관리하려는 흐름을 선택합니다.    
   ![개요 이미지](./media/introduction-to-button-flows/trigger-button-4.png)   
2. 수행하려는 작업에 따라 이러한 옵션 중 하나를 누를 수 있습니다.    
   ![개요 이미지](./media/introduction-to-button-flows/manage-flow-1.png)  
3. **흐름 삭제**를 눌러서 흐름을 삭제합니다.  

**참고** 흐름을 삭제하면 모든 실행 기록이 삭제됩니다.   
![개요 이미지](./media/introduction-to-button-flows/manage-flow-2.png)   

1. 단추 흐름을 편집한 후에 **업데이트**를 누르면 변경 내용을 저장합니다.   
   ![개요 이미지](./media/introduction-to-button-flows/manage-flow-3.png)   
2. **실행 기록**으 누르면 특정 단추 흐름의 모든 실행 결과를 확인합니다.    
   ![개요 이미지](./media/introduction-to-button-flows/manage-flow-4.png)  
3. 흐름을 사용하지 않도록 설정한 경우 **단추** 탭에서 더 이상 사용할 수 없습니다.    
   ![개요 이미지](./media/introduction-to-button-flows/manage-flow-5.png)  

## <a name="next-steps"></a>다음 단계
* [단추 흐름 공유](share-buttons.md)
* 단추 흐름이 실행되면 실시간으로 데이터를 보내는 [단추 트리거 토큰](introduction-to-button-trigger-tokens.md) 사용 방법에 대해 알아보세요.
* [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) 또는 [Windows Phone](https://aka.ms/flowmobilewindows)용 Microsoft Flow 모바일 앱 설치.

