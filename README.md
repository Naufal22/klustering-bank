# 🏦 Segmentasi Nasabah Bank dengan K-Means Clustering

Proyek ini menerapkan unsupervised learning untuk mengelompokkan nasabah bank ke dalam beberapa segmen yang berbeda berdasarkan pola transaksi dan demografi mereka. Dengan menggunakan algoritma K-Means Clustering, kita dapat menemukan pola tersembunyi dalam data yang bermanfaat untuk strategi bisnis, deteksi anomali, dan personalisasi layanan.

Proyek ini dibuat sebagai submission untuk menyelesaikan tugas akhir dari kelas "Belajar Machine Learning untuk Pemula" oleh Dicoding Indonesia.

---

## 📊 Dataset

- **Sumber**: Dataset ini merupakan versi modifikasi dari *Bank Transaction Dataset for Fraud Detection* yang tersedia di Kaggle.
- **Fitur Utama**:
  - `TransactionAmount`: Nilai transaksi.
  - `AccountBalance`: Saldo akun setelah transaksi.
  - `TransactionType`: Tipe transaksi (Debit/Kredit).
  - `Channel`: Kanal transaksi (Online, ATM, Cabang).
  - `CustomerAge`: Usia nasabah.
  - `CustomerOccupation`: Pekerjaan nasabah.
- **Ukuran**: ~2.500 sampel data transaksi.
- **Target**: Label cluster (misal: "Nasabah Loyal", "Berisiko Tinggi", "Pengguna ATM Aktif") dihasilkan oleh model, bukan bagian dari dataset asli.

---

## 🎯 Tujuan Proyek

- Menganalisis dan memvisualisasikan data transaksi nasabah untuk menemukan wawasan awal.
- Menerapkan teknik *preprocessing* data untuk menyiapkan data sebelum pemodelan.
- Menentukan jumlah segmen (cluster) yang paling optimal menggunakan **Elbow Method**.
- Membangun model K-Means untuk mengelompokkan nasabah.
- Menganalisis dan menginterpretasikan karakteristik unik dari setiap segmen nasabah yang terbentuk.

---

## ⚙️ Alur Kerja & Metodologi

1.  **Eksplorasi Data (EDA)**: Menganalisis korelasi antar fitur numerik dan distribusi data kategorikal untuk memahami karakteristik dataset.
2.  **Pra-pemrosesan Data**:
    - **Encoding**: Mengubah fitur kategorikal (seperti `CustomerOccupation`) menjadi format numerik menggunakan `LabelEncoder`.
    - **Scaling**: Menyamakan skala semua fitur numerik ke rentang [0, 1] menggunakan `MinMaxScaler` agar tidak ada fitur yang mendominasi.
    - **Outlier & Feature Engineering**: Menangani nilai ekstrem dan melakukan *binning* pada fitur `CustomerAge` untuk membuat kategori usia.
3.  **Pemodelan K-Means**:
    - Menggunakan `KElbowVisualizer` untuk menemukan jumlah cluster (K) yang optimal secara visual.
    - Melatih model `KMeans` dengan nilai K yang telah ditentukan.
4.  **Evaluasi & Interpretasi**:
    - Menghitung **Silhouette Score** untuk mengukur seberapa baik pemisahan antar cluster.
    - Memvisualisasikan cluster dalam ruang 2D menggunakan **PCA (Principal Component Analysis)**.
    - Menggunakan `inverse_transform` untuk mengembalikan data ke skala aslinya agar hasil analisis mudah dipahami oleh manusia.

---

## 🧪 Hasil

- Model berhasil mengidentifikasi **4 cluster** nasabah yang optimal.
- Didapatkan **Silhouette Score** sekitar **0.61**, yang menunjukkan bahwa cluster yang terbentuk memiliki kepadatan yang baik dan terpisah dengan cukup jelas.
- **Contoh Karakteristik Cluster yang Ditemukan**:
  - **Cluster 0 - Pengguna Digital Aktif**: Cenderung berusia lebih muda, melakukan banyak transaksi *online* dengan nominal bervariasi.
  - **Cluster 1 - Nasabah Konvensional**: Lebih sering bertransaksi di cabang bank (`Branch`) dengan saldo akun yang cenderung stabil.
  - *(Analisis lengkap terdapat di dalam notebook)*.

---

## 💻 Teknologi yang Digunakan

- **Python**
- **Scikit-learn** (untuk `KMeans`, `PCA`, `MinMaxScaler`, `LabelEncoder`)
- **Pandas** & **NumPy** (untuk manipulasi data)
- **Matplotlib** & **Seaborn** (untuk visualisasi data)
- **Yellowbrick** (untuk `KElbowVisualizer`)

---



## 🙋 Kontak

**Muhammad Naufal Aqil**
- **Email**: muhammadnaufalaqil20@gmail.com
- **GitHub**: [Naufal22](https://github.com/Naufal22)
- **LinkedIn**: [Muhammad Naufal Aqil](https://www.linkedin.com/in/muhammad-naufal-aqil-b6114424a/)
