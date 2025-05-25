# Proyek Klasifikasi Mata Terbuka & Mata Tertutup (Drowsiness Detection)

Contoh visualisasi deteksi mata terbuka/tertutup

## Daftar Isi

- [Tentang Proyek](#tentang-proyek)
- [Fitur Utama](#fitur-utama)
- [Dataset](#dataset)
- [Metodologi](#metodologi)
- [Teknologi yang Digunakan](#teknologi-yang-digunakan)
- [Cara Menjalankan](#cara-menjalankan)
- [Hasil](#hasil)
- [Potensi Pengembangan](#potensi-pengembangan)
- [Lisensi](#lisensi)
- [Kontak](#kontak)

## Tentang Proyek

Proyek ini adalah implementasi model Computer Vision untuk klasifikasi status mata (terbuka atau tertutup). Tujuan utamanya adalah mendeteksi tanda-tanda kantuk atau kelelahan pada individu, yang krusial dalam sistem peringatan dini saat bekerja di depan Laptop/PC.

Model ini dilatih menggunakan teknik Deep Learning dan dibangun sepenuhnya di lingkungan Google Colaboratory, memanfaatkan kemampuan GPU/TPU gratis yang disediakan Colab untuk pelatihan model yang efisien.

## Fitur Utama

- Klasifikasi Real-time: meskipun model dilatih di Colab, arsitekturnya dirancang agar dapat diintegrasikan ke dalam sistem real-time untuk deteksi mata.
- Akurasi Tinggi: model menunjukkan performa klasifikasi yang sangat baik pada dataset yang digunakan.
- Pembelajaran Mendalam: menggunakan arsitektur Convolutional Neural Network (CNN) yang kuat untuk ekstraksi fitur dan klasifikasi.
- Skalabilitas: dapat dilatih ulang dengan dataset yang lebih besar untuk meningkatkan akurasi dan robustness.
- Lingkungan Colab: semua kode dan proses pelatihan dapat direplikasi dengan mudah di Google Colab.

## Dataset

Model ini dilatih menggunakan [Drowsiness Detection Dataset](https://www.kaggle.com/datasets/hazemfahmy/openned-closed-eyes) yang berisi gambar-gambar mata dalam dua kategori: opened dan closed. Dataset ini memiliki total 4103 gambar, dengan 2171 untuk mata terbuka (opened) dan 1932 untuk mata tertutup (closed).

Sumber Dataset: [Kaggle](https://www.kaggle.com/datasets/hazemfahmy/openned-closed-eyes) <br>
Format Data: Gambar berformat .jpg dengan resolusi yang seragam <br>

## Metodologi 

Proyek ini mengikuti alur kerja Machine Learning standar:

1. Pengumpulan & Persiapan Data: mengunduh dan memuat dataset, diikuti dengan pre-processing yaitu normalisasi dan data augmentation
2. Pembagian Data: dataset dibagi menjadi set pelatihan, validasi, dan pengujian
3. Arsitektur Model: mengimplementasikan arsitektur CNN khusus yakni menggunakan model transfer learning berbasis MobileNetV2 yang di-fine-tune. Detail lapisan dan konfigurasi dapat dilihat pada notebook
4. Pelatihan Model: model dilatih selama 30 epochs dengan optimizer Adam dan loss function Binary Crossentropy
5. Evaluasi Model: model dievaluasi pada set pelatihan dan pengujian menggunakan metrik seperti akurasi dan loss
6. Penyimpanan Model: model yang telah terlatih disimpan dalam format savedModel, .h5, .tflite, dan tfjs untuk inferensi di masa mendatang

## Teknologi yang Digunakan

- Bahasa Pemrograman: Python 3
- Library Utama:
    - TensorFlow: digunakan untuk membangun dan melatih model Deep Learning `tensorflow==2.19.0`
    - Keras: antarmuka API tingkat tinggi yang terintegrasi dalam TensorFlow untuk pengembangan model yang cepat
    - OpenCV-Python: untuk operasi Computer Vision dasar seperti pembacaan gambar, pre-processing, dan augmentasi data `opencv-python==4.11.0.86`
    - Numpy: fundamental untuk operasi numerik, terutama manipulasi array data `numpy==2.2.6`
    - Pandas: digunakan untuk analisis dan manipulasi data tabular `pandas==2.2.3`
    - Matplotlib & Seaborn: untuk visualisasi data, metrik pelatihan, dan hasil model `matplotlib==3.10.3`, `seaborn==0.13.2`
    - Pillow: library dasar untuk pemrosesan gambar `Pillow==11.2.1`
    - Scikit-learn: untuk utilitas Machine Learning seperti pembagian data, evaluasi metrik, atau pre-processing tambahan `scikit-learn==1.6.1`
    - tqdm: untuk menampilkan progress bar selama proses iterasi atau pelatihan `tqdm==4.67.1`
- Lingkungan Pengembangan: Google Colaboratory

## Cara Menjalankan

Untuk mereplikasi proyek ini di Google Colab:

1. Buka Notebook: buka file notebook `CC25_CF019_Klasifikasi_Mata_Terbuka_dan_Mata_Tertutup.ipynb` ini di Google Colab
2. Jalankan Sel Berurutan: jalankan semua sel kode secara berurutan dari atas ke bawah
    - Pastikan mengaktifkan GPU runtime `Runtime -> Change runtime type -> pilih GPU`
    - Instal dependensi yang diperlukan di sel pertama
    - Dataset akan diunduh secara otomatis jika belum ada (sesuaikan path dataset jika diperlukan) <br>
    NB: diperlukan nya credentials yang didapatkan pada akun Kaggle untuk mengunduh dataset tersebut
3. Eksplorasi Hasil: sel-sel terakhir akan menampilkan metrik pelatihan, grafik, dan contoh prediksi model

## Hasil

Model ini berhasil mencapai akurasi validasi `94%` dan akurasi pengujian `94.16%`.

Hasil ini menunjukkan bahwa model memiliki kemampuan yang baik untuk membedakan antara mata terbuka dan mata tertutup, menjadikannya dasar yang kuat untuk aplikasi deteksi kantuk.

## Potensi Pengembangan

- Integrasi Kamera Real-time: mengimplementasikan model untuk deteksi kantuk real-time menggunakan webcam
- Deteksi Tingkat Kantuk: mengembangkan lebih lanjut untuk tidak hanya klasifikasi biner, tetapi juga mengukur tingkat kantuk
- Deteksi Kelelahan Komprehensif: menggabungkan dengan fitur lain seperti yawning detection atau analisis head pose
- Optimisasi Model: mengoptimalkan model untuk deployment pada perangkat edge dengan sumber daya terbatas
- Dataset yang Lebih Besar & Beragam: melatih model dengan dataset yang lebih bervariasi untuk meningkatkan generalisasi pada berbagai kondisi pencahayaan dan etnis

## Lisensi

Proyek ini dilisensikan di bawah [MIT License](LICENSE).

## Kontak

Jika Anda memiliki pertanyaan atau ingin berdiskusi lebih lanjut, jangan ragu untuk menghubungi tim kami:

- Tarq Hilmar Siregar
    - [GitHub](https://github.com/tarqhilmarsiregar)
    - [LinkedIn](https://www.linkedin.com/in/tarqhilmarsiregar/)

- Rasendra Akbar Satyatama
    - [GitHub](https://github.com/rasendraas)
    - [LinkedIn](https://www.linkedin.com/in/rasendra-akbar/)

- Fitri Fatma Dewi
    - [GitHub](https://github.com/fitrifatmadewi)
    - [LinkedIn](https://www.linkedin.com/in/fitri-fatma-dewi/)