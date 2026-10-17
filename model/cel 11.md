from google.colab import files
from ultralytics import YOLO

print("--- 📱 UJI COBA MODEL DENGAN FOTO SENDIRI ---")
print("Klik tombol 'Choose Files' di bawah ini untuk mengupload gambar:")

# 1. Memanggil fitur upload bawaan Google Colab
uploaded = files.upload()

if not uploaded:
    print("❌ Anda belum memilih/mengupload gambar apa pun.")
else:
    # 2. Mengambil nama file yang baru saja diupload
    nama_file = list(uploaded.keys())[0]
    print(f"\nMemproses gambar: {nama_file}...")

    # 3. Inference (Meminta AI menebak gambar tersebut)
    # Catatan: Variabel 'model' sudah tersimpan di memori dari Cell 5
    hasil_prediksi = model(nama_file)

    # 4. Mengekstrak dan menampilkan hasil
    probs = hasil_prediksi[0].probs
    nama_kelas = model.names[probs.top1]  # Tebakan paling yakin
    akurasi_persen = probs.top1conf.item() * 100

    print("\n==========================================")
    print("🧠 KESIMPULAN KECERDASAN BUATAN:")
    print("==========================================")
    print(f"📌 Diagnosis : {nama_kelas.upper()}")
    print(f"🎯 Keyakinan : {akurasi_persen:.2f}%")
    print("==========================================\n")

    # Tampilkan gambar beserta persentase prediksinya secara visual
    hasil_prediksi[0].show()

    --- 📱 UJI COBA MODEL DENGAN FOTO SENDIRI ---
Klik tombol 'Choose Files' di bawah ini untuk mengupload gambar:
Tidak ada file yang dipilih Upload widget is only available when the cell has been executed in the current browser session. Please rerun this cell to enable.
Saving black_pod_rot_2.jpg to black_pod_rot_2.jpg

Memproses gambar: black_pod_rot_2.jpg...

image 1/1 /content/yolov9/black_pod_rot_2.jpg: 224x224 black_pod_rot 1.00, healthy 0.00, pod_borer 0.00, 3.2ms
Speed: 10.6ms preprocess, 3.2ms inference, 0.0ms postprocess per image at shape (1, 3, 224, 224)

==========================================
🧠 KESIMPULAN KECERDASAN BUATAN:
==========================================
📌 Diagnosis : BLACK_POD_ROT
🎯 Keyakinan : 99.99%
==========================================
