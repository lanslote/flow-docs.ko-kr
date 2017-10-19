---
title: "Microsoft Flow 소개 | Microsoft Docs"
description: "Microsoft Flow의 정의 및 용도를 이해합니다."
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: kZs7lqgp4LU
courseduration: 5m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2016
ms.author: deonhe
ms.openlocfilehash: 63ecfabc6b91f3a12fffd6986187b6bbd254b6da
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2017
---
# <a name="guided-learning-for-microsoft-flow"></a>Microsoft Flow에 대한 가이드 학습
Microsoft Flow에 대한 **가이드 학습**을 시작합니다. 이 자습형 온라인 과정은 순차적인 방법으로 Microsoft Flow를 설명하므로 기초부터 지식을 쌓을 수 있습니다.

이 **가이드 학습** 과정에는 현재 시작 섹션이 있으며 다음 몇 주 동안 콘텐츠를 추가할 예정입니다. 과정은 개념, 정보 및 예제를 배우는 데 도움이 되는 논리 흐름과 함께 이해할 수 있는 청크로 지침을 제공하도록 설계되었습니다. 또한 학습을 돕도록 시각적 개체를 포함합니다.

Microsoft Flow **초보자**인 경우 이 과정을 통해 시작할 수 있으며 Microsoft Flow **베테랑**인 경우 이 과정을 통해 개념을 함께 결합하고 모자란 부분을 채울 수 있습니다. 이 과정을 즐기길 바라며 추후에 더 많은 콘텐츠가 포함되길 기대합니다.

이 학습 문제 해결 과정은 현재 **진행 중인 작업**입니다.  **이 코스에서**진행 상황과 **표시하려는 다른 항목**을 알려주세요.

## <a name="what-is-microsoft-flow"></a>Microsoft Flow란?
Microsoft Flow는 가장 일반적인 앱 및 서비스에서 워크플로를 자동화하여 더욱 우수하고 효율적으로 작업을 할 수 있도록 하는 온라인 **워크플로 서비스**입니다.  Microsoft Flow는 등록할 때 사용할 수 있는 백 개가 넘는 서비스에 연결할 수 있습니다. 또한 Microsoft Flow에는 워크플로를 끊임 없이 추적할 수 있는 모바일 애플리케이션, 기업에서 사용하기 위한 관리 환경이 있고 고유한 응용 프로그램에 Microsoft Flow도 포함할 수 있습니다.

이 과정에서는 Microsoft Flow 및 그 개념을 소개하고, 관리자로서 환경에서 흐름을 빌드하고 관리하고 제어할 수 있는 방법을 알려줍니다. Contoso Flooring Company라는 가상의 회사에서 사용할 정보 및 시나리오를 표시합니다.  빌드 중인 시나리오가 사용자의 비즈니스 또는 클라이언트의 비즈니스에서 얼마나 유용한지를 표시하기 위해 이를 수행합니다.

![흐름 개념 스케치](./media/learning-introducing-flow/flow-conceptual.png)

Microsoft Flow는 **인터넷의 응용 프로그램**에 국한되지 않습니다.  SharePoint 및 SQL Server에서와 같이 흐름에 **온-프레미스 데이터**를 포함할 수 있습니다.

## <a name="what-you-can-do-with-microsoft-flow"></a>Microsoft Flow를 통해 수행할 수 있는 작업
 Microsoft Flow를 사용하여 자주 사용하는 응용 프로그램과 서비스 사이에 **자동화된 워크플로**를 만들고, 파일을 동기화하고, 알림을 수신하고, 데이터를 수집하는 등의 작업을 수행할 수 있습니다.  [Microsoft Flow와 함께 사용할 수 있는 응용 프로그램 및 서비스 목록](https://flow.microsoft.com/services/)은 지속적으로 확장 중입니다.  Microsoft Flow와 함께 자동화할 수 있는 작업의 일부 예는 다음과 같습니다.

* 즉각적으로 중요한 알림 또는 전자 메일을 수신하고 응답합니다.
* 새 판매 선두 캡처, 추적 및 팔로업.
* 한 서비스에서 다른 서비스로 파일을 복사합니다.
* 비즈니스에 대한 데이터를 수집하고 팀에 알립니다.
* 승인을 자동화합니다.

Microsoft Flow의 일반적인 용도는 **알림을 수신하는** 것입니다. 예를 들어, 판매 잠재 고객을 Dynamics 365 또는 Salesforce에 추가할 때마다 즉시 잠재 고객에 대한 전자 메일을 수신하거나 휴대폰에서 모바일 앱에 푸시 알림을 수신할 수 있습니다. **새 판매 잠재 고객**을 팔로업할 수 있는 좋은 방법입니다.

Microsoft Flow를 사용하여 파일을 복사할 수도 있습니다. 예를 들어, 파일을 DropBox의 폴더에 추가할 때마다 SharePoint의 폴더에 복사하여 파일이 생성될 때 **팀에 알릴** 수 있습니다.

비즈니스에 대한 사람들의 피드백을 확인하려는 경우 특정 해시태그를 포함한 Tweet이 게시될 때마다 **트리거**되는 **흐름을 만들** 수 있습니다. 흐름은 해당 Tweet 세부 정보를 복사하여 SQL Database, SharePoint 목록 또는 OneDrive에서 호스트되는 Excel 파일로 만듭니다. 어느 쪽이든 작동합니다. 수집한 데이터를 사용하여 Power BI에 연결하고, 추세를 찾고, 데이터에 대한 질문을 묻는 **작업**을 만들 수 있습니다.

마지막으로 가장 일반적으로 Flow를 사용하는 방법 중 하나는 **승인을 자동화**하는 것입니다. 예를 들어, SharePoint 목록을 사용하여 회사에서 승인을 추적하는 경우 승인 작업 흐름을 트리거할 수 있습니다.

더 많은 내용은 **템플릿 기본** 페이지에서 **템플릿**의 목록을 찾아보세요(다음 섹션에서 자세히 설명). 해당 목록에 표시되지 않는 흐름에 대한 멋진 아이디어가 있나요?  문제 없습니다!  처음부터 직접 고유의 흐름을 만들 수 있으며 원한다면 커뮤니티와 공유할 수 있습니다!

## <a name="creating-and-administering-flows"></a>흐름 만들기 및 관리
흐름을 만들고 관리하기 위해 웹앱을 사용하거나 [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) 또는 [Windows Phone](https://aka.ms/flowmobilewindows)용 Microsoft Flow 모바일 앱을 사용할 수 있습니다. 선택하는 플랫폼에 관계 없이 문제를 진단하고 데이터를 동기화하기 쉽습니다.

* 어디에서든지 흐름을 켜거나 끕니다.
* 흐름이 실패한 경우 참조하세요.
* 자세한 실행 기록 보고서를 검토합니다.
* 알림 유형으로 실행을 보고 필터링합니다.

## <a name="next-lesson"></a>다음 단원
이제 Microsoft Flow가 무엇이고 가능한 작업이 무엇인지 살펴보았으니 흐름을 구성하는 것을 살펴보겠습니다.

