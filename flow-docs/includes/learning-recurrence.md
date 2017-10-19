이 항목에서는 **되풀이**라는 트리거를 사용하여 미리 예약된 흐름을 실행하는 방법을 확인합니다.  OneDrive의 Excel 테이블에서 고객 전자 메일 주소를 자동으로 가져오는 Contoso 마케팅 팀에 대한 흐름을 빌드합니다. 하루당 한 번 스프레드시트에 추가된 새 전자 메일 주소가 MailChimp 고객 목록에 추가되도록 흐름을 구성합니다. 

## <a name="create-a-scheduled-flow"></a>예약된 흐름 만들기
1. **Microsoft Flow**를 열고 **내 흐름**을 선택한 다음 **빈 페이지에서 만들기**를 선택합니다. 
   
    ![](./media/learning-recurrence/flow-create-blank.png)
2. **수백 개의 커넥터 및 트리거 검색**을 선택합니다.
3. **일정** 서비스를 검색하고 선택한 다음 **일정 – 되풀이** 트리거를 선택합니다.
   
    ![](./media/learning-recurrence/flow-recurrence-trigger.png)
4. **빈도**를 **일**로, **간격**을 **1**로 설정합니다. **새 단계**를 선택하고 **작업 추가**를 선택합니다. 
   
    ![](./media/learning-recurrence/frequency-interval.png)
5. **Excel**을 검색하고 **Excel** 서비스를 선택하고 작업 **Excel – 행 가져오기**를 선택합니다. 
   
    ![](./media/learning-recurrence/excel-get-rows.png)
   
    **참고**: **행(row) 가져오기**가 아니라 **행(rows) 가져오기**를 선택해야 합니다. 
6. **파일 이름**을 선택하고 파일 위치로 이동합니다. **테이블 이름**을 선택하고 스프레드시트에서 원하는 테이블을 선택합니다. 
   
    ![](./media/learning-recurrence/excel-get-file.png)
7. 새 작업을 추가합니다. 
   
    ![](./media/learning-recurrence/new-step.png)
8. **MailChimp** 서비스를 검색한 다음 작업 **MailChimp - 목록에 구성원 추가**를 선택합니다.
   
    ![](./media/learning-recurrence/select-mailchimp.png)
   
    **참고:** MailChimp는 *프리미엄* 커넥터입니다. Microsoft Flow 라이선스에 따라 이 커넥터를 사용하려면 평가판에 등록해야 할 수도 있습니다.
9. 드롭다운 메뉴에서 **목록 ID** 및 **상태** 필드를 추가합니다.
   
   * **목록 ID** – 원하는 MailChimp 메일 그룹 선택
   * **상태** – **구독 중** 선택 
     
     ![](./media/learning-recurrence/mailchimp-id-status.png)
10. **전자 메일 주소**에서 동적 콘텐츠 기능을 사용하여 **ContactEmail** 필드를 추가합니다. 
    
     ![](./media/learning-recurrence/mailchimp-address.png)
    
     흐름은 추가 단계를 자동으로 만듭니다. 흐름은 추가 작업이 필요한 작업을 설정하려는 것을 검색합니다. 흐름에서 새 메일 주소를 읽을 때마다 각 행에 대한 새 작업을 만듭니다. 
    
     ![](./media/learning-recurrence/mailchimp-for-each.png)
11. 동적 콘텐츠를 사용하여 **이름** 및 **성** 필드를 채웁니다.
    
    * **이름** – 이름
    * **성** – 성
      
      ![](./media/learning-recurrence/mailchimp-names.png)

이제 이 흐름은 하루에 한 번 실행되고 이 Excel 테이블에서 새 행을 가져오며, 전자 메일 주소 및 이름을 가져오고 이를 사용하여 MailChimp Contoso 메일 그룹을 채워 시간과 비용을 절약합니다. 

