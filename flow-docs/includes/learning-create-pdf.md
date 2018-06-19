ในหัวข้อนี้ คุณจะเห็นวิธีที่ Contoso Flooring ใช้ Microsoft Flow ในการแปลงเอกสารให้เป็นรูปแบบมาตรฐานโดยอัตโนมัติ จากนั้นจัดเก็บเอกสารใน SharePoint Online เพื่อเก็บรักษาในระบบคลาวด์ คุณจะสร้างโฟลว์ที่ตรวจหาเมื่อไฟล์ใหม่ถูกเพิ่มลงในโฟลเดอร์ OneDrive for Business แล้วแปลงไฟล์นั้นเป็น PDF และเก็บไว้ในโฟลเดอร์ SharePoint Online 

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น
สำหรับสถานการณ์สมมตินี้ คุณจะต้องมีบัญชีกับ **Muhimbi** ซึ่งเป็นบริการแปลง PDF ถ้าคุณยังไม่มีบัญชี Muhimbi คุณสามารถลงทะเบียนสำหรับ[รุ่นทดลองใช้ 30 วัน](http://www.muhimbi.com/Products/PDF-Converter-for-SharePoint/Products-PDF-Converter-for-SharePoint-Free-Trial.aspx)ได้ ทำตามคำแนะนำบนหน้านั้น เพื่อปรับใช้แอปผ่านไซต์ SharePoint Online ของคุณ 

## <a name="create-the-source-and-target-folders"></a>สร้างโฟลเดอร์ต้นทางและปลายทาง
ก่อนอื่น คุณจำเป็นต้องสร้างโฟลเดอร์ต้นทางและปลายทางบน OneDrive for Business และ SharePoint Online 

1. ใน OneDrive for Business ภายใต้**ไฟล์** สร้างโฟลเดอร์ที่ชื่อว่า **Finished Documents** 
   
    ![](./media/learning-create-pdf/onedrive-folder.png)
2. ใน SharePoint Online ใน**เอกสารที่แชร์** สร้างโฟลเดอร์ที่ชื่อว่า **PDF – Finished files** 
   
    ![](./media/learning-create-pdf/sharepoint-folder.png)

## <a name="create-the-flow"></a>สร้างโฟลว์
1. ใน Microsoft Flow เลือก**โฟลว์ของฉัน** และเลือก**สร้างจากว่างเปล่า** 
   
    ![](./media/learning-create-pdf/create-blank-flow.png)
2. เลือก**ค้นหาตัวเชื่อมต่อและทริกเกอร์นับร้อย**
3. ค้นหา **OneDrive** เลือก **OneDrive for Business** จากนั้น เลือกทริกเกอร์ **OneDrive for Business - เมื่อมีการสร้างไฟล์ใหม่** ใน**โฟลเดอร์** เลือกไอคอนโฟลเดอร์ และเลือกโฟลเดอร์ **Finished Documents** ที่คุณสร้างในขั้นตอนก่อนหน้า 
   
    ![](./media/learning-create-pdf/onedrive-trigger.png)
4. เลือก**ขั้นตอนใหม่** แล้วเลือก**เพิ่มการดำเนินการ** 
   
    ![](./media/learning-create-pdf/new-action.png)
5. ค้นหา **Muhimbi** เลือกตัวเชื่อมต่อ **Muhimbi PDF** และเลือกการดำเนินการ **Muhimbi PDF – แปลงเอกสาร**
   
    ![](./media/learning-create-pdf/muhimbi-action.png)
6. ในตอนนี้ คุณอาจได้รับพร้อมท์จาก Microsoft Flow เพื่อรับรองความถูกต้องกับ Muhimbi คุณจะต้องลงทะเบียนกับ Muhimbi โดยใช้ **ID ผู้เช่า SharePoint** ของคุณเพื่อให้ Microsoft Flow ใช้บริการ Muhimbi 
   
   1. เพื่อค้นหา ID ผู้เช่า เลือกไอคอนรูปเฟือง**การตั้งค่า** ใน SharePoint Online และเลือก**การตั้งค่าไซต์**
   2. ภายใต้**การดูแลไซต์คอลเลกชัน** เลือก**สิทธิ์ของแอปในไซต์คอลเลกชัน** ID ผู้เช่าของคุณเป็นตัวระบุที่ตามหลังเครื่องหมาย "**@**" ในรายการของแอปใด ๆ 
      
       ![](./media/learning-create-pdf/tenant-id.png)
7. ในการดำเนินการ**แปลงเอกสาร** ตั้งค่าต่อไปนี้:
   
   * **ชื่อไฟล์ต้นทาง**: จากรายการเนื้อหาแบบไดนามิก เลือก**ชื่อไฟล์**
   * **เนื้อหาไฟล์ต้นทาง**: จากรายการเนื้อหาแบบไดนามิก เลือก**เนื้อหาไฟล์**
   * **รูปแบบผลลัพธ์**: จากรายการดรอปดาวน์ เลือก**PDF**
     
     ![](./media/learning-create-pdf/muhimbi-configuration.png)

ที่ผ่านมา คุณได้กำหนดค่าโฟลว์ของคุณ ด้วยขั้นตอนต่อไปนี้: 

1. โฟลว์ถูกทริกเกอร์เมื่อใดก็ตามที่ไฟล์ใหม่ถูกเพิ่มในโฟลเดอร์ OneDrive for Business ที่กำหนด 
2. บริการ Muhimbi แปลงไฟล์นั้นเป็น PDF 

สำหรับขั้นตอนสุดท้าย คุณจะเพิ่มการดำเนินการที่จะย้ายเอกสาร PDF ไปยังโฟลเดอร์ SharePoint Online ที่ทีมสามารถเข้าถึง  

1. เลือก**ขั้นตอนใหม่** แล้วเลือก**เพิ่มการดำเนินการ**  ค้นหา **SharePoint** และเลือกการดำเนินการ **SharePoint – สร้างไฟล์**การดำเนินการ 
   
    ![](./media/learning-create-pdf/sharepoint-create-file.png)
2. ในการดำเนินการ**สร้างไฟล์** ตั้งค่าต่อไปนี้:
   
   * **ที่อยู่ไซต์**: URL ของไซต์ SharePoint ของคุณ  
   * **พาธของโฟลเดอร์**: เลือกไอคอนโฟลเดอร์ แล้วนำทางไปยังโฟลเดอร์ **PDF - Finished files**
   * **ชื่อไฟล์**: จากรายการเนื้อหาแบบไดนามิกสำหรับ**แปลงเอกสาร** เลือก**ชื่อหลักของไฟล์**แล้ว เพิ่ม "**.pdf**" เพื่อจะได้ถูกบันทึกใน SharePoint พร้อมกับนามสกุลไฟล์ 
   * **เนื้อหาไฟล์**: จากรายการเนื้อหาแบบไดนามิกสำหรับ**แปลงเอกสาร** เลือก**เนื้อหาไฟล์ที่ประมวลผลแล้ว**
3. เลือก**สร้างโฟลว์**ที่ด้านบนของหน้าเพื่อบันทึกงานของคุณ
   
    ![](./media/learning-create-pdf/sharepoint-configure-file.png)

## <a name="test-the-flow"></a>ทดสอบโฟลว์
1. เพื่อทดสอบโฟลว์ เพิ่มไฟล์ใหม่ลงในโฟลเดอร์ **Finished Documents** ใน OneDrive for Business 
2. ใน Flow เลือก**โฟลว์ของฉัน** แล้วเลือกโฟลว์ใหม่เพื่อดูประวัติการเรียกใช้ ตามค่าเริ่มต้น มีการกำหนดค่าโฟลว์เพื่อเรียกใช้ทุก ๆ ห้านาที 
3. หลังจากที่โฟลว์ทำงาน ตรวจสอบว่า ไฟล์ถูกแปลงเป็น PDF และบันทึกไปยัง SharePoint โฟลเดอร์ **PDF – Finished files** 
   
    ![](./media/learning-create-pdf/test-the-flow.png)

