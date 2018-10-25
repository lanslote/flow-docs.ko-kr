---
title: '샘플: 비즈니스 프로세스 흐름 작업(Dynamics 365 고객 관계 개발자 가이드) | Microsoft Docs'
description: 샘플은 엔터티 레코드의 비즈니스 프로세스 흐름 인스턴스 검색, 비즈니스 프로세스 흐름 인스턴스 및 해당 프로세스 스테이지의 활성 경로 검색 및 활성 스테이지 변경과 같은 비즈니스 프로세스 흐름 작업을 프로그래밍 방식으로 수행하는 방법을 보여 줍니다.
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
ms.assetid: 7d378504-b4b2-4a09-838c-69ee094072ef
caps.latest.revision: 15
author: msftman
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 6fe2b6d600d86dfd807dbb1ef794a1f428f26fbf
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690057"
---
# <a name="sample-work-with-business-process-flows"></a>샘플: 비즈니스 프로세스 흐름 작업

이 샘플은 엔터티 레코드의 비즈니스 프로세스 흐름 인스턴스 검색, 비즈니스 프로세스 흐름 인스턴스 및 해당 프로세스 스테이지의 활성 경로 검색 및 활성 스테이지 변경과 같이 비즈니스 프로세스 흐름 작업을 프로그래밍 방식으로 수행하는 방법을 보여 줍니다. 이러한 개념에 대한 자세한 내용은 [코드를 사용하여 비즈니스 프로세스 흐름 작업](business-process-flows-code.md)을 참조하세요.  

 이 샘플은 [샘플: 비즈니스 프로세스 흐름 작업](https://go.microsoft.com/fwlink/p/?LinkId=846108)에서 다운로드할 수 있습니다.  

<a name="BKMK_Prerequisites"></a>   
## <a name="prerequisites"></a>필수 구성 요소  
 샘플을 실행하기 전에 다음이 필요합니다.  

1. 앱용 Common Data Service 환경의 액세스 권한이 있어야 합니다.  

2. 이 샘플에서 사용되는 잠재 고객, 영업 기회 및 워크플로 엔터티 및 비즈니스 프로세스 흐름 정의 엔터티 레코드에 대한 적절한 권한이 있어야 합니다.  

3. 샘플을 실행하려면 Visual Studio 2015 이상이 있어야 합니다.  

4. 샘플 프로젝트를 다운로드하고 샘플 프로젝트에 사용되는 NuGet 패키지를 복원하려면 인터넷 연결이 필요합니다.  

<a name="BKMK_WhatThisSampleDoes"></a>   
## <a name="what-this-sample-does"></a>이 샘플에서 수행하는 작업  

1.  샘플 잠재 고객 레코드를 만듭니다. 이렇게 하면 잠재 고객 레코드의 “잠재 고객-영업 기회 영업 프로세스” 비즈니스 프로세스 흐름 인스턴스가 자동으로 생성됩니다.  

2.  잠재 고객 레코드를 영업 기회 레코드로 변환합니다.  


4.  `RetrieveProcessInstances` 메시지를 사용하여 “영업 기회” 레코드와 연결된 비즈니스 프로세스 흐름 인스턴스를 검색합니다. 반환된 컬렉션의 첫 번째 레코드는 영업 기회 레코드의 활성 비즈니스 프로세스 흐름 인스턴스입니다(이 경우 “잠재 고객-영업 기회 영업 프로세스”).  

5.  `RetrieveActivePath` 메시지를 사용하여 “잠재 고객-영업 기회 영업 프로세스” 인스턴스의 활성 경로 및 프로세스 스테이지를 검색합니다.  

6.  “잠재 고객-영업 기회 영업 프로세스” 인스턴스의 현재 활성 스테이지를 검색하고 사용자에게 다음 스테이지로 이동할지 묻는 메시지를 표시합니다. 이동 여부 확인 시 활성 경로의 다음 스테이지를 “잠재 고객-영업 기회 영업 프로세스” 인스턴스의 활성 스테이지로 설정합니다.  

7.  마지막으로 샘플 실행 중에 생성된 레코드를 삭제할지 묻는 메시지를 사용자에게 표시합니다.  

     다음은 샘플 출력입니다.  

    ![샘플 출력](media/work-with-bpf-sample-output.png "샘플 출력")  

<a name="BKMK_runSample"></a>   
## <a name="run-the-sample"></a>샘플 실행  

1. WorkWithBPF Visual Studio 예제 프로젝트를 [다운로드](https://go.microsoft.com/fwlink/p/?LinkId=846108)하여 컴퓨터의 폴더에 추출합니다.  

2. 추출된 폴더에서 `WorkWithBPF.sln` 파일을 찾고 Visual Studio에서 엽니다.  

3. 샘플 프로젝트는 샘플을 실행하기 전에 복원해야 하는 NuGet 패키지를 사용합니다. Visual Studio에서 NuGet 패키지의 자동 복원이 사용하도록 설정되었는지 확인합니다. 추가 정보: [NuGet 패키지 복원 사용 및 사용 안 함](https://go.microsoft.com/fwlink/?linkid=846106)  

    또는 **프로젝트** > **NuGet 패키지 관리**를 선택하고 **복원**을 선택하여 샘플에서 사용된 패키지를 수동으로 복원합니다.  

4. F5 키를 누르거나 **디버그** > **디버깅 시작**을 선택합니다.  

5. 이전에 샘플 중 하나를 실행하지 않은 경우 코드를 실행하려면 정보를 입력해야 합니다. 그렇지 않으면 이전에 설정한 인스턴스 중 하나의 번호를 입력합니다.  


   |                                 프롬프트                                  |                                                                                             설명                                                                                             |
   |-------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |      Dynamics 365 Server 이름 및 포트[crm.dynamics.com] 입력       | Dynamics 365 Server의 이름을 입력합니다. 기본값은 북아메리카의 Dynamics 365(온라인)(crm.dynamics.com)입니다.<br /><br /> 예제: <br />crm5.dynamics.com |
   | 이 조직은 Microsoft 온라인 서비스에서 프로비전되었나요? (y/n) [n] |                                                 Microsoft 온라인 서비스의 프로비전된 조직인 경우 **y**를 입력합니다. 그렇지 않으면 **n**을 입력합니다.                                                  |
   |                          domain\username 입력                          |                                                                                    Microsoft 계정을 입력합니다.                                                                                     |
   |                             암호 입력                              |                      암호를 입력합니다. 문자는 창에서 “\*”로 표시됩니다. 암호는 나중에 재사용할 수 있도록 Microsoft 자격 증명 관리자에 안전하게 저장됩니다.                       |
   |                조직 번호 지정 (1-n) [1]                 |                      사용자가 속한 조직 목록에서 해당 번호를 입력합니다. 기본값은 목록의 첫 번째 조직을 나타내는 1입니다.                       |


6. 샘플은 [이 샘플에서 수행하는 작업](#what-this-sample-does)에 설명된 작업을 수행하고 추가 옵션을 사용할지 묻는 메시지를 표시할 수 있습니다.  

7. 샘플이 완료되면 Enter 키를 눌러 콘솔 창을 닫습니다.  

