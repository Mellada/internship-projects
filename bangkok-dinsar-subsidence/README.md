# การวิเคราะห์การทรุดตัวของพื้นดินในกรุงเทพมหานครด้วย DInSAR และ Hexagonal Grid

โครงการนี้จัดทำขึ้นเพื่อศึกษาการทรุดตัวของพื้นดินในพื้นที่กรุงเทพมหานคร โดยใช้ข้อมูลเรดาร์ Sentinel-1 และเทคนิค Differential Interferometric Synthetic Aperture Radar (DInSAR) ประมวลผลผ่านโปรแกรม SNAP ก่อนนำผลลัพธ์มาวิเคราะห์ร่วมกับข้อมูลเชิงพื้นที่อื่น ๆ ภายใน Hexagonal Grid ขนาด 500 × 500 เมตร

ข้อมูลทั้งหมดถูกจัดให้อยู่ในหน่วยวิเคราะห์เดียวกัน เพื่อนำไปศึกษาความสัมพันธ์ระหว่างการทรุดตัวของพื้นดินกับปัจจัยด้านสิ่งแวดล้อมและการพัฒนาเมือง

---

## วัตถุประสงค์

- วิเคราะห์การทรุดตัวของพื้นดินในกรุงเทพมหานครด้วยเทคนิค DInSAR
- สร้างฐานข้อมูลเชิงพื้นที่แบบ Hexagonal Grid ขนาด 500 × 500 เมตร
- วิเคราะห์ความสัมพันธ์ระหว่างการทรุดตัวของพื้นดินกับตัวแปรเชิงพื้นที่
- สร้างแผนที่และผลการวิเคราะห์ทางสถิติสำหรับสนับสนุนการวางแผนเมือง

---

## ข้อมูลที่ใช้

### Sentinel-1 SAR

- Sentinel-1 IW SLC
- เทคนิค DInSAR
- โปรแกรม SNAP

### ตัวแปรที่ใช้วิเคราะห์

- Ground Subsidence (DInSAR)
- Land Surface Temperature (LST) ปี 2024
- Land Surface Temperature (LST) ปี 2025
- Nighttime Light (VIIRS)
- Population Density (WorldPop)

---

## ขั้นตอนการดำเนินงาน

### 1. ประมวลผล DInSAR

ดำเนินการผ่านโปรแกรม SNAP

Workflow

```
Read
    ↓
Snaphu Import
    ↓
Phase to Displacement
    ↓
Terrain Correction
    ↓
Write
```

ผลลัพธ์

- Ground Subsidence Raster

---

### 2. เตรียมข้อมูลเชิงพื้นที่

- ปรับระบบพิกัดข้อมูลทั้งหมดให้อยู่ในระบบเดียวกัน
- ตัดข้อมูลตามขอบเขตกรุงเทพมหานคร
- เตรียม Raster สำหรับการวิเคราะห์

---

### 3. สร้าง Hexagonal Grid

สร้าง Hexagonal Grid ขนาด

```
500 × 500 เมตร
```

เพื่อใช้เป็นหน่วยวิเคราะห์เชิงพื้นที่

---

### 4. สรุปค่าภายใน Hexagon

คำนวณค่าเฉลี่ยของตัวแปรแต่ละชนิด

- Subsidence
- LST 2024
- LST 2025
- Nighttime Light
- Population Density

---

### 5. วิเคราะห์ข้อมูล

ประกอบด้วย

- Pearson Correlation
- Ordinary Least Squares (OLS)
- Variance Inflation Factor (VIF)

---

## เครื่องมือที่ใช้

### โปรแกรม

- SNAP
- SNAPHU
- ArcGIS Pro
- Python
- Jupyter Notebook

### Python Libraries

- rasterio
- geopandas
- numpy
- pandas
- rasterstats
- matplotlib
- scipy
- statsmodels

---

## ผลลัพธ์


- Ground Subsidence Map
- Hexagonal Grid Dataset
- LST Maps
- Nighttime Light Map
- Population Density Map
- Correlation Analysis
- OLS Regression
- VIF Analysis

---
