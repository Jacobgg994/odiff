<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Jacobgg994/odiff/main/odiff-logo-dark.png">
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Jacobgg994/odiff/main/odiff-logo-light.png">
    <img alt="odiff logo" src="https://raw.githubusercontent.com/Jacobgg994/odiff/main/odiff-logo-dark.png">
  </picture>
</p>

<h3 align="center"> เครื่องมือเปรียบเทียบความแตกต่างของรูปภาพแบบพิกเซลต่อพิกเซล (Single-thread) ที่เร็วที่สุดในโลก </h3>

## Odiff คืออะไร?

ODiff เป็นเครื่องมือเปรียบเทียบรูปภาพระดับ Native ที่ทำงานได้รวดเร็วมาก สามารถเปรียบเทียบความแตกต่างทางสายตาระหว่าง 2 รูปภาพได้ในระดับ **มิลลิวินาที** ODiff ถูกออกแบบมาโดยเฉพาะเพื่อจัดการกับรูปภาพที่มีความคล้ายคลึงกันมาก เช่น ภาพสกรีนช็อต, รูปถ่าย, ภาพที่สร้างจาก AI และอื่นๆ โดยเน้นความสะดวกในการพกพา (Portable), ความเร็ว และการใช้หน่วยความจำอย่างมีประสิทธิภาพ

เดิมพัฒนาด้วย OCaml และปัจจุบันเปลี่ยนมาใช้ Zig พร้อมการเพิ่มประสิทธิภาพ SIMD สำหรับ SSE2, AVX2, AVX512 และ NEON

## ตัวอย่าง (Demo)

| รูปหลัก (Base) | รูปเปรียบเทียบ (Comparison) | ผลลัพธ์ความต่าง (Diff) |
| :--- | :--- | :--- |
| ![](https://raw.githubusercontent.com/dmtrKovalenko/odiff/main/images/tiger.jpg) | ![](https://raw.githubusercontent.com/dmtrKovalenko/odiff/main/images/tiger-2.jpg) | ![diff](https://raw.githubusercontent.com/dmtrKovalenko/odiff/main/images/tiger-diff.png) |
| ![](https://raw.githubusercontent.com/dmtrKovalenko/odiff/main/images/www.cypress.io.png) | ![](https://raw.githubusercontent.com/dmtrKovalenko/odiff/main/images/www.cypress.io-1.png) | ![diff](https://raw.githubusercontent.com/dmtrKovalenko/odiff/main/images/www.cypress-diff.png) |

## คุณสมบัติเด่น (Features)

- ✅ **เปรียบเทียบข้ามฟอร์แมต** - เปรียบเทียบไฟล์ .jpg กับ .png ได้อย่างไร้ปัญหา
- ✅ **รองรับไฟล์หลายประเภท** - สนับสนุน `.png`, `.jpeg`, `.jpg`, `.webp`, และ `.tiff`
- ✅ **รองรับเลย์เอาต์ที่ต่างกัน** - สามารถเปรียบเทียบรูปภาพที่มีการจัดวางต่างกันได้
- ✅ **ตรวจจับ Anti-aliasing** - ช่วยลดสัญญาณรบกวนจากการลบรอยหยัก
- ✅ **กำหนดขอบเขตที่ต้องการข้าม (Ignore Regions)** - ไม่นำพื้นที่บางส่วนมาคำนวณ
- ✅ **อัลกอริทึม YIQ NTSC** - ใช้เพื่อกำหนดความแตกต่างที่สายตามนุษย์มองเห็นจริง
- ✅ **SIMD Optimized** - รองรับ SSE2, AVX2, AVX512 และ NEON
- ✅ **ใช้หน่วยความจำต่ำ** - ควบคุมการใช้ทรัพยากรได้อย่างมีประสิทธิภาพ
- ✅ **ความถูกต้อง 100%** - มีการทดสอบครอบคลุมและรองรับเวอร์ชันเก่าได้สมบูรณ์

## วิธีการใช้งาน (Usage)

### การเปรียบเทียบพื้นฐาน

รันคำสั่งเปรียบเทียบง่ายๆ โดยระบุเส้นทางไฟล์รูปภาพ (รองรับฟอร์แมตที่กำหนด) ส่วนไฟล์ผลลัพธ์ (Diff output) เป็นตัวเลือกเสริมและต้องเป็นนามสกุล `.png` เท่านั้น

```bash
odiff ./base.png ./comparison.png ./diff.png
```

### การติดตั้ง

สามารถติดตั้งผ่าน npm ได้ง่ายๆ:

```bash
npm install -g odiff-bin
```

หรือดาวน์โหลดไฟล์ Executable จากหน้า [Releases](https://github.com/Jacobgg994/odiff/releases)
