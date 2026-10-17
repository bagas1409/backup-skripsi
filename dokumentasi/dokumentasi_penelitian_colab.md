# Dokumentasi Penelitian: Klasifikasi Penyakit Buah Kakao Menggunakan YOLOv8

## 1. Ikhtisar Penelitian
**Tujuan Penelitian:** Membangun sistem kecerdasan buatan berbasis *Computer Vision* untuk mendeteksi secara dini penyakit pada buah kakao guna mencegah penyebaran infeksi patogen dan hama yang dapat menghancurkan panen.

**Metode yang Digunakan:** Algoritma *Deep Learning* YOLOv8 (versi klasifikasi / `yolov8s-cls`) dipilih karena kemampuannya yang sangat ringan, cepat (waktu inferensi ~3.2ms), dan sangat akurat.

**Dataset:** Diambil dari repositori publik Kaggle (`zaldyjr/cacao-diseases`). Terdiri dari sekitar 4.300 citra dengan ukuran 1080x1080 piksel.

**Batasan Masalah:**
Model ini dilatih dan dibatasi hanya untuk mengklasifikasikan tiga (3) kondisi utama pada buah kakao berdasarkan ketersediaan data empiris, yaitu:
1. **Black Pod Rot** (Busuk Buah Hitam akibat infeksi patogen)
2. **Pod Borer** (Hama Penggerek Buah Kakao)
3. **Healthy** (Buah Kakao Sehat)
Kelainan di luar ketiga kelas tersebut (misalnya *Vascular Streak Dieback* atau kanker batang) berada di luar cakupan sistem pendeteksian ini.

**Hasil Pengujian:**
Dari hasil pengujian (*evaluation*) pada dataset uji yang belum pernah dilihat oleh mesin (data test), model berhasil mencapai tingkat akurasi tinggi sebesar **98.87% (Top-1 Accuracy)**. Pengujian manual (inferensi) dengan gambar acak eksternal juga mencapai tingkat keyakinan (*confidence*) hingga **99.99%**.

---

## 2. Dokumentasi Sintaks Google Colab

Berikut adalah penjelasan akademis dan teknis per baris kode (*syntax*) dari proses *Machine Learning* yang dijalankan di dalam lingkungan Google Colab. Dokumentasi ini dapat Anda sadur langsung untuk dimasukkan ke dalam laporan Skripsi Anda.

### Cell 1: Mengunduh Dataset dari Repositori Eksternal (Kaggle)
**Tujuan:** Mengotomatiskan pengambilan data mentah dari server pihak ketiga ke dalam memori Google Colab (sekitar 4.300 gambar).
```python
# Menginstal library kagglehub untuk koneksi tanpa otentikasi API manual
!pip install kagglehub -q

import kagglehub
import shutil
import os

print("Mengunduh dataset dari Kaggle...")
# Perintah mengekstraksi dataset secara langsung berdasarkan ID Repositori
path_asli = kagglehub.dataset_download("zaldyjr/cacao-diseases")

# Mendefinisikan direktori kerja (Working Directory) di memori lokal Colab
lokasi_baru = '/content/dataset'

# Membersihkan (remove) direktori jika script pernah dijalankan sebelumnya
if os.path.exists(lokasi_baru):
    shutil.rmtree(lokasi_baru)

# Menyalin secara struktural (copytree) seluruh data ke direktori yang mudah diakses
shutil.copytree(path_asli, lokasi_baru)
print("Dataset berhasil dipindahkan ke /content/dataset")
```

### Cell 2: Preprocessing dan Pemisahan Dataset (*Data Splitting*)
**Tujuan:** Algoritma *Deep Learning* menuntut agar data dipisah menjadi Data Latih (Train) untuk belajar, Validasi (Val) untuk kalibrasi selama belajar, dan Uji (Test) untuk mengukur kecerdasan murni di akhir ujian. Script ini menelusuri ribuan gambar acak dan mendistribusikannya secara matematis (80:10:10).
```python
import os
import glob
import shutil
import random

sumber_dataset = "/content/dataset"
tujuan_dataset = "/content/dataset_split"

# Melacak semua tipe file gambar secara rekursif hingga ke sub-folder paling dalam
semua_gambar = glob.glob(sumber_dataset + "/**/*.jpg", recursive=True) + \
               glob.glob(sumber_dataset + "/**/*.jpeg", recursive=True) + \
               glob.glob(sumber_dataset + "/**/*.png", recursive=True) + \
               glob.glob(sumber_dataset + "/**/*.JPG", recursive=True)

# Mempersiapkan folder / direktori yang steril
if os.path.exists(tujuan_dataset):
    shutil.rmtree(tujuan_dataset)
    
# Menyortir gambar berdasarkan nama kelas (Penyakit 1, Penyakit 2, dan Sehat)
kelas_dict = {}
for path_gambar in semua_gambar:
    nama_kelas = os.path.basename(os.path.dirname(path_gambar))
    if nama_kelas not in kelas_dict:
        kelas_dict[nama_kelas] = []
    kelas_dict[nama_kelas].append(path_gambar)
    
# Tahapan Ekstraksi (Pemisahan 80% Train, 10% Val, 10% Test)
for nama_kelas, daftar_gambar in kelas_dict.items():
    random.shuffle(daftar_gambar) # Pengacakan urutan agar model tidak menghafal urutan data
    
    total = len(daftar_gambar)
    batas_train = int(total * 0.8)
    batas_val = int(total * 0.9)
    
    grup_split = {
        'train': daftar_gambar[:batas_train],
        'val': daftar_gambar[batas_train:batas_val],
        'test': daftar_gambar[batas_val:]
    }
    
    # Eksekusi pemindahan file fisik ke dalam klasifikasi yang sesuai standar YOLO
    for nama_split, file_list in grup_split.items():
        folder_tujuan = os.path.join(tujuan_dataset, nama_split, nama_kelas)
        os.makedirs(folder_tujuan, exist_ok=True)
        for f in file_list:
            shutil.copy(f, os.path.join(folder_tujuan, os.path.basename(f)))
```

### Cell 3: Inisialisasi Arsitektur AI (Ultralytics)
**Tujuan:** Mengunduh modul utama untuk pengolahan algoritma YOLO.
```python
# Memasang modul ultralytics secara tersembunyi tanpa memenuhi layar log (-q)
!pip install ultralytics -q
import ultralytics

# Memverifikasi kesiapan lingkungan, versi Python, Torch, dan perangkat GPU
ultralytics.checks()
```

### Cell 4: Proses Pembelajaran Mesin (*Training Phase*)
**Tujuan:** Proses inti dari *Machine Learning*. Model diarahkan untuk mencari pola piksel (ciri visual) dari penyakit busuk buah dan lubang penggerek.
```python
from ultralytics import YOLO

# Memuat bobot dasar dari YOLOv8 versi 'Small' (S) yang efisien untuk citra klasifikasi
model = YOLO('yolov8s-cls.pt')

# Inisiasi proses pelatihan (Hyperparameter disesuaikan berdasar literatur)
hasil_training = model.train(
    data='/content/dataset_split', # Mengarahkan AI ke direktori data siap pakai
    epochs=50,                     # Menjalankan siklus belajar (propagasi) sebanyak 50 kali
    imgsz=224,                     # Dimensi input dinormalisasi ke ukuran matriks 224x224 piksel
    batch=32,                      # Mengirim data paralel sebanyak 32 gambar ke GPU per putaran
    device=0,                      # Indikator penggunaan GPU akselerator
    name='klasifikasi_kakao'       # Direktori penyimpanan bobot / model akhir (best.pt)
)
```

### Cell 5: Evaluasi Numerik dan Pengujian Simulasi (*Inference*)
**Tujuan:** Mengukur skor presisi final dan melakukan antarmuka (*Interface*) mini untuk menguji ketahanan model jika disodorkan citra dari perangkat lokal (*Real-world implementation*).
```python
from google.colab import files
from ultralytics import YOLO

# 1. Menampilkan Matriks Evaluasi (Skor Akurasi Akhir)
print("--- Hasil Evaluasi Numerik ---")
metrics = model.val(data='/content/dataset_split', split='test')
print(f"Tingkat Akurasi Top-1: {metrics.top1 * 100:.2f}%")

# 2. Simulasi Dunia Nyata (Real-World Inference)
print("\n--- 📱 UJI COBA MODEL DENGAN FOTO SENDIRI ---")
uploaded = files.upload() # Antarmuka dialog penelusuran file

if uploaded:
    # Membaca ekstensi dan lokasi file yang diunggah pengguna
    nama_file = list(uploaded.keys())[0]
    
    # Melemparkan gambar mentah ke dalam model AI (Proses Inferensi)
    hasil_prediksi = model(nama_file)
    
    # Mengurai objek hasil (*parsing object*) untuk menemukan probabilitas diagnosis
    probs = hasil_prediksi[0].probs
    nama_kelas = model.names[probs.top1]           # Ekstraksi string nama penyakit
    akurasi_persen = probs.top1conf.item() * 100   # Ekstraksi presentase keyakinan model
    
    print("\n--- HASIL KEPUTUSAN AI ---")
    print(f"Diagnosis : {nama_kelas.upper()}")
    print(f"Keyakinan : {akurasi_persen:.2f}%")
    
    # Menampilkan proyeksi gambar secara visual di Google Colab
    hasil_prediksi[0].show()
```
