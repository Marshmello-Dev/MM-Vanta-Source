<p align="center"><img src="src/Vanta/Assets/Branding/MM-Community.png" width="104" alt="MM Community"></p>

# Vanta 1.0.5 Release

เครื่องมือ Open Source สำหรับจัดการ FiveM / RedM และการตั้งค่า Windows โดย **MM Community**

[English](README_EN.md) · [MIT License](LICENSE) · [วิธีแจกบน GitHub](docs/GITHUB_RELEASE.md) · [Discord Support](https://discord.gg/WA58n6rspy)

## ฟีเจอร์

- Dashboard แสดง CPU, GPU, RAM, ดิสก์ และเครือข่าย
- จัดการแคช FiveM / RedM และโปรไฟล์การเปิด FiveM
- CPU Affinity, Dynamic CPU และ Smart Memory
- กฎ CPU / I/O / GPU Priority แยก FiveM / RedM รวมโปรเซสย่อยที่ตรวจพบ
- GPU Preference แยกตามไฟล์เกม และแผนพลังงาน Ultimate Performance
- ReShade สำหรับ FiveM / RedM และ GTA V พร้อม All Effects
- จัดการ QuantV จากไฟล์ ZIP หรือโฟลเดอร์ที่ผู้ใช้มี
- สำรอง/คืนค่า การตั้งค่าระบบและเครือข่าย
- Auto Click, ทางลัดดาวน์โหลด 18 โปรแกรม และภาษาไทย/อังกฤษ

## เริ่มใช้งาน

1. ดาวน์โหลด `Vanta-v1.0.5-Portable-win-x64.zip` จากหน้า Releases ของ repository นี้
2. แตก ZIP แล้วเปิด `Vanta.exe` บน Windows x64 โปรแกรมจะขอสิทธิ์ผู้ดูแลระบบ
3. Portable รวม .NET มาแล้ว ไม่ต้องติดตั้ง SDK เพื่อใช้งาน
4. ตรวจตำแหน่งเกมใน Settings แล้วใช้เฉพาะฟังก์ชันที่ต้องการ

กฎ Priority ทำงานทุก 2 วินาทีขณะเปิด Vanta และคืนค่าโปรเซสเดิมเมื่อปิดโปรแกรม ส่วน GPU Preference ต้องเปิดเกมใหม่จึงใช้ค่าใหม่ และคงอยู่จนสั่งคืนค่า แผนพลังงานมีผลทั้งระบบและยังคงอยู่หลังปิด Vanta

I/O High, GPU Priority และ Ultimate Performance ขึ้นอยู่กับสิทธิ์และการรองรับของ Windows/ไดรเวอร์ ให้ดูค่าจริงและสถานะในตาราง การตั้ง Priority ไม่รับประกันว่า FPS จะเพิ่ม

## ReShade และ QuantV ในรุ่น Open Source

รุ่น 1.0.5 ฝังแพ็ก mods ทั้งชุดไว้ใน `Vanta.exe` แล้ว ไม่ต้องมี `Packages` หรือดาวน์โหลด ZIP แยก กด **ติดตั้ง** ในหน้า ReShade เพื่อติดตั้ง RPF ทั้งสองไฟล์, ReShade 6.4.1, QuantV.addon, Shader/Texture และ Preset พร้อมสำรองก่อนเขียนทับ ระบบเปิด/ปิด FiveM เพื่อรับรหัส ReShade และคง Preset 2 ของแพ็กเป็นค่าเริ่มต้น

นำเข้า Preset `.ini` ได้หลายไฟล์ด้วย **Ctrl+A** ในหน้าต่างเลือกไฟล์ หรือลากลงกรอบ Preset Manager ชื่อซ้ำจะเติม `(2)`, `(3)` ไม่เขียนทับเดิม รายงานไฟล์ที่ไม่ใช่ Preset แยกจากไฟล์สำเร็จ

Source ZIP รวมโค้ดและไฟล์แพ็กที่ใช้ฝังในโปรแกรมแล้ว Build จากชุดนี้ได้เลย ดู [คู่มือแพ็กครบชุด](docs/COMPLETE-PACK.md)

Lilium รุ่นที่รองรับ 6.4.1 ยังคงรวมเป็นซอร์สต้นฉบับ พร้อม GPL และคำประกาศสิทธิ์ การเลือก All Effects ต้องใช้อินเทอร์เน็ต และบาง Shader อาจไม่รองรับเกม/รุ่น ReShade ที่ใช้อยู่

## Build จาก Source

ต้องมี Windows x64 และ **.NET SDK 10** เปิด `build-portable.bat` หรือใช้:

```powershell
pwsh ./scripts/test.ps1
pwsh ./scripts/package.ps1
```

ไฟล์แจกอยู่ใน `artifacts/release` หากไม่มี SDK สคริปต์ `.bat` จะเปิดหน้าดาวน์โหลด SDK ให้ มี `build-installer.bat` สำหรับผู้ที่ติดตั้ง Inno Setup เพิ่มแล้ว แต่แพ็กที่เตรียมมาให้ครั้งนี้เป็น Portable

## สถานะและข้อมูล

- [ผลตรวจและรายการที่ต้องทดสอบบน Windows](docs/VALIDATION.md)
- [คู่มือ GPU / Power Profile](docs/GPU-POWER.md)
- [วิเคราะห์ความพร้อมและ Roadmap](docs/READINESS_TH.md)
- [แนวทางร่วมพัฒนา](CONTRIBUTING.md)
- [ความปลอดภัยและข้อมูล Log](SECURITY.md)
- [ส่วนประกอบภายนอกและ License](THIRD_PARTY_NOTICES.md)

ข้อมูลตั้งค่าและสำรองเก็บที่ `%APPDATA%\Vanta` อย่าลบโฟลเดอร์นี้หากยังต้องใช้สำเนาคืนค่า ก่อนแนบ Log ให้ลบชื่อผู้ใช้, IP และพาธส่วนตัว

เวอร์ชันสาธารณะเริ่มที่ **1.0.0** ส่วนเลข 1.2.x ก่อนหน้านี้เป็นรุ่นพัฒนาภายใน เปลี่ยนเลขเวอร์ชันโดยยังใช้ข้อมูลตั้งค่าเดิม โค้ด Vanta ใช้ MIT; ส่วนประกอบภายนอกและเครื่องหมายการค้ามีเงื่อนไขของตนเอง


## แก้ Shader สีแดงใน 6.4.1
ปิด FiveM แล้วไป ReShade → **ซ่อม Shader 6.4.1** ในรุ่น 1.0.5 เพื่อซ่อม Lilium, cShade และ vort_HDR พร้อมสำรองไฟล์เดิม ไม่ต้องถอน QuantV
