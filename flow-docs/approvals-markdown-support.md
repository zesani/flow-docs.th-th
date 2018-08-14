---
title: ใช้ Markdown ในเพื่อจัดรูปแบบการอนุมัติ Microsoft Flow | Microsoft Docs
description: เรียนรู้วิธีใช้ Markdown เพื่อจัดรูปแบบคำขอการอนุมัติ Microsoft Flow
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
ms.contentlocale: th-TH
ms.lasthandoff: 08/06/2018
ms.locfileid: "39519812"
---
# <a name="use-markdown-in-microsoft-flow-approval-requests"></a>ใช้ Markdown ในคำขอการอนุมัติ Microsoft Flow

บทความนี้สอนวิธีใช้ไวยากรณ์ [Markdown](https://en.wikipedia.org/wiki/Markdown) เพื่อเพิ่มการจัดรูปแบบและตารางที่หลากหลายลงในคำขอการอนุมัติของคุณ

## <a name="headers"></a>ส่วนหัว

สร้างโครงสร้างข้อคิดเห็นของคุณโดยใช้ส่วนหัว ข้อคิดเห็นที่ยาวขึ้นของส่วนส่วนหัวทำให้อ่านง่ายขึ้น

เริ่มบรรทัดด้วยอักขระแฮช `#` เพื่อตั้งค่าเป็นหัวเรื่อง จัดระเบียบข้อคิดเห็นของคุณด้วยหัวข้อย่อย โดยเริ่มต้นบรรทัดด้วยอักขระแฮชเพิ่มเติม ตัวอย่างเช่น`####` รองรับหัวเรื่องได้สูงสุดหกระดับ

**ตัวอย่าง:**

```Markdown
# This is a H1 header
## This is a H2 header
### This is a H3 header
#### This is a H4 header
##### This is a H5 header
```

**ผลลัพธ์:**

![โฟลว์การส่งออก](./media/approvals-markdown-support/mrkdown-headers.png)

## <a name="paragraphs-and-line-breaks"></a>ตัวแบ่งย่อหน้าและบรรทัด

ทำให้ข้อความของคุณอ่านง่ายขึ้นโดยการแบ่งย่อหน้าหรือบรรทัด ใส่ช่องว่างสองช่องก่อนที่จะแบ่งบรรทัดเพื่อเริ่มย่อหน้าใหม่ หรือใส่ตัวแบ่งบรรทัดสองตัวเรียงกันเพื่อเริ่มย่อหน้าใหม่   
   
**ตัวอย่าง**

<pre>
Add lines between your text with the Enter key.
This spaces your text better and makes it easier to read.
</pre>

**ผลลัพธ์:**   
เพิ่มบรรทัดระหว่างข้อความของคุณด้วยแป้น Enter      
ซึ่งเว้นระยะห่างข้อความของคุณได้ดีกว่าและทำให้อ่านง่ายขึ้น


**ตัวอย่างที่ 2**

<pre>
Add two spaces prior to the end of the line.(space, space)     
This adds space in between paragraphs.
</pre>

**ผลลัพธ์:**  
ใส่ช่องว่างสองช่องก่อนที่จะจบบรรทัด   

ซึ่งจะเพิ่มช่องว่างระหว่างย่อหน้า
  

## <a name="lists"></a>แสดงรายการ

จัดระเบียบรายการย่อยที่เกี่ยวข้องกับรายการ คุณสามารถเพิ่มรายการจัดลำดับด้วยตัวเลข หรือรายการที่ไม่เรียงลำดับด้วยการใช้เพียงแค่สัญลักษณ์แสดงหัวข้อเท่านั้น

รายการจัดลำดับเริ่มต้นด้วยตัวเลข ตามด้วยจุดสำหรับแต่ละรายการ รายการที่ไม่เรียงลำดับที่เริ่มต้นด้วย`*` เริ่มต้นแต่ละรายการบนบรรทัดใหม่ ในไฟล์ Markdown หรือวิดเจ็ต ใส่ช่องว่างสองช่องก่อนที่จะแบ่งบรรทัดเพื่อเริ่มย่อหน้าใหม่ หรือใส่ตัวแบ่งบรรทัดสองตัวเรียงกันเพื่อเริ่มย่อหน้าใหม่   

### <a name="ordered-or-numbered-lists"></a>รายการที่เรียงลำดับหรือตามลำดับเลข

**ตัวอย่าง:**

```Markdown
0. First item.
0. Second item.
0. Third item.
```

**ผลลัพธ์:**

1. รายการแรก.
2. รายการที่สอง.
3. รายการที่สาม.

### <a name="bullet-lists"></a>รายการสัญลักษณ์แสดงหัวข้อ

**ตัวอย่าง:**

<pre>

- Item 1
- Item 2
- Item 3

</pre>

**ผลลัพธ์:**

- รายการที่ 1
- รายการที่ 2
- รายการที่ 3

### <a name="nested-lists"></a>รายการที่ซ้อนกัน

**ตัวอย่าง:**
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

**ผลลัพธ์:**  

1. รายการแรก.

    - รายการที่ 1
    - รายการที่ 2
    - รายการที่ 3
2. รายการที่สอง.
    - รายการที่ซ้อนกัน 1
    - รายการที่ซ้อนกัน 2
    - รายการที่ซ้อนกัน 3


## <a name="links"></a>การเชื่อมโยง

โดยอัตโนมัติจัดรูปแบบ HTTP และ HTTPS Url ตามลิงก์ 

คุณสามารถตั้งค่าข้อความไฮเปอร์ลิงก์สำหรับ URL ของคุณโดยใช้ลิงก์ของไวยากรณ์ Markdown มาตรฐาน:

```Markdown
[Link Text](Link URL)
```

**ตัวอย่าง:**
<pre>
&#91;Microsoft Flow](https://flow.microsoft.com)
</pre>

**ผลลัพธ์:**

[Microsoft Flow](https://flow.microsoft.com)

### <a name="anchor-links"></a>เชื่อมโยงจุดยึด

มีกำหนด ID จุดยึดกับหัวเรื่องทั้งหมดเมื่อแสดงเป็น HTML ID เป็นส่วนหัวของข้อความ จะแทนที่ช่องว่างด้วยเส้นประ (-) และตัวพิมพ์เล็กทั้งหมด

**ตัวอย่าง:**

<pre>
###Link to a heading in the page
</pre>

<br/>

**ผลลัพธ์:**

ไวยากรณ์สำหรับการลิงก์จุดยึดไปยังส่วน...

<pre>
[Link to a heading in the page](#link-to-a-heading-in-the-page)
</pre> 
<br/>
ID เป็นตัวพิมพ์เล็กทั้งหมด และลิงก์ต้องตรงตามตัวพิมพ์ใหญ่-เล็ก ดังนั้น โปรดแน่ใจว่าใช้ตัวพิมพ์เล็ก แม้ว่าหัวเรื่องเองใช้ตัวพิมพ์ใหญ่ก็ตาม


## <a name="tables"></a>ตาราง

จัดระเบียบข้อมูลที่มีการจัดโครงสร้างด้วยตาราง 

- วางตารางแต่ละแถวบนบรรทัดของตนเอง 
- เซลล์ตารางที่แยกต่างหากโดยใช้อักขระไปป์ `|` 
- สองบรรทัดแรกของตารางจะตั้งค่าส่วนหัวของคอลัมน์และการจัดแนวขององค์ประกอบในตาราง
- ใช้เครื่องหมายอัฒภาค (`:`) เมื่อแยกส่วนหัวและเนื้อหาของตารางออกจากกันเพื่อระบุการจัดแนวคอลัมน์ (ซ้าย กึ่งกลาง ขวา) 
- เมื่อต้องเริ่มบรรทัดใหม่ ใช้แท็กแบ่ง HTML (`<br/>`) (สามารถใช้ได้ภาย ใน Wiki แต่ใช้ไม่ได้กับที่อื่น ๆ)  
- ตรวจสอบให้แน่ใจว่าจบแต่ละแถว ด้วย CR หรือ LF 

**ตัวอย่าง:**

```
| Heading 1 | Heading 2 | Heading 3 |  
|-----------|:-----------:|-----------:|  
| Cell A1 | Cell A2 | Cell A3 |  
| Cell B1 | Cell B2 | Cell B3<br/>second line of text |  
```




**ผลลัพธ์:**  

| หัวเรื่อง 1 | หัวเรื่อง 2 | หัวเรื่อง 3 |  
|-----------|:---------:|-----------:|  
| เซลล์ A1 | เซลล์ A2 | เซลล์ A3 |  
| เซลล์ B1 | เซลล์ B2 | เซลล์ B3<br/>บรรทัดที่สองของข้อความ |  

 
## <a name="emphasis-bold-italics-strikethrough"></a>การเน้น (ตัวหนา ตัวเอียง ขีดทับ)  

คุณสามารถเน้นข้อความโดยการทำตัวอักขระให้เป็นตัวหนา ตัวเอียง หรือการขีดทับอักขระ: 
- เมื่อต้องการใช้ตัวเอียง: ล้อมรอบข้อความที่มีด้วยเครื่องหมายดอกจัน `*` หรือขีดล่าง `_`   
- เมื่อต้องการใช้ตัวหนา: ล้อมรอบข้อความที่ด้วยเครื่องหมายดอกจันคู่ `**`    
- เมื่อต้องการนำการขีดทับไปใช้: ล้อมรอบข้อความที่มีอักขระตัวหนอนคู่ `~~`   

รวมองค์ประกอบเหล่านี้เพื่อใช้การเน้นหลายแบบกับข้อความ    

**ตัวอย่าง:**

<pre>
Use _emphasis_ in comments to express **strong** opinions and point out ~~corrections~~ 
**_Bold, italicized text_**  
**~~Bold, strike-through text~~**
</pre>

<br/>

**ผลลัพธ์:**

ใช้_การเน้น_ในข้อคิดเห็นเพื่อแสดงวามคิดเห็นที่**น่าเชื่อถือ** และชี้ให้เห็น<s>แก้ไข</s>   
**_ข้อความตัวหนา ตัวเอียง_**   
**~~ข้อความตัวหนา ขีดทับ~~**  


## <a name="special-characters"></a>อักขระพิเศษ

<table width="650px">
<tbody valign="top">
<tr>
<th width="300px">ไวยากรณ์</th>
<th width="350px">ตัวอย่าง/บันทึกย่อ</th>
</tr>



<tr>
<td>
<p>เมื่อต้องแทรกหนึ่งในอักขระต่อไปนี้ ให้นำหน้าด้วยเครื่องหมายทับขวา:</p>

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
<td>ตัวอย่างในการแทรกอักขระพิเศษ
<p>ใส่ ```\\``` เพื่อให้ได้ \\ </p>
<p>ใส่ ```\_``` เพื่อให้ได้ _ </p>
<p>ใส่ ```\#``` เพื่อให้ได้ \# </p>
<p>ใส่ ```\(``` เพื่อให้ได้ \( </p>
<p>ใส่ ```\.``` เพื่อให้ได้ \. </p>
<p>ใส่ ```\!``` เพื่อให้ได้ \! </p>
</td>
</tr>

</tbody>
</table>
