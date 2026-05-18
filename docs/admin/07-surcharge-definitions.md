# บทที่ 7 — นิยาม Surcharge

*DOC-ADM-001 v1.0 | คู่มือผู้ดูแลระบบ*

---

## 7.1 ภาพรวม

**Surcharge Definition** คือการกำหนดนิยามของค่าธรรมเนียมเพิ่มเติม (Surcharge) ต่าง ๆ ที่สายเรือเรียกเก็บนอกจากอัตราค่าระวางพื้นฐาน

ระบบใช้ข้อมูลนี้เพื่อ:
- **แสดงผล** Surcharge ในการค้นหาอัตราค่าระวาง
- **จัดลำดับคอลัมน์** ใน Excel ที่ส่งออก
- **รวม** Surcharge ที่มีชื่อเรียกต่างกันแต่หมายถึงสิ่งเดียวกัน (ผ่าน Aliases)

**สิทธิ์การเข้าถึง:** Admin และ Superadmin

---

## 7.2 การดูรายการ Surcharge Definitions

<div class="procedure">

1. คลิกเมนู **Surcharge Definitions** ในแถบนำทาง
2. ระบบแสดงรายการ Surcharge ทั้งหมดพร้อมลำดับการแสดงผล

</div>

<div class="screenshot-placeholder">
[รูปที่ 7.1: หน้าจอ Surcharge Definitions]
</div>

---

## 7.3 การเพิ่ม Surcharge ใหม่

<div class="procedure">

1. คลิกปุ่ม **"เพิ่ม Surcharge"** (Add Surcharge Definition)
2. กรอกข้อมูลในแบบฟอร์ม (ดูตาราง 7.1)
3. คลิก **"บันทึก"**

</div>

**ตาราง 7.1 — ฟิลด์ในแบบฟอร์ม Surcharge Definition**

| ฟิลด์ | จำเป็น | คำอธิบาย | ตัวอย่าง |
|-------|:------:|---------|---------|
| Code | ✓ | รหัสเฉพาะ (ตัวพิมพ์ใหญ่) | `BUNKER` |
| Display Name | ✓ | ชื่อที่แสดงในระบบ | `ค่าน้ำมัน (Bunker)` |
| Group Name | | หมวดหมู่ | `BUNKER_SURCHARGES` |
| Is Container Type | | เป็นค่าตามประเภทตู้หรือไม่ | ✓ (ตาม 20'/40'/40HQ) |
| Aliases | | ชื่อเรียกอื่นที่ Parser อาจพบ | `BAF`, `BAF_CHG`, `BF` |
| Display Order | ✓ | ลำดับในการแสดงผลคอลัมน์ Excel | `10` |
| Is Active | ✓ | เปิด/ปิดการใช้งาน | เปิด |

---

## 7.4 ความหมายของฟิลด์ Is Container Type

| ค่า | ความหมาย | ตัวอย่าง |
|-----|---------|---------|
| **เปิด** (true) | Surcharge มีค่าแยกตามขนาดตู้ (20', 40', 40HQ) | BAF, PSS, GRI |
| **ปิด** (false) | Surcharge เป็นค่าคงที่ไม่ขึ้นกับขนาดตู้ | Documentation Fee, THC flat |

---

## 7.5 การกำหนด Aliases

Aliases คือชื่อเรียกอื่นของ Surcharge เดียวกันที่ Parser อาจพบในเอกสารของสายเรือต่าง ๆ

**วิธีเพิ่ม Aliases:**

- กรอกชื่อแล้วกด **Enter** หรือ **,**
- ระบบแสดงเป็น chip

**ตัวอย่าง Aliases ที่พบบ่อย:**

| Code | Aliases ที่พบ |
|------|-------------|
| `BUNKER` | `BAF`, `BAF_CHG`, `BF`, `BUNKER_ADJ` |
| `GRI` | `GRI_CHG`, `GENERAL_RATE_INCREASE` |
| `PSS` | `PSS_CHG`, `PEAK_SEASON` |
| `THC` | `TERMINAL_HANDLING`, `THC_CHG` |
| `EBS` | `EMERGENCY_BUNKER`, `EBS_CHG` |

---

## 7.6 การจัดลำดับ (Display Order)

ลำดับการแสดงผลส่งผลต่อ **ลำดับคอลัมน์ในไฟล์ Excel** ที่ส่งออก

- ค่าน้อย = แสดงก่อน (ทางซ้าย)
- แนะนำให้กำหนดเว้นช่วงห่าง เช่น 10, 20, 30 เพื่อให้เพิ่ม Surcharge ใหม่ระหว่างกันได้

**ตัวอย่างลำดับที่แนะนำ:**

| Display Order | Code | ชื่อ |
|:------------:|------|------|
| 10 | `BUNKER` | ค่าน้ำมัน |
| 20 | `GRI` | การปรับค่าระวางทั่วไป |
| 30 | `PSS` | ค่าฤดูกาล Peak |
| 40 | `EBS` | ค่าน้ำมันฉุกเฉิน |
| 50 | `THC` | ค่าดำเนินการท่าเรือ |
| 60 | `DOC` | ค่าเอกสาร |

---

## 7.7 การแก้ไขและลบ Surcharge

**แก้ไข:**

<div class="procedure">

1. คลิกปุ่ม **"แก้ไข"** ในแถวของ Surcharge ที่ต้องการ
2. แก้ไขข้อมูล
3. คลิก **"บันทึก"**

</div>

**ลบ:**

<div class="procedure">

1. คลิกปุ่ม **"ลบ"** (Delete)
2. ยืนยันการลบ

</div>

!!! warning "คำเตือน"
    การลบ Surcharge Definition จะไม่ลบข้อมูล Surcharge ที่บันทึกไว้แล้วในอัตราค่าระวาง แต่จะทำให้ไม่แสดงในคอลัมน์ Excel การส่งออกในอนาคต แนะนำให้ **ปิดการใช้งาน** แทนการลบ
