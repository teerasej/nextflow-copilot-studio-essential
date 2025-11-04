
# Claim Expense 3: การเพิ่ม tools เพื่อส่งอีเมลล์จริง

แบบฝึกหัดนี้จะสาธิตวิธีการเพิ่ม **Send Email Tool** ใน Copilot Studio เพื่อให้ AI Agent สามารถส่งอีเมลล์จริงไปยังแผนกการเงินได้หลังจากที่ร่างอีเมลล์เสร็จสิ้น

#### 1. จาก condition node ที่มีการเทียบค่าตัวแปร confirm_send_email เป็น Yes ให้กดสร้าง node ใหม่<br>
![Image](Snagit_Step_Image001.png)<br>
#### 2. เลือก Add a tool > Tool <br>
![Image](Snagit_Step_Image002.png)<br>
#### 3. เลือกรายการ Add a tool<br>
![Image](Snagit_Step_Image003.png)<br>
#### 4. จากรายการ tool ให้เลือก Office 365 Outlook Connector<br>
![Image](Snagit_Step_Image004.png)<br>
#### 5. เลือก "Send an email (V2)"<br>
![Image](Snagit_Step_Image005.png)<br>
#### 6. จะมีการแสดง tools และการตั้งค่าที่มีอยู่ก่อนแล้ว ถ้ามีการตังค่า connector อยู่แล้วจะมีรายการให้เลือก<br>
![Image](Snagit_Step_Image006.png)<br>
#### 7. แต่ถ้าต้องการให้สร้าง connector ใหม่ก็สามารถกดเลือกรายการ connection เพื่อเลือก Creative new connection<br>
![Image](Snagit_Step_Image007.png)<br>
#### 8. กดปุ่ม Create เพื่อสร้าง connection ใหม่ให้กับ Office 365 Outlook เพื่อ log in <br>
![Image](Snagit_Step_Image008.png)<br>
#### 9. ทำการ login ด้วย account ที่ใช้ในการเข้าใช้งาน Copilot Studio<br>
![Image](Snagit_Step_Image009.png)<br>
#### 10. ให้สังเกตว่า Connection ใหม่จะแสดงขึ้นมาในตัวเลือกปัจจุบัน ให้กดปุ่ม Add and configure<br>
![Image](Snagit_Step_Image010.png)<br>
#### 11. ตรงนี้จะเป็นการออกจาก Topic Designer ให้เราแน่ใจว่า Save topic แล้ว ก่อนกด Leave<br>
![Image](Snagit_Step_Image011.png)<br>
#### 12. จะสังเกตว่าเราอยู่ในส่วน tool ของ Agent และเรากำลังตั้งค่า tool ใหม่ที่สร้างขึ้นมานี้<br>
![Image](Snagit_Step_Image012.png)<br>
#### 13. เปลี่ยนชื่อ tool เป็น “Send an email to [ชื่อเรา]"<br>
![Image](Snagit_Step_Image013.png)<br>
#### 14. ในส่วนของ Inputs ด้านล่าง ให้เลือกค่า To: เป็น custom value<br>
![Image](Snagit_Step_Image014.png)<br>
#### 15. กรอกอีเมลล์ทดสอบลงไป ในที่นี้ให้ใช้เป็น email เดียวกันกับที่ใช้ใน Copilot Studio<br>
![Image](Snagit_Step_Image015.png)<br>
#### 16. เลือกลงมาด้านล่างในส่วน completion ให้เลือก after running เป็น send specific response<br>
![Image](Snagit_Step_Image016.png)<br>
#### 17. ใส่ข้อความว่า “Email sent. 🎉” <br>
```
Email sent. 🎉
```
![Image](Snagit_Step_Image017.png)<br>
#### 18. กดปุ่ม Save เพื่อบันทึกการตั้งค่า tool นี้<br>
![Image](Snagit_Step_Image018.png)<br>
#### 19. กดปุ่ม Back ด้านซ้ายของชื่อ tool ปัจจุบัน เพื่อกลับไปหน้า tools ของ Agent<br>
![Image](Snagit_Step_Image019.png)<br>
#### 20. จะเห็นว่ามี tool ที่เราสร้าง เพิ่มมาใน Agent tool ถือว่าสำเร็จ สามารถเลือกไปใช้งานได้<br>
![Image](Snagit_Step_Image020.png)<br>
#### 21. จากเมนูด้านบน กดกลับไปที่ Topics<br>
![Image](Snagit_Step_Image021.png)<br>
#### 22. กดเปิด Topic Claim Expense 3 ที่ทำค้างไว้ก่อนหน้านี้<br>
![Image](Snagit_Step_Image022.png)<br>
#### 23. จาก condition node ที่มีการเทียบค่าตัวแปร confirm_send_email เป็น Yes ให้กดสร้าง node ใหม่ (ก่อนหน้านี้เรากดแล้ว แต่สลับไปสร้างและตั้งค่า tool ให้ agent ก่อน<br>
![Image](Snagit_Step_Image023.png)<br>
#### 24. เลือก Add a tool > Tool > เลือก Send an Email to [ชื่อ Email]<br>
![Image](Snagit_Step_Image024.png)<br>
#### 25. จะเป็นการเพิ่ม tool node ลงไป เราสามารถกำหนดค่าลงไปใน tool จาก topic ได้ จากการกด Set value<br>
![Image](Snagit_Step_Image025.png)<br>
#### 26. จากรายชื่อ input ของ tool ให้เลือก body (สังเกตว่าในนี้ไม่มี To: เพราะเรากำหนดใน tool ไปแล้ว)<br>
![Image](Snagit_Step_Image026.png)<br>
#### 27. คลิกในช่อง input > body <br>
![Image](Snagit_Step_Image027.png)<br>
#### 28. เลือก draft_claim_email.text จากรายการตัวแปร<br>
![Image](Snagit_Step_Image028.png)<br>
#### 29. ตรวจให้แน่ใจว่าตัวแปรได้ถูกกำหนดลงไปใน Input > body แล้ว<br>
![Image](Snagit_Step_Image029.png)<br>
#### 30. กดปุ่ม Save และทดสอบการทำงาน<br>
![Image](Snagit_Step_Image030.png)<br>


### Final. ทำการกำหนดชื่อให้ node ในกลุ่ม condition เป็นตามภาพด้านล่างนี้<br>

#### 1. ชื่อ node สำหรับกรณีที่ผู้ใช้ตอบ Yes<br>
```
User confirm draft email
```
#### 2. ชื่อ node สำหรับกรณีที่ผู้ใช้ตอบ No<br>
```
User reject draft email
```
#### 3. ชื่อ tool node สำหรับส่งอีเมลล์<br>
```
Send an email to [ชื่อเรา]
```
#### 4. ชื่อ Send a message node ยืนยันการยกเลิกการเคลม<br>
```
Claim expense cancelled
```
![alt text](image-1.png)
#### 5. กดปุ่ม Save เพื่อบันทึกการตั้งค่าทั้งหมดของ Topic นี้<br>


## การทำงานที่คาดไว้

เมื่อผู้ใช้มาถึงจุดนี้ใน Topic flow 
- จะมีการถามให้แจ้งรายละเอียดในการเคลม
- ระบบจะนำรายละเอียดที่ได้รับมาไปสร้างร่างอีเมลโดยใช้ Prompt tool node
- ระบบจะแสดงข้อความสรุปอีเมลที่ร่างขึ้นมาให้ผู้ใช้ตรวจสอบก่อนส่งจริง 
- จากนั้นจะถามยืนยันว่าต้องการส่งอีเมลนี้หรือไม่ หากผู้ใช้ตอบว่า "Yes" ระบบจะไปเรียกใช้ Send Email tool ที่เราเพิ่มเข้าไป เพื่อนำข้อความที่ได้จาก Prompt node ส่งเป็นอีเมลล์จริงไปยัง email ที่มีการกำหนดไว้
- ระบบจะแจ้งว่าส่งอีเมลเรียบร้อยแล้ว แต่ถ้าผู้ใช้ตอบว่า "No" ระบบจะยกเลิกการเคลมและรอคำสั่งใหม่จากผู้ใช้

> NOTE: หากต้องการทดสอบการส่งอีเมลล์จริง ให้ตรวจสอบกล่องจดหมายของ email ที่ใช้ในการตั้งค่า Office 365 Outlook Connector ว่ามีอีเมลล์เข้ามาหรือไม่ 
> ถ้าไม่มีอีเมลล์เข้ามา ให้ตรวจสอบการตั้งค่า connection ว่าสามารถเชื่อมต่อกับ Office 365 ได้ถูกต้องหรือไม่ และบัญชีที่ไม่มีการเปิดใช้งาน Outlook จะไม่เกิดการส่งอีเมลล์