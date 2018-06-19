---
title: เริ่มต้นโฟลว์ด้วยปุ่ม Flic | Microsoft Docs
description: เริ่มต้นโฟลว์ของปุ่มได้อย่างง่ายดาย ด้วยปุ่มตามจริงจาก Flic โดย Shortcut Labs
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/19/2017
ms.author: deonhe
ms.openlocfilehash: 518834103c1a17ef2f5af218eae43ccab4e5fda2
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "31001329"
---
# <a name="run-your-flows-by-pressing-a-flic-smart-button-preview"></a>เรียกใช้โฟลว์ของคุณ โดยการกดปุ่มอัจฉริยะ Flic (คุณลักษณะตัวอย่าง)
ทริกเกอร์โฟลว์ของคุณ โดยการกดปุ่มทางกายภาพที่เรียกว่า Flic จาก Shortcut Labs ตัวอย่างเช่น กด Flic เพื่อติดตามชั่วโมงการทำงาน, บล็อกปฏิทินของคุณ, นับจำนวนผู้เยี่ยมชมงาน หรือบันทึกตำแหน่งที่ตั้งทางภูมิศาสตร์

> [!IMPORTANT]
> กำหนดค่าคุณสมบัติ Flic ทั้งหมด โดยใช้แอปสำหรับอุปกรณ์เคลื่อนที่ของ Flic สำหรับ [Android](https://play.google.com/store/apps/details?id=io.flic.app) หรือ [iOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) ก่อนที่คุณสร้างโฟลว์ของคุณ
> 
> 

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น
เพื่อใช้ Flics ด้วย Microsoft Flow คุณต้องมี:

* การเข้าถึง [Microsoft Flow](https://flow.microsoft.com)
* ดาวน์โหลดแอป Flic สำหรับ [Android](https://play.google.com/store/apps/details?id=io.flic.app) หรือ [iOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) และใช้เพื่อจับคู่หนึ่งหรือหลาย Flic

## <a name="configure-flic-properties"></a>กำหนดค่าคุณสมบัติ Flic
ใช้แอปสำหรับอุปกรณ์เคลื่อนที่ของ Flic เพื่อโปรแกรมเหตุการณ์ของ Flic เหตุการณ์ได้แก่:

* คลิก (กดเร็วหนึ่งครั้ง)
* ดับเบิลคลิก (กดเร็วสองครั้ง)
* กดค้างไว้ (กดนานหนึ่งครั้ง)

สกรีนช็อตนี้แสดงตัวอย่างการกำหนดค่า Flic ของคุณ ซึ่งอาจเป็นดังต่อไปนี้:

![กำหนดค่า Flics](./media/flic-button-flows/configure-flic-actions.png)

หลังจากที่คุณได้เชื่อมโยงเหตุการณ์ Flic กับ Microsoft Flow คุณสามารถเลือกให้ Flic เป็นทริกเกอร์สำหรับโฟลว์ของคุณ ในการฝึกปฏิบัตินี้ คุณจะเลือกทริกเกอร์ในภายหลัง

## <a name="create-a-flow-thats-triggered-by-a-flic"></a>สร้างโฟลว์ที่ทริกเกอร์โดย Flic
ในการฝึกปฏิบัตินี้ เราใช้ Flic เพื่อเรียกใช้โฟลว์ที่บันทึกเวลาที่ ที่ปรึกษาใช้กับลูกค้าแต่ละราย ที่ปรึกษากด Flic หนึ่งครั้งเมื่อไปถึง และกดอีกครั้งก่อนออกเดินทางจากลูกค้า การกด Flic แต่ละครั้งจะเริ่มต้นโฟลว์ที่เชื่อมต่ออยู่ โฟลว์จะบันทึกเวลาปัจจุบันใน Google Sheets จากนั้นจะส่งการแจ้งเตือนทางอีเมล อีเมลประกอบด้วยรายละเอียดเกี่ยวกับการเรียกใช้โฟลว์

หมายเหตุ: ตรวจสอบให้แน่ใจว่า คุณใช้แอปสำหรับอุปกรณ์เคลื่อนที่ Flic เพื่อจับคู่ และกำหนดค่าการดำเนินการ**คลิก**อย่างน้อยหนึ่งการดำเนินการ เพื่อทริกเกอร์ Microsoft Flow ในสกรีนช็อตนี้ ฉันได้กำหนดค่าการดำเนินการ**คลิก** เพื่อทริกเกอร์ Microsoft Flow ภายหลังในการฝึกปฏิบัตินี้ เราจะกำหนดให้ทริกเกอร์โฟลว์ของเราเมื่อกด Flic หนึ่งครั้ง (คลิก)

   ![กำหนดค่า Flic](./media/flic-button-flows/flic-configured-for-flow.png)

เรามาเริ่มสร้างโฟลว์ของเรากัน

### <a name="start-with-a-template"></a>เริ่มต้นด้วยเทมเพลต
1. ลงชื่อเข้าใช้ [Microsoft Flow](https://flow.microsoft.com)
   
    ![ลงชื่อเข้าใช้](./media/flic-button-flows/sign-into-flow.png)
2. ป้อน **flic** ลงในกล่องค้นหา จากนั้นเลือกไอคอนค้นหา
   
    ![ค้นหา Flic](./media/flic-button-flows/search-flic.png)
3. เลือกเทมเพลต **ติดตามชั่วโมงการทำงานของคุณด้วยปุ่มอัจฉริยะ Flic**
   
    ![เลือกเทมเพลต](./media/flic-button-flows/flic-templates.png)

### <a name="create-a-spreadsheet-in-google-sheets"></a>สร้างสเปรดชีตใน Google Sheets
1. ตรวจทานรายละเอียดของเทมเพลต และสังเกตว่า เทมเพลตนี้จำเป็นต้องใช้สเปรดชีตใน Google Sheets
   
   ![ตรวจทานรายละเอียดของเทมเพลต](./media/flic-button-flows/flic-template-details.png)
2. ใน Google Sheets สร้างสเปรดชีตที่ประกอบด้วยแผ่นงานที่มีคอลัมน์ที่ชื่อว่า **ClickType** และ **Timestamp**
   
      เคล็ดลับ: คุณตั้งชื่อคอลัมน์ใน Google Sheets โดยการใส่ชื่อที่ด้านบนของคอลัมน์ ดังนั้น แผ่นงานของคุณควรจะเหมือนกับสกรีนช็อตนี้:
   
   ![Google Sheets](./media/flic-button-flows/flic-google-sheet.png)
   
   หมายเหตุ: คุณใช้แผ่นงานนี้ภายหลังในการฝึกปฏิบัตินี้

### <a name="add-the-flic-trigger-to-your-flow"></a>เพิ่ม Flic ให้เป็นทริกเกอร์โฟลว์ของคุณ
1. ลงชื่อเข้าใช้บริการของเทมเพลต จากนั้นเลือก**ดำเนินการต่อ**
   
     **ดำเนินต่อ**จะเปิดใช้งาน หลังจากที่คุณลงชื่อเข้าใช้บริการที่จำเป็นทั้งหมดสำหรับเทมเพลต
   
    ![ระบุข้อมูลประจำตัว](./media/flic-button-flows/flic-template-services-sign-in.png)
2. ป้อน **flic** ลงในกล่องค้นหา จากนั้นเลือกทริกเกอร์ **Flic - When a Flic is pressed** (เมื่อกดปุ่ม Flic)
   
    ![ค้นหาทริกเกอร์ flic](./media/flic-button-flows/flic-search-trigger.png)
3. เลือก Flic ที่คุณต้องการใช้จากรายการ**ปุ่ม Flic** บนการ์ด **Flic - When a Flic is pressed**
4. เลือก**คลิก**จากรายการ**เหตุการณ์**เพื่อระบุว่า คุณต้องการทริกเกอร์โฟลว์เมื่อกด Flic แบบครั้งเดียว
   
    ![เลือกการดำเนินการ flic](./media/flic-button-flows/select-flic.png)
   
   ไม่บังคับ คุณสามารถเลือก **ใดๆ** เพื่อระบุว่า เหตุการณ์ Flic ใด ๆ (คลิก, ดับเบิลคลิก หรือกดค้าง) สามารถทริกเกอร์โฟลว์ได้
   
   **ดับเบิลคลิก** ระบุว่าโฟลว์จะทริกเกอร์เมื่อ Flic ถูกกดสองครั้งอย่างรวดเร็ว **กดค้างไว้** ระบุว่ากดแช่บน Flic เพื่อทริกเกอร์โฟลว์
   
   คุณมีอิสระที่จะสร้างโฟลว์อื่น ๆ และทริกเกอร์ด้วยเหตุการณ์อื่นในรายการ**เหตุการณ์** ตัวอย่างเช่น คุณสามารถใช้เหตุการณ์**ดับเบิลคลิก**เพื่อบันทึกเวลาที่คุณออกจากลูกค้าได้

### <a name="configure-the-sheet"></a>กำหนดค่าในแผ่นงาน
   บนการ์ด**แทรกแถว**:

1. เลือกสเปรดชีตที่คุณสร้างไว้ก่อนหน้านี้จากรายการ**ไฟล์**
2. เลือกแผ่นงานจากรายการ**เวิร์กชีต**
   
   หมายเหตุ: อีกสองกล่องจะปรากฏบนการ์ด**แทรกแถว**หลังจากที่คุณเลือกแผ่นงาน กล่องเหล่านี้แทนสองคอลัมน์ในแผ่นงานที่คุณสร้างไว้ก่อนหน้านี้
3. เลือกกล่อง **ClickType** จากนั้นเลือกโทเค็น **Click type** (ชนิดของการคลิก)
4. เลือกกล่อง **Timestamp** จากนั้นเลือกโทเค็น **Click time** (เวลาที่คลิก)
   
    ![กำหนดค่าข้อมูล Google Sheets](./media/flic-button-flows/flick-insert-row-card.png)

### <a name="confirm-the-email-settings-are-correct"></a>ยืนยันว่าการตั้งค่าอีเมลถูกต้อง
1. ยืนยันว่าการ์ด **ส่งการแจ้งเตือนถึงฉันทางอีเมล** เหมือนกับสกรีนช็อตนี้
   
    ![ยืนยันอีเมลแจ้งเตือน](./media/flic-button-flows/email-settings.png)

### <a name="save-your-flow-and-test-it"></a>บันทึกโฟลว์ของคุณ และทดสอบ
1. ตั้งชื่อให้โฟลว์ของคุณ แล้วบันทึก
   
    ![บันทึกโฟลว์ของคุณ](./media/flic-button-flows/save.png)

ถ้าคุณได้ทำตาม กด Flic หนึ่งครั้งเพื่อทริกเกอร์โฟลว์ โฟลว์จะบันทึกชนิดของการคลิกและเวลาปัจจุบันในแผ่นงาน จากนั้น ส่งอีเมลถึงคุณ

1. กด Flic ของคุณหนึ่งครั้ง
2. เปิดแผ่นงานของคุณใน Google Sheets คุณควรเห็นคอลัมน์ **ClickType** และ **Timestamp** ที่รวบรวมข้อมูลการ "คลิก" และเวลา ตามลำดับ
   
    ![ดูผลลัพธ์การเรียกใช้](./media/flic-button-flows/flic-google-sheet-after-run.png)
3. คุณยังสามารถดูผลลัพธ์ของการเรียกใช้ จากเว็บไซต์ Microsoft Flow หรือ จากแอปอุปกรณ์เคลื่อนที่ Microsoft Flow นี่คือสกรีนช็อตของการทดสอบการเรียกใช้
   
    ![บันทึกโฟลว์ของคุณ](./media/flic-button-flows/flic-test-run-results-portal.png)
4. นี่คือเนื้อความของอีเมลแจ้งเตือนที่ฉันได้รับจากการเรียกใช้โฟลว์
   
    ![บันทึกโฟลว์ของคุณ](./media/flic-button-flows/flic-email-body.png)

สำหรับคะแนนพิเศษ พิจารณาขยายโฟลว์เพื่อบันทึกตำแหน่งที่ตั้งของคุณ (ละติจูดและลองจิจูด) โดยอัตโนมัติเมื่อกด Flic

## <a name="more-information"></a>ข้อมูลเพิ่มเติม
* [แชร์โฟลว์ของปุ่ม](share-buttons.md)
* เรียนรู้วิธีใช้[โทเค็นทริกเกอร์ปุ่ม](introduction-to-button-trigger-tokens.md)เพื่อส่งข้อมูลปัจจุบันเมื่อโฟลว์ของปุ่มคุณทำงาน
* ติดตั้งแอป Microsoft Flow สำหรับอุปกรณ์เคลื่อนที่ [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) หรือ [Windows Phone](https://aka.ms/flowmobilewindows)

