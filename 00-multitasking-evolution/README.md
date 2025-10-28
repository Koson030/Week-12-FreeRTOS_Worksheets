# 00. วิวัฒนาการของ Multitasking ในไมโครคอนโทรลเลอร์

## ภาพรวมหัวข้อ

หัวข้อนี้จะพาคุณทำความเข้าใจเกี่ยวกับประวัติศาสตร์และวิวัฒนาการของการทำ Multitasking ในไมโครคอนโทรลเลอร์ ตั้งแต่ยุคเริ่มต้นจนถึงยุค RTOS

## 📋 เนื้อหาในหัวข้อ

### 📖 ทฤษฎี (1 ชั่วโมง)
- [theory.md](theory.md) - เนื้อหาบรรยายหลัก
  - ยุคเริ่มต้น: Single Task Systems
  - การพัฒนาสู่ Time-Sharing
  - เทคนิค Multitasking ต่างๆ
  - การเกิดขึ้นของ RTOS

### 💻 ปฏิบัติ (2 ชั่วโมง)
- [practice/](practice/) - โฟลเดอร์สำหรับการปฏิบัติ
  - Lab 1: Single Task vs Multitasking Demo
  - Lab 2: Time-Sharing Implementation
  - Lab 3: Cooperative vs Preemptive Comparison

## 🎯 วัตถุประสงค์การเรียนรู้

เมื่อจบหัวข้อนี้ นักเรียนจะสามารถ:
1. อธิบายวิวัฒนาการของ Multitasking ได้
2. เข้าใจปัญหาของระบบ Single Task
3. อธิบายเทคนิค Multitasking ต่างๆ พร้อมข้อดี-ข้อเสีย
4. เข้าใจเหตุผลที่ RTOS เกิดขึ้น
5. เลือกเทคนิคที่เหมาะสมสำหรับแต่ละงาน

## คำตอบ
1. **วิวัฒนาการของ Multitasking**
  - จากระบบ Single Task ที่ทำงานทีละงาน → Time-Sharing (แบ่งเวลาให้แต่ละงาน) → Multitasking (หลายงานทำงานพร้อมกัน) → RTOS (ระบบปฏิบัติการเวลาจริง)
2. **ปัญหาของระบบ Single Task**
  - ไม่สามารถตอบสนองหลายงานพร้อมกัน, งานที่ใช้เวลานานจะบล็อกงานอื่น, ไม่เหมาะกับงานที่ต้องตอบสนองทันที
3. **เทคนิค Multitasking ต่างๆ พร้อมข้อดี-ข้อเสีย**
  - Manual Time-Sharing: ควบคุมเอง, เข้าใจง่าย, แต่ซับซ้อนเมื่อมีหลายงาน
  - Cooperative Multitasking: งานต้องคืน CPU เอง, ลดปัญหาแย่งทรัพยากร, แต่ถ้างานใดงานหนึ่งไม่คืน CPU จะบล็อกทั้งระบบ
  - Preemptive Multitasking: ระบบจัดสรร CPU อัตโนมัติ, ตอบสนองดี, แต่ต้องระวังเรื่อง Synchronization และ Critical Section
4. **ผลที่ RTOS เกิดขึ้น**
  - เพิ่มประสิทธิภาพการจัดการงาน, รองรับงานหลายประเภท, สามารถกำหนด Priority, มีฟีเจอร์ Synchronization, Scheduling, Memory Management
5. **เลือกเทคนิคที่เหมาะสมสำหรับแต่ละงาน**
  - งานที่ต้องตอบสนองเร็วและมีหลายงานพร้อมกันควรใช้ Preemptive Multitasking หรือ RTOS
  - งานง่ายๆ หรือมีงานเดียว อาจใช้ Single Task หรือ Manual Time-Sharing

## 📚 เอกสารอ้างอิง
- Real-Time Systems Design and Analysis (Phillip A. Laplante)
- FreeRTOS Reference Manual
- ESP-IDF Programming Guide

## ⏱️ เวลาที่ใช้
- **ทฤษฎี**: 1 ชั่วโมง
- **ปฏิบัติ**: 2 ชั่วโมง
- **รวม**: 3 ชั่วโมง