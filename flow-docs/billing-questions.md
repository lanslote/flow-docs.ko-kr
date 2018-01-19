---
title: "청구 및 계량 질문 | Microsoft Docs"
description: "Microsoft Flow의 청구 및 계량과 관련된 질문과 답변"
services: 
suite: flow
documentationcenter: na
author: msftman
manager: aftowen
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/21/2017
ms.author: deonhe
ms.openlocfilehash: 302dc02e24b23b68e842ead001beb77b08e12aeb
ms.sourcegitcommit: 56d69fadcbc9169feb2e1a68d9e9361709084cf4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="billing-and-metering-questions"></a>청구 및 계량 질문

이 문서에서는 Microsoft Flow의 청구 및 계량과 관련된 질문과 답변을 볼 수 있습니다.

## <a name="where-can-i-find-out-what-pricing-plans-are-available"></a>사용할 수 있는 가격 책정 플랜은 어디에서 확인할 수 있나요?

[가격 책정 페이지](https://flow.microsoft.com/pricing/)를 참조하세요.

## <a name="where-can-i-find-out-what-my-plan-is"></a>내 플랜은 어디에서 확인할 수 있나요?

[가격 책정 페이지](https://flow.microsoft.com/pricing/)를 참조하세요.

## <a name="how-do-i-switch-plans"></a>플랜을 전환하려면 어떻게 해야 하나요?

위쪽 탐색 메뉴에서 **학습** > **가격 책정**을 선택한 다음 전환하려는 계획을 선택합니다.

![유용한 정보 > 가격 책정](./media/billing-questions/learn-pricing.png)

## <a name="how-do-i-know-how-much-ive-used"></a>사용량을 어떻게 알 수 있나요?

무료 플랜 또는 평가판 플랜인 경우 위쪽 탐색 모음에서 기어 아이콘을 클릭하거나 눌러 플랜을 기준으로 현재 사용량을 표시할 수 있습니다. 

![설정 단추](./media/billing-questions/settings.png)

유료 플랜인 경우 실행은 조직의 모든 사용자에 대해 풀링됩니다. 당사는 조직 전체에서 사용 가능한 할당량 및 사용량을 표시하는 기능에 대해 최선을 다하고 있습니다.

## <a name="what-happens-if-my-usage-exceeds-the-limits"></a>내 사용량이 한도를 초과하면 어떻게 되나요?

Microsoft Flow는 흐름 실행을 제한합니다.

## <a name="where-can-i-find-more-information-regarding-the-usage-limits"></a>사용량 한도에 대한 자세한 정보는 어디서 찾을 수 있습니까?

[가격 책정 페이지](https://flow.microsoft.com/pricing/)에서 **FAQ** 섹션을 참조하세요.

## <a name="what-happens-if-i-try-to-execute-runs-too-frequently"></a>너무 자주 실행하려고 하면 어떻게 되나요?

플랜에서 흐름의 실행 빈도를 결정합니다. 예를 들어 무료 플랜인 경우 흐름이 15분 간격으로 실행할 수 있습니다. 흐름이 마지막 실행 후 15분 이내에 트리거되면 15분이 경과할 때까지 대기합니다.

## <a name="what-counts-as-a-run"></a>무엇이 실행으로 계산되나요?

자동으로 트리거되거나 수동으로 시작하는 경우 모두 흐름이 트리거될 때마다 이를 실행으로 간주합니다. 새 데이터에 대한 확인은 실행으로 계산되지 않습니다.

## <a name="are-there-differences-between-microsoft-accounts-and-work-or-school-accounts-for-billing"></a>청구에 대해 Microsoft 계정과 회사 또는 학교 계정 간에 차이가 있나요?

예. Microsoft 계정(@outlook.com 또는 @gmail.com로 끝나는 계정 등)으로 로그인하는 경우, 무료 플랜만 사용할 수 있습니다. 유료 플랜의 기능을 이용하려면 회사 또는 학교 전자 메일 주소로 로그인합니다.

## <a name="im-trying-to-upgrade-but-im-told-my-account-isnt-eligible"></a>업그레이드하는 중에 내 계정이 적합하지 않다는 메시지를 받았습니다.

업그레이드하려면 회사 또는 학교 계정을 사용하거나 [Office 365 평가판 계정](https://powerbi.microsoft.com/documentation/powerbi-admin-signing-up-for-power-bi-with-a-new-office-365-trial/)을 만듭니다.

## <a name="why-did-i-run-out-of-runs-when-my-flow-only-ran-a-few-times"></a>내 흐름을 몇 번 실행하지 않았는데 왜 실행이 다 사용된 건가요?

일부 흐름은 예상보다 더 자주 실행될 수 있습니다. 예를 들어, 관리자가 사용자에게 전자 메일을 보낼 때마다 푸시 알림을 보내는 흐름을 만들 수 있습니다. 이러한 흐름은 관리자가 전자 메일을 보냈는지 여부를 확인해야 하므로 전자 메일을 받을 때마다 흐름이 실행되어야 합니다. 이 작업은 실행으로 계산됩니다.

이 문제는 트리거에 필요한 모든 필터링을 넣어 해결할 수 있습니다. 푸시 알림 예에서 **고급 옵션** 메뉴를 확장하고 **보낸 사람** 필드에 관리자의 전자 메일 주소를 입력합니다.

## <a name="other-limits-and-caveats"></a>기타 제한 및 주의 사항

* 각 계정에 다음 수만큼 포함할 수 있습니다.
  * 250개의 흐름입니다.
  * 15개의 사용자 지정 커넥터입니다.
  * API당 연결 20개 및 총 연결 100개.
* 기본 환경에만 게이트웨이를 설치할 수 있습니다.
* Twitter와 같은 특정 외부 커넥터는 서비스 품질을 제어하기 위해 연결 제한을 구현합니다. 제한이 적용되면 흐름이 실패합니다. 흐름이 실패하는 경우, 흐름 실행 내역에서 실패한 실행의 세부 정보를 검토합니다.