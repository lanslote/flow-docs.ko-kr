---
title: Markdown을 사용하여 Microsoft Flow 승인 서식 지정 | Microsoft Docs
description: Markdown을 사용하여 Microsoft Flow 승인 요청의 서식을 지정하는 방법을 알아봅니다.
services: ''
suite: flow
documentationcenter: na
author: gcorvera
manager: kfile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/23/2018
ms.author: gcorvera
ms.openlocfilehash: 147a5ee1e19744c6164cac4acdd04aef16440e46
ms.sourcegitcommit: cd3cdcff3accb9a54f002fdc33d33935b4276249
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39519804"
---
# <a name="use-markdown-in-microsoft-flow-approval-requests"></a>Microsoft Flow 승인 요청에서 Markdown 사용

이 문서에서는 [Markdown](https://en.wikipedia.org/wiki/Markdown) 구문을 사용하여 서식 지정과 테이블을 승인 요청에 추가하는 방법을 설명합니다.

## <a name="headers"></a>헤더

헤더를 사용하여 주석을 구조화합니다. 헤더는 더 긴 주석을 분할하여 더 읽기 쉽게 만듭니다.

해시 문자 `#`로 줄을 시작하여 제목을 설정합니다. 추가 해시 문자(예: `####`)가 있는 줄을 시작하여 하위 제목을 사용하여 설명을 구성합니다. 최대 6개의 제목 수준이 지원됩니다.

**예:**

```Markdown
# This is a H1 header
## This is a H2 header
### This is a H3 header
#### This is a H4 header
##### This is a H5 header
```

**결과:**

![흐름 내보내기](./media/approvals-markdown-support/mrkdown-headers.png)

## <a name="paragraphs-and-line-breaks"></a>단락 및 줄 바꿈

단락 또는 줄 바꿈으로 텍스트를 분할하여 더 읽기 쉽게 만듭니다. 줄 바꿈 앞에 두 개의 공백을 입력하여 새 단락을 시작하거나 두 개의 줄 바꿈을 연속 입력하여 새 단락을 시작합니다.   
   
**예**

<pre>
Add lines between your text with the Enter key.
This spaces your text better and makes it easier to read.
</pre>

**결과:**   
Enter 키를 사용하여 텍스트 사이에 줄을 추가합니다.      
이렇게 하면 텍스트 간격이 개선되어 더 읽기 쉽습니다.


**예 2**

<pre>
Add two spaces prior to the end of the line.(space, space)     
This adds space in between paragraphs.
</pre>

**결과:**  
줄 끝 앞에 두 개의 공백을 추가합니다.   

이렇게 하면 단락 사이에 공백이 추가됩니다.
  

## <a name="lists"></a>목록

목록으로 관련 항목을 구성합니다. 숫자를 사용하여 순서가 지정된 목록을 추가하거나 글머리 기호만 있는 순서가 지정되지 않은 목록을 추가할 수 있습니다.

순서가 지정된 목록은 숫자로 시작하고 이어서 목록 항목별로 마침표가 표시됩니다. 순서가 지정되지 않은 목록은 `*`로 시작합니다. 각 목록 항목을 새 줄에서 시작합니다. Markdown 파일 또는 위젯에서 줄 바꿈 앞에 두 개의 공백을 입력하여 새 단락을 시작하거나 두 개의 줄 바꿈을 연속 입력하여 새 단락을 시작합니다.   

### <a name="ordered-or-numbered-lists"></a>순서가 지정된 목록 또는 번호 매기기 목록

**예:**

```Markdown
0. First item.
0. Second item.
0. Third item.
```

**결과:**

1. 첫 번째 항목.
2. 두 번째 항목.
3. 세 번째 항목.

### <a name="bullet-lists"></a>글머리 기호 목록

**예:**

<pre>

- Item 1
- Item 2
- Item 3

</pre>

**결과:**

- 항목 1
- 항목 2
- 항목 3

### <a name="nested-lists"></a>중첩된 목록

**예:**
<pre>

1. First item.
   - Item 1
   - Item 2
   - Item 3
1. Second item.
   - Nested item 1
   - Nested item 2
   - Nested item 3

</pre>

**결과:**  

1. 첫 번째 항목.

    - 항목 1
    - 항목 2
    - 항목 3
2. 두 번째 항목.
    - 중첩 항목 1
    - 중첩 항목 2
    - 중첩 항목 3


## <a name="links"></a>링크

HTTP 및 HTTPS URL은 자동으로 링크로 서식이 지정됩니다. 

표준 markdown 링크 구문을 사용하여 URL에 대한 텍스트 하이퍼링크를 설정할 수 있습니다.

```Markdown
[Link Text](Link URL)
```

**예:**
<pre>
&#91;Microsoft Flow](https://flow.microsoft.com)
</pre>

**결과:**

[Microsoft Flow](https://flow.microsoft.com)

### <a name="anchor-links"></a>앵커 링크

앵커 ID는 HTML으로 렌더링될 때 모든 제목에 할당됩니다. ID는 공백이 대시(-)로 바뀌고 모두 소문자인 제목 텍스트입니다.

**예:**

<pre>
###Link to a heading in the page
</pre>

<br/>

**결과:**

섹션에 대한 앵커 링크 구문...

<pre>
[Link to a heading in the page](#link-to-a-heading-in-the-page)
</pre> 
<br/>
ID는 모두 소문자이고 링크는 대/소문자를 구분하므로 제목 자체에 대문자가 사용되더라도 소문자를 사용해야 합니다.


## <a name="tables"></a>테이블

구조화된 데이터를 테이블로 구성합니다. 

- 각 테이블 행을 고유한 줄에 배치 
- 파이프 문자 `|`를 사용하여 테이블 셀 구분 
- 테이블의 처음 두 줄은 테이블의 요소 맞춤과 열 머리글을 설정합니다.
- 테이블의 헤더와 본문을 나누어 열 맞춤(왼쪽, 가운데, 오른쪽)을 지정하는 경우 콜론(`:`)을 사용합니다. 
- 새 줄을 시작하려면 HTML 줄 바꿈 태그(`<br/>`)를 사용합니다(Wiki 내에서 작동하지만 다른 곳에서는 작동하지 않음).  
- CR 또는 LF로 각 행을 종료해야 합니다. 

**예:**

```
| Heading 1 | Heading 2 | Heading 3 |  
|-----------|:-----------:|-----------:|  
| Cell A1 | Cell A2 | Cell A3 |  
| Cell B1 | Cell B2 | Cell B3<br/>second line of text |  
```




**결과:**  

| 제목 1 | 제목 2 | 제목 3 |  
|-----------|:---------:|-----------:|  
| 셀 A1 | 셀 A2 | 셀 A3 |  
| 셀 B1 | 셀 B2 | 셀 B3<br/>두 번째 텍스트 줄 |  

 
## <a name="emphasis-bold-italics-strikethrough"></a>강조(굵게, 기울임꼴, 취소선)  

문자에 굵게, 기울임꼴 또는 취소선을 적용하여 텍스트를 강조할 수 있습니다. 
- 기울임꼴을 적용하려면: 텍스트를 별표 `*` 또는 밑줄 `_`로 묶습니다.   
- 굵게 적용하려면: 텍스트를 두 개의 별표 `**`로 묶습니다.    
- 취소선을 적용하려면: 텍스트를 두 개의 물결표 문자 `~~`로 묶습니다.   

이러한 요소를 결합하여 텍스트에 다양한 강조를 적용합니다.    

**예:**

<pre>
Use _emphasis_ in comments to express **strong** opinions and point out ~~corrections~~ 
**_Bold, italicized text_**  
**~~Bold, strike-through text~~**
</pre>

<br/>

**결과:**

주석에서 _강조_를 사용하여 **강한** 의견을 표시하고 <s>수정 사항</s>을 지적합니다   
**_굵게, 기울임꼴 텍스트_**   
**~~굵게, 취소선 텍스트~~**  


## <a name="special-characters"></a>특수 문자

<table width="650px">
<tbody valign="top">
<tr>
<th width="300px">구문</th>
<th width="350px">예제/메모</th>
</tr>



<tr>
<td>
<p>다음 문자 중 하나를 삽입하려면 접두사로 백슬래시를 지정합니다.</p>

<p style="margin-bottom:2px;">```\   backslash ``` </p>
<p style="margin-bottom:2px;"><code>\`</code>   `backtick`</p>
<p style="margin-bottom:2px;">```_   underscore  ```</p>
<p style="margin-bottom:2px;">```{}  curly braces  ``` </p>
<p style="margin-bottom:2px;">```[]  square brackets ```</p>
<p style="margin-bottom:2px;">```()  parentheses  ```</p>
<p style="margin-bottom:2px;">```#   hash mark  ``` </p>
<p style="margin-bottom:2px;">```+   plus sign  ```</p>
<p style="margin-bottom:2px;">```-   minus sign (hyphen) ```</p>
<p style="margin-bottom:2px;">```.   dot  ``` </p>
<p style="margin-bottom:2px;">```!   exclamation mark ```</p>


</td>
<td>특수 문자 삽입에 대한 몇 가지 예제
<p>```\\```를 입력하여 \\ 표시 </p>
<p>```\_```을 입력하여 _ 표시 </p>
<p>```\#```을 입력하여 \# 표시 </p>
<p>```\(```를 입력하여 \( 표시 </p>
<p>```\.```를 입력하여 \. 표시 </p>
<p>```\!```를 입력하여 \! 표시 </p>
</td>
</tr>

</tbody>
</table>
