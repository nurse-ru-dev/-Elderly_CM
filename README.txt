วิธีใช้งานชุดไฟล์ Dashboard เชื่อม Backend

ไฟล์ในชุดนี้
1) Code.gs
   - ใช้เป็น Backend Google Apps Script
   - ดึงข้อมูลจาก Google Sheet:
     https://docs.google.com/spreadsheets/d/1XQLK7zzi1iEzCMEAW8eVUV9hI2kb5P-4CRqigy1hWXg/edit?gid=1824119399

2) index.html
   - ใช้เป็น Frontend Dashboard
   - เหมาะสำหรับ Firebase Hosting / GitHub Pages / เปิดทดสอบในเครื่อง

ขั้นตอนติดตั้ง Backend
1) เข้า https://script.google.com
2) สร้าง Apps Script Project ใหม่
3) วาง Code.gs ทับไฟล์เดิม
4) กด Deploy > New deployment
5) เลือก Type = Web app
6) Execute as = Me
7) Who has access = Anyone
8) กด Deploy
9) Copy URL ที่ลงท้าย /exec

ขั้นตอนเชื่อม Frontend
1) เปิด index.html
2) หาบรรทัด:
   const API_URL = "PUT_YOUR_APPS_SCRIPT_WEB_APP_EXEC_URL_HERE";
3) แทนด้วย URL /exec ของ Apps Script
4) นำ index.html ไปวางใน Firebase Hosting ได้ทันที

หมายเหตุ
- ถ้าเว็บขึ้น Need API URL แปลว่ายังไม่ได้ใส่ URL backend
- ถ้าเว็บขึ้น Error ให้ตรวจว่า Apps Script Deploy เป็น Anyone แล้ว
- ถ้าหัวคอลัมน์ในชีตเปลี่ยนมาก อาจต้องเพิ่มชื่อหัวตารางใน field aliases ฝั่ง Code.gs
