# SiteView 360 — Viewer

ตัวดูรูป 360° แบบเฟซบุ๊ก สำหรับรูป equirectangular 2:1 (เช่น export จาก DJI Osmo 360)

- ลากหมุน (มีแรงเฉื่อย), ถ่างนิ้ว/ล้อเมาส์ซูม, ดับเบิลคลิกซูม
- เข็มทิศแสดงทิศ + มุมมอง กดเพื่อรีเซ็ต
- หมุนตามมือถือ (gyroscope) — ต้องเปิดผ่าน https
- เปิดหลายรูป / ลากไฟล์วาง, ย่อรูปอัตโนมัติตาม GPU

ไฟล์เดียว `index.html` ใช้ three.js r128 จาก cdnjs — เปิด GitHub Pages ได้ทันที

## ซิงค์กับโฟลเดอร์ Google Drive
ปุ่ม Google Drive → วางลิงก์โฟลเดอร์ → เว็บจะแสดงโฟลเดอร์ย่อยและรูปทั้งหมด (ใหม่สุดก่อน, ป้าย 360° สำหรับรูป 2:1) กดรีเฟรชเพื่อดึงรูปที่ทีมเพิ่งอัป
เว็บจำโฟลเดอร์ไว้ในเครื่อง / แชร์ให้ทีมด้วย `?folder=<ลิงก์หรือ ID>` / หรือตั้ง `DEFAULT_FOLDER`

### แบบ A — โฟลเดอร์แชร์ "ทุกคนที่มีลิงก์" (ง่ายสุด ไม่ต้องล็อกอิน)
1. Google Cloud Console → โปรเจกต์ใหม่ → Enable **Google Drive API**
2. Credentials → API key → จำกัด API: Drive API, HTTP referrer: `https://weerachid2540.github.io/*`
3. ใส่ `API_KEY`

### แบบ B — โฟลเดอร์จำกัดคน (ล็อกอิน Google)
4. OAuth consent screen → External → scope `drive.readonly` → เพิ่มอีเมลทีมใน Test users
5. Credentials → OAuth client ID (Web) → Authorized JavaScript origins: `https://weerachid2540.github.io`
6. ใส่ `CLIENT_ID` — ทุกคนต้องมีสิทธิ์ดูโฟลเดอร์นั้นอยู่แล้ว
