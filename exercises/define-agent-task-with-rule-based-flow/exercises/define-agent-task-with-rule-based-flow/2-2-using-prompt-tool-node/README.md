# Claim Expense 2: adding Prompt Tool Node

## สรุป

แบบฝึกหัดนี้จะสาธิตวิธีการใช้ **Prompt Tool Node** ใน Copilot Studio เพื่อใช้ประโยชน์จาก AI model ในการประมวลผลและสร้างเนื้อหาแบบไดนามิก Prompt Tool Node ช่วยให้คุณสามารถ:

- ส่งคำสั่งที่มีโครงสร้าง (prompts) ไปยัง AI model
- ส่งข้อมูลจากตัวแปรเข้าไปเป็น input เพื่อปรับแต่งงานของ AI
- รับผลลัพธ์ที่ AI สร้างขึ้นและเก็บไว้ในตัวแปร
- ผสานการสร้างเนื้อหาด้วย AI เข้ากับ topic flow ได้อย่างลงตัว

ในแบบฝึกหัดนี้ คุณจะสร้าง Prompt Tool Node ที่ร่างอีเมลถึงแผนกการเงินโดยอิงจากรายละเอียดการเบิกค่าใช้จ่าย AI model จะประมวลผลข้อมูลค่าใช้จ่ายและสร้างร่างอีเมลแบบมืออาชีพ ซึ่งจากนั้นจะแสดงให้ผู้ใช้ตรวจสอบ 

วิธีการนี้แสดงให้เห็นถึงการผสมผสานระหว่าง rule-based flow กับความสามารถของ generative AI เพื่อสร้างการตอบสนองของ agent ที่ชาญฉลาดและตระหนักถึงบริบท

---

#### 1. จาก Topic ของเรา กดปุ่ม + เพื่อเพิ่ม node ใหม่<br>
![Image](Snagit_Step_Image001.png)<br>
#### 2. จากรายการ เลือก Add a tool \> New prompt<br>
![Image](Snagit_Step_Image002.png)<br>
#### 3. หลังจากหน้าต่าง prompt เปิดขึ้นมา ให้แก้ไขชื่อเป็น **[ชื่อเรา] Drafting Email**<br>
```
[ชื่อเรา] Drafting Email
```
![Image](Snagit_Step_Image003.png)<br>
#### 4. คลิกลงไปในช่อง instruction > get started with copilot และใส่ข้อความว่า "Draft a short email to finance department to claim expense from given expense's detail”<br>
```
Draft a short email to finance department to claim expense from given expense's detail
```
![Image](Snagit_Step_Image004.png)<br>
#### 5. กดปุ่มส่ง เพื่อให้ Copilot ทำการร่าง prompt ที่ใช้ในการทำงานกับข้อมูลที่ถูกส่งเข้ามาที่ node นี้<br>
![Image](Snagit_Step_Image005.png)<br>
#### 6. ตรวจสอบข้อความ prompt และแก้ไขถ้าต้องการ เสร็จแล้วกดปุ่ม  "Keep it"<br>
![Image](Snagit_Step_Image006.png)<br>
#### 7. จากตัวอย่าง prompt ควรจะมี input ถูกสร้างขึ้นมาตัวหนึ่ง (นี่คือจุดที่เราสามารถแทรกค่าตัวแปร เข้ามาใน prompt ก่อนที่ node จะส่งไปให้ model ประมวลผลได้) ให้คลิกที่ชื่อ input <br>
![Image](Snagit_Step_Image007.png)<br>
#### 8. จากหน้าต่างที่เปิดขึ้นมา ให้เราใส่ข้อความ “เบิกค่าเที่ยวดูงานญี่ปุ่น 100 USD” และกดปุ่ม close<br>
```
เบิกค่าเที่ยวดูงานญี่ปุ่น 100 USD
```
![Image](Snagit_Step_Image008.png)<br>
#### 9. กดปุ่ม Test เพื่อทดสอบส่ง prompt พร้อมข้อมูล input ไปให้ model ประมวลผล<br>
![Image](Snagit_Step_Image009.png)<br>
#### 10. ตรวจสอบผลลัพธ์การทำงาน<br>
![Image](Snagit_Step_Image010.png)<br>
#### 11. กดปุ่ม Save เพื่อบันทึกการตั้งค่าของ prompt node<br>
![Image](Snagit_Step_Image011.png)<br>
#### 12. การมาที่หน้า Topic Designer ให้คลิกกล่องในส่วน input ด้านบนของ node เพื่อเลือกค่าตัวแปร มากำหนดใช้ใน Prompt node<br>
![Image](Snagit_Step_Image012.png)<br>
#### 13. จากรายการ เลือกตัวแปร PolicyClaimDetail <br>
![Image](Snagit_Step_Image013.png)<br>
#### 14. และเช็คให้แน่ใจว่าตัวแปรได้ไปอยู่ในช่อง input แล้ว<br>
![Image](Snagit_Step_Image014.png)<br>
#### 15. สำหรับผลลัพธ์การทำงานของ Prompt node นี้ เราจะสร้างตัวแปรใหม่มาเก็บ เริ่มจากการคลิกช่อง output ด้านล่างของ node<br>
![Image](Snagit_Step_Image015.png)<br>
#### 16. จากหน้าต่าง เลือก Custom \> Create a new variable<br>
![Image](Snagit_Step_Image016.png)<br>
#### 17. ตัวแปรจะถูกสร้างขึ้น และตั้งชื่อ Var ชั่วคราว ให้ทำการคลิกที่ตัวแปรในช่อง output เพื่อ เปิดหน้าต่างการตั้งค่าตัวแปร<br>
![Image](Snagit_Step_Image017.png)<br>
#### 18. คลิกในช่อง Variable Name และตั้งชื่อตัวแปรใหม่ว่า “draft\_claim\_email” และกด enter<br>
```
draft_claim_email
```
![Image](Snagit_Step_Image018.png)<br>
#### 19. คลิกที่ชื่อ prompt node และเปลี่ยนชื่อเป็น “Drafting Email”<br>
```
Drafting Email
```
![Image](Snagit_Step_Image019.png)<br>
#### 20. ถัดมา เราจะสร้าง Send message node เพื่อแสดงข้อความที่ได้จาก Prompt node ให้คลิกปุ่ม + ด้านล่างสุดของ topic<br>
![Image](Snagit_Step_Image020.png)<br>
#### 21. จากหน้าต่าง ให้เลือก "Send a message"<br>
![Image](Snagit_Step_Image021.png)<br>
#### 22. คลิกเปลี่ยนชื่อ node เป็น “Draft Email Summary”<br>
```
Draft Email Summary
```
![Image](Snagit_Step_Image022.png)<br>
#### 23. คลิกลงไปในช่อง Enter a message และกรอกข้อความด้านล่าง<br>
```
We are going to send the following email to finance department, please review:
```
![Image](Snagit_Step_Image023.png)<br>
#### 24. กดปุ่ม Insert variable {x} เพื่อเลือกตัวแปรที่ได้จาก Prompt node มาแสดง<br>
![Image](Snagit_Step_Image024.png)<br>
#### 25. จากรายการให้เลือก `draft_claim_email.text` 
> สังเกตว่าเราไม่ได้เลือกแค่ draft_claim_email เพราะตัวแปรแบบ record จะเก็บข้อมูลได้มากกว่า 1 ตัว ซึ่งในที่นี้เราต้องการ text ที่เป็นข้อความผลลัพธ์จาก prompt node มาใช้

![Image](Snagit_Step_Image025.png)<br>
#### 26. คลิกปุ่ม Save และทดสอบการทำงาน<br>
![Image](Snagit_Step_Image026.png)<br>

## การทำงานที่คาดไว้

เมื่อผู้ใช้มาถึงจุดนี้ใน Topic flow 
- จะมีการถามให้แจ้งรายละเอียดในการเคลม
- ระบบจะนำรายละเอียดที่ได้รับมาไปสร้างร่างอีเมลโดยใช้ Prompt tool node
- ระบบจะแสดงข้อความสรุปอีเมลที่ร่างขึ้นมาให้ผู้ใช้ตรวจสอบก่อนส่งจริง 
