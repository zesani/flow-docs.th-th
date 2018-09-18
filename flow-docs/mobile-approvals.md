---
title: อนุมัติคำขอบนอุปกรณ์เคลื่อนที่ | Microsoft Docs
description: ใช้อุปกรณ์เคลื่อนที่เพื่ออนุมัติคำขอที่สร้างขึ้นใน Microsoft Flow
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
ms.date: 07/20/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b41397d74c7396081154526ad2e248cb293e2460
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689605"
---
# <a name="approve-requests-on-your-mobile-device-by-using-microsoft-flow"></a>อนุมัติคำขอบนอุปกรณ์เคลื่อนที่ของคุณโดยใช้ Microsoft Flow
ถ้าโฟลว์ระบุตัวคุณว่าเป็นผู้อนุมัติ และคุณได้ติดตั้งแอปสำหรับอุปกรณ์เคลื่อนที่ Microsoft Flow แล้ว คุณได้รับการแจ้งเตือนพุชเมื่อใดก็ ตามที่มีการร้องขอการอนุมัติจากคุณ

บทความนี้จะแนะนำให้คุณเข้าใจสถานการณ์สมมติทั่วไปบางสถานการณ์ที่คุณมักจะพบในขณะที่คุณจัดการการร้องขอการอนุมัติในแอปสำหรับอุปกรณ์เคลื่อนที่ Microsoft Flow

> [!NOTE]
> รูปภาพในหัวข้อนี้มาจากอุปกรณ์ Android อย่างไรก็ตาม ประสบการณ์การใช้งานบน iOS จะคล้ายกัน
> 
> 

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น
ในการฝึกปฏิบัตินี้ให้สำเร็จ คุณจำเป็นต้องมี:

* อุปกรณ์ [Android](https://aka.ms/flowmobiledocsandroid) หรือ [iOS](https://aka.ms/flowmobiledocsios) ที่ใช้งานแอปสำหรับอุปกรณ์เคลื่อนที่ Microsoft Flow
* เพื่อให้ได้รับกำหนดเป็นผู้อนุมัติในโฟลว์การอนุมัติ
* คำขอระหว่างรอการอนุมัติ

## <a name="view-pending-requests"></a>ดูคำขอระหว่างรอดำเนินการ
1. เปิดแอปอุปกรณ์เคลื่อนที่ Microsoft Flow
   
    ![เปิดใช้งานแอปอุปกรณ์เคลื่อนที่](./media/mobile-approvals/open-app.png)
2. เลือก**การอนุมัติ**ที่มุมขวาบน
   
    ![เลือกการอนุมัติ](./media/mobile-approvals/select-approvals.png)
3. ดูการอนุมัติที่ค้างอยู่ทั้งหมด:
   
    ![ดูคำขออนุมัติที่ค้างอยู่](./media/mobile-approvals/show-pending-approval-requests.png)

ถ้าคุณไม่มีคำขออนุมัติที่ค้างอยู่ ให้สร้าง[โฟลว์การอนุมัติ](modern-approvals.md) ตั้งค่าให้ตนเองเป็นผู้อนุมัติ จากนั้นทริกเกอร์โฟลว์ คำขอการอนุมัติจะปรากฏในศูนย์การอนุมัติสองสามวินาทีหลังจากที่โฟลว์ทริกเกอร์ และส่งคำขออนุมัติ

## <a name="approve-requests-and-leave-an-optional-comment"></a>อนุมัติคำขอและใส่ข้อคิดเห็น (เป็นทางเลือก)
1. ถ้าคุณยังไม่ได้ทำขั้นตอนนั้น ให้ทำตามขั้นตอนก่อนหน้าเพื่อ[ดูคำขอที่ค้างอยู่](mobile-approvals.md#view-pending-requests)
2. เลือก**อนุมัติ**ในคำขอที่คุณต้องการอนุมัติ
   
    ![เลือกอนุมัติ](./media/mobile-approvals/select-approve.png)
3. (เป็นทางเลือก) เลือก**เพิ่มข้อคิดเห็น (เป็นทางเลือก)**
   
    ![เลือกเพิ่มข้อคิดเห็น](./media/mobile-approvals/select-add-comment.png)
   
    ใส่ข้อคิดเห็นบนหน้าจอ**เพิ่มข้อคิดเห็น**
   
    ![ใส่ข้อคิดเห็นของคุณ](./media/mobile-approvals/enter-comment-for-approval.png)
4. เลือก**ยืนยัน**ที่มุมบนขวา
   
    ![ยืนยันว่าคุณทำเสร็จแล้ว](./media/mobile-approvals/tap-confirm-button.png)
   
    หน้าจอความสำเร็จจะแสดงขึ้นหลังจากที่โฟลว์บันทึกการตัดสินใจของคุณ
   
    ![หน้าจอความสำเร็จ](./media/mobile-approvals/approved.png)

## <a name="reject-requests-and-leave-an-optional-comment"></a>ปฏิเสธคำขอและใส่ข้อคิดเห็น (เป็นทางเลือก)
ทำตาม[ขั้นตอนเพื่ออนุมัติคำขอ](mobile-approvals.md#approve-requests-and-leave-an-optional-comment) แต่เลือก**ปฏิเสธ**ในขั้นตอนที่สอง

## <a name="learn-more"></a>เรียนรู้เพิ่มเติม
[สร้างโฟลว์การอนุมัติแบบทันสมัย](modern-approvals.md)

