# notebook-capstone
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
