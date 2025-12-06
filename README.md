# Customer Segmentation for Personalized Retail Marketing 

Project ini adalah implementasi Machine Learning untuk melakukan segmentasi pelanggan (Customer Segmentation) guna mendukung strategi pemasaran ritel yang lebih personal. Project ini menggunakan metode analisis **RFM (Recency, Frequency, Monetary)** dan algoritma clustering (seperti K-Means) untuk mengelompokkan pelanggan berdasarkan perilaku transaksi mereka.

Hasil analisis divisualisasikan melalui dashboard interaktif yang dideploy menggunakan **Streamlit** dan **Netlify**.

## Demo Aplikasi

- **Streamlit Dashboard (Python):** [https://notebook-capstone-a25-cs273.streamlit.app/]
- **Web Dashboard (Netlify - HTML/JS):** [https://capstonea25.netlify.app/]

## Struktur Repository

Berikut adalah penjelasan mengenai file dan folder dalam repository ini:

| File/Folder | Deskripsi |
| :--- | :--- |
| `dataset/` | Folder berisi data mentah (raw data) transaksi ritel. |
| `notebook/` | Berisi Jupyter Notebook untuk proses pembersihan data, EDA, perhitungan RFM, dan modeling Clustering. |
| `app.py` | Source code utama untuk dashboard berbasis **Streamlit**. |
| `app.js` & `index.html` | Source code untuk visualisasi frontend yang dideploy ke **Netlify**. |
| `rfm_cluster_result.csv` | File output hasil clustering yang digunakan oleh dashboard untuk menampilkan data. |
| `requirements.txt` | Daftar library Python yang dibutuhkan untuk menjalankan project ini. |

## Teknologi yang Digunakan

- **Language:** Python, JavaScript (Visualisasi Web)
- **Data Processing:** Pandas, NumPy
- **Machine Learning:** Scikit-Learn (K-Means Clustering)
- **Visualization:** Plotly, Matplotlib
- **Deployment:** Streamlit Cloud, Netlify

## Cara Menjalankan di Lokal (Local Installation)

1. **Clone Repository**
   ```bash
   git clone [https://github.com/Mryourhead/notebook-capstone.git](https://github.com/Mryourhead/notebook-capstone.git)
   cd notebook-capstone
   
2.  **Install Dependencies**
    Pastikan Anda sudah menginstall Python.
    ```bash
    pip install -r requirements.txt
    ```

3.  **Jalankan Streamlit**
    ```bash
    streamlit run app.py
    ```

## Workflow & Update Dataset

Sistem ini memisahkan antara proses **Training (Notebook)** dan **Visualisasi (App)**. Dashboard (`app.py` dan `app.js`) **tidak** melakukan training ulang secara otomatis, melainkan hanya membaca hasil yang sudah jadi di `rfm_cluster_result.csv`.

### Skenario: Bagaimana jika saya punya data transaksi baru?

Jika Anda ingin memperbarui dashboard dengan data bulan terbaru atau mengganti dataset sepenuhnya, ikuti langkah berikut:

#### Langkah 1: Siapkan Data
Masukkan file CSV data transaksi baru Anda ke dalam folder `dataset/`.

#### Langkah 2: Proses Ulang di Notebook
1. Buka Jupyter Notebook yang ada di folder `notebook/`.
2. Sesuaikan kode untuk membaca file dataset yang baru (jika nama file berubah).
3. Jalankan semua sel (*Run All*) untuk melakukan:
   - Data Cleaning.
   - Perhitungan skor RFM terbaru.
   - Training ulang model K-Means untuk menentukan cluster baru.
4. **Penting:** Pastikan kode terakhir di notebook menyimpan hasilnya menimpa file `rfm_cluster_result.csv`.
   ```python
   # Contoh kode di akhir notebook
   df_final.to_csv('../rfm_cluster_result.csv', index=False)

#### Tentu, ini adalah naskah README.md yang lengkap dalam satu kesatuan. Anda tinggal menyalin seluruh blok kode di bawah ini dan menimpanya ke dalam file README.md di repository GitHub Anda.

Jangan lupa untuk mengubah bagian yang saya tandai dengan kurung siku [...] (seperti link demo atau nama Anda) dengan data yang sebenarnya.

Markdown

# 🛍️ Customer Segmentation for Personalized Retail Marketing

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![Streamlit](https://img.shields.io/badge/Streamlit-Deployed-red)
![Netlify](https://img.shields.io/badge/Netlify-Deployed-00C7B7)

> **Capstone Project**: Penerapan Machine Learning untuk strategi pemasaran ritel berbasis data.

## 📖 Tentang Project

Project ini bertujuan untuk membantu tim pemasaran ritel dalam memahami karakteristik pelanggan mereka. Dengan menggunakan teknik **RFM Analysis (Recency, Frequency, Monetary)** dan algoritma **K-Means Clustering**, kami mengelompokkan pelanggan ke dalam segmen-segmen yang berbeda (seperti *Loyal Customers*, *Big Spenders*, atau *Lost Customers*).

Hasil segmentasi ini divisualisasikan dalam dashboard interaktif untuk memudahkan pengambilan keputusan bisnis dan strategi promosi yang lebih personal.

## 🚀 Live Demo

Coba aplikasi yang sudah dideploy melalui link berikut:

* 📊 **Dashboard Analisis (Streamlit):** [MASUKKAN LINK STREAMLIT ANDA DI SINI]
* 🌐 **Visualisasi Web (Netlify):** [MASUKKAN LINK NETLIFY ANDA DI SINI]

## 📂 Struktur Repository

| File / Folder | Fungsi |
| :--- | :--- |
| `dataset/` | Menyimpan data mentah (raw data) transaksi penjualan. |
| `notebook/` | Jupyter Notebook untuk proses pembersihan data, EDA, dan permodelan K-Means. |
| `app.py` | Source code utama untuk dashboard **Streamlit**. |
| `app.js` | Logika visualisasi grafik untuk dashboard versi **Netlify** (HTML/JS). |
| `index.html` | Struktur halaman web untuk dashboard versi **Netlify**. |
| `rfm_cluster_result.csv` | **File Inti:** Hasil olahan data dan clustering yang dibaca oleh dashboard. |
| `requirements.txt` | Daftar library Python yang dibutuhkan. |

## 🛠️ Tech Stack

* **Bahasa:** Python, JavaScript
* **Data Processing:** Pandas, NumPy
* **Machine Learning:** Scikit-Learn (K-Means, Silhouette Score)
* **Visualization:** Plotly, Matplotlib, Chart.js (untuk versi Web)
* **Deployment:** Streamlit Cloud, Netlify

## 💻 Cara Menjalankan di Lokal (Installation)

Ikuti langkah ini jika ingin menjalankan dashboard di komputer Anda:

1.  **Clone Repository**
    ```bash
    git clone [https://github.com/Mryourhead/notebook-capstone.git](https://github.com/Mryourhead/notebook-capstone.git)
    cd notebook-capstone
    ```

2.  **Install Dependencies**
    Pastikan Anda sudah menginstall Python.
    ```bash
    pip install -r requirements.txt
    ```

3.  **Jalankan Streamlit**
    ```bash
    streamlit run app.py
    ```

## 🔄 Workflow & Update Dataset

Sistem ini memisahkan antara proses **Training (Notebook)** dan **Visualisasi (App)**. Dashboard (`app.py` dan `app.js`) **tidak** melakukan training ulang secara otomatis, melainkan hanya membaca hasil yang sudah jadi di `rfm_cluster_result.csv`.

### Skenario: Bagaimana jika saya punya data transaksi baru?

Jika Anda ingin memperbarui dashboard dengan data bulan terbaru atau mengganti dataset sepenuhnya, ikuti langkah berikut:

#### Langkah 1: Siapkan Data
Masukkan file CSV data transaksi baru Anda ke dalam folder `dataset/`.

#### Langkah 2: Proses Ulang di Notebook
1. Buka Jupyter Notebook yang ada di folder `notebook/`.
2. Sesuaikan kode untuk membaca file dataset yang baru (jika nama file berubah).
3. Jalankan semua sel (*Run All*) untuk melakukan:
   - Data Cleaning.
   - Perhitungan skor RFM terbaru.
   - Training ulang model K-Means untuk menentukan cluster baru.
4. **Penting:** Pastikan kode terakhir di notebook menyimpan hasilnya menimpa file `rfm_cluster_result.csv`.
   ```python
   # Contoh kode di akhir notebook
   df_final.to_csv('../rfm_cluster_result.csv', index=False)
#### Langkah 3: Push ke GitHub
Setelah file `rfm_cluster_result.csv` berubah isinya, upload perubahan tersebut ke GitHub.

```bash
git add rfm_cluster_result.csv
git commit -m "Update: Refresh data clustering dengan transaksi terbaru"
git push origin main
```
