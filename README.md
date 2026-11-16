# Magnet Mobilitas DIY: Analisis Data JogjaPulse

Tugas kelompok mata kuliah **Rekayasa Data**, Universitas Gadjah Mada.

**Pertanyaan utama:** Kapanewon mana yang menjadi "magnet" di DIY, dan dari mana saja pengunjungnya datang?

## Temuan Utama
- **Magnet relatif** terpusat di Kota Yogyakarta: seluruh 14 kapanewon kota tergolong magnet tinggi, tertinggi Gondomanan, Pakualaman, dan Gondokusuman.
- **Magnet absolut** berada di kapanewon penyangga kota: Depok, Banguntapan, Kasihan, Gamping, dan Ngaglik.
- Pengunjung umumnya berasal dari **kapanewon tetangga**, dengan Sleman sebagai penyumbang terbesar.

## Anggota Kelompok
| No | Nama | NIM |
|---|---|---|
| 1 | Akio Afifian Ahsan | 24/542230/TK/60198 |
| 2 | Bayu Rahmat Kurnia | 24/533736/TK/59139 |
| 3 | Dharu Bintang Mahendratama | 24/535960/TK/59484 |
| 4 | Muhammad Affandi Argya Bagaskara | 24/538984/TK/59778 |
| 5 | Muhammad Bintang Hidayatullah Marbun | 24/544012/TK/60468 |
| 6 | Nabil Aufa Danaputra | 24/535233/TK/59357 |
| 7 | Raka Bagus Samudra | 24/543213/TK/60349 |
| 8 | Razaqi Alkautsar | 24/544958/TK/60570 |

## Data
Sumber: [JogjaPulse: An Aggregated Spatio-Temporal Mobility Dataset for Yogyakarta, Indonesia](https://zenodo.org/records/23157460). Data agregat pergerakan HP di DIY, Desember 2021 – April 2022, dengan perlindungan privasi k-anonymity (k = 5).

| File | Kegunaan |
|---|---|
| `od_home_visits_kapanewon_monthly.csv` | Aliran pengunjung antar kapanewon per bulan |
| `od_origin_homes_monthly.csv` | Jumlah HP berumah per kapanewon (penyebut) |
| `home_maids_vs_population_kapanewon.csv` | Jumlah penduduk per kapanewon |
| `od_summary.csv` | Ringkasan dampak sensor privasi |
| `presence_kapanewon_hourly.csv` | Keramaian per jam (validasi) |
| `kapanewon_wkt.csv` | Peta batas kapanewon, dari [badaksambel/jogjapulse](https://github.com/badaksambel/jogjapulse) |

Analisis utama menggunakan data **Desember 2021 – Februari 2022**, karena kualitas data Maret–April 2022 menurun.

## Alur Pengerjaan
1. **Load Data**
2. **Exploratory Data Analysis**
3. **Data Cleaning**
4. **Data Integration**
5. **Transformation**: normalisasi, perkiraan jumlah orang, indeks magnet
6. **Data Warehouse**: fact constellation di DuckDB, query OLAP (roll-up, drill-down, slice, dice)
7. **Analisis & Visualisasi**: peta indeks magnet, peringkat, asal pengunjung, peta aliran, Sankey
8. **Kesimpulan & Keterbatasan**

## Cara Menjalankan
1. Buka notebook di [Google Colab](https://colab.research.google.com/drive/1ija0Y9Tw2S6vnfNpRwZGL4ouFGjN_phE?usp=sharing).
2. Unduh 5 file CSV dari [Zenodo](https://zenodo.org/records/23157460). Peta diunduh otomatis.
3. Taruh file di Google Drive (`PAKAI_DRIVE = True`, sesuaikan nama folder) atau unggah ke tab Files Colab (`PAKAI_DRIVE = False`).
4. Jalankan **Runtime → Run all**.

## Isi Repository
| File | Keterangan |
|---|---|
| `Tugas_Rekdat_Magnet_DIY.ipynb` | Notebook lengkap beserta output |
| `README.md` | Dokumentasi proyek |

## Tautan
- Notebook Colab: [link](https://colab.research.google.com/drive/1ija0Y9Tw2S6vnfNpRwZGL4ouFGjN_phE?usp=sharing)
- Video presentasi: [link](https://drive.google.com/file/d/1h2vX-Dr0cftuWFYkm2_eosjuHNBpn_NB/view?usp=sharing)
