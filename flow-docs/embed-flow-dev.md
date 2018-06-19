---
title: รวม Microsoft Flow เข้ากับเว็บไซต์และแอป | Microsoft Docs
description: ฝังประสบการณ์การใช้งาน Microsoft Flow ลงในเว็บไซต์หรือแอปของคุณ
services: ''
suite: flow
documentationcenter: na
author: bbarath
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/09/2017
ms.author: barathb
ms.openlocfilehash: af03ee70b09ba5ee1164a9a7ea5019b13c19eec6
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "31001239"
---
# <a name="integrate-microsoft-flow-with-websites-and-apps"></a>รวม Microsoft Flow เข้ากับเว็บไซต์และแอป
ฝัง Microsoft Flow ลงในแอปหรือเว็บไซต์ได้โดยตรง เพื่อให้ผู้ใช้มีวิธีที่ง่ายในการทำให้หน้าที่ทั้งส่วนบุคคลและด้านอาชีพเป็นกระบวนการอัตโนมัติ

ในการสร้างโฟลว์ ผู้ใช้จะต้องมี**บัญชี Microsoft** หรือบัญชีที่ทำงานหรือโรงเรียนใน **Azure Active Directory** Microsoft Flow ไม่สนับสนุนบางโซลูชัน ตัวอย่างเช่น โซลูชัน White-Lebel ที่สนับสนุนข้อมูลประจำตัวใดก็ตามที่ระบบของคุณใช้ (เว้นแต่ว่าจะใช้บัญชี Microsoft หรือ AAD)

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น
* [สร้างตัวเชื่อมต่อแบบกำหนดเอง](register-custom-api.md)ที่เชื่อมต่อบริการของคุณกับ Microsoft Flow
* [สร้างและเผยแพร่เทมเพลตอย่างน้อยหนึ่งเทมเพลต](publish-a-template.md)ที่ใช้ API ของคุณ

## <a name="show-templates-for-your-scenarios"></a>แสดงเทมเพลตสำหรับสถานการณ์ของคุณ
ในการเริ่มต้น เพิ่มรหัสนี้เพื่อแสดงเทมเพลตโฟลว์โดยตรงในเว็บไซต์ของคุณ:

```html
<iframe src="https://flow.microsoft.com/{locale}/widgets/templates/?q={search term}
&pagesize={number of templates}&destination={destination}"></iframe>
```

**หมายเหตุ**: เราได้เพิ่มตัวแบ่งบรรทัดเพื่อให้รหัสแสดงได้ดียิ่งขึ้นบนหน้าดังกล่าว

| พารามิเตอร์ | คำอธิบาย |
| --- | --- |
| ตำแหน่งที่ตั้ง |รหัสภาษาและภูมิภาคที่ประกอบด้วยสี่ตัวอักษรสำหรับมุมมองเทมเพลต ตัวอย่างเช่น `en-us`แสดงภาษาอังกฤษอเมริกัน และ`de-de`แสดงภาษาเยอรมัน |
| คำที่ใช้ค้นหา |คำที่ใช้ค้นหาสำหรับเทมเพลตที่คุณต้องการให้แสดงในมุมมอง ตัวอย่างเช่น ค้นหา`wunderlist`เพื่อแสดงเทมเพลตสำหรับ Wunderlist |
| จำนวนของเทมเพลต |จำนวนเทมเพลตที่คุณต้องการให้แสดงในมุมมอง |
| ปลายทาง |เพจที่เปิดขึ้นเมื่อผู้ใช้คลิกเทมเพลตนั้น ระบุ`details`เพื่อแสดงรายละเอียดเกี่ยวกับเทมเพลต หรือระบุ`new`เพื่อเปิดตัวออกแบบ Microsoft Flow |
| พารามิเตอร์.{name } |บริบทเพิ่มเติมเพื่อส่งผ่านลงในโฟลว์ |

ถ้าพารามิเตอร์ปลายทางคือ`new`, Microsoft Flow เปิดขึ้นเมื่อผู้ใช้คลิกเทมเพลต และจะสามารถสร้างโฟลว์ในตัวออกแบบได้ ดูส่วนถัดไปถ้าคุณต้องการให้ประสบการณ์การใช้งานเต็มทำงานจากภายในแอป

### <a name="passing-additional-parameters-to-the-flow"></a>การส่งผ่านพารามิเตอร์เพิ่มเติมไปยังโฟลว์
ถ้าผู้ใช้อยู่ในบางบริบทในเว็บไซต์หรือแอปของคุณ คุณอาจต้องการส่งบริบทนั้นไปยังโฟลว์ ตัวอย่างเช่น ผู้ใช้หนึ่งอาจเปิดเทมเพลตสำหรับ*แจ้งให้ฉันทราบเมื่อมีรายการถูกเพิ่มไปยังรายการ* ขณะที่ดูรายการใน Wunderlist ได้ การทำตามขั้นตอนเหล่านี้คุณสามารถส่งผ่าน ID รายการเป็น*พารามิเตอร์*ไปยังโฟลว์ได้:

1. กำหนดพารามิเตอร์ในเทมเพลตโฟลว์ก่อนที่คุณจะเผยแพร่ พารามิเตอร์มีลักษณะเหมือน `@{parameters('parameter_name')}`
2. ส่งผ่านพารามิเตอร์ใน iframe src ตัวอย่างเช่น เพิ่ม `&parameters.listName={the name of the list}` ถ้าคุณมีพารามิเตอร์ที่เรียกว่า **listName**

### <a name="full-sample"></a>ตัวอย่างแบบเต็ม
ในการแสดงเทมเพลตที่นิยมสูงสุดสี่เทมเพลตเกี่ยวกับ Wunderlist ในภาษาเยอรมัน และเพื่อเริ่มต้นผู้ใช้ด้วย **myCoolList**:

```html
<iframe src="https://flow.microsoft.com/de-de/widgets/templates/?q=wunderlist
&pagesize=4&destination=details&parameters.listName=myCoolList"></iframe>
```

## <a name="embed-the-management-of-flows"></a>ฝังการจัดการของโฟลว์
ใช้ Flow SDK ที่ได้รับการรับรองความถูกต้องเพื่อให้ผู้ใช้สามารถสร้างและจัดการโฟลว์ได้โดยตรงจากเว็บไซต์หรือแอปของคุณ (แทนการนำทางไปยังพอร์ทัล Microsoft Flow) คุณจะต้องลงชื่อผู้ใช้เข้าใช้บัญชี Microsoft หรือ Azure Active Directory เพื่อใช้ SDK ที่รับรองความถูกต้อง

> [!NOTE]
> ผู้ใช้ทั้งหมดที่ใช้ Microsoft Flow ในแอปพลิเคชันของคุณจะเป็นผู้ใช้ Microsoft Flow ไม่มีทางที่จะสามารถซ่อนตราสินค้า Microsoft Flow ได้
> 
> 

### <a name="include-the-javascript-for-the-authenticated-sdk"></a>รวม JavaScript สำหรับ SDK ที่รับรองความถูกต้อง
รวม SDK ในโค้ด HTML ของคุณโดยทำตามตัวอย่างนี้ คุณอาจดาวน์โหลด ลดขนาด และทำแพคเกจ SDK ด้วยผลิตภัณฑ์ของคุณ

```javascript
<script src="https://flow.microsoft.com/content/msflowsdk-1.1.js" async defer></script>
```

### <a name="create-a-container-to-contain-the-view"></a>สร้างคอนเทนเนอร์เพื่อเก็บมุมมอง
เพิ่ม HTML div:

```html
<div id="flowDiv" class="flowContainer"></div>
```

เราขอแนะนำให้คุณจัดลักษณะคอนเทนเนอร์นี้ เพื่อให้ปรากฏในขนาดที่เหมาะสมในประสบการณ์การใช้งานของคุณ:

```html
<head>
    <style>
        .flowContainer iframe {
            width: 400px;
            height: 1000px;
            border: none;
            overflow: hidden;
    }
    </style>
</head>
```

โปรดทราบว่า iframe จะไม่แสดงอย่างเหมาะสมหากมีพิกเซลความกว้างต่ำกว่า 320 และจะไม่เติมเนื้อหาากมีพิกเซลความสูงกว่า 1200 ความสูงใด ๆ ควรใช้งานได้

### <a name="authentication-against-the-sdk"></a>รับรองความถูกต้องเทียบกับ SDK
สำหรับการทำรายการโฟลว์ที่ผู้ใช้ได้รับอนุญาตอยู่แล้วและเพื่อสร้างโฟลว์จากเทมเพลต ให้ใส่ authToken จาก AAD

```javascript
<script>
    window.msFlowSdkLoaded = function() {
        var sdk = new MsFlowSdk({
            hostName:'https:/flow.microsoft.com'
        });
        var widget = sdk.renderWidget('flows', {
            container: 'flowDiv'
            environmentId: '[environmentId]'    // find environment id from browser URL when you 
                                                // click on 'my flows'
                                                //ex: https://flow.microsoft.com/manage/environments/[environmentId]/flows
        });
        widget.callbacks.GET_ACCESS_TOKEN = function(requestParam, widgetDoneCallback)
       {
            var authCallback = function(token) {
                widgetDoneCallback(null, {
                    token: token // Get AAD access token from your backend system
                });
            };
        }
    }
</script>
```

คุณสามารถค้นหา `environmentId` ได้โดยการเรียกใช้ API ต่อไปนี้ ซึ่งจะส่งกลับรายการของผู้ใช้สภาพแวดล้อมที่มีสิทธิ์เข้าถึง:

```http
GET https://management.azure.com/providers/Microsoft.ProcessSimple/environments
?api-version=2016-11-01 
```

ซึ่งจะส่งกลับการตอบสนอง JSON ด้วยรายการสภาพแวดล้อมที่ให้คุณสามารถเลือกสภาพแวดล้อมใดก็ได้ คุณสามารถค้นหาสภาพแวดล้อมผู้ใช้ค่าเริ่มต้นได้โดยการตรวจสอบคุณสมบัติดังกล่าว`properties.isDefault=true`

ในตัวอย่างนี้ `requestParam`ถูกกำหนดเป็น:

```javascript
export interface IRpcRequestParam {
    callInfo: IRpcCallInfo,
    data?: any;
}
```

ถัดไป `widgetDoneCallback`คือฟังก์ชันเรียกกลับที่จำเป็นต้องถูกเรียกใช้เมื่อโฮสต์มีโทเค็น ทำขั้นตอนนี้เนื่องจากการพัฒนาโทเค็นมีแนวโน้มเป็นกระบวนการต่างเวลา พารามิเตอร์ที่จำเป็นต้องมีการส่งผ่านเมื่อเรียกใช้ฟังก์ชันนี้คือ `(errorResult: any, successResult: any)` SuccessResult จะขึ้นอยู่กับชนิดของการเรียกกลับ สำหรับ `GetAccessToken` ชนิดคือ:

```javascript
export interface IGetAccessTokenResult {
    token: string;
}
```
