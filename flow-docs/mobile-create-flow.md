---
title: สร้างโฟลว์จากโทรศัพท์ของคุณ | Microsoft Docs
description: สร้างโฟลว์จากเทมเพลต ตัวอย่างเช่น ส่งการแจ้งเตือนเมื่อคุณได้รับจดหมายจากแอดเดรสที่คุณระบุ
services: ''
suite: flow
documentationcenter: na
author: adiregev
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/18/2016
ms.author: adiregev
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f87320c61427957c02ff75675e4e15b938ac99f4
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/12/2018
ms.locfileid: "44688340"
---
# <a name="create-a-flow-from-your-phone-by-using-microsoft-flow"></a>สร้างโฟลว์จากโทรศัพท์ของคุณโดยใช้ Microsoft Flow
สร้างโฟลว์จากโทรศัพท์ของคุณ โดยใช้เทมเพลต ซึ่งคุณสามารถค้นหา โดยการค้นหาผ่านรายการของบริการ โดยเรียกดูประเภท หรือระบุคำสำคัญ ทำตามขั้นตอนในหัวข้อนี้เพื่อสร้างโฟลว์ที่ส่งการแจ้งเตือนไปยังโทรศัพท์ของคุณเมื่อคุณได้รับอีเมลจากผู้จัดการของคุณ

ถ้าคุณไม่คุ้นเคยกับ Microsoft Flow, [ให้ดูภาพรวม](getting-started.md)

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น
* [บัญชีผู้ใช้สำหรับ Microsoft Flow](sign-up-sign-in.md)
* แอป Microsoft Flow สำหรับอุปกรณ์เคลื่อนที่[Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)หรือ[Windows Phone](https://aka.ms/flowmobilewindows)บน[อุปกรณ์ที่รองรับ](getting-started.md#use-the-mobile-app) รูปภาพในหัวข้อนี้แสดงเวอร์ชัน iPhone ของแอป แต่อินเทอร์เฟซบนอุปกรณ์ Android หรือ Windows Phone จะคล้ายกัน
* เมื่อต้องใช้แม่แบบที่แสดงในหัวข้อนี้ คุณจะต้อง:
  
  * ข้อมูลประจำตัว Office 365
  * ส่งการแจ้งเตือนที่เปิดใช้งานบนโทรศัพท์ของคุณ

## <a name="find-a-template"></a>หาเทมเพลต
1. เปิดแอป mobile และจากนั้น แตะ**เรียกดู**ที่ด้านล่างของหน้าจอ
   
    ![ไอคอนเรียกดู](./media/mobile-create-flow/browse-icon.png)
   
    คุณสามารถค้นหาเทมเพลตในวิธีเหล่านี้:
   
   * ระบุคำสำคัญในกล่องค้นหาที่ด้านบนของหน้าจอ
   * แตะตัวเลือกในรายการของบริการ
   * เลื่อนลงเพื่อแสดงหลากหลายประเภท และจากนั้น แตะเทมเพลตในประเภทใดก็ตาม
     
       ![เรียกดูแท็บ](./media/mobile-create-flow/browse-tab.png)
     
     สำหรับบทเรียนนี้ คุณจะเปิดแม่แบบที่ส่งการแจ้งเตือนเมื่อคุณได้รับเมลจากผู้จัดการของคุณ
2. ในรายการของบริการ แตะ**ดูทั้งหมด**
   
    ![แสดงรายการของบริการ](./media/mobile-create-flow/list-services.png)
3. แตะไอคอนเพื่อ**แจ้งเตือนแบบ Push**
   
    ![แจ้งเตือนแบบ Push](./media/mobile-create-flow/push-notifications.png)
4. ในแถบการค้นหา พิมพ์**อีเมล**แล้ว แตะแม่แบบที่จะส่งการแจ้งเตือนเมื่อคุณได้รับข้อความจากผู้จัดการของคุณ
   
    ![เลือกเทมเพลต](./media/mobile-create-flow/choose-template.png)
5. ในหน้าจอที่ให้รายละเอียดเกี่ยวกับเทมเพลตที่คุณได้เลือก แตะ**ใช้เทมเพลตนี้**
   
    ![ยืนยันเทมเพลต](./media/mobile-create-flow/confirm-template.png)

## <a name="finish-the-flow"></a>จบโฟลว์
1. ถ้าถูกถาม ให้แตะ**ลงชื่อเข้าใช้**และระบุข้อมูลประจำตัวของคุณสำหรับ Office 365 Outlook ผู้ใช้ Office 365 หรือทั้งสองอย่าง
   
    ![ลงชื่อเข้าใช้ Office 365](./media/mobile-create-flow/office-signin.png)
   
    คุณสามารถใช้การเชื่อมต่อเดียวกันเมื่อคุณสร้างโฟลว์อื่น ๆ
2. ในมุมขวาบน แตะ**ถัดไป**
   
    ![แตะถัดไป](./media/mobile-create-flow/next.png)
   
    หน้าจอถัดไปแสดงเหตุการณ์ทริกเกอร์และการดำเนินการที่เป็นผลลัพธ์ทั้งหมด
   
    ![ทริกเกอร์เหตุการณ์และการดำเนินการ](./media/mobile-create-flow/flow-structure.png)
   
    สำหรับเทมเพลตนี้ เมลใหม่ทริกเกอร์โฟลว์ ที่ดึงข้อมูลของคุณ (รวมถึงที่อยู่ของผู้จัดการของคุณ) และส่งการแจ้งเตือนคุณเมื่อคุณได้รับเมลจากที่อยู่นั้น เทมเพลตบางตัวต้องเป็นแบบกำหนดเองเพื่อให้ทำงานอย่างถูกต้อง แต่ไมใช่่แม่แบบนี้
3. (ไม่บังคับ) ใกล้กับด้านบนของหน้าจอ พิมพ์ชื่อโฟลว์ที่แตกต่างกัน
   
    ![เปลี่ยนชื่อโฟลว์](./media/mobile-create-flow/rename-flow.png)
4. ในมุมขวาบน แตะ**สร้าง**
   
    ![สร้างโฟลว์](./media/mobile-create-flow/create-flow.png)
   
    โฟลว์ของคุณถูกสร้างขึ้น และจะตรวจหาอีเมลจากผู้จัดการของคุณจนกว่าคุณหยุดชั่วคราวหรือลบโฟลว์

## <a name="next-steps"></a>ขั้นตอนถัดไป
* [ติดตามกิจกรรมของโฟลว์ของคุณ](mobile-monitor-activity.md)
* [จัดการโฟลว์ของคุณ](mobile-manage-flows.md)

