---
title: 단계별 프로세스에 앱용 CDS 대화 사용(더 이상 사용되지 않음) | Microsoft Docs
description: 대화는 단계별 스크립트를 사용하여 사용자에게 프로세스를 안내하는 방식으로 정보를 수집하고 처리하는 동기 또는 대화형 프로세스입니다.
ms.custom: ''
ms.date: 10/31/2017
ms.reviewer: ''
ms.topic: article
ms.assetid: d17f8ae2-854b-4f67-a115-5a03d4f0b8ce
caps.latest.revision: 25
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f8b2e87bdb9aed63e9f180d446349779cd37c25c
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689666"
---
# <a name="use-cds-for-apps-dialogs-for-guided-processes-deprecated"></a>단계별 프로세스에 앱용 CDS 대화 사용(더 이상 사용되지 않음)

[대화는 더 이상 사용되지 않습니다](/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated). 대화를 비즈니스 프로세스 흐름 또는 캔버스 앱으로 바꿔야 합니다. 추가 정보: [대화를 비즈니스 프로세스 흐름 또는 캔버스 앱으로 바꾸기](replace-dialogs.md) 

대화는 단계별 스크립트를 사용하여 사용자에게 프로세스를 안내하는 방식으로 정보를 수집하고 처리하는 앱용 CDS(Common Data Service)의 동기 또는 대화형 프로세스입니다. 예를 들어 사례 해결 및 사례 에스컬레이션 관련 서비스 담당자를 위한 가이드로 사용할 대화를 만들 수 있습니다. 마찬가지로 영업 기회 자격 및 잠재 고객 점수와 같이 영업 프로세스를 표준화하기 위한 대화를 만들 수 있습니다. 자세한 내용은 Dynamics 365 고객 관계 개발자 가이드에서 [단계별 프로세스에 대화 사용](/dynamics365/customer-engagement/developer/use-dialogs-guided-processes)을 참조하세요.

## <a name="differences-between-workflows-and-dialogs"></a>워크플로 및 대화의 차이점

다음 표는 앱용 CDS 워크플로와 대화의 차이점 정보를 제공합니다.  


| 워크플로     |    대화      |
|---------------|--------------|
|                                                                                                  사용자가 시작하거나 자동화할 수 있습니다.                                                                                                   |                                                                                          사용자가 시작해야 합니다.                                                                                          |
|                                  비동기 또는 실시간 프로세스로서, 완료될 때까지 실행하는 데 사용자 입력이 필요하지 않습니다. 실시간 프로세스는 즉시 실행되지만 비동기 프로세스는 백그라운드에서 실행됩니다.                                   | 완료될 때까지 실행하는 데 사용자 입력이 필요한 실시간 프로세스입니다. 이러한 프로세스를 실행할 때 프로세스를 실행하기 위해 적절하게 선택할 수 있도록 마법사 같은 인터페이스가 제공됩니다. |
|                                                    실행 중인 비동기 워크플로의 세부 정보를 저장하는 엔터티는 `AsyncOperation`이고 `Process`는 실시간 워크플로에 사용됩니다.                                                     |                                                       실행 중인 대화에서 생성된 정보를 저장하는 엔터티는 `ProcessSession` 엔터티입니다.                                                       |
|                  트리거는 워크플로에서 지원됩니다. 지원되는 트리거 목록을 보려면 [프로세스의 지원되는 형식, 트리거 및 엔터티](/dynamics365/customer-engagement/developer/supported-types-triggers-entities-actions-processes)를 참조하세요.                   |                                                                                   트리거는 대화에서 지원되지 않습니다.                                                                                    |
  
### <a name="see-also"></a>참고 항목
[대화를 비즈니스 프로세스 흐름 또는 캔버스 앱으로 바꾸기](replace-dialogs.md)
