# Ledger — Personal Finance Dashboard

เว็บแอปจัดการการเงินส่วนบุคคล สร้างด้วย HTML/CSS/JavaScript ล้วน (ไม่มี framework, ไม่มี build step) โชว์ทักษะการจัดการ state ที่ซับซ้อนและการนำเสนอข้อมูลด้วยกราฟ

**Live demo:** _(เติมลิงก์ GitHub Pages ของคุณที่นี่หลัง deploy เช่น `https://<username>.github.io/<repo>/`)_

## ฟีเจอร์

- **Authentication** — สมัครสมาชิก/เข้าสู่ระบบ แยกข้อมูลตามผู้ใช้แต่ละคน
- **CRUD รายรับ-รายจ่าย** — เพิ่ม/แก้ไข/ลบ พร้อมเลือกหมวดหมู่, วันที่, รายละเอียด
- **สรุปยอดแบบ Real-time** — ยอดคงเหลือ, รายรับรวม, รายจ่ายรวม, รายจ่ายวันนี้
- **กราฟ** — Pie chart สัดส่วนรายจ่ายตามหมวดหมู่ และ Bar chart เทียบรายรับ-รายจ่ายรายเดือน (ใช้ [Chart.js](https://www.chartjs.org/))
- **Filter** — กรองตามช่วงวันที่ หมวดหมู่ และประเภทรายการ
- **Smart To-Do List** — เพิ่ม/ลบ/ติ๊กงานที่ทำเสร็จ พร้อมระดับความสำคัญ (สูง/กลาง/ต่ำ)

## เทคโนโลยีที่ใช้

- Vanilla JavaScript (ไม่มี framework)
- Chart.js สำหรับกราฟ
- Google Fonts (Fraunces, Inter)
- Browser `localStorage` สำหรับเก็บข้อมูล (ดูข้อจำกัดด้านล่าง)

## วิธีรันโปรเจกต์

ไม่ต้อง build หรือติดตั้งอะไรเลย เปิดไฟล์ `index.html` ด้วยเบราว์เซอร์ได้ทันที หรือถ้าพัฒนาต่อแนะนำใช้ VS Code + [Live Server extension](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) เพื่อให้มี auto-reload

## Deploy ด้วย GitHub Pages

1. Push โปรเจกต์นี้ขึ้น repo บน GitHub
2. ไปที่ **Settings → Pages** เลือก source เป็น branch `main` (root)
3. จะได้ลิงก์ `https://<username>.github.io/<repo>/` ใช้งานได้ทันที

## ข้อจำกัด (สำคัญสำหรับผู้ใช้งาน)

ข้อมูลทั้งหมดเก็บไว้ใน `localStorage` ของเบราว์เซอร์ผู้ใช้แต่ละคน ซึ่งหมายความว่า:

- ข้อมูลไม่ sync ข้ามอุปกรณ์หรือเบราว์เซอร์
- ถ้าล้างข้อมูลเบราว์เซอร์ (clear site data) ข้อมูลจะหายทั้งหมด
- ระบบ auth เป็นแบบ client-side ล้วน เหมาะสำหรับสาธิตการใช้งาน **ไม่เหมาะกับข้อมูลจริงที่ต้องการความปลอดภัยสูง**

โปรเจกต์นี้ได้ออกแบบสถาปัตยกรรม backend ไว้รองรับการต่อยอด (Node.js/Express + PostgreSQL + Prisma + JWT auth) สำหรับทำให้ข้อมูลเก็บถาวรและปลอดภัยจริง

## License

MIT — ใช้งาน แก้ไข หรือต่อยอดได้อย่างอิสระ
