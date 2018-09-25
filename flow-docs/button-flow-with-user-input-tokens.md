---
title: เรียนรู้วิธีการทำให้งานซ้ำ ๆ เป็นงานอัตโนมัติด้วยโฟลว์ของปุ่มที่รับข้อมูลป้อนเข้าจากผู้ใช้ | Microsoft Docs
description: Microsoft Flow ทำให้งานซ้ำ ๆ เป็นงานอัตโนมัติได้ง่าย ๆ โฟลว์ของคุณยังสามารถรับข้อมูลป้อนเข้าจากผู้ใช้เมื่อทำงานที่ซ้ำ ๆ กัน
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
ms.date: 02/15/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f87b0d93b912799a4977f347d89b12421cf42e70
ms.sourcegitcommit: ffed9f02092fbd19fc4108aee05dd40d1a2a3755
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/24/2018
ms.locfileid: "46711576"
---
# <a name="introducing-button-flows-with-user-input"></a>แนะนำโฟลว์ของปุ่มที่มีการป้อนข้อมูลของผู้ใช้
สร้างโฟลว์ของปุ่มเพื่อทำงานที่เป็นประจำ เพียงแค่แตะที่ปุ่ม กำหนดค่าโฟลว์ของคุณ ให้ผู้ใช้สามารถระบุรายละเอียดที่จะใช้เมื่อโฟลว์ทำงาน หัวข้อนี้แนะนำคุณ ไปตามขั้นตอนการสร้างโฟลว์ของปุ่ม ที่รับการป้อนข้อมูลของผู้ใช้ แล้วเรียกใช้โฟลว์ของปุ่ม โดยเน้นที่วิธีการให้ผู้ใช้ป้อนข้อมูล

คุณสามารถสร้างโฟลว์ของปุ่มในเว็บไซต์ Microsoft Flow หรือแอปสำหรับอุปกรณ์เคลื่อนที่สำหรับ Microsoft Flow สำหรับหัวข้อนี้ คุณจะใช้เว็บไซต์

### <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น
* บัญชีผู้ใช้บนเว็บไซต์ Microsoft Flow

## <a name="open-the-template"></a>เปิดเทมเพลต
1. ลงชื่อเข้าใช้[เว็บไซต์ Microsoft Flow](https://flow.microsoft.com) ใส่ **Visual Studio** ใน กล่องค้นหา และจากนั้นคลิกหรือแตะไอคอนค้นหา เพื่อค้นหาเทมเพลตทั้งหมดที่เกี่ยวข้องกับ Visual Studio:
   
    ![](./media/button-flow-with-user-input-tokens/1.png)  
2. เลือกเทมเพลต**เปิดบั๊กความสำคัญระดับ 2 ใน Visual Studio**:
   
    ![](./media/button-flow-with-user-input-tokens/2.png)  
3. เลือกปุ่ม**ใช้เทมเพลตนี้**:
   
    ![](./media/button-flow-with-user-input-tokens/3.png)  
   
    เทมเพลตนี้ใช้ Visual Studio Team Services (VSTS) และบริการการแจ้งเตือนแบบพุช คุณจะต้องลงชื่อเข้าใช้บริการเหล่านี้ ถ้าคุณยังไม่มีการเชื่อมต่อไปยังบริการ ปุ่ม**ลงชื่อเข้าใช้**จะปรากฏขึ้นถ้าคุณจำเป็นต้องลงชื่อเข้าใช้บริการ
4. หลังจากที่คุณลงชื่อเข้าใช้บริการที่จำเป็นทั้งหมด เลือกปุ่ม**ดำเนินการต่อ**:
   
    ![](./media/button-flow-with-user-input-tokens/4.png)  
5. (ไม่บังคับ) เปลี่ยนชื่อของโฟลว์ โดยการพิมพ์ชื่อที่คุณเลือกลงในกล่องด้านบนของพอร์ทัล:
   
    ![](./media/button-flow-with-user-input-tokens/5.png)

## <a name="customize-the-user-input"></a>กำหนดค่าการป้อนข้อมูลของผู้ใช้
1. ในการ์ดทริกเกอร์ เลือก**แก้ไข**:
   
    ![](./media/button-flow-with-user-input-tokens/6.png)  
2. เลือกไอคอน **+** เพื่อขยายหน้าให้คุณสามารถเพิ่มฟิลด์ป้อนข้อมูลแบบกำหนดเอง:
   
    ![](./media/button-flow-with-user-input-tokens/7.png)
3. ใส่ค่า**ชื่อเรื่องการป้อนข้อมูล** และ**รายละเอียดการป้อนข้อมูล** สำหรับแต่ละฟิลด์แบบกำหนดเองที่คุณต้องการให้ เมื่อมีคนเรียกใช้โฟลว์ของคุณ  
   
    ในตัวอย่างนี้ คุณจะสร้างฟิลด์ป้อนข้อมูลแบบกำหนดเองสองฟิลด์ (**Bug repro steps** และ **Bug severity**) เพื่อให้ทุกคนที่ใช้โฟลว์นี้สามารถใส่ขั้นตอนที่ทำให้เกิดจุดบกพร่อง และจัดอันดับความรุนแรงของจุดบกพร่อง:  
   
    ![](./media/button-flow-with-user-input-tokens/8.png)

## <a name="customize-the-bug"></a>กำหนดค่าจุดบกพร่อง
1. แตะที่แถบชื่อเรื่องของการ์ด**สร้างรายการงานใหม่**:
   
    ![](./media/button-flow-with-user-input-tokens/9.png)  
2. เลือกตัวเลือกที่เหมาะสมสำหรับสภาพแวดล้อม VSTS ของคุณ จากนั้นเลือก**แก้ไข**:
   
    ตัวอย่างเช่น เชื่อมต่อกับ myinstance.visualstudio.com โดยการพิมพ์ **myinstance**
   
    ![](./media/button-flow-with-user-input-tokens/10.png)  
3. เลือก**แสดงตัวเลือกขั้นสูง**เพื่อแสดงฟิลด์อื่น ๆ สำหรับการ์ดนี้:
   
    ![](./media/button-flow-with-user-input-tokens/11.png)  
4. วางเคอร์เซอร์ไว้ก่อนโทเค็น **Bug title** และพิมพ์ "Severity: " ลงในฟิลด์ข้อความ**ชื่อเรื่อง**
5. เมื่อเคอร์เซอร์ยังอยู่ในฟิลด์ข้อความชื่อเรื่อง เลือกโทเค็น **Bug severity** แล้วพิมพ์ "--"  
6. ในฟิลด์ข้อความ**คำอธิบาย** วางเคอร์เซอร์ของคุณหลังโทเค็น **Bug description** พอดี จากนั้นกด Enter เพื่อเริ่มบรรทัดใหม่
7. วางเคอร์เซอร์ของคุณบนบรรทัดใหม่ จากนั้นเลือกโทเค็น **Bug Repro steps**:
   
    ![](./media/button-flow-with-user-input-tokens/12.png)

## <a name="customize-the-push-notification"></a>กำหนดค่าการแจ้งเตือนแบบพุช
1. แตะแถบชื่อเรื่องบนการ์ด**ส่งการแจ้งเตือนแบบพุช**เพื่อขยาย
2. ในรายการของโทเค็นเนื้อหาแบบไดนามิก เลือก**ดูเพิ่มเติม**แล้ว เพิ่มโทเค็น **URL** ในฟิลด์ข้อความ**ลิงก์**
3. ในฟิลด์ข้อความ**ป้ายชื่อลิงก์** เพิ่มโทเค็น **Id**:
   
    ![](./media/button-flow-with-user-input-tokens/13.png)  
4. แตะ**สร้างโฟลว์**บนเมนูเพื่อสร้างโฟลว์ของคุณ:  ![](./media/button-flow-with-user-input-tokens/14.png)  

## <a name="run-your-flow"></a>เรียกใช้โฟลว์ของคุณ
ในการฝึกปฏิบัตินี้ คุณจะใช้แอปสำหรับอุปกรณ์ที่ Microsoft Flow เพื่อเรียกใช้โฟลว์ปุ่มที่คุณเพิ่งสร้าง คุณจะให้ผู้ใช้ป้อนข้อมูลทั้งหมดที่จำเป็นในการสร้างรายงานจุดบกพร่อง ที่มีชื่อเรื่อง, คำอธิบาย, ขั้นตอนทำซ้ำ และระดับความร้ายแรง  

1. ในแอปสำหรับอุปกรณ์เคลื่อนที่สำหรับ Microsoft Flow แตะแท็บ**ปุ่ม** จากนั้น แตะปุ่ม **Create bug report with steps**
   
    ![](./media/button-flow-with-user-input-tokens/runmt1.png)  
2. ใส่ชื่อเรื่องสำหรับจุดบกพร่องที่คุณรายงาน จากนั้น แตะ**ถัดไป** ตัวอย่างเช่น:
   
    ![](./media/button-flow-with-user-input-tokens/runmt2.png)  
3. ป้อนคำอธิบายของจุดบกพร่องที่คุณรายงาน จากนั้น แตะ**ถัดไป** ตัวอย่างเช่น:
   
    ![](./media/button-flow-with-user-input-tokens/runmt3.png)  
4. ใส่ขั้นตอนในการทำซ้ำจุดบกพร่องที่คุณรายงาน จากนั้น แตะ**ถัดไป** ตัวอย่างเช่น:
   
    ![](./media/button-flow-with-user-input-tokens/runmt3-1.png)  
5. ป้อนความรุนแรงของจุดบกพร่องที่คุณรายงาน จากนั้น แตะ**เสร็จสิ้น**:  
    ![](./media/button-flow-with-user-input-tokens/runmt3-2.png)  
   
    โฟลว์ทำงาน
6. (ไม่บังคับ) แตะแท็บ**กิจกรรม**เพื่อแสดงผลลัพธ์
   
    ![](./media/button-flow-with-user-input-tokens/runmt5.png)  
7. (ไม่บังคับ) แสดงผลลัพธ์โดยละเอียดของการทำงานของโฟลว์ โดยการแตะขั้นตอน**สร้างรายการงานใหม่**
   
    ![](./media/button-flow-with-user-input-tokens/runmt6.png)  

## <a name="next-steps"></a>ขั้นตอนถัดไป
* [แชร์ button flow](share-buttons.md)
* [เรียนรู้เกี่ยวกับ button flow](introduction-to-button-flows.md)  
* [เรียนรู้เกี่ยวกับโฟลว์ของปุ่มที่มีโทเค็นทริกเกอร์](introduction-to-button-trigger-tokens.md)  

