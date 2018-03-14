---
title: "DLP(데이터 손실 방지) 정책 소개입니다. | Microsoft Docs"
description: "Microsoft Flow를 위한 데이터 손실 방지 정책 소개"
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/28/2018
ms.author: deonhe
ms.openlocfilehash: 7dbf6296383551d82d22682121210f1cd339b65e
ms.sourcegitcommit: 22a883c30c859b6193fc2a619e753d71247f5e15
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2018
---
# <a name="data-loss-prevention-dlp-policies"></a>DLP(데이터 손실 방지) 정책

이 문서에서는 정의한 커넥터 목록과 공유되지 않도록 조직 데이터를 보호할 수 있는 데이터 손실 방지 정책을 소개합니다.

## <a name="whats-a-data-loss-prevention-policy"></a>데이터 손실 방지 정책이란?

조직이 성공하려면 데이터가 중요합니다. 데이터는 의사 결정에 즉각적으로 사용할 수 있어야 하지만 액세스 권한이 없는 사용자와 공유하지 않도록 보호해야 합니다. 이 데이터를 보호하기 위해 Microsoft Flow를 통해 비즈니스 데이터에 액세스하고 공유할 수 있는 소비자 커넥터를 정의하는 정책을 만들고 적용할 수 있습니다. 데이터를 공유하는 방법을 정의하는 이러한 정책은 DLP(데이터 손실 방지) 정책으로 참조됩니다.

## <a name="why-create-a-dlp-policy"></a>DLP 정책을 만드는 이유는 무엇입니까?

비즈니스 데이터에 액세스하고 공유할 수 있는 소비자 커넥터를 명확하게 정의하는 소비자 DLP 정책을 만듭니다. 예를 들어 Microsoft Flow를 사용하는 조직은 SharePoint의 해당 비즈니스 데이터가 Twitter 피드에 자동으로 게시하지 않으려고 합니다. 이를 방지하기 위해 SharePoint 데이터가 트윗 원본으로 사용되지 않도록 DLP 정책을 만듭니다.

## <a name="benefits-of-a-dlp-policy"></a>DLP 정책의 이점

* 데이터는 조직 전체에서 일관된 방식으로 관리됩니다.
* 중요한 비즈니스 데이터를 실수로 소셜 미디어 사이트와 같은 커넥터에 게시되지 않도록 합니다.

## <a name="managing-dlp-policies"></a>DLP 정책 관리

### <a name="prerequisites-for-managing-dlp-policies"></a>DLP 정책을 관리하기 위한 필수 구성 요소

* 환경 관리자 또는 테넌트 관리자 권한

    [환경 아티클](environments-overview-admin.md)에서 사용 권한에 대해 자세히 알아볼 수 있습니다.
* [Microsoft Flow P2 라이선스](billing-questions.md)

## <a name="create-a-dlp-policy"></a>DLP 정책 만들기

### <a name="prerequisites-for-creating-dlp-policies"></a>DLP 정책을 만들기 위한 필수 구성 요소

DLP 정책을 만들려면 하나 이상의 환경에 대한 권한이 있어야 합니다.

이들 단계를 따라 회사 SharePoint의 데이터를 Twitter에 게시되고 않도록 하는 DLP 정책을 만듭니다.

1. [Microsoft Flow 관리 센터](https://admin.flow.microsoft.com)(관리 센터)에 로그인합니다.

1. 데이터 정책 탭을 선택한 다음, **새 정책** 링크를 선택합니다.

    ![로그인](./media/prevent-data-loss/create-policy-1.png)
1. **데이터 그룹** 탭을 선택합니다.

1. 페이지의 맨 위에 있는 **데이터 정책 이름**에서 *Contoso에 대한 보안 데이터 액세스*로 DLP 정책의 이름을 입력합니다.

    ![로그인](./media/prevent-data-loss/create-policy-2.png)

1. **환경** 탭에서 [환경](environments-overview-admin.md)을 선택합니다.

    > [!NOTE]
    > 환경 관리자인 경우 단일 환경에만 적용되는 정책을 만들 수 있습니다. 테넌트 관리자인 경우 환경의 조합에 적용되는 정책을 만들 수 있습니다.
    >
    >

    ![환경 선택](./media/prevent-data-loss/create-policy-3.png)

1. **데이터 그룹** 탭을 선택합니다.

    ![데이터 그룹 선택](./media/prevent-data-loss/create-policy-4.png)

1. **비즈니스 데이터만 적용** 그룹 상자 내에서 **추가** 링크를 선택합니다.

    ![추가 선택](./media/prevent-data-loss/create-policy-5.png)

1. **커넥터 추가** 페이지에서 **SharePoint** 및 **Salesforce** 커넥터를 선택합니다.

   ![커넥터 선택](./media/prevent-data-loss/create-policy-6.png)

1. **커넥터 추가** 단추를 선택하여 비즈니스 데이터를 공유할 수 있는 커넥터를 추가합니다.

1. 화면 오른쪽 위 모퉁이에서 **정책 저장**을 선택합니다.

1. 잠시 후 새 DLP 정책이 데이터 손실 방지 정책 목록에 표시됩니다.

    ![DLP 목록](./media/prevent-data-loss/create-policy-9.png)

1. **선택 사항** 전자 메일 또는 기타 통신을 팀에 보내어 새 DLP 정책을 지금 사용할 수 있음을 알립니다.

축하합니다. 이제 앱을 통해 SharePoint와 Salesforce 간에 데이터를 공유하고 다른 서비스를 사용하여 데이터 공유를 차단하는 DLP 정책을 만들었습니다.

> [!NOTE]
> 한 데이터 그룹에 서비스를 추가하면 자동으로 다른 데이터 그룹에서 해당 서비스가 제거됩니다. 예를 들어 Twitter가 현재 **비즈니스 데이터 전용** 데이터 그룹에 있고 Twitter와 비즈니스 데이터를 공유하지 않도록 하려는 경우 Twitter 서비스를 **비즈니스 데이터 허용 안됨** 데이터 그룹에 추가만 하면 됩니다. 이렇게 하면 Twitter가 비즈니스 데이터 전용 데이터 그룹에서 제거됩니다.
>
>

## <a name="data-sharing-violations"></a>데이터 공유 위반

사용자가 위에 나와 있는 DLP 정책을 만든 것으로 가정할 때 사용자가 Salesforce(**비즈니스 데이터로만 구성된** 데이터 그룹)와 Twitter(**사용할 수 없는 비즈니스 데이터로 구성된** 데이터 그룹) 간에 데이터를 공유하는 흐름을 만들 경우, 사용자가 만든 데이터 손실 방지 정책과 충돌하기 때문에 흐름이 **일시 중단**된다는 알림이 표시됩니다.

![흐름 만들기](./media/prevent-data-loss/10.png)

사용자가 일시 중단된 흐름에 대해 문의할 경우 다음 몇 가지 사항을 고려해야 합니다.

1. 이 예제에서는 SharePoint와 Twitter 간에 비즈니스 데이터를 공유할 만한 타당한 비즈니스 사유가 있는 경우 DLP 정책을 편집할 수 있습니다.

1. 사용자에게 흐름을 편집하여 DLP 정책을 준수하도록 요청합니다.

1. 사용자에게 이러한 두 엔터티 간에 데이터 공유와 관련된 결정이 내려질 때까지 일시 중단된 상태에서 흐름을 유지하도록 요청합니다.

## <a name="find-a-dlp-policy"></a>DLP 정책 찾기

### <a name="admins"></a>관리자

관리자는 관리 센터의 검색 기능을 사용하여 특정 DLP 정책을 찾을 수 있습니다.

> [!NOTE]
> 관리자는 조직의 사용자들이 흐름을 만들기 전에 정책을 인식하도록 모든 DLP 정책을 게시해야 합니다.
>
>

### <a name="makers"></a>결정권자

관리 권한이 없지만 조직의 DLP 정책에 대해 자세히 알아보려면 관리자에게 문의합니다. 또한 [결정자 환경 아티클](environments-overview-maker.md)에서도 알아볼 수 있습니다.

> [!NOTE]
> 관리자만 DLP 정책을 삭제하거나 편집할 수 있습니다.
>
>

## <a name="edit-a-dlp-policy"></a>DLP 정책 편집

1. [관리 센터](https://admin.flow.microsoft.com)를 시작합니다.

1. 시작된 관리 센터에서 왼쪽에 있는 **데이터 정책** 링크를 선택합니다.

    ![데이터 정책 선택](./media/prevent-data-loss/2.png)

1. 기존 DLP 정책의 목록을 검색하고 편집하려는 정책 옆에 있는 편집 단추를 선택합니다.

1. 정책에 필요한 사항을 변경합니다. 예를 들어, 데이터 그룹의 환경 또는 서비스를 수정할 수 있습니다.

1. **정책 저장**을 선택하여 변경 내용을 저장합니다.

> [!NOTE]
> 테넌트 관리자가 만든 DLP 정책은 환경 관리자가 볼 수 있지만 편집할 수는 없습니다.
>
>

## <a name="delete-a-dlp-policy"></a>DLP 정책 삭제

1. [관리 센터](https://admin.flow.microsoft.com)를 시작합니다.

1. 왼쪽에서 **데이터 정책** 탭을 선택합니다.

    ![데이터 정책 선택 탭](./media/prevent-data-loss/2.png)

1. 기존 DLP 정책의 목록을 검색한 다음, 삭제하려는 정책 옆에 있는 삭제 단추를 선택합니다.

    ![삭제 단추 선택](./media/prevent-data-loss/3-delete.png)

1. **삭제** 단추를 선택하여 정책을 정말로 삭제할지 여부를 확인합니다.

    ![정책을 삭제하려는지 확인](./media/prevent-data-loss/4.png)

## <a name="dlp-policy-permissions"></a>DLP 정책 권한

테넌트 및 환경 관리자만이 DLP 정책을 만들고 수정할 수 있습니다. [환경](environments-overview-admin.md) 아티클에서 권한에 대해 자세히 알아봅니다.

## <a name="next-steps"></a>다음 단계

* [환경에 대한 자세한 정보](environments-overview-admin.md)
* [Microsoft Flow에 대한 자세한 정보](getting-started.md)
* [관리 센터에 대한 자세한 정보](admin-center-introduction.md)
* [데이터 통합에 대한 자세한 정보](https://docs.microsoft.com/common-data-service/entity-reference/dynamics-365-integration)
