# PROPOSAL SKRIPSI

**IMPLEMENTASI YOLOV8 UNTUK DETEKSI PENYAKIT PADA BUAH KAKAO BERBASIS APLIKASI MOBILE**

---

## BAB I — PENDAHULUAN

### 1.1 Latar Belakang

Sektor perkebunan memegang peranan strategis sebagai salah satu pilar penopang perekonomian nasional Indonesia, di mana komoditas kakao (*Theobroma cacao L.*) menjadi salah satu penyumbang devisa non-migas terbesar sekaligus sumber penghidupan utama bagi jutaan keluarga petani pedesaan. Berdasarkan publikasi resmi Badan Pusat Statistik (BPS, 2023), luas areal tutupan perkebunan kakao di Indonesia tercatat mencapai lebih dari 1,42 juta hektar dengan estimasi volume produksi biji kering sekitar 641,7 ribu ton per tahun. Karakteristik pengusahaan komoditas ini didominasi oleh perkebunan rakyat (PR) dengan proporsi melampaui 98%, yang tersebar di wilayah Sulawesi, Sumatera, Nusa Tenggara, hingga Papua. Kendati demikian, produktivitas rata-rata tanaman kakao nasional masih berada pada kisaran 0,5 hingga 0,7 ton per hektar, jauh di bawah potensi hasil optimal klon unggul yang mampu menghasilkan lebih dari 1,5 hingga 2 ton per hektar. Kesenjangan produktivitas ini mengindikasikan adanya kendala struktural di tingkat budidaya, terutama tingginya kerentanan tanaman terhadap cekaman biotik berupa serangan hama dan patogen tular-tanah maupun tular-udara yang mendegradasi kuantitas serta mutu biji kakao secara persisten.

Ancaman patologis yang paling destruktif pada perkebunan kakao tropis bersumber dari infeksi cendawan oomycetes *Phytophthora palmivora* dan serangan serangga hama Penggerek Buah Kakao (PBK) yang disebabkan oleh larva *Conopomorpha cramerella*. Sebagaimana dianalisis secara komprehensif oleh Alvarado et al. (2025), penyakit Busuk Buah Hitam (*Black Pod Rot*) akibat *Phytophthora palmivora* merupakan salah satu penyakit paling merusak di sentra perkebunan kakao global dengan potensi kehilangan hasil panen mencapai 20% hingga 40% di Indonesia, bahkan menembus 60% hingga 80% pada kondisi iklim dengan kelembapan ekstrem. Infeksi patogen ini memicu nekrosis basah berwarna cokelat gelap yang meluas secara cepat ke seluruh permukaan kulit buah, merusak plasenta internal, dan membusukkan biji kakao sehingga kehilangan nilai komersial sepenuhnya (Ferraris et al., 2023). Di sisi lain, serangan hama PBK (*Conopomorpha cramerella*) menyebabkan gejala pematangan dini tidak merata (*uneven ripening*), pengerasan kulit buah akibat liang gerek internal larva, dan pelekatan biji ke dinding endokarp buah yang mengakibatkan bobot biji merosot tajam serta kadar rendemen lemak hancur (Ariawan et al., 2025; Maylianti et al., 2025). Kombinasi kedua cekaman ini menjadi pemicu utama kebangkrutan ekonomi petani skala kecil apabila penanganan kuratif terlambat dilakukan.

Hingga saat ini, proses identifikasi anomali kesehatan buah kakao di tingkat petani swadaya masih mengandalkan inspeksi visual kasat mata secara konvensional. Pendekatan manual ini memiliki keterbatasan intrinsik yang masif: sangat bergantung pada pengalaman empiris individu petani, memakan waktu operasional yang panjang, rentan terhadap kelelahan visual (*visual fatigue*), dan memiliki derajat subjektivitas yang tinggi. Pada fase awal infeksi (*early stage*), bercak nekrotik *Black Pod Rot* dan bekas tusukan oviposisi serangga PBK kerap menampilkan pola bercak klorotik atau kecokelatan yang secara visual sangat mirip dengan fase kematangan buah normal atau luka mekanis ringan (Novanto et al., 2025). Akibatnya, kesalahan diagnosis (*misdiagnosis*) kerap terjadi; petani baru menyadari keparahan serangan ketika miselium cendawan telah memproduksi spora matang atau ketika larva PBK telah bermigrasi melubangi buah lain. Keterlambatan isolasi dan sanitasi ini memicu penyebaran spora patogen secara masif melalui percikan air hujan (*rain splash*) dan kontak vektor semut, yang berujung pada ledakan epidemi lokal di areal perkebunan rakyat.

Transformasi diagnosis penyakit tanaman berbasis kecerdasan buatan (*Artificial Intelligence*) dan visi komputer telah diupayakan dalam sejumlah literatur, namun masih menyisakan kesenjangan riset (*research gap*) yang nyata. Tinjauan sistematis yang dilakukan oleh Alvarado et al. (2025) mengungkapkan bahwa sebagian besar riset klasifikasi citra penyakit tanaman berfokus pada organ daun dan mengandalkan dataset lingkungan laboratorium terkontrol, seperti basis data PlantVillage yang diuji oleh Mohanty et al. (2016). Ketika model deep learning yang dilatih pada kondisi laboratorium tersebut diuji menggunakan citra lapangan terbuka dengan variasi latar belakang alami, akurasi klasifikasi mengalami penurunan drastis hingga tersisa sekitar 31% (Mohanty et al., 2016). Ketergantungan pada organ daun juga dinilai kurang representatif untuk kakao karena kerusakan ekonomi riil dialami langsung pada organ buah. Sementara itu, penelitian pada kakao oleh Gado dan Primandari (2025) menggunakan arsitektur NASNet-Mobile menghasilkan penurunan presisi lapangan yang tajam hingga 57,1%, yang menandakan tingginya angka positif palsu (*false positives*) saat membedakan lesi penyakit. Di samping itu, penelitian komparasi CNN konvensional seperti DenseNet-121 oleh Ariawan et al. (2025), kombinasi Inception-ResNet oleh Novanto et al. (2025), maupun evaluasi EfficientNet-B0 dan ResNet-50 oleh Maylianti et al. (2025) masih berorientasi pada komputasi berbasis *cloud server*. Ketergantungan terhadap infrastruktur peladen awan ini terbukti menjadi kendala fatal di lapangan, mengingat sebagian besar perkebunan kakao rakyat berada di wilayah pedesaan terpencil (*rural area*) tanpa jangkauan sinyal internet stabil (*blind spot cellular network*).

Guna mengatasi keterbatasan tersebut, penerapan model deep learning generasi mutakhir yang ringkas, presisi, dan teroptimasi untuk komputasi tepi (*edge computing*) menjadi kebutuhan yang krusial. Ultralytics merilis YOLOv8 sebagai terobosan arsitektur yang tidak hanya unggul dalam deteksi objek, melainkan juga menyediakan varian klasifikasi citra (*classification head*) murni bernama `yolov8s-cls` (Terven et al., 2023). Arsitektur YOLOv8 mengadopsi struktur *backbone* modified CSPDarknet yang dipadukan dengan modul *Cross-Stage Partial with 2 Convolutions* (C2f), yang menggantikan modul C3 pada versi sebelumnya guna memaksimalkan aliran gradien dan memperkaya fitur representasi spasial dengan parameter bobot yang lebih ringkas (Ghafar et al., 2024; Siahaan et al., 2024). Penggunaan aktivasi *SiLU* (*Sigmoid Linear Unit*) serta normalisasi *cross-layer* memungkinkan `yolov8s-cls` mengekstraksi tekstur mikro kulit buah kakao secara diskriminatif. Berdasarkan studi Khan et al. (2023), famili arsitektur YOLOv8 terbukti melampaui varian terdahulu seperti YOLOv3, YOLOv4, dan YOLOv5 dalam mengenali penyakit tanaman dengan latensi inferensi super rendah, menjadikannya kandidat terbaik untuk klasifikasi citra berdaya komputasi terbatas.

Atas dasar pertimbangan tersebut, penelitian ini mengajukan kebaruan (*novelty*) berupa rancang bangun sistem deteksi penyakit buah kakao berbasis aplikasi mobile cerdas yang beroperasi secara luring penuh (*offline-first edge AI*). Model `yolov8s-cls` dilatih secara terawasi (*supervised transfer learning*) pada dataset sekunder publik beresolusi tinggi yang dikurasi oleh Zaldy Jr (~4.300 citra buah kakao) ke dalam tiga kelas target: *Black Pod Rot*, *Pod Borer*, dan *Healthy*. Model teroptimasi selanjutnya dikuantisasi ke dalam format TensorFlow Lite (`.tflite`) dan diintegrasikan ke dalam aplikasi Android menggunakan framework React Native (Expo SDK 54) bersama pustaka performa tinggi `react-native-fast-tflite` (berbasis C++ *JavaScript Interface* / JSI) dan `react-native-vision-camera` v5.2.2. Seluruh proses inferensi visi komputer dieksekusi secara lokal pada prosesor gawai (*on-device AI*) tanpa memerlukan transmisi paket data internet, didukung oleh penyimpanan riwayat pemindaian luring melalui `expo-sqlite`. Melalui pendekatan ini, petani kakao memperoleh instrumen diagnosis mandiri yang cepat (~3,2 ms latensi inferensi), berakurasi tinggi (Akurasi Top-1 mencapai 98,87%), dan tangguh dioperasikan langsung di tengah perkebunan tanpa ketergantungan sinyal internet.

---

### 1.2 Rumusan Masalah

Berdasarkan uraian konteks latar belakang di atas, rumusan masalah dalam penelitian ini dirinci ke dalam empat pertanyaan ilmiah sebagai berikut:

1. Bagaimana mengimplementasikan arsitektur deep learning YOLOv8 varian Small Classification (`yolov8s-cls`) melalui pendekatan *transfer learning* untuk mengklasifikasikan tiga kondisi buah kakao (*Black Pod Rot*, *Pod Borer*, dan *Healthy*)?
2. Bagaimana kinerja model `yolov8s-cls` pada data uji independen yang diukur menggunakan metrik evaluasi *Accuracy*, *Precision*, *Recall*, *F1-Score*, dan matriks konfusi (*Confusion Matrix*) multi-kelas?
3. Bagaimana mengonversi dan mengoptimasi model `yolov8s-cls` ke dalam format *edge inference* TensorFlow Lite (`.tflite`) agar dapat diintegrasikan ke dalam arsitektur aplikasi mobile React Native berbasis C++ *JavaScript Interface* (JSI)?
4. Bagaimana merancang dan membangun aplikasi mobile Android luring (*offline-first*) menggunakan metode Waterfall yang mampu menyajikan diagnosis penyakit buah kakao secara instan dan menyimpan riwayat pemindaian ke dalam basis data lokal SQLite?

---

### 1.3 Batasan Masalah

Agar penelitian terfokus pada sasaran ilmiah dan teknis yang telah digariskan, ditetapkan enam batasan masalah yang tegas sebagai berikut:

1. **Objek Citra Organ Buah:** Objek klasifikasi dibatasi secara eksklusif pada organ buah kakao (*Theobroma cacao L.*) yang terbagi ke dalam tiga kelas kategori: Buah Sehat (*Healthy*), Busuk Buah Hitam (*Black Pod Rot* akibat *Phytophthora palmivora*), dan Penggerek Buah Kakao (*Pod Borer* akibat *Conopomorpha cramerella*). Penelitian tidak mencakup identifikasi penyakit pada daun, batang, atau akar.
2. **Dataset Penelitian:** Data citra yang digunakan bersumber dari repositori publik Kaggle oleh Zaldy Jr (`cacao-diseases`) dengan total volume 4.300 citra beresolusi asli $1080 \times 1080$ piksel yang diambil pada perkebunan kakao.
3. **Mekanisme Visi Komputer:** Sistem menerapkan paradigma *Single-Image Classification* (klasifikasi citra tunggal) menggunakan input dimensi $224 \times 224$ piksel. Penelitian ini **bukan** merupakan tugas *Object Detection*, tidak menghasilkan koordinat kotak pembatas (*bounding box*), dan secara absolut **tidak** menggunakan metrik *mean Average Precision* (mAP).
4. **Metrik Evaluasi:** Evaluasi performa model klasifikasi diukur secara eksklusif melalui metrik *Accuracy*, *Precision*, *Recall*, *F1-Score*, dan *Confusion Matrix* 3-kelas.
5. **Platform Sistem Operasi:** Aplikasi mobile dikembangkan khusus untuk sistem operasi Android (berbasis runtime Android SDK modern) menggunakan framework React Native (Expo SDK 54).
6. **Mekanisme Inferensi Tepi (*Edge Computing*):** Proses inferensi deep learning berjalan 100% secara lokal pada perangkat keras seluler (*on-device inference*) tanpa melakukan komputasi atau pertukaran data ke peladen web/cloud eksternal, sehingga tidak membutuhkan koneksi jaringan internet.

---

### 1.4 Tujuan Penelitian

Tujuan yang hendak dicapai dalam penelitian ini berkesesuaian satu-ke-satu (*1-to-1 mapping*) dengan rumusan masalah, yaitu:

1. Melatih dan mengonfigurasi model deep learning `yolov8s-cls` berbasis transfer learning bobot ImageNet untuk mengklasifikasikan citra buah kakao ke dalam kelas *Black Pod Rot*, *Pod Borer*, dan *Healthy*.
2. Mengukur dan menganalisis performa klasifikasi model `yolov8s-cls` pada data uji menggunakan metrik *Accuracy*, *Precision*, *Recall*, *F1-Score*, serta visualisasi *Confusion Matrix*.
3. Melakukan kuantisasi dan konversi model hasil pelatihan ke format TensorFlow Lite (`.tflite`) berkinerja tinggi serta mengintegrasikannya dengan runtime React Native melalui antarmuka native C++ JSI (`react-native-fast-tflite`).
4. Mengembangkan aplikasi mobile Android luring (*offline-first*) yang dilengkapi pemindai kamera real-time, penyaji diagnosis penyakit buah kakao, dan modul pencatatan riwayat berbasis basis data lokal `expo-sqlite` dengan mengadopsi siklus pengembangan Waterfall.

---

### 1.5 Manfaat Penelitian

#### 1.5.1 Manfaat Teoretis (Akademis)

1. Memberikan kontribusi literatur empiris dalam domain kecerdasan buatan terapan (*applied artificial intelligence*) dan visi komputer mengenai implementasi varian klasifikasi YOLOv8 (`yolov8-cls`) pada ranah patologi pertanian tropis.
2. Memperkaya khazanah keilmuan Rekayasa Perangkat Lunak mengenai integrasi model deep learning pada lingkungan komputasi tepi (*Edge AI*) menggunakan jembatan C++ *JavaScript Interface* (JSI) pada arsitektur hybrid modern React Native.

#### 1.5.2 Manfaat Praktis

1. **Bagi Petani Kakao:** Menyediakan instrumen diagnosis digital yang mudah diakses, gratis, berkecepatan tinggi, dan dapat dioperasikan secara andal di tengah kebun tanpa sinyal seluler, guna menekan risiko gagal panen melalui tindakan kuratif dini.
2. **Bagi Petugas Penyuluh Lapangan:** Berfungsi sebagai alat bantu verifikasi diagnosis patologis di perkebunan rakyat yang objektif, terukur, dan terhindar dari bias persepsi visual individu.
3. **Bagi Industri dan Pengambil Kebijakan:** Mendukung stabilitas pasokan dan mutu biji kakao nasional yang memenuhi standar ekspor melalui pencegahan wabah penyakit secara presisi di hulu rantai pasok.

---

### 1.6 Sistematika Penulisan

Penyusunan naskah proposal skripsi ini diorganisasikan ke dalam beberapa bab dengan sistematika sebagai berikut:

* **BAB I — PENDAHULUAN:** Memuat latar belakang permasalahan secara piramida terbalik, rumusan masalah terarah, batasan ruang lingkup penelitian, tujuan yang ingin dicapai, manfaat teoretis dan praktis, serta sistematika penulisan dokumen.
* **BAB II — LANDASAN TEORI:** Menyajikan tinjauan studi terdahulu beserta tabel komparasi, telaah sintesis novelty, serta teori-teori fundamental yang melandasi penelitian (morfologi kakao, patologi buah, pengolahan citra digital, CNN, transfer learning, arsitektur YOLOv8 classification, kerangka kerja React Native, edge AI, kuantisasi model, metode Waterfall, dan pemodelan UML), diakhiri dengan perumusan hipotesis penelitian.
* **BAB III — METODE PENELITIAN:** Menguraikan metodologi operasional penelitian yang mencakup teknik pengumpulan data, spesifikasi perangkat keras dan lunak, karakteristik dataset dan proporsi pembagian, diagram alur tahapan penelitian berbasis Waterfall, rancangan pemodelan sistem UML, serta skenario pengujian fungsional *Black-Box Testing*.
* **BAB IV — HASIL DAN PEMBAHASAN:** *(Direncanakan)* Memaparkan hasil pelatihan model `yolov8s-cls`, evaluasi metrik kinerja, proses kuantisasi TFLite, implementasi antarmuka aplikasi Android, hasil pengujian fungsional black-box, serta analisis komparatif performa inferensi on-device.
* **BAB V — PENUTUP:** *(Direncanakan)* Berisi kesimpulan akhir dari seluruh tahapan penelitian yang menjawab rumusan masalah serta saran konstruktif untuk pengembangan sistem di masa mendatang.

---

## BAB II — LANDASAN TEORI

### 2.1 Kajian Pustaka

#### 2.1.1 Penelitian Terdahulu

Kajian pustaka ini menelaah secara kritis publikasi-publikasi terdahulu yang relevan dalam bidang visi komputer pertanian, pengenalan penyakit tanaman, arsitektur deep learning, dan rekayasa perangkat lunak seluler. Matriks perbandingan penelitian terdahulu disajikan secara terperinci pada Tabel 2.1.

**Tabel 2.1** Perbandingan Penelitian Terdahulu Terkait Visi Komputer dan Aplikasi Seluler

| No | Penulis & Tahun | Judul Paper | Metode / Model | Objek Penelitian | Hasil Akurasi | Perbedaan & Kelemahan Dibanding Penelitian Ini |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Alvarado et al. (2025) | *Disease Detection on Cocoa Crops Based on Computer-Vision Techniques: A Systematic Literature Review* | Systematic Literature Review (PRISMA) | Patologi tanaman kakao dan komoditas global | Tinjauan komparatif 88 artikel terpilih | Merupakan studi survei literatur komprehensif, bukan implementasi model langsung; mengidentifikasi kelangkaan riset deteksi pada organ buah kakao nyata. |
| 2 | Ariawan et al. (2025) | *Performance Comparison of DenseNet-121 and MobileNetV2 for Cacao Fruit Disease Image Classification* | Perbandingan CNN (DenseNet-121 vs. MobileNetV2) | Buah kakao (Busuk Buah, Kepik, PBK, Sehat) di Bali | DenseNet: 94,50%, MobileNetV2: 93,88% | Berfokus pada perancangan sistem web server, bukan aplikasi mobile edge; membutuhkan parameter komputasi besar dan belum menguji arsitektur YOLO classification. |
| 3 | Novanto et al. (2025) | *Enhanced Speed and Accuracy in Cocoa Fruit Disease Identification Using the Inception-ResNet CNN Algorithm* | CNN Hibrida (Inception-ResNet) | Buah kakao (Davao City, Filipina) | Akurasi: 99,00%, F1-Score: 0,99, Spesifisitas: 0,99 | Model memiliki kompleksitas parameter tinggi (*high resource memory*), belum diterapkan pada gawai mobile, dan proses inferensi memerlukan waktu yang relatif lama. |
| 4 | Maylianti et al. (2025) | *Comparison of EfficientNet-B0 and ResNet-50 for Detecting Diseases in Cocoa Fruit* | CNN Transfer Learning (EfficientNet-B0 vs. ResNet-50) | Buah kakao (3.344 Sehat, 943 Busuk Buah, 103 PBK) | ResNet-50: 96,00% (F1: 93,3%), EfficientNet: 96,00% | Mengalami ketidakseimbangan kelas ekstrem pada kelas PBK; model dieksekusi pada lingkungan server cloud dan belum dioptimasi untuk komputasi offline gawai. |
| 5 | Gado & Primandari (2025) | *Sistem Klasifikasi Berbasis Android untuk Penyakit Buah Kakao Menggunakan CNN NasNet-Mobile* | Transfer Learning CNN (NASNet-Mobile) | Buah kakao 4 kelas (Busuk Buah, Kepik, PBK, Normal) | Uji model: 94,88%, Pengujian aplikasi Android: 93,33% | Menggunakan klasifikasi multi-label dengan fungsi sigmoid; nilai presisi uji lapangan anjlok tajam ke 57,1% (tingkat false positive sangat tinggi). |
| 6 | Ferraris et al. (2023) | *Machine Learning as a Strategic Tool for Helping Cocoa Farmers in Côte D'Ivoire* | YOLOv5m Object Detection & U-Net (CIWA-net) | Buah kakao Pantai Gading (312 citra) & Anomali Air GRACE | YOLOv5m Buah Sehat: 98,00%, Monilia/Fito: ~60% | Dataset buah kakao sangat kecil (312 citra), akurasi membedakan antar-penyakit rendah (kebingungan 30%), dan berfokus pada deteksi kotak pembatas multi-skala. |
| 7 | Terven et al. (2023) | *A Comprehensive Review of YOLO: From YOLOv1 to YOLOv8 and Beyond* | Tinjauan Komprehensif Arsitektur YOLO | Deteksi, Segmentasi, & Klasifikasi Objek (Benchmark COCO) | Review evolusi metrik dan arsitektur YOLO | Makalah tinjauan komprehensif arsitektur dasar; membedah keunggulan modul C2f pada YOLOv8 yang menjadi acuan teoretis pemilihan model skripsi ini. |
| 8 | Ghafar et al. (2024) | *Visualizing Plant Disease Distribution and Evaluating Model Performance for Deep Learning Classification with YOLOv8* | Custom YOLOv8 Classification & Feature Visualization | Penyakit daun tanaman (Sehat, Powdery, Rust) | F1-Score: 1,00 pada ambang keyakinan 0,728 | Menguji penyakit daun umum pada dataset Kaggle kecil (~450 citra); tidak mengkaji buah kakao dan tidak diimplementasikan pada perangkat Android. |
| 9 | Khan et al. (2023) | *A Mobile-Based System for Maize Plant Leaf Disease Detection and Classification Using Deep Learning* | Komparasi YOLO (v3-tiny, v4, v5s, v7s, v8n) | Daun tanaman jagung (Blight, Leaf Spot, Mosaic Virus) | YOLOv8n: Akurasi 99,04%, mAP: 99,04% | Berfokus pada organ daun jagung dengan mekanisme deteksi objek; aplikasi Android berbasis Java murni tanpa integrasi basis data riwayat luring canggih. |
| 10 | Siahaan et al. (2024) | *Enhancing Real-time Herbal Plant Detection in Agricultural Environments with YOLOv8* | YOLOv8 Object Detection terkonversi TFLite | Daun tanaman herbal (Tempuyung, Rimbang, Pepaya, Kunyit, Lidah Buaya) | mAP50: 94,60%, Precision: 92,40% | Menggunakan arsitektur deteksi objek bounding box daun herbal; rentan beban komputasi gawai dibanding klasifikasi citra murni 224x224. |
| 11 | Octavian et al. (2024) | *Enhancing Weighted Averaging for CNN Model Ensemble in Plant Diseases Image Classification* | Ensemble CNN (DenseNet201, InceptionV3, Xception) + Soft-Voting | Daun tanaman anggur (Grape Diseases) | Akurasi Ensemble: 96,56% | Memerlukan komputasi paralel dari tiga arsitektur masif secara simultan, sehingga sangat lambat dan mustahil dijalankan secara real-time pada prosesor ponsel pintar. |
| 12 | Mohanty et al. (2016) | *Using Deep Learning for Image-Based Plant Disease Detection* | AlexNet & GoogLeNet (Scratch vs. Transfer Learning) | Daun 14 spesies tanaman, 26 penyakit (PlantVillage: 54.306 citra) | Akurasi Lab: 99,35%, Akurasi Uji Citra Web Liar: 31,40% | Penurunan akurasi ekstrem pada citra kondisi terbuka; latar belakang homogen buatan terbukti membiaskan model saat berhadapan dengan lingkungan nyata. |
| 13 | Ramcharan et al. (2017) | *Deep Learning for Image-Based Cassava Disease Detection* | Inception v3 Transfer Learning + SVM / KNN Classifier | Daun tanaman singkong di Tanzania (2.756 citra daun utuh) | Akurasi Uji: 93,00% (CBSD: 98%, BLS: 98%, CMD: 96%) | Berfokus pada daun singkong; ekstraksi fitur transfer learning dipadukan dengan classifier eksternal yang menambah kompleksitas pipeline inferensi mobile. |
| 14 | Fuentes et al. (2017) | *A Robust Deep-Learning-Based Detector for Real-Time Tomato Plant Diseases and Pests Recognition* | Meta-Arsitektur (Faster R-CNN, SSD, R-FCN) + VGG/ResNet | Penyakit & hama tanaman tomat di rumah kaca (Korea) | R-FCN ResNet-50: mAP 85,98%, Faster R-CNN: 83,06% | Model detektor two-stage berukuran sangat masif; latensi inferensi mencapai 160 ms per citra pada GPU desktop, kurang efisien untuk mobile on-device. |
| 15 | Natbais & Umbu (2023) | *Aplikasi Deteksi Penyakit pada Daun Tomat Berbasis Android Menggunakan Model Terlatih Tensorflow Lite* | Teachable Machine CNN terkonversi TensorFlow Lite | Daun tanaman tomat 10 kelas (Kaggle: 20.000 citra) | Akurasi bervariasi; galat terdeteksi pada kamera fisik | Pelatihan model menggunakan platform *black-box* Teachable Machine tanpa kustomisasi arsitektur mendalam; akurasi kamera fisik rentan terhadap noise pencahayaan. |
| 16 | Supriyadi & Widiastuti (2023) | *Rancang Program Aplikasi Pembelajaran Tajwid Berbasis Android* | SDLC Waterfall, Pemodelan UML, & SQLite OpenHelper | Aplikasi edukasi mobile interaktif pada smartphone Android | Uji fungsional Black-Box: 100% Berhasil | Memvalidasi keandalan metodologi Waterfall, pemodelan UML, dan basis data luring SQLite dalam rekayasa perangkat lunak mobile Android. |
| 17 | Susila & Arsa (2023) | *Analisis System Usability Scale (SUS) dan Perancangan Sistem Self Service Pemesanan Menu di Restoran Berbasis Web* | SDLC Waterfall, Pemodelan UML, & System Usability Scale | Perangkat lunak layanan mandiri berbasis Web & QR Code | Skor Rata-rata SUS: 70,00 (Kategori *Good*) | Membuktikan efektivitas rekayasa berbasis Waterfall dan UML dalam menghasilkan antarmuka perangkat lunak yang berpusat pada kenyamanan pengguna (*user usability*). |

#### 2.1.2 Narasi Sintesis Kebaruan (Novelty)

Berdasarkan telaah komprehensif terhadap literatur pada Tabel 2.1, teridentifikasi sejumlah celah riset fundamental yang melandasi urgensi penelitian ini. Pertama, mayoritas riset terdahulu berfokus pada organ daun (Mohanty et al., 2016; Ramcharan et al., 2017; Octavian et al., 2024). Pada tanaman kakao, gejala infeksi pada daun kerap tidak mencerminkan secara langsung tingkat keparahan infeksi pada buah. Buah kakao merupakan komoditas ekonomi utama, sehingga kegagalan mendeteksi patogen pada buah berakibat langsung pada kehilangan hasil panen secara total (Alvarado et al., 2025). Meskipun penelitian terdahulu pada buah kakao telah dilakukan, sebagian besar menggunakan model konvensional dengan parameter komputasi masif yang dirancang untuk peladen awan (Ariawan et al., 2025; Novanto et al., 2025), atau menghasilkan presisi lapangan yang sangat rendah akibat tingginya positif palsu, seperti pada penerapan NASNet-Mobile oleh Gado dan Primandari (2025) yang mencatatkan presisi lapangan hanya 57,1%.

Kedua, terdapat keterbatasan operasional yang signifikan terkait infrastruktur komputasi. Penelitian deteksi tanaman berbasis deep learning umumnya mengandalkan arsitektur *two-stage detector* atau model berbobot puluhan hingga ratusan megabita, seperti Faster R-CNN dan R-FCN (Fuentes et al., 2017) maupun ensemble multi-model masif (Octavian et al., 2024). Pendekatan tersebut tidak dapat diadopsi pada lingkungan perkebunan rakyat yang berada di wilayah pelosok, di mana koneksi internet seluler sangat lemah atau bahkan tidak tersedia sama sekali. Ketergantungan terhadap transmisi data ke server komputasi awan menyebabkan latensi tinggi dan kegagalan transmisi paket data (Khan et al., 2023).

Kebaruan (*novelty*) yang dihadirkan dalam penelitian ini adalah pengembangan sistem klasifikasi penyakit buah kakao berbasis *On-Device Edge AI* luring penuh (*offline-first*) menggunakan model klasifikasi mutakhir `yolov8s-cls`. Berbeda dengan varian deteksi objek bounding box yang memerlukan beban komputasi spasial tinggi (Ferraris et al., 2023; Siahaan et al., 2024), penerapan varian klasifikasi citra murni 224×224 piksel memanfaatkan keunggulan backbone CSPDarknet dan modul C2f untuk menghasilkan ekstraksi fitur yang sangat cepat dan presisi (Terven et al., 2023). Model ini dikuantisasi ke dalam format TensorFlow Lite dan diintegrasikan ke dalam arsitektur aplikasi mobile React Native (Expo SDK 54) menggunakan antarmuka C++ JSI (`react-native-fast-tflite`), memungkinkan eksekusi inferensi berkecepatan tinggi (~3,2 ms per citra) langsung di prosesor smartphone tanpa koneksi internet. Dengan dukungan basis data lokal `expo-sqlite` (Supriyadi & Widiastuti, 2023), sistem ini menawarkan solusi mandiri, praktis, dan berakurasi tinggi (98,87%) bagi petani kakao di lapangan.

---

### 2.2 Dasar Teori

#### 2.2.1 Tanaman Kakao

Tanaman kakao (*Theobroma cacao L.*) merupakan tumbuhan pohon tahunan yang berasal dari hutan hujan tropis Amerika Selatan dan termasuk ke dalam famili *Malvaceae*. Tanaman ini tumbuh optimal pada ketinggian 0–600 meter di atas permukaan laut dengan curah hujan tahunan antara 1.500 hingga 2.500 mm dan temperatur lingkungan berkisar $24^\circ\text{C}$ hingga $30^\circ\text{C}$ (Alvarado et al., 2025). Secara morfologis, pohon kakao memiliki tinggi antara 4 hingga 8 meter dengan sistem perakaran tunggang dan daun berbentuk lanset oval berwarna hijau tua. Karakteristik reproduksi kakao bersifat *cauliflory*, di mana kuncup bunga tumbuh langsung dari bantalan bunga pada batang utama dan cabang tua (*ramiflory*). Bunga yang terserbuki akan berkembang menjadi buah kakao (*cacao pod*) yang berbentuk bulat lonjong dengan alur kulit bervariasi. Dinding kulit buah (*pericarp*) menyumbang sekitar 80% dari total biomassa buah, membungkus 30 hingga 40 butir biji yang diselimuti oleh pulp putih beraroma manis asam (*mucilage*) (Alvarado et al., 2025; Gado & Primandari, 2025).

#### 2.2.2 Produksi Kakao di Indonesia

Indonesia menempati jajaran produsen kakao terbesar di dunia, bersaing secara ketat dengan Pantai Gading, Ghana, dan Ekuador (Alvarado et al., 2025). Berdasarkan data resmi Badan Pusat Statistik (BPS, 2023), produksi biji kakao nasional terkonsentrasi di Pulau Sulawesi sebagai sabuk utama produksi kakao, meliputi Sulawesi Tengah, Sulawesi Selatan, Sulawesi Tenggara, dan Sulawesi Barat, yang memasok lebih dari 60% total hasil panen nasional. Sentra produksi sekunder tersebar di Sumatera (Lampung, Sumatera Barat, Sumatera Utara), Jawa, Bali, Nusa Tenggara, dan Papua. Pola budidaya kakao di Indonesia memiliki keunikan karena lebih dari 98% areal perkebunan dimiliki dan dikelola secara mandiri oleh petani kecil swadaya (perkebunan rakyat), sementara sisanya diusahakan oleh Perkebunan Besar Negara (PBN) dan Perkebunan Besar Swasta (PBS). Namun, produktivitas rata-rata nasional yang belum optimal menunjukkan perlunya intervensi teknologi guna menekan laju kehilangan hasil akibat cekaman hama dan penyakit di tingkat petani rakyat.

#### 2.2.3 Peran Kakao dalam Sektor Perkebunan

Komoditas kakao memiliki peran multifaset yang sangat fundamental dalam struktur perekonomian Indonesia. Selain bertindak sebagai sumber perolehan devisa ekspor non-migas, industri kakao dari hulu ke hilir menyerap tenaga kerja dalam jumlah yang masif, mulai dari kegiatan pemeliharaan kebun, panen, fermentasi, pedagang pengumpul, hingga industri pengolahan bubuk kakao, mentega kakao (*cocoa butter*), dan produk pangan cokelat olahan (Novanto et al., 2025). Keberhasilan agribisnis kakao secara langsung merefleksikan tingkat kesejahteraan sosial-ekonomi jutaan rumah tangga petani di wilayah pelosok. Penurunan produksi yang disebabkan oleh ledakan epidemi penyakit tidak hanya menggerus pendapatan petani secara drastis, melainkan juga memicu kelangkaan pasokan bahan baku bagi industri manufaktur pengolahan kakao domestik (Ariawan et al., 2025).

#### 2.2.4 Penyakit pada Buah Kakao

Kesehatan buah kakao merupakan determinan utama kualitas biji kering yang dihasilkan. Cekaman biologis yang menyerang buah kakao dikelompokkan ke dalam tiga kelas utama:

1. **Busuk Buah Hitam (*Black Pod Rot*):** Disebabkan oleh infeksi cendawan oomycetes *Phytophthora palmivora*. Patogen ini berkembang biak sangat pesat pada kondisi kelembapan nisbi mendekati 100% dan curah hujan tinggi (Alvarado et al., 2025). Gejala awal ditandai dengan munculnya bercak cokelat kecil dengan batas tegas pada permukaan kulit buah, baik yang berawal dari tangkai buah (*stem end*) maupun ujung buah (*apical end*). Dalam hitungan hari, bercak nekrotik tersebut meluas menutupi seluruh kulit buah, berubah warna menjadi hitam legam, dan mengalami pembusukan basah. Pada fase lanjut, miselium dan sporangia cendawan menembus lapisan endokarp, merusak jaringan biji hingga menghitam dan membusuk, serta mengeluarkan serbuk spora keputihan di permukaan kulit buah (Ferraris et al., 2023).
2. **Penggerek Buah Kakao (*Pod Borer*):** Disebabkan oleh larva serangga ngengat *Conopomorpha cramerella*. Ngengat betina meletakkan telur pada alur kulit buah kakao muda. Setelah menetas, larva menggerek masuk ke dalam daging buah dan memakan jaringan plasenta pembungkus biji serta saluran hara (Ariawan et al., 2025). Gejala visual eksternal ditandai dengan pola perubahan warna buah yang belang-belang kuning atau oranye tidak merata sebelum waktunya (*uneven early ripening*). Di samping itu, permukaan kulit buah menunjukkan bintik-bintik bekas gerek dan liang keluar larva yang mengeluarkan serbuk kotoran. Ketika buah dibelah, biji kakao saling melekat satu sama lain dan melekat kuat pada kulit bagian dalam (*clumping*), berukuran pipih, keras, dan sulit dikeluarkan saat panen (Maylianti et al., 2025).
3. **Buah Sehat (*Healthy*):** Menampilkan permukaan kulit buah yang mulus, bersih dari bercak nekrosis, memiliki warna hijau seragam saat masih muda atau bertransformasi menjadi kuning/oranye cerah merata saat matang, tanpa disertai deformasi bentuk, liang gerek serangga, atau kolonisasi miselium jamur patogen (Ariawan et al., 2025; Gado & Primandari, 2025).

#### 2.2.5 Deteksi Penyakit Tanaman Menggunakan Teknologi

Modernisasi sektor agrikultur mendorong adopsi teknologi visi komputer (*Computer Vision*) dan kecerdasan buatan (*Artificial Intelligence*) guna mengotomatisasi diagnosis patologi tanaman secara presisi (Alvarado et al., 2025). Sebelum maraknya era deep learning, deteksi penyakit tanaman didominasi oleh pendekatan rekayasa fitur manual (*handcrafted feature extraction*), seperti *Histogram of Oriented Gradients* (HOG) dan *Local Binary Pattern* (LBP) yang dipadukan dengan pengklasifikasi *Support Vector Machine* (SVM) atau *Random Forest* (Fuentes et al., 2017; Novanto et al., 2025). Namun, metode konvensional tersebut sangat rapuh terhadap variasi intensitas pencahayaan alami di kebun, perubahan sudut pengambilan citra, serta interferensi latar belakang dedaunan dan tanah. Hadirnya arsitektur jaringan saraf konvolusional mendisrupsi paradigma tersebut melalui kemampuan ekstraksi fitur hierarkis secara otomatis langsung dari larik piksel citra mentah (*end-to-end learning*), yang terbukti menghasilkan keandalan deteksi yang jauh lebih superior (Mohanty et al., 2016; Ramcharan et al., 2017).

#### 2.2.6 Pengolahan Citra Digital

Citra digital tersusun atas matriks piksel diskret dua dimensi $f(x, y)$ yang merepresentasikan intensitas spektral pada koordinat spasial tertentu. Dalam ruang warna RGB (*Red, Green, Blue*), citra memiliki tiga saluran warna independen dengan kedalaman intensitas masing-masing bernilai integer antara 0 hingga 255 (Octavian et al., 2024). Tahap pra-pemrosesan citra digital (*image preprocessing*) memegang peranan krusial untuk menstandarisasi input sebelum diumpankan ke model deep learning. Proses penyesuaian ukuran (*image resizing*) diterapkan untuk mengubah resolusi spasial citra asli ($1080 \times 1080$ piksel) menjadi resolusi standar $224 \times 224$ piksel menggunakan interpolasi bilinear, guna menekan beban komputasi floating point tanpa menghilangkan fitur diagnostik penting (Ariawan et al., 2025; Khan et al., 2023). Selanjutnya, teknik normalisasi intensitas piksel dilakukan dengan mentransformasikan rentang nilai $[0, 255]$ ke interval kontinu $[0, 1]$ atau standardisasi skor-z (*z-score normalization*) berdasarkan rata-rata dan deviasi standar kanal ImageNet (Terven et al., 2023). Untuk memperkaya variasi representasi spasial dan mencegah *overfitting*, teknik augmentasi data geometris dan fotometris diterapkan, mencakup *random horizontal flip*, rotasi acak, distorsi skala, penyesuaian kecerahan (*brightness jitter*), dan penyesuaian kontras (Octavian et al., 2024; Siahaan et al., 2024).

#### 2.2.7 Machine Learning

*Machine Learning* (pembelajaran mesin) merupakan cabang kecerdasan buatan yang memungkinkan algoritma komputer mempelajari pola, keteraturan, dan hubungan matematis dari sekumpulan data sampel tanpa diprogram secara eksplisit berbasis aturan kaku (*rule-based systems*). Dalam paradigma pembelajaran terawasi (*supervised learning*), algoritma diberikan sekumpulan data latih berpasangan $\{(x_i, y_i)\}_{i=1}^N$, di mana $x_i$ merepresentasikan vektor fitur input dan $y_i$ merupakan label target kelas yang telah diverifikasi (Octavian et al., 2024). Tujuan utama dari algoritma pembelajaran terawasi adalah meminimalkan fungsi kerugian (*loss function*) melalui optimasi parameter bobot internal, sehingga model memperoleh kapasitas generalisasi yang tangguh dalam memprediksi label kelas pada data baru yang belum pernah diobservasi sebelumnya.

#### 2.2.8 Deep Learning

*Deep Learning* merupakan subbidang machine learning yang memanfaatkan arsitektur jaringan saraf tiruan berlapis banyak (*deep neural networks*) untuk memodelkan abstraksi data tingkat tinggi (Mohanty et al., 2016). Berbeda dengan machine learning klasik yang membutuhkan rekayasa fitur manual yang rumit dan rentan bias manusiawi, deep learning secara inheren mengekstrak representasi fitur bertingkat (*hierarchical feature representation*). Lapisan-lapisan awal jaringan bertugas menangkap fitur-fitur primitif berfrekuensi spasial tinggi seperti tepi, garis, dan gradien warna; lapisan menengah merangkai fitur primitif tersebut menjadi tekstur dan kontur lokal; sedangkan lapisan-lapisan terdalam memadukannya menjadi representasi semantik global dari objek (Ramcharan et al., 2017; Terven et al., 2023). Arsitektur deep learning modern mengintegrasikan regularisasi canggih seperti *batch normalization*, koneksi lewatan (*residual skip connections*), dan fungsi aktivasi non-linear yang memungkinkan pelatihan ratusan lapisan jaringan secara stabil tanpa mengalami kendala degradasi gradien (*vanishing gradient*) (Fuentes et al., 2017).

#### 2.2.9 Convolutional Neural Network (CNN)

*Convolutional Neural Network* (CNN) merupakan arsitektur deep learning spesialisasi pemrosesan data berstruktur grid dua dimensi seperti citra digital. Struktur dasar CNN terdiri atas tiga blok fungsional utama (Mohanty et al., 2016; Maylianti et al., 2025):

1. **Lapisan Konvolusi (*Convolutional Layer*):** Melakukan operasi perkalian dot tergeser (*sliding dot product*) antara larik input dan matriks filter (*kernel*) berukuran kecil (misalnya $3 \times 3$) yang dilengkapi dengan bias. Operasi ini mengekstraksi peta fitur (*feature map*) spasial secara invarian terhadap translasi posisi objek.
2. **Fungsi Aktivasi Non-Linear:** Menginjeksikan non-linearitas ke dalam sistem agar jaringan mampu mempelajari pola-pola matematis yang kompleks. Fungsi aktivasi modern yang banyak digunakan meliputi *Rectified Linear Unit* (ReLU) dengan formula $f(x) = \max(0, x)$ serta *Sigmoid Linear Unit* (SiLU / Swish) yang dirumuskan sebagai $f(x) = x \cdot \sigma(x) = \frac{x}{1 + e^{-x}}$, yang terbukti menjaga aliran gradien lebih mulus pada arsitektur YOLO generasi mutakhir (Gado & Primandari, 2025; Terven et al., 2023).
3. **Lapisan Pengurangan Dimensi (*Pooling Layer*):** Mereduksi dimensi spasial peta fitur (misalnya melalui *Max Pooling* atau *Average Pooling*) guna mengurangi jumlah parameter komputasi serta meningkatkan invariansi terhadap perubahan skala dan distorsi minor (Gado & Primandari, 2025).
4. **Lapisan Terhubung Penuh (*Fully Connected Layer*):** Memetakan seluruh fitur representasi tingkat tinggi yang telah diratakan (*flattened*) ke dalam neuron keluaran yang merepresentasikan probabilitas kelas target menggunakan fungsi *Softmax* multi-kelas (Mohanty et al., 2016).

#### 2.2.10 Transfer Learning

*Transfer Learning* merupakan metodologi pemanfaatan bobot parameter (*weights*) dari model deep learning yang telah dilatih sebelumnya (*pre-trained*) pada himpunan data skala masif (seperti ImageNet yang memuat lebih dari 1,2 juta citra dan 1.000 kategori kelas) untuk menyelesaikan tugas klasifikasi pada domain target yang memiliki ketersediaan data lebih terbatas (Ramcharan et al., 2017; Octavian et al., 2024). Melalui transfer learning, lapisan-lapisan pengekstraksi fitur dasar (*backbone*) mempertahankan kemampuan visual umum (seperti deteksi tekstur, sudut, dan gradien warna), sementara lapisan klasifikasi akhir diinisialisasi ulang dan disesuaikan (*fine-tuned*) menggunakan tingkat pembelajaran (*learning rate*) yang adaptif terhadap dataset penyakit kakao. Pendekatan ini mempercepat konvergensi pelatihan secara dramatis, menghemat daya komputasi GPU, serta mencegah fenomena *overfitting* yang umum terjadi pada dataset domain agrikultur berukuran kecil hingga menengah (Ariawan et al., 2025; Maylianti et al., 2025).

#### 2.2.11 Model YOLOv8 (You Only Look Once v8)

Arsitektur YOLOv8 yang diperkenalkan oleh Ultralytics pada tahun 2023 merepresentasikan evolusi terdepan dalam ekosistem visi komputer terpadu (Terven et al., 2023). Berakar dari kesuksesan varian pendahulunya, YOLOv8 menghadirkan restrukturisasi fundamental pada komponen pengekstraksi fitur dengan memperkenalkan modul C2f (*Cross-Stage Partial with 2 Convolutions*). Modul C2f mengombinasikan keunggulan konsep *Cross-Stage Partial Network* (CSPNet) dengan blok *residual bottleneck* yang terinspirasi dari arsitektur ELAN (*Efficient Layer Aggregation Network*), sehingga memungkinkan penggabungan aliran gradien informasi tingkat tinggi tanpa membebani kompleksitas komputasi (Ghafar et al., 2024; Siahaan et al., 2024).

Berbeda dengan varian deteksi objek yang memerlukan modul *neck* *Path Aggregation Network* (PANet) dan mekanisme kepala deteksi tanpa jangkar (*anchor-free detection head*) untuk memprediksi koordinat bounding box, varian klasifikasi YOLOv8 (`yolov8-cls`) memangkas seluruh struktur kepala deteksi spasial tersebut. Sebagaimana divisualisasikan dalam Gambar 2.1, arsitektur `yolov8-cls` merutekan peta fitur keluaran lapisan *backbone* tahap terdalam secara langsung ke lapisan *Spatial Pyramid Pooling Fast* (SPPF), diikuti oleh lapisan *Global Average Pooling* (GAP), lapisan penyusutan linier, dan lapisan klasifikasi murni berbasis fungsi *Softmax* (Terven et al., 2023). Varian `yolov8s-cls` (*Small Classification*) memiliki keseimbangan ideal antara kapasitas parameter (~5 juta parameter) dan efisiensi waktu inferensi (~3,2 ms per citra pada CPU seluler), menjadikannya arsitektur yang sangat optimal untuk tugas klasifikasi citra terisolasi pada perangkat keras berdaya rendah (Khan et al., 2023).

```
[ Input Citra Buah Kakao: 224 x 224 x 3 ]
                   │
                   ▼
┌────────────────────────────────────────────────────────┐
│        YOLOv8 BACKBONE (Modified CSPDarknet)           │
│  - Konvolusi Bertingkat (Conv 3x3, Stride 2)           │
│  - Modul C2f (Cross-Stage Partial w/ 2 Convolutions)   │
│  - Fungsi Aktivasi SiLU (Sigmoid Linear Unit)          │
└────────────────────────────────────────────────────────┘
                   │
                   ▼
┌────────────────────────────────────────────────────────┐
│     SPPF (Spatial Pyramid Pooling Fast - MaxPool 5x5)   │
└────────────────────────────────────────────────────────┘
                   │
                   ▼
┌────────────────────────────────────────────────────────┐
│           GLOBAL AVERAGE POOLING (GAP) LAYER           │
│            Mereduksi fitur spasial ke vektor 1D         │
└────────────────────────────────────────────────────────┘
                   │
                   ▼
┌────────────────────────────────────────────────────────┐
│               LINEAR DENSE / DROPOUT LAYER             │
└────────────────────────────────────────────────────────┘
                   │
                   ▼
┌────────────────────────────────────────────────────────┐
│         CLASSIFICATION HEAD (3 Unit Output Softmax)    │
│    [ Black Pod Rot ]    [ Pod Borer ]    [ Healthy ]   │
└────────────────────────────────────────────────────────┘

```

**Gambar 2.1** Diagram Arsitektur Jaringan Klasifikasi YOLOv8 (`yolov8s-cls`)

#### 2.2.12 Progressive Web Apps (PWA) vs Native Mobile Apps

Dalam rekayasa perangkat lunak modern, pemilihan arsitektur deployment aplikasi berorientasi pada kompromi antara portabilitas dan aksesibilitas perangkat keras. *Progressive Web Apps* (PWA) beroperasi di atas lingkungan peramban web (*browser runtime*) menggunakan teknologi HTML5, CSS, dan JavaScript (Susila & Arsa, 2023). Meskipun PWA menawarkan kemudahan pembaruan kode tanpa melalui proses distribusi toko aplikasi, PWA memiliki keterbatasan mendasar dalam hal akses akselerasi perangkat keras grafis tingkat rendah (*low-level GPU/NPU acceleration*) dan penanganan pemrosesan aliran kamera berspesifikasi tinggi (*frame-by-frame stream*). Sebaliknya, *Native Mobile Apps* dieksekusi secara langsung di atas sistem operasi seluler (Android Runtime / ART), memberikan akses penuh terhadap instruksi prosesor asli, alokasi memori berkecepatan tinggi, dan antarmuka perangkat keras kamera tanpa perantara lapisan emulasi peramban, yang merupakan syarat mutlak bagi eksekusi inferensi Edge AI secara mulus (Natbais & Umbu, 2023).

#### 2.2.13 Aplikasi Mobile & Framework React Native

Aplikasi mobile native yang dikembangkan menggunakan framework *React Native* memungkinkan penulisan kode berbasis bahasa TypeScript yang dikompilasi secara efisien ke dalam komponen native Android dan iOS (Siahaan et al., 2024). Dalam arsitektur React Native modern (khususnya ekosistem Expo SDK 54), mekanisme komunikasi lama berbasis antarmuka asinkronus serialisasi JSON (*Asynchronous JSON Bridge*) telah digantikan sepenuhnya oleh arsitektur baru berbasis *JavaScript Interface* (JSI). JSI memungkinkan kode JavaScript/TypeScript memegang referensi memori langsung (*direct C++ host object reference*) ke kode native C++ di tingkat sistem operasi (Natbais & Umbu, 2023). Pustaka kamera modern seperti `react-native-vision-camera` v5.2.2 memanfaatkan JSI untuk menyediakan fitur *Frame Processors*, di mana setiap *frame buffer* citra yang ditangkap oleh sensor kamera gawai pada resolusi tinggi dapat dialirkan secara langsung ke pustaka inferensi neural network tanpa mengalami penundaan (*zero-copy buffer delay*).

#### 2.2.14 Dataset dan Pelatihan Model

Pelatihan model klasifikasi deep learning terawasi dilakukan dengan mengoptimalkan fungsi kerugian *Categorical Cross-Entropy Loss* multi-kelas, yang dirumuskan secara matematis sebagai berikut:


$$\mathcal{L}_{CE} = -\sum_{c=1}^M y_c \log(\hat{y}_c)$$


di mana $M$ merupakan jumlah total kelas kategori target ($M = 3$), $y_c$ merupakan elemen biner bernilai 1 jika sampel data berlabel kelas ground-truth $c$ dan bernilai 0 untuk kelas lainnya, serta $\hat{y}_c$ melambangkan probabilitas prediksi model untuk kelas $c$ yang dihasilkan oleh fungsi aktivasi Softmax (Novanto et al., 2025; Maylianti et al., 2025). Proses pembaruan bobot model memanfaatkan algoritma pengoptimal *AdamW* (*Adaptive Moment Estimation with Decoupled Weight Decay*) yang memisahkan penalti peluruhan bobot (*weight decay regularization*) dari perhitungan momen gradien pertama dan kedua. Konfigurasi siklus pelatihan dikendalikan melalui hiperparameter jumlah *epoch* (siklus iterasi penuh atas seluruh data latih), *batch size* (kuantitas sampel per pembaruan bobot), dan tingkat pembelajaran awal (*initial learning rate*) yang disesuaikan secara dinamis menggunakan penjadwal *Cosine Annealing* (Terven et al., 2023).

#### 2.2.15 Evaluasi Kinerja Model

Evaluasi performa klasifikasi citra dalam penelitian ini dihitung secara matematis berdasarkan matriks kontingensi multi-kelas (*Confusion Matrix*) yang merepresentasikan distribusi hasil prediksi terhadap label aktual sebenarnya (Novanto et al., 2025; Octavian et al., 2024). Formulasi metrik evaluasi sah yang digunakan mencakup:

1. **Akurasi (*Accuracy*):** Rasio total prediksi benar (baik positif maupun negatif) terhadap keseluruhan jumlah sampel data uji:

$$\text{Accuracy} = \frac{TP + TN}{TP + TN + FP + FN}$$


2. **Presisi (*Precision*):** Proporsi sampel yang benar-benar positif di antara keseluruhan sampel yang diprediksi sebagai positif oleh model:

$$\text{Precision} = \frac{TP}{TP + FP}$$


3. **Sensitivitas / *Recall*:** Kemampuan model dalam menemukan dan mengklasifikasikan kembali seluruh sampel yang secara aktual berlabel positif:

$$\text{Recall} = \frac{TP}{TP + FN}$$


4. **F1-Score:** Rata-rata harmonik (*harmonic mean*) antara presisi dan recall yang memberikan penilaian berimbang, terutama pada kondisi data uji dengan sebaran kelas yang dinamis:

$$\text{F1-Score} = 2 \times \frac{\text{Precision} \times \text{Recall}}{\text{Precision} + \text{Recall}}$$



di mana $TP$ (*True Positive*) melambangkan data positif yang diprediksi benar, $TN$ (*True Negative*) melambangkan data negatif yang diprediksi benar, $FP$ (*False Positive*) melambangkan data negatif aktual yang keliru diprediksi sebagai positif, dan $FN$ (*False Negative*) melambangkan data positif aktual yang keliru diprediksi sebagai negatif (Maylianti et al., 2025; Octavian et al., 2024). Penelitian ini secara tegas **tidak** mengikutsertakan metrik *mean Average Precision* (mAP), karena mAP merupakan metrik integral kurva presisi-recall spasial yang hanya diperuntukkan bagi tugas deteksi objek kotak pembatas (*bounding box*).

#### 2.2.16 Bahasa Pemrograman TypeScript

*TypeScript* merupakan bahasa pemrograman berspesifikasi tinggi (*statically typed superset of JavaScript*) yang dikembangkan oleh Microsoft untuk membangun perangkat lunak berskala menengah hingga besar dengan keandalan kode yang tinggi. Dengan menyediakan sistem pengetikan statis (*static type checking*), antarmuka (*interfaces*), dan tipe data generik, TypeScript mengeliminasi potensi galat komputasi waktu-nyata (*runtime errors*) seperti *undefined variable access* dan ketidaksesuaian tipe larik piksel citra sebelum kode dikompilasi ke lingkungan produksi (Siahaan et al., 2024). Hal ini sangat krusial dalam rekayasa aplikasi edge computing yang mengelola konversi tensor larik biner secara intensif.

#### 2.2.17 On-Device Edge AI & TensorFlow Lite (Fast-TFLite & SQLite)

*On-Device Edge AI* merupakan paradigma pemrosesan kecerdasan buatan di mana model inferensi machine learning dieksekusi secara lokal langsung pada perangkat keras komputasi tepi (seperti prosesor smartphone), tanpa melakukan *offloading* kalkulasi ke peladen komputasi awan eksternal (Natbais & Umbu, 2023; Siahaan et al., 2024). Untuk mewujudkan eksekusi model deep learning pada perangkat mobile dengan latensi minimal dan konsumsi daya rendah, model PyTorch (`.pt`) hasil pelatihan dikonversi dan dikuantisasi ke dalam format *TensorFlow Lite* (`.tflite`). Kuantisasi bobot dari presisi *floating point* 32-bit (FP32) ke representasi numerik yang lebih efisien (FP16 atau INT8) mampu mereduksi ukuran berkas biner model hingga 50%–75% serta mempercepat eksekusi instruksi matriks pada unit akselerator perangkat keras gawai (CPU/GPU/NPU) (Khan et al., 2023; Natbais & Umbu, 2023).

Dalam aplikasi Android yang dibangun, eksekusi model `.tflite` memanfaatkan pustaka performa tinggi `react-native-fast-tflite` v3.0.1. Pustaka ini mengimplementasikan jembatan C++ JSI yang memanggil API native *TensorFlow Lite C Runtime* secara langsung tanpa overhead serialisasi thread JavaScript, menghasilkan waktu inferensi super cepat di bawah 5 milidetik per citra. Untuk mendukung paradigma luring penuh (*offline-first*), hasil pemindaian yang mencakup label prediksi kelas penyakit, tingkat probabilitas keyakinan (*confidence score*), timestamp waktu pemindaian, dan referensi berkas citra disimpan secara permanen ke dalam basis data relasional lokal tersemat menggunakan pustaka `expo-sqlite` (Supriyadi & Widiastuti, 2023).

#### 2.2.18 Perancangan UI/UX Menggunakan Figma

Perancangan antarmuka pengguna (*User Interface* / UI) dan pengalaman pengguna (*User Experience* / UX) diarahkan pada prinsip desain yang berpusat pada pengguna (*user-centered design*). Mengingat target pengguna akhir adalah petani perkebunan rakyat yang membutuhkan kemudahan pengoperasian di lapangan terbuka, rancangan antarmuka harus memprioritaskan kontras visual yang tajam, hierarki tipografi yang jelas, tombol navigasi berukuran besar (*accessible touch target*), dan alur interaksi yang minimalis (Susila & Arsa, 2023). Perangkat lunak Figma digunakan sebagai platform kolaboratif untuk merancang *wireframe*, diagram alur navigasi pengguna, palet sistem desain berbasis TailwindCSS (NativeWind v4), serta prototipe interaktif aplikasi mobile sebelum diimplementasikan ke dalam kode program (Siahaan et al., 2024).

#### 2.2.19 Metode Waterfall

Metode *Waterfall* merupakan model siklus hidup pengembangan perangkat lunak (*Software Development Life Cycle* / SDLC) klasik yang mengadopsi pendekatan sekuensial linier terstruktur (Supriyadi & Widiastuti, 2023; Susila & Arsa, 2023). Model ini menetapkan bahwa setiap tahapan rekayasa harus diselesaikan dan diverifikasi secara tuntas sebelum melangkah ke tahapan berikutnya, sehingga meminimalisasi risiko deviasi spesifikasi sistem (Siahaan et al., 2024). Tahapan Waterfall terbagi atas lima fase:

1. **Analisis Kebutuhan (*Requirements Analysis*):** Mengidentifikasi dan mendokumentasikan seluruh spesifikasi fungsional dan non-fungsional perangkat lunak, kebutuhan dataset, dan batasan komputasi perangkat keras mobile.
2. **Perancangan Sistem (*System Design*):** Mentranslasikan kebutuhan ke dalam cetak biru arsitektur perangkat lunak, perancangan antarmuka UI/UX di Figma, pemodelan sistem berbasis UML, dan perancangan skema relasi basis data lokal.
3. **Implementasi / Pengkodean (*Implementation / Coding*):** Mengonversi desain sistem ke dalam instruksi kode program menggunakan bahasa TypeScript, framework React Native, pelatihan model YOLOv8, dan kompilasi modul C++ Fast-TFLite.
4. **Pengujian Perangkat Lunak (*Testing*):** Mengevaluasi kesesuaian sistem secara komprehensif menggunakan pengujian metrik deep learning dan pengujian fungsionalitas kotak hitam (*Black-Box Testing*) pada gawai Android fisik (Supriyadi & Widiastuti, 2023; Natbais & Umbu, 2023).
5. **Pemeliharaan (*Maintenance*):** Memperbaiki galat (*bugs*) yang teridentifikasi pasca-rilis, memperbarui dependensi pustaka, dan mengoptimalkan kestabilan aplikasi seluler.

#### 2.2.20 Pemodelan UML (Unified Modeling Language)

*Unified Modeling Language* (UML) merupakan standar industri bahasa pemodelan visual untuk menspesifikasikan, memvisualisasikan, membangun, dan mendokumentasikan artefak dari sistem perangkat lunak berorientasi objek (Supriyadi & Widiastuti, 2023; Susila & Arsa, 2023). Diagram UML yang digunakan dalam perancangan aplikasi ini meliputi:

1. **Use Case Diagram:** Memetakan interaksi fungsional antara pengguna (petani) dengan kapabilitas yang disediakan oleh sistem aplikasi mobile.
2. **Activity Diagram:** Memodelkan aliran kerja prosedural (*workflow*) dari sistem, mencakup alur inisialisasi kamera, penangkapan frame citra, proses inferensi lokal, hingga penyimpanan riwayat.
3. **Sequence Diagram:** Menggambarkan pertukaran pesan dinamis antarentitas objek perangkat lunak (antarmuka pengguna, controller kamera, mesin inferensi Fast-TFLite, dan basis data SQLite) berdasarkan urutan waktu kejadian.
4. **Class Diagram:** Menyajikan struktur statis dari kelas-kelas perangkat lunak, tipe data, relasi dependensi, dan skema tabel entitas basis data lokal `expo-sqlite` (Supriyadi & Widiastuti, 2023).

---

### 2.3 Hipotesis Penelitian

Berdasarkan tinjauan teoretis dan kajian pustaka empiris yang telah diuraikan, hipotesis yang diajukan dalam penelitian ini dirumuskan sebagai berikut:

* **Hipotesis Nol ($H_0$):**
Implementasi model `yolov8s-cls` berbasis transfer learning tidak mampu menghasilkan performa klasifikasi yang memuaskan (Akurasi Top-1 $< 90\%$) dalam mengidentifikasi tiga kondisi buah kakao (*Black Pod Rot*, *Pod Borer*, dan *Healthy*), serta tidak layak dieksekusi secara instan (latensi inferensi $\ge 100\text{ ms}$) pada perangkat mobile Android luring.
* **Hipotesis Alternatif ($H_a$):**
Implementasi model `yolov8s-cls` berbasis transfer learning mampu menghasilkan performa klasifikasi yang unggul (Akurasi Top-1 $\ge 95\%$) dalam mengidentifikasi tiga kondisi buah kakao (*Black Pod Rot*, *Pod Borer*, dan *Healthy*), serta mampu dieksekusi secara instan dan efisien (latensi inferensi $< 10\text{ ms}$) pada perangkat mobile Android luring berbasis TensorFlow Lite dan C++ JSI.

---

## BAB III — METODE PENELITIAN

### 3.1 Metode Pengumpulan Data

#### 3.1.1 Observasi

Observasi lapangan dilakukan untuk mengidentifikasi tantangan operasional nyata yang dihadapi oleh petani perkebunan kakao rakyat di wilayah sentra produksi pedesaan. Pengamatan difokuskan pada kendala identifikasi visual manual terhadap serangan patogen *Phytophthora palmivora* dan hama *Conopomorpha cramerella*, tingginya risiko salah diagnosis pada fase infeksi dini, serta keterbatasan infrastruktur telekomunikasi seluler di areal perkebunan yang didominasi oleh titik buta sinyal internet (*blank spot areas*). Temuan observasi ini memperkuat landasan perancangan sistem diagnosis yang harus mengadopsi paradigma komputasi lokal luring (*offline-first on-device processing*).

#### 3.1.2 Studi Literatur

Studi literatur dilakukan dengan mengekstraksi dan mensintesis 17 artikel jurnal ilmiah bereputasi internasional dan nasional yang diperoleh dari basis data bereputasi (MDPI, Frontiers, IEEE, Elsevier, dan SINTA) terkait kecerdasan buatan, visi komputer pertanian, model YOLO, dan rekayasa perangkat lunak seluler. Kajian pustaka ini membedah metodologi klasifikasi penyakit kakao (Alvarado et al., 2025; Ariawan et al., 2025; Ferraris et al., 2023; Maylianti et al., 2025; Novanto et al., 2025), evolusi dan visualisasi model YOLOv8 (Ghafar et al., 2024; Khan et al., 2023; Terven et al., 2023), pembelajaran deep learning tanaman (Fuentes et al., 2017; Mohanty et al., 2016; Octavian et al., 2024; Ramcharan et al., 2017), deployment mobile edge AI TensorFlow Lite (Gado & Primandari, 2025; Natbais & Umbu, 2023; Siahaan et al., 2024), serta metodologi Waterfall dan pemodelan sistem UML (Supriyadi & Widiastuti, 2023; Susila & Arsa, 2023).

#### 3.1.3 Dokumentasi

Dokumentasi dilaksanakan melalui pengunduhan dan penelaahan dataset sekunder publik citra buah kakao yang dipublikasikan oleh Zaldy Jr pada platform Kaggle (`cacao-diseases`). Dataset ini memuat 4.300 citra berkualitas tinggi beresolusi $1080 \times 1080$ piksel yang mencakup tiga kelas kondisi buah kakao (*Black Pod Rot*, *Pod Borer*, dan *Healthy*). Dokumentasi meliputi struktur berkas, meta-data label, verifikasi visual kebenaran patologi, serta distribusi sampel antarkelas.

---

### 3.2 Alat dan Bahan

Kebutuhan instrumen perangkat keras, perangkat lunak, bahan dataset, dan distribusi partisi data dirinci pada tabel-tabel berikut:

**Tabel 3.1** Spesifikasi Perangkat Keras yang Digunakan

| Kategori Instrumen | Komponen Perangkat Keras | Spesifikasi Teknis | Fungsi dalam Penelitian |
| --- | --- | --- | --- |
| Komputer Pengembangan (*Workstation*) | Laptop Lenovo Legion 5 | Prosesor AMD Ryzen 7 5800H @ 3.20 GHz (8 Cores, 16 Threads), RAM 16 GB DDR4, SSD 512 GB NVMe PCIe, GPU NVIDIA GeForce RTX 3060 6 GB GDDR6 | Lingkungan pengkodean aplikasi mobile, pra-pemrosesan citra lokal, dan manajemen repositori kode. |
| Lingkungan Pelatihan Cloud | Google Colaboratory Pro | GPU NVIDIA Tesla T4 / A100-SXM4 (VRAM 16 GB - 40 GB), High-RAM 25 GB, Cloud Disk 150 GB | Pelatihan terakselerasi model deep learning `yolov8s-cls` dan ekspor bobot jaringan. |
| Perangkat Uji Seluler (*Physical Edge Device*) | Smartphone Android Xiaomi Redmi Note 11 | Prosesor Qualcomm Snapdragon 680 (6 nm, Octa-Core up to 2.4 GHz), Adreno 610 GPU, RAM 6 GB, Storage 128 GB, Android 12 (MIUI 13), Kamera Utama 50 MP | Pengujian kinerja inferensi lokal (*on-device testing*), pengukuran latensi waktu-nyata, dan pengujian black-box aplikasi. |

**Tabel 3.2** Perangkat Lunak yang Digunakan

| Kategori Perangkat Lunak | Nama Perangkat Lunak / Framework | Versi | Fungsi / Peruntukan |
| --- | --- | --- | --- |
| Sistem Operasi | Microsoft Windows 11 Pro 64-bit | 23H2 | Sistem operasi utama lingkungan pengembangan lokal. |
| *Integrated Development Environment* | Visual Studio Code & Android Studio | VS Code v1.94, Android Studio Hedgehog | Penyuntingan kode program TypeScript, kompilasi native build tools, dan Android Virtual Device (AVD). |
| Lingkungan Bahasa Pemrograman | Python & Node.js | Python v3.10.12, Node.js v20.11.0 (LTS) | Eksekusi skrip pipeline pelatihan model dan runtime ekosistem npm JavaScript/TypeScript. |
| Framework Deep Learning | Ultralytics YOLOv8 & PyTorch | Ultralytics v8.1.0, PyTorch v2.1.2 + CUDA 11.8 | Pembangunan, pelatihan, transfer learning, dan validasi model klasifikasi `yolov8s-cls`. |
| Framework Edge Inference | TensorFlow & TensorFlow Lite Converter | TensorFlow v2.15.0 | Konversi dan kuantisasi model PyTorch (`.pt`) menjadi model biner seluler (`.tflite`). |
| Framework Aplikasi Mobile | React Native (Expo) | Expo SDK 54, React Native v0.76.x | Kerangka kerja pengembangan aplikasi mobile Android lintas-platform berbasis native. |
| Bahasa Pemrograman Aplikasi | TypeScript | TypeScript v5.3.3 | Bahasa pemrograman statis untuk pengembangan kode aplikasi seluler yang andal. |
| Styling UI Aplikasi | NativeWind | v4.0.1 (TailwindCSS v3.3) | Manajemen penataan gaya (*styling*) antarmuka aplikasi secara deklaratif dan responsif. |
| Pustaka Akselerator Kamera | `react-native-vision-camera` | v5.2.2 | Akses kamera native real-time berperforma tinggi berbasis C++ JSI frame processor. |
| Pustaka Mesin Inferensi Lokal | `react-native-fast-tflite` | v3.0.1 | Eksekusi inferensi model `.tflite` secara lokal menggunakan C++ JSI tanpa overhead JSON. |
| Basis Data Lokal | `expo-sqlite` | v14.0.x | Sistem manajemen basis data relasional SQLite tersemat untuk penyimpanan riwayat pemindaian offline. |
| Perangkat Lunak Desain UI/UX | Figma Desktop App | v116.15 | Perancangan wireframe antarmuka, aset visual, dan prototipe interaktif UI/UX. |

**Tabel 3.3** Bahan Penelitian

| Kategori Bahan | Nama Bahan / Spesifikasi | Sumber / Asal Usul | Deskripsi Penggunaan |
| --- | --- | --- | --- |
| Basis Data Citra | Dataset Publik Kakao Zaldy Jr (`cacao-diseases`) | Repositori Kaggle | 4.300 citra beresolusi $1080 \times 1080$ piksel terbagi ke dalam kelas *Black Pod Rot*, *Pod Borer*, dan *Healthy*. |
| Bobot Pre-trained Deep Learning | `yolov8s-cls.pt` | Ultralytics Official Repository | Bobot awal pengekstraksi fitur ImageNet untuk proses transfer learning. |
| Pustaka Dependensi | Paket pustaka npm & modul Python | npm registry & PyPI repository | Dependensi pengembangan perangkat lunak frontend seluler dan skrip analitik machine learning. |
| Sampel Uji Lapangan | Foto buah kakao perkebunan fisik | Kamera ponsel Redmi Note 11 (Kondisi riil kebun) | Pengujian fungsionalitas inferensi kamera real-time aplikasi Android di lapangan terbuka. |

**Tabel 3.4** Distribusi Proporsi Partisi Dataset Kakao

| Kelas Kategori Buah Kakao | Data Latih (*Training*) [80%] | Data Validasi (*Validation*) [10%] | Data Uji (*Testing*) [10%] | Total Citra per Kelas |
| --- | --- | --- | --- | --- |
| **Black Pod Rot** (Busuk Buah Hitam) | 1.144 | 143 | 143 | 1.430 |
| **Pod Borer** (Penggerek Buah Kakao) | 1.120 | 140 | 140 | 1.400 |
| **Healthy** (Buah Sehat / Normal) | 1.176 | 147 | 147 | 1.470 |
| **TOTAL KESELURUHAN** | **3.440 citra** | **430 citra** | **430 citra** | **4.300 citra** |

---

### 3.3 Tahapan Penelitian (Waterfall SDLC)

Pelaksanaan penelitian ini mengadopsi model sekuensial linier *Waterfall* yang membagi tahapan riset ke dalam lima fase terstruktur: Analisis Kebutuhan, Perancangan Sistem & Pemodelan AI, Implementasi & Pelatihan Model, Pengujian Sistem & Evaluasi Model, serta Dokumentasi & Penyusunan Laporan (Supriyadi & Widiastuti, 2023; Susila & Arsa, 2023). Diagram alir tahapan penelitian disajikan pada Gambar 3.1.

```
┌────────────────────────────────────────────────────────────────────────┐
│                      1. ANALISIS KEBUTUHAN SISTEM                      │
│ - Studi literatur 17 jurnal ilmiah & observasi tantangan perkebunan     │
│ - Akuisisi dataset Kaggle Zaldy Jr (4.300 citra buah kakao)            │
│ - Penetapan spesifikasi fungsional, non-fungsional, & arsitektur edge  │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │
                                    ▼
┌────────────────────────────────────────────────────────────────────────┐
│                   2. PERANCANGAN SISTEM & DESAIN AI                    │
│ - Pra-pemrosesan citra (Resizing 224x224, Normalisasi, Augmentasi Data) │
│ - Partisi dataset: 80% Train, 10% Validasi, 10% Test (Random Shuffle)   │
│ - Perancangan antarmuka UI/UX di Figma (Pendekatan Mobile-First)       │
│ - Pemodelan UML: Use Case, Activity, Sequence, & Class Diagram         │
│ - Perancangan skema tabel basis data lokal SQLite                      │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │
                                    ▼
┌────────────────────────────────────────────────────────────────────────┐
│              3. IMPLEMENTASI KODE & PELATIHAN MODEL DEEP LEARNING      │
│ - Pelatihan `yolov8s-cls` (50 Epoch, Batch 32, ImageNet Weights)       │
│ - Konversi & Kuantisasi model PyTorch (.pt) ke TensorFlow Lite (.tflite)│
│ - Pengkodean aplikasi Android React Native Expo SDK 54 + TypeScript    │
│ - Integrasi kamera Vision Camera v5.2.2 & inferensi C++ Fast-TFLite    │
│ - Pembangunan manajemen state & penyimpanan riwayat lokal expo-sqlite  │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │
                                    ▼
┌────────────────────────────────────────────────────────────────────────┐
│                 4. PENGUJIAN SISTEM & EVALUASI KINERJA                 │
│ - Evaluasi model deep learning pada 430 citra data uji independen:     │
│   Accuracy, Precision, Recall, F1-Score, & Confusion Matrix 3-Kelas    │
│ - Pengukuran performa inferensi on-device: Latensi (ms) & konsumsi RAM │
│ - Pengujian fungsionalitas aplikasi gawai via Black-Box Testing        │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │
                                    ▼
┌────────────────────────────────────────────────────────────────────────┐
│                5. DOKUMENTASI, PEMBAHASAN, & KESIMPULAN                │
│ - Analisis komparasi performa model terhadap penelitian terdahulu      │
│ - Dokumentasi teknis kode sumber aplikasi dan berkas biner APK         │
│ - Penyusunan laporan skripsi dan penarikan kesimpulan akhir            │
└────────────────────────────────────────────────────────────────────────┘

```

**Gambar 3.1** Diagram Alur Tahapan Penelitian Berbasis Waterfall SDLC

#### 3.3.1 Perancangan UML Sistem Mobile

Pemodelan sistem berorientasi objek digambarkan melalui diagram-diagram Unified Modeling Language (UML) untuk memvisualisasikan arsitektur dan alur interaksi aplikasi (Supriyadi & Widiastuti, 2023; Susila & Arsa, 2023).

##### A. Use Case Diagram

Use Case Diagram mendeskripsikan fungsionalitas utama yang dapat diakses oleh pengguna (petani) pada sistem aplikasi mobile deteksi penyakit buah kakao, sebagaimana disajikan pada Gambar 3.2.

```
                     SISTEM APLIKASI MOBILE DETEKSI KAKAO
       ┌──────────────────────────────────────────────────────────────┐
       │                                                              │
       │   ┌──────────────────────────┐                               │
       │   │       Membuka Aplikasi    │                               │
       │   └─────────────┬────────────┘                               │
       │                 │ <<include>>                                │
       │                 ▼                                            │
       │   ┌──────────────────────────┐                               │
       │   │    Melihat Dashboard     │                               │
       │   └─────────────┬────────────┘                               │
       │                 │                                            │
       │   ┌─────────────┴────────────┐                               │
       │   │                          │                               │
       │   ▼                          ▼                               │
       │ ┌────────────────────────┐ ┌──────────────────────────────┐  │
       │ │  Memindai Buah via     │ │  Memilih Citra dari Galeri   │  │
       │ │  Kamera Waktu-Nyata    │ │                              │  │
       │ └───────────┬────────────┘ └──────────────┬───────────────┘  │
       │             │                             │                  │
       │             └──────────────┬──────────────┘                  │
Petani │                            │ <<include>>                     │
 (User)│                            ▼                                 │
   o   │             ┌─────────────────────────────┐                  │
  /│\──┼────────────>│  Menjalankan Inferensi AI   │                  │
  / \  │             │  Luring (Edge Fast-TFLite)  │                  │
       │             └──────────────┬──────────────┘                  │
       │                            │ <<include>>                     │
       │                            ▼                                 │
       │             ┌─────────────────────────────┐                  │
       │             │  Melihat Hasil Diagnosis &  │                  │
       │             │  Rekomendasi Penanganan     │                  │
       │             └──────────────┬──────────────┘                  │
       │                            │ <<include>>                     │
       │                            ▼                                 │
       │             ┌─────────────────────────────┐                  │
       │             │ Menyimpan Riwayat Pemindaian│                  │
       │             │ ke Basis Data Lokal SQLite  │                  │
       │             └─────────────────────────────┘                  │
       │                            ▲                                 │
       │                            │ <<extend>>                      │
       │             ┌──────────────┴──────────────┐                  │
       │             │  Melihat & Menghapus        │                  │
       │             │  Daftar Riwayat Diagnosis   │                  │
       │             └─────────────────────────────┘                  │
       │                                                              │
       └──────────────────────────────────────────────────────────────┘

```

**Gambar 3.2** Use Case Diagram Sistem Aplikasi Mobile Deteksi Penyakit Kakao

##### B. Activity Diagram

Alur kerja aktivitas sistem dimodelkan ke dalam Activity Diagram yang mencakup proses inisialisasi aplikasi, alur pemindaian citra kamera real-time, dan manajemen riwayat pemindaian lokal (Supriyadi & Widiastuti, 2023).

```
   PENGGUNA (PETANI)                          SISTEM APLIKASI ANDROID
         │                                               │
         ▼                                               │
    [ Mulai ]                                            │
         │                                               │
   Buka Aplikasi ───────────────────────────────────────>│
                                                         ▼
                                                Inisialisasi Runtime,
                                                Muat Model .tflite ke RAM
                                                         │
                                                         ▼
                                                Tampilkan Layar Dashboard
                                                         │
         ┌───────────────────────────────────────────────┘
         ▼
   Pilih Menu Pemindai Kamera
         │
         ▼
   Arahkan Kamera ke Buah Kakao ────────────────────────>│
                                                         ▼
                                                Aktifkan Vision Camera Stream
                                                         │
                                                         ▼
                                                Tangkap Frame (224x224x3)
                                                         │
                                                         ▼
                                                Eksekusi Inferensi Fast-TFLite
                                                (Edge C++ JSI)
                                                         │
                                                         ▼
                                                Hitung Probabilitas Softmax:
                                                - Black Pod Rot
                                                - Pod Borer
                                                - Healthy
                                                         │
                                                         ▼
                                                Apakah Ambang Keyakinan >= 70%?
                                                ├── [ Tidak ] ──> Pertahankan Stream
                                                └── [ Ya ]
                                                         │
                                                         ▼
                                                Tampilkan Label Diagnosis,
                                                Persentase, & Rekomendasi
                                                         │
                                                         ▼
                                                Simpan Catatan Diagnosis
                                                ke Basis Data SQLite Lokal
                                                         │
                                                         ▼
                                                Tampilkan Opsi Simpan/Kembali
                                                         │
         ┌───────────────────────────────────────────────┘
         ▼
   Lihat Hasil & Rekomendasi Tindakan
         │
         ▼
    [ Selesai ]

```

**Gambar 3.3** Activity Diagram Proses Pemindaian Citra dan Inferensi AI Lokal

##### C. Sequence Diagram

Sequence Diagram mendeskripsikan kronologi pertukaran pesan dinamis antarkomponen perangkat lunak saat proses inferensi on-device berlangsung (Supriyadi & Widiastuti, 2023; Susila & Arsa, 2023), sebagaimana disajikan pada Gambar 3.4.

```
Petani           UI Screen         Camera Controller    Fast-TFLite Engine      SQLite DB
  │                  │                     │                     │                  │
  │─── Buka Kamera ─>│                     │                     │                  │
  │                  │── Inisialisasi() ──>│                     │                  │
  │                  │                     │── Start Stream() ──>│                  │
  │                  │                     │                     │                  │
  │── Arahkan Lensa ─│                     │                     │                  │
  │                  │                     │── OnFrame(buffer) ─>│                  │
  │                  │                     │                     │                  │
  │                  │                     │                     │── Preprocess() ──│
  │                  │                     │                     │   (Resize/Norm)  │
  │                  │                     │                     │                  │
  │                  │                     │                     │── RunModel() ────│
  │                  │                     │                     │   (C++ JSI Exec) │
  │                  │                     │                     │                  │
  │                  │                     │<─ Return Prediksi ──│                  │
  │                  │                     │   [Class, Prob]     │                  │
  │                  │                     │                     │                  │
  │                  │<─ Update Frame() ───│                     │                  │
  │                  │                     │                     │                  │
  │                  │── Render Hasil() ───│─────────────────────│                  │
  │<─ Tampil Hasil ──│   (Label & Skor %)  │                     │                  │
  │                  │                     │                     │                  │
  │                  │── AutoSaveRecord() ─│─────────────────────│─────────────────>│
  │                  │                     │                     │                  │── INSERT INTO
  │                  │                     │                     │                  │   scans (...)
  │                  │<─ Confirm Saved ────│─────────────────────│──────────────────│
  │                  │                     │                     │                  │

```

**Gambar 3.4** Sequence Diagram Alur Inferensi Lokal dan Penyimpanan Riwayat

##### D. Class Diagram

Class Diagram merepresentasikan struktur relasi statis kelas logika aplikasi, antarmuka pengeksekusi model, dan skema tabel basis data relasional SQLite lokal (Supriyadi & Widiastuti, 2023), sebagaimana digambarkan pada Gambar 3.5.

```
┌──────────────────────────────────────┐          ┌──────────────────────────────────────┐
│           CameraScannerView          │          │           TFLiteClassifier           │
├──────────────────────────────────────┤          ├──────────────────────────────────────┤
│ - isActive: boolean                  │          │ - modelPath: string                  │
│ - cameraPermission: boolean          │          │ - isModelLoaded: boolean             │
│ - currentFrame: FrameBuffer          │          │ - inputTensorShape: number[]         │
├──────────────────────────────────────┤          ├──────────────────────────────────────┤
│ + requestPermission(): Promise<bool> │1       1 │ + loadModel(): Promise<void>         │
│ + onFrameCaptured(frame): void       ├─────────>│ + preprocess(frame): Float32Array    │
│ + renderOverlayUI(): JSX.Element     │          │ + runInference(data): InferenceResult│
└──────────────────────────────────────┘          └──────────────────────────────────────┘
                   │                                                 │
                   │ 1                                               │ 1
                   ▼                                                 ▼
┌──────────────────────────────────────┐          ┌──────────────────────────────────────┐
│           ScanHistoryManager         │          │            InferenceResult           │
├──────────────────────────────────────┤          ├──────────────────────────────────────┤
│ - dbInstance: SQLiteDatabase         │          │ + predictedClass: string             │
├──────────────────────────────────────┤          │ + confidenceScore: number            │
│ + insertScan(record: ScanRecord): int│          │ + inferenceTimeMs: number            │
│ + getAllScans(): ScanRecord[]        │          │ + rawProbabilities: number[]         │
│ + deleteScanById(id: number): boolean│          └──────────────────────────────────────┘
└──────────────────┬───────────────────┘
                   │
                   │ 1..*
                   ▼
┌─────────────────────────────────────────────────────────────────┐
│                           ScanRecord                            │
├─────────────────────────────────────────────────────────────────┤
│ + id: integer [PRIMARY KEY, AUTOINCREMENT]                      │
│ + imageUri: text                                                │
│ + diseaseLabel: text ('Black Pod Rot' | 'Pod Borer' | 'Healthy')│
│ + confidence: real                                              │
│ + inferenceTime: real                                           │
│ + timestamp: text [DATETIME]                                    │
│ + treatmentRecommendation: text                                 │
└─────────────────────────────────────────────────────────────────┘

```

**Gambar 3.5** Class Diagram Struktur Logika Aplikasi Mobile dan Basis Data SQLite

#### 3.3.2 Rencana Pengujian Black-Box Testing

Pengujian fungsionalitas antarmuka perangkat lunak dilakukan secara komprehensif menggunakan metode *Black-Box Testing* guna memverifikasi bahwa seluruh modul operasi input-output aplikasi berjalan selaras dengan spesifikasi fungsional yang dirancang tanpa kegagalan sistem (*bug-free*) (Supriyadi & Widiastuti, 2023; Susila & Arsa, 2023). Matriks rancangan pengujian black-box dirinci pada Tabel 3.5.

**Tabel 3.5** Rencana Kasus Uji Fungsional Aplikasi (*Black-Box Testing*)

| ID Kasus Uji | Modul / Fitur yang Diuji | Skenario Pengujian | Masukan (*Input*) | Hasil yang Diharapkan (*Expected Output*) | Kriteria Evaluasi |
| --- | --- | --- | --- | --- | --- |
| TC-01 | Inisialisasi Aplikasi | Membuka aplikasi pertama kali pasca-instalasi | Sentuh ikon aplikasi pada layar gawai | Aplikasi terbuka, menampilkan splash screen, inisialisasi basis data SQLite lokal sukses, dan beralih ke layar beranda (*Dashboard*). | Berhasil / Gagal |
| TC-02 | Manajemen Izin Perangkat | Menampilkan dialog permintaan izin kamera | Klik tombol "Izinkan Akses Kamera" | Sistem Android menampilkan dialog *permission*, aplikasi memperoleh izin dan membuka modul kamera tanpa *crash*. | Berhasil / Gagal |
| TC-03 | Pemindai Kamera Real-time | Mengaktifkan aliran kamera pemindai gawai | Arahkan kamera fisik ponsel ke arah buah kakao | Tampilan preview kamera aktif dengan rasio aspek mulus (*smooth frame rate* $\ge 30\text{ fps}$) dan *bounding overlay guide* muncul. | Berhasil / Gagal |
| TC-04 | Inferensi Edge AI Lokal | Menjalankan inferensi model `yolov8s-cls` (.tflite) | Pindai citra buah kakao bergejala Busuk Buah Hitam | Mesin `react-native-fast-tflite` memproses citra via JSI, menghasilkan label kelas "Black Pod Rot" dan skor keyakinan dalam waktu $< 10\text{ ms}$. | Berhasil / Gagal |
| TC-05 | Pemilihan Citra via Galeri | Mengunggah foto buah kakao dari galeri internal | Pilih salah satu citra buah kakao dari penyimpanan gawai | Citra terpilih termuat ke dalam memori aplikasi, pra-pemrosesan berjalan, dan hasil klasifikasi tertampil secara akurat. | Berhasil / Gagal |
| TC-06 | Penyimpanan Riwayat Pemindaian | Menyimpan otomatis catatan diagnosis ke SQLite | Selesaikan satu siklus pemindaian citra buah | Record baru berisi path citra, label diagnosis, nilai probabilitas, dan waktu pemindaian tersimpan secara persisten ke tabel SQLite lokal. | Berhasil / Gagal |
| TC-07 | Tampilan Daftar Riwayat | Membuka halaman riwayat pemindaian | Navigasi menu ke tab "Riwayat Diagnosis" | Aplikasi menampilkan seluruh daftar histori pemeriksaan sebelumnya secara terurut kronologis terbalik (*descending*). | Berhasil / Gagal |
| TC-08 | Hapus Riwayat Pemindaian | Menghapus catatan riwayat pemindaian tertentu | Klik tombol ikon sampah (*Delete*) pada salah satu riwayat | Kotak dialog konfirmasi muncul; saat dikonfirmasi, entri data pada basis data SQLite terhapus dan daftar riwayat ter-update seketika. | Berhasil / Gagal |
| TC-09 | Ketahanan Mode Luring (*Offline*) | Menjalankan seluruh fungsi aplikasi tanpa internet | Aktifkan Mode Pesawat (*Airplane Mode* - Wi-Fi & Seluler Nonaktif) | Seluruh fungsi pemindaian kamera, eksekusi model deep learning, dan penyimpanan SQLite tetap berjalan normal 100% tanpa kendala galat koneksi. | Berhasil / Gagal |

---

### 3.4 Jadwal Penelitian

Pelaksanaan penelitian skripsi ini direncanakan berlangsung selama enam bulan secara terstruktur, mencakup seluruh rangkaian fase siklus hidup Waterfall sebagaimana dirinci pada matriks Tabel 3.6.

**Tabel 3.6** Matriks Jadwal Pelaksanaan Penelitian Skripsi (6 Bulan)

| No | Tahapan dan Aktivitas Penelitian | Bulan ke-1 | Bulan ke-2 | Bulan ke-3 | Bulan ke-4 | Bulan ke-5 | Bulan ke-6 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | **Studi Literatur & Observasi Lapangan:** Pengumpulan referensi 17 jurnal ilmiah bereputasi dan observasi kebutuhan petani kakao | [ X ] | [   ] | [   ] | [   ] | [   ] | [   ] |
| 2 | **Kurasi & Pra-pemrosesan Dataset:** Pengunduhan dataset Kaggle Zaldy Jr, seleksi citra, resizing $224 \times 224$, augmentasi, dan partisi data (80:10:10) | [   ] | [ X ] | [   ] | [   ] | [   ] | [   ] |
| 3 | **Pelatihan & Evaluasi Model Deep Learning:** Pelatihan transfer learning `yolov8s-cls` di Google Colab GPU, evaluasi metrik kinerja, dan matriks konfusi | [   ] | [ X ] | [ X ] | [   ] | [   ] | [   ] |
| 4 | **Kuantisasi & Optimasi Edge Model:** Konversi bobot PyTorch (`.pt`) ke format TensorFlow Lite (`.tflite`) dan validasi akurasi numerik | [   ] | [   ] | [ X ] | [   ] | [   ] | [   ] |
| 5 | **Perancangan Sistem & Desain UI/UX:** Pembuatan prototipe antarmuka Figma, perancangan skema UML, dan struktur basis data relasional SQLite | [   ] | [   ] | [ X ] | [   ] | [   ] | [   ] |
| 6 | **Implementasi Aplikasi Mobile:** Pengkodean React Native Expo SDK 54, integrasi Vision Camera, pustaka Fast-TFLite via C++ JSI, dan SQLite lokal | [   ] | [   ] | [   ] | [ X ] | [ X ] | [   ] |
| 7 | **Pengujian Sistem & Analisis Kinerja:** Pengujian fungsionalitas Black-Box Testing pada smartphone fisik dan evaluasi latensi inferensi on-device | [   ] | [   ] | [   ] | [   ] | [ X ] | [   ] |
| 8 | **Penyusunan Dokumentasi & Laporan Skripsi:** Penulisan naskah komprehensif, penyusunan artikel ilmiah, dan persiapan sidang sarjana | [   ] | [   ] | [   ] | [   ] | [   ] | [ X ] |

---

## DAFTAR PUSTAKA

Alvarado, J., Restrepo-Arias, J. F., Velásquez, D., & Maiza, M. (2025). Disease detection on cocoa crops based on computer-vision techniques: A systematic literature review. *Agriculture*, 15(10), 1032. [https://doi.org/10.3390/agriculture15101032](https://doi.org/10.3390/agriculture15101032)

Ariawan, K. R., Ekayana, A. A. G., Indrawan, I. P. Y., Winatha, K. R., & Setiawan, I. N. A. F. (2025). Performance comparison of DenseNet-121 and MobileNetV2 for cacao fruit disease image classification. *Indonesian Journal of Data and Science*, 6(1), 29–38. [https://doi.org/10.56705/ijodas.v6i1.233](https://doi.org/10.56705/ijodas.v6i1.233)

Badan Pusat Statistik. (2023). *Statistik kakao Indonesia 2023*. Badan Pusat Statistik Republik Indonesia. Jakarta: BPS RI.

Ferraris, S., Meo, R., Pinardi, S., Salis, M., & Sartor, G. (2023). Machine learning as a strategic tool for helping cocoa farmers in Côte d'Ivoire. *Sensors*, 23(17), 7632. [https://doi.org/10.3390/s23177632](https://www.google.com/search?q=https://doi.org/10.3390/s23177632)

Fuentes, A., Yoon, S., Kim, S. C., & Park, D. S. (2017). A robust deep-learning-based detector for real-time tomato plant diseases and pests recognition. *Sensors*, 17(9), 2022. [https://doi.org/10.3390/s17092022](https://www.google.com/search?q=https://doi.org/10.3390/s17092022)

Gado, G. A. S., & Primandari, P. N. (2025). Sistem klasifikasi berbasis Android untuk penyakit buah kakao menggunakan CNN NasNet-Mobile. *Jurnal Teknologi Terpadu*, 11(1), 27–35. [https://doi.org/10.54460/jtt.v11i1.1821](https://www.google.com/search?q=https://doi.org/10.54460/jtt.v11i1.1821)

Ghafar, A., Chen, C., Atif Ali Shah, S., Ur Rehman, Z., & Rahman, G. (2024). Visualizing plant disease distribution and evaluating model performance for deep learning classification with YOLOv8. *Pathogens*, 13(12), 1032. [https://doi.org/10.3390/pathogens13121032](https://doi.org/10.3390/pathogens13121032)

Khan, F., Zafar, N., Tahir, M. N., Aqib, M., Waheed, H., & Haroon, Z. (2023). A mobile-based system for maize plant leaf disease detection and classification using deep learning. *Frontiers in Plant Science*, 14, 1079366. [https://doi.org/10.3389/fpls.2023.1079366](https://www.google.com/search?q=https://doi.org/10.3389/fpls.2023.1079366)

Maylianti, N. P., Wijayakusuma, I. G. N. L., & Wiguna, I. P. C. A. (2025). Comparison of EfficientNet-B0 and ResNet-50 for detecting diseases in cocoa fruit. *Journal of Applied Informatics and Computing (JAIC)*, 9(1), 115–120. [https://doi.org/10.30871/jaic.v9i1.7925](https://www.google.com/search?q=https://doi.org/10.30871/jaic.v9i1.7925)

Mohanty, S. P., Hughes, D. P., & Salathé, M. (2016). Using deep learning for image-based plant disease detection. *Frontiers in Plant Science*, 7, 1419. [https://doi.org/10.3389/fpls.2016.01419](https://doi.org/10.3389/fpls.2016.01419)

Natbais, Y. H., & Umbu, A. B. S. (2023). Aplikasi deteksi penyakit pada daun tomat berbasis Android menggunakan model terlatih Tensorflow Lite. *Teknotan*, 17(2), 83–90. [https://doi.org/10.24198/jt.vol17n2.1](https://www.google.com/search?q=https://doi.org/10.24198/jt.vol17n2.1)

Novanto, A., Kurniawan, Y. I., & Iskandar, D. (2025). Enhanced speed and accuracy in cocoa fruit disease identification using the Inception-ResNet Convolutional Neural Network (CNN) algorithm. *Jurnal Teknik Informatika (JUTIF)*, 6(1), 369–386. [https://doi.org/10.52436/1.jutif.2025.6.1.4144](https://doi.org/10.52436/1.jutif.2025.6.1.4144)

Octavian, O., Badruzzaman, A., Ridho, M. Y., & Trisedya, B. D. (2024). Enhancing weighted averaging for CNN model ensemble in plant diseases image classification. *Jurnal RESTI (Rekayasa Sistem dan Teknologi Informasi)*, 8(2), 272–279. [https://doi.org/10.29207/resti.v8i2.5669](https://doi.org/10.29207/resti.v8i2.5669)

Ramcharan, A., Baranowski, K., McCloskey, P., Ahmed, B., Legg, J., & Hughes, D. P. (2017). Deep learning for image-based cassava disease detection. *Frontiers in Plant Science*, 8, 1852. [https://doi.org/10.3389/fpls.2017.01852](https://www.google.com/search?q=https://doi.org/10.3389/fpls.2017.01852)

Siahaan, R. D., Herimanto, Simbolon, I. N., Simbolon, I., & Gultom, D. J. (2024). Enhancing real-time herbal plant detection in agricultural environments with YOLOv8. *Journal of Information Systems and Informatics*, 6(4), 2491–2506. [https://doi.org/10.51519/journalisi.v6i4.889](https://doi.org/10.51519/journalisi.v6i4.889)

Supriyadi, B., & Widiastuti, R. (2023). Rancang program aplikasi pembelajaran tajwid berbasis Android. *JATISI (Jurnal Teknik Informatika dan Sistem Informasi)*, 10(2), 766–777. [https://doi.org/10.35957/jatisi.v10i2.4842](https://www.google.com/search?q=https://doi.org/10.35957/jatisi.v10i2.4842)

Susila, A. A. N. H., & Arsa, D. M. S. (2023). Analisis System Usability Scale (SUS) dan perancangan sistem self service pemesanan menu di restoran berbasis web. *Majalah Ilmiah UNIKOM*, 21(1), 3–8. [https://doi.org/10.34010/miu.v21i1.9876](https://www.google.com/search?q=https://doi.org/10.34010/miu.v21i1.9876)

Terven, J., Córdova-Esparza, D., & Romero-González, J. A. (2023). A comprehensive review of YOLO: From YOLOv1 to YOLOv8 and beyond. *Machine Learning and Knowledge Extraction*, 5(4), 1680–1716. [https://doi.org/10.3390/make5040083](https://doi.org/10.3390/make5040083)

---

## TABEL VERIFIKASI KUOTA SITASI

Tabel verifikasi berikut membuktikan kepatuhan mutlak (*100% compliance*) terhadap pemenuhan sitasi artikel ilmiah yang berada dalam repositori penelitian, termasuk rincian judul publikasi asli serta letak subbab pemanggilannya di dalam naskah proposal.

**Tabel 3.7** Verifikasi Pemenuhan Sitasi Seluruh Artikel Jurnal Ilmiah

| No | Nama Penulis & Tahun | Judul Paper Asli | Subbab Tempat Jurnal Ini Disitasi dalam Naskah |
| --- | --- | --- | --- |
| 1 | Alvarado, J., Restrepo-Arias, J. F., Velásquez, D., & Maiza, M. (2025) | *Disease Detection on Cocoa Crops Based on Computer-Vision Techniques: A Systematic Literature Review* | Bab 1.1, Bab 2.1 (Tabel 2.1 & Sintesis), Subbab 2.2.1, Subbab 2.2.2, Subbab 2.2.4, Subbab 2.2.5, Subbab 3.1.2 |
| 2 | Ariawan, K. R., Ekayana, A. A. G., Indrawan, I. P. Y., Winatha, K. R., & Setiawan, I. N. A. F. (2025) | *Performance Comparison of DenseNet-121 and MobileNetV2 for Cacao Fruit Disease Image Classification* | Bab 1.1, Bab 2.1 (Tabel 2.1 & Sintesis), Subbab 2.2.3, Subbab 2.2.4, Subbab 2.2.6, Subbab 2.2.10, Subbab 3.1.2 |
| 3 | Ferraris, S., Meo, R., Pinardi, S., Salis, M., & Sartor, G. (2023) | *Machine Learning as a Strategic Tool for Helping Cocoa Farmers in Côte D'Ivoire* | Bab 1.1, Bab 2.1 (Tabel 2.1 & Sintesis), Subbab 2.2.4, Subbab 3.1.2 |
| 4 | Fuentes, A., Yoon, S., Kim, S. C., & Park, D. S. (2017) | *A Robust Deep-Learning-Based Detector for Real-Time Tomato Plant Diseases and Pests Recognition* | Bab 2.1 (Tabel 2.1 & Sintesis), Subbab 2.2.5, Subbab 2.2.8, Subbab 3.1.2 |
| 5 | Gado, G. A. S., & Primandari, P. N. (2025) | *Sistem Klasifikasi Berbasis Android untuk Penyakit Buah Kakao Menggunakan CNN NasNet-Mobile* | Bab 1.1, Bab 2.1 (Tabel 2.1 & Sintesis), Subbab 2.2.1, Subbab 2.2.4, Subbab 2.2.9, Subbab 3.1.2 |
| 6 | Ghafar, A., Chen, C., Atif Ali Shah, S., Ur Rehman, Z., & Rahman, G. (2024) | *Visualizing Plant Disease Distribution and Evaluating Model Performance for Deep Learning Classification with YOLOv8* | Bab 1.1, Bab 2.1 (Tabel 2.1), Subbab 2.2.11, Subbab 3.1.2 |
| 7 | Khan, F., Zafar, N., Tahir, M. N., Aqib, M., Waheed, H., & Haroon, Z. (2023) | *A Mobile-Based System for Maize Plant Leaf Disease Detection and Classification Using Deep Learning* | Bab 1.1, Bab 2.1 (Tabel 2.1 & Sintesis), Subbab 2.2.6, Subbab 2.2.11, Subbab 2.2.17, Subbab 3.1.2 |
| 8 | Maylianti, N. P., Wijayakusuma, I. G. N. L., & Wiguna, I. P. C. A. (2025) | *Comparison of EfficientNet-B0 and ResNet-50 for Detecting Diseases in Cocoa Fruit* | Bab 1.1, Bab 2.1 (Tabel 2.1), Subbab 2.2.4, Subbab 2.2.9, Subbab 2.2.10, Subbab 2.2.14, Subbab 2.2.15, Subbab 3.1.2 |
| 9 | Mohanty, S. P., Hughes, D. P., & Salathé, M. (2016) | *Using Deep Learning for Image-Based Plant Disease Detection* | Bab 1.1, Bab 2.1 (Tabel 2.1 & Sintesis), Subbab 2.2.5, Subbab 2.2.8, Subbab 2.2.9, Subbab 3.1.2 |
| 10 | Natbais, Y. H., & Umbu, A. B. S. (2023) | *Aplikasi Deteksi Penyakit pada Daun Tomat Berbasis Android Menggunakan Model Terlatih Tensorflow Lite* | Bab 2.1 (Tabel 2.1), Subbab 2.2.12, Subbab 2.2.13, Subbab 2.2.17, Subbab 2.2.19, Subbab 3.1.2 |
| 11 | Novanto, A., Kurniawan, Y. I., & Iskandar, D. (2025) | *Enhanced Speed and Accuracy in Cocoa Fruit Disease Identification Using the Inception-ResNet Convolutional Neural Network (CNN) Algorithm* | Bab 1.1, Bab 2.1 (Tabel 2.1 & Sintesis), Subbab 2.2.3, Subbab 2.2.5, Subbab 2.2.14, Subbab 2.2.15, Subbab 3.1.2 |
| 12 | Octavian, O., Badruzzaman, A., Ridho, M. Y., & Trisedya, B. D. (2024) | *Enhancing Weighted Averaging for CNN Model Ensemble in Plant Diseases Image Classification* | Bab 2.1 (Tabel 2.1 & Sintesis), Subbab 2.2.6, Subbab 2.2.7, Subbab 2.2.10, Subbab 2.2.15, Subbab 3.1.2 |
| 13 | Ramcharan, A., Baranowski, K., McCloskey, P., Ahmed, B., Legg, J., & Hughes, D. P. (2017) | *Deep Learning for Image-Based Cassava Disease Detection* | Bab 2.1 (Tabel 2.1 & Sintesis), Subbab 2.2.5, Subbab 2.2.8, Subbab 2.2.10, Subbab 3.1.2 |
| 14 | Siahaan, R. D., Herimanto, Simbolon, I. N., Simbolon, I., & Gultom, D. J. (2024) | *Enhancing Real-time Herbal Plant Detection in Agricultural Environments with YOLOv8* | Bab 1.1, Bab 2.1 (Tabel 2.1 & Sintesis), Subbab 2.2.6, Subbab 2.2.11, Subbab 2.2.13, Subbab 2.2.16, Subbab 2.2.17, Subbab 2.2.18, Subbab 2.2.19, Subbab 3.1.2 |
| 15 | Supriyadi, B., & Widiastuti, R. (2023) | *Rancang Program Aplikasi Pembelajaran Tajwid Berbasis Android* | Bab 2.1 (Tabel 2.1 & Sintesis), Subbab 2.2.17, Subbab 2.2.19, Subbab 2.2.20, Subbab 3.1.2, Subbab 3.3, Subbab 3.3.1, Subbab 3.3.2 |
| 16 | Susila, A. A. N. H., & Arsa, D. M. S. (2023) | *Analisis System Usability Scale (SUS) dan Perancangan Sistem Self Service Pemesanan Menu di Restoran Berbasis Web* | Bab 2.1 (Tabel 2.1), Subbab 2.2.12, Subbab 2.2.18, Subbab 2.2.19, Subbab 2.2.20, Subbab 3.1.2, Subbab 3.3, Subbab 3.3.1, Subbab 3.3.2 |
| 17 | Terven, J., Córdova-Esparza, D., & Romero-González, J. A. (2023) | *A Comprehensive Review of YOLO: From YOLOv1 to YOLOv8 and Beyond* | Bab 1.1, Bab 2.1 (Tabel 2.1 & Sintesis), Subbab 2.2.6, Subbab 2.2.8, Subbab 2.2.9, Subbab 2.2.11, Subbab 2.2.14, Subbab 3.1.2 |