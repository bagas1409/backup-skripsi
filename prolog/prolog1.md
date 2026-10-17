

Berikut adalah penjelasan mendalam dari masing-masing poin penelitian **"Development of Cocoa Pod Rot Disease Identification Model Using YOLO-v9"**:

### 1. Fokus Penelitian: Mengatasi "Kanker" pada Kebun Kakao

Penyakit Busuk Buah Kakao (*Cocoa Pod Rot* / *Black Pod*) adalah salah satu ancaman terbesar bagi petani karena disebabkan oleh patogen yang menyebar dengan sangat cepat, terutama di musim hujan. Penyakit ini bisa menghancurkan panen dalam waktu singkat.

* **Tujuan utama penelitian ini:** Membuat sistem "alarm dini". Jika penyakit ini bisa dideteksi sejak awal (saat gejalanya masih kecil/samar), petani bisa langsung mengisolasi atau mengobati buah tersebut sebelum menular ke seluruh kebun.

### 2. Metode: Menggunakan YOLO-v9 (Kamera Cerdas Berbasis AI)

Penelitian ini menggunakan **YOLO-v9** (*You Only Look Once version 9*). Untuk memahaminya, bayangkan algoritma ini sebagai mata dan otak buatan.

* **Deep Learning & Object Detection:** Ini adalah cabang dari *Machine Learning*. Sistem diajarkan untuk tidak hanya "melihat" sebuah gambar, tetapi juga mengenali dan melokalisasi (memberi kotak pembatas pada) objek tertentu di dalam gambar tersebut.
* **Mengapa YOLO?** YOLO sangat terkenal di dunia *Computer Vision* karena kemampuannya mendeteksi objek secara *real-time* (sangat cepat dan akurat). Versi 9 (YOLO-v9) adalah salah satu generasi yang sangat mutakhir (terbaru), yang memiliki arsitektur jauh lebih pintar dalam menangkap detail halus dibandingkan versi-versi sebelumnya.

### 3. Hasil: Akurasi Tinggi Melalui Proses Pembelajaran

Pada bagian hasil, ada beberapa istilah teknis metrik evaluasi AI yang menunjukkan bahwa model ini sangat sukses:

* **50 Epoch:** *Epoch* adalah siklus pembelajaran. "Pelatihan 50 epoch" berarti komputer disuruh mempelajari ribuan foto buah kakao (baik yang sehat maupun yang busuk) secara berulang-ulang sebanyak 50 kali putaran. Di setiap putarannya, sistem akan terus memperbaiki kesalahannya hingga menjadi pintar.
* **Presisi (Precision) 99%:** Presisi mengukur seberapa akurat tebakan sistem. Angka 99% berarti jika sistem ini menunjuk sebuah buah dan berkata, *"Ini terinfeksi busuk buah"*, maka sistem tersebut 99% benar dan bisa dipercaya. Sangat minim "alarm palsu" (*False Positive*).
* **Recall 99%:** *Recall* mengukur seberapa peka sistem tersebut dalam menemukan *semua* buah yang sakit. Angka 99% berarti dari 100 buah kakao yang benar-benar sakit di kebun, sistem berhasil menemukan 99 di antaranya. Sangat minim kasus di mana buah sakit terlewatkan (*False Negative*).

### 4. Implikasi dan Sumber Publikasi

Penelitian ini dipublikasikan oleh **IIETA pada tahun 2025**. Fakta bahwa teknologi ini sudah mencapai presisi dan recall 99% menunjukkan bahwa sistem ini sudah sangat siap untuk diimplementasikan ke dalam aplikasi *smartphone* atau kamera *drone* pertanian untuk membantu petani secara langsung.

---

