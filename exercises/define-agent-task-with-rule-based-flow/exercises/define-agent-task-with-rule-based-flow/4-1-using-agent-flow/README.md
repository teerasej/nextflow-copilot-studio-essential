
# Claim Expense 4: การสร้าง Agent Flow เพื่อเชื่อมต่อความสามารถของ Agent

ดาวน์โหลดไฟล์ตัวอย่าง Claim log.xlsx ได้จากลิงก์นี้: [Claim log.xlsx](../../../../../files/Claim%20log.xlsx)

#### 1. ใน Copilot Studio กดเปิดเมนูด้านบนซ้าย เพื่อแสดงรายชื่อ App ใน Microsoft 365<br>
![Image](Snagit_Step_Image001.png)<br>
#### 2. กดเลือก OneDrive<br>
![Image](Snagit_Step_Image002.png)<br>
#### 3. กดปุ่ม Create or upload<br>
![Image](Snagit_Step_Image003.png)<br>
#### 4. เลือก Files upload และเลือกไฟล์ Claim Log.xslx<br>
ดาวน์โหลดไฟล์ตัวอย่าง Claim log.xlsx ได้จากลิงก์นี้: [Claim log.xlsx](../../../../../files/Claim%20log.xlsx)
![Image](Snagit_Step_Image004.png)<br>
#### 5. จากเมนูด้านซ้าย คลิกเลือก My files เพื่อเช็คว่า มีไฟล์อยู่ใน OneDrive ของเรา<br>
![Image](Snagit_Step_Image005.png)<br>
#### 6. คลิกเปิดไฟล์​ Claim log.xlsx เพื่อเช็คว่ามี table อยู่ในไฟล์<br>
![Image](Snagit_Step_Image006.png)<br>
#### 7. คลิก tab เพื่อกลับมาที่ Copilot Studio<br>
![Image](Snagit_Step_Image007.png)<br>
#### 8. คลิกปุ่ม + ด้านล่าง condition node “Yes” (ด้านบนของ Tool Node)<br>
![Image](Snagit_Step_Image008.png)<br>
#### 9. เลือก Add a tool \> New Agent flow<br>
![Image](Snagit_Step_Image009.png)<br>
#### 10. Copilot Studio จะออกจาก Topic Designer ให้แน่ใจว่าได้กด Save การแก้ไขใดๆ ไว้แล้ว<br>
![Image](Snagit_Step_Image010.png)<br>
#### 11. เราจะมาส่วน Agent flow Designer, ในหน้าต่าง Add trigger เลือก “When an agent call the flow”<br>
![Image](Snagit_Step_Image011.png)<br>
#### 12. จาก Trigger node คลิกเลือก  "Add an input"<br>
![Image](Snagit_Step_Image012.png)<br>
#### 13. เลือกประเภทของ input เป็น Text \(ข้อความ\)<br>
![Image](Snagit_Step_Image013.png)<br>
#### 14. คลิกในช่องด้านซ้ายที่มีข้อความ Text เพื่อตั้งชื่อตัวแปร input ของ trigger ให้ตั้งชื่อว่า claim detail<br>
```
claim detail
```
![Image](Snagit_Step_Image014.png)<br>
#### 15. ด้านขวาที่มีข้อความว่า "Please enter your input" ไม่ต้องแก้ไขอะไร<br>
![Image](Snagit_Step_Image015.png)<br>
#### 16. คลิกที่ปุ่ม + ด้านล่างของ Trigger เพื่อเพิ่ม node ใหม่<br>
![Image](Snagit_Step_Image016.png)<br>
#### 17. ในช่อง Search node ให้ค้นหา node ที่เกี่ยวกับ Excel <br>
```
excel
```
![Image](Snagit_Step_Image017.png)<br>
#### 18. เลือก Add a row into a table<br>
![Image](Snagit_Step_Image018.png)<br>
#### 19. หลังจากสร้าง node แล้ว ให้คลิกกรอกข้อมูล เริ่มจาก ช่อง Location<br>
![Image](Snagit_Step_Image019.png)<br>
#### 20. เลือก OneDrive for Business<br>
![Image](Snagit_Step_Image020.png)<br>
#### 21. ถัดมาเลือก Document Library \> OneDrive<br>
![Image](Snagit_Step_Image021.png)<br>
#### 22. ในส่วนของ File ให้กดปุ่ม browse และเลือกไฟล์ที่เราอัพโหลดไว้<br>
![Image](Snagit_Step_Image022.png)<br>
#### 23. ในส่วนของ Table ให้เลือก table claim\_log<br>
![Image](Snagit_Step_Image023.png)<br>
#### 24. คลิกเลือกรายการในส่วน Advanced Parameters เพื่อเลือกใส่ข้อมูลลงไปใน Table<br>
![Image](Snagit_Step_Image024.png)<br>
#### 25. ให้เลือก “timestamp” และ “claim message” ซึ่งเป็น column ใน table<br>
![Image](Snagit_Step_Image025.png)<br>
#### 26. กดคลิกเลือกช่อง claim message<br>
![Image](Snagit_Step_Image026.png)<br>
#### 27. คลิกเลือกปุ่มสายฟ้า เพื่อใส่ dynamic content \(variable\)<br>
![Image](Snagit_Step_Image027.png)<br>
#### 28. จากรายการให้เลือกชื่อ claim detail ของ trigger “When an agent calls the flow”<br>
![Image](Snagit_Step_Image028.png)<br>
#### 29. ด้านบนของ node “Add a row into a table” ให้กดสร้าง node เพิ่ม<br>
![Image](Snagit_Step_Image029.png)<br>
#### 30. ค้นหา compose data operation<br>
![Image](Snagit_Step_Image030.png)<br>
#### 31. คลิกลงไปในช่อง input ของ compose node<br>
![Image](Snagit_Step_Image031.png)<br>
#### 32. คลิกไอคอน fx ด้านขวาของช่อง input<br>
![Image](Snagit_Step_Image032.png)<br>
#### 33. คัดลอก formula ที่เตรียมไว้ด้านล่างไปวางในช่องที่ปรากฎขึ้นมา และกดปุ่ม Add<br>
```
convertTimeZone(utcNow(),'UTC','SE Asia Standard Time','yyyy-MM-dd HH:mm:ss')
```
![Image](Snagit_Step_Image033.png)<br>
#### 34. หลังจากใส่ formula แล้ว ให้กดเปิด \(...\) ด้านบนขวาของ compose node<br>
![Image](Snagit_Step_Image034.png)<br>
#### 35. เลือกคำสั่ง rename<br>
![Image](Snagit_Step_Image035.png)<br>
#### 36. ตั้งชื่อใหม่ว่า “Create timestamp”<br>
![Image](Snagit_Step_Image036.png)<br>
#### 37. กลับลงมาใน Add new row to table ให้เลือกใส่ค่า dynamic value ให้ช่อง timestamp<br>
![Image](Snagit_Step_Image037.png)<br>
#### 38. เลือกค่า output ของ Create timestamp node<br>
![Image](Snagit_Step_Image038.png)<br>
#### 39. เช็คว่าค่า timestamp และ claim message ได้ถูกกำหนดโดยค่าตัวแปรแล้ว จากนั้นกดเพิ่ม node ใหม่<br>
![Image](Snagit_Step_Image039.png)<br>
#### 40. ค้นหา และเพิ่ม “Respond to the agent"<br>
![Image](Snagit_Step_Image040.png)<br>
#### 41. กดเพิ่ม Add an output เพื่อกำหนดส่งค่าจาก Agent flow กลับไปที่ topic ที่เรียกใช้<br>
![Image](Snagit_Step_Image041.png)<br>
#### 42. เลือกประเภท output เป็น text<br>
![Image](Snagit_Step_Image042.png)<br>
#### 43. กำหนดชื่อ output เป็น **result text** และใส่ค่าเป็น “claim logged”<br>
```
result text
```
```
claim logged
```
![Image](Snagit_Step_Image043.png)<br>
#### 44. กดปุ่ม Save draft เพื่อบันทึกการทำงาน<br>
![Image](Snagit_Step_Image044.png)<br>
#### 45. จากเมนูของ Agent flow ด้านบน ให้คลิกเปิด Overview<br>
![Image](Snagit_Step_Image045.png)<br>
#### 46. กดปุ่ม Edit เพื่อแก้ไขและตั้งชื่อ Agent flow นี้ใหม่<br>
![Image](Snagit_Step_Image046.png)<br>
#### 47. คลิกช่อง flow name และตั้งชื่อ **[ชื่อเรา] Log claim to excel file**<br>
```
[ชื่อเรา] Log claim to excel file
```
![Image](Snagit_Step_Image047.png)<br>
#### 48. กดปุ่ม  "Save" เพื่อยืนยันการตั้งชื่อ<br>
![Image](Snagit_Step_Image048.png)<br>
#### 49. จากเมนูของ Agent flow กดกลับไปที่ "Designer"<br>
![Image](Snagit_Step_Image049.png)<br>
#### 50. กดปุ่ม "Publish” เพื่อนำ Agent flow นี้ไปใช้งาน<br>
![Image](Snagit_Step_Image050.png)<br>
#### 51. กดปุ่ม  "Test" เพื่อเริ่มการทดสอบ Agent flow<br>
![Image](Snagit_Step_Image051.png)<br>
#### 52. เลือก Manually เพื่อเริ่มการทำงานโดยตัวเรา<br>
![Image](Snagit_Step_Image052.png)<br>
#### 53. ลงมาด้านล่างและกดปุ่ม "Test"<br>
![Image](Snagit_Step_Image053.png)<br>
#### 54. ใส่รายละเอียด claim detail เป็น "travel 10 USD"<br>
```
travel 10 USD
```
![Image](Snagit_Step_Image054.png)<br>
#### 55. กดปุ่ม "Run flow" เพื่อเริ่มการทำงาน<br>
![Image](Snagit_Step_Image055.png)<br>
#### 56. กดปุ่ม Done<br>
![Image](Snagit_Step_Image056.png)<br>
#### 57. จากหน้าเว็บ คลิกเปิด tab ที่เราเปิด Excel  ทิ้งไว้ เพื่อดูผลการทำงาน<br>
![Image](Snagit_Step_Image057.png)<br>
#### 58. จะเห็นว่ามีข้อความแสดงขึ้นมา<br>
![Image](Snagit_Step_Image058.png)<br>
#### 59. เรายังสามารถกดดู Activity ของ Agent Flow เพื่อเช็คการทำงานของ node ต่างๆ ได้<br>
![Image](Snagit_Step_Image059.png)<br>
#### 60. กดกลับไปที่ Expense Agent<br>
![Image](Snagit_Step_Image060.png)<br>
#### 61. กลับไปที่ Topics และเลือกทำ Topic ของเราต่อ<br>
![Image](Snagit_Step_Image061.png)<br>
#### 62. กลับมาตรงจุดที่เราพยายามสร้าง Agent flow node อีกครั้ง<br>
![Image](Snagit_Step_Image062.png)<br>
#### 63. เลือก Add a tool \> \[ชื่อ\] Log claim to excel file<br>
![Image](Snagit_Step_Image063.png)<br>
#### 64. เราจะได้ action node \(Agent flow\) มา ซึ่งเราจะกดกำหนดตัวแปรให้กับ claim detail<br>
![Image](Snagit_Step_Image064.png)<br>
#### 65. เลือก PolicyClaimDetail<br>
![Image](Snagit_Step_Image065.png)<br>
#### 66. เปลี่ยนชื่อ node เป็น “Log claim to excel”<br>
```
Log claim to excel
```
![Image](Snagit_Step_Image066.png)<br>
#### 67. กดปุ่ม Save และทดสอบการใช้งาน<br>
![Image](Snagit_Step_Image067.png)<br>