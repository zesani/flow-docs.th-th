---
title: สร้างเวิร์กโฟลว์การอนุมัติที่ทันสมัย ที่มีผู้อนุมัติหลายราย | Microsoft Docs
description: 'สร้างเวิร์กโฟลว์การอนุมัติที่ทันสมัย ที่มีผู้อนุมัติหลายราย '
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/08/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f75f9b822078fcec8701bf06c3dcb8be0e07d874
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690755"
---
# <a name="manage-sequential-approvals-with-microsoft-flow"></a>จัดการการอนุมัติตามลำดับ ด้วย Microsoft Flow
เวิร์กโฟลว์บางอย่างจำเป็นต้องมีการอนุมัติล่วงหน้า ก่อนที่ผู้อนุมัติขั้นสุดท้ายต้องลงชื่อ ตัวอย่างเช่น บริษัทอาจมีนโยบายการอนุมัติตามลำดับ ที่ต้องมีการอนุมัติล่วงหน้าสำหรับใบแจ้งหนี้เกิน $1000.00 ก่อนที่จะได้รับการอนุมัติโดยแผนกการเงิน

ในการฝึกปฏิบัตินี้ เราจะสร้างโฟลว์การอนุมัติตามลำดับ ที่จัดการคำขอวันหยุดพักผ่อนของพนักงาน

## <a name="detailed-steps-in-the-flow"></a>รายละเอียดของขั้นตอนในโฟลว์
โฟลว์:

1. เริ่มต้นเมื่อพนักงานสร้างการร้องขอวันหยุดพักผ่อนใน[รายการ SharePoint Online](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7)
2. เพิ่มคำขอวันหยุดพักผ่อนไปยังศูนย์การอนุมัติ แล้วส่งอีเมลคำขอไปยังผู้อนุมัติล่วงหน้า
3. ส่งอีเมลผลการอนุมัติล่วงหน้าไปยังพนักงาน
4. ปรับปรุงรายการ SharePoint Online ด้วยผลการตัดสินใจและข้อคิดเห็นของผู้อนุมัติล่วงหน้า
   
   หมายเหตุ: ถ้าคำขอได้รับอนุมัติล่วงหน้าแล้ว โฟลว์จะการดำเนินต่อด้วยขั้นตอนเหล่านี้:
5. ส่งคำขอไปยังผู้อนุมัติขั้นสุดท้าย
6. ส่งอีเมลผลการตัดสินใจสุดท้ายให้กับพนักงาน
7. ปรับปรุงรายการ SharePoint ด้วยการตัดสินใจสุดท้าย

รูปนี้สรุปขั้นตอนต่าง ๆ ก่อนหน้า:

   ![ไดอะแกรม Visio ของโฟลว์](./media/sequential-modern-approvals/visio-overview.png)

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น
[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

รายการ SharePoint Online ที่คุณสร้าง ต้องมีคอลัมน์ต่อไปนี้:

   ![คอลัมน์รายการ SharePoint](./media/sequential-modern-approvals/sharepoint-columns.png)

จดบันทึกชื่อและ URL ของรายการ SharePoint Online เราจะใช้รายการเหล่านี้ภายหลัง เมื่อคุณกำหนดค่า**SharePoint - เมื่อมีการสร้างรายการใหม่**ทริกเกอร์

## <a name="create-your-flow-from-the-blank-template"></a>สร้างโฟลว์ของคุณจากเทมเพลตว่างเปล่า
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>เพิ่มทริกเกอร์
[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![ข้อมูล SharePoint](./media/sequential-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>รับผู้จัดการ สำหรับบุคคลที่สร้างคำขอวันหยุดพักผ่อน
[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

1. ใส่ชื่อสำหรับโฟลว์ของคุณ จากนั้น**สร้างโฟลว์**เพื่อบันทึกงานที่เราได้ทำแล้ว
   
    ![บันทึกโฟลว์](./media/sequential-modern-approvals/save.png)
   
   > [!NOTE]
   > เลือก**ปรับปรุงโฟลว์**จากด้านบนของหน้าจอเป็นระยะ ๆ เพื่อบันทึกการเปลี่ยนแปลงของโฟลว์คุณ
   > 
   > 
   
    ![เลือกการดำเนินการปรับปรุง](./media/sequential-modern-approvals/update.png)

หลังจากการบันทึกแต่ละครั้ง เลือก**แก้ไขโฟลว์**จากด้านบนของหน้าจอ แล้วทำการเปลี่ยนแปลงต่อไป

## <a name="add-an-approval-action-for-pre-approvals"></a>เพิ่มการดำเนินการอนุมัติ สำหรับการอนุมัติล่วงหน้า
[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

หมายเหตุ: การดำเนินการนี้ส่งคำขออนุมัติล่วงหน้า ไปยังที่อยู่อีเมลในกล่อง**กำหนดให้**

## <a name="add-a-condition"></a>เพิ่มเงื่อนไข
[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

> [!NOTE]
> เงื่อนไขนี้ตรวจสอบการตอบสนองจาก การดำเนินการ**เริ่มการอนุมัติ**
> 
> 

## <a name="add-an-email-action-for-pre-approvals"></a>เพิ่มการดำเนินการอีเมล สำหรับการอนุมัติล่วงหน้า
[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![กำหนดค่าเทมเพลตอีเมล การอนุมัติล่วงหน้า](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-pre-approved-requests"></a>เพิ่มการดำเนินการปรับปรุง สำหรับคำขออนุมัติล่วงหน้า
[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

   ![กำหนดค่ารายการปรับปรุง](./media/sequential-modern-approvals/configure-update-item.png)

## <a name="get-the-pre-approvers-manager"></a>รับผู้จัดการของผู้อนุมัติล่วงหน้า
1. ใช้ขั้นตอน [รับผู้จัดการ สำหรับบุคคลที่สร้างคำขอวันหยุดพักผ่อน](sequential-modern-approvals.md#get-the-manager-for-the-person-who-created-the-vacation-request) ที่เราได้ทำก่อนหน้านี้ เพื่อเพิ่มและกำหนดการดำเนินการ**รับผู้จัดการ**อีกหนึ่งรายการ ครั้งนี้ เราจะรับผู้จัดการของผู้อนุมัติล่วงหน้า
2. การ์ด**รับผู้จัดการ 2** ควรมีลักษณะดังรูปนี้เมื่อคุณทำเสร็จแล้ว ตรวจสอบให้แน่ใจว่า ได้ใช้โทเค็น**อีเมล** จากประเภท**รับผู้จัดการ** บนการ์ด**เพิ่มเนื้อหาแบบไดนามิกจากแอปและตัวเชื่อมต่อต่างๆ ที่ใช้ในโฟลว์นี้**
   
   ![รับผู้จัดการของผู้อนุมัติล่วงหน้า](includes/media/modern-approvals/get-pre-approver-manager.png)

## <a name="add-the-final-approval-action"></a>เพิ่มการดำเนินการอนุมัติขั้นสุดท้าย
1. ใช้ขั้นตอน [เพิ่มการดำเนินการอนุมัติ สำหรับการอนุมัติล่วงหน้า](sequential-modern-approvals.md#add-an-approval-action-for-pre-approvals) ที่เราได้ทำก่อนหน้านี้ เพื่อเพิ่มและกำหนดการดำเนินการ**รับผู้จัดการ**อีกหนึ่งรายการ การดำเนินการนี้ ส่งอีเมลการร้องขอสำหรับการอนุมัติขั้นสุดท้าย
2. เมื่อคุณทำเสร็จแล้ว การ์ดควรมีลักษณะดังรูปนี้:
   
    ![กำหนดค่าการอนุมัติ](./media/sequential-modern-approvals/provide-approval-config-info.png)

## <a name="add-the-final-approval-condition"></a>เพิ่มเงื่อนไขการอนุมัติขั้นสุดท้าย
1. ทำซ้ำขั้นตอนจาก[เพิ่มเงื่อนไข](sequential-modern-approvals.md#add-a-condition) เพื่อเพิ่มและกำหนดค่า**เงื่อนไข** ที่ตรวจสอบการตัดสินใจของผู้อนุมัติขั้นสุดท้าย

## <a name="send-email-with-final-approval"></a>ส่งอีเมลที่มีการอนุมัติขั้นสุดท้าย
1. ใช้ขั้นตอนจาก [เพิ่มการดำเนินการอีเมล สำหรับการอนุมัติล่วงหน้า](sequential-modern-approvals.md#add-an-email-action-for-pre-approvals) เพื่อเพิ่มและกำหนดค่าการดำเนินการที่ส่งอีเมล เมื่อคำขอวันหยุดพักผ่อนได้รับการอนุมัติ
2. เมื่อคุณทำเสร็จแล้ว การ์ดของคุณควรมีลักษณะดังรูปนี้:
   
   ![เทมเพลตอีเมลการอนุมัติขั้นสุดท้าย](./media/sequential-modern-approvals/vacatioin-request-approved-email-template.png)

## <a name="update-sharepoint-with-approval"></a>ปรับปรุง SharePoint ด้วยการอนุมัติ
1. ใช้ขั้นตอนจาก [เพิ่มการดำเนินการปรับปรุง สำหรับคำขออนุมัติล่วงหน้า](sequential-modern-approvals.md#add-an-update-action-for-pre-approved-requests) เพื่อเพิ่มและกำหนดค่าการดำเนินการที่ปรับปรุง SharePoint เมื่อคำขอวันหยุดพักผ่อนได้รับอนุมัติ
2. เมื่อคุณเสร็จแล้ว การ์ดควรมีลักษณะดังรูปนี้:
   
    ![กำหนดค่ารายการปรับปรุง](./media/sequential-modern-approvals/configure-update-item-approved.png)

## <a name="send-email-with-pre-approval-rejection"></a>ส่งอีเมลที่มีการปฏิเสธการอนุมัติล่วงหน้า
[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

   ![กำหนดค่าสำหรับคำขอที่ถูกปฏิเสธ](./media/sequential-modern-approvals/configure-rejected-email.png)

หมายเหตุ: การดำเนินการนี้ต้องเพิ่มลงในสาขา **ถ้าไม่ใช่ ไม่ต้องทำอะไร** ด้านล่างการ์ด**เงื่อนไข**

## <a name="update-sharepoint-with-pre-approval-rejection"></a>อัปเดต SharePoint ด้วยการปฏิเสธการอนุมัติล่วงหน้า
[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   ![อัปเดต SharePoint สำหรับคำขอที่ถูกปฏิเสธ](./media/sequential-modern-approvals/update-sharepoint-with-rejection.png)

## <a name="send-email-with-final-rejection"></a>ส่งอีเมลที่มีการปฏิเสธขั้นสุดท้าย
1. ใช้ขั้นตอนจาก[ส่งอีเมลที่มีการปฏิเสธการอนุมัติล่วงหน้า](sequential-modern-approvals.md#send-email-with-pre-approval-rejection) เพื่อเพิ่มและกำหนดค่าการดำเนินการที่ส่งอีเมล เมื่อคำขอวันหยุดพักผ่อนถูกปฏิเสธจากผู้อนุมัติขั้นสุดท้าย
   
    หมายเหตุ: การดำเนินการนี้ต้องเพิ่มลงในสาขา **ถ้าไม่ใช่ ไม่ต้องทำอะไร** ด้านล่างการ์ด**เงื่อนไข 2**
2. เมื่อคุณเสร็จแล้ว การ์ดควรมีลักษณะดังรูปนี้:
   
   ![กำหนดค่าสำหรับคำขอที่ถูกปฏิเสธ](./media/sequential-modern-approvals/final-rejection-email-card.png)

## <a name="update-sharepoint-with-final-rejection"></a>อัปเดต SharePoint ด้วยการปฏิเสธขั้นสุดท้าย
1. ใช้ขั้นตอนจาก[อัปเดต SharePoint ด้วยการปฏิเสธการอนุมัติล่วงหน้า้า](sequential-modern-approvals.md#update-sharepoint-with-pre-approval-rejection) เพื่อเพิ่มและกำหนดค่าการดำเนินการที่อัปเดต SharePoint ถ้าผู้อนุมัติขั้นสุดท้ายปฏิเสธคำขอวันหยุดพักผ่อน
2. เมื่อคุณเสร็จแล้ว การ์ดควรมีลักษณะดังรูปนี้:
   
   ![การ์ดปรับปรุงรายการ](./media/sequential-modern-approvals/final-rejection-update-sharepoint.png)
3. เลือก**ปรับปรุงโฟลว์** เพื่อบันทึกงานที่เราทำเสร็จ
   
   ![เลือกการดำเนินการปรับปรุง](./media/sequential-modern-approvals/update.png)

ถ้าคุณได้ทำตาม โฟลว์ของคุณควรมีลักษณะดังรูปนี้:

![ภาพรวมของโฟลว์](./media/sequential-modern-approvals/completed-flow.png)

หลังจากที่เราได้สร้างโฟลว์ ลองมาดูโฟลว์ทำงานกัน

## <a name="request-an-approval"></a>ร้องขอการอนุมัติ
[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]

คำขอของคุณควรคล้ายกับรูปนี้:

![คำขอวันหยุดพักผ่อน](./media/sequential-modern-approvals/vacation-request.png)

## <a name="view-pending-approval-requests"></a>ดูคำขออนุมัติที่ค้างอยู่
[!INCLUDE [view-pending-approvals](includes/view-pending-approvals.md)]

## <a name="pre-approve-a-request"></a>อนุมัติคำขอไว้ล่วงหน้า
[!INCLUDE [approve-request-from-different-locations](includes/approve-request-from-different-locations.md)]

## <a name="approve-the-request"></a>อนุมัติคำขอ
ขั้นตอนในการอนุมัติคำขอจะเหมือนกับขั้นตอน [อนุมัติคำขอไว้ล่วงหน้า](sequential-modern-approvals.md#pre-approve-a-request)

หมายเหตุ: ผู้อนุมัติขั้นสุดท้ายรับคำขอวันหยุดพักผ่อน เฉพาะคำขอที่ได้รับการอนุมัติล่วงหน้าแล้วเท่านั้น

## <a name="reject-a-request"></a>ปฏิเสธการร้องขอ
[!INCLUDE [reject-a-request](includes/reject-a-request.md)]

## <a name="more-information"></a>ข้อมูลเพิ่มเติม
[การฝึกปฏิบัติ ผู้อนุมัติรายเดียวในการอนุมัติที่ทันสมัย](modern-approvals.md)

