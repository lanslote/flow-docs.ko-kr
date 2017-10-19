---
title: "DLP(데이터 손실 방지) 정책 사용 | Microsoft Docs"
description: "Microsoft Flow를 사용하여 작업을 자동화하는 경우 데이터를 공유할 수 있는 서비스를 제어하기 위해 데이터 손실 방지 정책을 사용하는 방법에 대해 알아봅니다."
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: vls4RPVP5xE
courseduration: 6m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/16/2017
ms.author: deonhe
ms.openlocfilehash: 2e69fd07103cb16e6c91476462f39586810b4a5d
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2017
---
# <a name="use-data-loss-prevention-dlp-policies"></a>DLP(데이터 손실 방지) 정책 사용
[Microsoft Flow](https://flow.microsoft.com)를 통해 워크플로를 작성할 수 있는 [서비스](https://flow.microsoft.com/services)의 확장 목록을 사용하면 SharePoint 또는 Salesforce와 같은 엔터프라이즈 서비스에 저장된 중요한 비즈니스 데이터를 보호해야 할 수 있습니다. 조직에서 중요한 비즈니스 데이터가 소비자 서비스(예: Twitter 및 Facebook)에 게시되지 않도록 하는 정책을 만들어야 합니다. Microsoft Flow를 사용하면 사용자가 흐름을 만들 때 비즈니스 데이터를 공유할 수 있는 소비자 서비스를 엄격하게 제어하는 **DLP(데이터 손실 방지)** 정책을 쉽게 만들 수 있습니다.  

## <a name="terms-you-should-get-familiar-with"></a>용어 설명
| 용어 | 설명 |
| --- | --- |
| **DLP** |Data Loss Prevention(데이터 손실 방지)의 약어입니다. **서비스** 사이의 데이터 공유를 관리하는 DLP 정책을 만듭니다. |
| **서비스** |[서비스](https://flow.microsoft.com/services)는 Salesforce, SharePoint 및 Twitter와 같은 응용 프로그램입니다. 이러한 서비스는 흐름을 만드는 데 많이 사용됩니다. |
| **데이터 그룹** |서비스의 논리적 그룹화입니다. 동일한 데이터 그룹에서 데이터를 공유하도록 허용된 서비스를 배치합니다. 여기에는 두 데이터 그룹, 즉 **비즈니스 데이터 전용** 그룹 및 **비즈니스 데이터 허용 안됨** 그룹이 있습니다. |
| **환경** |DLP는 [환경](../environments-overview-admin.md)에 적용됩니다. 환경에는 사용자가 포함됩니다. |
| **사용자** |사용자는 환경의 구성원 자격을 기반으로 하여 DLP 정책이 적용되는 조직의 구성원입니다. |
| **흐름** |흐름은 사용 가능한 서비스의 조합을 사용하는 워크플로 앱입니다. |

## <a name="all-about-how-dlp-policies-work"></a>자세한 DLP 정책 작동 방식 소개
DLP 정책은 단순히 각 서비스를 상호 배타적인 두 데이터 그룹 중 하나에 배치하는 명명 규칙입니다. 따라서 이 규칙도 환경에 적용됩니다. 환경은 사용자의 논리적 그룹화입니다. 사용자는 다른 데이터 그룹에 배치한 서비스 간에 데이터를 공유하는 흐름을 작성할 수 없습니다. 즉 사용자는 **단일** 데이터 그룹 내의 서비스 간에 데이터를 공유하는 흐름만 만들 수 있습니다. 따라서 데이터 그룹 간 공유는 허용되지 않습니다.  

| **데이터 그룹 이름** | **데이터 그룹에 대한 설명** |
| --- | --- |
| **비즈니스 데이터 전용** |이 그룹의 모든 서비스는 서로 간에 데이터를 공유할 수 있습니다. **비즈니스 데이터를 허용하지 않는** 데이터 그룹과는 데이터를 공유할 수 없습니다. |
| **비즈니스 데이터 허용 안됨** |이 그룹의 모든 서비스는 서로 간에 데이터를 공유할 수 있습니다. **비즈니스 데이터 전용** 데이터 그룹과 데이터를 공유할 수 없습니다. |

**참고**: 한 데이터 그룹에 서비스를 추가하면 자동으로 다른 데이터 그룹에서 해당 서비스가 제거됩니다. 예를 들어 Twitter가 현재 **비즈니스 데이터 전용** 데이터 그룹에 있고 Twitter와 비즈니스 데이터를 공유하지 않도록 하려는 경우 Twitter 서비스를 **비즈니스 데이터 허용 안됨** 데이터 그룹에 추가만 하면 됩니다. 이렇게 하면 Twitter가 **비즈니스 데이터 전용** 데이터 그룹에서 제거됩니다.

## <a name="heres-what-you-need-to-create-a-dlp"></a>DLP를 만드는 데 필요한 항목은 다음과 같습니다.
* Microsoft Flow [관리 센터](https://admin.flow.microsoft.com)에 대한 액세스  
* 환경 관리자 역할의 계정  
* 사용자가 할당된 환경  

## <a name="create-a-dlp-policy"></a>DLP 정책 만들기
다음은 DLP 정책을 만드는 방법에 대한 간략한 개요입니다.  

1. 정책 이름 지정
2. 정책을 적용할 환경 선택
3. 두 데이터 그룹 중 하나에 서비스 추가 - 특정 그룹에 있는 서비스만 데이터를 공유할 수 있으므로 작성자가 두 데이터 그룹에 있는 서비스 간에 데이터를 공유하기 위해 만든 흐름을 저장하면 모두 자동으로 차단됩니다.  

사용 가능한 DLP 정책에 대한 [자세한 연습](../prevent-data-loss.md)도 있습니다.  

## <a name="examples"></a>예제
* SharePoint, Office 365 사용자, Office 365 Outlook, 비즈니스용 OneDrive, Dynamics 365, SQL Server 및 Salesforce 간에 비즈니스 데이터를 공유하도록 흐름을 제한하는 정책을 만드는 경우 이 정책은 다음과 같을 것입니다.  
  ![](./media/learning-data-loss-prevention/a-few-business-centric-services.png)  
* 특정 환경의 구성원이 SharePoint 데이터를 공유하는 흐름을 만들지 못하도록 하는 정책을 만들려는 경우 다음과 같습니다. SharePoint는 **비즈니스 데이터 전용** 데이터 그룹의 유일한 서비스입니다.  
  ![비즈니스 데이터 전용](./media/learning-data-loss-prevention/sharepoint-only-no-sharing-guided-learning.png)

