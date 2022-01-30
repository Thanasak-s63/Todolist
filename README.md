# Commit 1 : Create server.js

สร้างไฟล์ server.js เพื่อใช้จัดการกับส่วน backend โดยใช้ express.js เพื่อใช้งาน middleware โดยสร้าง app เป็นตัวแปร instance ของ express ซึ่งสามารถเรียกใช้ use ในการเรียกใช้ middleware อื่น , get ในการรับ get request ของ url ที่เรากำหนดโดย ตัวฟังก์ชั่นที่ใช้ใน get ก็เป็น middleware เรียกว่า middleware function โดยสามารถจัดการ response และ request ได้ , listen ใช้ในการรับการเชื่อมต่อใน port นั้นๆ

# Commit 2 : Create database config file

สร้าง folder app สำหรับรวมระบบ backend ทั้งหมดโดยในทีนี้เราสร้าง folder config ก่อนสำหรับเก็บข้อมูลการตั้งค่าสำหรับเชื่อม database และสร้างไฟล์ db.config.js ข้างในนั้น ข้างในไฟล์ได้ทำการสร้างตัวแปรสำหรับเก็บค่าต่างๆไม่ว่าจะเป็น host, user, password, ชื่อ database, ตัว database ที่ใช้, และ pool (ที่เป็น option เสริมสำหรับการทำงานของ database)