# 📦 Download YT-DLP PRO TERMUX

> **YT-DLP PRO TERMUX V2.1 — Crash Hotfix**
>
> สำหรับ Android + Termux

## ⬇️ วิธีดาวน์โหลด

### วิธีที่ 1 — Download ZIP

1. เปิดหน้า Repository
2. กดปุ่ม **Code**
3. เลือก **Download ZIP**
4. แตกไฟล์ ZIP แล้วเข้าโฟลเดอร์โปรเจกต์

### วิธีที่ 2 — Clone ด้วย Git

```bash
git clone https://github.com/kimanojoshave-cpu/Gim.git
cd Gim
```

> ถ้า Termux ยังไม่มี Git ให้ติดตั้งด้วย `pkg install git`

## 📱 ติดตั้งบน Termux

```bash
pkg update
pkg install python ffmpeg git
pip install -r requirements.txt
python main.py
```

## 🔧 ตรวจสอบระบบก่อนใช้งาน

สามารถใช้ Diagnostics ในโปรแกรมเพื่อตรวจสอบ Python, yt-dlp, FFmpeg, ffprobe, storage และ network ได้

## 📁 โครงสร้างหลังดาวน์โหลด

```text
Gim/
├── main.py
├── requirements.txt
├── app/
├── tests/
├── docs/
└── README.md
```

## ⚠️ หมายเหตุ

- โปรเจกต์นี้ออกแบบสำหรับ **Android + Termux**
- ต้องมี Python และ FFmpeg พร้อมใช้งาน
- ฟีเจอร์บางอย่างของ yt-dlp อาจขึ้นอยู่กับเว็บไซต์ต้นทางและเวอร์ชันของ yt-dlp
- ก่อนใช้งานควรอ่าน `README.md` และ `requirements.txt`

## 🔗 Repository

**GitHub:** https://github.com/kimanojoshave-cpu/Gim

---

<div align="center">

**💙 YT-DLP PRO TERMUX**  
Built for Android • Powered by yt-dlp • Designed for Termux

</div>
