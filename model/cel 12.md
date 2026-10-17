from google.colab import files
import glob

# Mencari file best.pt terbaru di dalam folder runs
list_model = glob.glob('/content/yolov9/runs/classify/**/weights/best.pt', recursive=True)

if len(list_model) > 0:
    # Mengambil model yang paling baru dilatih
    model_terbaru = max(list_model, key=os.path.getctime)
    print(f"Menemukan model terbaik di: {model_terbaru}")
    print("Sedang mengunduh ke komputer Anda (File ini besarnya sekitar belasan MB)...")

    # Memulai proses unduh otomatis
    files.download(model_terbaru)
else:
    print("File best.pt tidak ditemukan. Pastikan proses training di Cell 5 sudah selesai 100%.")

Menemukan model terbaik di: /content/yolov9/runs/classify/klasifikasi_kakao-6/weights/best.pt
Sedang mengunduh ke komputer Anda (File ini besarnya sekitar belasan MB)...