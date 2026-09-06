# IDENTIFIKASI POLA DAN SEGMENTASI KECELAKAAN LALU LINTAS DENGAN K-MEANS CLUSTERING: STUDI KASUS JASA RAHARJA SURABAYA

## 📌 Deskripsi Proyek

Proyek ini merupakan bagian dari **Kerja Praktik di PT Jasa Raharja** yang bertujuan untuk mengidentifikasi pola dan melakukan segmentasi data kecelakaan lalu lintas menggunakan algoritma **K-Means Clustering**.

Analisis dilakukan berdasarkan karakteristik demografi korban, waktu kejadian, jenis kendaraan, serta karakteristik kecelakaan.

Tahapan analisis meliputi:

- Exploratory Data Analysis (EDA)
- Data Preprocessing
- K-Means Clustering
- Evaluasi Jumlah Cluster
- Principal Component Analysis (PCA)
- Interpretasi Hasil Clustering

> **Catatan:** Dataset asli merupakan data internal perusahaan dan tidak disertakan dalam repository ini.

---

## 🎯 Tujuan

- Menentukan jumlah cluster yang optimal untuk data kecelakaan lalu lintas.
- Mengidentifikasi pola dan segmentasi kecelakaan.
- Menganalisis karakteristik dari setiap cluster.
- Menghasilkan insight yang dapat mendukung strategi pencegahan kecelakaan berbasis data.

---

## 📊 Dataset

Dataset berisi informasi mengenai korban kecelakaan lalu lintas yang tercatat oleh PT Jasa Raharja.

Variabel yang digunakan meliputi:

- Hari, tanggal, dan jam kecelakaan
- Wilayah
- Jenis kelamin korban
- Usia korban
- Profesi korban
- Jenis kendaraan
- Sifat kecelakaan
- Jenis kasus kecelakaan

Dataset yang dianalisis terdiri dari **194.423 baris dan 9 kolom** setelah tahap persiapan data.

---

## 🔎 Exploratory Data Analysis

EDA dilakukan untuk memahami karakteristik, distribusi, dan pola awal pada data.

### Temuan Utama

- Korban kecelakaan didominasi oleh laki-laki.
- Sepeda motor merupakan jenis kendaraan yang paling banyak terlibat.
- Jenis kecelakaan yang paling umum adalah tabrakan depan-depan.
- Kelompok usia muda dan usia produktif merupakan kelompok yang cukup dominan.
- Profesi korban yang banyak ditemukan adalah wiraswasta, pelajar/mahasiswa, dan karyawan swasta.

---

## ⚙️ Data Preprocessing

### 1. Feature Scaling

Variabel numerik ditransformasikan menggunakan **MinMaxScaler** ke dalam rentang 0–1 agar setiap fitur memiliki skala yang sebanding dalam proses perhitungan jarak.

### 2. Pengolahan Variabel Kategorikal

Variabel kategorikal diproses melalui:

- Penggabungan kategori dengan frekuensi rendah menjadi kategori **MINORITY**.
- **One-Hot Encoding** untuk mengubah variabel kategorikal menjadi representasi numerik.

---

## 🤖 K-Means Clustering

Proses clustering dilakukan menggunakan **Python melalui Google Colab**.

Untuk menentukan jumlah cluster yang digunakan, dilakukan evaluasi menggunakan:

- **Elbow Method**
- **Silhouette Score**
- **Calinski-Harabasz Index**

### Jumlah Cluster

Berdasarkan hasil evaluasi dan pertimbangan tujuan segmentasi, digunakan:

**k = 5**

Metode Elbow menunjukkan titik siku pada k = 5. Sementara itu, Silhouette Score dan Calinski-Harabasz Index memiliki nilai tertinggi pada k = 2.

Namun, k = 5 dipilih karena memberikan segmentasi yang lebih rinci dan lebih mudah diinterpretasikan sesuai dengan tujuan analisis.

---

## 📈 Visualisasi PCA

**Principal Component Analysis (PCA)** digunakan untuk mereduksi dimensi data sehingga hasil clustering dapat divisualisasikan dalam bentuk 2D dan 3D.

Visualisasi PCA menunjukkan adanya pemisahan antar beberapa cluster, meskipun masih terdapat area yang mengalami overlap akibat adanya kemiripan karakteristik antar kelompok.

### PCA 2D

![PCA 2D](outputs/pca_2d.png)

### PCA 3D

![PCA 3D](outputs/pca_3d.png)

---

## 📊 Evaluasi Jumlah Cluster

### Elbow Method

![Elbow Method](outputs/elbow_plot.png)

### Silhouette Score

![Silhouette Score](outputs/silhouette_plot.png)

### Calinski-Harabasz Index

![Calinski-Harabasz Index](outputs/ch_index_plot.png)

---

## 🧩 Profil Cluster

Hasil K-Means menghasilkan lima kelompok dengan karakteristik utama sebagai berikut:

| Cluster | Karakteristik Utama |
|---------|---------------------|
| **Cluster 0** | Pengendara motor pria dewasa, dominan karyawan swasta |
| **Cluster 1** | Pengendara motor pria muda, dominan pelajar/mahasiswa |
| **Cluster 2** | Pria dewasa dengan profesi wiraswasta, terkait kecelakaan dengan pejalan kaki |
| **Cluster 3** | Pria dewasa dengan profesi wiraswasta, dominan kecelakaan depan-depan |
| **Cluster 4** | Pengendara motor wanita dewasa, dominan wiraswasta |

---

## 💡 Insight Utama

Hasil clustering menunjukkan adanya beberapa kelompok dengan karakteristik demografis dan aktivitas yang berbeda.

Beberapa kelompok yang teridentifikasi antara lain:

- Pengendara motor pria usia muda, terutama pelajar/mahasiswa.
- Pengendara motor usia produktif yang bekerja sebagai karyawan swasta.
- Kelompok wiraswasta dengan karakteristik mobilitas tinggi.
- Pengendara motor wanita dewasa dengan profesi wiraswasta.

Hasil segmentasi dapat menjadi dasar untuk memahami karakteristik kelompok korban dan mendukung penyusunan strategi pencegahan kecelakaan yang lebih terarah.

---

## 🛠️ Tools & Technologies

| Kategori | Tools |
|----------|-------|
| Programming | Python |
| Data Processing | Pandas, NumPy |
| Machine Learning | Scikit-learn |
| Clustering | K-Means |
| Dimensionality Reduction | PCA |
| Visualization | Matplotlib, Seaborn |
| Environment | Google Colab |

---

## 📁 Struktur Repository

```text
KP-KMeans-Traffic-Accident-Clustering/
│
├── README.md
│
├── notebooks/
│   └── KMeans_Traffic_Accident_Analysis.ipynb
│
├── outputs/
│   ├── elbow_plot.png
│   ├── silhouette_plot.png
│   ├── ch_index_plot.png
│   ├── pca_2d.png
│   └── pca_3d.png
│
├── requirements.txt
│
└── .gitignore
