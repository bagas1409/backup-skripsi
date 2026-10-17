# 📋 DOKUMENTASI PROGRES PENELITIAN SKRIPSI
**Tanggal Pembaruan:** 15 Oktober 2026  
**Topik:** Implementasi Model Deep Learning YOLOv8 pada Buah Kakao Berbasis Mobile  

---

## 1. IDENTITAS PENELITIAN RESMI

* **Judul Skripsi:**  
  `IMPLEMENTASI YOLOV8 UNTUK DETEKSI PENYAKIT PADA BUAH KAKAO BERBASIS APLIKASI MOBILE`
* **Bidang Keilmuan:** Teknik Informatika / Visi Komputer (*Computer Vision*) & *Mobile Edge AI*
* **Objek Klasifikasi (3 Kelas):**
  1. *Black Pod Rot* (Penyakit Busuk Buah Hitam akibat cendawan *Phytophthora palmivora*)
  2. *Pod Borer* (Hama Penggerek Buah Kakao / PBK akibat larva *Conopomorpha cramerella*)
  3. *Healthy* (Buah Kakao Sehat / Normal)
* **Dataset:** 4.300 citra resolusi $1080 \times 1080$ piksel (Repositori Kaggle oleh Zaldy Jr)
* **Partisi Data:** 80% Latih (3.440 citra), 10% Validasi (430 citra), 10% Uji (430 citra)

---

## 2. STATUS CAPAIAN RIIL (PER 15 OKTOBER 2026)

| Komponen Riset | Status | Keterangan & Rincian Capaian |
| :--- | :---: | :--- |
| **Model Deep Learning (Colab)** | **SELESAI (100%)** | Model `yolov8s-cls` berhasil dilatih 50 epoch. Akurasi data uji independen: **98,87% (Top-1)**, latensi inferensi **~3,2 ms**, confidence inferensi acak mencapai **99,99%**. Format biner dikonversi ke `.tflite`. |
| **Arsitektur Aplikasi Mobile** | **SELESAI (100%)** | Kode dasar React Native Expo SDK 54 + TypeScript + NativeWind v4. Pustaka kamera native `react-native-vision-camera` v5.2.2 dan engine inferensi C++ JSI `react-native-fast-tflite` v3.0.1 (Offline-First). Penyimpanan riwayat lokal via `expo-sqlite`. |
| **Rancangan Fitur Aplikasi** | **SELESAI (100%)** | Struktur navigasi 6 menu: Dashboard, Scan AI Kamera Real-time, Riwayat Diagnosis SQLite, Ensiklopedia/Katalog Penyakit Kakao, Berita Pertanian, dan Profil Pengguna. |
| **Naskah Proposal BAB I** | **SELESAI (100%)** | Lengkap: 1.1 Latar Belakang (Piramida terbalik, data BPS, research gap 17 jurnal), 1.2 Rumusan Masalah, 1.3 Batasan Masalah (bebas mAP), 1.4 Tujuan, 1.5 Manfaat, **1.6 Metode Penelitian (1.6.1 s.d. 1.6.5)**, dan 1.7 Sistematika Penulisan. |
| **Naskah Proposal BAB II** | **SELESAI (100%)** | Lengkap: 2.1 Kajian Pustaka (Tabel 2.1 komparasi 17 jurnal & sintesis novelty), 2.2 Dasar Teori (20 subbab lengkap + formula matematika), dan 2.3 Hipotesis Penelitian ($H_0$ & $H_a$). |
| **Naskah Proposal BAB III** | **SELESAI (100%)** | Lengkap: 3.1 Metode Pengumpulan Data, 3.2 Alat & Bahan (Tabel HW, SW, Partisi Data), 3.3 Tahapan Waterfall SDLC, Pemodelan UML (Use Case, Activity, Sequence, Class Diagram), Rencana Black-Box Testing (9 kasus uji), dan 3.4 Jadwal Penelitian 6 Bulan. |
| **Daftar Pustaka & Verifikasi** | **SELESAI (100%)** | 17 Sumber referensi (16 jurnal Google Drive + BPS 2023) format APA 7th Edition dengan tautan DOI aktif. Dilengkapi **Tabel 3.7 Verifikasi Pemenuhan Sitasi (1-to-1 mapping)**. |

---

## 3. LOKASI BERKAS PENTING DALAM WORKSPACE

1. **Naskah Proposal Siap Salin (Bab I s.d. Bab III):**  
   📂 `d:\backup\proyek-kerja\proyek ku\skripsi\prompt\hasil prompt\proposal 1.md`  
   *(Dokumen utama yang sudah dilengkapi subbab 1.6 Metode Penelitian dan penomoran 1.7 Sistematika Penulisan).*
2. **Dokumentasi Sintaks & Training Google Colab:**  
   📂 `d:\backup\proyek-kerja\proyek ku\skripsi\dokumentasi\dokumentasi_penelitian_colab.md`  
   *(Dokumentasi per cell training Python/Ultralytics).*
3. **Spesifikasi Arsitektur & Antarmuka Aplikasi:**  
   📂 `d:\backup\proyek-kerja\proyek ku\skripsi\arsitektur aplikasi\point1.md`  
   *(Peta fitur lengkap aplikasi mobile).*
4. **Master Prompt Cadangan:**  
   📂 `d:\backup\proyek-kerja\proyek ku\skripsi\prompt\newPrompt.md`  
   *(Prompt panduan terstruktur).*

---

## 4. AGENDA LANGKAH BERIKUTNYA (*NEXT ACTION STEPS*)

1. **Pemindahan ke Microsoft Word (`.docx`):**
   * Mengatur margin standar kampus (biasanya 4-4-3-3 cm) dan font Times New Roman 12 pt / Arial 11 pt.
   * Mengubah rumus matematika format LaTeX ke Word Equation (`Alt + =`).
2. **Visualisasi Grafis Diagram UML:**
   * Menggambar diagram UML (Use Case, Activity, Sequence, Class Diagram) ke **Draw.io** berdasarkan skema ASCII yang sudah disediakan di Bab III agar menjadi gambar beresolusi tinggi.
3. **Penyusunan Lembar Awal:**
   * Melengkapi Halaman Judul/Cover, Lembar Pengesahan, Kata Pengantar, Abstrak, dan Lembar Persembahan yang sudah disiapkan sebelumnya.
4. **Bimbingan Pra-Seminar Proposal (Sempro):**
   * Mengajukan draf Bab I - III ini ke Dosen Pembimbing untuk mendapatkan tanda tangan persetujuan maju seminar proposal.
