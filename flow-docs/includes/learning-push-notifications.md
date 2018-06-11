สำหรับโฟลว์นี้ คุณจะได้สร้างรายการ **SharePoint** ที่ทีมการตลาดสำหรับ **Contoso Flooring** จัดเก็บ **โพสต์ Twitter** และวันที่โพสต์ จากที่นั่น คุณจะได้สร้างโฟลว์ที่จะทวีตเนื้อหาโดยอัตโนมัติ 

## <a name="connect-microsoft-flow-services"></a>เชื่อมต่อบริการ Microsoft Flow
ในหัวข้อนี้ คุณจะได้ใช้ **SharePoint** และบริการ **Twitter** ถ้าคุณกำลังใช้บริการที่ไม่เคยใช้มาก่อน ก่อนอื่น คุณต้องเชื่อมต่อกับบริการใหม่ 

1. ใน Microsoft Flow ให้เลือก**ไอคอนรูปเฟือง** แล้วเลือก **การเชื่อมต่อ**
   
    ![รับการเชื่อมต่อ](./media/learning-push-notifications/2-get-connection.png) 
2. เลือก **+ สร้างเฉพาะการเชื่อมต่อเท่านั้น**
   
    ![สร้างการเชื่อมต่อ](./media/learning-push-notifications/3-create-connection.png) 
3. เลื่อนดูรายการ ค้นหา Twitter แล้วเลือก **+**
   
    ![คลิกเครื่องหมายบวก](./media/learning-push-notifications/4-click-plus.png)
4. เมื่อต้องการอนุญาตบัญชี Twitter ให้ป้อนชื่อผู้ใช้หรืออีเมล และรหัสผ่านของคุณ แล้วเลือก **อนุญาตแอป**
   
    ![สร้าง ID และรหัสผ่าน](./media/learning-push-notifications/5-create-id-pswd.png)
5. เมื่อต้องการตรวจสอบการเชื่อมต่อ ให้เลือก**ไอคอนรูปเฟือง** แล้วเลือก **การเชื่อมต่อ**
   
    ![การเชื่อมต่อของฉัน](./media/learning-push-notifications/6-my-connections.png)
   
    คุณควรเห็นการเชื่อมต่อ Twitter ใหม่และการเชื่อมต่ออื่นๆ ที่คุณสร้างขึ้น 
   
    ![เชื่อมต่อ Twitter](./media/learning-push-notifications/7-twitter-connection.png)

## <a name="build-a-sharepoint-list"></a>สร้างรายการ SharePoint
สิ่งแรกที่คุณต้องทำคือการสร้างรายการ SharePoint Online ใหม่สำหรับ Contoso Flooring 

1. ใน SharePoint Online ให้เลือก **ใหม่** แล้วเลือก **รายการ**
   
    ![สร้างรายการใหม่](./media/learning-push-notifications/1-new-list.png)
2. ตั้งชื่อรายการว่า **Contoso Tweets** 
3. ล้างกล่องกาเครื่องหมาย **แสดงในการนำทางไซต์** แล้วเลือก **สร้าง**
   
    ![สร้างรายการ](./media/learning-push-notifications/2-name-create-list.png)
   
    เมื่อคุณเลือก **สร้าง** SharePoint จะนำคุณไปยังรายการใหม่
4. ตามค่าเริ่มต้น รายการจะมีคอลัมน์เดียว ซึ่งก็คือ **ชื่อเรื่อง** เพิ่มคอลัมน์และตั้งชื่อว่า **Tweet Contents** สิ่งที่คุณกล่าวในทวีตจะอยู่ที่นี่ 
   
   1. เลือกเครื่องหมายบวก แล้วเลือก **เพิ่มเติม...**
      
       ![สร้างรายการ](./media/learning-push-notifications/3-add-more-column-types.png)
   2. เลือก **ข้อความหลายบรรทัด** แล้วเลือก **ตกลง**
      
       ![สร้างรายการ](./media/learning-push-notifications/4-add-column.png)
5. เพิ่มคอลัมน์สำหรับวันที่และเวลาที่ทวีต แล้วตั้งชื่อว่า **Tweet Date**
   
   1. เหมือนกับ **Tweet Contents** ทางด้านบน ให้เลือกเครื่องหมายบวก แล้วเลือก **เพิ่มเติม...**
      
       ![คอลัมน์วันที่และเวลา](./media/learning-push-notifications/5-date-time-col.png)
   2. เลื่อนลงไปที่ **รูปแบบวันที่และเวลา** เลือก **วันที่และเวลา** เพื่อให้มีทั้งสองอย่าง
      
       ![วันที่และเวลา](./media/learning-push-notifications/6-date-time-must-do.png)
   3. เลือก **ตกลง** คุณจะเห็นรายการ **Contoso Tweets** ในไซต์ SharePoint ของคุณ และคุณสามารถเพิ่มรายการใหม่ไปยังรายการได้

## <a name="build-the-flow"></a>สร้างโฟลว์
รายการของคุณจะถูกสร้างขึ้น ดังนั้น คุณจึงสามารถสร้างโฟลว์ได้

### <a name="choose-a-trigger"></a>เลือกทริกเกอร์
1. ใน Microsoft Flow ให้ไปที่ **โฟลว์ของฉัน** แล้วเลือก **สร้างตั้งแต่ต้น**
   
    ![สร้างตั้งแต่ต้น](./media/learning-push-notifications/8-create-from-blank.png)
2. เลือก **เมื่อสร้างรายการ**
   
    ![เพิ่มทริกเกอร์](./media/learning-push-notifications/9-add-trigger.png)
   
    เราต้องการให้ทริกเกอร์ทำงานเมื่อเพิ่มแถวใหม่ที่มีเนื้อหาทวีต
3. เลือกไซต์ SharePoint ของคุณ แล้วเลือกรายการที่คุณตั้งค่าก่อนหน้านี้ **Contoso Tweets**
   
    ![รายการจะถูกสร้างขึ้น](./media/learning-push-notifications/11-set-trigger.png)

เรียบร้อย ทริกเกอร์พร้อมแล้ว

### <a name="add-an-action-to-delay-posting"></a>เพิ่มการดำเนินการเพื่อหน่วงเวลาการโพสต์
1. เลือก **+ ขั้นตอนใหม่** แล้วเลือก **เพิ่มการดำเนินการ** 
   
    ![เพิ่มขั้นตอนและการดำเนินการ](./media/learning-push-notifications/12-add-step-and-action.png)
2. ภายใต้บริการ **กำหนดการ** ให้เลือก **หน่วงเวลาจนถึง** 
   
    ![หน่วงเวลาจนถึง](./media/learning-push-notifications/13-delay-until-schedule.png)  
3. ตั้งค่าการหน่วงเวลา
   
   1. คลิกหรือแตะในเขตข้อมูล **ประทับเวลา** 
   2. เมื่อกล่องเนื้อหาแบบไดนามิกเปิดขึ้น ให้เลื่อนลงไปยังด้านล่าง และคุณจะเห็นสามคอลัมน์จากรายการ SharePoint: **ชื่อเรื่อง** **Tweet Date** และ **Tweet Content**
   3. เลือก **Tweet Date** 
      
       ![หน่วงเวลาจนถึงประทับเวลา](./media/learning-push-notifications/14-delay-until-timestamp.png)
      
       ในตอนนี้ เมื่อมีบุคคลเพิ่มบางอย่างลงในรายการ SharePoint จะหน่วงเวลาการดำเนินการไว้จนกว่าจะถึงวันที่และเวลาที่คุณตั้งค่าไว้ในคอลัมน์ **Tweet Date**
      
       ![ประทับเวลาแบบไดนามิก](./media/learning-push-notifications/15-dynamic-timestamp.png)

### <a name="add-an-action-to-post-a-tweet"></a>เพิ่มการดำเนินการที่จะโพสต์ทวีต
ในตอนนี้ คุณจะเพิ่มการดำเนินการอื่นสำหรับโฟลว์ที่จะทำงานเมื่อถึงวันที่และเวลาที่ระบุไว้ในคอลัมน์ **Tweet Date**

1. เลือก **+ ขั้นตอนใหม่** **เพิ่มการดำเนินการ** แล้วค้นหา **Twitter**
   
    ![เพิ่มทวีต](./media/learning-push-notifications/16-add-tweet.png) 
2. เลือกการดำเนินการ **Twitter - โพสต์ทวีต**
   
    ![โพสต์ทวีต](./media/learning-push-notifications/17-post-tweet.png) 
3. คลิกหรือแตะในเขตข้อมูล **ข้อความทวีต** และในกล่องเนื้อหาแบบไดนามิก ให้เลือก **Tweet Contents** นี่คือลำดับที่คุณสร้างขึ้น 
   
    ![เนื้อหาวันที่ทวีต](./media/learning-push-notifications/18-tweet-date-content.png)
4. เลือก **สร้างโฟลว์...**
   
    ![สร้างโฟลว์](./media/learning-push-notifications/19-tiny-create.png) 
5. เลือก **เสร็จสิ้น**
   
    ![คลิกเสร็จสิ้น](./media/learning-push-notifications/19-click-done.png)
   
    ขณะนี้ โฟลว์เสร็จสมบูรณ์แล้ว
   
    ![โฟลว์เสร็จเรียบร้อยแล้ว](./media/learning-push-notifications/20-flow-is-done.png)
   
    เมื่อสร้างรายการใหม่ในรายการ SharePoint ของคุณ โฟลว์จะหน่วงเวลาการโพสต์จนถึงวันที่ที่กำหนดไว้ล่วงหน้า เมื่อถึงวันที่ โฟลว์จะโพสต์ข้อความจากคอลัมน์ **Tweet Content** ในรายการของคุณลงใน Twitter

## <a name="next-lesson"></a>บทเรียนถัดไป
ในบทเรียนถัดไป คุณจะได้เรียนรู้วิธีการ**เรียกใช้โฟลว์ตามกำหนดการ**โดยใช้ทริกเกอร์ที่ชื่อว่า **กิจวัตร**

