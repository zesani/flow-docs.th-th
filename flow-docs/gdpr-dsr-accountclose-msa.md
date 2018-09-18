---
title: การร้องขอเพื่อปิดบัญชีเจ้าของข้อมูล Microsoft Flow GDPR สำหรับบัญชี Microsoft (MSA) | Microsoft Docs
description: เรียนรู้วิธีการใช้ Microsoft Flow เพื่อตอบสนองคำขอการปิดบัญชีของเจ้าของข้อมูล GDPR สำหรับบัญชี Microsoft
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
ms.openlocfilehash: be12491490cac51a0b91906b1a663522c2a7658f
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/12/2018
ms.locfileid: "44688777"
---
# <a name="responding-to-gdpr-data-subject-account-close-requests-for-microsoft-flow"></a>การตอบสนองคำขอการปิดบัญชีเจ้าของข้อมูล GDPR สำหรับ Microsoft Flow

**สิทธิ์ในการตรวจสอบความปลอดภัย**ของข้อมูลส่วนบุคคลคือการปกป้องที่สำคัญใน GDPR สิทธิ์นี้รวมถึงการลบข้อมูลส่วนบุคคลทั้งหมด ยกเว้นข้อมูลบันทึกการตรวจสอบ เมื่อผู้ใช้ตัดสินใจที่จะปิดบัญชี Microsoft (MSA) ของตน ข้อมูลพื้นฐานของผู้ใช้จะถูกลบออกไปด้วย

แหล่งข้อมูลเหล่านี้ประกอบด้วยข้อมูลส่วนบุคคลที่จะถูกลบโดยอัตโนมัติเมื่อผู้ใช้ปิดบัญชี MSA:

|ทรัพยากรที่มีข้อมูลส่วนบุคคล|
|------|
|กิจกรรมของผลิตภัณฑ์และบริการ|
|ประวัติการเรียกใช้|
|โฟลว์|
|ฟีดกิจกรรม|
|รายละเอียดผู้ใช้งาน|
|การเชื่อมต่อ|

## <a name="account-close-requests"></a>คำขอการปิดบัญชี

ขั้นตอนเหล่านี้อธิบายวิธีการตอบสนองต่อคำขอการปิดบัญชีด้วยตนเองสำหรับ GDPR

1. ลงชื่อเข้าใช้[พอร์ทัลปิดบัญชี Microsoft](http://go.microsoft.com/fwlink/?LinkId=523898) โดยใช้บัญชี Microsoft ของคุณ จากนั้น **ถัดไป**

    > [!NOTE]
    > คุณกำลังได้รับการเตือนให้ยกเลิกการสมัครใช้งานที่มีอยู่ หรือให้ส่งออกข้อมูลจากบริการปัจจุบัน ซึ่งคุณอาจมีการสมัครใช้งาน
    >
    >

    ![ยกเลิกการสมัครใช้งาน](./media/gdpr-dsr-delete-msa/accountclose.png)

1. ยอมรับว่าคุณเข้าใจถึงผลกระทบของการปิดบัญชี MSA ของคุณ จากนั้น**ทำเครื่องหมายปิดบัญชี**

    การแจ้งเตือนปรากฏขึ้นเพื่อแสดงว่า บัญชีของคุณจะถูกปิดใน 30 วัน คุณสามารถเปิดบัญชีนี้ได้ทุกเวลาในระหว่างรอบระยะเวลา 30 วันนี้

    ![บัญชีแล้ว](./media/gdpr-dsr-delete-msa/accountclosed.png)

    ที่ส่วนท้ายของหน้าต่าง 30 วันนี้ กระบวนการการลบทรัพยากรทั้งหมดของ Microsoft Flow สำหรับ MSA นี้เริ่มต้นขึ้น

## <a name="learn-more"></a>เรียนรู้เพิ่มเติม

* เริ่มต้นใช้งาน[Microsoft Flow](getting-started.md)
* เรียนรู้[มีอะไรใหม่](release-notes.md)ด้วย Microsoft Flow
