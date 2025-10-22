# Analisis Data Kelulusan Mahasiswa

## 1. Dataset
Dataset awal berisi 10 baris dengan kolom:
- `IPK`: Indeks Prestasi Kumulatif
- `Jumlah_Absensi`: Total absensi
- `Waktu_Belajar_Jam`: Jam belajar per minggu
- `Lulus`: Target (1 = lulus, 0 = tidak lulus)

Dataset sudah dibersihkan dari duplikat dan missing value (diisi median untuk numerik, modus untuk kategorikal).  


## 2. Langkah Preprocessing
1. **Cek missing value** menggunakan `df.isnull().sum()`  
2. **Hapus duplikat** dengan `df.drop_duplicates()`  
3. **Tangani missing value**:  
   - Numerik → isi median  
   - Kategorikal → isi modus  
4. **Buat fitur turunan**:  
   - `Rasio_Absensi = Jumlah_Absensi / 14`  
   - `IPK_x_Study = IPK * Waktu_Belajar_Jam`  

Dataset hasil preprocessing disimpan sebagai `processed_kelulusan.csv`.

---

## 3. Train / Validation / Test Split
Dataset dibagi menjadi **70% Train, 15% Validation, 15% Test** tanpa stratify karena dataset sangat kecil.

- Train: 7 baris  
- Validation: 1–2 baris  
- Test: 1–2 baris  

File CSV: `train.csv`, `validation.csv`, `test.csv`

---

## 4. Analisis Data (EDA)
1. **Statistik deskriptif** menggunakan `df.describe()`  
2. **Visualisasi**:  
   - Histogram distribusi `IPK`  
   - Scatter plot `IPK` vs `Waktu_Belajar_Jam` dengan target `Lulus`  
   - Heatmap korelasi antar kolom numerik  
3. **Ringkasan distribusi target** per subset tersedia dalam tabel.

---

## 5. Catatan Hasil
- IPK rata-rata: ~3.2  
- Waktu belajar berkorelasi positif dengan IPK  
- Rasio absensi rendah cenderung lulus  

Dataset sudah siap untuk tahap modeling machine learning.# Pertemuan4_MachineLearning
