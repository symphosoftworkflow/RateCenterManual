# บทที่ 6 — การกำหนด Source Email

*DOC-ADM-001 v1.0 | คู่มือผู้ดูแลระบบ*

---

## 6.1 ภาพรวม

**Source Email** คือการกำหนดความสัมพันธ์ระหว่าง **อีเมลผู้ส่ง** กับ **สายเรือ** เพื่อให้ระบบทราบว่าอีเมลที่มาจากที่อยู่ใดควรวิเคราะห์ด้วย Parser ของสายเรือใด

ตัวอย่าง: อีเมลที่มาจาก `rates@cosco.com` → ใช้ COSCO Parser

**สิทธิ์การเข้าถึง:** Admin และ Superadmin

---

## 6.2 การดูรายชื่อ Source Email

<div class="procedure" markdown="block">

1. คลิกเมนู **Source Emails** ในแถบนำทางด้านซ้าย
2. ระบบแสดงรายชื่อ Source Email ทั้งหมดที่กำหนดไว้

</div>

<div class="screenshot-placeholder" markdown="block">
[รูปที่ 6.1: หน้าจอ Source Emails]
</div>

---

## 6.3 การเพิ่ม Source Email ใหม่

<div class="procedure" markdown="block">

1. คลิกปุ่ม **"เพิ่ม Source Email"** (Add Source Email)
2. กรอกข้อมูลในแบบฟอร์ม (ดูตาราง 6.1)
3. คลิก **"บันทึก"**

</div>

<div class="screenshot-placeholder" markdown="block">
[รูปที่ 6.2: แบบฟอร์มเพิ่ม Source Email]
</div>

**ตาราง 6.1 — ฟิลด์ในแบบฟอร์ม Source Email**

| ฟิลด์ | จำเป็น | คำอธิบาย | ตัวอย่าง |
|-------|:------:|---------|---------|
| Source Email | ✓ | อีเมลของผู้ส่ง (สายเรือ) | `shipping@cosco.com` |
| Source Name | ✓ | รหัสสายเรือในระบบ | `COSCO` |
| Description | | คำอธิบายเพิ่มเติม | `COSCO Shipping Thailand` |
| Keywords | | คำสำคัญในหัวข้ออีเมล | `RATE SHEET`, `MARCH 2026` |
| Is Active | ✓ | เปิด/ปิดการใช้งาน | เปิด |

---

## 6.4 การกำหนด Keywords

**Keywords** ใช้สำหรับการค้นหาอีเมลที่เกี่ยวข้องกับ Rate Sheet จากหัวข้ออีเมล (Subject)

### 6.4.1 ความสำคัญของ Keywords

ในกรณีที่อีเมลผู้ส่งเดียวกัน (**ที่อยู่อีเมลเดียวกัน**) ส่ง Rate Sheet ของหลายสายเรือ Keywords จะช่วยแยกแยะว่าอีเมลไหนเป็นของสายเรือใด

ตัวอย่าง:

| Source Email | Source Name | Keywords |
|-------------|------------|---------|
| `agent@forwarder.com` | COSCO | `COSCO RATE`, `COSCO SHIPPING` |
| `agent@forwarder.com` | HMM | `HMM RATE`, `HYUNDAI MERCHANT` |

### 6.4.2 วิธีกรอก Keywords

- กรอก Keyword แต่ละคำแล้วกด **Enter** หรือ **,** (ลูกน้ำ) เพื่อเพิ่ม
- ระบบแสดง Keyword เป็น chip สีน้ำเงิน
- คลิก × บน chip เพื่อลบ Keyword

!!! note "หมายเหตุ"
    Keywords ไม่จำเป็นต้องกรอกในกรณีที่ผู้ส่งแต่ละรายส่งให้สายเรือเดียว (1 อีเมล = 1 สายเรือ)

---

## 6.5 รหัสสายเรือที่รองรับ (Source Name)

ต้องกรอก **Source Name ตรงตามรหัสต่อไปนี้** (ตัวพิมพ์ใหญ่):

| Source Name | ชื่อสายเรือ |
|------------|-----------|
| `COSCO` | COSCO Shipping |
| `ESL` | Emirates Shipping Line |
| `HMM` | Hyundai Merchant Marine |
| `KMTC` | Korea Marine Transport Corporation |
| `PIL` | Pacific International Lines |
| `ZIM` | ZIM Integrated Shipping Services |
| `CKLINE` | CK Line |
| `SMLINE` | SM Line |
| `TSLINE` | TS Lines |
| `RCL` | Regional Container Lines |
| `IAL` | IAL |
| `JJS` | JJS |
| `SINOKOR` | Sinokor Merchant Marine |
| `SITC` | SITC Container Lines |
| `YANGMING` | Yang Ming Marine Transport |

!!! warning "คำเตือน"
    หาก Source Name ไม่ตรงกับรหัสในตารางข้างต้น ระบบจะไม่สามารถเลือก Parser ที่ถูกต้องได้ และกระบวนการวิเคราะห์จะล้มเหลว

---

## 6.6 การแก้ไขและปิดการใช้งาน

**แก้ไข:**

<div class="procedure" markdown="block">

1. คลิกปุ่ม **"แก้ไข"** ในแถวของ Source Email ที่ต้องการ
2. แก้ไขข้อมูล
3. คลิก **"บันทึก"**

</div>

**ปิดการใช้งาน:**

ปิด Toggle **"Is Active"** — อีเมลจากผู้ส่งรายนั้นจะไม่ถูกประมวลผลชั่วคราว

**ลบ:**

<div class="procedure" markdown="block">

1. คลิกปุ่ม **"ลบ"** (Delete)
2. ยืนยันการลบ

</div>

!!! danger "ข้อควรระวัง"
    การลบ Source Email จะทำให้อีเมลใหม่จากผู้ส่งนั้นไม่ถูกประมวลผล ข้อมูลที่ดึงมาแล้วยังคงอยู่ในระบบ แนะนำให้ **ปิดการใช้งาน** แทนการลบ
