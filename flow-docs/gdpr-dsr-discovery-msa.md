---
title: การร้องขอเพื่อค้นหาเจ้าของข้อมูล Microsoft Flow GDPR สำหรับบัญชี Microsoft (MSA) | Microsoft Docs
description: เรียนรู้วิธีใช้ Microsoft Flow เพื่อตอบสนองคำขอการค้นหาเจ้าของข้อมูล GDPR สำหรับบัญชี Microsoft
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
ms.date: 5/16/2018
ms.author: keweare
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 9a7031780ed6582d9f881571c3d07ce8aece074d
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690746"
---
# <a name="respond-to-gdpr-data-subject-discovery-requests"></a>ตอบสนองต่อคำขอการค้นหาเจ้าของข้อมูล GDPR 

ขั้นตอนแรกในการตอบสนองต่อคำขอ DSR คือค้นหาข้อมูลส่วนบุคคลที่มีเจ้าของคำขอ
นี่คือข้อมูลสรุปของทรัพยากร Microsoft Flow ที่ประกอบด้วยข้อมูลส่วนบุคคลสำหรับผู้ใช้ที่รับรองความถูกต้องด้วยบัญชีผู้ใช้ Microsoft (MSA) ของตน

|ทรัพยากร|วัตถุประสงค์|
|-----|-----|
|ประวัติการเรียกใช้|ใส่ประวัตการดำเนินการของแต่ละโฟลว์สำหรับ 28 วันที่ผ่านมา ข้อมูลนี้มีเวลาเริ่มต้น เวลาสิ้นสุด สถานะ และข้อมูลการรับเข้า/ส่งออกทั้งหมดสำหรับแต่ละโฟลว์ที่เรียกใช้งาน เรียนรู้เพิ่มเติมเกี่ยวกับ[ประวัติการเรียกใช้โฟลว์](https://flow.microsoft.com/blog/download-history-recurrence/)|
|ตัวดึงข้อมูลกิจกรรม| แสดงบทสรุปของแต่ละกิจกรรมของโฟลว์ การรวมถึงสถานะรัน ความล้มเหลว และการแจ้งเตือน|
|โฟลว์|ตรรกะของเวิร์กโฟลว์สำหรับการ[โฟลว์](https://docs.microsoft.com/flow/get-started-logic-flow)|
|การเชื่อมต่อ|ถูกใช้โดยตัวเชื่อมต่อและอนุญาตให้มีการเชื่อมต่อกับ API ระบบ ฐานข้อมูล และอื่น ๆ อีกมาก [เรียนรู้เพิ่มเติมเกี่ยวกับการเชื่อมต่อ](add-manage-connections.md)|

