---
title: สร้างโฟลว์จากเทมเพลต | Microsoft Docs
description: สร้างโฟลว์จากเทมเพลตภายในที่มีอยู่มากมาย
services: ''
suite: flow
documentationcenter: na
author: aftowen
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/07/2017
ms.author: anneta
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 52aae570f65eaae537f548e686f437592eb5ef03
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689467"
---
# <a name="create-a-flow-from-a-template-in-microsoft-flow"></a>สร้างโฟลว์จากเทมเพลตใน Microsoft Flow
สร้างโฟลว์จากหนึ่งในเทมเพลตภายในที่มีอยู่มากมายที่สามารถ ตัวอย่างเช่น ส่งข้อความ Slack เมื่อผู้จัดการของคุณส่งอีเมลหาคุณใน Office 365

**หมายเหตุ:** [สร้างโฟลว์ตั้งแต่เริ่มต้น](get-started-logic-flow.md)หากคุณมีกระบวนการที่ทราบแล้ว และไม่สามารถค้นหาเทมเพลตตามที่ต้องการได้

**ข้อกำหนดเบื้องต้น**

* บัญชีผู้ใช้บน [flow.microsoft.com](https://flow.microsoft.com)
* บัญชี Slack
* ข้อมูลประจำตัว Office 365

## <a name="choose-a-template"></a>เลือกเทมเพลต
<iframe width="560" height="315" src="https://www.youtube.com/embed/ZJK8cYdjAic?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. ใน [flow.microsoft.com](https://flow.microsoft.com) เลือก**เทมเพล**ในแถบนำทางด้านบน
2. ในแถบการค้นหา พิมพ์ **Slack** แล้ว เลือกไอคอนค้นหา
3. คุณจะเห็นเฉพาะเทมเพลตที่เกี่ยวข้องกับ Slack ดังนั้นตอนนี้คุณจึงสามารถเลือก**ส่งข้อความบน Slack เมื่อผู้จัดการของฉันส่งอีเมลถึงฉัน**
   
    ![ตัวเลือกใหม่ในแถบนำทางด้านซ้าย](./media/get-started-logic-template/select-template.png)
4. ยืนยันว่าเทมเพลตนี้จะทำสิ่งที่คุณต้อง จากนั้นเลือก**ใช้เทมเพลตนี้**
5. ถ้าคุณไม่ได้ลงชื่อเข้าใช้ Office หรือ Slack เลือก**ลงชื่อเข้าใช้**แล้วทำตามข้อความปรากฏ
   
    ![รายการของการเชื่อมต่อที่เทมเพลตจำเป็นต้องใช้](./media/get-started-logic-template/confirm-connections.png)
6. หลังจากที่คุณยืนยันการเชื่อมต่อของคุณแล้ว เลือก**ดำเนินการต่อ**
   
    โฟลว์ของคุณปรากฏขึ้นและแสดงแต่ละการดำเนินการด้วยแถบชื่อเรื่องสีส้ม
   
    ![เหตุการณ์และการดำเนินการค่าเริ่มต้นจากเทมเพลต](./media/get-started-logic-template/template-default.png)

## <a name="customize-your-flow"></a>ปรับแต่งโฟลว์ของคุณ
1. เลือกแถบชื่อเรื่องสำหรับเหตุการณ์หนึ่งเพื่อขยาย จากนั้นกำหนดค่า (ตัวอย่างเช่น โดยการระบุตัวกรองบนอีเมลที่คุณสนใจ)
2. การดำเนินการที่คุณจำเป็นต้องป้อนข้อมูลจะสามารถขยายได้โดยอัตโนมัติ
   
    ตัวอย่างเช่น การดำเนินการ**โพสต์ข้อความ**จะขยายเนื่องจากคุณจำเป็นต้องใส่แชนเนล เช่น *\@ชื่อผู้ใช้* ของคุณ นอกจากนี้คุณยังสามารถกำหนดค่าเนื้อหาข้อความได้ ตามค่าเริ่มต้น ข้อความจะประกอบด้วยเพียงหัวเรื่อง แต่คุณสามารถใส่ข้อมูลอื่น ๆ ได้
   
    ![ระบุแชนเนลสำหรับ Slack](./media/get-started-logic-template/specify-keyword.png)
3. ใกล้กับด้านบนของหน้าจอ ระบุชื่อสำหรับโฟลว์ของคุณ จากนั้นเลือก**สร้างโฟลว์**
4. สุดท้าย เมื่อคุณพอใจกับโฟลว์ของคุณ เลือก**เสร็จสิ้น**
   
    ![ปุ่มเสร็จสิ้น](./media/get-started-logic-template/done.png)

ตอนนี้เมื่อผู้จัดการส่งอีเมลถึงคุณ คุณจะได้รับข้อความ Slack ที่ประกอบด้วยข้อมูลที่คุณระบุ

## <a name="next-steps"></a>ขั้นตอนถัดไป
* [ดูโฟลว์ของคุณทำงาน](see-a-flow-run.md)
* [เผยแพร่เทมเพลตของคุณเอง](publish-a-template.md)
* [ใช้เทมเพลตสำหรับ Common Data Service](common-data-model-intro.md)
* [เริ่มต้นใช้งานโฟลว์ทีม](create-team-flows.md)และเชิญบุคคลอื่นเข้าทำงานร่วมกับคุณเพื่อออกแบบโฟลว์

