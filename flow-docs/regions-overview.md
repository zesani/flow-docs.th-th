---
title: ภาพรวมของภูมิภาคสำหรับ Microsoft Flow | Microsoft Docs
description: ภาพรวมพร้อมคำถามและคำตอบเกี่ยวกับภูมิภาคใน Microsoft Flow
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
ms.date: 08/28/2017
ms.author: deonhe
ms.openlocfilehash: ec9b72e570c562c091aefd370f73d6862ff56f18
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "31001434"
---
# <a name="faq-for-regions-in-microsoft-flow"></a>ถามที่ถามบ่อยสำหรับภูมิภาคใน Microsoft Flow
เอกสารนี้ให้รายการของคำถามที่ถามบ่อยเกี่ยวกับ Microsoft Flow

## <a name="how-do-i-find-out-where-my-flow-is-deployed"></a>ฉันรู้ได้อย่างไรว่า้โฟลว์ของฉันถูกปรับใช้ที่ไหน?
โฟลว์ของคุณถูกปรับใช้ใน[ภูมิภาค](https://azure.microsoft.com/regions/)ที่โฮสต์[สภาพแวดล้อม](environments-overview-admin.md) ตัวอย่างเช่น ถ้าสภาพแวดล้อมของคุณถูกสร้างขึ้นในภูมิภาคยุโรป โฟลว์ของคุณจะถูกปรับใช้ในศูนย์ข้อมูลยุโรป

ผู้ดูแลระบบสามารถระบุภูมิภาคที่ใช้ ถ้าพวกเขาลงชื่อเข้าใช้ที่[ศูนย์การจัดการ](https://admin.flow.microsoft.com) Microsoft Flow ได้ แท็บ**สภาพแวดล้อม** แสดงรายการสภาพแวดล้อมที่มีอยู่ทั้งหมดและภูมิภาคของสภาพแวดล้ามนั้น ๆ

![ดูสภาพแวดล้อม](media/regions-overview/environments-list.png)

## <a name="what-regions-are-available"></a>มีภูมิภาคใดบ้างที่พร้อมใช้งาน?
* สหรัฐอเมริกา
* ยุโรป
* เอเชีย
* ออสเตรเลีย
* อินเดีย
* ญี่ปุ่น
* แคนาดา

## <a name="what-features-are-specific-to-a-given-region"></a>คุณลักษณะใดบ้าง ที่มีใช้เฉพาะภูมิภาค?
สภาพแวดล้อมสามารถสร้างขึ้นในภูมิภาคต่าง ๆ กัน และถูกผูกไว้กับตำแหน่งที่ตั้งทางภูมิศาสตร์ เมื่อคุณสร้างโฟลว์ในสภาพแวดล้อม โฟลว์นั้นจะถูกปรับใช้ในศูนย์ข้อมูลในตำแหน่งที่ตั้งทางภูมิศาสตร์นั้น ซึ่งมีผลกับรายการใด ๆ ที่คุณสร้างขึ้นในสภาพแวดล้อม รวมถึง Common Data Model, โฟลว์, การเชื่อมต่อ, เกตเวย์, แอป และตัวเชื่อมต่อแบบกำหนดเอง

เพื่อประสิทธิภาพที่ดีที่สุด สร้างสภาพแวดล้อมของคุณในภูมิภาคที่ใกล้ผู้ใช้ของคุณมากที่สุด ตัวอย่างเช่น ถ้าผู้ใช้ของคุณอยู่ในยุโรป สร้างสภาพแวดล้อมของคุณในภูมิภาคยุโรป ถ้าผู้ใช้ของคุณอยู่ในสหรัฐอเมริกา สร้างสภาพแวดล้อมของคุณในภูมิภาคสหรัฐอเมริกา

## <a name="gateways"></a>เกตเวย์
เกตเวย์:

* ไม่มีในภูมิภาคอินเดีย
* ได้รับการสนับสนุนในสภาพแวดล้อมเริ่มต้นเท่านั้น ไม่สามารถสร้างในสภาพแวดล้อมแบบกำหนดเองได้

## <a name="is-microsoft-flow-available-in-national-clouds"></a>Microsoft Flow พร้อมใช้งานในระบบคลาวด์ในประเทศหรือไม่?
ไม่ Microsoft Flow ยังไม่พร้อมใช้งานในระบบคลาวด์ในประเทศ การสนับสนุนระบบคลาวด์ในประเทศ วางแผนไว้สำหรับปี 2018

## <a name="what-outbound-ip-addresses-are-used-in-each-region"></a>ที่อยู่ IP ขาออกอะไรบ้างที่ถูกใช้ในแต่ละภูมิภาค?
ดูที่ [ขีดจำกัดและการกำหนดค่า](limits-and-config.md)

