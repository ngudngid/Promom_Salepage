# Promom — DHA Probio 9 / 9+ Salepage

Landing page (salepage) แบบ **ไฟล์เดียวจบ** (HTML + CSS + JS อยู่ใน index.html)
สไตล์เดียวกับเว็บเดิม พร้อม Push ขึ้น Git หรืออัปโหลดหน้าเว็บ GitHub แล้ว Deploy บน Vercel ได้ทันที (static, ไม่ต้อง build)

## โครงสร้างไฟล์
```
.
├── index.html          # หน้า Salepage ทั้งหมด (HTML + CSS + JS + SEO + JSON-LD ในไฟล์เดียว)
├── vercel.json         # ตั้งค่า Vercel (clean URLs + cache รูป)
├── robots.txt          # SEO
├── sitemap.xml         # SEO
├── README.md
└── images/             # รูปภาพที่ใช้บนเว็บ (8 รูปคลีน)
    └── _source/        # ภาพหน้าต้นฉบับเต็ม 11 หน้า ไว้ครอปอ้างอิง
```

## รูปภาพ (อยู่ในโฟลเดอร์ `images/` แล้ว)
ผมครอปเอาเฉพาะรูปภาพ/กราฟิกล้วน (ตัดข้อความการตลาดออก) จาก PDF มาใส่ให้ครบ 8 ช่องแล้ว
ถ้าอยากเปลี่ยนรูปไหน เซฟทับชื่อไฟล์เดิมได้เลย (ภาพต้นฉบับความละเอียดสูงอยู่ใน `images/_source/`)

> หมายเหตุ: ส่วน **Probiotics 5 สายพันธุ์** และ **รีวิว** ทำเป็น HTML/CSS การ์ดล้วน (ไม่ใช้รูป)
> เพราะรูปต้นฉบับมีข้อความทับเยอะ แยกรูปสะอาดไม่ได้ — การ์ดข้อความดูโปรกว่า
>
> แนะนำ: รูปกราฟิก/สินค้า ใช้ `.png`, รูปถ่าย ใช้ `.jpg` (ไฟล์เล็ก โหลดเร็ว)

## ลิงก์ปุ่ม Line (CTA)
เปิด `index.html` เลื่อนไปท้ายไฟล์ (ใน `<script>`) แก้บรรทัดเดียว:
```js
var LINE_URL = "#"; // เปลี่ยนเป็น เช่น "https://lin.ee/xxxxxx"
```
ทุกปุ่มที่มี `data-line` (ปุ่มในหน้า + FAB ลอย + แถบล่างมือถือ) จะอัปเดตลิงก์ให้อัตโนมัติ

## วิธี Deploy ขึ้น Vercel
1. Push โค้ดขึ้น GitHub
2. เข้า [vercel.com](https://vercel.com) → New Project → เลือก repo นี้
3. Framework Preset: **Other** (static) → กด Deploy
4. หลัง deploy แล้ว แทนที่ `promom-salepage.vercel.app` ด้วยโดเมนจริง ในไฟล์ `index.html` (canonical + og:url + og:image), `robots.txt` และ `sitemap.xml`

## หมายเหตุ
- ไฟล์ `.md` และ `.pdf` ต้นฉบับถูก ignore ไว้ใน `.gitignore` (ไม่ขึ้น repo เพื่อให้เบา) — ถ้าต้องการเก็บใน repo ลบบรรทัดออกได้
