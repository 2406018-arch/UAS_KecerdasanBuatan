# LAPORAN UAS KECERDASAN BUATAN

## Prediksi Tingkat Obesitas Berdasarkan Pola Makan dan Aktivitas Fisik Menggunakan Algoritma Decision Tree dan K-Nearest Neighbors

### Identitas Kelompok

| No. | Nama | NIM |
|---:|---|---|
| 1 | **[Isi nama anggota 1]** | **[Isi NIM]** |
| 2 | **[Isi nama anggota 2 jika ada]** | **[Isi NIM]** |

**Program studi:** [Isi program studi]  
**Kelas:** [Isi kelas]  
**Mata kuliah:** Kecerdasan Buatan  

> **Catatan etis:** proyek ini dibuat untuk tujuan akademik. Model bukan alat
> diagnosis dan tidak boleh menggantikan penilaian tenaga kesehatan.

---

# 1. Judul Proyek

**Prediksi Tingkat Obesitas Berdasarkan Pola Makan dan Aktivitas Fisik
Menggunakan Algoritma Decision Tree dan K-Nearest Neighbors**

## 1.1 Domain Proyek

Proyek berada pada domain kesehatan dan analitik gaya hidup. Permasalahan
yang diselesaikan adalah klasifikasi multikelas untuk memperkirakan tingkat
berat badan seseorang berdasarkan data demografis, ukuran tubuh, kebiasaan
makan, aktivitas fisik, penggunaan teknologi, riwayat keluarga, serta moda
transportasi.

Obesitas merupakan masalah kesehatan yang kompleks karena dipengaruhi oleh
interaksi faktor biologis, pola makan, aktivitas fisik, lingkungan, dan
perilaku. Oleh sebab itu, analisis tidak cukup hanya melihat satu atribut.
Machine learning dapat digunakan untuk mempelajari pola dari sejumlah
atribut secara bersamaan dan menghasilkan prediksi kelas.

---

# 2. Business Understanding

## 2.1 Permasalahan Dunia Nyata

Pola makan tinggi kalori, rendahnya aktivitas fisik, penggunaan perangkat
teknologi dalam waktu lama, kebiasaan makan di antara waktu makan, serta
riwayat keluarga dapat berkaitan dengan tingkat berat badan. Dalam praktiknya,
pengamatan banyak faktor secara manual membutuhkan waktu dan berpotensi
menghasilkan penilaian yang tidak konsisten.

Proyek ini membangun model klasifikasi yang memetakan karakteristik individu
ke dalam tujuh kelas, mulai dari berat badan kurang sampai obesitas tipe III.
Model digunakan sebagai demonstrasi akademik untuk menunjukkan bagaimana
algoritma supervised learning mengolah data tabular.

## 2.2 Literature Review

Mendoza Palechor dan de la Hoz Manotas (2019) memperkenalkan dataset yang
digunakan dalam proyek ini. Dataset memiliki 2.111 observasi dan 17 atribut,
termasuk target tingkat obesitas. Penelitian tersebut juga menjelaskan bahwa
sebagian besar observasi dihasilkan secara sintetis menggunakan Weka dan
SMOTE, sedangkan sebagian lainnya dikumpulkan melalui platform web.

De-La-Hoz-Correa et al. (2019) mengembangkan perangkat estimasi tingkat
obesitas berbasis Decision Tree. Cañas Cervantes dan Martinez Palacio (2020)
membandingkan Decision Tree, SVM, dan K-Means dalam estimasi tingkat
obesitas. Ferdowsy et al. (2021) membandingkan beberapa algoritma, termasuk
KNN dan Decision Tree, untuk prediksi risiko obesitas.

Cheng et al. (2021) menunjukkan bahwa aktivitas fisik dapat dianalisis
bersama faktor lainnya menggunakan pendekatan statistik dan machine learning.
Quiroz (2022), Gozukara Bag et al. (2023), serta Görmez et al. (2025)
menunjukkan perkembangan pendekatan klasifikasi tingkat obesitas berdasarkan
kebiasaan makan dan kondisi fisik. Kajian DeGregory et al. (2018) juga
menjelaskan luasnya pemanfaatan machine learning dalam penelitian obesitas.

Literatur tersebut mendukung pemilihan Decision Tree karena dapat
menghasilkan aturan yang relatif mudah dipahami, serta KNN karena dapat
mengklasifikasikan observasi berdasarkan kedekatan karakteristiknya.

## 2.3 Tujuan Proyek

1. Memahami karakteristik dataset tingkat obesitas.
2. Membersihkan data dari duplikasi dan memeriksa missing value.
3. Menganalisis distribusi, korelasi, nilai ekstrem, dan keseimbangan kelas.
4. Mengubah fitur kategorik menjadi representasi numerik.
5. Menstandardisasi fitur numerik untuk kebutuhan KNN.
6. Membangun model Decision Tree dan K-Nearest Neighbors.
7. Membandingkan model menggunakan accuracy, precision, recall, F1-score,
   classification report, dan confusion matrix.
8. Menentukan model terbaik dan menjelaskan keterbatasannya.

## 2.4 Pengguna Sistem

Pengguna potensial dalam konteks akademik meliputi:

- mahasiswa yang mempelajari klasifikasi multikelas;
- dosen atau peneliti yang membutuhkan contoh penerapan supervised learning;
- analis data kesehatan;
- pengembang prototipe edukasi mengenai pola hidup dan tingkat berat badan.

## 2.5 Solusi dan Manfaat Implementasi AI

Solusi yang dikembangkan adalah pipeline machine learning yang menerima
atribut individu, melakukan encoding dan standardisasi secara otomatis, lalu
menghasilkan prediksi kelas tingkat obesitas.

Manfaat proyek meliputi:

- menunjukkan alur kerja machine learning secara lengkap;
- membandingkan dua algoritma dengan karakteristik berbeda;
- menyediakan visualisasi yang membantu memahami pola data;
- menghasilkan kode yang dapat dijalankan ulang di Google Colab;
- menjadi dasar pengembangan model yang lebih kuat.

---

# 3. Data Understanding

## 3.1 Sumber Data

Dataset yang digunakan adalah **Estimation of Obesity Levels Based on Eating
Habits and Physical Condition**. File proyek bernama:

```text
data/dataset/ObesityDataSet_raw_and_data_sinthetic.csv
```

Dataset asli dikembangkan dari responden di Meksiko, Peru, dan Kolombia.
Data terdiri atas pola makan, kondisi fisik, serta label tingkat obesitas.

## 3.2 Ukuran dan Format Data

| Keterangan | Nilai |
|---|---:|
| Jumlah baris awal | 2111 |
| Jumlah kolom | 17 |
| Jumlah fitur prediktor | 16 |
| Jumlah target | 1 |
| Missing value | 0 |
| Baris duplikat | 24 |
| Jumlah baris setelah pembersihan | 2087 |
| Format | CSV |

## 3.3 Deskripsi Atribut

| Atribut                        | Tipe      | Keterangan                                     |
|--------------------------------|-----------|------------------------------------------------|
| Age                            | Numerik   | Usia responden.                                |
| Gender                         | Kategorik | Jenis kelamin responden.                       |
| Height                         | Numerik   | Tinggi badan dalam meter.                      |
| Weight                         | Numerik   | Berat badan dalam kilogram.                    |
| CALC                           | Kategorik | Frekuensi konsumsi alkohol.                    |
| FAVC                           | Kategorik | Konsumsi makanan tinggi kalori.                |
| FCVC                           | Numerik   | Frekuensi konsumsi sayuran.                    |
| NCP                            | Numerik   | Jumlah makanan utama per hari.                 |
| SCC                            | Kategorik | Kebiasaan memantau konsumsi kalori.            |
| SMOKE                          | Kategorik | Status kebiasaan merokok.                      |
| CH2O                           | Numerik   | Konsumsi air harian.                           |
| family_history_with_overweight | Kategorik | Riwayat keluarga dengan kelebihan berat badan. |
| FAF                            | Numerik   | Frekuensi aktivitas fisik.                     |
| TUE                            | Numerik   | Waktu penggunaan perangkat teknologi.          |
| CAEC                           | Kategorik | Kebiasaan makan di antara waktu makan.         |
| MTRANS                         | Kategorik | Moda transportasi yang digunakan.              |
| NObeyesdad                     | Target    | Tujuh kelas tingkat berat badan dan obesitas.  |

## 3.4 Target Klasifikasi

Target `NObeyesdad` terdiri atas tujuh kelas:

| Kelas               | Jumlah | Persentase |
|---------------------|--------|------------|
| Insufficient_Weight | 267    | 12.79      |
| Normal_Weight       | 282    | 13.51      |
| Obesity_Type_I      | 351    | 16.82      |
| Obesity_Type_II     | 297    | 14.23      |
| Obesity_Type_III    | 324    | 15.52      |
| Overweight_Level_I  | 276    | 13.22      |
| Overweight_Level_II | 290    | 13.90      |

Terjemahan kelas:

| Label dataset | Arti |
|---|---|
| `Insufficient_Weight` | Berat badan kurang |
| `Normal_Weight` | Berat badan normal |
| `Overweight_Level_I` | Kelebihan berat badan tingkat I |
| `Overweight_Level_II` | Kelebihan berat badan tingkat II |
| `Obesity_Type_I` | Obesitas tipe I |
| `Obesity_Type_II` | Obesitas tipe II |
| `Obesity_Type_III` | Obesitas tipe III |

## 3.5 Tipe Permasalahan

Proyek merupakan **multiclass classification**, karena model memilih satu
dari tujuh kelas target.

## 3.6 Insight Awal Dataset

1. Dataset tidak memiliki missing value.
2. Terdapat 24 baris duplikat yang dihapus.
3. Terdapat delapan fitur numerik dan delapan fitur kategorik.
4. Rasio kelas terbesar terhadap kelas terkecil sebesar
   **1.31:1**, sehingga distribusi kelas relatif seimbang.
5. Beberapa nilai terdeteksi sebagai outlier menurut aturan IQR, tetapi tidak
   langsung dihapus karena dapat menjadi variasi yang masih masuk akal.

---

# 4. Exploratory Data Analysis (EDA)

## 4.1 Distribusi Kelas

![Distribusi kelas](assets/01_distribusi_kelas_bar.png)

Grafik menunjukkan bahwa setiap kelas memiliki jumlah data yang relatif
berdekatan. Kelas terbanyak adalah `Obesity_Type_I` sebanyak
351 data, sedangkan kelas paling sedikit adalah
`Insufficient_Weight` sebanyak 267 data.

![Persentase kelas](assets/02_distribusi_kelas_pie.png)

Karena tidak terdapat dominasi satu kelas yang sangat besar, proyek ini tidak
menerapkan oversampling tambahan. Pembagian train-test menggunakan
stratifikasi agar proporsi setiap kelas tetap terjaga.

## 4.2 Distribusi Usia dan Berat Badan

![Histogram usia](assets/03_histogram_usia.png)

Sebagian besar observasi berada pada kelompok usia dewasa muda. Terdapat
sejumlah observasi usia lebih tinggi yang terdeteksi sebagai nilai ekstrem
berdasarkan IQR.

![Histogram berat badan](assets/04_histogram_berat_badan.png)

Distribusi berat badan memperlihatkan variasi yang cukup luas. Variasi tersebut
penting karena target tingkat obesitas memiliki hubungan kuat dengan
karakteristik antropometrik.

## 4.3 Aktivitas Fisik

![Aktivitas fisik](assets/05_distribusi_aktivitas_fisik.png)

Fitur `FAF` menunjukkan frekuensi aktivitas fisik. Nilai yang lebih tinggi
merepresentasikan aktivitas yang lebih sering.

## 4.4 Boxplot Berat Badan

![Boxplot berat](assets/06_boxplot_berat_per_kelas.png)

Median berat badan cenderung meningkat dari kelas berat badan kurang menuju
obesitas tipe III. Pola ini menunjukkan bahwa berat badan menjadi fitur
pemisah yang sangat kuat.

## 4.5 Analisis Korelasi

![Heatmap korelasi](assets/07_heatmap_korelasi.png)

Korelasi dihitung hanya pada fitur numerik. `Weight` dan `Height` berhubungan
dengan ukuran tubuh, sedangkan `FAF`, `FCVC`, `CH2O`, `NCP`, dan `TUE`
merepresentasikan perilaku atau kondisi fisik. Korelasi tidak selalu
menunjukkan hubungan sebab akibat.

## 4.6 Hubungan Tinggi dan Berat Badan

![Scatter tinggi berat](assets/08_scatter_tinggi_berat.png)

Scatter plot menunjukkan bahwa kelas target membentuk kelompok yang cukup
jelas pada kombinasi tinggi dan berat badan. Hal ini membantu menjelaskan
mengapa Decision Tree dapat menghasilkan kinerja tinggi.

## 4.7 Konsumsi Makanan Tinggi Kalori

![FAVC](assets/09_favc_per_kelas.png)

Fitur `FAVC` membedakan individu yang sering mengonsumsi makanan tinggi
kalori dan yang tidak. Namun, satu faktor saja tidak cukup untuk menentukan
kelas karena target dipengaruhi oleh gabungan banyak atribut.

## 4.8 Deteksi Outlier

![Outlier IQR](assets/10_outlier_iqr.png)

Metode IQR mendeteksi **699 baris** yang memiliki setidaknya satu
nilai ekstrem. Nilai ekstrem paling banyak ditemukan pada `NCP` dan `Age`.
Outlier tidak dihapus secara otomatis karena:

- nilai dapat merepresentasikan perilaku nyata;
- dataset mengandung data sintetis yang telah melalui proses pembentukan;
- Decision Tree relatif tidak sensitif terhadap skala;
- KNN menggunakan standardisasi untuk menyamakan skala fitur.

## 4.9 Insight EDA

1. Distribusi kelas relatif seimbang.
2. Tinggi dan berat badan membentuk pola yang jelas terhadap kelas.
3. Kebiasaan makan dan aktivitas fisik menambah informasi perilaku.
4. KNN membutuhkan standardisasi karena fitur memiliki rentang berbeda.
5. Decision Tree berpotensi unggul karena hubungan target dengan beberapa
   fitur dapat dibentuk menjadi batas keputusan.

---

# 5. Data Preparation

## 5.1 Pembersihan Data

Tahapan yang dilakukan:

1. membaca dataset CSV;
2. memeriksa struktur dan tipe data;
3. memeriksa missing value;
4. mendeteksi 24 baris duplikat;
5. menghapus duplikasi;
6. menyimpan data bersih sebagai `data/processed/obesity_clean.csv`.

Dataset tidak memerlukan imputasi karena tidak memiliki missing value.

## 5.2 Encoding Data Kategorik

Fitur kategorik bersifat nominal sehingga digunakan **One-Hot Encoding**.
Teknik ini membuat kolom biner baru tanpa memberikan urutan palsu pada
kategori.

Fitur kategorik yang di-encoding:

```text
Gender, CALC, FAVC, SCC, SMOKE, family_history_with_overweight, CAEC, MTRANS
```

Target dikonversi menjadi bilangan menggunakan `LabelEncoder`. Pemetaan kelas
disimpan agar hasil prediksi dapat dikembalikan ke label aslinya.

## 5.3 Standardisasi Data Numerik

Decision Tree menggunakan fitur numerik asli karena algoritma pohon tidak
bergantung pada perhitungan jarak.

KNN menggunakan `StandardScaler` karena algoritma menghitung jarak
antarobservasi. Standardisasi mencegah fitur dengan skala besar mendominasi
perhitungan.

## 5.4 Split Data

Dataset dibagi menjadi:

| Bagian | Jumlah | Persentase |
|---|---:|---:|
| Data latih | 1669 | 80% |
| Data uji | 418 | 20% |

Pembagian menggunakan:

```python
train_test_split(
    X,
    y,
    test_size=0.20,
    random_state=42,
    stratify=y
)
```

Penggunaan `stratify=y` menjaga proporsi setiap kelas. Seluruh preprocessing
diletakkan di dalam `Pipeline` agar parameter hanya dipelajari dari data
latih dan mengurangi risiko data leakage.

---

# 6. Modeling

## 6.1 Decision Tree

Decision Tree membagi data melalui aturan berbentuk cabang. Algoritma dipilih
karena:

- mudah dijelaskan;
- dapat menangani hubungan nonlinear;
- tidak membutuhkan standardisasi;
- dapat menampilkan feature importance;
- dapat divisualisasikan.

Konfigurasi utama:

```python
DecisionTreeClassifier(
    max_depth=10,
    min_samples_split=4,
    class_weight="balanced",
    random_state=42
)
```

## 6.2 K-Nearest Neighbors

KNN memprediksi kelas berdasarkan tetangga terdekat. Algoritma dipilih karena:

- konsepnya sederhana;
- cocok untuk data berlabel;
- dapat menangkap kemiripan observasi;
- menjadi pembanding yang berbeda dari model berbasis pohon.

Konfigurasi utama:

```python
KNeighborsClassifier(
    n_neighbors=3,
    weights="distance",
    metric="minkowski",
    p=2
)
```

KNN ditempatkan setelah StandardScaler dan One-Hot Encoder dalam pipeline.

## 6.3 Implementasi Model

Kode lengkap tersedia di:

```text
UAS_Obesitas_Colab.ipynb
UAS_Obesitas_Colab.py
```

## 6.4 Visualisasi Decision Tree

![Decision Tree](assets/13_visualisasi_decision_tree.png)

Gambar menampilkan tiga tingkat awal pohon agar tetap terbaca. Model aktual
dapat memiliki cabang lebih dalam sampai batas `max_depth=10`.

## 6.5 Fitur Terpenting

![Feature importance](assets/14_feature_importance.png)

Sepuluh fitur teratas:

| Fitur                | Importance |
|----------------------|------------|
| num__Weight          | 0.4605     |
| num__Height          | 0.2323     |
| cat__Gender_Male     | 0.1551     |
| num__Age             | 0.0404     |
| num__FCVC            | 0.0250     |
| cat__FAVC_no         | 0.0226     |
| cat__CALC_no         | 0.0220     |
| cat__CAEC_Frequently | 0.0083     |
| num__NCP             | 0.0076     |
| cat__SMOKE_no        | 0.0042     |

Feature importance menjelaskan kontribusi fitur terhadap pemisahan pada
Decision Tree, tetapi tidak membuktikan hubungan sebab akibat.

---

# 7. Evaluation

## 7.1 Metrik Evaluasi

Metrik yang digunakan:

- **Accuracy:** proporsi seluruh prediksi yang benar.
- **Precision:** ketepatan prediksi setiap kelas.
- **Recall:** kemampuan menemukan data yang benar pada setiap kelas.
- **F1-score:** rata-rata harmonik precision dan recall.
- **Confusion matrix:** rincian prediksi benar dan salah antar kelas.

Karena target memiliki tujuh kelas, laporan menggunakan weighted average
agar setiap kelas berkontribusi sesuai jumlah datanya. F1-macro juga
disediakan untuk memberi bobot sama kepada seluruh kelas.

## 7.2 Hasil Perbandingan

| Model               | Accuracy | Precision | Recall | F1-score | F1-macro |
|---------------------|----------|-----------|--------|----------|----------|
| Decision Tree       | 0.9330   | 0.9344    | 0.9330 | 0.9334   | 0.9315   |
| K-Nearest Neighbors | 0.8493   | 0.8458    | 0.8493 | 0.8379   | 0.8310   |

![Perbandingan model](assets/12_perbandingan_model.png)

## 7.3 Confusion Matrix Decision Tree

![Confusion Matrix Decision Tree](assets/11_confusion_matrix_decision_tree.png)

Decision Tree memperoleh accuracy **93.30%** dan weighted
F1-score **93.34%**. Kesalahan paling banyak terjadi
pada kelas yang posisinya berdekatan, seperti normal dan overweight tingkat I.

## 7.4 Confusion Matrix KNN

![Confusion Matrix KNN](assets/11_confusion_matrix_knearest_neighbors.png)

KNN memperoleh accuracy **84.93%** dan weighted F1-score
**83.79%**. KNN dapat mengenali beberapa kelas dengan
baik, tetapi lebih sering tertukar pada wilayah kelas yang berdekatan.

## 7.5 Model Terbaik

Model terbaik berdasarkan weighted F1-score adalah **Decision Tree**.

Decision Tree unggul karena fitur antropometrik seperti berat dan tinggi
membentuk batas kelas yang cukup jelas. KNN lebih sensitif terhadap
kedekatan observasi dan jumlah dimensi setelah One-Hot Encoding.

## 7.6 Analisis Kritis

Hasil tinggi tidak boleh langsung dianggap sebagai bukti bahwa model siap
digunakan secara klinis. Target dataset berkaitan erat dengan tinggi dan
berat badan, sehingga kedua fitur tersebut memberikan informasi yang sangat
kuat. Selain itu, sebagian besar dataset merupakan data sintetis. Karena itu,
kinerja pada data uji internal dapat lebih tinggi dibandingkan kinerja pada
populasi nyata yang berbeda.

---

# 8. Kesimpulan dan Rekomendasi

## 8.1 Ringkasan Hasil

Proyek berhasil:

- menggunakan dataset dengan 2111 baris dan 17 kolom;
- menghapus 24 baris duplikat;
- melakukan EDA dan deteksi outlier;
- melakukan One-Hot Encoding;
- melakukan standardisasi untuk KNN;
- membangun Decision Tree dan KNN;
- mengevaluasi model menggunakan lima ukuran evaluasi;
- memilih Decision Tree sebagai model terbaik.

## 8.2 Apakah Tujuan Proyek Tercapai?

Tujuan proyek **tercapai dalam konteks akademik**. Sistem dapat memproses
dataset, membangun dua model, dan menghasilkan perbandingan terukur pada data
uji.

## 8.3 Kelebihan Model

- pipeline dapat dijalankan ulang;
- preprocessing terpisah sesuai kebutuhan algoritma;
- Decision Tree mudah divisualisasikan;
- evaluasi tidak hanya menggunakan accuracy;
- kelas relatif seimbang;
- kode dapat dijalankan di Google Colab.

## 8.4 Keterbatasan Model

1. Sebagian besar data dibentuk secara sintetis menggunakan Weka dan SMOTE.
2. Dataset hanya mewakili konteks responden tertentu.
3. Tinggi dan berat badan sangat dekat dengan definisi kelas target.
4. Model belum divalidasi pada dataset eksternal.
5. Hyperparameter tuning masih sederhana.
6. Outlier tidak diverifikasi oleh ahli kesehatan.
7. Model tidak dapat digunakan untuk diagnosis medis.

## 8.5 Rekomendasi

1. Menguji model tanpa fitur `Height` dan `Weight` untuk menilai kontribusi
   murni kebiasaan makan dan aktivitas fisik.
2. Menggunakan cross-validation.
3. Membandingkan Random Forest, SVM, Logistic Regression, dan XGBoost.
4. Melakukan GridSearchCV untuk optimasi parameter.
5. Menguji model pada data nyata dari populasi Indonesia.
6. Menambahkan interpretasi SHAP atau permutation importance.
7. Melibatkan ahli kesehatan dalam validasi fitur dan kesimpulan.

---

# 9. Referensi

1. Blüher, M. (2019). Obesity: Global epidemiology and pathogenesis. *Nature Reviews Endocrinology, 15*(5), 288–298. https://doi.org/10.1038/s41574-019-0176-8

2. Cañas Cervantes, R., & Martinez Palacio, U. (2020). Estimation of obesity levels based on computational intelligence. *Informatics in Medicine Unlocked, 21*, 100472. https://doi.org/10.1016/j.imu.2020.100472

3. Cheng, X., Lin, S.-Y., Liu, J., Liu, S., Zhang, J., Nie, P., Fuemmeler, B. F., Wang, Y., & Xue, H. (2021). Does physical activity predict obesity—A machine learning and statistical method-based analysis. *International Journal of Environmental Research and Public Health, 18*(8), 3966. https://doi.org/10.3390/ijerph18083966

4. De-La-Hoz-Correa, E., Mendoza-Palechor, F. E., De-La-Hoz-Manotas, A., Morales-Ortega, R. C., & Sarmiento-Hernández, B. A. (2019). Obesity level estimation software based on decision trees. *Journal of Computer Science, 15*(1), 67–77. https://doi.org/10.3844/jcssp.2019.67.77

5. DeGregory, K. W., Kuiper, P., DeSilvio, T., Pleuss, J. D., Miller, R., Roginski, J. W., Fisher, C. B., Harness, D., Viswanath, S., Heymsfield, S. B., Dungan, I., & Thomas, D. M. (2018). A review of machine learning in obesity. *Obesity Reviews, 19*(5), 668–685. https://doi.org/10.1111/obr.12667

6. Ferdowsy, F., Rahi, K. S. A., Jabiullah, M. I., & Habib, M. T. (2021). A machine learning approach for obesity risk prediction. *Current Research in Behavioral Sciences, 2*, 100053. https://doi.org/10.1016/j.crbeha.2021.100053

7. Gozukara Bag, H. G., Yagin, F. H., Gormez, Y., González, P. P., Colak, C., Gülü, M., Badicu, G., & Ardigò, L. P. (2023). Estimation of obesity levels through the proposed predictive approach based on physical activity and nutritional habits. *Diagnostics, 13*(18), 2949. https://doi.org/10.3390/diagnostics13182949

8. Görmez, Y., Yagin, F. H., Yagin, B., Aygun, Y., Boke, H., Badicu, G., De Sousa Fernandes, M. S., Alkhateeb, A., Al-Rawi, M. B. A., & Aghaei, M. (2025). Prediction of obesity levels based on physical activity and eating habits with a machine learning model integrated with explainable artificial intelligence. *Frontiers in Physiology, 16*, 1549306. https://doi.org/10.3389/fphys.2025.1549306

9. Kaur, R., Kumar, R., & Gupta, M. (2022). Predicting risk of obesity and meal planning to reduce the obese in adulthood using artificial intelligence. *Endocrine, 78*(3), 458–469. https://doi.org/10.1007/s12020-022-03215-4

10. Mendoza Palechor, F., & de la Hoz Manotas, A. (2019). Dataset for estimation of obesity levels based on eating habits and physical condition in individuals from Colombia, Peru and Mexico. *Data in Brief, 25*, 104344. https://doi.org/10.1016/j.dib.2019.104344

11. Quiroz, J. P. S. (2022). Estimation of obesity levels based on dietary habits and condition physical using computational intelligence. *Informatics in Medicine Unlocked, 29*, 100901. https://doi.org/10.1016/j.imu.2022.100901

12. Thamrin, S. A., Arsyad, D. S., Kuswanto, H., Lawi, A., & Nasir, S. (2021). Predicting obesity in adults using machine learning techniques: An analysis of Indonesian Basic Health Research 2018. *Frontiers in Nutrition, 8*, 669155. https://doi.org/10.3389/fnut.2021.669155

---

# 10. Lampiran

## 10.1 Struktur Folder

```text
UAS-Obesitas-DecisionTree-KNN/
├── README.md
├── Laporan_uas.md
├── UAS_Obesitas_Colab.ipynb
├── UAS_Obesitas_Colab.py
├── requirements.txt
├── PANDUAN_GITHUB_DAN_COLAB.md
├── data/
│   ├── dataset/
│   │   └── ObesityDataSet_raw_and_data_sinthetic.csv
│   ├── processed/
│   │   └── obesity_clean.csv
│   └── Jurnal/
│       └── Daftar_Referensi.md
├── assets/
├── models/
└── results/
```

## 10.2 Dataset

Dataset mentah tersedia pada folder `data/dataset`. Dataset hasil
pembersihan tersedia pada folder `data/processed`.

## 10.3 Grafik Tambahan

Seluruh grafik tersimpan di folder `assets`.

## 10.4 Hasil Evaluasi

Tabel metrik, classification report, confusion matrix, dan feature importance
tersimpan di folder `results`.

## 10.5 Model

Model yang sudah dilatih tersimpan di folder `models`.

## 10.6 Catatan Sebelum Dikumpulkan

- isi nama, NIM, program studi, dan kelas;
- jalankan seluruh cell notebook;
- pastikan seluruh gambar muncul di laporan;
- unggah repository sebagai **Public**;
- tempelkan tautan GitHub pada LMS.
