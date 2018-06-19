---
title: สร้างตัวเชื่อมต่อแบบกำหนดเองและฝังโฟลว์ | Microsoft Docs
description: สร้างตัวเชื่อมต่อแบบกำหนดเอง แชร์ ฝังโฟลว์ และอื่น ๆ อีกมาก
services: ''
suite: flow
documentationcenter: na
author: bbarath
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2017
ms.author: barathb
ms.openlocfilehash: a3f1e21cfbf00749a0ef09c0363da162f0419f42
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "31001219"
---
# <a name="start-to-build-with-microsoft-flow"></a>เริ่มสร้างด้วย Microsoft Flow

ต่อไปนี้เป็นบางวิธีที่คุณสามารถขยายการใช้งานของคุณด้วย Microsoft Flow:

* สร้างและเชื่อมต่อกับตัวเชื่อมต่อแบบกำหนดเอง
* แชร์ตัวเชื่อมต่อแบบกำหนดเองของคุณกับผู้ใช้ Microsoft Flow ทั้งหมด
* ฝังประสบการณ์การใช้งานโฟลว์ภายในแอป
* ไฮไลต์ตัวเชื่อมต่อแบบกำหนดเองทั้งหมดเพื่อให้ผู้ใช้สามารถโต้ตอบกับ Microsoft Flow ในแบบที่ดีที่สุดสำหรับผู้ใช้

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

* บัญชี [Microsoft Flow](https://flow.microsoft.com)

## <a name="create-a-custom-connector"></a>สร้างตัวเชื่อมต่อแบบกำหนดเอง

ถ้าคุณมีบริการเว็บที่คุณต้องการเชื่อมต่อจาก Microsoft Flow ก่อนอื่นคุณจะต้องสร้างตัวเชื่อมต่อแบบกำหนดเองก่อน เมื่อคุณลงทะเบียนตัวเชื่อมต่อแบบกำหนดเอง คุณสอน Microsoft Flow เกี่ยวกับลักษณะของบริการบนเว็บของคุณ รวมถึงการรับรองความถูกต้องที่ต้องมี ทริกเกอร์ และการดำเนินการที่สนับสนุน และพารามิเตอร์ และผลลัพธ์สำหรับแต่ละการดำเนินการเหล่านั้น

ทำตามบทช่วยสอนนี้เพื่อเรียนรู้วิธีการ[ลงทะเบียนและใช้ตัวเชื่อมต่อแบบกำหนดเอง](https://powerapps.microsoft.com/tutorials/register-custom-api/) หลังจากที่คุณลงทะเบียนตัวเชื่อมต่อแบบกำหนดเองของคุณแล้ว คุณสามารถแชร์ตัวเชื่อมต่อนั้นได้ภายในองค์กรของคุณเพื่อทำการทดสอบ

## <a name="share-a-custom-connector-with-all-microsoft-flow-users"></a>แชร์ตัวเชื่อมต่อแบบกำหนดเองกับผู้ใช้ Microsoft Flow ทั้งหมด

หลังจากที่คุณทดสอบตัวเชื่อมต่อแบบกำหนดเองของคุณอย่างเต็มที่แล้ว เริ่ม[กระบวนการตรวจทาน](https://flow.microsoft.com/blog/calling-all-saas-apps-now-you-can-build-your-own-connector-for-flow-and-logic-apps/)เพื่อให้ได้รับการอนุมัติโดย Microsoft ในการแชร์กับผู้ใช้ Microsoft Flow อื่น ๆ ทั้งหมด

ต่อไปนี้คือสิ่งที่คุณจำเป็นต้องมีสำหรับกระบวนการตรวจทาน:

* ไฟล์ OpenAPI ที่แสดง API ของคุณและข้อมูลการรับรองความถูกต้องใด ๆ
* ไอคอนสำหรับตัวเชื่อมต่อของคุณ
* คำอธิบายของตัวเชื่อมต่อของคุณ
* แนวคิดประมาณ 10 แนวคิดว่าตัวเชื่อมต่อของคุณจะเป็นประโยชน์กับผู้ใช้อื่นผ่านเทมเพลตต่าง ๆ อย่างไร

หลังจากที่คุณส่งข้อมูลนี้ Microsoft เริ่มต้นประเมินฟังก์ชันการทำงานของ API ของคุณใน Microsoft Flow และ Microsoft PowerApps

## <a name="embed-the-flow-experience-into-your-website-or-app"></a>ฝังประสบการณ์การใช้งานโฟลว์ลงในเว็บไซต์หรือแอปของคุณ

คุณสามารถ[ฝัง](embed-flow-dev.md) Microsoft Flow ลงในแอปของคุณเพื่อให้ได้การรวมกันในบริบทที่ลึกระหว่างแอปของคุณและบริการอื่น ๆ ทั้งหมดที่ Microsoft Flow สนับสนุน ตัวอย่างเช่น คุณสามารถ:

* เรียกดูเทมเพลตทั้งหมดที่เกี่ยวข้องกับบริการของคุณ และให้ผู้ใช้เลือกเทมเพลตหนึ่ง
* จัดการโฟลว์ที่ผู้ใช้มีที่เกี่ยวข้องกับแอปของคุณ

## <a name="next-steps"></a>ขั้นตอนถัดไป

เรียนรู้วิธีการ[ฝัง](embed-flow-dev.md) Microsoft Flow ลงในแอปของคุณ
