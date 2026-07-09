# Analisis dan Segmentasi Data Transaksi Perbankan

Proyek akhir kelas *Belajar Machine Learning untuk Pemula* — Dicoding Indonesia (2026).

Proyek ini menerapkan alur kerja *unsupervised* dilanjutkan *supervised learning* pada data transaksi perbankan: melakukan segmentasi nasabah menggunakan K-Means, kemudian melatih model klasifikasi untuk mempelajari batas antar segmen yang terbentuk.

## Dataset

`bank_transactions_data_2.csv` — 2.512 baris, 16 kolom, memuat atribut transaksi (nominal, jenis, kanal, lokasi, perangkat) dan atribut nasabah (usia, pekerjaan, saldo, percobaan login).

Dataset disediakan oleh Dicoding Indonesia dan tidak disertakan dalam repositori ini.

## Metode

**1. Clustering** — `[Clustering]_Submission_Akhir_BMLP.ipynb`

- Pembersihan data dan penanganan nilai hilang
- Rekayasa fitur (pengelompokan usia)
- Standardisasi fitur numerik dan *encoding* fitur kategorik
- Reduksi dimensi dengan PCA
- Segmentasi menggunakan K-Means
- Pemilihan jumlah klaster melalui *elbow method* dan *silhouette analysis*

**2. Klasifikasi** — `[Klasifikasi]_Submission_Akhir_BMLP.ipynb`

- Label klaster dari tahap sebelumnya digunakan sebagai target
- Pelatihan model Decision Tree dan Random Forest
- *Hyperparameter tuning*
- Evaluasi melalui *confusion matrix* dan *classification report*

## Hasil

| Tahap | Metrik | Nilai |
|---|---|---|
| Clustering | Jumlah klaster | 2 |
| Clustering | Silhouette Score | 0,572 |

Catatan: pada tahap klasifikasi, target yang diprediksi adalah label klaster yang dihasilkan oleh K-Means pada tahap sebelumnya. Karena label tersebut merupakan keluaran deterministik dari algoritma pemisah yang sama, akurasi yang sangat tinggi bersifat wajar dan tidak dapat ditafsirkan sebagai ukuran generalisasi terhadap fenomena dunia nyata. Tahap klasifikasi di sini berfungsi sebagai latihan pemodelan, bukan sebagai bukti daya prediksi.

## Teknologi

Python, pandas, NumPy, scikit-learn, Matplotlib, Seaborn, Jupyter Notebook.

## Cara Menjalankan

1. Unduh dataset dan letakkan di direktori yang sama dengan notebook.
2. Pasang dependensi:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
```

3. Jalankan `[Clustering]_Submission_Akhir_BMLP.ipynb` terlebih dahulu, lalu `[Klasifikasi]_Submission_Akhir_BMLP.ipynb`.

## Penulis

Muhammad Hadyan Taris — [LinkedIn](https://www.linkedin.com/in/hadyantaris93/)
