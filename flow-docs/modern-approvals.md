---
title: ทำเวิร์กโฟลว์การอนุมัติให้เป็นอัตโนมัติได้อย่างง่ายดาย | Microsoft Docs
description: เวิร์กโฟลว์การอนุมัติที่ทำงานโดยอัตโนมัติและรวมเข้ากับ SharePoint, Dynamics CRM, Salesforce, OneDrive for Business, Zendesk หรือ WordPress
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
ms.openlocfilehash: bd89bca994a77072815a73ba1cbc7ba1db6955d3
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "34051420"
---
# <a name="create-and-test-an-approval-workflow-with-microsoft-flow"></a>สร้างและทดสอบเวิร์กโฟลว์การอนุมัติด้วย Microsoft Flow

ด้วย Microsoft Flow คุณสามารถจัดการการอนุมัติเอกสารหรือกระบวนการในหลากหลายบริการ รวมถึง SharePoint, Dynamics CRM, Salesforce, OneDrive for Business, Zendesk หรือ WordPress

ในการสร้างเวิร์กโฟลว์การอนุมัติ เพิ่มการดำเนินการ**การอนุมัติ - เริ่มการอนุมัติ**สำหรับโฟลว์ หลังจากที่คุณเพิ่มการดำเนินการนี้ โฟลว์ของคุณจะสามารถจัดการการอนุมัติเอกสารหรือกระบวนการได้ ตัวอย่างเช่น คุณสามารถสร้างโฟลว์การอนุมัติเอกสารเพื่ออนุมัติใบแจ้งหนี้ คำสั่งงาน หรือใบเสนอราคาขายได้ นอกจากนี้ คุณยังสามารถสร้างโฟลว์การอนุมัติกระบวนการที่อนุมัติคำขอวันลาพักร้อน งานล่วงเวลา หรือแผนการเดินทางได้

ผู้อนุมัติสามารถตอบสนองคำขอได้จากกล่องขาเข้าของอีเมล [ศูนย์การอนุมัติ](https://flow.microsoft.com/manage/approvals/received/)บนเว็บไซต์ Microsoft Flow หรือแอป Microsoft Flow ได้

## <a name="create-an-approval-flow"></a>สร้างโฟลว์การอนุมัติ
ต่อไปนี้คือภาพรวมของโฟลว์ที่เราจะสร้างและทดสอบ:

   ![ภาพรวมของโฟลว์](./media/modern-approvals/create-flow-overview.png)

โฟลว์ดำเนินขั้นตอนต่อไปนี้:

1. เริ่มต้นขึ้นเมื่อมีผู้สร้างคำขอวันลาพักร้อนในรายการ SharePoint Online
2. เพิ่มคำขอวันหยุดพักผ่อนไปยังศูนย์การอนุมัติ แล้วส่งอีเมลคำขอไปยังผู้อนุมัติ
3. ส่งอีเมลที่มีการตัดสินใจของผู้อนุมัติไปยังบุคคลที่ร้องขอวันลาพักร้อน
4. ปรับปรุงรายการ SharePoint Online ด้วยข้อคิดเห็นในการตัดสินใจของผู้อนุมัติ

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น
เพื่อฝึกปฏิบัติให้เสร็จสมบูรณ์ คุณต้องมีสิทธิ์ในการใช้งาน:

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

สร้างคอลัมน์เหล่านี้ในรายการ SharePoint Online ของคุณ:

   ![คอลัมน์รายการ SharePoint Online](./media/modern-approvals/sharepoint-list-fields.png)

จดบันทึกชื่อและ URL ของรายการ SharePoint Online คุณจะต้องมีรายการเหล่านี้ภายหลัง เมื่อคุณกำหนดค่าทริกเกอร์ **SharePoint - เมื่อมีการสร้างรายการหนึ่ง**

## <a name="create-your-flow-from-the-blank-template"></a>สร้างโฟลว์ของคุณจากเทมเพลตว่างเปล่า
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>เพิ่มทริกเกอร์

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

**ที่อยู่ไซต์**และ**ชื่อรายการ** เป็นรายการที่คุณจดบันทึกไว้ก่อนหน้านี้ในการฝึกปฏิบัตินี้

![ข้อมูล SharePoint](./media/modern-approvals/select-sharepoint-site-info.png)

## <a name="add-a-profile-action"></a>เพิ่มการดำเนินการโปรไฟล์

1. เลือก**ขั้นตอนใหม่** แล้วเลือก**เพิ่มการดำเนินการ**
   
    ![ขั้นตอนใหม่](./media/modern-approvals/select-sharepoint-add-action.png)
2. ป้อน**โปรไฟล์**ลงในกล่องค้นหา**เลือกการดำเนินการ**
   
    ![ค้นหาโปรไฟล์](./media/modern-approvals/search-for-profile.png)
3. ค้นหา จากนั้นเลือกการดำเนินการ**ผู้ใช้ Office 365 - ตั้งโพรไฟล์ของฉัน**
   
    ![เลือกผู้ใช้ Office](./media/modern-approvals/select-my-profile.png)
4. ใส่ชื่อสำหรับโฟลว์ของคุณ จากนั้นเลือก**สร้างโฟลว์**เพื่อบันทึกงานที่เราได้ทำไว้
   
    ![บันทึกโฟลว์](./media/modern-approvals/save.png)

## <a name="add-an-approval-action"></a>เพิ่มการดำเนินการอนุมัติ

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!NOTE]
> การดำเนินการนี้ส่งคำขออนุมัติไปยังที่อยู่อีเมลในกล่อง**กำหนดให้**
>
>

## <a name="add-a-condition"></a>เพิ่มเงื่อนไข

[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

## <a name="add-an-email-action-for-approvals"></a>เพิ่มการดำเนินการอีเมล สำหรับการอนุมัติ

ทำตามขั้นตอนนี้เพื่อส่งอีเมลถ้าคุณอนุมัติคำขอวันลาพักร้อน:

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![กำหนดค่าเทมเพลตอีเมลการอนุมัติ](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-approved-requests"></a>เพิ่มการดำเนินการปรับปรุง สำหรับคำขออนุมัติ

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

> [!NOTE]
> จำเป็นต้องมี**ที่อยู่ไซต์** **ชื่อรายการ** **ID**และ**ชื่อเรื่อง**
>
>

![กำหนดไอเท็มการอัปเดต](./media/modern-approvals/configure-update-item.png)

## <a name="add-an-email-action-for-rejections"></a>เพิ่มการดำเนินการอีเมลสำหรับการปฏิเสธ

[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

![กำหนดค่าสำหรับคำขอที่ถูกปฏิเสธ](./media/modern-approvals/configure-rejected-email.png)

## <a name="add-update-action-for-rejected-requests"></a>เพิ่มอัปเดตการดำเนินการสำหรับคำขอที่ถูกปฏิเสธ

[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   > [!NOTE]
   > จำเป็นต้องมี**ที่อยู่ไซต์** **ชื่อรายการ** **ID**และ**ชื่อเรื่อง**
   >
   >

![บัตรอัปเดตรายการ](./media/modern-approvals/configure-update-item-no.png)

1. เลือก**ปรับปรุงโฟลว์** เพื่อบันทึกงานที่เราทำเสร็จ
   
    ![เลือกการดำเนินการปรับปรุง](./media/modern-approvals/update.png)

ถ้าคุณได้ทำตาม โฟลว์ของคุณควรมีลักษณะดังภาพถ่ายหน้าจอนี้:

![ภาพรวมของโฟลว์](./media/modern-approvals/completed-flow.png)

ตอนนี้เราได้สร้างโฟลว์ และถึงเวลาของการทดสอบแล้ว

## <a name="request-an-approval"></a>ร้องขอการอนุมัติ

[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]

หลังจากที่คุณสร้างและทดสอบโฟลว์ของคุณแล้ว อย่าลืมแจ้งให้บุคคลอื่นทราบถึงวิธีการใช้งานโฟลว์ของคุณ

## <a name="learn-more"></a>เรียนรู้เพิ่มเติม

* ดูและจัดการ[คำขออนุมัติที่ค้างอยู่](approve-reject-requests.md)
* สร้าง[โฟลว์การอนุมัติตามลำดับ](sequential-modern-approvals.md)
* สร้าง[โฟลว์การอนุมัติแบบขนาน](parallel-modern-approvals.md)
* ติดตั้งแอปอุปกรณ์เคลื่อนที่ Microsoft Flow [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) หรือ [Windows Phone](https://aka.ms/flowmobilewindows)
