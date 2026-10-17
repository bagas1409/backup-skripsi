import os
import glob
import shutil
import random

sumber_dataset = "/content/dataset"
tujuan_dataset = "/content/dataset_split"

print("Memulai pelacakan file gambar secara mendalam...")

# 1. Cari semua file gambar di dalam folder sumber secara rekursif (sedalam apa pun)
semua_gambar = glob.glob(sumber_dataset + "/**/*.jpg", recursive=True) + \
               glob.glob(sumber_dataset + "/**/*.jpeg", recursive=True) + \
               glob.glob(sumber_dataset + "/**/*.png", recursive=True) + \
               glob.glob(sumber_dataset + "/**/*.JPG", recursive=True)

print(f"Total gambar ditemukan: {len(semua_gambar)}")

if len(semua_gambar) == 0:
    print("❌ ERROR CRITICAL: Tidak ada gambar sama sekali. Pastikan download dari Kaggle di Cell 2.5 sukses!")
else:
    # 2. Hapus folder output lama yang rusak jika ada
    if os.path.exists(tujuan_dataset):
        shutil.rmtree(tujuan_dataset)

    # 3. Kelompokkan gambar berdasarkan nama folder kelasnya
    kelas_dict = {}
    for path_gambar in semua_gambar:
        # Ambil nama folder tepat di atas file gambar sebagai "Nama Kelas"
        nama_kelas = os.path.basename(os.path.dirname(path_gambar))

        if nama_kelas not in kelas_dict:
            kelas_dict[nama_kelas] = []
        kelas_dict[nama_kelas].append(path_gambar)

    print(f"✅ Kelas yang terdeteksi secara otomatis: {list(kelas_dict.keys())}\n")

    # 4. Distribusikan ke Train (80%), Val (10%), Test (10%)
    for nama_kelas, daftar_gambar in kelas_dict.items():
        random.shuffle(daftar_gambar) # Acak urutan agar adil

        total = len(daftar_gambar)
        batas_train = int(total * 0.8)
        batas_val = int(total * 0.9)

        grup_split = {
            'train': daftar_gambar[:batas_train],
            'val': daftar_gambar[batas_train:batas_val],
            'test': daftar_gambar[batas_val:]
        }

        # Pindahkan file-file tersebut ke struktur YOLO yang benar
        for nama_split, file_list in grup_split.items():
            folder_tujuan = os.path.join(tujuan_dataset, nama_split, nama_kelas)
            os.makedirs(folder_tujuan, exist_ok=True)

            for f in file_list:
                shutil.copy(f, os.path.join(folder_tujuan, os.path.basename(f)))

        print(f"📂 Memproses '{nama_kelas}': {len(grup_split['train'])} Train, {len(grup_split['val'])} Val, {len(grup_split['test'])} Test")

    print("\n🚀 PROSES SELESAI SEMPURNA! Silakan jalankan Cell 5 (Training) sekarang.")


Memulai pelacakan file gambar secara mendalam...
Total gambar ditemukan: 4390
✅ Kelas yang terdeteksi secara otomatis: ['pod_borer', 'black_pod_rot', 'healthy']

📂 Memproses 'pod_borer': 82 Train, 10 Val, 11 Test
📂 Memproses 'black_pod_rot': 754 Train, 94 Val, 95 Test
📂 Memproses 'healthy': 2675 Train, 334 Val, 335 Test

🚀 PROSES SELESAI SEMPURNA! Silakan jalankan Cell 5 (Training) sekarang.