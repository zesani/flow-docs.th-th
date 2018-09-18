---
title: เริ่มต้นขั้นตอน ด้วย bttns | Microsoft Docs
description: เรียนรู้วิธีการเริ่มต้นโฟลว์ของคุณ ด้วย bttn
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
ms.date: 05/30/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 813ad16dbc9514975daadac456b73d98fc30db79
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689076"
---
# <a name="run-your-flows-with-physical-buttons-bttns-from-the-button-corporation-preview"></a>เรียกใช้โฟลว์ของคุณ ด้วยปุ่มที่มีอยู่จริง (bttns) จาก The Button Corporation (ตัวอย่าง)
ทริกเกอร์โฟลว์ของคุณ โดยการกด bttn (ปุ่มมีอยู่จริงที่ทำโดย[ The Button Corporation](https://my.bt.tn/)) ตัวอย่างเช่น คุณสามารถกด bttn ที่ทริกเกอร์โฟลว์เมื่อต้องทำงานเหล่านี้:

* ติดต่อฝ่ายสนับสนุนของคุณ ด้วยข้อมูลตำแหน่งที่ตั้ง
* ส่งอีเมลให้กับทีมของคุณ
* บล็อกปฏิทินของคุณ
* จัดลำดับใหม่

> [!IMPORTANT]
> คุณต้อง[ลงทะเบียน](https://my.bt.tn/)bttnของคุณก่อน แล้ว่คุณจะสามารถใช้ในโฟลว์
> 
> [!TIP]
> กำหนดค่าคุณสมบัติ bttn ทั้งหมดเช่นชื่อ ตำแหน่ง และอีเมลแอดเดรสบน[เว็บไซต์ bttn](https://my.bt.tn/)ก่อนที่คุณสร้างโฟลว์ของคุณ
> 
> 

คุณยังสามารถทริกเกอร์โฟลว์ โดยใช้[ปุ่ม Flic ที่มีอยู่จริง](flic-button-flows.md)

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น
* การเข้าถึง [Microsoft Flow](https://flow.microsoft.com)
* อย่างน้อยการ [ลงทะเบียน bttn](https://my.bt.tn/) หนึ่งตัว

## <a name="create-a-flow-thats-triggered-from-a-bttn"></a>สร้างโฟลว์ที่ถูกทริกเกอร์โดย Flic
ในการฝึกปฏิบัตินี้ เราใช้แม่แบบ helpdesk เพื่อสร้างโฟลว์ที่คุณสามารถทริกเกอร์ ด้วยการกด [bttn](https://my.bt.tn/) ครั้งเดียว เมื่อโฟลว์ทำงาน จะสร้างคำขอการสนับสนุน และส่งให้เจ้าหน้าที่ helpdesk คำขอการสนับสนุนจากเจ้าหน้าที่ helpdesk พร้อมกับตำแหน่งที่ตั้งของห้องที่ต้องการความช่วยเหลือ การฝึกปฏิบัตินี้สาธิตวิธีการสร้างโฟลว์นี้จากเทมเพลต แต่คุณสามารถใช้เทมเพลตที่ว่าง ที่ให้คุณควบคุมทั้งหมดผ่านทุกด้านของโฟลว์

คุณสามารถใช้แม่แบบ้ใดๆ เหล่านี้เพื่อสร้างโฟลว์สำหรับ bttn ของคุณได้อย่างรวดเร็ว และเชื่อมต่อกับ Zendesk Google และ SharePoint เป็นต้น:

![แม่แบบ bttn](./media/bttn-button-flows/bttn-templates.png)

เคล็ดลับ: สำหรับวัตถุประสงค์ในการฝึกปฏิบัตินี้ ตั้งชื่อ bttn ของคุณให้แสดงถึงห้องประชุมในอาคารสำนักงานแบบทั่วไป

การตั้งค่า bttn ของคุณควรมีลักษณะดังตัวอย่างนี้ (จากเว็บไซต์ bttn):

![แม่แบบ bttn](./media/bttn-button-flows/bttn-config.png)

หลังจากที่คุณได้ลงทะเบียน และกำหนดค่า bttn ของคุณ มาเริ่มการสร้างโฟลว์ของเรากันเลย

### <a name="sign-in-and-select-a-template"></a>ลงชื่อเข้าใช้ และเลือกเทมเพลต
1. ลงชื่อเข้าใช้ [Microsoft Flow](https://flow.microsoft.com)
   
    ![ลงชื่อเข้าใช้](./media/bttn-button-flows/sign-into-flow.png)
   
    หมายเหตุ: เป็นทางเลือก คุณสามารถสร้างโฟลว์ได้ในแอปมือถือ Microsoft Flow สำหรับ[Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)หรือ[Windows Phone](https://aka.ms/flowmobilewindows)ได้
2. ป้อน **flic** ลงในกล่องค้นหา จากนั้นเลือกไอคอนค้นหา
   
    ![ค้นหา](./media/bttn-button-flows/bttn-search-template.png)
   
    หลังจากที่คุณเลือกไอคอนค้นหา เทมเพลตทั้งหมดที่คุณสามารถใช้กับ bttns ที่ปรากฏขึ้น
3. เลือกแม่แบบ**ใช้ Bttn เรียกการสนับสนุนทางเทคนิคของประชุม**
   
    ![สนับสนุนเทมเพลต](./media/bttn-button-flows/bttn-select-template.png)

### <a name="authorize-microsoft-flow-to-connect-to-your-bttn"></a>อนุมัติ Microsoft Flow ให้เชื่อมต่อกับ bttn ของคุณ
1. ถ้าถูกถาม ให้ลงชื่อเข้าใช้เซอร์วิซ bttn และ Office 365 Outlook ซึ่งจะทำให้สามารถใช้ปุ่ม**ดำเนินการต่อ**
   
    ![ข้อมูลประจำตัว](./media/bttn-button-flows/bttn-provide-credentials.png)
2. เมื่อคุณลงชื่อเข้าใช้บริการ bttn คุณอนุญาต Microsoft Flow ให้ใช้ bttns ของคุณ
   
    **สิ่งสำคัญ**: ถ้าคุณไม่ได้อนุญาตให้ Microsoft Flow ใช้ bttns ของคุณ คุณไม่สามารถดูหรือเชื่อมต่อกับพวกมันจาก Microsoft Flow ได้
   
    ![อนุญาต](./media/bttn-button-flows/authorize-bttn.png)
3. หลังจากที่คุณลงชื่อเข้าใช้บริการทั้งสอง ให้เลือก**ดำเนินการต่อ**
   
    ![ดำเนินการต่อ](./media/bttn-button-flows/continue.png)

### <a name="select-the-bttn-that-triggers-the-flow"></a>เลือก bttn ซึ่ง่ทริกเกอร์โฟลว์
1. ในบัตร **เมื่อกด bttn** เปิดรายการรหัส bttn จากนั้นเลือก bttn ที่คุณต้องการใช้
   
    ![เลือก bttn](./media/bttn-button-flows/bttn-id.png)
   
    โฟลว์ของคุณตอนนี้ควรมีลักษณะดังตัวอย่างนี้
   
    ![ภาพรวมของโฟลว์](./media/bttn-button-flows/bttn-done.png)
2. ตั้งชื่อให้โฟลว์ของคุณ จากนั้นเลือก**สร้างโฟลว์**เพื่อบันทึก
   
    ![บันทึกโฟลว์](./media/bttn-button-flows/save.png)

## <a name="test-your-flow-and-confirm-results"></a>ทดสอบโฟลว์ของคุณ และยืนยันผลลัพธ์
1. กดปุ่มบน bttn ของคุณ
2. ดูประวัติการเรียกใช้โฟลว์ของคุณเพื่อยืนยันว่เรียกใช้เสร็จเรียบร้อยแล้ว
   
    คุณสามารถตรวจสอบประวัติการเรียกใช บนเว็บไซต์ Microsoft Flow หรือบนอุปกรณ์เคลื่อนที่ของคุณ
   
    หมายเหตุ: สถานะการรันถูกตั้งให้เป็น**กำลังรัน**จนกว่าจะมีคนเลือก**รับทราบ**ในอีเมลคำขอการสนับสนุน
3. นอกจากนี้คุณสามารถยืนยันได้ว่าอีเมลถูกส่งไปยังทีมสนับสนุน
   
    ถ้าคุณได้ติดตาม อีเมลที่สนับสนุนมีลักษณะคล้ายกับตัวอย่างนี้:
   
    ![](./media/bttn-button-flows/support-request-email.png)

## <a name="troubleshooting"></a>การแก้ไขปัญหา
* ถ้าโฟลว์ของคุณไม่ได้ถูกทริกเกอร์ ให้ลงชื่อเข้าใช้ในไซต์ของ The Button Corporation และยืนยันว่าปุ่มกิจกรรม (กด)กำลังถูกบันทึก
* นอกจากนี้คุณสามารถเจาะลึกกิจกรรมที่เรียกใช้บนไซต์ Microsoft Flow และตรวจสอบข้อผิดพลาด

## <a name="more-information"></a>ข้อมูลเพิ่มเติม
* [แชร์ button flow](share-buttons.md)
* เรียนรู้วิธีใช้[โทเค็นทริกเกอร์ปุ่ม](introduction-to-button-trigger-tokens.md)เพื่อส่งข้อมูลปัจจุบันเมื่อ button flow ของคุณทำงาน
* [ติดตั้งแอป Microsoft Flow สำหรับ Android](https://aka.ms/flowmobiledocsandroid)
* [ติดตั้งแอป Microsoft Flow สำหรับ iOS](https://aka.ms/flowmobiledocsios)

