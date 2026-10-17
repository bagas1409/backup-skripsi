# Arsitektur Halaman Aplikasi Mobile (React Native)

## 1. Autentikasi
*   **Login & Register:** Halaman masuk dan pendaftaran pengguna (petani/penyuluh). Data akan dihubungkan dengan *database* (misalnya Firebase/Supabase) agar riwayat pemindaian tersimpan aman di akun masing-masing.

## 2. Navigasi Utama (Tab Bar)
Berikut adalah rincian konten untuk setiap menu di dalam *Tab Bar* bawah:

### A. Dashboard (Beranda)
*   **Sapaan & Cuaca:** Menampilkan nama pengguna dan info cuaca (cuaca lembab sangat berpengaruh pada penyebaran jamur *Black Pod Rot*).
*   **Ringkasan Statistik:** Grafik atau kartu info (*card*) yang menunjukkan jumlah total buah yang telah di-scan bulan ini, serta persentase kondisi kebun (Sehat vs Sakit).
*   **Akses Cepat:** *Banner* edukasi harian atau pintasan cepat untuk membuka kamera.

### B. Riwayat (History)
*   **Daftar Scan AI:** Menampilkan riwayat (*list*) foto-foto buah kakao yang pernah di-scan sebelumnya, diurutkan berdasarkan waktu (terbaru di atas).
*   **Detail Diagnosis:** Jika riwayat ditekan, muncul halaman detail berisi: Foto resolusi tinggi, hasil diagnosis (Black Pod Rot / Pod Borer / Sehat), akurasi keyakinan AI (%), dan rekomendasi tindakan awal.

### C. Scan / Kamera (Fitur Inti - Offline AI)
*   **Kamera Real-time:** Halaman utama tempat *Machine Learning* beraksi secara *offline* menggunakan arsitektur C++ JSI (*react-native-vision-camera*).
*   **Overlay Diagnosis:** Deteksi visual langsung (*Live UI*) di layar yang menunjukkan hasil tebakan AI seketika saat kamera diarahkan ke buah kakao.
*   **Tombol Jepret & Simpan:** Tombol untuk mengabadikan gambar dan menyimpan hasil diagnosis ke *database* Riwayat.

### D. Ensiklopedia (Edukasi Kakao)
*   **Katalog Penyakit & Hama:** Berisi literatur teknis yang berkaitan dengan 3 kelas AI kita:
    1.  **Black Pod Rot:** Penjelasan jamur *Phytophthora*, cara mencegah penyebaran, dan daftar fungisida yang direkomendasikan.
    2.  **Pod Borer (PBK):** Penjelasan hama penggerek, siklus hidupnya, dan teknik penyelubungan (*sarungisasi*) buah.
    3.  **Kakao Sehat:** Standar fisik dan perawatan kakao bermutu.

### E. Berita (Agrikultur)
*   **Artikel Pertanian:** *Feed* berisi artikel terbaru, tips perawatan, pemangkasan, atau pemupukan kakao.
*   **Info Pasar:** (Opsional) Informasi harga biji kakao atau tengkulak terdekat.

### F. Profil
*   **Data Pengguna:** Nama, email, dan detail luas perkebunan.
*   **Pengaturan Sistem:** Pilihan bahasa aplikasi (Indonesia/Daerah), dan status versi model AI.
*   **Tentang:** Info pembuat aplikasi (kredit Skripsi) dan panduan penggunaan aplikasi.
*   **Logout:** Keluar dari sesi.