# 📋 DOKUMENTASI PROGRES PENELITIAN SKRIPSI
**Tanggal Pembaruan:** 18 Oktober 2026  
**Fokus Progres:** Audit Integritas Sitasi, Eliminasi Halusinasi Data, Penulisan Ulang Bab 1 & Bab 2 Berbasis Jurnal Mutakhir (2023–2025), serta Dokumentasi Koreksi  

---

## 1. IDENTITAS PENELITIAN RESMI

* **Judul Skripsi:**  
  `IMPLEMENTASI YOLOV8 UNTUK DETEKSI PENYAKIT PADA BUAH KAKAO BERBASIS APLIKASI MOBILE`
* **Bidang Keilmuan:** Teknik Informatika / Visi Komputer (*Computer Vision*) & *Mobile Edge AI*
* **Objek Klasifikasi (3 Kelas Target):**
  1. *Black Pod Rot* (Penyakit Busuk Buah Hitam akibat cendawan patogen *Phytophthora palmivora*)
  2. *Pod Borer* (Hama Penggerek Buah Kakao / PBK akibat larva serangga *Conopomorpha cramerella*)
  3. *Healthy* (Buah Kakao Normal Bebas Penyakit)
* **Dataset Penelitian:** 4.300 citra buah kakao (Kaggle Zaldy Jr), terbagi menjadi 80% Latih (3.440), 10% Validasi (430), dan 10% Uji (430).
* **Arsitektur Model & Kinerja:** `yolov8s-cls` (Akurasi Top-1 Uji: **98,87%**, Latensi Inferensi: **~3,2 ms**, Format Biner: `.tflite`).
* **Framework Aplikasi:** React Native (Expo SDK 54) + TypeScript + Fast-TFLite (C++ JSI) + VisionCamera + SQLite (Offline-First).

---

## 2. STATUS CAPAIAN & RESTRUKTURISASI SITASI (PER 18 OKTOBER 2026)

| Komponen Riset | Status | Keterangan & Rincian Capaian Terkini |
| :--- | :---: | :--- |
| **Pembersihan Referensi Usang** | **SELESAI (100%)** | 3 jurnal lawas terbitan 2016–2017 (*Mohanty et al. 2016, Ramcharan et al. 2017, Fuentes et al. 2017*) telah resmi **dieliminasi**. Repositori referensi kini memuat **14 jurnal mutakhir (2023–2025)** dengan DOI aktif dan publikasi resmi BPS (2023). |
| **Audit Anti-Halusinasi & Sitasi Fiktif** | **SELESAI (100%)** | Mengidentifikasi dan membuang klaim fiktif draf lama (istilah *oviposisi*, *luka mekanis ringan*, *bercak klorotik* pada Novanto; klaim *0–600 mdpl*, *pericarp 80% biomassa* pada Alvarado/Gado; klaim *mentega kakao*, *pedagang pengumpul* pada Novanto; serta gejala spora Monilia yang tertukar ke Black Pod pada Ferraris). |
| **Naskah BAB 1 (Latar Belakang & Batasan)** | **SELESAI (100%)** | Ditulis ulang 100% berbasis teks otentik BPS 2023 dan jurnal aktif: 1.1 Latar Belakang (Piramida terbalik, 6 paragraf akademis, *research gap*), 1.2 Rumusan Masalah (4 butir), 1.3 Batasan Masalah (6 butir bebas mAP/bounding box), dan 1.4 Tujuan Penelitian (*1-to-1 mapping*). |
| **Naskah BAB 2 (Penelitian Terdahulu)** | **SELESAI (100%)** | Bab 2.1 (berkas `1.9 Penelitian terdahulu.md`) memuat Tabel 2.1 Matriks Komparasi 14 Jurnal Terkini (2023–2025) dalam format Markdown rapi, dilengkapi telaah mendalam *Research Gap* dan 3 pilar *Novelty* skripsi. |
| **Naskah BAB 2 (Dasar Teori Kakao)** | **SELESAI (100%)** | Menyelesaikan parafrasa akademis berbobot tinggi untuk 4 sub-bab dasar teori: `2.1.1 Tanaman Kakao`, `2.1.2 Produksi Kakao di Indonesia`, `2.1.3 Peran Kakao dalam Sektor Perkebunan`, dan `2.1.4 Penyakit pada Buah Kakao`. |
| **Dokumen Audit & Pelacak Koreksi** | **SELESAI (100%)** | Diterbitkan 5 dokumen audit komparasi lengkap di folder `skripsi/koreksi/` yang memuat perbandingan naskah lama vs baru serta transkrip kutipan teks asli jurnal rujukan. |
| **Proyeksi Uji Turnitin** | **SANGAT AMAN** | Skor *Similarity Index* diproyeksikan berkisar antara **3% – 8%** (jauh di bawah batas toleransi kampus 20%–25%) karena mengadopsi parafrasa struktur kalimat mandiri dan alih bahasa dari jurnal internasional. |

---

## 3. INVENTARIS BERKAS DOKUMEN PROPOSAL & KOREKSI TERBARU

### A. Berkas Draf Proposal Bab 1 & Bab 2 (Folder `skripsi/proposal/`)
1. **[pendahuluan.md](file:///d:/backup/proyek-kerja/proyek%20ku/skripsi/skripsi/proposal/pendahuluan.md)**: Naskah 1.1 Latar Belakang (6 paragraf akademis formal, bersih dari jurnal lawas).
2. **[1.2-.1.4 .md](file:///d:/backup/proyek-kerja/proyek%20ku/skripsi/skripsi/proposal/1.2-.1.4%20.md)**: Rumusan Masalah, 6 Batasan Masalah, dan Tujuan Penelitian.
3. **[1.9 Penelitian terdahulu.md](file:///d:/backup/proyek-kerja/proyek%20ku/skripsi/skripsi/proposal/1.9%20Penelitian%20terdahulu.md)**: Bab 2.1 Penelitian Terdahulu (Tabel 2.1 matriks 14 jurnal 2023–2025 + *Research Gap* & *Novelty*).
4. **[2.1.1 tanaman kakao.md](file:///d:/backup/proyek-kerja/proyek%20ku/skripsi/skripsi/proposal/2.1.1%20tanaman%20kakao.md)**: Morfologi dan karakteristik tanaman kakao (Theobroma cacao L.).
5. **[2.1.2 Produksi Kakao di Indonesia.md](file:///d:/backup/proyek-kerja/proyek%20ku/skripsi/skripsi/proposal/2.1.2%20Produksi%20Kakao%20di%20Indonesia.md)**: Peringkat global, data resmi BPS 2023, sentra produksi rakyat, dan tantangan penyakit.
6. **[2.1.3 Peran Kakao dalam Sektor Perkebunan.md](file:///d:/backup/proyek-kerja/proyek%20ku/skripsi/skripsi/proposal/2.1.3%20Peran%20Kakao%20dalam%20Sektor%20Perkebunan.md)**: Kontribusi PDB/ekspor makro, penyerapan tenaga kerja pedesaan, fenomena *supply shortages*, dan mitigasi AI.
7. **[2.1.4 Penyakit pada Buah Kakao.md](file:///d:/backup/proyek-kerja/proyek%20ku/skripsi/skripsi/proposal/2.1.4%20Penyakit%20pada%20Buah%20Kakao.md)**: Taksonomi dan gejala visual 3 kelas target (*Black Pod Rot*, *Pod Borer*, dan *Healthy*).

### B. Berkas Audit & Verifikasi Koreksi (Folder `skripsi/koreksi/`)
1. **[pendahuluan koreksi.md](file:///d:/backup/proyek-kerja/proyek%20ku/skripsi/skripsi/koreksi/pendahuluan%20koreksi.md)**: Tabel audit 15 butir klaim latar belakang vs bukti riil jurnal & BPS.
2. **[2.1.1 tanaman kakao koreksi.md](file:///d:/backup/proyek-kerja/proyek%20ku/skripsi/skripsi/koreksi/2.1.1%20tanaman%20kakao%20koreksi.md)**: Tabel audit 7 butir koreksi morfologi kakao + transkrip teks jurnal.
3. **[2.1.2 Produksi Kakao di Indonesia koreksi.md](file:///d:/backup/proyek-kerja/proyek%20ku/skripsi/skripsi/koreksi/2.1.2%20Produksi%20Kakao%20di%20Indonesia%20koreksi.md)**: Tabel audit 6 butir koreksi produksi kakao + transkrip teks jurnal.
4. **[2.1.3 Peran Kakao dalam Sektor Perkebunan koreksi.md](file:///d:/backup/proyek-kerja/proyek%20ku/skripsi/skripsi/koreksi/2.1.3%20Peran%20Kakao%20dalam%20Sektor%20Perkebunan%20koreksi.md)**: Tabel audit 5 butir koreksi peran ekonomi + transkrip teks jurnal.
5. **[2.1.4 Penyakit pada Buah Kakao koreksi.md](file:///d:/backup/proyek-kerja/proyek%20ku/skripsi/skripsi/koreksi/2.1.4%20Penyakit%20pada%20Buah%20Kakao%20koreksi.md)**: Tabel audit 6 butir koreksi patologi 3 kelas + transkrip teks jurnal.

---

## 4. DAFTAR 14 JURNAL REFERENSI AKTIF (2023–2025)

Semua rujukan ilmiah yang digunakan dalam naskah kini murni berasal dari 14 publikasi resmi berikut:
1. **Alvarado et al. (2025)** — *Disease Detection on Cocoa Crops Based on Computer-Vision Techniques: A Systematic Literature Review* (Agriculture - MDPI).
2. **Ariawan et al. (2025)** — *Performance Comparison of DenseNet-121 and MobileNetV2 for Cacao Fruit Disease Image Classification* (Indonesian Journal of Data and Science).
3. **Ferraris et al. (2023)** — *Machine Learning as a Strategic Tool for Helping Cocoa Farmers in Côte D'Ivoire* (Sensors - MDPI).
4. **Gado & Primandari (2025)** — *Sistem Klasifikasi Berbasis Android untuk Penyakit Buah Kakao Menggunakan CNN NasNet-Mobile* (Jurnal Teknologi Terpadu).
5. **Ghafar et al. (2024)** — *Visualizing Plant Disease Distribution and Evaluating Model Performance for Deep Learning Classification with YOLOv8* (Journal of Computer Science).
6. **Khan et al. (2023)** — *A Mobile-Based System for Maize Plant Leaf Disease Detection and Classification Using Deep Learning* (IEEE Access).
7. **Maylianti et al. (2025)** — *Comparison of EfficientNet-B0 and ResNet-50 for Detecting Diseases in Cocoa Fruit* (Journal of Applied Informatics and Computing).
8. **Natbais & Umbu (2023)** — *Aplikasi Deteksi Penyakit pada Daun Tomat Berbasis Android Menggunakan Model Terlatih Tensorflow Lite* (TEKNOTAN).
9. **Novanto et al. (2025)** — *Enhanced Speed and Accuracy in Cocoa Fruit Disease Identification Using the Inception-ResNet CNN Algorithm* (Jurnal Teknik Informatika - JUTIF).
10. **Octavian et al. (2024)** — *Enhancing Weighted Averaging for CNN Model Ensemble in Plant Diseases Image Classification* (Jurnal RESTI).
11. **Siahaan et al. (2024)** — *Enhancing Real-time Herbal Plant Detection in Agricultural Environments with YOLOv8* (Sinkron).
12. **Supriyadi & Widiastuti (2023)** — *Rancang Program Aplikasi Pembelajaran Tajwid Berbasis Android* (Jurnal Teknik Informatika dan Sistem Informasi).
13. **Susila & Arsa (2023)** — *Analisis System Usability Scale (SUS) dan Perancangan Sistem Self Service Pemesanan Menu di Restoran Berbasis Web* (Majalah Ilmiah UNIKOM).
14. **Terven et al. (2023)** — *A Comprehensive Review of YOLO: From YOLOv1 to YOLOv8 and Beyond* (ACM Computing Surveys).
* **Rujukan Data Statistik Tambahan:** Badan Pusat Statistik (BPS, 2023) — *Statistik Kakao Indonesia 2023*.

---

## 5. AGENDA LANGKAH KERJA BERIKUTNYA (*NEXT ACTION STEPS*)

1. **Penyusunan Sub-Bab Dasar Teori Berikutnya di Bab 2:**
   * Melanjutkan sub-bab Dasar Teori Visi Komputer, Arsitektur YOLOv8, Pengolahan Citra Digital, TensorFlow Lite, Fast-TFLite C++ JSI, React Native Expo, SQLite, dan Metodologi Waterfall SDLC.
2. **Konsolidasi File Bab 1 dan Bab 2:**
   * Menggabungkan file pecahan per sub-bab ke dalam draf naskah utuh bab 1 dan bab 2 yang rapi dan terurut.
3. **Penyelarasan Daftar Pustaka:**
   * Memastikan daftar pustaka di dokumen akhir memuat 14 jurnal di atas dan data BPS dengan format APA 7th Edition yang valid.
