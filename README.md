# Proyek Klasifikasi Gambar Sayuran

Proyek ini bertujuan untuk membangun dan melatih model *machine learning* yang dapat mengklasifikasikan gambar berbagai jenis sayuran. Model ini dibangun menggunakan arsitektur Convolutional Neural Network (CNN) dengan *framework* TensorFlow dan Keras.

## Dataset

Dataset yang digunakan dalam proyek ini adalah **Vegetable Image Dataset** yang tersedia secara publik di Kaggle. Dataset ini berisi ribuan gambar dari 15 jenis sayuran yang berbeda.

- **Sumber:** [Kaggle Vegetable Image Dataset](https://www.kaggle.com/datasets/misrakahmed/vegetable-image-dataset)

## Struktur File

- **`main.ipynb`**: Jupyter Notebook utama yang berisi semua langkah, mulai dari pra-pemrosesan data, pembuatan arsitektur model, proses training, evaluasi, hingga konversi model.
- **`convert_model_tensorflowjs.ipynb`**: Notebook terpisah untuk mengonversi model yang sudah dilatih ke format TensorFlow.js, yang memungkinkan model untuk dijalankan langsung di web browser.
- **`requirements.txt`**: File yang berisi daftar semua *library* Python yang dibutuhkan untuk menjalankan proyek ini.
- **`README.md`**: File dokumentasi ini.

Untuk menjalankan proyek ini di lingkungan lokal Anda, ikuti langkah-langkah berikut:

1.  **Clone Repository**
    *(Jika proyek ini ada di Git, jika tidak, cukup unduh folder proyeknya)*
    ```bash
    git clone [URL_REPOSITORY_ANDA]
    cd [NAMA_FOLDER_PROYEK]
    ```

2.  **Buat dan Aktifkan Virtual Environment**
    Ini adalah praktik terbaik untuk menjaga dependensi proyek tetap terisolasi.
    ```bash
    # Membuat venv
    python -m venv venv

    # Mengaktifkan venv (Windows)
    .\venv\Scripts\activate

    # Mengaktifkan venv (macOS/Linux)
    source venv/bin/activate
    ```

3.  **Install Dependensi**
    Pasang semua *library* yang diperlukan menggunakan file `requirements.txt`.
    ```bash
    pip install -r requirements.txt
    ```

## Penggunaan

1.  Pastikan *virtual environment* Anda sudah aktif dan semua dependensi telah terpasang.
2.  Jalankan Jupyter Notebook:
    ```bash
    jupyter notebook main.ipynb
    ```
3.  Di dalam notebook, Anda dapat menjalankan setiap sel kode secara berurutan untuk melihat keseluruhan proses, mulai dari memuat data, melatih model, hingga menyimpan hasil model.

## Model yang Dihasilkan

Proyek ini menghasilkan dua format model utama:
1.  **TensorFlow SavedModel**: Tersimpan di dalam direktori `saved_model/`. Ini adalah format standar untuk menggunakan model dengan ekosistem TensorFlow.
2.  **TensorFlow Lite (`.tflite`)**: File `model.tflite` adalah model yang lebih ringan dan cocok untuk aplikasi *mobile* (Android/iOS) atau perangkat IoT.
3. **TensorFlow.js Web Model**: Dihasilkan oleh `convert_model_tensorflowjs.ipynb`. Format ini terdiri dari beberapa file (model.json dan file *.bin) yang dirancang untuk dieksekusi langsung pada aplikasi web berbasis JavaScript.