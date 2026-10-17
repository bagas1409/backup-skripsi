# PROJECT_CONTEXT.md: CocoaCare (Deteksi Penyakit Kakao Berbasis AI)

## 1. Project Overview
* **Nama Proyek:** CocoaCare (cocoa-detector) - Proyek Skripsi / Penelitian Agrikultur AI
* **Tujuan Proyek:** Membantu petani kakao dan penyuluh pertanian melakukan deteksi dini terhadap penyakit dan hama buah kakao secara *real-time* dan *offline* langsung melalui perangkat seluler pintar (*smartphone*), sehingga penyebaran patogen dapat dicegah sedini mungkin dan kerugian hasil panen dapat diminimalisir.
* **Fokus Klasifikasi:**
  1. `Black Pod Rot` (*Phytophthora palmivora* / Busuk Buah Hitam)
  2. `Pod Borer` (*Conopomorpha cramerella* / Penggerek Buah Kakao - PBK)
  3. `Healthy` (Buah Kakao Sehat)
* **Teknologi Utama:**
  * **Machine Learning:** Ultralytics YOLOv8 (arsitektur `yolov8s-cls`), akurasi pengujian Top-1 98.87%, model weight: `model/best.pt`.
  * **Mobile Framework:** React Native 0.81.5 dengan Expo SDK 54 (New Architecture ready, Expo Router v6).
  * **Styling:** NativeWind v4 (TailwindCSS v3.4).
  * **Mobile Computer Vision & Edge AI:** `react-native-vision-camera` (v5.2.2), `react-native-fast-tflite` (v3.0.1), `react-native-worklets-core` (v1.6.3).
  * **Penyimpanan Lokal:** `expo-sqlite` (v16.0.10) database `cocoa.db`.

---

## 2. Features

### Fitur Utama (Core)
* **Offline Real-Time AI Detection (Scan AI):** Antarmuka kamera dengan overlay visual pembidik buah kakao untuk mendeteksi kondisi buah secara instan.
* **Autentikasi Pengguna:** Pendaftaran (*register*) dan masuk (*login*) akun pengguna yang tersimpan di database lokal.
* **Riwayat Diagnosis (History):** Log riwayat pemindaian buah kakao lengkap dengan tanggal, waktu, tingkat keyakinan (*confidence score*), dan status kondisi.
* **Dashboard Interaktif:** Tampilan ringkasan statistik kesehatan kebun bulan berjalan, indikator cuaca, dan pintasan cepat pemindaian.

### Fitur Pendukung
* **Ensiklopedia Penyakit & Hama:** Informasi literatur botani mengenai patogen *Black Pod Rot*, hama *Pod Borer*, gejala, serta SOP rekomendasi penanganan sanitasi dan sarungisasi.
* **Warta Pertanian (Berita):** Informasi edukasi budidaya kakao dan artikel tren harga biji kakao.
* **Profil Pengguna:** Manajemen profil petani, pengaturan bahasa, dan informasi versi model AI.

---

## 3. User Roles & Permissions
* **Role Saat Ini:** `Petani / Pengguna Aplikasi (Single User Role)`
* **Permissions:**
  * Akses kamera (`android.permission.CAMERA` - perlu dipastikan di manifest/app.json).
  * Akses media penyimpanan untuk menyimpan atau memuat foto buah kakao.
  * Membaca dan menulis riwayat pemindaian lokal (`cocoa.db`).

---

## 4. Database Architecture

### Embedded Database: SQLite (`expo-sqlite`)
* **File Database:** `cocoa.db` (diinisialisasi otomatis saat aplikasi pertama kali dijalankan via `database/db.ts`).
* **Tabel `users`:**
  * `id` INTEGER PRIMARY KEY AUTOINCREMENT
  * `name` TEXT NOT NULL
  * `email` TEXT UNIQUE NOT NULL
  * `password` TEXT NOT NULL (Catatan: saat ini plaintext, perlu di-hash untuk keamanan produksi)
* **Tabel `scans`:**
  * `id` INTEGER PRIMARY KEY AUTOINCREMENT
  * `user_id` INTEGER NOT NULL (Foreign Key ke `users(id)`)
  * `status` TEXT NOT NULL
  * `confidence` REAL NOT NULL
  * `date_time` TEXT NOT NULL
  * `image_uri` TEXT NULLABLE

### PostgreSQL / Cloud Database Status
* **Status:** `UNKNOWN / NEED USER INPUT`
* Berdasarkan dokumen arsitektur (`arsitektur aplikasi/point1.md`), terdapat rencana integrasi database cloud (seperti Supabase / PostgreSQL atau Firebase). Namun, pada source code repositori saat ini, **tidak ditemukan migration, schema, konfigurasi ORM (Prisma/Drizzle/TypeORM), maupun docker-compose PostgreSQL**.

---

## 5. Backend Architecture
* **Status Saat Ini:** `Client-Side / Embedded Architecture (Serverless Local)`
* Logika data, autentikasi sesi dasar, dan inferensi model ML dieksekusi langsung di perangkat (*edge computing*) tanpa ketergantungan koneksi internet (*offline-first*).

---

## 6. Frontend Architecture
* **Framework:** React Native + Expo Router File-Based Routing.
* **Struktur Navigasi:**
  * Root Layout: `app/_layout.tsx` (Theme provider, splash screen handler, database initialization).
  * Auth Stack: `app/(auth)/` (`login.tsx`, `register.tsx`).
  * Tab Bar Navigation: `app/(tabs)/` (`index.tsx`, `scan.tsx`, `riwayat.tsx`, `ensiklopedia.tsx`, `berita.tsx`, `profil.tsx`).
* **Design System:** Utility-first styling via NativeWind Tailwind CSS, emerald/nature-themed color palette.

---

## 7. Environment Variables
* Tidak ada variabel environment `.env` sensitif yang saat ini terdaftar pada codebase React Native / Expo.
* Seluruh dependensi berjalan secara lokal dan offline.

---

## 8. Development & How to Run

### Prasyarat
* Node.js LTS (v18+ atau v20+)
* Java Development Kit (JDK 17) & Android SDK (untuk build native)
* Android Studio & Emulator atau Perangkat Android Fisik (disarankan dengan USB Debugging aktif)

### Langkah Menjalankan
1. Masuk ke direktori mobile:
   ```bash
   cd cocoa-detector
   ```
2. Jalankan Expo development server:
   ```bash
   npm start
   ```
3. Menjalankan di perangkat Android:
   ```bash
   npm run android
   ```

---

## 9. Known Issues & Technical Debt
1. **Model Format Gap:** Model PyTorch `model/best.pt` belum diekspor ke format `.tflite` untuk dimasukkan ke folder `assets/model/` aplikasi mobile.
2. **Kamera & Inferensi Masih Dimock:** Kode pada `app/(tabs)/scan.tsx` saat ini dikomentari karena menunggu build native APK dengan modul C++ VisionCamera & Fast-TFLite.
3. **Riwayat Scan Masih Menggunakan Mock Data:** File `app/(tabs)/riwayat.tsx` masih merender array statis `DUMMY_DATA` alih-alih melakukan query `SELECT * FROM scans` dari `expo-sqlite`.
4. **Keamanan Kredensial:** Password pengguna disimpan dalam format plaintext di SQLite tanpa enkripsi (e.g., bcrypt/Argon2).
5. **Konfigurasi Plugin Kamera di `app.json`:** Perlu penambahan konfigurasi plugin `react-native-vision-camera` dan izin permission `CAMERA` di `app.json` sebelum melakukan build ulang.

---

## 10. Future Improvements
1. Konversi model `best.pt` ke `cocoa_classifier.tflite` menggunakan script Python Ultralytics export.
2. Menghubungkan query riwayat scan nyata dengan database SQLite.
3. Menambahkan fitur penyimpanan foto hasil jepretan ke memori lokal file system perangkat (`expo-file-system`).
4. Opsional: Sinkronisasi cloud PostgreSQL / Supabase jika aplikasi ingin dapat diakses lintas perangkat dengan akun terpusat.
