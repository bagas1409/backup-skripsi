# 2. Unduh dataset
import kagglehub
import shutil
import os
print("Mengunduh dataset dari Kaggle...")
path_asli = kagglehub.dataset_download("zaldyjr/cacao-diseases")
print(f"Dataset berhasil diunduh di: {path_asli}")
# 3. Pindahkan dataset ke direktori kerja kita di /content/dataset
lokasi_baru = '/content/dataset'
# Jika folder dataset sudah ada, hapus dulu agar bersih
if os.path.exists(lokasi_baru):
    shutil.rmtree(lokasi_baru)
# Pindahkan file
shutil.copytree(path_asli, lokasi_baru)
print(f"Dataset dipindahkan ke: {lokasi_baru}")
# 4. Cek struktur isi foldernya
!ls /content/dataset

Mengunduh dataset dari Kaggle...
Using Colab cache for faster access to the 'cacao-diseases' dataset.
Dataset berhasil diunduh di: /kaggle/input/cacao-diseases
Dataset dipindahkan ke: /content/dataset
cacao_diseases
