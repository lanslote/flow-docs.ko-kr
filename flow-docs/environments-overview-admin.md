---
title: 관리자를 위한 환경 개요 | Microsoft Docs
description: Microsoft Flow에서 환경 사용, 만들기 및 관리
services: ''
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2017
ms.author: sunayv
ms.openlocfilehash: cf1a618b9e0ed76147eb4ede2aed42111c66b4a5
ms.sourcegitcommit: d00c10759d4afb54517a0b1032f8d0a509006d5b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="using-environments-within-microsoft-flow"></a>Microsoft Flow 내에서 환경 사용

## <a name="benefits"></a>이점

환경은 다음과 같은 이점을 제공합니다.

* **데이터 지역성**: 환경은 다양한 지역에서 만들 수 있으며 해당 지리적 위치에 바인딩됩니다. 환경에서 흐름을 만들면 이 흐름은 해당 지리적 위치의 모든 데이터 센터에 라우팅됩니다. 이는 성능상의 이점도 제공합니다.

    사용자가 유럽에 있는 경우 유럽 지역에서 환경을 만들어 사용합니다. 사용자가 미국에 있는 경우 미국에서 환경을 만들어 사용합니다. 

    > [!IMPORTANT]
    > 환경을 삭제하면 이 환경 내의 모든 흐름도 삭제됩니다. 이 작업은 연결, 게이트웨이, PowerApps 등을 포함하여 해당 환경에서 사용자가 만든 모든 항목에 적용됩니다.
* **데이터 손실 방지**: 관리자로서 내부 위치에서 데이터를 가져오는 흐름을 원하지 않고(예: ‘비즈니스용 OneDrive’ 또는 급여 정보가 포함된 SharePoint 목록) 해당 데이터를 공개적으로 게시합니다(예: *Twitter*). 데이터 손실 방지를 사용하여 Microsoft Flow 배포 내에서 데이터를 공유할 수 있는 서비스를 제어합니다.

    예를 들어, *SharePoint* 및 ‘비즈니스용 OneDrive’ 서비스를 비즈니스 데이터 전용 정책에 추가할 수 있습니다. 이 환경에서 만든 모든 흐름은 *SharePoint* 및 ‘비즈니스용 OneDrive’ 서비스를 사용할 수 있습니다. 그러나 비즈니스 데이터 전용 정책에 포함되지 않는 기타 서비스에서는 데이터를 공유할 수 없습니다.

  > [!NOTE]
  > 데이터 손실 방지는 P2 라이선스를 비롯한 일부 라이선스 SKU에서 사용할 수 있습니다.

* **모든 리소스에 대한 격리 경계**: 모든 흐름, 게이트웨이, 연결, 사용자 지정 커넥터 등이 특정 환경에 있습니다. 다른 환경에는 존재하지 않습니다.
* **Common Data Service**: 서비스에 데이터를 삽입하는 흐름을 만들려는 경우 다음과 같은 옵션이 있습니다.

  * Excel 파일에 데이터를 삽입하고 OneDrive와 같은 클라우드 저장소 계정에 Excel 파일을 저장합니다.
  * SQL Database를 만들고 그 안에 데이터를 저장합니다.
  * Common Data Service를 사용하여 데이터를 저장합니다.

    모든 환경은 Common Data Service에서 흐름을 위해 최대 하나의 데이터베이스를 가질 수 있습니다. Common Data Service에 대한 액세스 권한은 구입한 라이선스에 따라 다르며, Common Data Service는 체험 라이선스에 포함되지 않습니다.

## <a name="limitations"></a>제한 사항

환경은 많은 혜택을 제공하지만 새로운 제한 사항이 생겨날 수 있습니다. 환경이 격리 경계라는 사실은 환경 ‘간에’ 리소스를 참조하는 리소스는 가질 수 없다는 의미입니다. 예를 들어, 한 환경에서 사용자 지정 커넥터를 만들고 다른 환경에서 이 사용자 지정 커넥터를 사용하는 흐름을 만들 수 없습니다.

## <a name="use-the-default-environment"></a>기본 환경 사용

**기본** 환경은 모든 사용자가 공유하며 모든 사용자는 **기본** 환경에서 흐름을 만들 수 있습니다.

> [!TIP]
> 미리 보기 사용자인 경우 모든 기존 흐름이 기본 환경에 있습니다. 미리 보기 사용자는 GA(일반 공급) 전에 Microsoft Flow를 사용 중이었던 사용자입니다.

## <a name="the-admin-center"></a>관리 센터

관리자는 관리 센터를 사용하여 환경을 만들고 관리합니다. 다음과 같은 두 가지 방법으로 관리 센터를 열 수 있습니다.

### <a name="option-1-select-settings"></a>옵션 1: 설정 선택

1. [flow.microsoft.com](https://flow.microsoft.com)에 로그인합니다.
1. 설정 기어를 선택하고 목록에서 **관리 센터**를 선택합니다.

   ![설정 및 관리자 포털](./media/environments-overview-admin/settings.png)
1. 관리자 센터를 엽니다.

### <a name="option-2-open-adminflowmicrosoftcom"></a>옵션 2: admin.flow.microsoft.com 열기

[admin.flow.microsoft.com](https://admin.flow.microsoft.com)으로 이동하고 회사 계정으로 로그인합니다.

## <a name="create-an-environment"></a>환경 만들기

1. [Microsoft Flow 관리자 센터](https://admin.flow.microsoft.com)에서 **환경**을 선택합니다. 모든 기존 환경: ![환경](./media/environments-overview-admin/environments-list.png)이 표시됩니다.
2. **새 환경**을 선택하고 필요한 정보를 제공합니다.


   |     속성     |                                                 설명                                                 |
   |------------------|-------------------------------------------------------------------------------------------------------------|
   | 환경 이름 |              환경의 이름을 `Human Resources` 또는 `Europe flows` 등과 같이 입력합니다.              |
   |      지역      | 사용자의 환경을 호스트할 위치를 선택합니다. 최고의 성능을 위해 사용자와 가장 가까운 지역을 사용합니다. |
   | 환경 유형 |                  라이선스에 따라 환경 유형(프로덕션 또는 평가판)을 선택합니다.                   |

     ![환경 설정](./media/environments-overview-admin/new-environment-dialog.png)
3. **환경 만들기**를 클릭합니다.
4. 이제 **데이터베이스 만들기** 또는 **건너뛰기** 옵션이 있습니다.
5. **데이터베이스 만들기**를 선택하면 데이터베이스에 대한 **통화** 및 **언어**를 입력하라는 메시지가 표시됩니다. 샘플 앱 및 데이터 배포를 선택할 수도 있습니다.

   ![데이터베이스 구성 설정](./media/environments-overview-admin/create-database-dialog2.png)


이제 환경에 사용자를 추가할 수 있습니다.

## <a name="manage-your-existing-environments"></a>기존 환경 관리

1. [Microsoft Flow 관리자 센터](https://admin.flow.microsoft.com)에서 **환경**을 선택합니다.

   ![환경 메뉴 항목](./media/environments-overview-admin/select-environments.png)
1. 속성을 열 환경을 선택합니다.
1. **세부 정보** 탭을 사용하여 환경을 만든 사람, 지리적 위치 등을 비롯하여 환경에 대한 추가 정보를 확인합니다.

   ![세부 정보 탭](./media/environments-overview-admin/open-environment.png)
1. **보안**을 선택합니다.

    이전 단계에서 **데이터베이스 만들기**를 선택하지 않은 경우 **환경 역할**에 **환경 관리자**와 **환경 작성자**라는 두 옵션이 있습니다.

    ![관리자 역할](./media/environments-overview-admin/environment-roles.png)

    **작성자**는 환경의 흐름, 데이터 연결, 게이트웨이 등의 새로운 리소스를 만들 수 있습니다.

   > [!NOTE]
   > 사용자는 환경의 리소스를 ‘편집’하기 위해 **작성자**가 될 필요는 없습니다. 각 작성자는 환경 작성자가 아닌 사용자에게 권한을 부여하여 자신의 리소스를 편집할 수 있는 사용자를 결정합니다.
   > 
   > 

    **관리자**는 데이터 손실 방지 정책을 만들고 환경 만들기, 환경에 사용자 추가, 관리자/작성자 권한 할당 등의 기타 관리 작업을 수행할 수 있습니다.

   1. **환경 작성자** 역할을 선택한 다음, **사용자**: ![작성자 역할](./media/environments-overview-admin/add-environment-maker.png)을 선택합니다.
   1. **작성자**역할을 부여하려는 이름, 메일 주소 또는 사용자 그룹을 입력합니다.
   1. **저장**을 선택합니다.

1. **보안** 내에서 **사용자 역할**을 선택합니다.

    ![사용자 역할](./media/environments-overview-admin/security-user-roles.png)

    역할을 편집하거나 삭제하는 옵션을 비롯하여 모든 기존 역할이 나열됩니다.

    **새 역할**을 선택하여 새 역할을 만듭니다.
1. **보안** 내에서 **권한 집합**을 선택합니다.

    ![권한 설정](./media/environments-overview-admin/security-permission-set.png)

    기존의 모든 권한 집합 및 옵션을 보고 역할을 편집하거나 삭제할 수 있습니다.

    **새 권한 집합**을 선택하여 새 권한 집합을 만듭니다.
1. 데이터를 저장하기 위해 **데이터베이스 만들기**를 선택하지 않은 경우 이 데이터베이스는 Common Data Service의 일부가 됩니다. **보안** 탭을 클릭하면 역할 기반 보안을 적용할 수 있는 **Dynamics 365 인스턴스 관리 센터**로 이동하라는 메시지가 표시됩니다.
![Dynamics 보안 설정](./media/environments-overview-admin/Security-Link-D365.png)

1. 환경/인스턴스의 사용자 목록에서 사용자를 선택합니다.
  ![Dynamics 보안 설정](./media/environments-overview-admin/D365-Select-User.png)

1. 사용자에게 역할을 할당합니다.

   ![사용자에게 역할 할당](./media/environments-overview-admin/D365-Assign-Role.png)

> [!NOTE]
> 이러한 환경 역할에 할당된 사용자 또는 그룹은 환경의 데이터베이스(존재하는 경우)에 대한 액세스 권한이 자동으로 부여되지 않으며 데이터베이스 소유자가 별도로 액세스 권한을 부여해야 합니다. 
>
>

### <a name="database-security"></a>데이터베이스 보안
데이터베이스 스키마 생성 및 수정 기능과 환경에 프로비전된 데이터베이스 내에 저장된 데이터에 연결하는 기능은 데이터베이스의 사용자 역할 및 권한 집합으로 제어됩니다. **보안** 탭의 **사용자 역할** 및 **권한 집합** 섹션에서 환경의 데이터베이스에 대한 사용자 역할 및 권한 집합을 관리할 수 있습니다. 

   ![사용자에게 역할 할당](./media/environments-overview-admin/D365-Assign-Role.png)

## <a name="frequently-asked-questions"></a>질문과 대답

### <a name="can-i-move-a-flow-between-environments"></a>환경 간에 흐름을 이동할 수 있나요?

예, 흐름은 한 환경에서 내보내고 다른 환경으로 가져올 수 있습니다.

### <a name="which-license-includes-the-common-data-service"></a>Common Data Service를 포함하는 라이선스는 무엇입니까?

Microsoft PowerApps 플랜 2에만 Common Data Service와 데이터베이스를 만들 수 있는 권한이 있습니다. 그러나 모든 유료 플랜(Microsoft Flow 플랜 1, 2 및 Microsoft PowerApps 플랜 1, 2)에는 Common Data Service를 사용할 수 있는 권한이 있습니다.

[Microsoft Flow 가격 책정](https://flow.microsoft.com/pricing/) 페이지를 방문하여 적절한 요금제를 선택하세요.

청구에 대해 자주 묻는 질문과 대답은 [청구 관련 질문](billing-questions.md) 문서를 참조하세요.

### <a name="can-the-common-data-service-be-used-outside-of-an-environment"></a>환경 외부에서 Common Data Service를 사용할 수 있습니까?

아니요. Common Data Service를 사용하려면 환경이 필요합니다. 그것에 관해 [자세히 알아봅니다](common-data-model-intro.md).

### <a name="what-regions-include-microsoft-flow"></a>Microsoft Flow를 포함하는 지역은 어디입니까?

Microsoft Flow는 Office 365를 지원하는 대부분의 지역을 지원합니다. 자세한 내용은 [지역 개요](regions-overview.md)를 참조하세요.

### <a name="whats-needed-to-create-my-own-custom-environment"></a>나만의 사용자 지정 환경을 만들려면 무엇이 필요하나요?

Microsoft Flow 요금제 2 라이선스가 있는 모든 사용자는 자신만의 환경을 만들 수 있습니다. 모든 Microsoft Flow 사용자는 요금제 2 관리자가 만든 환경을 사용할 수 있지만 자신만의 환경을 만들 수는 없습니다.
