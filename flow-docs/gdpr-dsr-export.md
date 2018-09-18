---
title: คำขอการส่งออกเจ้าของข้อมูล GDPR ของ Microsoft Flow | Microsoft Docs
description: เรียนรู้วิธีใช้ Microsoft Flow เพื่อตอบสนองต่อคำขอการส่งออกเจ้าของข้อมูล GDPR
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/24/2018
ms.author: keweare
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: e0f9b8e5b345b4dbc226cff2f42850bb126c09b3
ms.sourcegitcommit: 44bc9de9f06b64615731ceb60a4f46cfcd45b167
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/17/2018
ms.locfileid: "45727147"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-microsoft-flow"></a>ตอบสนองต่อคำขอการส่งออกเจ้าของข้อมูล GDPR ของ Microsoft Flow

ในฐานะส่วนหนึ่งของข้อผูกมัดในการพาคุณไปสู่การทำตามข้อบังคับทั่วไปเกี่ยวกับการคุ้มกันข้อมูล (GDPR) เราจึงพัฒนาคู่มือขึ้นมาเพื่อช่วยให้คุณเตรียมพร้อม คู่มือไม่เพียงอธิบายสิ่งที่เรากำลังดำเนินการเพื่อเตรียมพร้อมสำหรับ GDPR แต่ยังแชร์ตัวอย่างของขั้นตอนที่คุณสามารถใช้ได้กับ Microsoft ในปัจจุบันเพื่อสนับสนุนการปฏิบัติตาม GDPR เมื่อใช้ Microsoft Flow

## <a name="manage-export-requests"></a>การจัดการคำขอการส่งออก

*สิทธิของความสามารถในการเคลื่อนย้ายข้อมูล*ช่วยให้เจ้าของข้อมูลสามารถขอสำเนาของข้อมูลส่วนบุคคลของพวกเขาในรูปแบบอิเล็กทรอนิกส์ได้ (นั่นคือ "มีโครงสร้าง ใช้กันทั่วไป เครื่องสามารถอ่านได้ และมีรูปแบบที่สามารถใช้ร่วมกันได้") ที่อาจถูกส่งไปยังตัวควบคุมข้อมูลอื่น

Microsoft Flow ขอมอบประสบการณ์การใช้งานเพื่อค้นหา หรือส่งออกข้อมูลส่วนบุคคลสำหรับผู้ใช้ที่เฉพาะเจาะจงดังต่อไปนี้:

* **การเข้าถึงเว็บไซต์:** ลงชื่อเข้าใช้ [ศูนย์การจัดการ PowerApps](https://admin.powerapps.com/) หรือ [ศูนย์การจัดการ Microsoft Flow](https://admin.flow.microsoft.com/)

* **การเข้าถึง PowerShell:**  [cdmlets ของ PowerShell ของผู้ดูแลระบบ PowerApps](https://go.microsoft.com/fwlink/?linkid=871804)

|**ข้อมูลของลูกค้า**|**เข้าถึงเว็บไซต์**|**เข้าถึง PowerShell**|
|-----------------|------------------|-------------------|
|บันทึกที่ระบบสร้างขึ้น|[Service Trust Portal ของ Office 365](https://servicetrust.microsoft.com/)|
|ประวัติการเรียกใช้|พอร์ทัลผู้สร้างของ Microsoft Flow||
|โฟลว์|พอร์ทัลผู้สร้างของ Microsoft Flow||
|สิทธิ์โฟลว์| พอร์ทัลผู้สร้างของ Microsoft Flow และศูนย์การจัดการ Microsoft Flow||
|รายละเอียดผู้ใช้งาน||cmdlet ของ PowerApps|
|การเชื่อมต่อ|พอร์ทัลผู้สร้างของ Microsoft Flow|cmdlet ของ PowerApps |
|สิทธิ์การเชื่อมต่อ|พอร์ทัลผู้สร้างของ Microsoft Flow|cmdlet ของ PowerApps |
|ตัวเชื่อมต่อแบบกำหนดเอง|พอร์ทัลผู้สร้างของ Microsoft Flow|cmdlet ของ PowerApps |
|สิทธิของตัวเชื่อมต่อแบบกำหนดเอง|พอร์ทัลผู้สร้างของ Microsoft Flow|cmdlet ของ PowerApps |
|เกตเวย์|พอร์ทัลผู้สร้างของ Microsoft Flow|cmdlets ของ PowerShell เกตเวย์ข้อมูลภายในองค์กร|
|สิทธิ์ของเกตเวย์|พอร์ทัลผู้สร้างของ Microsoft Flow|cmdlets ของ PowerShell เกตเวย์ข้อมูลภายในองค์กร|

## <a name="export-a-flow"></a>การส่งออกโฟลว์

ผู้ใช้ปลายทางหรือผู้ดูแลระบบที่มีสิทธิ์เข้าถึงโฟลว์สามารถส่งออกโฟลว์ได้โดยทำตามขั้นตอนเหล่านี้:

1. ลงชื่อเข้าใช้ [Microsoft Flow](https://flow.microsoft.com/)

1. เลือกลิงก์ **โฟลว์ของฉัน** จากนั้นเลือกขั้นตอนการส่งออกโฟลว์

1. เลือก **... เพิ่มเติม** แล้วเลือก **ส่งออก**

    ![การส่งออกโฟลว์](./media/gdpr-dsr-export/export-flow.png)

1. เลือก**Package (.zip)**

โฟลว์ของคุณพร้อมใช้งานเป็นแพคเกจซิปแล้วในตอนนี้ สำหรับข้อมูลเพิ่มเติม ดูบล็อกโพสต์เกี่ยวกับ[วิธีการส่งออกและนำเข้าโฟลว์](https://flow.microsoft.com/blog/import-export-bap-packages/)

## <a name="export-run-history"></a>ส่งออกประวัติการเรียกใช้

ประวัติการเรียกใช้จะมีรายการการดำเนินการทั้งหมดที่เกิดขึ้นกับโฟลว์ ข้อมูลนี้มีสถานะ เวลาเริ่มต้น ระยะเวลา และรับเข้า/ส่งออกข้อมูลของโฟลว์สำหรับการทริกเกอร์และการดำเนินการ

ผู้ใช้ปลายทางหรือผู้ดูแลระบบที่ได้รับอนุญาตให้เข้าถึงโฟลว์ผ่านศูนย์การจัดการ Microsoft Flow สามารถทำตามขั้นตอนต่อไปนี้เพื่อส่งออกข้อมูลได้:

1. ลงชื่อเข้าใช้ [Microsoft Flow](https://flow.microsoft.com/)
1. เลือกลิงก์ **โฟลว์ของฉัน** จากนั้นเลือกโฟลว์ที่คุณต้องการส่งออกประวัติการเรียกใช้
1. ในบานหน้าต่าง **ประวัติการเรียกใช้** เลือก **ดูทั้งหมด**

    ![ประวัติการเรียกใช้](./media/gdpr-dsr-export/run-history.png)

1. เลือก **ดาวน์โหลด CSV**

    ![ดาวน์โหลด CSV](./media/gdpr-dsr-export/download-csv.png)

ประวัติการเรียกใช้จะถูกดาวน์โหลดเป็นไฟล์.csv เพื่อให้คุณสามารถเปิดใน Microsoft Excel หรือตัวแก้ไขข้อความ และวิเคราะห์ผลลัพธ์เพิ่มเติมได้

## <a name="export-a-users-activity-feed"></a>ส่งออกตัวดึงข้อมูลกิจกรรมของผู้ใช้

ใน [Microsoft Flow](https://flow.microsoft.com/) ตัวดึงข้อมูลกิจกรรมแสดงประวัติกิจกรรม ความล้มเหลว และการแจ้งเตือนของผู้ใช้ ผู้ใช้ทุกคนสามารถดูตัวดึงข้อมูลกิจกรรมของพวกเขาได้โดยทำตามขั้นตอนเหล่านี้:

1. ลงชื่อเข้าใช้ [Microsoft Flow](http://flow.microsoft.com/) เลือกไอคอนกระดิ่งใกล้กับมุมขวาบน แล้วเลือก **แสดงกิจกรรมทั้งหมด**

    ![แสดงตัวดึงข้อมูลกิจกรรม](./media/gdpr-dsr-export/show-activity-feed.png)

1. ในหน้าจอ **กิจกรรม** ให้คัดลอกผลลัพธ์ แล้ววางลงในตัวแก้ไขเอกสารเช่น Microsoft Word

    ![แสดงตัวดึงข้อมูลกิจกรรม](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>การส่งออกการเชื่อมต่อของผู้ใช้

การเชื่อมต่อจะอนุญาตให้โฟลว์เชื่อมต่อกับ API แอปพลิเคชัน SaaS และระบบของบริษัทอื่น ทำตามขั้นตอนเหล่านี้เพื่อดูการเชื่อมต่อของคุณ:

1. ลงชื่อเข้าใช้ [Microsoft Flow](http://flow.microsoft.com/) เลือกไอคอนรูปเฟืองใกล้กับมุมขวาบน จากนั้นเลือก **การเชื่อมต่อ**

    ![แสดงการเชื่อมต่อ](./media/gdpr-dsr-export/show-connections.png)
1. คัดลอกผลลัพท์นั้นแล้ววางลงในตัวแก้ไขเอกสารเช่น Microsoft Word

cmdlet ของ PowerShell ของผู้ดูแลระบบ PowerApps

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnection -CreateBy $userId | ConvertTo-Json |Out-File -FilePath "UserConnections.txt"
```

## <a name="export-a-list-of-a-users-connection-permissions"></a>ส่งออกรายการสิทธิ์เชื่อมต่อของผู้ใช้

ผู้ใช้สามารถส่งออกการกำหนดบทบาทการเชื่อมต่อสำหรับการเชื่อมต่อทั้งหมดที่พวกเขามีสิทธิ์เข้าถึงผ่านทางฟังก์ชัน ConnectionRoleAssignment ใน [cdmlets PowerShell ของ PowerApps](https://go.microsoft.com/fwlink/?linkid=871804)ได้

```PowerShell
Add-PowerAppsAccount
Get-ConnectionRoleAssignment | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt"
```
cmdlet ของ PowerShell ของผู้ดูแลระบบ PowerApps

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectionRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt" 
```

## <a name="export-a-users-custom-connectors"></a>การส่งออกตัวเชื่อมต่อแบบกำหนดเองของผู้ใช้

ตัวเชื่อมต่อแบบกำหนดเองเพิ่มเติมจากเวลาของตัวเชื่อมต่อกล่อง และอนุญาตการเชื่อมต่อไปยัง API, SaaS และระบบที่พัฒนาตามที่กำหนดเองอื่นๆ คุณสามารถโอนหรือลบความเป็นเจ้าของตัวเชื่อมต่อแบบกำหนดเองออกได้

ทำตามขั้นตอนเหล่านี้เพื่อส่งออกรายการของตัวเชื่อมต่อลูกค้า:

1. นำทางไปยัง[Microsoft Flow](https://flow.microsoft.com)
1. เลือกการตั้งค่าที่เป็นไอคอน**เฟือง**
1. เลือก**ตัวเชื่อมต่อแบบกำหนดเอง**
1. คัดลอก และวางรายการของตัวเชื่อมต่อแบบกำหนดเองลงในตัวแก้ไขข้อความเช่น Microsoft Word

    ![การการส่งออกตัวเชื่อมต่อแบบกำหนดเอง](./media/gdpr-dsr-export/export-custom-connectors.png)

นอกเหนือจากประสบการณ์การใช้งานอยู่ใน Microsoft Flow คุณสามารถใช้ฟังก์ชันตัวเชื่อมต่อทำงานได้จาก [cmdlet ของ PowerApps PowerShell](https://go.microsoft.com/fwlink/?linkid=871804) เมื่อต้องการส่งออกตัวเชื่อมต่อแบบกำหนดเองทั้งหมดได้

~~~~
Add-PowerAppsAccount
Get-Connector -FilterNonCustomConnectors | ConvertTo-Json | Out-File -FilePath "CustomConnectors.txt"
~~~~

cmdlet ของ PowerShell ของผู้ดูแลระบบ PowerApps

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnector -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserCustomConnectors.txt"  
```

## <a name="export-a-users-custom-connector-permissions"></a>การส่งออกตัวเชื่อมต่อแบบกำหนดเองของผู้ใช้

ผู้ใช้สามารถส่งออกสิทธิ์ตัวเชื่อมต่อแบบกำหนดเองทั้งหมดที่พวกเขาได้สร้างโดยใช้ฟังก์ชัน ConnectorRoleAssignment ใน [cdmlets ของ PowerShell ของ PowerApps](https://go.microsoft.com/fwlink/?linkid=871804) ได้

```PowerShell
Add-PowerAppsAccount
Get-ConnectorRoleAssignment | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"
```

cmdlet ของ PowerShell ของผู้ดูแลระบบ PowerApps

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectorRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"   
```

## <a name="export-approval-history"></a>การส่งออกประวัติการอนุมัติ

ประวัติของการอนุมัติ Microsoft Flow จะรวบรวมระเบียนการอนุมัติในอดีตที่ได้รับหรือส่งของผู้ใช้ ผู้ใช้ทุกคนสามารถดูประวัติการอนุมัติของพวกเขาได้โดย:

1. ลงชื่อเข้าใช้ [Microsoft Flow](http://flow.microsoft.com/) เลือก **การอนุมัติ** จากนั้นเลือก **ประวัติ**

    ![ดูประวัติการอนุมัติ](./media/gdpr-dsr-export/view-approval-history.png)

1. รายการแสดงการอนุมัติที่ผู้ใช้งานได้รับ ผู้ใช้สามารถแสดงการอนุมัติที่พวกเขาส่ง โดยการเลือกลูกศรลงถัดจาก **รับ** แล้วเลือก **ส่ง** ได้

    ![ดูการอนุมัติที่ได้รับ](./media/gdpr-dsr-export/view-received-approvals.png)

## <a name="export-user-details"></a>ส่งออกรายละเอียดผู้ใช้
รายละเอียดผู้ใช้ให้ความเชื่อมโยงระหว่างผู้ใช้และผู้เช่าที่เฉพาะเจาะจง ผู้ดูแลระบบสามารถส่งออกข้อมูลนี้ได้โดยการเรียกใช้ cmdlet **AdminFlowUserDetails รับ** และส่งผ่านใน ID ออบเจ็กต์สำหรับผู้ใช้

cmdlet ของ PowerShell ของผู้ดูแลระบบ PowerApps

```PowerShell
Add-PowerAppsAccount

Get-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

## <a name="export-gateway-settings"></a>ส่งออกการตั้งค่าเกตเวย์
การตอบสนองต่อการร้องขอการส่งออกเจ้าของข้อมูลสำหรับเกตเวย์ข้อมูลภายในองค์กรสามารถดูได้[ที่นี่](https://docs.microsoft.com/power-bi/service-gateway-onprem#tenant-level-administration)

