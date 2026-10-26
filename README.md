# Analisis Segmentasi Pelanggan E-Commerce Berdasarkan Perilaku Transaksi Menggunakan RFM dan K-Means Clustering

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-CC0%201.0-green.svg)](https://creativecommons.org/publicdomain/zero/1.0/)
[![CRISP-DM](https://img.shields.io/badge/Methodology-CRISP--DM-orange.svg)](#metodologi)

Repositori ini memuat proyek akhir praktikum dan portofolio Ujian Tengah Semester (UTS) mata kuliah **Data Science** Tahun Ajaran 2026/2027, Program Studi Informatika, Jurusan Informatika, Fakultas Teknik Industri, **Universitas Pembangunan Nasional "Veteran" Yogyakarta**.

---

## 📌 Ringkasan Proyek (Executive Summary)
Dalam ekosistem *e-commerce*, pendekatan pemasaran massal (*one-size-fits-all*) kerap mengakibatkan inefisiensi alokasi anggaran promosi dan hilangnya pelanggan bernilai tinggi (*churn*). Proyek ini menerapkan metodologi ilmiah **CRISP-DM (*Cross-Industry Standard Process for Data Mining*)** untuk membangun sistem segmentasi pelanggan berbasis perilaku transaksi nyata menggunakan kerangka kerja **Recency, Frequency, Monetary (RFM)** yang dikelompokkan secara *unsupervised* dengan algoritma **K-Means Clustering**.

Melalui analisis terhadap **138.116 transaksi log e-commerce** (rentang 2021–2025), penelitian ini menyaring 61.099 transaksi sah berdenominasi USD yang mencakup 14.680 pelanggan unik. Dilakukan penanganan skewness data menggunakan transformasi logaritmik $\ln(1+x)$ dan standardisasi skala (*StandardScaler*). Evaluasi multi-metrik (*Elbow Method*, *Silhouette Analysis*, *Davies-Bouldin Index*, dan *Calinski-Harabasz Index*) menetapkan konfigurasi **$k = 4$ cluster** sebagai partisi paling optimal dan berdaya guna bisnis.

### Temuan Utama Segmen:
1. **Cluster 0 (High-Monetary Loyalists - 32.8% Pelanggan):** Menyumbang **49.3% ($36.95 juta)** dari total pendapatan. Merupakan penopang finansial utama bisnis yang membutuhkan retensi VIP eksklusif.
2. **Cluster 3 (Active Champions - 20.3% Pelanggan):** Pelanggan paling aktif (Median Recency = 33 hari) yang menyumbang **24.5% ($18.34 juta)** omzet. Sasaran utama untuk *cross-selling* dan program rujukan (*referral*).
3. **Cluster 2 (At-Risk Occasional - 34.3% Pelanggan):** Pelanggan yang telah lama tidak aktif (Median Recency = 457 hari) namun memiliki kontribusi kumulatif **23.7% ($17.80 juta)**. Sasaran kampanye reaktivasi (*win-back*).
4. **Cluster 1 (Hibernating Low-Spenders - 12.6% Pelanggan):** Hanya menyumbang **2.5% ($1.88 juta)** pendapatan. Direkomendasikan efisiensi promosi biaya rendah (*low-cost email outreach*).

---

## 👥 Informasi Kelompok & Kontribusi Anggota

| No | Nama Lengkap | NIM | Peran & Kontribusi Utama |
| :---: | :--- | :---: | :--- |
| 1 | **Albertus Bagus Dwi Y. A.** | *[Isi NIM]* | Business Understanding, Data Understanding, dan Perumusan Tujuan SMART |
| 2 | *[Nama Anggota 2]* | *[Isi NIM]* | Exploratory Data Analysis (EDA) dan Visualisasi Statistik |
| 3 | *[Nama Anggota 3]* | *[Isi NIM]* | Data Cleaning, Preprocessing, Log-Transform, dan Rekayasa Fitur RFM |
| 4 | *[Nama Anggota 4]* | *[Isi NIM]* | Pemodelan K-Means & Komparasi Model, Evaluasi Metrik, dan Konklusi Strategi CRM |

*Dosen Pengampu:* **Dhimas Arief Dharmawan**  
*Program Studi Informatika, UPN "Veteran" Yogyakarta*

---

## 📊 Dataset & Lisensi

- **Nama Dataset:** *E-Commerce Sales and Customer Analytics Dataset*
- **Sumber:** [Kaggle Repositori Publik (datascikhan)](https://www.kaggle.com/datasets/datascikhan/e-commerce-sales-and-customer-analytics)
- **Lisensi:** *CC0: Public Domain / Open Data Commons* (Aman digunakan untuk keperluan akademik & riset)
- **Volume & Skema:** 138.116 baris transaksi, 46 kolom fitur mencakup informasi pesanan, pengiriman, biaya pokok (COGS), diskon, dan keuntungan bersih.
- **Kepatuhan Privasi Data:** Seluruh pengenal identitas langsung (PII seperti nama pelanggan, alamat, kode pos) dihilangkan sebelum proses clustering untuk memenuhi standar etika perlindungan privasi.

---

## 🗂️ Struktur Direktori Repositori

```text
Customer-Segmentation-with-RFM-method-and-K-Means/
│
├── E-Commerce Dataset/
│   ├── ecommerce_sales_customer_analytics_150k.csv  # Dataset transaksi utama (138k baris)
│   ├── customer_master.csv                          # Data demografi pelanggan (25k baris)
│   ├── order_items.csv                              # Data rincian item per pesanan (397k baris)
│   ├── product_catalog.csv                          # Katalog produk e-commerce (1.175 produk)
│   └── dataset_statistics.csv                       # Ringkasan statistik makro dataset
│
├── segmentasi_pelanggan_rfm_kmeans.ipynb           # Notebook utama lengkap & ter-eksekusi (CRISP-DM)
├── README.md                                       # Laporan ringkas repositori & panduan eksekusi
├── Panduan Proyek Akhir Praktikum Data Science...   # Panduan praktikum dari prodi
└── UTS Data Science 2026_2027.pdf                   # Rubrik & sistematika laporan UTS
```

---

## 🚀 Panduan Instalasi dan Menjalankan Proyek (Reproduction Guide)

Ikuti langkah-langkah berikut untuk menjalankan notebook secara mandiri:

### 1. Klon Repositori
```bash
git clone https://github.com/ichsannnwp/Customer-Segmentation-with-RFM-method-and-K-Means.git
cd Customer-Segmentation-with-RFM-method-and-K-Means
```

### 2. Pasang Dependensi Python
Pastikan Python versi 3.10 atau yang lebih baru telah terpasang:
```bash
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
```

### 3. Eksekusi Notebook
Anda dapat membuka notebook melalui antarmuka Jupyter Lab / Notebook:
```bash
jupyter notebook segmentasi_pelanggan_rfm_kmeans.ipynb
```
Atau mengeksekusi seluruh sel secara headless melalui baris perintah:
```bash
jupyter nbconvert --to notebook --execute --inplace segmentasi_pelanggan_rfm_kmeans.ipynb
```

---

## 📈 Metodologi CRISP-DM yang Diterapkan

1. **Business Understanding:** Perumusan latar belakang, rumusan masalah, tujuan SMART, pemetaan stakeholder-data, serta mitigasi etika dan risiko hukum.
2. **Data Understanding & Gathering:** Pemuatan dataset, telaah kamus data (*data dictionary*), pengujian representativitas sampel, dan lisensi data.
3. **Exploratory Data Analysis (EDA):** Analisis statistik univariat, bivariat, tren temporal bulanan (2021–2025), serta korelasi Pearson antar fitur finansial (disertai wawasan tertulis di bawah setiap grafik).
4. **Data Cleaning & Preprocessing:** Penyaringan transaksi valid USD, penanganan missing values, tabel komparasi kondisi sebelum vs sesudah pembersihan, agregasi RFM level pelanggan, transformasi logaritmik $\ln(1+x)$, dan standardisasi Z-score.
5. **Modelling:** Evaluasi variasi nilai $k$ (2 hingga 8) menggunakan *Elbow Method*, *Silhouette Analysis*, *Davies-Bouldin Index*, dan *Calinski-Harabasz Index*. Dilengkapi perbandingan model terhadap *Mini-Batch K-Means* dan *Agglomerative Clustering*.
6. **Evaluation:** Rekapitulasi metrik model final ($k=4$), visualisasi *Silhouette Plot*, proyeksi 2D PCA (variansi kumulatif >90%), *Snake Plot*, *Boxplot RFM*, dan grafik distribusi Pareto pendapatan.
7. **Deployment & Actionable CRM Strategy:** Matriks profil persona tiap segmen, alokasi rekomendasi promosi terarah, analisis *Cost-Benefit*, skema pipeline I/O, deteksi *Data Drift* menggunakan *Population Stability Index* (PSI), serta batasan riset.

---

## 📚 Referensi Ilmiah

1. Chapman, P., Clinton, J., Kerber, R., et al. (2000). *CRISP-DM 1.0: Step-by-step data mining guide*. SPSS Inc.
2. Fader, P. S., Hardie, B. G., & Lee, K. L. (2005). "RFM and CLV: Using iso-value curves for multicustomer analysis". *Journal of Marketing Research*, 42(4), 415-430.
3. Hughes, A. M. (1994). *Strategic database marketing: The masterplan for starting and managing a profitable, customer-based marketing program*. McGraw-Hill.
4. Jain, A. K. (2010). "Data clustering: 50 years beyond K-means". *Pattern Recognition Letters*, 31(8), 651-666.
5. MacQueen, J. (1967). "Some methods for classification and analysis of multivariate observations". *Proceedings of the Fifth Berkeley Symposium on Mathematical Statistics and Probability*, 1(14), 281-297.
6. Rousseeuw, P. J. (1987). "Silhouettes: A graphical aid to the interpretation and validation of cluster analysis". *Journal of Computational and Applied Mathematics*, 20, 53-65.
