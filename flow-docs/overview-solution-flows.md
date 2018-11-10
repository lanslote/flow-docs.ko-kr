---
title: 솔루션 인식 흐름 개요 | Microsoft Docs
description: 솔루션에서 흐름을 만드는 것의 이점을 알아봅니다.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/05/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 2515b64629436ccb96de497eaf928b83f281dc5f
ms.sourcegitcommit: b41b45f6fa29a22e9a9a4d3c726a2321b2ff3cbf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51025825"
---
# <a name="overview"></a>개요

[솔루션](https://docs.microsoft.com/powerapps/maker/common-data-service/solutions-overview)에서 흐름을 호스트하면 이식 가능하게 되어 흐름과 모든 구성 요소를 한 환경에서 다른 환경으로 손쉽게 이동할 수 있습니다. ISV(Independent Software Vendor)의 경우 일반적인 사용 사례는 샌드박스 환경에서 흐름을 개발한 후 해당 흐름을 테스트 환경으로 이동하는 것입니다. 테스트 후 ISV는 이러한 흐름을 구입하는 클라이언트를 위해 프로덕션 환경으로 흐름을 이동합니다. 솔루션에서 흐름을 만든 후 솔루션과 해당 콘텐츠를 이동하면 이 프로세스가 훨씬 더 간단합니다.

솔루션 내에서 만드는 흐름을 ‘솔루션 인식’ 흐름이라고 합니다.  단일 솔루션에서 여러 흐름을 추가할 수 있습니다.

> [!NOTE] 
> 비솔루션 인식 흐름(솔루션에서 만들지 않은 흐름)은 솔루션으로 이동할 수 없습니다.

## <a name="prerequisites"></a>필수 구성 요소

솔루션과 솔루션 인식 흐름을 만들려면 다음 구성 요소가 있어야 합니다.

- [앱용 Common Data Service 2.0](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)
- 버전이 9.1.0.267 이상인 환경.

  버전을 확인하려면 [Microsoft Flow 관리 센터](https://admin.flow.microsoft.com)로 이동하고 **환경**을 선택한 후 관심 있는 환경을 선택하고 **세부 정보** 탭을 선택합니다.

## <a name="create-a-solution"></a>솔루션 만들기

다음 단계에 따라 솔루션을 만듭니다.

1. [Microsoft Flow](https://flow.microsoft.com)에 로그인합니다.
1. 탐색 모음에서 **솔루션**을 선택합니다.

   ![](./media/overview-solution-flows/select-solutions-from-left-nav.png)

1. **+ 새 솔루션**을 선택합니다.

   ![](./media/overview-solution-flows/select-new-solution.png)

1. **표시 이름**, **게시자**, **버전**, **이름** 등 새 솔루션에 대해 필요한 정보를 모두 제공합니다. 솔루션에 대한 설명을 제공하는 것도 좋습니다.

   ![](./media/overview-solution-flows/new-solution.png)

1. 맨 위의 메뉴에서 **저장 후 닫기**를 선택합니다.

   ![](./media/overview-solution-flows/save-and-close-solution.png)

   새 솔루션이 다음 이미지처럼 표시됩니다.

   ![](./media/overview-solution-flows/new-solution-created.png)

   > [!TIP]
   > 새 솔루션이 표시되지 않는 경우 **솔루션**을 선택하여 솔루션 목록을 새로 고칩니다.

## <a name="learn-more"></a>자세한 정보

- [솔루션에서 흐름 만들기](./create-flow-solution.md)
- [솔루션 내보내기](./export-flow-solution.md)
- [솔루션 가져오기](./import-flow-solution.md)
- [솔루션 인식 흐름 편집](./edit-solution-aware-flow.md)
- [솔루션 인식 흐름 제거](./remove-solution-aware-flow.md)
