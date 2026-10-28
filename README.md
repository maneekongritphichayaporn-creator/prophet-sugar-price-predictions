# MITR PHOL AI HACKATHON: Sugar Price Prediction

โปรเจกต์นี้พัฒนาขึ้นจากการแข่งขัน MITR PHOL AI HACKATHON โดยมีโจทย์หลักคือการพยากรณ์ราคาน้ำตาลจากข้อมูลอนุกรมเวลา และทดลองใช้โมเดล Prophet

## ข้อมูลการแข่งขัน

ชุดข้อมูลจริงที่ได้รับจากบริษัทเป็นข้อมูลส่วนตัว จึงไม่นำมาเผยแพร่ใน repository นี้ ผู้ที่ต้องการทดลองสามารถใส่ข้อมูลตัวเลขของตนเองลงใน [`data/data_collection.csv`](data/data_collection.csv) ตามโครงสร้างที่อธิบายไว้ใน [`data/data_description.md`](data/data_description.md) ได้

ไฟล์ CSV ใช้คอลัมน์ `ID`, `column_1` ถึง `column_40` และ `sugar_price` โดยแต่ละแถวแทนข้อมูลหนึ่งวัน ค่าในคอลัมน์ต้องเป็นตัวเลข และควรมี header ตามตัวอย่างในไฟล์

> อย่านำข้อมูลของบริษัทหรือข้อมูลที่ไม่มีสิทธิ์เผยแพร่ใส่ใน repository นี้

## ทดลองใช้งาน

1. ใช้ Python และติดตั้งไลบรารีที่ต้องใช้:

   ```bash
   python -m pip install -r requirements.txt
   ```

2. เติมข้อมูลทดลองที่ได้รับอนุญาตให้เผยแพร่ใน `data/data_collection.csv` โดยคงชื่อและลำดับคอลัมน์ตามที่กำหนด
3. เปิด [`notebooks/prophet.ipynb`](notebooks/prophet.ipynb) แล้วรันเซลล์ตามลำดับจากโฟลเดอร์ repository หรือจาก `notebooks/` ได้
4. Notebook จะบันทึกผลเป็น `submission.csv` ใน working directory ที่ใช้เปิด Notebook

`data/sandbox_submission.csv` เป็นตัวอย่างโครงสร้างไฟล์ผลลัพธ์ (365 แถว; `ID`, `Prediction`) ไม่ใช่ผลพยากรณ์ที่รับรองความถูกต้อง หากนำไปใช้กับระบบส่งงาน ให้ตรวจข้อกำหนดของระบบนั้นอีกครั้ง

## ไฟล์ในโปรเจกต์

- [`data/data_collection.csv`](data/data_collection.csv) — แม่แบบข้อมูลสำหรับกรอกข้อมูลทดลอง
- [`data/data_description.md`](data/data_description.md) — รายละเอียดคอลัมน์และรูปแบบข้อมูล
- [`data/sandbox_submission.csv`](data/sandbox_submission.csv) — ตัวอย่างรูปแบบไฟล์ผลลัพธ์สำหรับส่งงาน
- [`notebooks/prophet.ipynb`](notebooks/prophet.ipynb) — notebook สำหรับทดลองพยากรณ์ราคาน้ำตาลด้วย Prophet
- [`MODEL_EXPLANATION.md`](MODEL_EXPLANATION.md) — คำอธิบายขั้นตอนการทำงาน การประเมินผล และข้อจำกัดของโมเดล
- [`requirements.txt`](requirements.txt) — ไลบรารี Python ที่ใช้ใน notebook
- [`.gitignore`](.gitignore) — ไฟล์และโฟลเดอร์ที่ไม่ควรเพิ่มเข้า Git
- [`LICENSE`](LICENSE) — MIT License สำหรับโค้ดและเอกสารใน repository; ไม่ครอบคลุมข้อมูลของบริษัทที่ไม่ได้เผยแพร่
