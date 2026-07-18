# 1. Judul Proyek

# Prediksi Tingkat Obesitas Berdasarkan Pola Makan dan Aktivitas Fisik Menggunakan Algoritma Decision Tree dan K-Nearest Neighbors

## Nama Kelompok

| No. | Nama | NIM |
|---:|---|---|
| 1 | **Hilma Putri Andriyani Lestari** | **2406018** |

**Kelas:** A

---

## Domain Proyek (Latar Belakang)

Obesitas merupakan kondisi kompleks yang dipengaruhi oleh interaksi antara
karakteristik fisik, pola makan, aktivitas fisik, riwayat keluarga, dan
kebiasaan hidup. Perubahan pola konsumsi, meningkatnya konsumsi makanan
tinggi kalori, rendahnya aktivitas fisik, serta bertambahnya waktu
penggunaan perangkat elektronik dapat berhubungan dengan meningkatnya
risiko kelebihan berat badan.

Penilaian tingkat berat badan secara sederhana umumnya menggunakan tinggi
dan berat badan. Namun, informasi tersebut belum menjelaskan kebiasaan dan
kondisi lain yang berkaitan dengan pola hidup seseorang. Dataset yang
digunakan dalam proyek ini menyediakan 16 fitur yang menggambarkan faktor
demografis, antropometrik, pola makan, aktivitas fisik, dan kebiasaan
sehari-hari.

Machine learning dapat digunakan untuk mempelajari pola pada data tersebut
dan mengelompokkan observasi ke dalam tujuh kelas tingkat berat badan.
Pendekatan ini tidak dimaksudkan menggantikan pemeriksaan tenaga kesehatan,
melainkan sebagai implementasi akademik klasifikasi multikelas.

Pada proyek ini digunakan dua algoritma, yaitu **Decision Tree** dan
**K-Nearest Neighbors**. Decision Tree dipilih karena menghasilkan aturan
keputusan yang relatif mudah dipahami dan dapat divisualisasikan. KNN
dipilih karena mampu menentukan kelas berdasarkan kedekatan karakteristik
antarobservasi.

Kedua algoritma dibandingkan menggunakan Accuracy, Precision, Recall,
F1-score, Classification Report, Confusion Matrix, dan 5-Fold
Cross-Validation. Hasil perbandingan digunakan untuk menentukan algoritma
yang memberikan performa terbaik pada dataset yang digunakan.

> **Catatan etis:** model ini hanya untuk keperluan akademik dan tidak dapat
> digunakan sebagai diagnosis atau pengganti konsultasi kesehatan.

---

# 2. Business Understanding

Business Understanding merupakan tahap awal untuk memahami permasalahan
dunia nyata, menentukan tujuan proyek, mengidentifikasi pengguna sistem,
serta merancang solusi yang sesuai.

## 2.1 Permasalahan Dunia Nyata

Tingkat berat badan tidak hanya berkaitan dengan tinggi dan berat badan,
tetapi juga berhubungan dengan pola makan, aktivitas fisik, riwayat
keluarga, konsumsi air, kebiasaan memantau kalori, penggunaan perangkat
elektronik, dan moda transportasi.

Apabila jumlah data besar, pengamatan seluruh faktor secara manual menjadi
tidak efisien. Machine learning dapat membantu mengidentifikasi pola dari
banyak fitur secara bersamaan dan menghasilkan klasifikasi secara
otomatis.

Permasalahan yang diselesaikan dalam proyek ini adalah:

> Bagaimana mengklasifikasikan tingkat berat badan dan obesitas berdasarkan
> pola makan, aktivitas fisik, karakteristik tubuh, dan kebiasaan hidup
> menggunakan Decision Tree dan K-Nearest Neighbors?

## 2.2 Literature Review

Mendoza Palechor dan de la Hoz Manotas (2019) menyediakan dataset tingkat
obesitas berdasarkan kebiasaan makan dan kondisi fisik individu dari
Kolombia, Peru, dan Meksiko. Dataset tersebut menjadi salah satu dataset
yang banyak digunakan dalam penelitian klasifikasi obesitas.

De-La-Hoz-Correa et al. (2019) menerapkan Decision Tree untuk membangun
perangkat lunak estimasi tingkat obesitas. Penelitian tersebut menunjukkan
bahwa model berbasis pohon dapat digunakan untuk membentuk aturan
klasifikasi yang mudah dipahami.

Cañas Cervantes dan Martinez Palacio (2020) menggunakan pendekatan
computational intelligence untuk mengestimasi tingkat obesitas dan
membandingkan beberapa teknik analisis. Quiroz (2022) juga menerapkan
algoritma machine learning pada data kebiasaan makan dan kondisi fisik
untuk melakukan klasifikasi tingkat obesitas.

Thamrin et al. (2021) menggunakan data Riset Kesehatan Dasar Indonesia
untuk memprediksi obesitas orang dewasa dengan teknik machine learning.
Penelitian tersebut menunjukkan bahwa machine learning dapat digunakan
untuk menganalisis faktor yang berkaitan dengan obesitas pada populasi
besar.

Gozukara Bag et al. (2023) mengembangkan pendekatan prediksi tingkat
obesitas berdasarkan aktivitas fisik dan kebiasaan nutrisi. Görmez et al.
(2025) melanjutkan pendekatan tersebut dengan mengintegrasikan machine
learning dan explainable artificial intelligence.

Berdasarkan penelitian terdahulu, Decision Tree dan KNN dipilih karena
mewakili dua pendekatan berbeda. Decision Tree membangun aturan bercabang,
sedangkan KNN menentukan kelas berdasarkan kedekatan data.

## 2.3 Tujuan Proyek

1. Memahami struktur dan karakteristik dataset.
2. Memeriksa missing value dan data duplikat.
3. Melakukan Exploratory Data Analysis.
4. Mendeteksi korelasi, distribusi kelas, dan nilai ekstrem.
5. Melakukan encoding fitur kategorik.
6. Melakukan standardisasi fitur numerik untuk KNN.
7. Membagi data menjadi data latih dan data uji.
8. Membangun model Decision Tree.
9. Membangun model K-Nearest Neighbors.
10. Membandingkan performa kedua model.
11. Menentukan model terbaik berdasarkan metrik evaluasi.
12. Menyediakan dasar bagi form skrining edukatif.

## 2.4 User/Pengguna Sistem

Sistem ditujukan kepada:

### 1. Mahasiswa

Mahasiswa dapat memanfaatkan proyek sebagai contoh penerapan supervised
learning pada data tabular.

### 2. Dosen

Dosen dapat menggunakan proyek sebagai bahan evaluasi pemahaman mahasiswa
mengenai EDA, preprocessing, klasifikasi, dan evaluasi model.

### 3. Peneliti dan Analis Data

Peneliti dapat menggunakan proyek sebagai eksperimen awal sebelum
mengembangkan model yang lebih kompleks.

### 4. Pengguna Umum

Pengguna umum dapat mencoba form sebagai skrining edukatif, dengan
pemahaman bahwa hasilnya bukan diagnosis medis.

## 2.5 Solusi dan Manfaat Implementasi AI

Solusi yang dikembangkan berupa pipeline machine learning yang:

- membaca dataset;
- membersihkan data duplikat;
- mengubah fitur kategorik menjadi numerik;
- menstandardisasi fitur KNN;
- melatih dua algoritma;
- mengevaluasi model;
- menghasilkan prediksi pada data baru.

Manfaat implementasi:

- mempercepat klasifikasi data;
- menyediakan perbandingan algoritma;
- membantu memahami pola data;
- menghasilkan visualisasi yang mudah dijelaskan;
- menyediakan kode yang dapat dijalankan ulang.

---

# 3. Data Understanding

Data Understanding bertujuan memahami sumber, ukuran, format, atribut, dan
target dataset.

## 3.1 Sumber Data

Dataset yang digunakan adalah:

**Estimation of Obesity Levels Based on Eating Habits and Physical
Condition**

File dataset:

```text
data/dataset/ObesityDataSet_raw_and_data_sinthetic.csv
```

Dataset berkaitan dengan individu dari Kolombia, Peru, dan Meksiko.
Sebagian data dikumpulkan melalui platform web, sedangkan sebagian lainnya
dibentuk secara sintetis. Kondisi tersebut harus dicantumkan sebagai
keterbatasan penelitian.

## 3.2 Ukuran dan Format Data

| Keterangan | Nilai |
|---|---:|
| Jumlah baris awal | 2111 |
| Jumlah kolom | 17 |
| Jumlah fitur | 16 |
| Jumlah target | 1 |
| Missing value | 0 |
| Data duplikat | 24 |
| Jumlah data bersih | 2087 |
| Format | CSV |

## 3.3 Deskripsi Atribut

| No. | Atribut                        | Tipe      | Keterangan                                     |
|-----|--------------------------------|-----------|------------------------------------------------|
| 1   | Gender                         | Kategorik | Jenis kelamin responden.                       |
| 2   | Age                            | Numerik   | Usia responden dalam tahun.                    |
| 3   | Height                         | Numerik   | Tinggi badan dalam meter.                      |
| 4   | Weight                         | Numerik   | Berat badan dalam kilogram.                    |
| 5   | family_history_with_overweight | Kategorik | Riwayat keluarga dengan kelebihan berat badan. |
| 6   | FAVC                           | Kategorik | Kebiasaan mengonsumsi makanan tinggi kalori.   |
| 7   | FCVC                           | Numerik   | Frekuensi konsumsi sayuran.                    |
| 8   | NCP                            | Numerik   | Jumlah makanan utama per hari.                 |
| 9   | CAEC                           | Kategorik | Kebiasaan makan di antara waktu makan.         |
| 10  | SMOKE                          | Kategorik | Kebiasaan merokok.                             |
| 11  | CH2O                           | Numerik   | Konsumsi air harian.                           |
| 12  | SCC                            | Kategorik | Kebiasaan memantau kalori.                     |
| 13  | FAF                            | Numerik   | Frekuensi aktivitas fisik.                     |
| 14  | TUE                            | Numerik   | Waktu penggunaan perangkat teknologi.          |
| 15  | CALC                           | Kategorik | Frekuensi konsumsi alkohol.                    |
| 16  | MTRANS                         | Kategorik | Moda transportasi utama.                       |
| 17  | NObeyesdad                     | Target    | Kelas tingkat berat badan dan obesitas.        |

## 3.4 Tipe Data dan Target Klasifikasi

Proyek merupakan **multiclass classification**, karena target memiliki
tujuh kelas.

| Kelas               | Jumlah | Persentase |
|---------------------|--------|------------|
| Insufficient_Weight | 267    | 12.79      |
| Normal_Weight       | 282    | 13.51      |
| Obesity_Type_I      | 351    | 16.82      |
| Obesity_Type_II     | 297    | 14.23      |
| Obesity_Type_III    | 324    | 15.52      |
| Overweight_Level_I  | 276    | 13.22      |
| Overweight_Level_II | 290    | 13.90      |

Arti kelas target:

| Label | Arti |
|---|---|
| `Insufficient_Weight` | Berat badan kurang |
| `Normal_Weight` | Berat badan normal |
| `Overweight_Level_I` | Kelebihan berat badan tingkat I |
| `Overweight_Level_II` | Kelebihan berat badan tingkat II |
| `Obesity_Type_I` | Obesitas tipe I |
| `Obesity_Type_II` | Obesitas tipe II |
| `Obesity_Type_III` | Obesitas tipe III |

## 3.5 Insight Awal Dataset

- Dataset tidak memiliki missing value.
- Terdapat 24 data duplikat.
- Terdapat 8 fitur numerik.
- Terdapat 8 fitur kategorik.
- Distribusi kelas relatif tidak timpang secara ekstrem.
- Tinggi dan berat badan memiliki hubungan kuat dengan target.
- Fitur aktivitas fisik dan pola makan memberikan informasi tambahan.

---

# 4. Exploratory Data Analysis (EDA)

EDA bertujuan memahami distribusi, hubungan antarfitur, nilai ekstrem, dan
pola awal sebelum proses modeling.

## 4.1 Distribusi Kelas

![Distribusi kelas] (<img width="1089" height="590" alt="Image" src="https://github.com/user-attachments/assets/af56251a-6315-43a9-a3ea-1900e6f11118" />)
Grafik menunjukkan jumlah observasi pada setiap kelas. Kelas terbanyak
adalah `Obesity_Type_I` sebanyak 351 data,
sedangkan kelas paling sedikit adalah `Insufficient_Weight` sebanyak
267 data.

Distribusi kelas relatif berdekatan sehingga tidak dilakukan oversampling.
Namun, proses evaluasi tetap menggunakan Precision, Recall, dan F1-score.

## 4.2 Persentase Kelas

![Persentase kelas] (<img width="791" height="674" alt="Image" src="https://github.com/user-attachments/assets/ca1ebadf-35f2-4945-b431-4d62eba4e913" />)

Diagram lingkaran memperlihatkan persentase tujuh kelas. Tidak terdapat
kelas tunggal yang mendominasi sebagian besar data.

## 4.3 Histogram Usia

![Histogram usia] (<img width="889" height="590" alt="Image" src="https://github.com/user-attachments/assets/e57ec743-78e3-4ebb-b6be-ec01559bee39" />)

Histogram membantu mengetahui rentang usia yang paling banyak muncul.
Sebagian besar data berada pada kelompok usia dewasa muda.

## 4.4 Histogram Berat Badan

![Histogram berat badan] (<img width="889" height="590" alt="Image" src="https://github.com/user-attachments/assets/6857c87d-e95f-43dd-822d-1edbc31c907a" />)

Berat badan memiliki variasi luas dan menjadi salah satu fitur penting
dalam membedakan kelas target.

## 4.5 Histogram Aktivitas Fisik

![Histogram aktivitas fisik] (<img width="889" height="590" alt="Image" src="https://github.com/user-attachments/assets/e233a9e9-10de-4b12-ba36-50c7e593f903" />)

Fitur `FAF` menggambarkan frekuensi aktivitas fisik. Nilai yang lebih tinggi
menunjukkan aktivitas yang lebih sering.

## 4.6 Boxplot Berat Badan per Kelas

<img width="1289" height="690" alt="Image" src="https://github.com/user-attachments/assets/5c7fb6a6-ac91-4ddd-8cbd-6f859872b06e" />

Median berat badan cenderung meningkat seiring meningkatnya kelas target.
Pola tersebut menunjukkan bahwa berat badan menjadi pemisah penting.

## 4.7 Heatmap Korelasi

![Heatmap korelasi] (<img width="950" height="790" alt="Image" src="https://github.com/user-attachments/assets/0d387156-2da9-4758-87dd-f9c16bf87ea8" />
)

Heatmap menunjukkan hubungan linear antarfitur numerik. Korelasi tidak
menunjukkan hubungan sebab akibat, tetapi membantu menemukan fitur yang
berhubungan.

## 4.8 Scatter Plot Tinggi dan Berat Badan

![Scatter tinggi berat] (<img width="988" height="690" alt="Image" src="https://github.com/user-attachments/assets/2914dcbd-7fdf-43cc-86ff-43cd31d26fa8" />)

Kombinasi tinggi dan berat badan membentuk kelompok yang cukup jelas
berdasarkan kelas target. Hal ini membantu menjelaskan mengapa model
Decision Tree memperoleh performa tinggi.

## 4.9 Insight Awal EDA

1. Distribusi kelas relatif seimbang.
2. Tinggi dan berat badan membentuk pola yang jelas terhadap target.
3. Aktivitas fisik dan kebiasaan makan memberikan informasi tambahan.
4. KNN memerlukan standardisasi karena rentang fitur berbeda.
5. Nilai ekstrem tidak selalu merupakan kesalahan pencatatan.
6. Model harus diuji menggunakan data yang tidak dipakai saat pelatihan.

---

# 5. Data Preparation

Data Preparation bertujuan menyiapkan data agar dapat digunakan oleh
Decision Tree dan KNN.

## 5.1 Data Cleaning

Pemeriksaan menghasilkan:

- missing value: 0;
- data duplikat: 24;
- data setelah pembersihan: 2087.

Data duplikat dihapus dengan:

```python
df = df_raw.drop_duplicates().reset_index(drop=True)
```

## 5.2 Label Encoding Target

Target `NObeyesdad` berbentuk teks. Target diubah menjadi angka menggunakan
`LabelEncoder`.

```python
label_encoder = LabelEncoder()
y = label_encoder.fit_transform(y_text)
```

Pemetaan kelas disimpan agar hasil prediksi dapat dikembalikan ke nama kelas
aslinya.

## 5.3 One-Hot Encoding Fitur Kategorik

Fitur kategorik bersifat nominal. One-Hot Encoding digunakan agar kategori
diubah menjadi kolom biner tanpa memberikan urutan palsu.

```python
OneHotEncoder(handle_unknown="ignore")
```

## 5.4 Standardisasi Data Numerik

Decision Tree tidak membutuhkan standardisasi karena pemisahan dilakukan
berdasarkan batas nilai.

KNN membutuhkan StandardScaler karena KNN menghitung jarak. Tanpa
standardisasi, fitur dengan rentang besar dapat mendominasi perhitungan.

## 5.5 Train-Test Split

Data dibagi menjadi:

| Bagian | Jumlah | Persentase |
|---|---:|---:|
| Data latih | 1669 | 80% |
| Data uji | 418 | 20% |

Kode:

```python
X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.20,
    random_state=42,
    stratify=y
)
```

`stratify=y` digunakan untuk menjaga proporsi kelas.

## 5.6 Pencegahan Data Leakage

Preprocessing dimasukkan ke dalam `Pipeline`. Encoder dan scaler hanya
dipelajari dari data latih sehingga mengurangi risiko data leakage.

---

# 6. Modeling

Tahap Modeling membangun dua algoritma klasifikasi.

## 6.1 Decision Tree

Decision Tree membagi data menjadi aturan bercabang.

Alasan pemilihan:

- mudah dipahami;
- mudah divisualisasikan;
- dapat menangkap hubungan nonlinear;
- tidak membutuhkan standardisasi;
- memiliki feature importance.

Parameter:

```python
DecisionTreeClassifier(
    max_depth=10,
    min_samples_split=4,
    class_weight="balanced",
    random_state=42
)
```

## 6.2 K-Nearest Neighbors

KNN menentukan kelas berdasarkan tetangga terdekat.

Alasan pemilihan:

- konsep sederhana;
- dapat menjadi pembanding model berbasis pohon;
- cocok untuk data numerik dan kategorik yang telah ditransformasi;
- dapat menangkap kedekatan pola antarobservasi.

Parameter:

```python
KNeighborsClassifier(
    n_neighbors=3,
    weights="distance",
    metric="minkowski",
    p=2
)
```

## 6.3 Implementasi Pipeline

```python
decision_tree = Pipeline([
    ("preprocessor", tree_preprocessor),
    ("classifier", DecisionTreeClassifier(...))
])

knn = Pipeline([
    ("preprocessor", knn_preprocessor),
    ("classifier", KNeighborsClassifier(...))
])
```

## 6.4 Visualisasi Decision Tree

![Decision Tree](assets/12_visualisasi_decision_tree.png)

Visualisasi hanya menampilkan tiga tingkat awal agar masih terbaca. Model
yang digunakan tetap memiliki struktur lengkap sampai batas kedalaman
maksimal.

## 6.5 Feature Importance

![Feature importance](assets/13_feature_importance.png)

Sepuluh fitur terpenting:

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

Feature importance menunjukkan kontribusi fitur dalam pemisahan Decision
Tree, bukan hubungan sebab akibat.

---

# 7. Evaluation

Evaluasi dilakukan menggunakan data uji yang tidak pernah digunakan saat
training.

## 7.1 Metrik Evaluasi

### Accuracy

Accuracy menunjukkan proporsi seluruh prediksi yang benar.

### Precision

Precision menunjukkan ketepatan prediksi pada suatu kelas.

### Recall

Recall menunjukkan kemampuan model menemukan seluruh anggota kelas.

### F1-score

F1-score merupakan rata-rata harmonik Precision dan Recall.

### Confusion Matrix

Confusion Matrix menunjukkan rincian prediksi benar dan salah antar kelas.

## 7.2 Hasil Perbandingan

| Model               | Accuracy | Precision | Recall | F1-score | F1-macro |
|---------------------|----------|-----------|--------|----------|----------|
| Decision Tree       | 0.9330   | 0.9344    | 0.9330 | 0.9334   | 0.9315   |
| K-Nearest Neighbors | 0.8493   | 0.8458    | 0.8493 | 0.8379   | 0.8310   |

![Perbandingan model](assets/11_perbandingan_model.png)

## 7.3 Evaluasi Decision Tree

Decision Tree memperoleh:

- Accuracy: **0.9330** atau **93.30%**
- Precision: **0.9344**
- Recall: **0.9330**
- F1-score: **0.9334** atau **93.34%**

![Confusion Matrix Decision Tree](assets/10_confusion_matrix_decision_tree.png)

Selisih accuracy data latih dan data uji adalah **0.0532** atau
**5.32%**. Selisih tersebut menunjukkan adanya perbedaan performa
train dan test, tetapi belum menunjukkan overfitting yang sangat besar pada
eksperimen ini.

## 7.4 Evaluasi KNN

KNN memperoleh:

- Accuracy: **0.8493** atau **84.93%**
- Precision: **0.8458**
- Recall: **0.8493**
- F1-score: **0.8379** atau **83.79%**

![Confusion Matrix KNN](assets/10_confusion_matrix_knearest_neighbors.png)

KNN menghasilkan performa yang lebih rendah dibandingkan Decision Tree.
Salah satu penyebabnya adalah meningkatnya jumlah dimensi setelah One-Hot
Encoding dan adanya kelas yang berdekatan.

## 7.5 Cross-Validation

| Model               | Accuracy_mean | Accuracy_std | Precision_mean | Recall_mean | F1_mean | F1_std |
|---------------------|---------------|--------------|----------------|-------------|---------|--------|
| Decision Tree       | 0.9253        | 0.0116       | 0.9267         | 0.9253      | 0.9254  | 0.0114 |
| K-Nearest Neighbors | 0.8548        | 0.0060       | 0.8550         | 0.8548      | 0.8429  | 0.0091 |

Cross-validation digunakan untuk menguji kestabilan model pada lima
pembagian data yang berbeda. Nilai standar deviasi yang relatif kecil
menunjukkan hasil model cukup konsisten.

## 7.6 Model Terbaik

Model terbaik berdasarkan weighted F1-score adalah:

> **Decision Tree**

Decision Tree memberikan performa lebih baik karena tinggi dan berat badan
membentuk batas kelas yang cukup jelas. Decision Tree juga lebih mudah
diinterpretasikan daripada KNN.

## 7.7 Analisis Kritis

Hasil tinggi tidak berarti model siap digunakan secara klinis. Tinggi dan
berat badan memiliki hubungan sangat dekat dengan kelas target. Selain itu,
sebagian dataset dibentuk secara sintetis.

Oleh karena itu:

- hasil hanya berlaku pada dataset dan konfigurasi penelitian;
- hasil belum tentu sama pada populasi Indonesia;
- skor model bukan probabilitas klinis;
- model bukan diagnosis;
- validasi eksternal masih diperlukan.

---

# 8. Kesimpulan dan Rekomendasi

## 8.1 Ringkasan Hasil Modeling dan Evaluasi

Proyek berhasil:

- membaca dataset dengan 2111 baris dan 17 kolom;
- menghapus 24 data duplikat;
- melakukan EDA;
- melakukan One-Hot Encoding;
- melakukan standardisasi untuk KNN;
- membangun Decision Tree dan KNN;
- menghitung Accuracy, Precision, Recall, dan F1-score;
- membuat Confusion Matrix;
- melakukan 5-Fold Cross-Validation;
- menentukan Decision Tree sebagai model terbaik.

## 8.2 Apakah Tujuan Proyek Tercapai?

Tujuan proyek **tercapai dalam konteks akademik**.

Model dapat memproses data, melatih dua algoritma, menghasilkan prediksi,
dan membandingkan performanya secara objektif menggunakan data uji.

## 8.3 Kelebihan Model

- menggunakan pipeline;
- dapat direproduksi;
- menggunakan dua algoritma;
- Decision Tree dapat divisualisasikan;
- menyediakan feature importance;
- menggunakan lebih dari satu metrik;
- menggunakan cross-validation;
- dapat digunakan sebagai dasar form interaktif.

## 8.4 Keterbatasan Model

- sebagian data merupakan data sintetis;
- data berasal dari konteks populasi tertentu;
- target berkaitan sangat kuat dengan tinggi dan berat badan;
- model belum diuji pada data eksternal;
- hyperparameter tuning masih terbatas;
- tidak ada validasi klinis;
- model tidak memprediksi kondisi masa depan secara pasti.

## 8.5 Rekomendasi Pengembangan

1. Menggunakan data nyata dari populasi Indonesia.
2. Menggunakan GridSearchCV untuk optimasi parameter.
3. Membandingkan Random Forest, SVM, Logistic Regression, dan XGBoost.
4. Menguji model tanpa fitur Height dan Weight.
5. Menggunakan SHAP atau permutation importance.
6. Melakukan validasi eksternal.
7. Melibatkan ahli kesehatan dalam interpretasi.
8. Mengembangkan aplikasi Streamlit atau Gradio.
9. Menambahkan validasi input pengguna.
10. Menjelaskan bahwa hasil bukan diagnosis medis.

---

# 9. Referensi

[1] H. G. Gozukara Bag, F. H. Yagin, Y. Gormez, P. P. González, C. Colak, M. Gülü, G. Badicu, and L. P. Ardigò, "Estimation of obesity levels through the proposed predictive approach based on physical activity and nutritional habits," Diagnostics, vol. 13, no. 18, p. 2949, 2023, doi: 10.3390/diagnostics13182949.
[2] M. Iqbal, Lisnawanty, W. S. Dharmawan, and R. Septian, "Prediction of obesity categories based on physical activity using machine learning algorithms," J. Comput. Netw. Archit. High Perform. Comput., vol. 6, no. 3, pp. 1025–1034, 2024, doi: 10.47709/cnahpc.v6i3.4053.
[3] A. Khikam, N. M. Anggadimas, and M. Udin, "Implementasi decision tree untuk klasikasi obesitas," JATI (Jurnal Mahasiswa Teknik Informatika), vol. 9, no. 3, pp. 3946–3952, 2025.
[4] A. I. Putri, N. A. Husna, N. M. Cia, M. A. Arba, N. R. Aisyi, C. H. Pramesthi, and A. S. Irdayusman, "Implementation of K-Nearest Neighbors, Naïve Bayes Classifier, Support Vector Machine and Decision Tree Algorithms for obesity risk prediction," Public Res. J. Eng. Data Technol. Comput. Sci., vol. 2, no. 1, pp. 26–33, 2024, doi: 10.57152/predatecs.v2i1.1110.
[5] S. A. Utiarahman and A. M. M. Pratama, "Analisis perbandingan KNN, SVM, decision tree dan regresi logistik untuk klasifikasi obesitas multi kelas," KLIK: Kajian Ilmiah Informatika dan Komputer, vol. 4, no. 6, pp. 3137–3146, 2024, doi: 10.30865/klik.v4i6.1871.

---

# 10. Lampiran

## Lampiran A. Dataset

Dataset mentah:

```text
data/dataset/ObesityDataSet_raw_and_data_sinthetic.csv
```

## Lampiran B. Notebook

Notebook Google Colab:

```text
UAS_Obesitas_Per_Note.ipynb
```

## Lampiran C. Kode Python

```text
untitled4_diperbaiki.py
```

## Lampiran D. Hasil EDA

Folder `assets` berisi:

- distribusi kelas;
- persentase kelas;
- histogram usia;
- histogram berat badan;
- histogram aktivitas fisik;
- boxplot;
- heatmap;
- scatter plot;
- grafik outlier.

## Lampiran E. Hasil Modeling

- visualisasi Decision Tree;
- feature importance;
- model comparison.

## Lampiran F. Hasil Evaluation

Folder `results` berisi:

- `model_comparison.csv`;
- `cross_validation_summary.csv`;
- classification report;
- `feature_importance.csv`.

## Lampiran G. Struktur Proyek

```text
UAS-KecerdasanBuatan/
├── README.md
├── Laporan_uas.md
├── UAS_Obesitas_Per_Note.ipynb
├── untitled4_diperbaiki.py
├── data/
│   └── dataset/
├── assets/
└── results/
```
