# ค่าเงินบาทรายสัปดาห์ (Telegram Mini App)

กราฟแท่งเทียนค่าเงินบาทแบบโต้ตอบ เปิดจากปุ่มในบอท Telegram
ข้อมูลอัตราอ้างอิง ECB ผ่าน [Frankfurter API](https://frankfurter.dev) ดึงสดทุกครั้งที่เปิด ไม่มีเซิร์ฟเวอร์ของตัวเอง

| ไฟล์ | หน้าที่ |
|---|---|
| `index.html` | หน้า Mini App |
| `config.json` | สกุลเงิน ราคาเป้า เกณฑ์ % และเส้นค่าเฉลี่ย (สคริปต์แจ้งเตือนอ่านไฟล์นี้ด้วย) |
| `.nojekyll` | บอก GitHub Pages ให้เสิร์ฟไฟล์ตรง ๆ |

## เปิดใช้ GitHub Pages

1. สร้าง repository ใหม่บน GitHub ชื่อ `fx-miniapp` (Public)
2. อัปโหลด 3 ไฟล์ข้างบน (ลากวางในหน้า repo ได้) หรือ push ด้วย git
3. Settings → Pages → Source: **Deploy from a branch** → Branch: `main` / `(root)` → Save
4. รอ 1–2 นาที จะได้ลิงก์ `https://<ชื่อผู้ใช้>.github.io/fx-miniapp/`
5. ใส่ลิงก์นั้นเป็น `MINIAPP_URL` ใน `telegram.env` แล้วรัน `python fx_alert.py --set-menu`

## แก้ราคาเป้า

แก้ `config.json` แล้วอัปโหลดทับใน GitHub (Mini App เห็นค่าใหม่ทันทีที่ Pages อัปเดต)
ไฟล์นี้เป็นสาธารณะ อย่าใส่ token หรือข้อมูลส่วนตัว
