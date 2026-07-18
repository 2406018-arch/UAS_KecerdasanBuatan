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

![Distribusi kelas](data:image/png;base64,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f16PPPKI1q9fryVLlji/15v5nTz99NM6fPiwFi9efNVtP9fy008/6Z9//tFzzz133Z5P7du314QJEzR//nw98MADzvSdO3eqVatW6tq1qzp06KAJEybo0Ucf1YIFC1S7dm1Jl3o7Va1aVYcOHdLTTz+t/Pnza9WqVerXr5+OHDnijOexePFiPfbYY6pZs6b+97//SZK2bdumn3/+Wc8999w16/XKK68oIiLC61amTJkySZIiIyP16aef6rHHHlOXLl10+vRpjR8/XnXr1tUvv/zi3K72Xz4XAJAKGQAAqciECRNMkq1bt+66ZQIDA61s2bLO+0GDBtnlX4mjRo0ySXbixInrrmPdunUmySZMmHDVvKpVq5okGzdu3DXnVa1a1Xn/ww8/mCS76667LDIy0pk+a9Ysk2TvvfeeMy0kJMQ6dOjwr+t85JFH7N57771u3c3+7/e0Z8+eG5aL/92EhIRYQECArV69+prlatasaaVKlbILFy440+Li4uzBBx+0u++++6rt/eGHH5xp586du2p9w4YNM4/HY/v27TMzs3/++cck2dtvv33D+v6bBg0aWEhIyDXnXe9vU7x4cYuKinKmv/feeybJNm/ebGZmUVFRlj17ditfvrxFR0c75SZOnGiSrrnO2bNn2+nTp61q1aqWI0cO++2337zqcjO/EzOz7t27280ezr377rsmyebOnXvdMuHh4SbJmjVr5kwLCQkxSfbFF1840yIiIix37txe/49ee+01y5gxo+3YscNrnX379jVfX1/bv3+/mZk999xzFhAQYDExMdetx7XayfX+djExMV5/H7NL7SUoKMg6derkTLuZzwUApH7cDgMAcJ1MmTLd8CkxWbJkkSR9/fXXV3Xjv1n+/v7q2LHjTZdv3769MmfO7Lxv0aKFcufOre+++y7Bn50lSxYdPHhQ69atS/Cy13Ps2DFlypRJuXPnvmpeeHi4li1bppYtW+r06dM6efKkTp48qb///lt169bVzp07dejQoeuu+/KeLmfPntXJkyf14IMPysz022+/OWXSpk2r5cuX659//km07boZHTt29BrLJb7nz19//SVJWr9+vf7++2916dLFq4dFmzZtlDVr1muuMyIiQnXq1NGff/6p5cuXXzW47s38ThIqvs1f3s6uFD8vMjLSa3qePHm8evMEBASoffv2+u2333T06FFJl3qvPPTQQ8qaNavTBk6ePKlatWopNjZWK1eulHSpfZ49e1aLFy/+T9txJV9fX+fvExcXp/DwcMXExKhcuXJeTy5K7M8FANyZCEEAAK5z5syZG54ItmrVSpUqVdKTTz6poKAgtW7dWrNmzUpQIHLXXXclaBDUu+++2+u9x+NRkSJF/tN4Fy+//LIyZcqkChUq6O6771b37t2dW3n+q6lTpyo8PFy1a9fW8ePHvebt2rVLZqZXX31VOXPm9HoNGjRIkq5a5nL79+/XE088oWzZsilTpkzKmTOnqlatKulSWCBdCpX+97//6fvvv1dQUJCqVKmi4cOHOyfgSSl//vxe7+ODjfgwZt++fZKkIkWKeJXz8/O77m06zz//vNatW6clS5bo3nvvvWr+zfxOEiq+zd8oALxeUFKkSJGrxhspWrSoJDltdOfOnVqwYMFVbaBWrVqS/q8NPPPMMypatKjq1aunvHnzqlOnTlqwYMF/2qZ4kyZNUunSpZUuXTplz55dOXPm1Lfffuv1u0qKzwUA3HkIQQAArnLw4EFFRERcdcJ6ufTp02vlypVasmSJ2rVrp02bNqlVq1aqXbu2YmNjb+pzEjqOx8243qCXV9apePHi2r59uz7//HNVrlxZX3zxhSpXruwEEv9F1apVNWvWLO3Zs0d169b1OrmMD4defPFFLV68+Jqv6/2+Y2NjVbt2bX377bd6+eWX9dVXX2nx4sXOILOXB0/PP/+8duzYoWHDhildunR69dVXVbx48f/cM+JmXe8pOmb2n9f5yCOPyMz01ltvXRWuJeR3khDFixeXJG3atOm6ZeLnlShRIsHrj4uLU+3ata/bBpo3by5JypUrlzZu3KhvvvlGjRs31g8//KB69eqpQ4cO/2GrLgV0TzzxhAoXLqzx48drwYIFWrx4sWrUqOH1u0rszwUA3JkYGBUA4CrxA0jWrVv3huV8fHxUs2ZN1axZUyNHjtSbb76pV155RT/88INq1ap1w6dw/Bc7d+70em9m2rVrl0qXLu1My5o1q06dOnXVsvv27VOhQoW8pmXMmFGtWrVSq1atdPHiRTVr1kxvvPGG+vXr958fPdqoUSN99tln6tChgxo2bKhFixYpffr0zmenSZPGuep/szZv3qwdO3Zo0qRJat++vTP9ercsFC5cWC+88IJeeOEF7dy5U2XKlNGIESO8nvZzu4WEhEi61COmevXqzvSYmBjt3bvX628Yr0mTJqpTp46eeOIJZc6cWR9++KEzLyG/k4S0w/inHU2fPl2vvPLKNcOdyZMnS5IaNmzoNT2+t8/ln7djxw5Jcnq7FC5cWGfOnLmpNpA2bVo1atRIjRo1UlxcnJ555hl99NFHevXVV68bmF1vW+fMmaNChQrpyy+/9CpzrdDvv3wuACB1oScIAMA1li1bptdee00FCxZUmzZtrlsuPDz8qmnxYzZERUVJuhQySLpmKPFfTJ482es2hTlz5ujIkSOqV6+eM61w4cJas2aNLl686EybP3/+VY/S/fvvv73ep02bViVKlJCZKTo6+pbq2a5dO7377rv66aef1Lx5c0VHRytXrlyqVq2aPvroIx05cuSqZU6cOHHd9cWfiF/eq8LMrnps6blz53ThwgWvaYULF1bmzJmdv0lyKVeunLJnz65PPvlEMTExzvRp06bdcPyS9u3ba/To0Ro3bpxefvllZ/rN/k6khLXDDBky6MUXX9T27dv1yiuvXDX/22+/1cSJE1W3bl2vJ8NI0uHDhzV37lznfWRkpCZPnqwyZcooODhYktSyZUutXr1aCxcuvGrdp06dcn43V7ZPHx8fJyi60d8yY8aM17wV6Fq/r7Vr12r16tVe5f7r5wIAUhd6ggAAUqXvv/9ef/75p2JiYnTs2DEtW7ZMixcvVkhIiL755psb9oYYOnSoVq5cqQYNGigkJETHjx/XBx98oLx586py5cqSLp2AZ8mSRePGjVPmzJmVMWNGVaxYUQULFvxP9c2WLZsqV66sjh076tixY3r33XdVpEgRr8f4Pvnkk5ozZ44efvhhtWzZUrt379bUqVNVuHBhr3XVqVNHwcHBqlSpkoKCgrRt2za9//77atCgwQ3HQrlZzz77rMLDwzVkyBC1b99e06ZN09ixY1W5cmWVKlVKXbp0UaFChXTs2DGtXr1aBw8e1O+//37NdRUrVkyFCxfWiy++qEOHDikgIEBffPHFVeHBjh07VLNmTbVs2VIlSpSQn5+f5s6dq2PHjql169a3vE23Im3atBo8eLB69uypGjVqqGXLltq7d68mTpyowoUL37C3Ro8ePRQZGalXXnlFgYGB6t+//03/TiQpNDRU0qW/Sd26deXr63vD30ffvn3122+/6X//+59Wr16t5s2bK3369Prpp580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9+6177//3rZu3Wpnz541M7N+/fpZ4cKF7auvvjKzS7dLFSpUyIoVK2adO3e20qVL24MPPmiRkZFWoEABe/XVV5NlO3B7XH6VbP/+/V7zIiIi7L777rM+ffqYmdnJkyctJCTEHn/8cTt37pxTbt++fZY+fXpbsmTJVesn/HA3ehAhoehBhFt15X5iwoQJTu/W+F5Cx44ds/r169vQoUOdi4/nzp2zpUuX2ieffGIjRoxwLjBea51I3ehBlDoRgqQQV54cxP+Hix/xvHjx4hYWFma5cuWyt99+286ePWtr16616tWrW7NmzZzlli5dasOGDbNnn33W1q9fb2Zm77//voWFhVlERMTt2yAkqyvb05tvvmlBQUF23333WYkSJaxevXrOvBo1aljt2rWd22AOHTpkzz33nD322GP2wgsvmJlZeHi4FSpUyL788svbtxG4beLi4pw2c+bMGXvooYfs+eef9wo3YmJirGXLlta9e3dn2vfff28+Pj72v//9z/bs2WNmZiNGjLC77777qhAFqRs9iJCU6EGEhIqLi7vq5DV+HzJ16lR7+OGHLX/+/LZ69WozM3v++eetUqVKV5W9HLeSuxc9iFIfQpAU5NSpU9a8eXP766+/zOzSldaaNWtat27dnDKPPvqo5cyZ03744QczM/v444+tZMmS9vbbb1+1vpiYGPv+++8tT5481rdvXw4gXWLu3Lk2ceJE5/2nn35qBQsWtO+//97MzH7//XfzeDw2cOBAMzPbsmWL5c+f31566SU7dOjQVeuLioqybt26WenSpZ0TGaQel1+F+Oqrryxz5szWuHFjO378uO3fv9/roO+zzz6z7Nmze92m16dPH/N4PFasWDFr27atZc6c2T777LPbug1IXvQgQlKiBxFuxaZNm6xevXrWokULa9asmbOPOnPmjLVo0cLuu+8+69+/v23YsMHy5s3rjCdzJfZD7kIPotSPECQFWblypeXPn98ZMGf79u1WpkwZCw8Pt7i4OOvWrZsFBATYmDFjnGVOnjxpL7zwgmXLls3ZccfFxdn27dutRYsWljVrVhs+fHhybA6SSbFixaxJkyZmdinAaNKkiXN/4tq1a61kyZJWvnx5Z5Ams0u9hXLkyGHjxo1zvuiPHDlin3zyiZUsWdKKFy/u7PSRelx+8hp/hX7cuHFmZtauXTsrVKiQ1y1QW7ZssVKlStm3337rTDt79qxVr17dSpcubT/99JPXbXccNKZu9CDCraIHEZLS1KlTLXPmzPb000/b5MmTrWbNmhYaGur1hLsPPvjAihcvbvnz57ccOXLYjBkzkrHGSG70IHIPQpBkcr3/JFWqVLGWLVua2aVH3+bLl8/Wr19vxYsXtwoVKjiPVLpw4YLz85o1a2zkyJFeV2djYmJs/vz5tnv37tuwNUgOVybK8X//6dOnW9q0aZ2DwkceecQ++OADe/vtty1TpkzWp08fZ5C4y59D3rp1a1u0aJHXOhcuXOj1PHOkPmvWrLE8efJYgQIF7K677nKu2J84ccJGjx5td911l7Vu3doZj+juu++2yZMnm9n/tbn169dbmjRpnMdMcuKR+tGDCLeKHkRIak2bNnWe3mFm1qFDB8uePbstWbLEax928OBBq1SpkuXJk8c2b96cHFVFCkMPotSPECQZLV682N577z0LDw93ps2aNct8fX1tz549Fh0dbaGhoebxeGzw4MFejyedPn26PfPMM1eN80FXK/f59NNPnYFOzcx27NhhZcuWdcbz6NSpk+XKlctCQkJs5cqVTrmTJ09au3btnEcDXr6jjv+ZnXfq9u6775rH47GhQ4daVFSUffrpp5Y5c2abN2+emV36+//xxx9Wu3Ztu/fee23atGnWoUMHq1OnjrOO+DYyfPhwy5Qpk3N1BKkXPYhwK+hBhMRwrUEmL5/3119/WfHixe3s2bO2YcMGK1SokNfjk+PD+vj1HDt27LqPYYa70IPIHQhBkkl4eLgVLVrUfH19rW3bts7048ePW6lSpaxnz55mdukkJU+ePDZr1iwzu7TTXrJkiZUsWdJ69erlFYxw4OgusbGxNmDAAPN4PNazZ0+nF8f58+etbdu2VqdOHTt//rytXLnScufObS+++KKzbFRUlPXu3dtCQ0OdK/y0H/fZuXOn/fzzz877AwcO2BNPPGEhISFej2s7dOiQTZgwwQIDA61gwYJ233332YEDB65aX5kyZZzwDakbPYjwX9CDCIlp1apVzs9XBiExMTFWqFAhq1WrlgUGBnr1gj1w4ICNHz/ejh07dtU6uXUB9CByB0KQ2+BaB3UXLlywPn36WPv27e2ee+6xNm3aOKOVP/vss1atWjU7cuSIHTp0yHr16mVp0qSx8uXLOyOeDxo06DZvBZLbtXr5fP311+bxeOzFF1+0Bg0a2HfffWdml+6T9vf3t7Vr15qZ2csvv2ylS5e2e+65x7p3725lypSxwoULX7f7HlK/611FW7dund1333326KOPXjV/2bJl1rlzZ0uTJo1t3779qmUjIyOTutpIAehBhP+CHkRITLt377agoCDr0KHDNedHR0fb0KFDLXPmzFfd1jtp0iSrWbOm1y3BcAd6ECEeIchtFP9El3hTpkyxqlWr2oEDB6xp06bWoUMHW716ta1fv94yZMjgdevC3LlzbfTo0fb66697pY0k1u7y999/28mTJ72mValSxXr16mUTJ060gIAAW758uUVFRVmVKlWsefPmZnZpp71+/Xrr2bOn9e3b14YOHeoszy1UMPu/A4Po6GibNm2aZcmSxcaPH29mZhcvXnTKhYeHW1hYGEGsi9GDCP8VPYiQWM6dO2cffvihZcuWzb755hszu/qY+KeffrLq1atbmTJlbNmyZfbzzz9bnz59LCAgwD788MPkqDZSAHoQwYwQ5Lb54IMPLHv27NajRw+v6YUKFbJx48bZP//8Y0OGDLECBQrY1q1b7YEHHrB27dpdd3186bvPyZMnLVOmTNauXTsnkb548aKNHTvWaSuDBg2yBg0a2LBhw2zEiBFWoUIF52DyWkivcS3xT50KCgpy7rWPbyuxsbFWr149e+2118yMq69uQw8i/Ff0IEJiO3LkiD355JOWL18+Zz8SExPjtZ/auHGj1axZ0+666y6777777P7777d169Y58/kOcxd6ECEeIchtcuzYMfv4448tXbp09uyzzzr/gT755BOrX7++c3W/f//+ds8991jdunUtV65ctmXLFjO79qCVcI/4v/lnn31mlStXtnLlyjkDwy1YsMCqVavm3E710UcfWfPmza1YsWL24IMP2qRJk264TqRu//XqRHwYW6pUKa/pUVFRljdvXq/eRHAvehDhZtGDCElh/fr1dv/991uzZs1uWC4iIsL++OMP5/2VYQncgR5EiEcIcpvNmTPHgoODrUWLFrZz507bunWrNWrUyFasWOGUGTZsmBUtWtQ8Ho9zhQSIt3jxYnvooYesQIECtmbNGjMze+ihh5xuxWfPnrXNmzdbkSJFzOPxWMeOHbnlBc4V+JsVFxdnX3/9tfOFHxcXZ9HR0fbWW29Z69ataVO4Cj2IcD30IEJSiY6OthkzZljW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hQvrnXfe0cSJE50r9jcKNWJiYrzuczUz7ntNxVasWKHevXs7J6UtWrRQpkyZNGHCBLVv314LFy509kE9evTQtGnTVLx4cb388stasWKFvv32W/3zzz9eV119fHy0bNkyFSpUSMeOHdOqVavUuXPn5NxMJLHffvtN7du3d95/+umn+vPPP5U7d261adNGb731lnbt2qWcOXOqSZMmmjlzpqSrDwgv3//MmDFDQUFBmjFjxg3HNMKdizGIkBgOHDigtm3bavr06ZKktGnT6sSJExo1apSmTp2qiIgI1a9fX6NHj1bWrFk1ZMgQHT58WJJ3G4w/Nrr8av1rr72mpk2b6uDBg7d5q5Ac4tvD+fPnJUn+/v76888/1a9fP7344oteZW60jsDAQN1///2S5NxOg9SPs6UEiL9q6uvr6/yn8vPz09tvv62ZM2eqaNGieu655xQbGys/P7/r3o92+YHj3LlztXfvXq64usjlj9dat26dxo0bp4ULF+r06dPy9fVVvXr11K1bN3Xp0kXh4eHy8fG5aiceFxfnXME3M/3www+SGP8jtQsNDdXWrVtVuHBhRUdH6+zZs7r33ntVvXp1bdu2TWfOnJH0fycWQUFB+vLLL/X4448rQ4YMOnfunObPny/p/9rKtGnTVKtWLT311FNavHix7r777uTZOCQpehDhVtGDCInB19dXf/75p+bNm6ddu3Zp7dq1KliwoGbNmqWOHTuqW7du+vHHHyVJc+bM0aJFizRt2jSdP3/eOW6S/i908/X11YkTJ1SjRg2NHz9ezz33nAoXLpxs24ekRQ8iJBrDTYmJiXF+XrRokYWGhlqDBg3shRdecKZPmzbNypQpY3379r3msjExMRYbG2tmZrGxsdaqVSsLDAy0xYsX34YtQErz3HPPWY4cOax8+fJWtGhRe+CBB5z2ceDAAStdurTVr1//quUub4vLli2znDlzWu/eve38+fO3re5IXnPnzrXKlSs777/++msrV66c9ezZ05kWGxtrcXFxzvvw8HArVaqUvfjii2b2f+3o6NGj9uuvv96mmiM5LF++3AoVKmS7du0yM7MzZ85YaGioeTwe69at21Xljx49ak2bNrW6detaWFiYZcyY0fbt22dm5tWmli5daiEhIVa9enXbsWPH7dkYJJtff/3V2rZt67z/5JNP7LPPPrOnn37a0qdPb8OGDbOdO3eamVnHjh2tadOm11xPdHS08/P06dPNx8fHnn32Wa+2hdQp/nvn22+/tbJly9rgwYPtueees3HjxpnZpePrypUrW/v27Z19zrBhwyxjxow2aNAga9eunfn5+dmmTZucdU6ZMsWyZctmrVq1suPHj9/+jcJtsX//fmvTpo1NnTrVmXb8+HEbOXKkTZkyxU6dOuVMv+eee+zhhx+2Q4cOmZn391b8cfblx9JDhw61atWqOd+RcAdCkATavHmz5cmTx/r162fdunWzzJkzOyceERERNmTIECtRooR99dVXZmY2YsQImzt3rl28eNFZx9KlSy1fvnxWo0YN54AB7nH+/Hl76aWXrGzZsrZhwwYzM9u6dat5PB7r1auXs2NeunSpZcqUycaMGWNml3bYl++0n3/+eQsMDLShQ4d6TUfqEv+FfblvvvnGsmXLZv379zczs9OnT9tbb71l99xzj82ePdspFx0d7dU23nnnHStSpEjSVxopyunTp+3ChQtmZnbx4kU7duyYtW/f3mrUqGHVqlWz06dPm5n3yamZ2aRJk6xmzZrm8Xhs7NixXvOmTp1qHo/H3njjDfY/qVj8sYyZ2cSJE+2ee+6xTp06WcaMGa1OnTp29uxZMzMbM2aM1axZ04oVK2YbN260vn37WsuWLS0yMtI5AYmLi/O6ENS6dWvLkSOHffrpp7d/w3DbXfld1qdPHytZsqQVLVrUdu/e7Uz/+OOPrWLFijZo0CBn2vPPP2/169e3WrVq2f79+83sUntq3ry55cqVizbkAocOHbLQ0FBr1aqV7dy509asWWMZM2a0Bx54wPz8/Oyxxx6zlStXmtmlczUfHx8bPny4nTt3zszMfvnll6vWefz4catevbqFhITY3Llzb+fmIAUgBLlJ4eHh9uCDD1qfPn1s9OjRZnbpgPGLL74wX19f58Rj27Zt1qFDB8uSJYuVLVvWsmTJYn/++aeznvgT19dff50DR5e48os/MjLShg0b5uyQv/32W8uXL5+VLVvWPB6PTZo0ycwuta9+/fqZx+OxkydPOstv2bLFSpcubaVLl7ZVq1bdvg3BbXf5PuLrr7+2jz/+2DmhHTlypGXOnNlWrFhhZpf2PZ06dbJSpUrZ1q1bbd68efbII4947X+GDRtmjRs3dg4K4C70IEJC0IMIiSEuLs7r779mzRozuxTONm3a1HLmzOmcvMbr3r27Va1a1Tm2jomJsX/++cerzL59++yxxx6jDbkAPYiQFAhBruPKE9cTJ05YnTp1zOPx2LRp07zKPfPMM5YrVy47evSomV06EJgwYYK99957TrkzZ87Y448/boUKFbLVq1ffno1Asrq8DV15hfWvv/4ys0tXPPLnz2//+9//LC4uzlq3bm1FihRxTlzDw8Od3iJmZnPmzLHAwEB75plnnKu3SN3i4uLs0UcftRw5ctirr77qHPDt3bvXWrZsaUWLFnUOMFesWGE1a9a03LlzW2BgoI0cOdJZz5YtW8zj8djrr7+eLNuB24seRLhV9CDCrbr8b3zq1Cl78803rUyZMrZx40YzM/v555+tbNmy1r17d68T0d27d1vdunWtWrVqtmfPnqvWea39G1InehAhqRCCXOHy/2xRUVFe4yxs2rTJcufObT169PAqe+LECStTpow1btz4uuu8cOGCrVmzxs6cOZOEtUdKNG3aNGvcuLG9+OKLXoFGVFSUNWzY0AYNGuRcfW3durV5PB6rXLmy14Fl/Enu6tWrbcmSJbd9G5A8zp8/by1btrSwsDA7ePDgVScbq1atsrvvvts6duxoZpfayenTp23evHlOKBsvOjqaK/cuQQ8iJCZ6ECGhrjxxHTZsmLVt29bpIdS1a1cnYBs+fLjdf//9Ti/reDNmzLhqGtyDHkRIaoQg1zFlyhSrUqWKValSxfr27et8aX/yySfm8Xhs2bJlZvZ/J6c//PCDeTyeq05QGejLXa48EJwwYYIFBQVZr1697K677rK6devad999Z2ZmR44csbRp0zqDPJ06dcqefPJJ+/rrr23GjBnJUn8kryv3F0eOHLFKlSo5X+g7d+60zZs32/Tp053eROPHj7esWbPalClTrlpfTEwM+yCXogcR/gt6EOG/+u2332zAgAHO+/gxYPr06WO5cuWyL774wr755htr2rSpFSpUyN555x2n7GOPPWZ16tS57oMC+B5zF3oQ4XZwdQhy+PBh596xy/Xp08eyZs1qo0aNsk8++cRatGhhJUqUsN27d1tMTIy1a9fO8uXLd9XTODZv3ny7qo4U6PKd67Fjx8zMbMCAAc5gS7///rs1btzYGjZs6Nxj/cQTT1jatGntySeftJCQEKtTpw5PeXGhy7/w46+OmZmdPXvWcuTIYR06dLBWrVpZo0aN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o0OHDigoKEBkZCQCAgI03TxqZh4+fAgHBweYm5sjNjYWFhYWAJ4tnbtmzRocOnSowQtpIm3RpEEQhUIBb29v3L59G//5z3/Qrl07AC9fu5yIiIiIiJ65dOkSDh8+jOrqaqhUKvj4+MDMzAzAs4dbIrWMjAxMmjQJn376KRYtWgRHR0colUrs27cPixYtQlBQEBYtWsRnMdI6TRoEAYBbt27h0aNH6NWrFwAGQIiIiIiI3pRKpeIqivRKzCAielGTB0HUGK0mIiIiInpzfJlIvwUziIga0lgQhIiIiIiIiJoeM4hImzEIQkREREREpCWYQUTajrlPREREREREWoIBENJ2DIIQERERERERkVZgEISIiIiIiIiItAKDIERERERERESkFRgEISIiIiIiIiKtwCAIEREREREREWkFBkGIiIiIiIiISCswCEJEREREREREWoFBECIiInrrSZKErKwsTTeDiIiINIxBECIiImr2pk6dik8++aRBWVpaGvT19REdHa2ZRhEREVGLo6fpBhARERG9rvj4eAQEBCA2NhbTpk3TdHOIiIiohWAmCBEREbUoUVFRCAoKQkpKihwA2bdvHxwcHKCvrw8LCwusXr0aSqXylXWEhITA0tISBgYGsLCwQFhYGBQKhbz9xx9/xIgRI2BoaAgjIyM4Ojri9OnTjX5sRERE1LiYCUJEREQtRkhICL788kscOHAArq6uAICjR4/Cz88PW7duhbOzM65cuYJZs2YBAFauXPnSegwNDZGYmIiuXbvi3LlzmDlzJgwNDbFkyRIAgK+vL/r3748dO3ZAV1cXRUVFaNWqVdMcJBERETUaSQghNN0IIiIiol8zdepU/Otf/0JtbS1ycnIwcuRIeZubmxtcXV0RGhoql+3ZswdLlixBWVkZgKcTo2ZmZr4wr4jaxo0bkZKSImd7GBkZYdu2bfjss88a76CIiIioyTEThIiIiFoEOzs7VFRUYOXKlRg0aBDatWsH4OnQlePHj2PdunXyviqVCjU1NXj06BEMDAxeqCs1NRVbt27FlStXUF1dDaVSCSMjI3n7woULMWPGDCQnJ8PNzQ2TJk1Cr169Gv8giYiIqFFxThAiIiJqEczMzJCXl4ebN2/Cw8MD//vf/wAA1dXVWL16NYqKiuSfc+fO4fLly9DX13+hnhMnTsDX1xejR4/GgQMHcObMGSxbtgy1tbXyPqtWrcKFCxcwZswY5ObmwtraGpmZmU12rERERNQ4mAlCRERELYa5uTkOHz6MESNGwMPDA//+97/h4OCAS5cuoXfv3r+pjvz8fJibm2PZsmVyWWlp6Qv7WVpawtLSEgsWLMDkyZPxt7/9DV5eXr/bsRAREVHTYxCEiIiIWpRu3bohLy8PI0aMgLu7O0JCQjBx4kR0794dEydOhI6ODn788UecP38ea9eufeHzffr0wc8//4yUlBQMHDgQBw8ebJDl8fjxYwQHB2PixIno2bMnbty4gVOnTmHChAlNeZhERETUCDgchoiIiFqc9957D3l5eaioqMAXX3yBtLQ0fPfddxg4cCCGDBmCzZs3w9zc/KWf9fT0xIIFCxAYGIh+/fohPz8fYWFh8nZdXV3cvXsXfn5+sLS0xB//+EeMGjUKq1evbqrDIyIiokbC1WGIiIiIiIiISCswE4SIiIiIiIiItAKDIERERERERESkFRgEISIiIiIiIiKtwCAIEREREREREWkFBkGIiIiIiIiISCswCEJEREREREREWoFBECIiIiIiIiLSCgyCEBEREREREZFWYBCEiIiIiIiIiLQCgyBEREREREREpBUYBCEiIiIiIiIircAgCBERERERERFphf8DV/M1H+OtjdcAAAAASUVORK5CYII=)

Grafik menunjukkan jumlah observasi pada setiap kelas. Kelas terbanyak
adalah `Obesity_Type_I` sebanyak 351 data,
sedangkan kelas paling sedikit adalah `Insufficient_Weight` sebanyak
267 data.

Distribusi kelas relatif berdekatan sehingga tidak dilakukan oversampling.
Namun, proses evaluasi tetap menggunakan Precision, Recall, dan F1-score.

## 4.2 Persentase Kelas

![Persentase kelas](assets/02_persentase_kelas.png)

Diagram lingkaran memperlihatkan persentase tujuh kelas. Tidak terdapat
kelas tunggal yang mendominasi sebagian besar data.

## 4.3 Histogram Usia

![Histogram usia](assets/03_histogram_usia.png)

Histogram membantu mengetahui rentang usia yang paling banyak muncul.
Sebagian besar data berada pada kelompok usia dewasa muda.

## 4.4 Histogram Berat Badan

![Histogram berat badan](assets/04_histogram_berat_badan.png)

Berat badan memiliki variasi luas dan menjadi salah satu fitur penting
dalam membedakan kelas target.

## 4.5 Histogram Aktivitas Fisik

![Histogram aktivitas fisik](assets/05_histogram_aktivitas_fisik.png)

Fitur `FAF` menggambarkan frekuensi aktivitas fisik. Nilai yang lebih tinggi
menunjukkan aktivitas yang lebih sering.

## 4.6 Boxplot Berat Badan per Kelas

<img width="1089" height="590" alt="image" src="https://github.com/user-attachments/assets/d5fe1db4-59ef-4390-9da2-c20d08682f44" />

Median berat badan cenderung meningkat seiring meningkatnya kelas target.
Pola tersebut menunjukkan bahwa berat badan menjadi pemisah penting.

## 4.7 Heatmap Korelasi

![Heatmap korelasi](assets/07_heatmap_korelasi.png)

Heatmap menunjukkan hubungan linear antarfitur numerik. Korelasi tidak
menunjukkan hubungan sebab akibat, tetapi membantu menemukan fitur yang
berhubungan.

## 4.8 Scatter Plot Tinggi dan Berat Badan

![Scatter tinggi berat](assets/08_scatter_tinggi_berat.png)

Kombinasi tinggi dan berat badan membentuk kelompok yang cukup jelas
berdasarkan kelas target. Hal ini membantu menjelaskan mengapa model
Decision Tree memperoleh performa tinggi.

## 4.9 Deteksi Outlier

![Outlier IQR](assets/09_outlier_iqr.png)

Metode IQR mendeteksi **699 baris** yang memiliki minimal satu
nilai ekstrem. Nilai ekstrem tidak langsung dihapus karena dapat
merepresentasikan variasi data yang masih valid.

## 4.10 Insight Awal EDA

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
