---
title: Common Data Service | Microsoft Docs
description: สร้างโฟลว์เพื่อนำเข้าข้อมูล ส่งออกข้อมูล หรือสร้างการอนุมัติโดยใช้ Common Data Service
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/22/2016
ms.author: stepsic
ms.openlocfilehash: e4e92bfdcf1ea65de272233b2056523641010cf2
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "31002519"
---
# <a name="create-a-flow-that-uses-the-common-data-service"></a>สร้างโฟลว์ที่ใช้ Common Data Service
ปรับปรุงประสิทธิภาพในการดำเนินงาน ด้วยมุมมองข้อมูลทางธุรกิจแบบรวมกันในที่เดียว โดยการสร้างโฟลว์ที่ใช้ [Common Data Service](https://powerapps.microsoft.com/tutorials/data-platform-intro/) ปรับใช้ฐานข้อมูลทางธุรกิจที่มีความปลอดภัยนี้ ซึ่งประกอบด้วยเอนทิตีธุรกิจมาตรฐานที่จัดรูปแบบอย่างดี (เช่น ยอดขาย ซื้อ ส่วนบริการลูกค้า และประสิทธิภาพการทำงาน) ในองค์กรของคุณ จัดเก็บข้อมูลขององค์กรใน[เอนทิตีแบบกำหนดเอง](https://powerapps.microsoft.com/tutorials/data-platform-create-entity/)อย่างน้อยหนึ่งรายการ ซึ่งมีประโยชน์มากต่อแหล่งข้อมูลภายนอก เช่น Microsoft Excel และ Salesforce

ตัวอย่างเช่น ใช้ประโยชน์จาก Common Data Service ภายใน Microsoft Flow โดยใช้วิธีหลักต่อไปนี้:

* สร้างโฟลว์เพื่อนำเข้าข้อมูล ส่งออกข้อมูล หรือดำเนินการที่ด้านบนของข้อมูล (เช่น การส่งการแจ้งเตือน) โปรดทราบว่า วิธีนี้ไม่ใช่บริการซิงโครไนซ์แบบสมบูรณ์ เพียงแค่ช่วยให้คุณสามารถย้ายข้อมูลเข้าหรือออกสำหรับหลักเกณฑ์แต่ละเอนทิตี
  
    สำหรับขั้นตอนโดยละเอียด ดูที่กระบวนงานในหัวข้อนี้ภายหลัง
* แทนที่จะ[สร้างการวนรอบการอนุมัติผ่านทางอีเมล](wait-for-approvals.md) ให้สร้างโฟลว์ที่จัดเก็บสถานะการอนุมัติในเอนทิตี และสร้างแอปแบบกำหนดเองที่ผู้ใช้สามารถอนุมัติหรือปฏิเสธรายการได้
  
    สำหรับขั้นตอนรายละเอียด ดูที่[สร้างรอบการอนุมัติด้วย Common Data Service](common-data-model-approve.md)

**ข้อกำหนดเบื้องต้น**

* ลงทะเบียนสำหรับ [Microsoft Flow](https://flow.microsoft.com) และ [PowerApps](https://web.powerapps.com)
  
    ถ้าคุณมีปัญหา ให้ตรวจสอบว่า [Microsoft Flow](sign-up-sign-in.md) และ [PowerApps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/) สนับสนุนชนิดของบัญชีที่คุณมี และองค์กรของคุณไม่ได้บล็อกการลงทะเบียน
* ถ้าคุณยังไม่เคยใช้ Common Data Service มาก่อน เปิดแท็บ**เอนทิตี**ของ [powerapps.com](https://web.powerapps.com/#/entities) และจากนั้น คลิกหรือแตะ**สร้างฐานข้อมูลของฉัน**

## <a name="sign-in-to-your-environment"></a>ลงชื่อเข้าใช้สภาพแวดล้อมของคุณ
1. เปิด[พอร์ทัลของ Microsoft Flow](https://flow.microsoft.com) แล้วคลิกหรือแตะ**ลงชื่อเข้าใช้**ที่มุมขวาบน
   
    **หมายเหตุ**: คุณอาจจำเป็นต้องเปิดเมนูด้านบนซ้ายเพื่อแสดงปุ่ม**ลงชื่อเข้าใช้**
   
    ![ลงชื่อเข้าใช้](./media/common-data-model-intro/signin-flow.png)
2. ในเมนูขวาบน ให้คุณเลือกสภาพแวดล้อมที่คุณสร้างฐานข้อมูลใน powerapps.com
   
    **หมายเหตุ**: ถ้าคุณไม่เลือกสภาพแวดล้อมเดียวกัน คุณจะไม่เห็นเอนทิตีของคุณ
   
    ![เลือกสภาพแวดล้อม](./media/common-data-model-intro/select-environment.png)

## <a name="open-a-template"></a>เปิดเทมเพลต
1. ในกล่อง**ค้นหาเทมเพลต**ที่ด้านบนของหน้าจอ พิมพ์หรือวาง**ทั่วไป**แล้ว กด Enter
   
    ![ค้นหาเทมเพลต](./media/common-data-model-intro/template-search.png)
2. ในรายการเทมเพลต คลิกหรือแตะเทมเพลตที่นำเข้าข้อมูลจากแหล่งข้อมูลที่คุณต้องการลงในเอนทิตี (หรือ*วัตถุ*) ที่คุณต้องการ
   
    ตัวอย่างเช่น คลิกหรือแตะเทมเพลตที่คัดลอกข้อมูลที่ติดต่อจาก Dynamics 365 ลงใน Common Data Service
   
    ![เลือกเทมเพลต](./media/common-data-model-intro/choose-template.png)
3. คลิกหรือแตะ **ใช้เทมเพลตนี้**
   
    ![ใช้เทมเพลต](./media/common-data-model-intro/use-template.png)
4. ถ้าคุณยังไม่ได้สร้างการเชื่อมต่อจาก Microsoft Flow ไปยัง Dynamics 365 ให้คลิกหรือแตะ**ลงชื่อเข้าใช้** แล้วใส่ข้อมูลประจำตัวของคุณถ้าได้รับพร้อมท์
   
    ![ลงชื่อเข้าใช้ Dynamics 365](./media/common-data-model-intro/dynamics-signin.png)
5. คลิกหรือแตะ**ดำเนินการต่อ**
   
    ![ยืนยันบัญชีผู้ใช้](./media/common-data-model-intro/confirm-accounts.png)

## <a name="build-your-flow"></a>สร้างโฟลว์ของคุณ
1. ในบัตรใบแรก ให้ระบุเหตุการณ์ที่จะทริกเกอร์โฟลว์
   
    ตัวอย่างเช่น คุณกำลังสร้างโฟลว์ที่จะคัดลอกที่ติดต่อใหม่จากอินสแตนซ์ของ Dynamics 365 ไปยัง Common Data Service ภายใต้**เมื่อสร้างเรกคอร์ด** ระบุอินสแตนซ์โดยการคลิกหรือแตะลูกศรลง แล้วคลิกหรือแตะตัวเลือกในรายการที่ปรากฏขึ้น
   
    ![ระบุอินสแตนซ์ของ Dynamics 365](./media/common-data-model-intro/specify-instance.png)
2. (ตัวเลือกเพิ่มเติม) ใกล้กับด้านบนของหน้าจอ ระบุชื่ออื่นสำหรับขั้นตอนที่คุณกำลังสร้างอยู่
   
    **หมายเหตุ**: ถ้าหน้าต่างเบราว์เซอร์ของคุณไม่ได้ขยายใหญ่สุด UI อาจดูแตกต่างออกไปเล็กน้อยได้
   
    ![โฟลว์ชื่อ](./media/common-data-model-intro/name-flow.png)
3. คลิกหรือแตะ**สร้างโฟลว์**
   
    **หมายเหตุ**: ถ้าหน้าต่างเบราว์เซอร์ของคุณไม่ได้ขยายใหญ่สุด อาจมีเฉพาะเครื่องหมายถูกปรากฏขึ้น
   
    ![สร้างโฟลว์](./media/common-data-model-intro/create-flow.png)

ตอนนี้ เมื่อใดก็ตามที่วัตถุนั้นถูกสร้างขึ้นในระบบต้นทาง วัตถุดังกล่าวจะถูกนำเข้าใน Common Data Service ถ้าคุณไม่สามารถค้นหาเทมเพลตที่ทำในสิ่งที่คุณต้องการ คุณสามารถ[สร้างโฟลว์ตั้งแต่เริ่มแรก](get-started-logic-flow.md) ซึ่งทำงานที่ด้านบนของ Common Data Service

คุณสามารถดำเนินการกับการเปลี่ยนแปลงในฐานข้อมูลได้ ตัวอย่างเช่น คุณสามารถส่งเมลแจ้งเตือนเมื่อใดก็ตามที่ข้อมูลมีการเปลี่ยนแปลง

