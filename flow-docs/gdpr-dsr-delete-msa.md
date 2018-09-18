---
title: การร้องขอเพื่อลบเจ้าของข้อมูล Microsoft Flow GDPR สำหรับบัญชี Microsoft (MSA) | Microsoft Docs
description: เรียนรู้วิธีใช้ Microsoft Flow เพื่อตอบสนองคำขอการลบเจ้าของข้อมูล GDPR สำหรับบัญชี Microsoft
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: KFile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/25/2018
ms.author: keweare
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: e42da775d5c004bfbe0d6bb8923e6d05aaa5e976
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/12/2018
ms.locfileid: "44688984"
---
# <a name="respond-to-gdpr-data-subject-delete-requests"></a>ตอบสนองต่อคำขอการลบเจ้าของข้อมูล GDPR

**สิทธิ์ในการตรวจสอบความปลอดภัย**โดยการลบข้อมูลส่วนบุคคลคือการปกป้องที่สำคัญใน GDPR การลบข้อมูลส่วนบุคคลรวมถึงการลบข้อมูลส่วนบุคคลทั้งหมด ยกเว้นข้อมูลบันทึกการตรวจสอบ

Microsoft Flow ช่วยให้ผู้ใช้สามารถสร้างเวิร์กโฟลว์ได้อัตโนมัติ เมื่อผู้ใช้ตัดสินใจที่จะลบข้อมูลส่วนบุคคลของตนจาก Microsoft Flow ผู้ใช้สามารถตรวจสอบข้อมูลส่วนบุคคลของตนได้ และกำหนดว่าจะลบบางส่วนหรือทั้งหมด

ตารางต่อไปนี้แสดงข้อมูลส่วนบุคคลใดที่จะถูกลบโดยอัตโนมัติ และข้อมูลใดที่จำเป็นต้องมีผู้ใช้บัญชี Microsoft (MSA) เพื่อตรวจสอบและลบข้อมูล

|จำเป็นต้องมีผู้ใช้ MSA เพื่อตรวจทานและลบข้อมูล|ถูกลบโดยอัตโนมัติ|
|------|------|
|กิจกรรมของผลิตภัณฑ์และบริการ|ประวัติการเรียกใช้|
|โฟลว์|ฟีดกิจกรรม|
|การเชื่อมต่อ||

Microsoft Flow มีประสบการณ์การใช้งานต่อไปนี้เพื่อช่วยให้ผู้ใช้ค้นหา ตรวจทาน หรือเปลี่ยนข้อมูลส่วนบุคคล รวมถึงแหล่งข้อมูลที่ไม่ได้ถูกลบโดยอัตโนมัติ:

## <a name="manage-delete-requests"></a>จัดการคำขอการลบ

ขั้นตอนด้านล่างนี้อธิบายวิธีการทำงานเพื่อตอบสนองคำขอการลบ GDPR ด้วยตนเอง

### <a name="delete-product-and-service-activity"></a>ลบกิจกรรมของผลิตภัณฑ์และบริการ

1. ลงชื่อเข้าใช้[แดชบอร์ดความเป็นส่วนตัวของ Microsoft](https://account.microsoft.com/privacy/)ด้วย MSA ของคุณ
1. เลือกลิงก์**ประวัติกิจกรรม**

    ![ประวัติกิจกรรม](./media/gdpr-dsr-export-msa/activityhistory.png)

1. คุณสามารถค้นหาหรือเรียกดูประวัติกิจกรรมของคุณสำหรับแอปพลิเคชัน Microsoft และบริการอื่น ๆ ที่คุณใช้ได้ รวมถึง Microsoft Flow ด้วย เลือก**ลบ**เพื่อลบบางเหตุการ์ของกิจกรรมผลิตภัณฑ์หรือบริการ

    ![ลบเหตุการณ์](./media/gdpr-dsr-delete-msa/deleteevent.png)

1. ภายในอีกสักครู่ รายการจะถูกลบและถูกเอาออกจากแดชบอร์ดความเป็นส่วนตัว

### <a name="list-and-delete-flows"></a>สร้างรายการและลบโฟลว์

ผู้ใช้สามารถสร้างรายการ และลบโฟลว์ของตนจาก [Microsoft Flow](https://flow.microsoft.com) ได้โดยขั้นตอนต่อไปนี้:

1. ลงชื่อเข้าใช้[Microsoft Flow](https://flow.microsoft.com) จากนั้นเลือกที่**โฟลว์ของฉัน**

1. เลือก **...** ด้านข้างโฟลว์ที่คุณกำลังลบ แล้ว เลือก**ลบ**

    ![ลบเหตุการณ์](./media/gdpr-dsr-delete-msa/deleteflow.png)

### <a name="delete-connections"></a>ลบการเชื่อมต่อ

ตัวเชื่อมต่อที่ใช้การเชื่อมต่อเพื่อติดต่อสื่อสารกับระบบ API และ SaaS การเชื่อมต่อรวมอ้างอิงต่าง ๆ ไปยังผู้ใช้ที่เป็นผู้สร้างการเชื่อมต่อขึ้น ผู้ใช้นั้นสามารถลบอ้างอิงเหล่านี้ได้ทุกเวลาโดยทำตามขั้นตอนเหล่านี้:

1. ลงชื่อเข้าใช้ [Microsoft Flow](https://flow.microsoft.com) เลือกไอคอนรูปเฟือง จากนั้นเลือก **การเชื่อมต่อ**

    ![ลบเหตุการณ์](./media/gdpr-dsr-delete-msa/deleteconnections.png)

1. เลือกการเชื่อมต่อที่คุณต้องการลบ เลือก **...**  แล้วเลือก**ลบ**

    ![ลบเหตุการณ์](./media/gdpr-dsr-delete-msa/delete-connection.png)

1. เลือกไอคอน**ลบ**บนข้อความปรากฏเพื่อการยืนยัน

    ![ลบเหตุการณ์](./media/gdpr-dsr-delete-msa/confirmdelete.png)

> [!NOTE]
> ถ้าขั้นตอนอื่น ๆ ใช้การเชื่อมต่อที่คุณกำลังลบ คุณจะได้รับแจ้งว่าต้องมีการเชื่อมต่อใหม่ มิฉะนั้น เลือก**ลบ**เพื่อดำเนินต่อ
>
>

## <a name="learn-more"></a>เรียนรู้เพิ่มเติม

* เริ่มต้นใช้งาน[Microsoft Flow](getting-started.md)
* เรียนรู้[มีอะไรใหม่](release-notes.md)ด้วย Microsoft Flow
