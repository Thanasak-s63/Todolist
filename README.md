# Commit 1 : Create server.js

สร้างไฟล์ server.js เพื่อใช้จัดการกับส่วน backend โดยใช้ express.js เพื่อใช้งาน middleware โดยสร้าง app เป็นตัวแปร instance ของ express ซึ่งสามารถเรียกใช้ use ในการเรียกใช้ middleware อื่น , get ในการรับ get request ของ url ที่เรากำหนดโดย ตัวฟังก์ชั่นที่ใช้ใน get ก็เป็น middleware เรียกว่า middleware function โดยสามารถจัดการ response และ request ได้ , listen ใช้ในการรับการเชื่อมต่อใน port นั้นๆ

# Commit 2 : Create database config file

สร้าง folder app สำหรับรวมระบบ backend ทั้งหมดโดยในทีนี้เราสร้าง folder config ก่อนสำหรับเก็บข้อมูลการตั้งค่าสำหรับเชื่อม database และสร้างไฟล์ db.config.js ข้างในนั้น ข้างในไฟล์ได้ทำการสร้างตัวแปรสำหรับเก็บค่าต่างๆไม่ว่าจะเป็น host, user, password, ชื่อ database, ตัว database ที่ใช้, และ pool (ที่เป็น option เสริมสำหรับการทำงานของ database)

# Commit 3 : Create models for database

ทำการดึงตัว db.config.js ที่เราได้สร้างไว้มาใช้งาน และมีการเรียกใช้งาน sequelize.js เพื่อใช้เชื่อมกับ database โดยใช้การตั้งค่าจาก config file ที่เรียกมาใช้และมีการเรียกใช้ model ที่เราสร้างไว้ที่ชื่อ "todo.model.js" โดยข้างในไฟล์ได้มีการประกาศโครงสร้างข้อมูลว่าแต่ละ column มีชื่ออะไรและรับค่าชนิดอะไรบ้าง โดยใช้คำสั่ง define ตั้งชื่อ model ว่า todo เมื่อเราทำการ run ในส่วนนี้ โปรแกรมจะไปสร้าง table ใน database โดยใช้ชื่อว่า todos ซึ่งมี s เพิ่มมา

# Commit 4 : Create controllers and edit published to finished

ทำการสร้าง folder controllers และ todo.controller.js เพื่อจัดการเป็นตัวกลางระหว่าง model กับส่วนของ view(ในที่นี้คือส่วนของ react) โดยข้างในก็จะมีการ export function การทำงานต่างๆโดยที่มีการรับค่า response กับ request นั่นคือเป็น function ที่ทำงานเป็น milddleware เช่น create ทำหน้าที่เพิ่มข้อมูลลง database, findAll ทำหน้าที่ค้นหาทั้งหมดใน database แบบมีเงื่อนไข, findOne ทำหน้าที่หาข้อมูลใน database โดยใช้ id, update ทำหน้าที่ update ข้อมูลใน database โดยแก้ตาม id, delete ทำหน้าที่ลบข้อมูลใน database โดยลบตาม id, deleteAll ทำหน้าที่ลบข้อมูลทั้งหมดใน database, findAllFinished ทำหน้าที่ค้นหาข้อมูลโดยเลือกเฉพาะที่ attribute finished เป็น true

แก้ไขทุกจุดที่มีการใช้คำว่า published เป็น finished โดยมีในที่ todo.model.js และ todo.controller.js
