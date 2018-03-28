---
title: 릴리스 정보 | Microsoft Docs
description: 일반적인 문제 및 Microsoft Flow 릴리스의 새로운 기능
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/12/2018
ms.author: stepsic
ms.openlocfilehash: 4d88b0baee16fb0aeea24e2f2c84806595f21662
ms.sourcegitcommit: 753d52fa29d04f2eb774f7bec29b8d5793ccbb93
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2018
---
# <a name="release-notes"></a>릴리스 정보
## <a name="top-questions"></a>주요 질문
1. 내 흐름이 실패했습니다. 어떻게 해결해야 하나요?
   
   1. 오류를 식별합니다. 웹 포털 위쪽의 알림 아이콘으로 이동하거나 모바일 앱에서 **작업** 탭을 선택하여 시작합니다. 여기서 흐름이 표시되며 해당 흐름을 선택할 수 있습니다.
   2. 이제 흐름 정보를 자세히 볼 수 있습니다. 빨간색 느낌표(!) 아이콘이 있는 단계를 찾습니다. 여기서 흐름에 대한 오류 메시지가 표시됩니다.
   3. 오류 메시지에 따라 흐름을 **편집**하고 수정할 수 있어야 합니다. [일반적인 흐름 오류를 수정하는 방법에 대해 자세히 알아보세요](fix-flow-failures.md).
2. 고급 조건 또는 식은 어떻게 사용합니까?
   
   * [조건을 추가하는 방법](add-condition.md)에 대해 자세히 알아보세요.
   * 흐름의 여러 사례를 보려는 경우 기존 조건 내에서 **조건 추가**를 클릭하거나 누릅니다.
   * [Logic Apps에서 함수](https://docs.microsoft.com/rest/api/logic/definition-language)를 참조하여 고급 식을 만듭니다.
3. Office 365 라이선스는 어떻게 작동합니까?
   
   * Office 365 사용자인 경우 Office 365용 Microsoft Flow 요금제를 통해 모든 액세스 권한을 얻습니다. 자세한 내용은 [Microsoft Flow에 대한 가격 책정 플랜](https://flow.microsoft.com/pricing/)을 참조하세요.
   * 관리자인 경우 Office 365를 비롯하여 [Microsoft Flow의 라이선스](organization-q-and-a.md)에 대한 정보를 참조하세요.

## <a name="known-issues-and-resolutions"></a>알려진 문제 및 해결 방법
1. 내 사이트에 있는 SharePoint 목록 및 *사용자 지정 목록* 형식이 아닌 SharePoint 목록은 지원되지 않습니다. 이 문제를 해결하려면 표준 SharePoint 사이트에서 사용자 지정 목록을 만듭니다.
2. 흐름은 SharePoint 목록의 분류 필드에 쓸 수 없습니다. 이 문제가 해결될 때까지 간단한 문자열 필드를 사용하는 것이 좋습니다.
3. 선택한 폴더의 중첩된 폴더 내에 추가되는 파일에 대해 파일 트리거가 발생하지 않습니다.

## <a name="whats-new"></a>새로운 기능

### <a name="release-2018-02-09"></a>릴리스 2018-02-09

- **게이트웨이 고가용성** - 온-프레미스 데이터 게이트웨이에 대해 가용성이 뛰어난 클러스터를 만들어 단일 컴퓨터가 작동을 멈출 때 연결을 유지합니다.
- **향상된 Apply to each(각각에 적용)** - Flow 요금제 1 또는 Flow 요금제 2를 사용하는 경우 Apply to each(각각에 적용) 루프에서 프로세스가 단일 실행으로 최대 100,000개의 항목을 처리하고 50개 작업을 나란히 처리합니다. 

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/gateway-ha-increased-apply-to-each/).

### <a name="release-2018-01-29"></a>릴리스 2018-01-29

- **Microsoft Teams 내의 흐름** - Teams에서 흐름을 만들고 관리하고, 받은 승인과 보낸 승인을 검토하고, Teams 데스크톱 앱 또는 teams.microsoft.com에서 바로 흐름을 시작할 수 있습니다. [자세한 정보](https://flow.microsoft.com/blog/microsoft-flow-in-microsoft-teams/)
- **공유 편집 알림** - 사용자가 소유한 흐름을 동료가 변경할 때마다 누가 어떤 흐름을 변경했는지를 알려주는 메일 알림을 받습니다.
- **새 식** - 새로운 두 식이 추가되었습니다. 하나는 URL 구문 분석 식이고 다른 하나는 JSON 개체를 사용하는 식입니다.
- **새로운 세 커넥터** - 이번 주 새로운 두 Plumsail 커넥터(Plumsail SP, Plumsail Forms)와 kintone에 대한 새 커넥터가 있습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/shared-notifications-and-expressions/).

### <a name="release-2018-01-17"></a>릴리스 2018-01-17

- **Office 365 프로필 정보** - 사용자 프로필 및 사진과 작동하는 Office 365 사용자 커넥터에 새로운 동작을 추가했습니다.
- **문자열 변수에 추가** - 루프 내의 문자열에 추가하여 테이블 또는 기타 목록을 빌드할 수 있습니다.
- **Infobip 커넥터** - Infobip은 음성 호출 및 인바운드 SMS에 대한 트리거 등 엔터프라이즈급 통신을 사용하는 서비스입니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/o365-profile-infobip/).

### <a name="release-2017-12-20"></a>릴리스 2017-12-20

이제 모든 Microsoft Flow 지역에서 Microsoft Flow Analytics를 사용하여 사용자 환경 내에서 실행 중인 흐름의 상태에 대한 자세한 정보를 얻을 수 있습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/announcing-microsoft-flow-analytics/).


### <a name="release-2017-12-14"></a>릴리스 2017-12-14

- **Outlook 커넥터 기능 향상** - 전자 메일을 ".eml" 파일로 저장하고, 일정 초대에 자동으로 응답하고, 전자 메일 스레드에 본인이 언급된 경우 흐름을 트리거할 수 있습니다.
- **연결 기능 향상** - Microsoft Flow는 가장 최근에 사용된 연결을 기억하고 새로 추가된 커넥터를 모두 보여 줍니다.
- **5개의 새 커넥터** - Azure Container Instances, Azure Kusto, Metatask, Microsoft To-Do 및 Plumsail 문서가 추가되었습니다.
- **HTTP 기능 향상** - 이제 HTTP 동작이 청크 분할 인코딩을 지원합니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/outlook-connector-more/).

### <a name="release-2017-12-05"></a>릴리스 2017-12-05

이제 모든 지역에서 Microsoft Flow 시작 패널을 사용할 수 있습니다. 이 패널을 사용하면 SharePoint 목록 또는 문서 라이브러리 내에서 흐름을 실행할 때 흐름에 값을 추가할 수 있습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/introducing-flow-launch-panel-in-sharepoint-lists-and-libraries/).


### <a name="release-2017-11-28"></a>릴리스 2017-11-28

- **관리되는 메타데이터** - 관리되는 메타데이터(즉, 분류) 유형을 사용하는 SharePoint의 열에서 데이터를 읽거나 씁니다.
- **배열에 추가** - 배열 변수에 추가라는 새로운 작업을 사용하여 배열 끝에 항목을 추가합니다.
- **Tago** - 외부 데이터와 전자 장치의 간편한 연결을 지원하여 문맥 분석을 사용한 더 스마트한 결정을 이끄는 Tago에 대한 새로운 커넥터입니다.
- **iPhone X** - iPhone X에서 전체 화면을 사용하고, 이미지 업로드 속도가 개선된 새로운 버전의 Microsoft Flow 앱입니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/managed-metadata-tago/).

### <a name="release-2017-11-09"></a>릴리스 2017-11-09

- **OneDrive for Business 통합** - 이제 선택한 파일 또는 폴더에 대한 흐름을 만들거나 트리거할 수 있는 [OneDrive for Business 내부의 흐름 단추](https://flow.microsoft.com/blog/microsoft-flow-integration-in-one-drive-for-business-and-new-connector-actions/)가 있습니다.
- **Planner 트리거** - 새 작업이 생성된 경우, 새 작업이 할당된 경우 또는 작업이 완료된 경우 흐름을 시작합니다.
- **SharePoint 첨부 파일** - SharePoint 목록 항목에서 첨부 파일 관련 작업을 수행합니다(첨부 파일 나열, 다운로드, 추가 또는 삭제).
- **흐름 관리 커넥터** - 사용자 환경에서 다른 흐름의 관리를 자동화하는 흐름을 만듭니다(예: 자동으로 흐름에 권한 추가).
- **4개의 새 커넥터** - Azure Custom Vision Service, D&B Optimizer, Enadoc 및 Derdak SIGNL4가 추가되었습니다. 
- **추가 커넥터 작업** - SQL 쿼리를 실행하고, 전자 메일 트리거를 더 빨리 가져오고, Azure AD에서 HTTP와 관련한 모든 메서드를 사용할 수 있습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/planner-triggers-connector-improvements/).

### <a name="release-2017-11-02"></a>릴리스 2017-11-02

- **감사 로깅** - 이제 Office 365 Security & Compliance Center에서 모든 테넌트의 Microsoft Flow 감사 이벤트를 사용할 수 있습니다.
- **흐름 위젯 수정** - Flow 모바일 앱의 위젯에서 단추가 로드되지 않게 하는 문제가 해결되었습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/security-and-compliance-center/).

### <a name="release-2017-10-19"></a>릴리스 2017-10-19

- **각각에 중첩 적용** - 각 작업에 적용을 추가하고, 각 컨테이너 작업에 다른 작업을 필터링하고 선택할 수 있습니다.
- **날짜 시간 작업** - 현지 시간 가져오기, 시간 더하기/빼기/서식 지정을 위한 새로운 작업입니다.
- **4개의 새 커넥터** - Content Moderator, Docparser, Microsoft Kaizala 및 Pitney Bowes Data Validation이 추가되었습니다.
- **향상된 연결 환경** - 연결이 끊긴 경우 흐름 포털에 알림이 표시되고, 더욱 풍부한 연결 세부 정보가 제공됩니다.
- **이동 중 컬렉션** - [이동 중인 작업자](https://flow.microsoft.com/collections/onthego/)를 위한 새로운 템플릿 컬렉션입니다.
- **전자 메일 주소 단추 입력** - 단추를 실행하는 사용자의 전자 메일 주소를 수집합니다.
- **파일 단추 입력** - 단추를 실행하는 사용자의 사진과 같은 업로드된 파일을 가져옵니다.
- **최초 실행 및 자동 로그인** - 모바일 앱의 최초 실행 환경이 개선되었습니다(자동 로그인 포함).
- **더 빠른 Microsoft Forms 트리거** - Forms가 전보다 훨씬 더 빨리 흐름을 트리거합니다(이전에는 한 시간에 한 번).
- **세션 전체에 적용되는 단추 입력** - 휴대폰에서 트리거된 단추가 이전 입력을 기억합니다.
- **모바일 활동 피드** - 보다 자세한 실행 요약 및 문제 해결 세부 정보를 포함하도록 활동 피드가 개선되었습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/nested-apply-to-each/).

### <a name="release-2017-10-03"></a>릴리스 2017-10-03

- **모든 사람이 승인해야 함** - 승인 요청을 여러 사람에게 전송하여 요청을 받은 모든 사람에게 승인을 받아야 합니다.
- **새로운 비즈니스용 OneDrive 작업** - 비즈니스용 OneDrive에 저장된 파일에 대한 PDF를 생성할 수 있고, 그 밖에 새로운 작업 네 가지가 지원됩니다.
- **Apache Impala 커넥터** - Apache Impala(개발 중)는 오픈 소스이며, Apache Hadoop용 네이티브 분석 데이터베이스입니다.
- **흐름 설명 추가** - 공동 작업자가 흐름 작업에 대한 요약을 볼 수 있도록 흐름을 공유할 때 흐름 설명을 제공합니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/all-must-approve-and-onedrive/).

### <a name="release-2017-09-25---q3-update-for-microsoft-flow"></a>릴리스 2017-09-25 - Microsoft Flow에 대한 3분기 업데이트

- **첫 번째 릴리스의 더 긴밀한 SharePoint 통합** - 검토 흐름과 흐름 패널에 첫 번째 릴리스 테넌트에 대한 흐름을 실행할 때 입력을 수집하기 위한 새로운 기본 제공 보내기 기능이 있습니다.
- **고객 관계용 Dynamics 365** - 이제 고객 관계용 Dynamics 365의 UI에 흐름이 통합됩니다.
- **Microsoft Trust Center** - 흐름이 Microsoft Trust Center에 나열되고, HIPAA, ISO 및 SOC와 같은 인증이 표시됩니다.
- **사용 현황 분석** - 모든 흐름에는 기본 사용 현황 분석을 제공하는 Power BI 대시보드가 포함되어 있습니다.
- **첫 번째 릴리스의 감사 로깅** - Office 365 Security and Compliance Center에 첫 번째 릴리스 테넌트에 대한 모든 흐름 관리 이벤트가 로깅됩니다.
- **6개의 새로운 커넥터** - LinkedIn, Office 365 그룹, 비즈니스용 Skype, Adobe Sign, Bizzy 및 Azure Log Analytics Data Collection이 추가되었습니다.
- **SQL 트리거** - SQL 테이블에서 새 행이 추가되거나 행이 업데이트될 때 흐름을 실행합니다.
- **온-프레미스 사용자 지정 커넥터** - 사용자 지정 커넥터는 이제 온-프레미스 데이터 게이트웨이를 사용하여 네트워크의 내부 끝점에 연결할 수 있습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/q3-2017-update/).

### <a name="release-2017-09-21"></a>릴리스 2017-09-21

- **흐름 기록 다운로드** - 흐름의 실행 기록을 Excel에서 열리는 CSV 파일로 다운로드합니다.
- **고급 되풀이** - 흐름을 트리거하는 되풀이 예약을 작성합니다(예: 평일에만 트리거).
- **IntelliSense** - 식에 입력할 때 IntelliSense가 매개 변수를 제안합니다.
- **4개의 새로운 커넥터** - Azure AD HTTP 서비스, Amazon Redshift, Azure Event Grid Publish 및 FlowForma에 대한 커넥터가 추가되었습니다.
- **링크 공유** - OneDrive 파일 또는 Azure Storage Blob에 대한 공유 가능한 링크를 생성하는 새로운 작업입니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/download-history-recurrence/).


### <a name="release-2017-08-25"></a>릴리스 2017-08-25
* **SharePoint에 대한 문서 속성 및 추가 사항** - [SharePoint 문서 라이브러리 속성을 읽고 설정하며](https://flow.microsoft.com/blog/support-for-sharepoint-document-library-properties/), 링크와 같은 SharePoint 항목에 대한 추가 필드를 사용합니다.
* **흐름 컬렉션** - 흐름 컬렉션은 역할 또는 세로로 구성된 템플릿 컬렉션 집합입니다.
* **단추 재공유** - 동료와 단추를 재공유하면 다른 사람과도 재공유할 수 있습니다.
* **단추에서 목록 수집** - 단추를 탭할 때 사용자가 선택할 옵션 드롭다운을 정의합니다.
* **7개의 새 커넥터** - AWeber, Azure Log Analytics, Azure Tables, DocFusion365, Azure Event Grid, Azure Event Hubs 및 StaffHub. 
* **Slack 및 MySQL의 향상된 기능** - Slack에서 채널을 만들거나 조인하고 MySQL 데이터베이스에 쓸 수 있습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/button-updates-seven-connectors/).

### <a name="release-2017-08-02"></a>릴리스 2017-08-02
* **Person, Choice 및 Lookup 필드에 쓰기** ‑ SharePoint의 항목 만들기 및 항목 업데이트는 이제 Person, Choice 및 Lookup 필드를 설정하는 [기능을 지원합니다](https://flow.microsoft.com/blog/setting-sharepoint-s-person-choice-and-lookup-fields/).
* **더 많은 작업 설정** ‑ 다시 시도 정책 및 페이지 매김을 구성하는 것을 비롯한 트리거 및 작업 실행 방법을 더 많이 제어할 수 있습니다.
* **4개의 새 커넥터** -이제 Azure File Storage, Elastic Forms, Plivo 및 Video Indexer를 사용할 수 있습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/four-connector-action-settings/).

### <a name="release-2017-07-27---q2-update-for-microsoft-flow"></a>릴리스 2017-07-27 - Microsoft Flow에 대한 2분기 업데이트
* **가져오기 및 내보내기** - 여러 환경에 걸친 또는 테스트에서 제작으로의 내보내기 및 가져오기 흐름 솔루션. 
* **작업에서 식 사용하기** - 어떤 작업에서든 식을 입력하고 사용 방법을 설명하는 인라인 도움을 받으십시오.
* **Azure Logic Apps로 축적** - 흐름을 Visual Studio나 Azure Portal을 통해 배포할 수 있는 Azure Logic Apps 리소스로 저장합니다.
* **관리자 가시성** - 흐름이 어디에 어떻게 사용되는지 정확히 이해하기 위해 Microsoft Flow 사용법을 테넌트에 다운로드합니다.
* **Dynamics 365에서의 흐름** - 작업 및 금융, Business Edition에 대해 흐름을 Dynamics 365 내에서 사용합니다.
* **시나리오를 보다 쉽게 찾기** - 커넥터가 수행할 수 있는 모든 것을 검색한 다음 흐름을 빌드하기 위한 출발점으로 트리거를 사용합니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/q2-2017-update/).

### <a name="release-2017-07-13"></a>릴리스 2017-07-13
* **향상된 템플릿 게시** - 만든 모든 흐름을 그 범주와 함께 공용 갤러리에 게시합니다.
* **Outlook 일정에서 이벤트 가져오기** - 달력에서 두 시간 사이의 모든 이벤트를 반환하는 새 작업.
* **새 모바일 기능** - 흐름을 요청시 실행하고 모바일 앱에서 실패한 실행을 다시 제출합니다.
* **사용자 지정 커넥터에서 동적 드롭다운** - 동적 드롭다운을 빌드하고, 트리거를 폴링한 후 사용자 지정 커넥터를 테스트합니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/publishing-and-custom-connectors/).

### <a name="release-2017-06-28"></a>릴리스 2017-06-28
* **언어 설정 업데이트** - 설정 메뉴를 통해 Microsoft Flow에서 사용하는 언어 및 영역을 사용자 지정할 수 있습니다.
* **5개의 새 커넥터** - Adobe Creative Cloud, Bing Maps, Bing Search, JotForm 및 Freshservice에 대한 지원이 추가되었습니다.
* **시간 제한 구성** - 승인처럼 오래 실행되는 작업이 "시간 제한"으로 처리되고 흐름이 계속 진행되는 시간을 변경합니다.
* **Outlook에 승인에 대한 주석 포함하기** - 승인 요청을 받을 때 Outlook에서 벗어나지 않고도 의견을 제공할 수 있습니다.
* **사용자 지정 커넥터 브랜드 색** - 이제 배경에 사용될 사용자 지정 커넥터의 색을 입력할 수 있습니다.
* **팀 흐름에 대한 다른 이름으로 저장** - 팀 흐름을 포함하여 흐름의 복사본을 만듭니다.
* **흐름 정보 삭제** - 흐름을 삭제하면 해당 흐름에 대해 보류 중인 모든 실행 목록이 표시됩니다.
* **커넥터 페이지에서 필터링** - 커넥터 페이지에서 원하는 커넥터를 검색하고 커넥터 유형으로 필터링합니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/language-settings-3-connectors/).

### <a name="release-2017-06-19"></a>릴리스 2017-06-19
이제 사용자가 보낸 모든 보류 중인 승인 요청의 상태를 볼 수 있습니다. 뿐만 아니라 모바일 장치에서 바로 모든 보류 중인 승인을 찾아보고 작업할 수 있습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/sent-requests-flow-mobile/).

### <a name="release-2017-06-15"></a>릴리스 2017-06-15
* **콘텐츠 변환** - HTML 콘텐츠를 일반 텍스트로 변환할 수 있는 새 커넥터는 HTML 형식의 전자 메일을 처리하는 데 유용합니다.
* **3개의 새 데이터베이스 커넥터** - MySQL, PostgreSQL 및 Teradata에 대한 읽기 전용 지원이 추가되었습니다. 이러한 커넥터는 온-프레미스 데이터 게이트웨이를 통해 연결합니다.
* **3개의 다른 커넥터** - Azure Application Insights, Calendly 및 팀 프로젝트에 연결합니다.
* **개선된 오류 처리 시각화** - 이제 오류 후 실행되는 단계에 빨간색 점선 화살표가 표시되므로 쉽게 식별할 수 있습니다.
* **실행 세부 정보 창** - 이제 흐름이 실패하면 오른쪽 창에 흐름을 수정하는 방법에 대한 유용한 단계가 표시됩니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/seven-connectors-and-html/).

### <a name="release-2017-06-04"></a>릴리스 2017-06-04
* **Windows Phone 일반 공급** - [Microsoft Flow 모바일 앱이 Windows Phone에 일반 공급됩니다](https://flow.microsoft.com/blog/announcing-flow-windows-phone-app/).
* **흐름 오류에 대한 전자 메일** - 흐름에 오류가 발생하면 전자 메일을 통해 알림을 받습니다. 이러한 오류 전자 메일은 일주일에 한 번만 전송되며, 사용자가 켜거나 끌 수 있습니다.
* **테이블에 대한 작업 선택** - 새로운 선택 작업을 사용하여 테이블에 포함될 열 집합을 변경할 수 있습니다.
* **Microsoft Forms 커넥터** - Office 365 Education에 새로 포함된 Microsoft Forms는 교사와 학생이 사용자 지정 퀴즈, 설문 조사, 질문, 등록 등을 쉽고 빠르게 만들 수 있게 해줍니다.
* **Office 365 Enterprise K1 계획** - PowerApps 및 Microsoft Flow는 이제 Office 365 Enterprise K1 계획에 포함되며 특정 할당량이 있습니다.
* **더욱 쉬워진 HTTP 헤더** - 선택 작업처럼 작업에서 텍스트 상자에 정보를 입력하여 헤더 이름 및 헤더 값을 제공할 수 있습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/microsoft-forms-tables-flow-failures/).

### <a name="release-2017-05-23"></a>릴리스 2017-05-23
* **Microsoft Teams 커넥터** - [Microsoft Teams](https://flow.microsoft.com/blog/introducing-the-microsoft-teams-connector-for-flow/)는 Office 365의 채팅 기반 작업 영역으로, 팀이 필요로 하는 도구와 함께 사람, 대화 및 콘텐츠를 결합하여 공동 작업을 더 쉽게 할 수 있습니다.
* **iOS 및 Android의 위젯** - Microsoft Flow 위젯은 단추 바로 가기로, 홈 화면에서 바로 단추를 빠르고 쉽게 트리거할 수 있습니다.
* **"오류 처리" 단계 만들기** - 작업이 실패한 후 실행하는 하나 이상의 단계를 정의합니다. 예를 들어, 흐름이 Dynamics 365에서 레코드를 만들지 못하는 경우 즉시 알림을 받습니다.
* **정수 및 부동 소수점 변수** - 특정 논리 집합의 실행 횟수를 계산하기 위해 흐름 실행 내에서 카운터를 초기화하고 증가시키거나 감소시킵니다.
* **흐름 세부 정보 페이지** - **내 흐름** 목록에서 흐름을 선택하면 누가 액세스 및 실행 기록을 가지고 있는지 등 해당 흐름에 대한 세부 정보가 포함된 페이지가 표시됩니다.
* **관리자에 대한 흐름 실행 할당량** - 관리자는 이제 일반적인 회사 실행 할당량에 대해 한 조직 내에서 흐름 실행 사용량을 모니터링하고 어떤 라이선스가 그 할당량에 기여하는지 파악하기 위해 할당량 분석을 가져올 수 있습니다.
* **HTTP 요청 트리거 개선** - 다른 HTTP 메서드를 사용하며, 요청 트리거에 대한 경로 세그먼트를 추가합니다.
* **두 파트너 커넥터** - Microsoft Flow는 이제 전자 메일을 구문 분석 서비스인 Parserr와 온라인 양식 서비스인 Cognito Forms에 연결할 수 있습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/error-handling/).

### <a name="release-2017-05-12"></a>릴리스 2017-05-12
* **SharePoint 문서 라이브러리 통합** - 예를 들어, 문서 라이브러리의 모든 파일을 선택하고 승인을 얻기 위해 관리자에게 보내는 작업 [등](https://flow.microsoft.com/blog/flow-in-spo-document-libraries/)과 같은 흐름을 시작할 수 있습니다.
* **Microsoft Planner 커넥터** - 결과를 개선하기 위해 Microsoft Planner를 통해 쉽게 팀, 작업, 문서 및 대화를 수행할 수 있습니다.
* **라이선스 관리 보기** - 관리자는 Microsoft Flow 관리 센터에서 Microsoft Flow 및 PowerApps 라이선스(평가판 및 유료 모두)를 모두 볼 수 있습니다.
* **PowerApps 커뮤니티 계획** - PowerApps 커뮤니티 계획은 PowerApps, Microsoft Flow 및 Common Data Service용 기술을 탐색하고 배우고 빌드하기 위한 무료 계획입니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/planner-community-and-licenses/).

### <a name="release-2017-05-09"></a>릴리스 2017-05-09
* **Azure AD 커넥터** - 사용자 만들기 또는 그룹에 사용자 추가를 포함하는 Microsoft Flow에서 관리자 작업 수행을 위한 새로운 커넥터가 있습니다.
* **Office 365 Outlook 개선** - 흐름은 이제 공유 사서함에서 트리거될 수 있으며 공유 사서함으로 메일을 보낼 수 있습니다. 자동 회신을 설정하거나 읽을 수도 있습니다.
* **캐나다에서 사용 가능** - 이제 캐나다에서 흐름을 만들 수 있습니다.
* **사용자 지정 API 웹후크 만들기** - 사용자 지정 커넥터 개발자는 이제 웹후크를 사용하여 해당 사용자 지정 API에 트리거를 추가할 수 있습니다.
* **관리 센터에서 흐름 소유자 관리** - 환경 관리자는 Microsoft Flow 관리 센터에서 흐름 소유자를 관리할 수 있습니다.
* **커넥터 문서 참조** - 이제 [docs.microsoft.com에서 전체 커넥터 참조](https://docs.microsoft.com/Connectors/)를 가집니다.
* **두 개의 파트너 서비스** - 두 개의 새로운 파트너 서비스(Nexmo 및 Paylocity)가 출시되었습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/canada-mailboxes-aad).

### <a name="release-2017-04-27"></a>릴리스 2017-04-27
* **병렬 단계가 있는 흐름 빌드** - 병렬 실행이 가능한 흐름을 만듭니다. 즉, 두 개 이상의 단계가 정확히 동시에 실행될 수 있습니다.
* **지원되는 새로운 서비스 5개** - Approvals, Benchmark Email, Capsule CRM, LiveChat 및 Outlook Customer Manager와 같은 5개의 새로운 서비스입니다.
* **작업 재시도 모니터링** - Microsoft Flow는 서비스와 관련한 오류가 발생할 경우 작업을 다시 시도합니다. 이제 자동 재시도 횟수와 관련 세부 정보를 확인할 수 있습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/parallel-actions/).

### <a name="release-2017-04-17---q1-update-for-microsoft-flow"></a>릴리스 2017-04-17 - Microsoft Flow에 대한 1분기 업데이트
* **최신 승인 환경** - 승인자가 Microsoft Flow 모바일 앱 또는 Microsoft Flow 웹 사이트의 통합 승인 센터 내에서 안전하게 승인할 수 있는 워크플로를 만드세요.
* **팀 흐름 일반 공급** - 이제 일반적으로 사용할 수 있는 팀 흐름을 통해 여러 사람이 하나의 흐름을 소유하고 관리할 수 있습니다.
* **Microsoft Flow에 대한 커넥터 빌드** - 누구나 전 세계 사람들이 무료로 사용할 수 있는 Microsoft Flow 커넥터를 직접 만들어 제출할 수 있습니다.
* **"간소화된" 디자이너** - 새 버전의 디자이너는 특정 템플릿에 맞게 환경을 간소화하는 흐름을 만드는 데 필요한 필드만 제공합니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/q1-2017-update/).

### <a name="release-2017-04-11"></a>릴리스 2017-04-11
* **테이블 및 목록을 작성하는 새 작업** - 새로운 HTML 테이블 만들기, CSV 테이블 만들기 및 항목 목록을 처리할 수 있는 작업 조인 기능(이전의 각각에만 적용하는 기능 대신).
* **어디서나 단계 삽입** - 이제 끌어서 놓을 필요 없이 워크플로의 어디에나 새 단계를 삽입할 수 있습니다.
* **새 서비스 4개** - Flow는 이제 10 to 8 Scheduling, Act!, Inoreader 및 Computer Vision API를 지원합니다. Computer Vision API를 사용하면 이미지를 처리하여 텍스트 콘텐츠를 가져오거나(OCR이라고 함) 해당 콘텐츠에 따라 이미지에 자동으로 태그를 적용할 수 있습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/html-tables-csvs-computer-vision/).

### <a name="release-2017-04-03"></a>릴리스 2017-04-03
* **Windows Phone 베타** - Windows Phone에서 Windows Phone 앱 베타 프로그램을 사용하여 앱의 미리 보기를 가져올 수 있습니다. [자세히 알아보세요](https://flow.microsoft.com/blog/windows-phone-app-beta-is-now-available/).
* **Muhimbi PDF** - 이제 Muhimbi PDF를 사용하여 Microsoft Word 파일을 PDF로 변환, 워터마크 추가, 문서 병합 등의 작업을 수행할 수 있습니다. [자세히 알아보세요](https://flow.microsoft.com/blog/convert-files-using-muhimbi/).
* **물리적 단추에서 흐름 트리거** - 물리적 단추 업계의 최고 제품인 Shortcut Labs의 Flic과 The Button Corporation의 Bttn이라는 두 제품과 파트너십을 체결했다는 소식을 발표합니다. [자세히 알아보기](https://flow.microsoft.com/blog/physical-buttons/)

### <a name="release-2017-03-22"></a>릴리스 2017-03-22
* **흐름의 사본 만들기** - 이제 초안 버전에서 작동하는 흐름의 사본을 만들거나 이전에 만든 흐름을 복제할 수 있습니다.
* **두 개의 새로운 서비스** - 작업을 생성하고 업데이트하여 할 일 목록을 관리하는 Toodledo와 고객 서비스를 제공하고 티케팅 플랫폼을 지원하는 Zendesk에 대한 지원이 추가됩니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/make-a-copy/).

### <a name="release-2017-03-15"></a>릴리스 2017-03-15
* **동료와 단추 공유** - 이제 흐름 단추를 다른 사용자와 공유하여 모든 비즈니스 사용자가 빠른 작업을 수행하기 쉽게 해줄 수 있습니다.
* **홈 화면에서 단추 트리거** - 모바일 장치의 홈 및 잠금 화면에서 흐름 단추에 대한 바로 가기를 사용하면 흐름 트리거가 그 어느 때보다 더 빨라집니다.
* **Microsoft Flow 앱의 팀 흐름** - 이제 iOS 또는 Android용 Microsoft Flow 앱에서 다른 소유자를 포함하는 흐름을 볼 수 있습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/button-sharing/).

### <a name="release-2017-03-10"></a>릴리스 2017-03-10
* **향상된 사용자 지정 커넥터 경험** - 이제 Postman 컬렉션을 사용하여 사용자 지정 커넥터를 만들고 작업을 편집, 추가 및 테스트할 수 있습니다.
* **두 가지 새로운 서비스** -PowerApps Notifications 및 PivotalTracker 지원이 추가되었습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/new-updates-custom-api/).

### <a name="release-2017-02-27"></a>릴리스 2017-02-27
* **흐름 단추 트리거** - 이제 Microsoft Flow 웹 사이트에서 바로 흐름 단추를 트리거할 수 있습니다. 흐름의 목록을 볼 때 "..." 메뉴를 선택하고 지금 실행 명령을 선택하기만 하면 됩니다.
* **다섯 가지 새로운 서비스** -Oracle 데이터베이스, Intercom, FreshBooks, LeanKit 및 WebMerge 지원이 추가되었습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/trigger-flow-buttons-web/).

### <a name="release-2017-02-21"></a>릴리스 2017-02-21
* **환경 흐름 보기** - 환경 관리자는 이제 지정된 환경 내에서 모든 흐름의 전체 목록을 볼 수 있을 뿐만 아니라 흐름을 활성화, 비활성화 또는 삭제할 수도 있습니다.
* **두 가지 새로운 서비스** - Azure Automation 및 Basecamp 2 지원이 추가되었습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/).

### <a name="release-2017-02-16"></a>릴리스 2017-02-16
* **다섯 가지 새로운 서비스** - Azure Data Lake, Bitbucket(GIT 개정판 제어를 사용하는 프로젝트용 웹 기반 호스팅 서비스), Eventbrite, Infusionsoft 및 Pipedrive 지원이 추가되었습니다.
* **사용자 지정 HTTP 인증** - 흐름 디버거에서 이제 사용자 지정 HTTP 끝점에 인증을 사용할 수 있습니다.
* **JSON 메시지 구문 분석** - HTTP 요청 트리거에서 오는 JSON 데이터 또는 HTTP 작업에서 반환된 데이터를 구문 분석할 수 있습니다.
* **흐름 실행 필터링** - 실행 중인 흐름 또는 취소된 실행을 보는 기능을 포함하여 더 구체적인 옵션으로 흐름 실행에 대한 필터링이 향상되었습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/).

### <a name="release-2017-02-06"></a>릴리스 2017-02-06
* **팀 흐름** - 팀 흐름을 사용하면 여러 명이 함께 흐름을 소유하고 관리할 수 있습니다. 그리고 이들이 조직을 떠나더라도 만든 흐름을 계속 실행할 수 있습니다.
* **사용자 지정 커넥터 공유** - 팀 흐름과 같이 사용자 지정 커넥터를 공유하고 조직 내에서 전체적으로 관리할 수 있습니다.
* **Gmail 및 LUIS 지원** - Gmail 및 Azure Cognitive Services의 언어 이해 인텔리전스 서비스에 연결합니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/team-flows/).

### <a name="release-2017-01-30"></a>릴리스 2017-01-30
* **흐름 단추 입력** - 이제 흐름 단추는 흐름 작성자가 단추를 탭할 때 전달되는 정보를 정의할 수 있도록 런타임 시 사용자 입력을 수신할 수 있습니다.
* **Outlook 태스크 및 HelloSign** -Outlook 태스크 서비스를 사용하면 태스크를 관리할 수 있고 HelloSign을 사용하면 전자 서명의 보안을 유지할 수 있습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/button-user-inputs/).

### <a name="release-2017-01-23"></a>릴리스 2017-01-23
* **서비스별 검색** - 트리거 또는 작업을 추가할 때 서비스별로 검색하여 각 서비스에 대한 모든 작업을 봅니다.
* **대/소문자 전환** - 스위치 블록을 추가하여 병렬 논리의 여러 분기를 추가합니다.
* **전자 메일 작업 추가** - Office 365 Outlook 및 Outlook.com 서비스의 새로운 기능에서는 플래그가 지정된 메일을 사용합니다.
* **새로운 5개 서비스** - 로컬 또는 네트워크 파일 시스템, 지불 서비스 스트라이프, IBM Informix, IBM DB2 및 UserVoice에 연결합니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/search-by-service/).

### <a name="release-2017-01-14"></a>릴리스 2017-01-14
* **실행 다시 제출** - 흐름이 실패하여 이를 수정하고 다시 실행하려는 경우 실패한 실행을 다시 제출할 수 있습니다.
* **실행 취소** - 흐름이 멈춘 경우 이제는 명시적으로 실행을 취소할 수 있습니다.
* **새로운 두 가지 서비스** - GoToTraining 및 GoToWebinar에 대한 지원을 추가했습니다.
* **모바일 링크** - 모바일 앱에서 템플릿을 직접 공유할 수 있으며, 웹 사이트의 위쪽에 앱에 대한 빠른 다운로드 링크를 추가했습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/managing-runs/).

### <a name="release-2016-12-29"></a>릴리스 2016-12-29
Microsoft Flow는 이제 eSignature 및 DTM(Digital Transaction Management)을 처리하는 DocuSign, 웹 기반 설문 조사를 위한 SurveyMonkey 및 OneNote 메모 작성 앱(비즈니스 계정만)을 지원합니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/final-2016-services/).

### <a name="release-2016-12-20"></a>릴리스 2016-12-20
* **지금 실행** - 매일 예약된 보고서가 있는 경우처럼 되풀이 트리거를 실행할 수 있지만 **지금** 실행하는 보고서도 필요합니다.
* **새로운 6개 서비스** - MSN 날씨, 중간(Medium), Google 연락처, 버퍼, 수집(Harvest) 및 TypeForm에 연결되는 흐름을 빌드합니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/run-now-and-six-more-services/).

### <a name="release-2016-12-14"></a>릴리스 2016-12-14
이제는 단추 흐름을 트리거할 때 단추를 트리거한 위치, 실행자, 시간 등과 같은 중요한 정보를 활용할 수 있습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/button-trigger-tokens/).

### <a name="release-2016-12-06"></a>릴리스 2016-12-06
* **단계별 학습 소개** - Microsoft Flow의 광범위하고 강력한 기능을 이해하는 데 도움을 주기 위해 동영상과 설명서가 짝을 이루어 일련의 학습 과정을 시작합니다.
* **새로운 두 가지 서비스** - Flow에서 이제 Freshdesk 고객 지원 솔루션과 GoToMeeting 온라인 모임 도구를 사용할 수 있습니다.
* **HTTP 웹후크 지원** - 흐름은 이제 웹후크의 끝점으로 자동으로 등록되고 해제됩니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/guided-learning-and-two-services/).

### <a name="release-2016-11-23"></a>릴리스 2016-11-23
* **Flow에서 Power BI 경고 지원** - Power BI 데이터 경고에서 흐름을 트리거하여 작업에 대한 통찰력을 높입니다.
* **모바일 응용 프로그램 개선** - 템플릿을 사용하여 만든 기존 환경 외에도 비어 있는 새 흐름을 만들 수 있는 기능이 추가되었습니다. 또한 흐름을 표시하는 성능이 향상되었습니다.
* **새로운 8개 서비스** - 이제 Azure Resource Manager, Azure Queues, Chatter, Disqus, Azure Cosmos DB, Cognitive Services Face API, HipChat 및 Wordpress에 연결할 수 있습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/power-bi-and-eight-other-services/).

### <a name="release-2016-11-15"></a>릴리스 2016-11-15
* **Microsoft Flow 파트너 프로그램** - Microsoft Flow에는 이제 인증된 파트너 프로그램이 있으며, 전 세계에서 Microsoft Flow를 통해 다른 회사의 능력과 경험을 활용할 수 있습니다.
* **새로운 6개 서비스** - 이번 주에 Asana, Campfire, EasyRedmine, JIRA, Redmine 및 Vimeo와 같은 6개의 서비스를 출시합니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/partner-program-six-new-services/).

### <a name="release-2016-10-31---general-availability"></a>릴리스 2016-10-31-일반 공급
* **가격 책정 및 라이선스** - 현재 무료 및 유료 플랜 모두 공급되며 또한 Office 365 및 Dynamics 365에도 포함됩니다.
* **Microsoft 흐름 관리자 센터** -새 관리자 센터를 겸비한 엔터프라이즈 수준입니다. 관리자 센터에서 조직 내의 환경을 관리할 수 있습니다.
* **데이터 손실 방지 정책** - 관리자는 서비스 간의 데이터 흐름을 제어하는 데이터 손실 방지  정책을 만들 수 있습니다.
* **Android 가용성** - 이제 Microsoft Flow는 iOS 및 Android에서 모두 사용할 수 있습니다. 앱의 단추를 탭하면 알림을 가져오고, 작업을 모니터링하고, 흐름을 시작 수 있습니다.
* **새 디자이너 환경** - 이제는 단계에서 단계로 전달된 동적 콘텐츠를 검색할 수 있어, 원하는 데이터를 훨씬 더 빠르게 참조할 수 있습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/announcing-ga/).

### <a name="release-2016-10-26"></a>릴리스 2016-10-26
* **흐름 단추** - 우리가 언제 어디서나 트리거할 수 있었으면 하는 수많은 작업이 있습니다. 이제 Button Flows를 사용하여 모바일 장치에서 단 한 번의 단추 클릭으로 그렇게 할 수 있습니다.
* **환경 발표** - 환경은 조직의 흐름을 저장하고 관리하는 별개의 공간입니다. 환경은 지역 기반, 	즉 환경 내에 있는 흐름, 앱 및 비지니스 데이터가 환경이 위치한 지역에 있을 것이란 뜻입니다.
* **6개의 새로운 서비스** - Bit.ly, Cognitive Services Text Analytics, Dynamics NAV, Dynamics 365 for Financials, Instapaper, 및 Pinterest에 대한 지원 추가.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/environments-for-makers/).

### <a name="release-2016-10-16"></a>릴리스 2016-10-16
* **더 많은 인증 형식을 지원하는 사용자 지정 커넥터** - 사용자 지정 커넥터에서 이제 API 키 인증을 지원하고 전체 OAuth 2.0 사양을 지원하는 모든 서비스에 대해 인증할 수 있습니다.
* **새로 지원되는 세 개의 서비스** - Basecamp 3, Blogger 및 PagerDuty에 대한 지원이 추가되었습니다.
* **개선된 디자이너** - 개선된 성능으로 모든 작업의 "..." 메뉴에서 연결을 즉시 업데이트하고 복구할 수 있게 되었으며 흐름 작동을 끝낼 때 사용할 수 있는 Terminate라는 새로운 단계를 추가했습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/early-october-updates/).

### <a name="release-2016-09-25"></a>릴리스 2016-09-25
이제 휴대폰에서 흐름을 만들 수 있습니다. 풍부한 템플릿 갤러리를 찾아보거나 서비스 목록에서 탐색하거나 템플릿 범주를 선택하여 자세히 봅니다. 이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/mobile-creation/).

### <a name="release-2016-09-22"></a>릴리스 2016-09-22
* **Microsoft Graph 사용자 선택기** - 새 Microsoft Graph 사용자 선택기는 Microsoft Flow UI에 직접 통합되어 사용자가 바른 연락처 또는 이메일 주소를 선택할 수 있습니다.
* **Microsoft Dynamics AX 지원** - 흐름 내에서 이제 새 레코드 작성부터 데이터에 대한 쿼리까지 사용자 Dynamics AX 온라인 작업 데이터에 작업할 수 있습니다.
* **파트너의 두 가지 새로운 서비스** - 이제 흐름에서 appFigures 또는 Insightly를 사용합니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/more-september-updates/).

### <a name="release-2016-09-14"></a>릴리스 2016-09-14
* **웹 사이트 또는 앱에 포함** - 개발자가 앱 또는 웹 사이트에 직접 Microsoft Flow를 포함하여 사용자에게 개인용 또는 전문가용 작업을 자동화하는 간단한 방법을 제공할 수 있습니다.
* **HTTP 끝점으로 흐름 사용하기** - 이제 HTTP API로 흐름 자체를 사용할 수 있습니다. 흐름 내에서 요청을 호출하는 트리거가 있으며 응답 카드를 추가하여 들어오는 요청에 응답하도록 선택할 수 있습니다.
* **Todoist 지원** - Todoist는 회사와 집에서의 모든 프로젝트에 대한 관점을 제공합니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/extend-web-site-application/).

### <a name="release-2016-09-01"></a>릴리스 2016-09-01
모든 사용자를 위한 Microsoft Flow 지금 사용 가능 - Office 365 Business 또는 Office 365 Enterprise와 사용하는 전자 메일과 같이 직장 또는 학교에서 제공하는 전자 메일 주소에 한해서 미리 보기를 먼저 선보였습니다. 오늘 미리 보기를 공식적으로 발표하며 사용하는 전자 메일에 상관없이 모든 사용자가 무료로 사용할 수 있습니다. 이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/available-for-everyone/).

### <a name="release-2016-08-31"></a>릴리스 2016-08-31
* **중첩된 조건** - 이제 한 조건 안에 두 번째(또는 세 번째, 등...) 조건을 추가할 수 있습니다.
* **각각에 적용** - 각 루프에 적용하면 반복되는 목록을 제어할 수 있습니다.
* **Do-until** - Do-until 루프를 사용하면 특정 조건이 충족될 때까지 단계를 반복합니다.
* **배열 필터링** - 목록에 있는 모든 항목이 사용자가 정의한 몇 가지 표현과 일치하는지 확인하는 단일 기본 필터 단계입니다.
* **문자열 변수 구성** - 이제 문자열 변수를 구성할 수 있습니다.
* **범위** - 범위는 두 개 이상의 작업을 함께 그룹화하는 간단한 방법입니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/build-advanced-flows/).

### <a name="release-2016-08-27"></a>릴리스 2016-08-27
* **단계에 대한 의견** - 설명을 사용하면 메모와 함께 각 개별 작업에 주석을 쉽게 추가할 수 있어 흐름에 필요한 것을 쉽게 기억할 수 있습니다.
* **Smartsheet 지원** - 이번 주에 Smartsheet에 연결하는 지원이 추가되었습니다. Smartsheet는 클라우드의 시트에서 공동으로 작업하도록 해주는 서비스입니다.
* **흐름 작성 시 UI 구체화** - 흐름 이름을 앞과 가운데에 위치시켰고 저장 단추를 페이지 맨위에 두어 쉽게 찾을 수 있도록 하였습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/add-comments-smartsheet/).

### <a name="release-2016-08-18"></a>릴리스 2016-08-18
이제 Microsoft Flow 통합을 포함하는 새 SharePoint Online 최신 목록 환경을 미리 볼 수 있습니다. 이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/microsoft-flow-integration-with-sharepoint-modern-lists-preview/).

### <a name="release-2016-08-13"></a>릴리스 2016-08-13
* **Visual Studio Team Services** - 흐름을 통해 이제 VSTS를 O365 전자 메일, Slack, Trello, Wunderlist와 같은 다양한 서비스에 연결할 수 있습니다.
* **SharePoint의 향상된 기능** - SharePoint 목록은 한 줄의 텍스트, 날짜와 시간 등의 간단한 개체에서 사용자 또는 그룹, 조회 및 선택 등의 복잡한 개체까지 데이터 형식의 범위를 지원합니다.
* **O365 Outlook 연결 테스트** - 이제 새 O365 Outlook 연결을 만들 때마다 사용할 준비가 되었는지 테스트합니다.
* **부울 제어** - 또한 새 전자 메일이 트리거에 도착했을 때에 있는 첨부 파일 포함과 같은 부울 입력 필드에 대해 입력해야 하는 값을 분명하게 만들기 위해 부울 컨트롤을 추가했습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/visual-studio-team-services-enhancements-to-sharepoint-and-o365-outlook-and-boolean-control/).

### <a name="release-2016-08-08"></a>릴리스 2016-08-08
Microsoft Common Data Service의 공개 미리 보기가 Microsoft Flow에 통합됩니다. 이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/flow-and-common-data-model/).

### <a name="release-2016-08-05"></a>릴리스 2016-08-05
* **SharePoint 온-프레미스** - SharePoint Online과 마찬가지로 미리 정의된 템플릿을 사용하거나 템플릿을 처음부터 제작하여 SharePoint 온-프레미스 목록 및 문서 라이브러리를 만들 수 있습니다.
* **디자이너의 정보 거품** - 각 트리거 및 작업의 기능을 정교하게 만들기 위해 흐름의 각 단계 위에 정보 거품을 추가했습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/sharepoint-on-premises-and-info-bubbles-2/).

### <a name="release-2016-07-15"></a>릴리스 2016-07-15
* **새롭게 추가된 네 가지 서비스** - Google 달력, Google 작업, YouTube 및 SparkPost에 연결합니다.
* **사용자의 작업 이름 바꾸기** - 이제 이러한 작업 이름을 바꾸어 다른 작업임을 구별할 수 있습니다.
* **다른 시간 단위의 지연** - 이제 초, 분, 시간 또는 날짜를 선택할 수 있습니다.
* **쉬워진 폴더 브라우저 사용** - 폴더 브라우저를 간소화했습니다. 이제 왼쪽 클릭으로 폴더를 선택할 수 있고 오른쪽 클릭으로 폴더를 열어 폴더 내의 하위 폴더를 선택할 수 있습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/new-google-services-rename-more/).

### <a name="release-2016-07-08"></a>릴리스 2016-07-08
온-프레미스 데이터 게이트웨이를 사용한 Microsoft Flow의 온-프레미스 연결 이 옵션을 사용하면 SQL Server에 안전하게 연결할 수 있고 흐름에 통합할 수 있습니다. 이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/on-premises-data-gateway/).

### <a name="release-2016-07-02"></a>릴리스 2016-07-02
* **Google 스프레드시트 지원** - 이전에는 Google 드라이브와 Excel을 사용했지만 이번 주에는 기본 Google 스프레드시트 지원을 추가합니다.
* **템플릿에서 더 빠른 시작 지원** - 템플릿에서 시작하는 방식을 일부 최적화하였습니다. 이제 템플릿 페이지에서 오른쪽 인라인 템플릿에 사용할 계정을 선택할 수 있습니다.
* **SharePoint 및 Office 365에 대한 무기한 인증** - 이제 Microsoft Flow가 자동으로 Azure Active Directory에 액세스 기반 서비스를 갱신하여 암호 변경을 통해 모든 흐름이 작업을 지속합니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/more-june-updates/).

### <a name="release-2016-06-20"></a>릴리스 2016-06-20
* **Microsoft Flow용 새로운 모바일 앱 소개** - 오늘 Microsoft 제품의 또다른 주요 사항을 소개하려고 합니다. 이제 자동화된 워크플로를 언제 어디서나 관리, 추적, 탐색할 수 있는 모바일 앱을 iOS에서 다운로드할 수 있습니다(곧 Android에서도 사용 가능).  
* **Single Sign-On** - Office 365와 같은 기타 Microsoft 서비스로 Microsoft Flow에 인증하는 Single Sign-On을 구현했습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/welcome-to-flow-now-more-mobile/).

### <a name="release-2016-06-18"></a>릴리스 2016-06-18
* **새 메일 서비스** - 이제 Microsoft Flow 내의 개인 또는 회사 전자 메일 계정에 연결할 필요없이 Microsoft Flow에서 직접 전자 메일을 보낼 수 있습니다.
* **포털에서 알림** - 이제 흐름에서 무언가가 깨질 때마다 포털 맨 위에 알림이 표시됩니다.
* **포털에서 모든 작업** - 이제 웹 사이트에서 새 활동 탭을 클릭하여 모든 흐름 에서 활동을 볼 수 있습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/mail-and-all-activity/).

### <a name="release-2016-05-27"></a>릴리스 2016-05-27
* **서비스로 템플릿 탐색** - 이제 로그인하지 않고도 지원되는 모든 서비스를 확인할 수 있습니다. 이 페이지에서 각 서비스에 대한 설명을 보고 해당 서비스에 포함된 템플릿을 확인할 수 있습니다.
* **사용자 지정 커넥터 제작 및 사용** - PowerApps에서 사용자 지정 커넥터를 만드는 것처럼 flow.microsoft.com에서 바로 사용자의 API에 연결할 수도 있습니다.
* **완료하기 전에 흐름 테스트** - 시작 작업을 수행하는 경우 흐름을 저장할 때마다 페이지에 실시간 흐름 실행 결과를 볼 수 있습니다.

이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/may-updates-to-microsoft-flow/).

### <a name="release-2016-05-07"></a>릴리스 2016-05-07
두 가지 새로운 서비스 추가: Microsoft Project Online 및 Mailchimp의 Mandrill 이 릴리스에 대한 [자세한 내용 보기 및 질문하기](https://flow.microsoft.com/blog/announcing-microsoft-flow-webinars/).

### <a name="release-2016-04-27---public-preview"></a>릴리스 2016-04-27 - 프로그램 미리 보기
[Microsoft PowerApps](https://powerapps.microsoft.com)의 일환으로 논리 흐름을 사용한 경우 Microsoft Flow 미리 보기 릴리스는 몇 가지 새로운 기능을 제공합니다.

* 이제 다양한 템플릿의 갤러리를 탐색하고 인기도, 이름 또는 게시일에 따라 정렬할 수 있습니다.
* 흐름을 사용자 지정한 후 [자체 템플릿](publish-a-template.md)을 갤러리에 게시할 수 있습니다.
* 흐름의 모든 확인 및 실행 내역을 볼 수 있습니다.
* 흐름을 저장하면 트리거 동작을 실행하여 [즉시 동작을 확인](see-a-flow-run.md)할 수 있습니다.
* 흐름에 대해 논의하거나 [아이디어를 제출할 수 있는](https://go.microsoft.com/fwlink/?LinkID=787474) [새 커뮤니티](https://go.microsoft.com/fwlink/?LinkID=787467)를 마련했습니다.

## <a name="next-steps"></a>다음 단계
이 릴리스 정보나[FAQ](frequently-asked-questions.md)에서 다루지 않은 문제가 있는 경우 [커뮤니티에 가입](https://go.microsoft.com/fwlink/?LinkID=787467)하여 질문하거나 [지원을 요청합니다](http://go.microsoft.com/fwlink/?LinkID=787479).

