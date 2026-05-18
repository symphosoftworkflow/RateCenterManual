# ระบบ RateSheetExtractor — เอกสารคู่มือระบบ

<div class="doc-title-page" style="text-align:center; padding:2rem; border:3px double #1a237e; margin-bottom:2rem;">
  <div style="font-size:14px; color:#666;">เอกสารอ้างอิงระบบ | RSE-DOC-2568</div>
  <h1 style="font-size:2rem; color:#1a237e; margin:1rem 0;">RateSheetExtractor</h1>
  <p style="font-size:1.1rem; color:#444;">ระบบประมวลผลอัตราค่าระวางสินค้าทางทะเลแบบอัตโนมัติ</p>
  <div style="display:inline-block; background:#f5f5f5; border:1px solid #ddd; border-radius:4px; padding:1rem 2rem; margin-top:1rem; text-align:left;">
    <strong>รุ่นเอกสาร:</strong> 1.0 &nbsp;|&nbsp;
    <strong>วันที่บังคับใช้:</strong> 18 พฤษภาคม 2568 &nbsp;|&nbsp;
    <strong>ผู้จัดทำ:</strong> LA-OR CO.,LTD.
  </div>
</div>

---

## เอกสารคู่มือที่ให้บริการ

ระบบ RateSheetExtractor มีเอกสารคู่มือ **3 เล่ม** จัดทำตามมาตรฐาน **ISO/IEC 29110-4-1** เพื่อรองรับกลุ่มผู้ใช้งานที่แตกต่างกัน

---

### :material-shield-account: คู่มือผู้ดูแลระบบ

**รหัสเอกสาร:** DOC-ADM-001 | **รุ่น:** 1.0

สำหรับ **ผู้ดูแลระบบ (Admin)** และ **ผู้ดูแลระบบสูงสุด (Superadmin)** ครอบคลุมการติดตั้ง กำหนดค่า และบริหารจัดการระบบ

[:material-arrow-right: เปิดคู่มือผู้ดูแลระบบ](admin/index.md){ .md-button .md-button--primary }

**เนื้อหาหลัก:**

- ภาพรวมระบบและสถาปัตยกรรม
- การจัดการผู้ใช้งานและบทบาท
- การตั้งค่าอีเมล IMAP และ Source Email
- การตรวจสอบและอนุมัติข้อมูลอัตราค่าระวาง
- การบำรุงรักษาและติดตามสถานะระบบ

---

### :material-account: คู่มือผู้ใช้งาน

**รหัสเอกสาร:** DOC-USR-001 | **รุ่น:** 1.0

สำหรับ **ผู้ใช้งานทั่วไป (Sale)** ครอบคลุมการใช้งานฟังก์ชันค้นหาและส่งออกอัตราค่าระวาง

[:material-arrow-right: เปิดคู่มือผู้ใช้งาน](user/index.md){ .md-button .md-button--primary }

**เนื้อหาหลัก:**

- การเข้าสู่ระบบและการตั้งรหัสผ่าน
- การใช้งานหน้าแดชบอร์ด
- การค้นหาอัตราค่าระวางพร้อมตัวกรอง
- การส่งออกข้อมูลในรูปแบบ Excel และ FWD

---

### :material-cog: คู่มือการปฏิบัติงาน

**รหัสเอกสาร:** DOC-OPR-001 | **รุ่น:** 1.0

สำหรับ **เจ้าหน้าที่ปฏิบัติงาน** ครอบคลุมขั้นตอนการปฏิบัติงานประจำวัน การแก้ไขปัญหา และการรายงาน

[:material-arrow-right: เปิดคู่มือการปฏิบัติงาน](operation/index.md){ .md-button .md-button--primary }

**เนื้อหาหลัก:**

- ภาพรวมกระบวนการทำงานตั้งแต่รับอีเมลถึงจัดเก็บอัตราค่าระวาง
- รายการตรวจสอบประจำวัน
- ขั้นตอนการดึงข้อมูลอีเมลและการตรวจสอบ
- การวินิจฉัยและแก้ไขปัญหา

---

## ข้อมูลระบบ

| รายการ | ข้อมูล |
|--------|--------|
| ชื่อระบบ | RateSheetExtractor (ระบบประมวลผลอัตราค่าระวาง) |
| เวอร์ชันระบบ | 1.0 (Phase 7 Complete) |
| ผู้พัฒนา | LA-OR CO.,LTD. |
| เทคโนโลยีหลัก | Node.js, React, PostgreSQL, Python |
| สภาพแวดล้อม | Railway Cloud (Production) |
| มาตรฐานเอกสาร | ISO/IEC 29110-4-1 |
| วันที่ออกเอกสาร | 18 พฤษภาคม 2568 |
| รุ่นเอกสาร | 1.0 |

---

## สัญลักษณ์ที่ใช้ในเอกสาร

| สัญลักษณ์ | ความหมาย |
|-----------|-----------|
| !!! note | ข้อมูลเพิ่มเติมที่ควรทราบ |
| !!! warning | คำเตือน — ดำเนินการด้วยความระมัดระวัง |
| !!! danger | ข้อควรระวังสำคัญ — อาจส่งผลต่อระบบ |
| !!! tip | เคล็ดลับและแนวปฏิบัติที่ดี |
| [รูปที่ X.X: ...] | ตำแหน่งสำหรับภาพประกอบ |
| `ข้อความในกรอบ` | ชื่อปุ่ม เมนู หรือค่าที่ต้องกรอก |

---

---

## :material-presentation: สไลด์นำเสนอโครงการ

[:material-arrow-right: เปิด Presentation (Full Screen)](presentation/index.html){ .md-button }

---

*จัดทำตามมาตรฐาน ISO/IEC 29110-4-1 — Software Engineering: Lifecycle Profiles for Very Small Entities (VSEs)*  
*ลิขสิทธิ์ © 2568 LA-OR CO.,LTD. — สงวนลิขสิทธิ์ทุกประการ*
