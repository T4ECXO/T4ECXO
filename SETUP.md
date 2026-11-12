# ตั้งค่าโปรไฟล์ T4ECXO

นำโฟลเดอร์ `assets` ไปไว้ที่ราก repository ด้วย เพื่อให้หัวโปรไฟล์ Ocex แสดงได้ ชื่อที่แสดงคือ Ocex แต่บัญชีสำหรับกราฟยังเป็น T4ECXO

1. ใช้ repository แบบ Public ชื่อ `T4ECXO/T4ECXO` และนำ `README.md` ไปไว้ที่ราก repository
2. นำ `.github/workflows/metrics.yml` ไปไว้ตามเส้นทางนี้บน default branch ด้วย (โฟลเดอร์ .github อาจถูกซ่อนเมื่อแตก ZIP)
3. ไปที่ GitHub Settings > Developer settings > Personal access tokens > Tokens (classic) แล้วสร้าง token โดยไม่เลือก scopes สำหรับอ่านข้อมูลสาธารณะ ตั้งวันหมดอายุที่ต้องการ
4. ที่ repository ไปที่ Settings > Secrets and variables > Actions > New repository secret ตั้งชื่อ `METRICS_TOKEN` แล้ววาง token เป็นค่าของ secret เท่านั้น ไม่ใส่ใน README หรือไฟล์โค้ด
5. ไปที่ Actions > 3D contribution calendar > Run workflow แล้วรอจนสำเร็จ ระบบจะสร้าง `metrics.isocalendar.svg` ให้ README แสดง

กราฟเป็น Metrics isocalendar แบบครึ่งปี มีกราฟ 3D และสถิติข้างกราฟเหมือนรูปอ้างอิง ข้อมูลจะมาจากบัญชี T4ECXO จริงเมื่อ workflow รัน ไม่ใช่ตัวเลขในรูปตัวอย่าง
ตั้งเวลาอัปเดตไว้ทุกวันประมาณ 03:17 น. เวลาไทย (GitHub อาจเริ่มช้ากว่าเวลา) หาก token หมดอายุ ต้องอัปเดต secret ก่อนรันต่อ

ไฟล์ติดตั้งแล้วบน GitHub ตั้งค่า METRICS_TOKEN ตามข้อ 3–4 แล้วรัน workflow ตามข้อ 5 เพื่อสร้างกราฟครั้งแรก

โลโก้ใช้ Shields.io / Simple Icons ส่วน Autodesk Fusion และ CiRA CORE ใช้ป้ายชื่อ ไม่มีการสร้างโลโก้เลียนแบบ

เอกสาร:
- https://github.com/lowlighter/metrics/blob/master/source/plugins/isocalendar/README.md
- https://github.com/lowlighter/metrics/blob/master/.github/readme/partials/documentation/setup/action.md

หัวโปรไฟล์พิมพ์ทีละตัวทุก 0.7 วินาที หยุด 4 วินาที แล้ววนซ้ำ พร้อมเคอร์เซอร์กะพริบ ใช้ SVG animation ไม่ต้องตั้งค่าเพิ่ม หากมีไฟล์เดิมอยู่แล้ว เปลี่ยนเฉพาะ assets/ocex-header.svg ได้เลย
