---
title: เรียนรู้วิธีการทำให้งานเป็นแบบอัตโนมัติ และเรียกใช้งานที่ซ้ำ ๆ ด้วยโฟลว์ของปุ่ม | Microsoft Docs
description: บทนำสู่โฟลว์ของปุ่ม
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
ms.date: 01/30/2017
ms.author: deonhe
ms.openlocfilehash: 558570733819e1fde6c1845ed5ca9debe9232c88
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "31001294"
---
# <a name="introducing-button-flows"></a>แนะนำโฟลว์ของปุ่ม
## <a name="what-are-button-flows"></a>โฟลว์ของปุ่มคืออะไร?
มีงานที่ซ้ำ ๆ มากมาย ที่เราหวังว่าจะเรียกใช้งานเพียงแค่แตะปุ่ม ตัวอย่างเช่น คุณอาจต้องส่งอีเมลให้ทีมของคุณอย่างรวดเร็ว เพื่อเตือนให้พวกเขาเข้าร่วมการประชุมทีมประจำวัน หรือคุณอาจต้องการเริ่มการสร้าง หรือบิลด์ (build) ใน Visual Studio Online จากฐานโค้ดของคุณ หลังจากที่คุณได้รับการแจ้งว่า จะไม่มีเช็คอินที่วางแผนไว้แล้วอีกสำหรับวันนี้ โฟลว์ของปุ่มให้คุณสามารถทำงานเหล่านี้ และอื่น ๆ อีกมากให้สำเร็จโดยการแตะปุ่มบนอุปกรณ์เคลื่อนที่ของคุณ

**หมายเหตุ** คุณสามารถสร้างโฟลว์ของปุ่ม จากอุปกรณ์เคลื่อนที่ของคุณ หรือจากพอร์ทัล Flow ได้  
  ![รูปภาพรวม](./media/introduction-to-button-flows/buttons-montage.png)  

## <a name="why-create-buttons"></a>ทำไมต้องสร้างปุ่ม?
สร้างปุ่มเพื่อให้คุณสามารถเรียกใช้งานซ้ำ ๆ จากทุกที่ทุกเวลา ได้อย่างง่ายดาย โดยใช้อุปกรณ์เคลื่อนที่ของคุณ การดำเนินการโดยปุ่ม ให้คุณประหยัดเวลา เนื่องจากงานที่ทำจะเป็นแบบอัตโนมัติ และมีข้อผิดพลาดน้อยกว่าการที่คุณทำงานด้วยตนเอง  

## <a name="create-a-button"></a>สร้างปุ่ม
### <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น
* การเข้าถึง Flow ผู้ดูแลระบบของคุณสามารถให้สิทธิ์การเข้าถึงแก่คุณได้
* บัญชีผู้ใช้ที่มีสิทธิ์การใช้ตัวเชื่อมต่อเพื่อสร้างปุ่มของคุณ ตัวอย่างเช่น คุณจะต้องมีบัญชี Dropbox เพื่อสร้างปุ่มที่เข้าถึง Dropbox

### <a name="from-the-portal"></a>จากพอร์ทัล
ในการฝึกปฏิบัตินี้ เรามาสร้างปุ่มที่เริ่มต้นการสร้างใน Visual Studio Online (VSO) และส่งการแจ้งเตือนเพื่อแจ้งให้คุณทราบเมื่อการสร้างได้เริ่มต้น:  

1. เลือกรายการดรอปดาวน์**กำลังแสดง** และเลือกประเภท**ปุ่ม** ซึ่งจะกรองรายการของเทมเพลต สำหรับเฉพาะที่สามารถใช้ในโฟลว์ของปุ่ม  
   ![รูปภาพรวม](./media/introduction-to-button-flows/create-button-1.png)   
2. เลือกเทมเพลต**เรียกการสร้างใหม่ใน VSO** จากรายการของเทมเพลต  
   ![รูปภาพรวม](./media/introduction-to-button-flows/create-button-2.png)  
3. เลือกปุ่ม**ใช้เทมเพลตนี้**บนหน้า**เรียกการสร้างใหม่ใน VSO**   
   ![รูปภาพรวม](./media/introduction-to-button-flows/create-button-3.png)  
4. ถ้าคุณยังไม่ได้ลงชื่อเข้าใช้ คุณจะได้รับพร้อมท์ให้ทำในตอนนี้:  
   ![รูปภาพรวม](./media/introduction-to-button-flows/create-button-4.png)  
5. หลังจากที่คุณได้ลงชื่อเข้าใช้ Flow คุณจะได้รับการพร้อมท์ให้ลงชื่อเข้าใช้ตัวเชื่อมต่อที่ใช้ในเทมเพลตที่คุณเลือก ในตัวอย่างนี้ ในขั้นตอนที่ 2 ด้านบน เราเลือกเทมเพลต**เรียกการสร้างใหม่ใน VSO** ดังนั้นเราจำเป็นต้องลงชื่อเข้าใช้ใน VSO (และตัวเชื่อมต่ออื่น ๆ ที่คุณกำลังทำงานด้วย) ถ้าคุณยังไม่ได้ลงชื่อเข้าใช้:  
   ![รูปภาพรวม](./media/introduction-to-button-flows/create-button-pre-req-1.png)    
6. เลือกปุ่ม**ยอมรับ**หากคุณยอมรับเงื่อนไขการอนุญาต Flow ให้เข้าถึงบัญชี VSO ของคุณ  
   ![รูปภาพรวม](./media/introduction-to-button-flows/create-button-5.png)   
   **หมายเหตุ** คุณจำเป็นต้องอนุญาตตัวเชื่อมต่อแต่ละตัวในทำนองเดียวกัน ตัวออกแบบควรจะปรากฏคล้ายกับรูปนี้ เมื่อคุณพร้อมที่จะไปขั้นตอนถัดไป เลือกปุ่ม**ดำเนินการต่อ**เพื่อไปต่อ:  
   ![รูปภาพรวม](./media/introduction-to-button-flows/create-button-6.png)   
7. ในตอนนี้คุณพร้อมที่จะกำหนดค่าคุณสมบัติสำหรับรุ่นที่คุณต้องการเริ่มต้นสร้าง:    
   ![รูปภาพรวม](./media/introduction-to-button-flows/create-button-7.png)  
8. เลือกหรือป้อนค่า**ชื่อบัญชี**, **ชื่อโครงการ**, **Id ข้อกำหนดของบิลด์**, **สาขาต้นทาง** และเลือก**พารามิเตอร์** (ไม่บังคับ) ในการ์ด**คิวการสร้างใหม่**:    
   ![รูปภาพรวม](./media/introduction-to-button-flows/create-button-8.png)  
9. ถัดไป กำหนดคุณสมบัติของการแจ้งเตือนแบบพุชบนการ์ด**ส่งการแจ้งเตือนแบบพุช** ตามค่าเริ่มต้น แจ้งเตือนนี้ถูกจะกำหนดค่าให้ส่งลิงก์แบบ HTML ไปยังเว็บเพจที่แสดงสถานะของการสร้าง:  
   ![รูปภาพรวม](./media/introduction-to-button-flows/create-button-9.png)  
10. เลือกปุ่ม**สร้างโฟลว์**เพื่อบันทึกโฟลว์ของปุ่มคุณ: ![รูปภาพรวม](./media/introduction-to-button-flows/create-button-10.png)  
11. คุณควรจะเห็นข้อความสำเร็จนี้ในเวลาไม่นาน:  
    ![รูปภาพรวม](./media/introduction-to-button-flows/create-button-11.png)  

ยินดีด้วย คุณได้สร้างโฟลว์ของปุ่มแล้ว! คุณสามารถเรียกใช้โฟลว์ของปุ่มนี้ได้ทุกที่ทุกเวลา จากแท็บ**ปุ่ม**ในแอป Flow ได้ เพียงแค่กด "ปุ่ม" แล้วปุ่มจะทำงาน! แอปสำหรับอุปกรณ์เคลื่อนที่ของ Microsoft Flow มีสำหรับ [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) หรือ [Windows Phone](https://aka.ms/flowmobilewindows)

### <a name="from-your-mobile-device"></a>จากอุปกรณ์เคลื่อนที่ของคุณ
**หมายเหตุ**: ถึงแม้ว่าการฝึกปฏิบัตินี้จะแสดงหน้าจอจากอุปกรณ์ Android หน้าจอและประสบการณ์การใช้งานบนอุปกรณ์ iOS จะคล้ายกัน

ในแอป Flow:

1. เลือกแท็บ**เรียกดู** แล้วเลื่อนไปที่ประเภท**ปุ่ม**  
   ![รูปภาพรวม](./media/introduction-to-button-flows/create-button-from-mobile-1.png)  
2. เลือกลิงก์**ดูทั้งหมด** ซึ่งแสดงเทมเพลตปุ่มที่พร้อมทำงานทั้งหมด     
   ![รูปภาพรวม](./media/introduction-to-button-flows/create-button-from-mobile-2.png)  
3. เลือกเทมเพลต**ส่งอีเมลเพื่อเตือนให้ทีมของคุณเข้าร่วมการประชุม**    
   ![รูปภาพรวม](./media/introduction-to-button-flows/create-button-from-mobile-3.png)  
4. เลือกลิงก์**ใช้เทมเพลตนี้** ที่ด้านล่างของหน้า    
   ![รูปภาพรวม](./media/introduction-to-button-flows/create-button-from-mobile-4.png)  
5. คุณจะต้องลงชื่อเข้าใช้บริการทั้งหมดที่ใช้ในเทมเพลตนี้:    
   ![รูปภาพรวม](./media/introduction-to-button-flows/create-button-from-mobile-5.png)  
6. เลือกลิงก์**ถัดไป**หลังจากที่คุณได้ลงชื่อเข้าใช้บริการทั้งหมด      
   ![รูปภาพรวม](./media/introduction-to-button-flows/create-button-from-mobile-6.png)  
7. เลือกลิงก์**สร้าง** ที่นี่คุณยังสามารถตรวจทานโฟลว์ และทำการแก้ไขตามที่คุณต้องการ เช่น การปรับแต่งอีเมล        
   ![รูปภาพรวม](./media/introduction-to-button-flows/create-button-from-mobile-7.png)  
8. สักครู่ โฟลว์ของปุ่มจะถูกสร้างขึ้น เลือก**ดูโฟลว์ของฉัน**:   
   ![รูปภาพรวม](./media/introduction-to-button-flows/create-button-from-mobile-8.png)  
9. ดูโฟลว์ทั้งหมดของคุณบนแท็บ**โฟลว์ของฉัน**  
   ![รูปภาพรวม](./media/introduction-to-button-flows/create-button-from-mobile-9.png)  

ยินดีด้วย คุณได้สร้างโฟลว์ของปุ่มแล้ว! คุณสามารถเรียกใช้โฟลว์ของปุ่มนี้ได้ทุกที่ทุกเวลา จากแท็บ**ปุ่ม**ในแอป Flow ได้ เพียงแค่กด "ปุ่ม" แล้วปุ่มจะทำงาน! แอป Flow ขณะนี้พร้อมใช้งานบนอุปกรณ์เคลื่อนที่ Android และ iOS  

![รูปภาพรวม](./media/introduction-to-button-flows/create-button-from-mobile-10.png)  

## <a name="trigger-a-button-flow"></a>ทริกเกอร์โฟลว์ของปุ่ม
หลังจากที่คุณได้สร้างโฟลว์ของปุ่ม ถึงเวลาที่จะเรียกใช้แล้ว เนื่องจากคุณสามารถเรียกใช้โฟลว์ของปุ่มจากแอป Flow เท่านั้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งโฟลว์บนอุปกรณ์มือถือ Android หรือ iOS  

1. ตอนนี้ เปิดใช้แอปโฟลว์ แตะแท็บ**ปุ่ม**ที่อยู่ที่ด้านล่างของหน้า แตะ*ปุ่ม*ที่แทนโฟลว์ของปุ่มที่คุณต้องการทริกเกอร์:  
   ![รูปภาพรวม](./media/introduction-to-button-flows/trigger-button-1.png)   
2. ดูความคืบหน้าขณะที่โฟลว์ทำงาน:  
   ![รูปภาพรวม](./media/introduction-to-button-flows/trigger-button-2.png)   
3. สุดท้าย หน้าจะอัปเดต แสดงว่าโฟลว์ของปุ่มทำงานเสร็จแล้ว:  
   ![รูปภาพรวม](./media/introduction-to-button-flows/trigger-button-3.png)   

นั่นคือทั้งหมดของการเรียกใช้โฟลว์ 

คุณควรได้รับการแจ้งเตือนแบบพุช ว่าอีเมลถูกส่งไปแล้ว  

## <a name="monitor-your-button-flow-runs"></a>ตรวจสอบการทำงานของโฟลว์ของปุ่มคุณ
คุณสามารถตรวจสอบโฟลว์ของปุ่มจากแท็บ**กิจกรรม**ของแอป Flow:   
![รูปภาพรวม](./media/introduction-to-button-flows/create-button-from-mobile-13.png)  

**หมายเหตุ**: แตะที่กิจกรรมใด ๆ เพื่อเจาะลึกลงในผลลัพธ์การทำงานเพื่อเรียนรู้เกี่ยวกับการทำงาน  

![รูปภาพรวม](./media/introduction-to-button-flows/activity-details-1.png)  

## <a name="manage-button-flows"></a>จัดการโฟลว์ของปุ่ม
คุณสามารถควบคุมโฟลว์ของปุ่มคุณได้เต็มรูปแบบ เพื่อให้คุณสามารถเปิด/ปิดใช้งาน, แก้ไข หรือลบปุ่มได้ ทุกที่ทุกเวลา จากแอปสำหรับอุปกรณ์เคลื่อนที่ หรือจากพอร์ทัลของ Flow เลือก**โฟลว์ของฉัน**เพื่อเริ่มต้นจัดการโฟลว์ของคุณ    

บนแท็บ**โฟลว์ของฉัน**ของแอป Flow:

1. เลือกโฟลว์ที่คุณต้องการจัดการ:    
   ![รูปภาพรวม](./media/introduction-to-button-flows/trigger-button-4.png)   
2. คุณสามารถแตะตัวเลือกเหล่านี้ ขึ้นอยู่กับว่าคุณต้องการทำอะไร:    
   ![รูปภาพรวม](./media/introduction-to-button-flows/manage-flow-1.png)  
3. แตะ**ลบโฟลว์**เพื่อลบโฟลว์  

**หมายเหตุ** ประวัติการเรียกใช้ทั้งหมดจะถูกลบเมื่อคุณลบโฟลว์:   
![รูปภาพรวม](./media/introduction-to-button-flows/manage-flow-2.png)   

1. แตะ**อัปเดต** หลังจากที่คุณแก้ไขโฟลว์ของปุ่มเสร็จ เพื่อบันทึกการเปลี่ยนแปลงของคุณ:   
   ![รูปภาพรวม](./media/introduction-to-button-flows/manage-flow-3.png)   
2. แตะ**ประวัติการเรียกใช้** เพื่อดูผลลัพธ์ของการทำงนทั้งหมดของโฟลว์ของปุ่มนั้น:    
   ![รูปภาพรวม](./media/introduction-to-button-flows/manage-flow-4.png)  
3. ถ้าคุณปิดใช้งานโฟลว์ จะมีให้ใช้งานในแท็บ**ปุ่ม**:    
   ![รูปภาพรวม](./media/introduction-to-button-flows/manage-flow-5.png)  

## <a name="next-steps"></a>ขั้นตอนถัดไป
* [แชร์โฟลว์ของปุ่ม](share-buttons.md)
* เรียนรู้วิธีใช้[โทเค็นทริกเกอร์ปุ่ม](introduction-to-button-trigger-tokens.md) เพื่อส่งข้อมูลแบบเรียลไทม์เมื่อโฟลว์ของปุ่มคุณทำงาน
* ติดตั้งแอป Microsoft Flow สำหรับอุปกรณ์เคลื่อนที่ [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) หรือ [Windows Phone](https://aka.ms/flowmobilewindows)

