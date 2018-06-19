---
title: กลุ่มข้อมูลสำหรับ Microsoft Flow | Microsoft Docs
description: บทนำสู่กลุ่มข้อมูลสำหรับ Microsoft PowerApps และ Microsoft Flow
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
ms.date: 10/26/2016
ms.author: deonhe
ms.openlocfilehash: fd76c12d1879c9b613ba833d9ef2211cd4aab702
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "31001259"
---
# <a name="learn-all-about-data-groups"></a>เรียนรู้เกี่ยวกับกลุ่มข้อมูลทั้งหมด
## <a name="what-is-a-data-group"></a>กลุ่มข้อมูลคืออะไร?
กลุ่มข้อมูลคือ วิธีง่าย ๆ ในการจัดประเภทบริการภายใน[นโยบายการป้องกันการสูญหายของข้อมูล (DLP)](prevent-data-loss.md) กลุ่มข้อมูลสองกลุ่มที่มีคือ กลุ่ม**เฉพาะข้อมูลธุรกิจเท่านั้น** และกลุ่ม**ไม่อนุญาตให้มีข้อมูลธุรกิจ** องค์กรสามารถตัดสินใจได้อย่างอิสระว่า บริการใดจะอยู่ในกลุ่มข้อมูลไหน วิธีที่ดีในการจัดประเภทบริการ คือ จัดไว้ในกลุ่มตามผลกระทบต่อองค์กร ตามค่าเริ่มต้น บริการทั้งหมดจะถูกจัดลงในกลุ่มข้อมูล**ไม่อนุญาตให้มีข้อมูลธุรกิจ** คุณสามารถจัดการบริการในกลุ่มข้อมูล เมื่อคุณสร้างหรือปรับเปลี่ยนคุณสมบัติของนโยบาย DLP จากศูนย์การจัดการ

## <a name="how-data-is-shared-between-data-groups"></a>ข้อมูลถูกแชร์ระหว่างกลุ่มข้อมูลอย่างไร
ข้อมูลไม่สามารถแชร์ระหว่างบริการที่อยู่ในคนละกลุ่มได้ ตัวอย่างเช่น ถ้าคุณจัด SharePoint และ Salesforce ในกลุ่ม**เฉพาะข้อมูลธุรกิจเท่านั้น** และคุณจัด Facebook และ Twitter ในกลุ่ม**ไม่อนุญาตให้มีข้อมูลธุรกิจ** คุณไม่สามารถสร้างโฟลว์ที่ย้ายข้อมูลระหว่าง SharePoint และ Facebook ในขณะที่ข้อมูลไม่สามารถแชร์ระหว่างบริการที่อยู่คนละกลุ่ม คุณสามารถแชร์ข้อมูลระหว่างบริการภายในกลุ่มเดียวกันได้ ดังนั้น กลับไปยังตัวอย่างก่อนหน้า เนื่องจาก SharePoint และ Salesforce ถูกจัดในกลุ่มข้อมูลเดียวกัน โฟลว์ที่สร้างโดยผู้ใช้ของคุณสามารถแชร์ข้อมูลระหว่าง SharePoint และ Salesforce ได้ ในทำนองเดียวกัน ผู้ใช้ปลายทางสามารถสร้างโฟลว์และ PowerApps ที่แชร์ข้อมูลระหว่าง Facebook และ Twitter จุดสำคัญคือ บริการในกลุ่มสามารถแชร์ข้อมูลภายในกลุ่มนั้น ขณะที่บริการที่อยู่คนละกลุ่มไม่สามารถแชร์ข้อมูลกันได้  

นอกจากนี้ ต้องกำหนดกลุ่มข้อมูลหนึ่งเป็นกลุ่ม*เริ่มต้น* เริ่มแรก กลุ่ม**ไม่อนุญาตให้มีข้อมูลธุรกิจ**คือกลุ่ม*เริ่มต้น* และบริการทั้งหมดจะอยู่ในกลุ่มข้อมูลนี้ ผู้ดูแลระบบสามารถเปลี่ยนกลุ่มข้อมูลเริ่มต้นเป็นกลุ่มข้อมูล**เฉพาะข้อมูลธุรกิจเท่านั้น**ได้ **หมายเหตุ** บริการใหม่ที่เพิ่มลงใน Flow จะถูกวางลงในกลุ่ม*เริ่มต้น*ที่กำหนด ด้วยเหตุผลนี้ เราแนะนำให้คุณเก็บ**ไม่อนุญาตให้มีข้อมูลธุรกิจ**เป็นกลุ่มเริ่มต้น และเพิ่มบริการด้วยตนเองลงในกลุ่ม**เฉพาะข้อมูลธุรกิจเท่านั้น** หลังจากที่องค์กรของคุณได้ประเมินผลกระทบของ การอนุญาตให้ข้อมูลทางธุรกิจถูกแชร์กับบริการใหม่

## <a name="add-services-to-a-data-group"></a>เพิ่มบริการไปยังกลุ่มข้อมูล
ในการฝึกปฏิบัตินี้ เราจะเพิ่ม SharePoint และ Salesforce ไปยังกลุ่มข้อมูล**เฉพาะข้อมูลธุรกิจเท่านั้น** ของนโยบายการป้องกันการสูญหายของข้อมูล (DLP) 

1. เลือกลิงก์ **+ เพิ่ม** ภายในกล่องกลุ่ม**เฉพาะข้อมูลธุรกิจเท่านั้น**ของนโยบาย DLP:    
   ![รูปภาพการเพิ่ม](./media/introduction-to-data-groups/add-to-data-group-1.png)  
2. เลือก SharePoint และ Salesforce จากนั้นเลือก**เพิ่มบริการ** เพื่อเพิ่มทั้งสองบริการไปยังกลุ่มเฉพาะข้อมูลธุรกิจเท่านั้น:    
   ![รูปภาพการเพิ่มบริการ](./media/introduction-to-data-groups/add-to-data-group-2.png)  
3. เลือก**บันทึกนโยบาย**จากเมนูที่ด้านบน:  
   ![บันทึกนโยบาย](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. สังเกตว่า ทั้ง SharePoint และ Salesforce ตอนนี้อยู่ในกลุ่มเฉพาะข้อมูลธุรกิจเท่านั้น:  
   ![ปรับปรุงกลุ่มข้อมูลทางธุรกิจ](./media/introduction-to-data-groups/add-to-data-group-3.png)   

ในการฝึกปฏิบัตินี้ คุณได้เพิ่ม SharePoint และ Salesforce ไปยังกลุ่มข้อมูล**เฉพาะข้อมูลธุรกิจเท่านั้น**ของนโยบาย DLP ถ้าบุคคลที่เป็นส่วนหนึ่งของสภาพแวดล้อมของนโยบาย DLP สร้างแอปที่ต้องแชร์ข้อมูลระหว่าง SharePoint หรือ Salesforce และบริการใด ๆ ก็ตามในกลุ่มข้อมูล**ไม่อนุญาตให้มีข้อมูลธุรกิจ** แอปจะไม่ได้รับอนุญาตให้ทำงาน

## <a name="remove-services-from-a-data-group"></a>เอาบริการออกจากกลุ่มข้อมูล
เนื่องจากบริการทั้งหมดต้องอยู่ในกลุ่มข้อมูลกลุ่มใดกลุ่มหนึ่ง เพื่อเอาบริการออกจากกลุ่มที่ระบุ เพียงแค่เพิ่มบริการไปยังอีกกลุ่มหนึ่ง จากนั้นบันทึกนโยบาย  

## <a name="change-the-default-data-group"></a>เปลี่ยนกลุ่มข้อมูลเริ่มต้น
ในการฝึกปฏิบัตินี้ เราจะเปลี่ยนเป็นกลุ่มข้อมูลเริ่มต้นจากกลุ่มข้อมูล**ไม่อนุญาตให้มีข้อมูลธุรกิจ** ไปเป็นกลุ่มข้อมูล**เฉพาะข้อมูลธุรกิจเท่านั้น**  

**เรื่องสำคัญ** บริการใหม่ใด ๆ ที่เพิ่มลงใน Flow จะถูกวางลงในกลุ่ม*เริ่มต้น*ที่กำหนด ด้วยเหตุผลนี้ เราขอแนะนำให้คุณเก็บกลุ่ม**ไม่อนุญาตให้มีข้อมูลธุรกิจ**เป็นกลุ่มเริ่มต้น และเพิ่มบริการด้วยตนเองลงในกลุ่ม**เฉพาะข้อมูลธุรกิจเท่านั้น**

1. เลือก **...**  ที่มุมบนขวาของกลุ่มข้อมูลที่คุณต้องการกำหนดให้เป็นกลุ่มข้อมูลเริ่มต้น:    
   ![เปลี่ยนกลุ่มเริ่มต้น](./media/introduction-to-data-groups/default-data-group-0.png)  
2. เลือก**ตั้งเป็นกลุ่มค่าเริ่มต้น**:  
   ![เปลี่ยนกลุ่มเริ่มต้น](./media/introduction-to-data-groups/default-data-group-1.png)   
3. เลือก**บันทึกนโยบาย**จากเมนูที่ด้านบน:  
   ![เปลี่ยนกลุ่มเริ่มต้น](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. สังเกตว่า กลุ่มข้อมูลถูกกำหนดให้เป็นกลุ่มข้อมูลเริ่มต้นแล้ว:  
   ![เปลี่ยนกลุ่มเริ่มต้น](./media/introduction-to-data-groups/default-data-group-2.png)   

## <a name="next-steps"></a>ขั้นตอนถัดไป
* [เรียนรู้เพิ่มเติมเกี่ยวกับนโยบายการป้องกันการสูญหายของข้อมูล (DLP)](prevent-data-loss.md)
* [เรียนรู้เพิ่มเติมเกี่ยวกับสภาพแวดล้อม](environments-overview-admin.md)   
