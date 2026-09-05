# AR เครื่องซักผ้า 🧺

เว็บ AR แบบ marker-based เมื่อกล้องเจอ Hiro marker จะแสดงเครื่องซักผ้า 3D
ที่ปรับความเร็วรอบ (RPM) ได้ด้วยปุ่มกด สร้างด้วย A-Frame + AR.js

## ไฟล์ในโปรเจกต์
| ไฟล์ | คำอธิบาย |
|------|----------|
| `index.html` | หน้าเว็บ AR หลัก |
| `marker.png` | Hiro marker (สำหรับแสดงบนจอ) |
| `marker-print.png` | หน้ากระดาษ A4 พร้อมพิมพ์ (marker + คำแนะนำ) |

---

## วิธีอัปโหลดขึ้น GitHub + เปิดใช้ GitHub Pages

> AR ต้องเปิดผ่าน **HTTPS** เท่านั้น กล้องถึงจะทำงาน — GitHub Pages ให้ HTTPS ฟรี

### วิธีที่ 1: ผ่านหน้าเว็บ GitHub (ง่ายสุด ไม่ต้องใช้คำสั่ง)
1. ล็อกอิน [github.com](https://github.com) → กด **New repository**
2. ตั้งชื่อ repo เช่น `ar-washing-machine` → เลือก **Public** → **Create repository**
3. กด **uploading an existing file** แล้วลากไฟล์ทั้งหมด (`index.html`, `marker.png`, `marker-print.png`, `README.md`) เข้าไป → **Commit changes**
4. ไปที่ **Settings → Pages**
5. หัวข้อ *Build and deployment* → *Source* เลือก **Deploy from a branch**
6. *Branch* เลือก **main** และโฟลเดอร์ **/ (root)** → **Save**
7. รอ 1–2 นาที รีเฟรชหน้า Pages จะได้ลิงก์ประมาณ
   `https://<username>.github.io/ar-washing-machine/`

### วิธีที่ 2: ผ่าน Git (คำสั่ง)
```bash
git init
git add .
git commit -m "AR washing machine"
git branch -M main
git remote add origin https://github.com/<username>/ar-washing-machine.git
git push -u origin main
```
จากนั้นไปตั้งค่า **Settings → Pages** เหมือนข้อ 4–7 ด้านบน

---

## วิธีใช้งาน
1. เปิดลิงก์ GitHub Pages (`https://...`) บนมือถือ
   - **อย่าเปิดในแอป Line/Facebook** เพราะจะบล็อกกล้อง — ให้เปิดใน **Safari** (iPhone) หรือ **Chrome** (Android) โดยตรง
2. แตะปุ่ม **"📷 แตะเพื่อเปิดกล้อง"** แล้วกด **อนุญาต**
3. เล็งกล้องไปที่ **Hiro marker** (พิมพ์จาก `marker-print.png` หรือเปิดค้างบนจออีกเครื่อง)
4. เครื่องซักผ้าจะปรากฏขึ้น — กดปุ่มปรับความเร็ว: ปิด / ซัก / ล้าง / ปั่นหมาด / ปั่นแห้ง / อัตโนมัติ และปุ่ม +/− ปรับละเอียด

## แก้ปัญหาที่พบบ่อย
- **จอขาว ไม่มีภาพกล้อง** → เปิดในแอปที่บล็อกกล้อง หรือยังไม่ได้กดอนุญาต → เปิดใน Safari/Chrome แล้วกดอนุญาต
- **ขึ้นกล่องแดง "โหลดไลบรารีไม่สำเร็จ"** → เน็ตหลุด/ช้า ครั้งแรกต้องต่อเน็ตเพื่อโหลดไลบรารี → รีเฟรชใหม่
- **ไม่เห็นเครื่องซักผ้าทั้งที่กล้องติด** → เล็ง marker ให้เต็มเฟรม แสงสว่างพอ ไม่เอียง/สะท้อนแสง

---
สร้างด้วย A-Frame 1.3.0 + AR.js 3.4.5
