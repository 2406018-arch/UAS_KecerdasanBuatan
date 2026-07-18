# 🧠 Proyek UAS Kecerdasan Buatan

## Prediksi Tingkat Obesitas Berdasarkan Pola Makan dan Aktivitas Fisik Menggunakan Algoritma Decision Tree dan K-Nearest Neighbors

---

## 📖 Deskripsi Proyek

Proyek ini merupakan tugas akhir mata kuliah **Kecerdasan Buatan** yang
bertujuan membangun model klasifikasi tingkat berat badan dan obesitas
berdasarkan karakteristik fisik, pola makan, aktivitas fisik, riwayat
keluarga, serta kebiasaan sehari-hari.

Dua algoritma yang dibandingkan adalah:

1. **Decision Tree**, sebagai model berbasis aturan yang mudah
   divisualisasikan dan dijelaskan.
2. **K-Nearest Neighbors (KNN)**, sebagai model berbasis kedekatan atau
   kemiripan antarobservasi.

Model dievaluasi menggunakan **accuracy, precision, recall, F1-score,
classification report**, dan **confusion matrix**.

> **Catatan:** proyek ini dibuat untuk pembelajaran dan bukan alat diagnosis
> medis.

---

# 🎯 Tujuan Proyek

- Memahami karakteristik dataset tingkat obesitas.
- Membersihkan missing value dan data duplikat.
- Melakukan Exploratory Data Analysis.
- Melakukan One-Hot Encoding pada fitur kategorik.
- Melakukan standardisasi fitur numerik khusus untuk KNN.
- Membangun model Decision Tree dan KNN.
- Membandingkan performa kedua model.
- Menentukan model terbaik berdasarkan hasil evaluasi.
- Menyediakan dasar pengembangan form skrining edukatif.

---

# 📂 Dataset

Dataset yang digunakan adalah:

**Estimation of Obesity Levels Based on Eating Habits and Physical
Condition**

Nama file:

```text
ObesityDataSet_raw_and_data_sinthetic.csv
```

Ringkasan dataset:

| Keterangan | Nilai |
|---|---:|
| Jumlah data awal | 2111 |
| Jumlah kolom | 17 |
| Jumlah fitur prediktor | 16 |
| Missing value | 0 |
| Data duplikat | 24 |
| Data setelah pembersihan | 2087 |
| Jumlah kelas target | 7 |

Target klasifikasi berada pada kolom `NObeyesdad`.

---

# 🔄 Tahapan Pengerjaan

## 1️⃣ Data Understanding

- Membaca dataset CSV.
- Menampilkan lima data pertama.
- Memeriksa tipe data.
- Memeriksa missing value.
- Memeriksa data duplikat.
- Mendeskripsikan fitur dan target.

## 2️⃣ Exploratory Data Analysis

Visualisasi yang digunakan:

- distribusi kelas;
- persentase kelas;
- histogram usia;
- histogram berat badan;
- histogram aktivitas fisik;
- boxplot berat badan;
- heatmap korelasi;
- scatter plot tinggi dan berat badan;
- deteksi outlier dengan IQR.

## 3️⃣ Data Preparation

- Menghapus 24 baris duplikat.
- Melakukan Label Encoding pada target.
- Melakukan One-Hot Encoding pada fitur kategorik.
- Melakukan StandardScaler pada fitur numerik KNN.
- Membagi data menjadi 80% train dan 20% test.
- Menggunakan stratifikasi agar proporsi kelas terjaga.

## 4️⃣ Modeling

- Decision Tree.
- K-Nearest Neighbors.
- Pipeline preprocessing dan modeling.
- Visualisasi pohon keputusan.
- Feature importance.

## 5️⃣ Evaluation

- Accuracy.
- Precision.
- Recall.
- F1-score.
- F1-macro.
- Classification report.
- Confusion matrix.
- Stratified 5-Fold Cross-Validation.

---

# 🤖 Algoritma yang Digunakan

## Decision Tree

Parameter utama:

```python
DecisionTreeClassifier(
    max_depth=10,
    min_samples_split=4,
    class_weight="balanced",
    random_state=42
)
```

Decision Tree dipilih karena mudah dijelaskan dan dapat divisualisasikan
sebagai aturan bercabang.

## K-Nearest Neighbors

Parameter utama:

```python
KNeighborsClassifier(
    n_neighbors=3,
    weights="distance",
    metric="minkowski",
    p=2
)
```

KNN menggunakan StandardScaler karena algoritma menghitung jarak
antarobservasi.

---

# 📊 Hasil Evaluasi

| Model               | Accuracy | Precision | Recall | F1-score | F1-macro |
|---------------------|----------|-----------|--------|----------|----------|
| Decision Tree       | 0.9330   | 0.9344    | 0.9330 | 0.9334   | 0.9315   |
| K-Nearest Neighbors | 0.8493   | 0.8458    | 0.8493 | 0.8379   | 0.8310   |

Model terbaik berdasarkan weighted F1-score adalah **Decision Tree**.

Hasil 5-Fold Cross-Validation:

| Model               | Accuracy_mean | Accuracy_std | Precision_mean | Recall_mean | F1_mean | F1_std |
|---------------------|---------------|--------------|----------------|-------------|---------|--------|
| Decision Tree       | 0.9253        | 0.0116       | 0.9267         | 0.9253      | 0.9254  | 0.0114 |
| K-Nearest Neighbors | 0.8548        | 0.0060       | 0.8550         | 0.8548      | 0.8429  | 0.0091 |

---

# 📁 Struktur Repository

```text
UAS-KecerdasanBuatan/
├── README.md
├── Laporan_uas.md
├── UAS_Obesitas_Per_Note.ipynb
├── untitled4_diperbaiki.py
├── requirements.txt
├── data/
│   └── dataset/
│       └── ObesityDataSet_raw_and_data_sinthetic.csv
├── assets/
│   ├── 01_distribusi_kelas.png
│   ├── 02_persentase_kelas.png
│   ├── 03_histogram_usia.png
│   ├── 04_histogram_berat_badan.png
│   ├── 05_histogram_aktivitas_fisik.png
│   ├── 06_boxplot_berat_per_kelas.png
│   ├── 07_heatmap_korelasi.png
│   ├── 08_scatter_tinggi_berat.png
│   ├── 09_outlier_iqr.png
│   ├── 10_confusion_matrix_decision_tree.png
│   ├── 10_confusion_matrix_knearest_neighbors.png
│   ├── 11_perbandingan_model.png
│   ├── 12_visualisasi_decision_tree.png
│   └── 13_feature_importance.png
└── results/
    ├── model_comparison.csv
    ├── cross_validation_summary.csv
    └── feature_importance.csv
```

---

# ▶️ Cara Menjalankan Proyek di Google Colab

1. Buka Google Colab.
2. Pilih **File → Upload notebook**.
3. Unggah `UAS_Obesitas_Per_Note.ipynb`.
4. Pilih **Runtime → Run all**.
5. Unggah dataset apabila diminta.
6. Tunggu seluruh cell selesai dijalankan.
7. Periksa hasil grafik dan evaluasi model.

---

# 🛠 Library yang Digunakan

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-Learn
- Joblib
- IPyWidgets

---

# 👥 Anggota Kelompok

| No. | Nama | NIM |
|---:|---|---|
| 1 | **Hilma Putri Andriyani Lestari** | **2406018** |
| 2 | **-** | **2406018** |
