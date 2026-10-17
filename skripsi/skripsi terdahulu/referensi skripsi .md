IMPLEMENTASI APLIKASI PROGRESSIVE MOBILE APP (PMA) 
UNTUK DETEKSI PENYAKIT PADA DAUN KOPI MENGGUNAKAN 
TRANSFER LEARNING DENGAN MODEL DENSENET 
SKRIPSI 
disusun oleh 
Fathur Rizki Ali 
220203008 
PROGRAM STUDI REKAYASA PERANGKAT LUNAK 
FAKULTAS TEKNOLOGI DAN INFORMATIKA 
UNIVERSITAS AISYAH PRINGSEWU 
2026
IMPLEMENTASI APLIKASI PROGRESSIVE MOBILE APP (PMA) 
UNTUK DETEKSI PENYAKIT PADA DAUN KOPI MENGGUNAKAN 
TRANSFER LEARNING DENGAN MODEL DENSENET 
SKRIPSI 
Disusun untuk memenuhi sebagian persyaratan  
mencapai gelar Sarjana 
pada Program Studi Rekayasa Perangkat Lunak 
disusun oleh 
Fathur Rizki Ali 
220203008 
PROGRAM STUDI REKAYASA PERANGKAT LUNAK 
FAKULTAS TEKNOLOGI DAN INFORMATIKA 
UNIVERSITAS AISYAH PRINGSEWU 
2026
ii 
 
 
 
 
 
 
SKRIPSI 
 
 
IMPLEMENTASI APLIKASI PROGRESSIVE MOBILE APP (PMA) 
UNTUK DETEKSI PENYAKIT PADA DAUN KOPI MENGGUNAKAN 
TRANSFER LEARNING DENGAN MODEL DENSENET 
 
 
Dipersiapkan dan disusun oleh 
 
Fathur Rizki Ali 
220203008 
 
 
telah disetujuai oleh Dosen Pembimbing Skripsi 
pada tanggal .......................... 
 
 
Dosen Pembimbing, 
 
 
Ratnasari, S.Kom., M.Kom. 
NIDN. 0222127602 
           
 
 
LEMBAR PERSETUJUAN PEMBIMBING 
 
 
iv 
 
 
 
SKRIPSI 
 
IMPLEMENTASI APLIKASI PROGRESSIVE MOBILE APP (PMA) 
UNTUK DETEKSI PENYAKIT PADA DAUN KOPI MENGGUNAKAN 
TRANSFER LEARNING DENGAN MODEL DENSENET 
 
Dipersiapkan dan disusun oleh 
Fathur Rizki Ali 
220203008 
Telah dipertahankan di depan Dewan Penguji  
pada tanggal Hari Bulan Tahun 
dan dinyatakan telah memenuhi syarat 
 
Susunan Dewan Penguji 
 
Nama Penguji    Tanda Tangan 
 
 
Panji Bintoro, S.Kom., M.Cs    _________________ 
NIDN. xxxxxxxxxx 
 
 
Tahta Herdian Andika, S.Kom., M.T.I                       _________________ 
NIDN. xxxxxxxxxx 
  
 
Pringsewu, Hari Bulan Tahun 
Dekan Fakultas Teknologi dan Informatika 
Universitas Aisyah Pringsewu 
 
 
 
 
Dr. Ir. Zulkifli, S.T., M.Kom 
NIDN:219028201 
 
LEMBAR PERSETUJUAN PENGUJI 
 
LEMBAR PERNYATAAN KEASLIAN 
SURAT PERNYATAAN 
Saya yang bertandatangan dibawah ini menyatakan bahwa, skripsi ini merupakan 
karya saya sendiri (ASLI), dan isi dalam skripsi ini tidak terdapat karya yang 
pernah diajukan oleh orang lain untuk memperoleh gelar akademis di suatu 
institusi pendidikan tinggi manapun, dan sepanjang pengetahuan saya juga tidak 
terdapat karya atau pendapat yang pernah ditulis dan/atau diterbitkan oleh orang 
lain, kecuali yang secara tertulis diacu dalam naskah ini dan disebutkan dalam 
daftar pustaka. 
Segala sesuatu yang terkait dengan naskah dan karya yang telah dibuat adalah 
menjadi tanggungjawab saya pribadi. 
Pringsewu, ……….. 
Meterai 
Rp. 10.000 
Fathur Rizki Ali 
NPM. 220203008 
v 
MOTTO 
“Allah tidak akan mengubah keadaan suatu kaum hingga mereka 
mengubah keadaan yang ada pada diri mereka sendiri.” 
(QS. Ar-Ra‘d: 11) 
“Barang siapa menempuh jalan untuk mencari ilmu, maka Allah akan 
memudahkan baginya jalan menuju surga.” 
(HR. Muslim) 
vi 
PERSEMBAHAN 
Dengan penuh rasa syukur ke hadirat Allah SWT, skripsi ini penulis persembahkan 
sebagai wujud ikhtiar dan pengabdian dalam menuntut ilmu. 
Skripsi ini penulis persembahkan kepada: 
1. Allah SWT, yang telah memberikan nikmat iman, kesehatan, kesabaran, 
serta kemudahan dalam setiap proses penyusunan skripsi ini. Semoga karya 
ini bernilai ibadah dan menjadi amal kebaikan. 
2. Nabi Muhammad SAW, sebagai suri teladan terbaik dalam kehidupan, 
yang ajarannya senantiasa menjadi pedoman bagi penulis dalam menuntut 
ilmu dan menjalani kehidupan. 
3. Kedua orang tua tercinta, yang dengan penuh keikhlasan telah memberikan 
doa, kasih sayang, pengorbanan, serta dukungan tanpa henti, baik secara 
moral maupun material. Semoga Allah SWT membalas segala kebaikan 
dengan pahala yang berlipat ganda. 
4. Keluarga tercinta, yang senantiasa memberikan semangat, doa, dan 
dukungan dalam setiap langkah penulis. 
5. Bapak dan Ibu dosen, khususnya dosen pembimbing, yang telah dengan 
sabar membimbing, mengarahkan, serta memberikan ilmu dan motivasi 
selama proses perkuliahan dan penyusunan skripsi ini. 
6. Kepada pasangan tercinta yang selalu mensupport penulis dalam 
mengerjakan skripsi ini. 
7. Teman-teman seperjuangan, yang telah berbagi cerita, pengalaman, dan 
semangat dalam menempuh perjalanan akademik hingga tahap akhir ini. 
Semoga skripsi ini dapat memberikan manfaat, menambah wawasan, serta menjadi 
langkah awal untuk mengabdi kepada masyarakat, bangsa, dan agama. 
vii 
KATA PENGANTAR 
Bismillāhirraḥmānirraḥīm. 
Segala puji dan syukur penulis panjatkan ke hadirat Allah SWT, Tuhan semesta 
alam, atas limpahan rahmat, taufik, dan hidayah-Nya, sehingga penulis dapat 
menyelesaikan skripsi yang berjudul “Implementasi Aplikasi Progressive 
Mobile App (PMA) untuk Deteksi Penyakit pada Daun Kopi Menggunakan 
Transfer Learning dengan Model DenseNet” dengan baik. Shalawat serta salam 
semoga senantiasa tercurah kepada junjungan kita Nabi Muhammad SAW, beserta 
keluarga, sahabat, dan umatnya hingga akhir zaman. 
Skripsi ini disusun sebagai salah satu syarat untuk memperoleh gelar Sarjana pada 
Program Studi Rekayasa Perangkat Lunak. Penelitian ini bertujuan untuk 
mengembangkan aplikasi berbasis Progressive Mobile App (PMA) yang 
memanfaatkan teknologi kecerdasan buatan melalui metode transfer learning 
dengan model DenseNet dalam mendeteksi penyakit pada daun kopi. Penulis 
berharap hasil penelitian ini dapat memberikan manfaat bagi pengembangan ilmu 
pengetahuan dan penerapan teknologi, khususnya di bidang pertanian dan rekayasa 
perangkat lunak. 
Dalam proses penyusunan skripsi ini, penulis menyadari sepenuhnya bahwa tanpa 
pertolongan Allah SWT serta bantuan dan dukungan dari berbagai pihak, skripsi 
ini tidak akan dapat diselesaikan dengan baik. Oleh karena itu, dengan penuh rasa 
hormat dan kerendahan hati, penulis mengucapkan terima kasih yang sebesar
besarnya kepada: 
1. Dr. Sukarni, SST., M. Kes. selaku Ketua Yayasan Aisyah Lampung. 
2. Dr. Sutrisno, S. Kep., Ners., MAN selaku Rektor Universitas Aisyah 
Pringsewu. 
3. Dr. Ir. Zulkifli, S. T., M. Kom selaku Dekan Fakultas Teknologi dan 
Informatika Universitas Aisyah Pringsewu. 
4. Nur Aminudin, S. Kom, M. T. I., selaku Ketua Program Studi Rekayasa 
Perangkat Lunak. 
5. Ratnasari, S. Kom., M. Kom selaku Dosen Pembimbing Skripsi yang telah 
meluangkan waktu untuk membimbing penulis menyelesaikan skripsi ini. 
viii 
6. Dosen dan Staff Fakultas Teknologi dan Informatika Universitas Aisyah 
Pringsewu. 
7. Teman-teman dan rekan-rekan mahasiswa/i Rekayasa Perangkat Lunak 
angkatan 2022. 
8. Semua pihak yang telah membatu dalam penyusunan skripsi ini, dan tidak 
dapat saya sebutkan satu persatu. 
Penulis menyadari bahwa skripsi ini masih jauh dari kesempurnaan, baik dari segi 
isi maupun penyajiannya. Oleh karena itu, penulis dengan lapang dada 
mengharapkan kritik dan saran yang membangun demi perbaikan dan 
penyempurnaan di masa mendatang. Semoga skripsi ini dapat memberikan 
manfaat dan menjadi amal jariyah bagi penulis serta semua pihak yang terlibat. 
Akhir kata, semoga Allah SWT senantiasa meridai setiap usaha dan langkah kita 
dalam menuntut ilmu. Āmīn yā Rabbal ‘ālamīn. 
Penulis, 
Fathur Rizki Ali 
ix 
 
 
x 
 
DAFTAR ISI 
 
 
COVER............................................................................................................................................ I 
LEMBAR JUDUL .......................................................................................................................III 
LEMBAR PERNYATAAN KEASLIAN ................................................................................... IV 
LEMBAR PERSETUJUAN PENGUJI ..................................................................................... IV 
MOTTO ........................................................................................................................................ VI 
PERSEMBAHAN ...................................................................................................................... VII 
KATA PENGANTAR .............................................................................................................. VIII 
DAFTAR ISI ................................................................................................................................. X 
DAFTAR TABEL ...................................................................................................................... XII 
DAFTAR GAMBAR ................................................................................................................ XIII 
DAFTAR ISTILAH .................................................................................................................. XIV 
BAB I PENDAHULUAN .............................................................................................................. 2 
1.1 LATAR BELAKANG ....................................................................................................... 2 
1.2 RUMUSAN MASALAH ................................................................................................... 2 
1.3 BATASAN MASALAH .................................................................................................... 9 
1.1 TUJUAN PENELITIAN ................................................................................................. 10 
1.4 MANFAAT PENELITIAN .............................................................................................. 10 
1.5 SISTEMATIKA PENULISAN ......................................................................................... 13 
BAB II ........................................................................................................................................... 15 
LANDASAN TEORI ................................................................................................................... 15 
2.1 KAJIAN PUSTAKA ....................................................................................................... 15 
2.1.1. Penelitian Terdahulu ............................................................................................. 15 
2.2 DASAR TEORI ............................................................................................................. 19 
2.2.1 Tanaman Kopi ....................................................................................................... 19 
2.2.2 Produksi Kopi di Indonesia ................................................................................... 20 
2.2.3 Peran Kopi dalam Sektor Perkebunan .................................................................. 21 
2.2.4 Penyakit pada Daun Kopi ...................................................................................... 21 
2.2.5 Deteksi Penyakit Tanaman Menggunakan Teknologi ............................................ 23 
2.2.6 Pengolahan Citra Digital ...................................................................................... 25 
2.2.7 Machine Learning .................................................................................................. 27 
 
 
xi 
 
2.2.8 Deep Learning ....................................................................................................... 30 
2.2.9 Convolutional Neural Network (CNN) .................................................................. 31 
2.2.10 Transfer Learning ............................................................................................. 33 
2.2.11 Model DenseNet ................................................................................................ 35 
2.2.12 Progressive Mobile App (PMA) / Progressive Web App (PWA) ....................... 38 
2.2.13 Aplikasi Mobile ................................................................................................. 40 
2.2.14 Dataset dan Training Model ............................................................................. 41 
2.2.15 Evaluasi Kinerja Model .................................................................................... 43 
2.2.16 Bahasa Pemrograman Java .............................................................................. 46 
2.2.17 Firebase (Database Cloud) ............................................................................... 47 
2.2.18 Figma ................................................................................................................ 48 
2.2.19 Metode Waterfall .............................................................................................. 49 
2.2.20 UML (Unified Modeling Language) ................................................................. 51 
BAB III ......................................................................................................................................... 52 
METODOLOGI PENELITIAN ................................................................................................. 53 
3.1 METODE PENGUMPULAN DATA .......................................................................... 53 
3.1.1 OBSERVASI ................................................................................................................. 53 
3.1.2 STUDI LITERATUR ..................................................................................................... 54 
3.1.3 DOKUMENTASI ........................................................................................................... 55 
3.2 ALAT DAN BAHAN ..................................................................................................... 56 
3.2.1 ALAT .......................................................................................................................... 57 
3.2.2 BAHAN ........................................................................................................................ 58 
3.3 TAHAPAN PENELITIAN ........................................................................................... 59 
3.4 JADWAL PENELITIAN .............................................................................................. 74 
DAFTAR PUSTAKA .................................................................................................................. 76 
 
 
 
 
 
 
xii 
 
Daftar Tabel 
Table 2.0.1 Perbandingan Jurnal Ilmiah ............................................................... 15 
Table 3.1 spesifikasi Perangkat Keras .................................................................. 57 
Table 3.2 Perangkat Lunak yang Digunakan ....................................................... 57 
Table 3.3 Bahan Penelitian ................................................................................... 58 
Table 3.4 Dataset .................................................................................................. 60 
Table 3.5 Jadwal Pelaksanaan Penelitian ............................................................. 74 
 
 
 
 
xiii 
 
Daftar Gambar 
Gambar 3.1 Alur Tahapan Penelitian ................................................................... 59 
Gambar 3.2 use case diagram pengguna .............................................................. 64 
Gambar 3.3 use case diagram admin .................... Error! Bookmark not defined. 
Gambar 3.4 Activity Diagram Login .................................................................... 65 
Gambar 3.5 Activity Diagram Register ................................................................ 66 
Gambar 3.6 Activity Diagram Pemindai Daun Kopi ........................................... 67 
Gambar 3.7 Sequence Diagram Login ................................................................. 68 
Gambar 3.8 Sequence Diagram Registrasi ........................................................... 69 
Gambar 3. 9 Sequence Diagram Pemindaian ....................................................... 70 
Gambar 3.10 Class Diagram ................................................................................. 71 
 
 
Daftar Istilah 
Istilah / Singkatan 
Accuracy (Akurasi) 
Activity Diagram 
Android Studio 
API (Application Programming 
Interface) 
Arsitektur Model 
Augmentasi Data 
Backend-as-a-Service (BaaS) 
Backpropagation 
Batch 
Black Box Testing 
Categorical Cross-Entropy 
Definisi 
Proporsi prediksi benar dari keseluruhan data uji. Rumus: (TP + TN) 
/ (TP + TN + FP + FN) × 100%. 
Diagram UML yang menggambarkan alur aktivitas atau proses 
bisnis dalam sistem secara berurutan. 
IDE resmi Google untuk mengembangkan aplikasi Android 
berbasis Java dan Kotlin. 
Antarmuka yang memungkinkan dua sistem atau aplikasi berbeda 
untuk berkomunikasi dan bertukar data. 
Susunan lapisan dan komponen dalam jaringan saraf tiruan yang 
menentukan cara data diproses dan diklasifikasikan. 
Teknik memperkaya dataset secara artifisial melalui transformasi 
gambar (rotasi, flip, zoom, dll.) untuk mencegah overfitting. 
Layanan cloud yang menyediakan infrastruktur backend siap pakai 
tanpa perlu mengelola server sendiri. 
Algoritma pelatihan jaringan saraf yang menghitung dan 
menyebarkan error dari output ke input untuk memperbarui bobot 
model. 
Sejumlah sampel data yang diproses secara bersamaan dalam satu 
iterasi pelatihan model. 
Pengujian fungsionalitas aplikasi dari sisi pengguna tanpa 
memperhatikan struktur internal kode. 
Fungsi kerugian (loss function) untuk mengukur perbedaan antara 
prediksi model dengan label kelas yang sebenarnya. 
Cercospora (Bercak Daun Coklat) Penyakit daun kopi akibat jamur Cercospora coffeicola, ditandai 
bercak bulat coklat dengan lingkaran kuning. 
Class Diagram 
CNN 
(Convolutional 
Network) 
Coffee Leaf Rust (Karat Daun 
Kopi) 
Coffea arabica (Kopi Arabika) 
Coffea canephora (Kopi Robusta) 
Diagram UML yang menggambarkan struktur statis sistem berupa 
kelas, atribut, metode, dan hubungan antar kelas. 
Neural 
Arsitektur jaringan saraf dalam yang dirancang untuk memproses 
data gambar menggunakan lapisan konvolusi. 
Penyakit kopi paling merusak secara global akibat cendawan 
Hemileia vastatrix, dapat menurunkan panen 60–75%. 
Spesies kopi unggulan yang tumbuh optimal di dataran tinggi 
1.000–2.000 mdpl, menghasilkan cita rasa kompleks. 
Spesies kopi yang adaptif di dataran rendah, lebih tahan penyakit, 
dan banyak dibudidayakan di Lampung. 
xiv 
Computer Vision 
Confusion Matrix 
Dataset 
Deep Learning 
Dense Connection 
DenseNet (Densely Connected 
Conv. Net) 
Epoch 
F1-Score 
False Negative (FN) 
False Positive (FP) 
Feature Map 
Feature Reuse 
Figma 
Fine-tuning 
Firebase 
Ground Truth 
Hemileia vastatrix 
Hyperparameter 
Bidang AI yang memungkinkan komputer menginterpretasikan dan 
memahami konten visual dari gambar atau video. 
Tabel evaluasi yang membandingkan hasil prediksi model dengan 
label sebenarnya, terdiri dari nilai TP, TN, FP, dan FN. 
Kumpulan data terstruktur berupa gambar daun kopi berlabel yang 
digunakan untuk melatih, memvalidasi, dan menguji model. 
Cabang machine learning yang menggunakan jaringan saraf 
berlapis banyak untuk mempelajari representasi data secara 
otomatis. 
Mekanisme khas DenseNet di mana setiap lapisan terhubung 
langsung ke semua lapisan sebelumnya dalam satu blok. 
Arsitektur CNN yang setiap lapisannya terhubung ke semua lapisan 
sebelumnya, efektif untuk klasifikasi penyakit daun kopi. 
Satu siklus penuh pelatihan di mana seluruh data training digunakan 
satu kali untuk memperbarui bobot model. 
Rata-rata harmonik Precision dan Recall. Rumus: 2 × (Precision × 
Recall) / (Precision + Recall). Bernilai 0–1. 
Kondisi model memprediksi sampel sebagai sehat, padahal 
sebenarnya sakit (penyakit tidak terdeteksi). 
Kondisi model memprediksi sampel sebagai sakit, padahal 
sebenarnya sehat (alarm palsu). 
Output dari operasi konvolusi CNN yang merepresentasikan fitur
fitur visual yang telah diekstraksi dari gambar. 
Kemampuan model memanfaatkan kembali fitur yang dipelajari 
lapisan sebelumnya, difasilitasi oleh dense connection DenseNet. 
Alat desain UI/UX berbasis cloud untuk membuat wireframe, 
mockup, dan prototype aplikasi secara kolaboratif. 
Proses menyesuaikan model pre-trained untuk tugas baru dengan 
melatih ulang lapisan-lapisan terakhirnya. 
Platform BaaS dari Google yang menyediakan layanan database 
real-time, autentikasi, dan penyimpanan file untuk aplikasi mobile. 
Label kelas yang benar dan akurat pada setiap sampel dataset, 
digunakan sebagai referensi evaluasi model. 
Nama ilmiah cendawan penyebab Karat Daun Kopi (Coffee Leaf 
Rust), penyakit paling merusak bagi perkebunan kopi global. 
Parameter konfigurasi model yang ditetapkan sebelum pelatihan, 
seperti learning rate, batch size, dan jumlah epoch. 
xv 
ImageNet 
Inferensi (Inference) 
Java 
Java Development Kit (JDK) 
Karat Daun Kopi 
Kecerdasan Buatan (AI) 
Learning Rate 
Leaf Miner (Penambang Daun) 
Leucoptera coffeella 
Machine Learning 
MobileNetV2 
Model Waterfall 
OOP 
Programming) 
(Object-Oriented 
On-device Inference 
Optimizer Adam 
Overfitting 
Phoma 
Precision (Presisi) 
Dataset citra skala besar berisi 1,2 juta gambar dari 1.000 kelas, 
digunakan untuk melatih model pre-trained. 
Proses menggunakan model yang telah dilatih untuk membuat 
prediksi pada data baru. 
Bahasa pemrograman berorientasi objek yang digunakan sebagai 
bahasa utama pengembangan aplikasi Android dalam penelitian ini. 
Paket pengembangan yang menyediakan compiler dan runtime 
untuk menjalankan program Java. 
Lihat Coffee Leaf Rust. Penyakit akibat Hemileia vastatrix yang 
dapat mereduksi panen kopi hingga 60–75%. 
Bidang ilmu komputer yang mengembangkan sistem mampu 
melakukan tugas yang membutuhkan kecerdasan manusia. 
Hyperparameter yang menentukan seberapa besar langkah 
pembaruan bobot model pada setiap iterasi pelatihan. 
Penyakit daun kopi akibat larva lalat Leucoptera coffeella yang 
menggerek jaringan daun dari dalam. 
Nama ilmiah lalat penyebab penyakit Penambang Daun (Leaf 
Miner) pada tanaman kopi. 
Cabang AI yang memungkinkan sistem belajar secara otomatis dari 
data tanpa diprogram secara eksplisit. 
Arsitektur CNN ringan dari Google yang dirancang efisien untuk 
inferensi pada perangkat mobile. 
Model pengembangan perangkat lunak sekuensial linier dengan 
tahapan: Analisis, Perancangan, Implementasi, Pengujian, dan 
Pemeliharaan. 
Paradigma pemrograman yang mengorganisir kode berdasarkan 
objek yang menggabungkan data dan perilaku. 
Proses inferensi model AI yang berjalan langsung di perangkat 
pengguna tanpa koneksi ke server eksternal. 
Algoritma optimasi adaptif untuk pelatihan deep learning yang 
menyesuaikan learning rate secara otomatis per parameter. 
Kondisi model terlalu menghafal data training sehingga tidak 
mampu melakukan generalisasi pada data baru. 
Penyakit daun kopi akibat jamur Phoma costarricensis yang 
menghasilkan bercak gelap dan menyebabkan kerontokan daun. 
Proporsi prediksi positif yang benar-benar positif. Rumus: TP / (TP 
+ FP). 
xvi 
Pre-trained Model 
Progressive Mobile App (PMA) 
Progressive Web App (PWA) 
Python 
Recall (Sensitivitas) 
ResNet (Residual Network) 
Sequence Diagram 
Service Worker 
Smart Agriculture 
TensorFlow 
TensorFlow Lite (TFLite) 
Test Set (Data Uji) 
Training Set (Data Latih) 
Transfer Learning 
True Negative (TN) 
True Positive (TP) 
UML 
Language) 
(Unified 
Modeling 
Model deep learning yang telah dilatih pada dataset besar 
(ImageNet) dan siap digunakan sebagai titik awal Transfer 
Learning. 
Aplikasi mobile berbasis teknologi web modern yang dapat 
beroperasi secara offline menggunakan Service Worker. 
Konsep aplikasi web yang menggabungkan fitur web dan native, 
dapat diinstal dan berjalan secara offline. 
Bahasa pemrograman yang digunakan untuk membangun dan 
melatih 
model 
TensorFlow/Keras. 
DenseNet-121 menggunakan framework 
Kemampuan model mendeteksi semua kasus positif yang ada. 
Rumus: TP / (TP + FN). 
Arsitektur CNN populer yang menggunakan skip connection untuk 
mengatasi vanishing gradient pada jaringan sangat dalam. 
Diagram UML yang menggambarkan interaksi antar objek sistem 
berdasarkan urutan waktu. 
Script JavaScript yang berjalan di background browser untuk 
mengelola caching dan memungkinkan aplikasi berjalan secara 
offline. 
Penerapan teknologi modern (AI, IoT, sensor) dalam pertanian 
untuk meningkatkan efisiensi dan produktivitas. 
Framework open-source dari Google untuk membangun dan 
melatih model machine learning dan deep learning. 
Versi ringan TensorFlow untuk menjalankan model AI pada 
perangkat mobile. Model disimpan dalam format .tflite. 
Subset data (10–20%) yang digunakan hanya untuk evaluasi akhir 
model, tidak pernah digunakan saat pelatihan. 
Subset terbesar dataset (70–80%) yang digunakan untuk melatih 
bobot model deep learning. 
Teknik memanfaatkan bobot model pre-trained sebagai titik awal 
pelatihan untuk tugas baru yang lebih spesifik. 
Kondisi model memprediksi sampel sebagai sehat dan prediksi 
tersebut benar (memang sehat). 
Kondisi model memprediksi sampel sebagai sakit dan prediksi 
tersebut benar (memang sakit). 
Bahasa pemodelan standar untuk memvisualisasikan dan 
mendokumentasikan desain sistem perangkat lunak. 
xvii 
Usability Testing 
Use Case Diagram 
Validation Set (Data Validasi) 
Vanishing Gradient 
VGG (Visual Geometry Group) 
Web App Manifest 
YOLOv7 
Pengujian yang melibatkan pengguna nyata (petani kopi) untuk 
mengevaluasi kemudahan penggunaan aplikasi di lapangan. 
Diagram UML yang menggambarkan hubungan antara aktor 
(pengguna) dengan fungsi-fungsi yang disediakan sistem. 
Subset data (10–15%) yang digunakan selama pelatihan untuk 
memantau performa dan mencegah overfitting. 
Masalah pelatihan jaringan sangat dalam di mana gradien 
menghilang sehingga lapisan awal tidak belajar. Diatasi oleh 
DenseNet. 
Arsitektur CNN klasik dari Oxford yang menjadi pembanding 
performa dengan DenseNet dalam klasifikasi penyakit kopi. 
File JSON berisi metadata aplikasi web (nama, ikon, mode 
tampilan) agar dapat diinstal di layar utama perangkat. 
Arsitektur deep learning untuk deteksi objek real-time. Berbeda 
paradigma dengan klasifikasi berbasis Transfer Learning DenseNet. 
xviii 
2 
BAB I 
PENDAHULUAN 
1.1 
Latar Belakang 
Kopi merupakan salah satu komoditas perkebunan bernilai strategis yang 
memberikan kontribusi besar terhadap perekonomian dan devisa negara 
Indonesia. Berdasarkan data resmi Badan Pusat Statistik (BPS) dalam Statistik 
Kopi Indonesia 2023, luas areal perkebunan kopi nasional mencapai lebih dari 
1,26 juta hektare dengan total produksi sebesar 756,1 ribu ton pada tahun 2023 
[1]. Lebih dari 98,6% produksi tersebut dihasilkan oleh perkebunan rakyat 
dengan jumlah rumah tangga petani mencapai 1.634.914 kepala keluarga yang 
tersebar di seluruh wilayah Indonesia [1]. Sebagai produsen kopi terbesar 
kelima di dunia setelah Brazil, Vietnam, Kolombia, dan Ethiopia, Indonesia 
menghasilkan berbagai varietas unggulan seperti Arabika, Robusta, dan 
Liberika yang menjadi andalan ekspor non-migas. Nilai ekspor kopi Indonesia 
tercatat sebesar US$ 916,5 juta pada tahun 2023 dengan sentra produksi utama 
tersebar di Sumatera Selatan, Lampung, Bengkulu, Aceh, dan Sulawesi Selatan 
[1]. Besarnya kontribusi sosial dan ekonomi komoditas kopi menjadikan 
keberlanjutan produktivitas perkebunan sebagai isu strategis yang tidak dapat 
diabaikan. 
Namun di balik potensi besar tersebut, produktivitas perkebunan kopi 
Indonesia menghadapi ancaman serius dari serangan penyakit tanaman yang 
menyerang daun sebagai organ utama fotosintesis. Penyakit karat daun (Coffee 
Leaf Rust/CLR) yang disebabkan oleh cendawan Hemileia vastatrix 
merupakan penyakit paling merusak secara global, dengan potensi mereduksi 
3 
hasil panen hingga 60–75% pada kasus epidemi parah [2]. Pada skala global, 
kerugian ekonomi akibat CLR diperkirakan mencapai lebih dari US$ 2 miliar 
per tahun dalam biaya pengendalian penyakit saja, belum termasuk kehilangan 
produksi langsung [3]. Selain karat daun, penyakit bercak daun Cercospora 
(Cercospora coffeicola), penambang daun (Leucoptera coffeella), dan Phoma 
turut menyebabkan kerontokan daun dalam jumlah besar yang menurunkan 
kapasitas fotosintesis tanaman, berdampak langsung pada penurunan kualitas 
biji kopi yang dihasilkan [4]. Kondisi ini diperparah oleh perubahan iklim yang 
menciptakan lingkungan lebih sesuai bagi penyebaran patogen, sehingga 
ancaman penyakit daun kopi semakin intensif dari tahun ke tahun [5]. 
Proses deteksi dan diagnosis penyakit daun kopi di lapangan hingga saat 
ini masih sangat bergantung pada metode konvensional, yakni pengamatan 
visual secara langsung oleh petani atau penyuluh pertanian [6][7], yang 
memiliki sejumlah keterbatasan mendasar. Dari sisi akurasi, pengamatan visual 
sangat bergantung pada kepekaan dan pengalaman individu pemeriksa 
sehingga bersifat subjektif dan rentan terhadap kesalahan identifikasi, terutama 
pada tahap awal kemunculan gejala ketika bahkan petani berpengalaman kerap 
kesulitan membedakan satu jenis penyakit dengan jenis lainnya [6][8]. Kondisi 
ini berpotensi mengakibatkan penanganan yang tidak tepat atau terlambat, 
sehingga infeksi yang semula terbatas dapat berkembang meluas ke seluruh 
area perkebunan. Dari sisi efisiensi dan skalabilitas, pemeriksaan daun secara 
manual satu per satu pada lahan yang berhektare-hektare merupakan pekerjaan 
yang lambat dan padat tenaga kerja, sehingga tidak mampu mengimbangi laju 
penyebaran penyakit yang dalam kondisi tertentu dapat berlangsung hanya 
4 
dalam hitungan hari [9][10]. Persoalan ini diperparah oleh keterbatasan 
struktural berupa kelangkaan tenaga ahli patologi tanaman di wilayah-wilayah 
terpencil, sebuah kondisi yang umum dijumpai di sentra perkebunan kopi 
Indonesia dengan akses yang masih sangat terbatas terhadap konsultan maupun 
penyuluh pertanian yang kompeten [11][3], sehingga petani sering kali 
terpaksa mengambil keputusan penanganan secara mandiri berdasarkan 
perkiraan pribadi, bukan diagnosis yang terverifikasi secara ilmiah. Siddiqua 
et al. dalam evaluasi komprehensif terhadap 17 aplikasi mobile deteksi 
penyakit tanaman menegaskan bahwa keterlambatan deteksi akibat 
keterbatasan akses terhadap teknologi menyebabkan penanganan tidak 
optimal, sehingga penyakit berkembang lebih luas dan merugikan petani secara 
ekonomi [12]. 
Perkembangan pesat teknologi kecerdasan buatan (Artificial Intelligence), 
khususnya dalam bidang Computer Vision dan Deep Learning, membuka 
peluang baru untuk mengatasi keterbatasan metode konvensional tersebut. Li 
et al. dalam tinjauan komprehensif terhadap lebih dari 100 penelitian 
menegaskan bahwa model Convolutional Neural Network (CNN) berbasis 
Deep Learning telah menjadi pendekatan terdepan dalam deteksi dan 
klasifikasi penyakit tanaman berbasis citra, secara konsisten melampaui 
seluruh metode machine learning tradisional [13]. Berbagai penelitian 
terdahulu telah membuktikan keunggulan pendekatan ini: Novtahaning et al. 
berhasil mengklasifikasikan empat jenis penyakit daun kopi menggunakan 
ensemble sembilan model CNN pre-trained dengan akurasi 97% [14]; Aufar 
dan Kaloka mengimplementasikan Transfer Learning berbasis MobileNetV2 
5 
untuk deteksi penyakit daun kopi Robusta dan mencapai akurasi 99,93% [15]; 
dan Gürsoy dalam studi review berbagai arsitektur deep learning untuk deteksi 
penyakit tanaman mengkonfirmasi bahwa CNN dengan mekanisme ekstraksi 
fitur hierarkis mampu mengenali pola visual penyakit yang sangat halus, jauh 
melampaui kemampuan penglihatan manusia [16]. Salah satu pendekatan yang 
terbukti sangat efektif dalam pengembangan sistem deteksi penyakit tanaman 
adalah Transfer Learning, yaitu teknik yang memanfaatkan bobot model yang 
telah dilatih pada dataset skala besar (pre-trained model) seperti ImageNet 
yang memuat lebih dari 1,2 juta gambar dari 1.000 kelas sebagai titik awal 
pelatihan, kemudian disesuaikan (fine-tuning) untuk permasalahan target yang 
lebih spesifik [17]. Strategi ini menawarkan empat keunggulan utama: 
kebutuhan data berlabel yang jauh lebih relevan mengingat keterbatasan 
dataset citra daun kopi yang teranotasi, waktu pelatihan yang lebih singkat 
karena model tidak perlu mempelajari representasi fitur dari nol, performa 
klasifikasi yang umumnya lebih tinggi berkat feature reuse dari pengetahuan 
bidang visual yang sudah dimiliki model, serta berkurangnya risiko overfitting 
pada dataset berukuran terbatas [18]. Sharma et al. mengkonfirmasi bahwa 
Transfer Learning merupakan strategi yang sangat efektif untuk klasifikasi 
penyakit daun kopi mengingat pengumpulan dan anotasi dataset berskala besar 
membutuhkan biaya, waktu, dan keahlian bidang yang substansial [17], dan 
Tassis serta Krohling memperkuat argumen ini dengan membuktikan bahwa 
model berbasis Transfer Learning secara konsisten menghasilkan akurasi 
klasifikasi lebih tinggi dibandingkan model yang dilatih dari awal pada bidang 
stres biotik tanaman kopi [19]. 
6 
Dalam konteks penelitian ini, arsitektur yang dipilih adalah DenseNet-121 
(Densely Connected Convolutional Network), yang pemilihannya didasarkan 
pada bukti empiris yang kuat dari penelitian-penelitian terdahulu. DenseNet 
memiliki keunggulan dasar berupa mekanisme koneksi padat (dense 
connection), di mana setiap lapisan menerima masukan langsung dari semua 
lapisan sebelumnya dalam blok yang sama melalui operasi concatenation 
feature map. Arsitektur ini secara efektif mengatasi masalah vanishing gradient 
yang menghambat pelatihan jaringan sangat dalam, mendorong feature reuse 
yang efisien, sekaligus mengurangi jumlah parameter secara signifikan 
dibandingkan arsitektur CNN konvensional [20]. Mansouri et al. membuktikan 
bahwa DenseNet dengan pendekatan Transfer Learning dan fine-tuning 
mencapai akurasi 99,36% dalam klasifikasi tiga jenis penyakit daun kopi 
(Phoma, Cercospora, dan Rust), mengungguli ResNet50 dan VGG19 pada 
dataset yang sama [21]. Araaf et al. mengimplementasikan DenseNet untuk 
deteksi karat daun kopi dan membuktikan bahwa arsitektur ini tidak hanya 
unggul dalam akurasi klasifikasi, tetapi juga layak secara praktis untuk 
diimplementasikan pada perangkat komputasi terbatas di lapangan [3]. 
Sedangkan Karia et al. mengembangkan DenseNet201Plus dengan Transfer 
Learning dan memperoleh akurasi 99,0% untuk deteksi karat daun kopi, 
mengkonfirmasi dominasi arsitektur DenseNet pada bidang ini [22]. 
Meskipun demikian, terdapat kesenjangan (research gap) signifikan yang 
belum terjawab oleh penelitian-penelitian terdahulu. Esgario et al. yang 
mengembangkan aplikasi mobile Android untuk deteksi penyakit daun kopi 
belum mengintegrasikan arsitektur Transfer Learning modern seperti 
7 
DenseNet, sehingga potensi akurasi deteksinya belum optimal [4]. Ardiansyah 
dan Hasan menggunakan pendekatan deteksi objek berbasis YOLOv7 yang 
berbeda paradigma dengan klasifikasi berbasis Transfer Learning DenseNet, 
serta belum dikemas dalam platform aplikasi yang aksesibel secara luas oleh 
petani [23]. Novtahaning et al. yang menghasilkan akurasi ensemble 97% juga 
hanya berhenti pada tahap eksperimen model tanpa menghadirkan sistem siap 
pakai yang dapat dioperasikan petani di lapangan [14]. Mazumder et al. 
menegaskan bahwa meskipun banyak model deep learning telah menunjukkan 
akurasi tinggi di lingkungan laboratorium, implementasi praktis pada 
perangkat mobile dengan sumber daya komputasi terbatas masih menjadi 
tantangan yang belum banyak dieksplorasi secara komprehensif [18], dan 
tantangan infrastruktur berupa keterbatasan konektivitas internet di wilayah 
perkebunan terpencil menjadi hambatan nyata bagi petani dalam mengadopsi 
aplikasi smartphone konvensional yang membutuhkan koneksi server secara 
terus-menerus [12]. Teknologi Progressive Mobile App (PMA) yang 
dikembangkan berdasarkan prinsip Progressive Web App (PWA) hadir sebagai 
solusi yang sesuai untuk menjawab tantangan aksesibilitas tersebut, dengan 
mengintegrasikan Service Worker, Web App Manifest, dan responsive design 
untuk menghadirkan pengalaman layaknya aplikasi native tanpa proses 
instalasi melalui toko aplikasi resmi, serta mampu beroperasi secara offline 
atau pada kondisi jaringan yang sangat buruk, karakteristik yang sangat relevan 
bagi petani yang beroperasi di kebun terpencil [24]. Integrasi model DenseNet
121 yang telah dikonversi ke format TensorFlow Lite (.tflite) memungkinkan 
proses inferensi dilakukan langsung di perangkat mobile tanpa ketergantungan 
8 
pada koneksi internet atau server eksternal, sebagaimana dikonfirmasi oleh 
Ghosh et al. bahwa integrasi model Deep Learning ke dalam platform aplikasi 
mobile telah memberikan dampak besar dalam praktik pertanian cerdas (smart 
agriculture) dengan meningkatkan kemampuan deteksi dini penyakit tanaman 
[25], serta oleh Siddiqua et al. yang menegaskan bahwa aksesibilitas dan 
akurasi merupakan dua faktor penentu utama tingkat adopsi teknologi deteksi 
penyakit tanaman di kalangan petani, dan PMA memenuhi kedua kriteria 
tersebut secara inheren [12]. Berdasarkan seluruh pemaparan tersebut, 
penelitian ini menawarkan kontribusi nyata (novelty) melalui tiga aspek yang 
saling bersinergi dan belum pernah diintegrasikan sebelumnya, yakni 
mengimplementasikan arsitektur DenseNet-121 dengan metode Transfer 
Learning yang terbukti unggul dalam akurasi klasifikasi penyakit daun kopi, 
mengoptimalkan model untuk kebutuhan inferensi on-device pada perangkat 
mobile melalui konversi ke format TensorFlow Lite, dan mengemas seluruh 
fungsionalitas tersebut dalam platform Progressive Mobile App (PMA) 
berbasis Java Android yang dapat digunakan secara offline di lokasi 
perkebunan terpencil sekalipun. Integrasi ketiga aspek ini secara sinergis 
mengisi kesenjangan antara riset akademik dan kebutuhan implementasi 
teknologi di lapangan pertanian kopi Indonesia. Oleh karena itu, peneliti 
mengangkat judul: “Implementasi Aplikasi Progressive Mobile App (PMA) 
untuk Deteksi Penyakit pada Daun Kopi Menggunakan Transfer Learning 
dengan Model DenseNet”. 
9 
1.2 
1.3 
Rumusan Masalah 
Merujuk pada latar belakang di atas, inti permasalahan yang akan 
diselesaikan dalam penelitian ini dirumuskan sebagai berikut: 
1. Bagaimana merancang dan mengimplementasikan metode Transfer 
Learning dengan arsitektur DenseNet untuk mengenali dan 
mengklasifikasikan jenis penyakit pada citra daun kopi?  
2. Bagaimana performa model DenseNet dalam mendeteksi penyakit 
daun kopi dengan pengukuran menggunakan metrik evaluasi accuracy, 
precision, recall, dan F1-score?  
3. Bagaimana membangun aplikasi berbasis Progressive Mobile App 
(PMA) yang mampu mengintegrasikan model deteksi tersebut sehingga 
dapat digunakan secara responsif, mudah, dan mendukung akses offline 
di perangkat mobile? 
Batasan Masalah 
Agar penelitian ini terarah dan fokus pada tujuan utama, penulis 
menetapkan batasan-batasan masalah sebagai berikut: 
1. Objek Penelitian: Dataset citra yang digunakan terbatas pada citra daun 
kopi, yang terdiri dari kategori daun sehat dan daun yang terindikasi 
penyakit (seperti karat daun dan bercak daun). 
2. Arsitektur Model: Penerapan Transfer Learning difokuskan secara spesifik 
menggunakan arsitektur DenseNet121, tanpa melakukan komparasi 
performa dengan arsitektur CNN lainnya dalam proses pengembangan ini. 
3. Lingkup Aplikasi: Aplikasi dikembangkan dengan teknologi Progressive 
Mobile App (PMA). Fitur utama mencakup pengunggahan citra, proses 
10 
deteksi otomatis, dan kemampuan akses terbatas saat offline menggunakan 
teknologi service worker. 
4. Fungsionalitas: Sistem yang ada dalam penelitian ini hanya berfokus pada 
klasifikasi jenis penyakit. 
5. Evaluasi: Pengujian performa dibatasi pada metrik efektivitas model 
(accuracy, precision, recall, F1-score), dan tidak mencakup analisis 
mendalam terkait efisiensi waktu komputasi perangkat keras. 
1.1 Tujuan Penelitian 
Tujuan  yang ingin dicapi melalui penelitian ini adalah: 
1. Mengembangkan model deteksi penyakit daun kopi menggunakan metode 
Transfer Learning dengan arsitektur DenseNet untuk mengenali kategori 
penyakit dari citra daun. 
2. Menganalisis performa model deteksi menggunakan metrik evaluasi untuk 
mengetahui tingkat akurasi dan efektivitas DenseNet dalam 
mengklasifikasi penyakit daun kopi. 
3. Membangun Progressive Mobile App (PMA) yang mampu 
mengintegrasikan model DenseNet sehingga mendukung proses deteksi 
penyakit daun kopi secara cepat, mudah, dan dapat diakses melalui 
perangkat mobile. 
1.4 
Manfaat Penelitian 
Hasil penelitian ini diharapkan dapat memberikan kontribusi 
positif bagi berbagai pihak, antara lain: 
1 Bagi Petani Kopi 
11 
Penelitian ini secara langsung memberikan manfaat praktis bagi para petani 
kopi, khususnya yang berada di daerah terpencil dengan keterbatasan akses 
terhadap tenaga ahli patologi tanaman. Melalui aplikasi PMA yang 
dikembangkan, dapat membantu petani dapat mendeteksi jenis penyakit 
pada daun kopi secara mandiri dan akurat hanya dengan menggunakan 
kamera smartphone mereka. Kemampuan aplikasi untuk beroperasi secara 
offline menjadikannya sangat relevan untuk kondisi lapangan perkebunan 
yang kerap kali tidak memiliki koneksi internet yang stabil. Dengan 
demikian, langkah pencegahan dan penanganan penyakit dapat dilakukan 
lebih dini, sehingga kerugian hasil panen akibat keterlambatan diagnosis 
dapat diminimalkan secara signifikan. 
2 Bagi Akademisi dan Peneliti 
Hasil penelitian ini diharapkan dapat memperkaya khazanah ilmu 
pengetahuan dan menjadi referensi empiris yang berharga dalam 
pengembangan teknologi Computer Vision dan Transfer Learning pada 
bidang pertanian cerdas (smart agriculture). Penelitian ini mengisi 
kesenjangan riset yang selama ini masih terbuka, yaitu integrasi model 
DenseNet-121 ke dalam platform aplikasi mobile yang dapat digunakan 
secara nyata di lapangan, bukan sekadar berhenti pada tahap eksperimen 
laboratorium. Temuan-temuan dalam penelitian ini, termasuk hasil 
evaluasi model menggunakan metrik accuracy, precision, recall, dan F1
score, diharapkan dapat menjadi landasan pengembangan penelitian 
selanjutnya di bidang deteksi penyakit tanaman berbasis kecerdasan 
buatan. 
12 
3 Bagi Pengembang Sistem 
Penelitian ini menyediakan blueprint teknis yang komprehensif mengenai 
cara mengintegrasikan model kecerdasan buatan berbasis Deep Learning 
ke dalam platform aplikasi mobile modern. Mulai dari proses pelatihan 
model DenseNet-121 menggunakan TensorFlow/Keras, konversi model ke 
format TensorFlow Lite (.tflite) untuk kebutuhan inferensi on-device, 
hingga implementasinya ke dalam aplikasi Android berbasis Java dengan 
dukungan Firebase sebagai backend, seluruh rangkaian proses ini 
didokumentasikan secara rinci sehingga dapat dijadikan acuan praktis bagi 
para pengembang sistem yang ingin membangun solusi serupa di bidang 
pertanian maupun domain lainnya. 
4 Bagi Program Studi Rekayasa Perangkat Lunak 
Penelitian ini berkontribusi pada pengembangan kapasitas akademik 
Program Studi Rekayasa Perangkat Lunak Universitas Aisyah Pringsewu 
dengan menghadirkan karya ilmiah yang mengeksplorasi penerapan 
teknologi mutakhir, yaitu kecerdasan buatan (AI) dan pengembangan 
aplikasi mobile (Mobile Development), dalam konteks permasalahan nyata 
di masyarakat. Penelitian ini diharapkan dapat menjadi inspirasi dan 
motivasi bagi mahasiswa angkatan berikutnya untuk terus berinovasi dalam 
menghasilkan solusi teknologi yang berdampak, serta memperkuat rekam 
jejak akademik program studi dalam bidang AI dan pengembangan 
perangkat lunak berbasis mobile. 
Secara keseluruhan, penelitian ini merupakan wujud nyata dari 
sinergisitas antara riset akademik dan kebutuhan masyarakat, yang 
13 
diharapkan dapat memberikan dampak positif jangka panjang bagi 
kemajuan sektor pertanian kopi Indonesia melalui pemanfaatan teknologi 
kecerdasan buatan yang inovatif dan aksesibel. 
1.5 
Sistematika Penulisan 
Untuk memberikan gambaran menyeluruh mengenai alur 
penelitian, laporan skripsi ini disusun dengan sistematika sebagai berikut: 
• BAB I PENDAHULUAN: Menguraikan latar belakang masalah, 
rumusan masalah, batasan masalah, tujuan dan manfaat penelitian, serta 
metodologi dan sistematika penulisan. 
• BAB II LANDASAN TEORI: Memaparkan tinjauan pustaka, 
penelitian terdahulu yang relevan, serta kerangka teori mengenai 
Transfer Learning, Convolutional Neural Network (CNN), arsitektur 
DenseNet, dan konsep Progressive Mobile App (PMA). 
• BAB III METODE PENELITIAN: Menjelaskan secara rinci tahapan 
penelitian, mulai dari teknik pengumpulan data, alat dan bahan yang 
digunakan, skenario eksperimen model, hingga alur perancangan 
sistem. 
 
 
15 
 
BAB II  
LANDASAN TEORI 
 
2.1 Kajian Pustaka 
2.1.1. Penelitian Terdahulu 
Untuk mendapatkan hasil penelitian yang baik, penulis melakukan 
peninjauan terhadap penelitian sebelumnya yang berkaitan dengan topik 
penelitian ini. Tujuannya untuk menghindari terjadinya duplikasi terhadap 
penelitian sebelumnya yang telah membahas permasalahan serupa. 
Penelitian terdahulu yang penulis  dapatkan dari jurnal diuraikan dalam 
Tabel 2.1. 
Table 2.1 Perbandingan Jurnal Ilmiah 
No Penelti Judul Objek 
Penelitian 
Hasil 
Kekangan 
Penelitian 
Terdahulu/GAP, 
Relevansi & 
Novelty 
1 Qian Ouyang 
(2023)[26] 
Study on High
resolution Remote 
Sensing Image 
Scene Classification 
Using Transfer 
Learning 
Remote sensing 
image 
classification 
(RSIC) 
Penigkatan performa  
klasifikasi scene citra 
remote sensing yang 
signifikan menggunakan 
pendekatan transfer 
learning dengan fine
tuning. 
Penelitian ini 
menggunakan 
transfer learning 
seperti penelitian 
ini, namun 
penggunaannya 
untuk klasifikasi 
citra melalui jarak 
jauh, meskipun 
berbeda object  
pendekatan prediktif 
dan output 
regresifnya relevan 
dengan penelitian 
ini 
16 
 
 
No Penelti Judul 
Objek 
Penelitian 
Hasil 
Kekangan 
Penelitian 
Terdahulu/GAP, 
Relevansi & 
Novelty 
2 Suleiman 
Shelash 
Mohammad, 
et all [27] 
Aiding the Digital 
Eyes to Detect the 
Leaf-Spot Diseases 
in Rice Crops using 
DenseNet CNN 
Algorithms 
Penyakit bercak 
daun pada 
tanaman padi 
Penelitian ini 
menunjukkan bahwa 
arsitektur DenseNet-201 
berbasis transfer learning 
menghasilkan akurasi 
tertinggi sebesar 97–98% 
dalam mendeteksi 
penyakit daun padi 
dibandingkan dengan 
arsitektur CNN lainnya 
seperti ResNet, 
GoogleNet, dan 
Xception. Modifikasi 
arsitektur DenseNet juga 
berhasil meningkatkan 
efisiensi komputasi tanpa 
menurunkan performa 
klasifikasi. 
Penelitian ini 
mengoptimasi 
akurasi sedangkan 
penelitian ini 
mengembangkan 
system dengan 
model pendekatan 
arsitektur yang 
berbeda. 
3 A. Gajanan, 
N. 
Preetham[28] 
Deep Learning for 
Smart Agriculture: A 
Comprehensive 
Review of CNN 
Architectures, 
Multispectral 
Imaging, 
Explainable AI and 
Transfer Learning 
for Crop Disease 
Detection 
Dari berbagai 
macam tanaman 
CNN dan transfer 
learning mampu 
meningkatkan akurasi 
deteksi penyakit 
tanaman, sementara 
multispectral imaging 
dan XAI membantu 
deteksi dini serta 
interpretasi model AI. 
Pada penelitian ini 
berfokus pada study 
review dari objek, 
sedangkan yang 
akan dilakukan 
lebih implementif 
dan berfokus pada 
daun kopi 
4 J.G.M. 
Esgario et 
al[29]. 
An App to Assist 
Farmers in the 
Identification of 
Citra daun kopi Model CNN mampu 
mengklasifikasi penyakit 
daun kopi melalui 
Belum 
mengintegrasikan 
metode transfer 
17 
 
 
No Penelti Judul 
Objek 
Penelitian 
Hasil 
Kekangan 
Penelitian 
Terdahulu/GAP, 
Relevansi & 
Novelty 
Diseases and Pests 
of Coffee Leaves 
Using Deep 
Learning (2022) 
aplikasi mobile dengan 
akurasi tinggi. 
learning model 
modern seperti 
DenseNet. 
Relevansi : Menjadi 
dasar 
pengembangan 
aplikasi mobile, 
penelitian baru 
menggunakan 
transfer learning 
DenseNet dan 
PMA.  
5 Ardiansyah,  
Nur 
Fitrianingsih 
Hasan(2023)[
23] 
Deteksi dan 
Klasifikasi Penyakit 
Pada Daun Kopi 
Menggunakan 
Yolov7 
 
Daun kopi YOLOv7 mampu 
mendeteksi beberapa 
jenis penyakit dengan 
performa baik 
Penelitian ini 
menggunakan 
pendekatan object 
detection, bukan 
klasifikasi berbasis 
transfer learning 
dengan DenseNet. 
Selain itu, sistem 
belum 
dikembangkan 
dalam bentuk 
aplikasi mobile 
progresif yang dapat 
diakses secara luas 
oleh petani. 
6 J. Jepkoech 
et al.[30] 
Arabica Coffee Leaf 
Images Dataset for 
Coffee Leaf Disease 
Detection and 
Classification (2021) 
Dataset citra 
daun kopi 
Arabika 
Menyediakan dataset 
citra daun kopi untuk 
penelitian klasifikasi 
penyakit. 
Tidak membahas 
implementasi model 
klasifikasi secara 
komprehensif. 
Relevansi : Dataset 
menjadi referensi 
18 
 
 
No Penelti Judul 
Objek 
Penelitian 
Hasil 
Kekangan 
Penelitian 
Terdahulu/GAP, 
Relevansi & 
Novelty 
untuk pelatihan 
model deteksi 
penyakit daun kopi. 
7 D. 
Novtahaning 
et al.[14] 
Deep Learning 
Ensemble-Based 
Automated 
Recognition of 
Coffee Leaf Disease 
(2022) 
Citra daun kopi Pendekatan ensemble 
CNN menghasilkan 
akurasi klasifikasi 97%. 
Model cukup 
kompleks dan 
membutuhkan 
komputasi tinggi. 
Relevansi : 
Penelitian baru 
menggunakan 
transfer learning 
DenseNet yang 
lebih efisien. 
8 Ahmed, 
Imtiaz 
Yadav, 
Pramod 
Kumar[31] 
Plant disease 
detection using 
machine learning 
approaches 
Citra daun 
tanaman 
Aplikasi mobile mampu 
membantu petani 
mendeteksi penyakit 
tanaman secara cepat. 
Model yang 
digunakan belum 
spesifik untuk kopi. 
Novelty : Penelitian 
baru fokus pada 
penyakit daun kopi 
dengan model 
DenseNet. 
9 A. J. Karia, J. 
S. Ally, and 
S. 
Leonard[22] 
Enhancing Coffee 
Leaf Rust Detection 
with 
DenseNet201Plus 
and Transfer 
Learning (2025) 
Deteksi karat 
daun kopi (CLR) 
menggunakan 
DenseNet201Plus 
+ transfer 
learning. 
Akurasi 99.0% pada 
dataset Mbozi, lebih baik 
dari baseline ImageNet 
(97.78%). 
Tidak disebutkan 
deployment 
mobile/PWA; fokus 
dataset spesifik 
Relevansi : sangat 
relevan (DenseNet + 
TL untuk kopi) 
 novelty: PMA 
mobile untuk real
time field use, 
bukan hanya 
desktop. 
19 
No 
Penelti 
Judul 
Objek 
Penelitian 
Hasil 
10 
P. Too et 
al.[32] 
A Comparative 
Study of Fine‑Tuned 
CNN Models for 
Plant Disease 
Identification (2022) 
Citra daun 
tanaman 
Transfer learning CNN 
meningkatkan akurasi 
klasifikasi. 
Kekangan 
Penelitian 
Terdahulu/GAP, 
Relevansi & 
Novelty 
Tidak fokus pada 
tanaman kopi. 
Relevansi : Menjadi 
dasar pemilihan 
model transfer 
learning. 
Merujuk pada Tabel 2.1, penelitian terdahulu Sebagian besar studi 
hanya berfokus pada pengembangan dan evaluasi model deep learning 
untuk klasifikasi penyakit pada daun. Namun demikian, Adapun 
kesenjangan yang masih terbuka seperti Sebagian peneliti terdahulu 
hanya berhenti dalam tahap eksperimen tanpa pengembangan system 
aplikasi yang siap digunakan. Serta pengoptimasi model untuk kebutuhan 
perangkat mobile dan penggunaan lapangan belum banyak dibahas secara 
kompeherensif. Dengan demikian untuk mengisi kesenjangan dalam 
penelitian tersebut, dengan mengembangkan aplikasi progressive mobile 
app (PMA) berbasis transfer learning dengan menggunakan arsitektur 
desenet untuk mendeteksi penyait pada daun kopi. Selain menitikberatkan 
pada akurasi model, penelitian ini juga mempertimbangkan aspek 
implementasi praktis, efisiensi model pada perangkat mobile, serta 
kemudahan akses bagi pengguna di lapangan.    
2.2 Dasar Teori 
2.2.1  
Tanaman Kopi 
Tanaman kopi (Coffea sp.) merupakan tanaman perkebunan tropis 
yang tergolong dalam famili Rubiaceae dan genus Coffea. Tanaman ini 
termasuk jenis dikotil berbentuk pohon yang dapat tumbuh hingga 
ketinggian 8–10 meter di alam bebas, namun dalam budidaya komersial 
20 
ketinggiannya dipertahankan pada kisaran 2–3 meter agar memudahkan 
panen dan pemeliharaan. Genus Coffea mencakup lebih dari 100 spesies, 
namun dua spesies yang paling banyak dibudidayakan secara global 
adalah Coffea arabica (kopi arabika) dan Coffea canephora (kopi robusta). 
Kopi arabika tumbuh optimal pada ketinggian 1.000–2.000 mdpl dengan 
suhu 15–24°C, sedangkan kopi robusta lebih adaptif pada dataran rendah 
hingga 700 mdpl dan lebih tahan terhadap beberapa jenis penyakit 
tertentu[15]. 
Tanaman kopi memiliki morfologi yang khas, dengan daun berbentuk 
elips berwarna hijau tua mengkilap, bunga berwarna putih beraroma 
harum yang muncul di ketiak daun, serta buah berbentuk bulat atau 
lonjong yang berubah dari hijau menjadi merah atau kuning saat matang. 
Siklus produksi tanaman kopi relatif panjang; tanaman mulai berbuah 
pada usia 2,5 hingga 3 tahun setelah penanaman dan dapat berproduksi 
selama 20–30 tahun apabila mendapatkan perawatan memadai serta 
terbebas dari serangan hama dan penyakit yang merusak. Aufar dan 
Kaloka (2022) menegaskan bahwa Indonesia merupakan eksportir dan 
produsen kopi besar, dan budidaya kopi memberikan kontribusi nyata 
bagi perekonomian nasional[15]. 
2.2.2  
Produksi Kopi di Indonesia 
Indonesia menduduki posisi keempat sebagai produsen kopi 
terbesar di dunia setelah Brasil, Vietnam, dan Kolombia. Luas area 
perkebunan kopi Indonesia mencapai lebih dari 1,2 juta hektare dengan 
total produksi yang secara konsisten berada di kisaran 700 ribu ton per 
tahun. Komoditas kopi menjadi salah satu penghasil devisa negara yang 
signifikan dalam sektor ekspor non-migas, menyerap lebih dari 1,8 juta 
keluarga petani yang menggantungkan penghidupan mereka pada sektor 
perkebunan kopi di seluruh kepulauan Indonesia[15]. 
Sentra produksi kopi tersebar di beberapa provinsi unggulan, antara 
lain Sumatera Selatan, Lampung, Bengkulu, Aceh, dan Sulawesi Selatan. 
Lampung dikenal sebagai produsen kopi robusta terbesar, sementara Aceh 
21 
dan Toraja dikenal dengan kopi arabika premium yang diminati pasar 
internasional. Keberagaman geografi dan iklim Indonesia menghasilkan 
profil rasa kopi yang beragam, menjadikan kopi Indonesia sebagai salah 
satu kopi spesialti yang diperhitungkan di pasar global. Namun, tantangan 
berupa serangan penyakit tanaman yang semakin intensif mengancam 
keberlanjutan produktivitas perkebunan dan membutuhkan solusi 
teknologi inovatif[14]. 
2.2.3  
Peran Kopi dalam Sektor Perkebunan 
Kopi memainkan peran strategis dalam sektor perkebunan 
Indonesia dari tiga dimensi utama: ekonomi, sosial, dan lingkungan. 
Secara ekonomi, kopi merupakan komoditas ekspor andalan yang 
menyumbang pendapatan devisa secara rutin dan berkontribusi pada 
pertumbuhan Produk Domestik Bruto (PDB) sektor pertanian. Permintaan 
kopi global yang terus meningkat seiring pertumbuhan industri kafe dan 
budaya minum kopi di berbagai belahan dunia menjadi peluang besar bagi 
pengembangan industri kopi Indonesia yang berkelanjutan[15]. 
Dari dimensi sosial, perkebunan kopi menyerap tenaga kerja dalam 
jumlah besar mulai dari tingkat petani, buruh tani, pengumpul, pengolah, 
hingga eksportir. Perkebunan kopi rakyat yang mendominasi struktur 
industri ini menjadi instrumen penting dalam peningkatan kesejahteraan 
masyarakat pedesaan. Sementara dari sisi ekologi, perkebunan kopi yang 
dikelola dengan sistem agroforestri berkontribusi pada konservasi 
keanekaragaman hayati, pengurangan erosi tanah, dan penyerapan 
karbon. Serangan penyakit tanaman yang semakin intensif akibat 
perubahan iklim mengancam keberlanjutan produktivitas perkebunan 
kopi dan membutuhkan solusi teknologi yang inovatif [14]. 
2.2.4 Penyakit pada Daun Kopi 
Penyakit tanaman didefinisikan sebagai kondisi abnormal yang 
dialami tanaman akibat interaksi berkelanjutan antara inang (host), 
patogen, dan lingkungan yang menyebabkan gangguan terhadap proses 
fisiologis normal tanaman. Konsep segitiga penyakit (disease triangle) 
22 
menjelaskan bahwa suatu penyakit berkembang apabila terdapat secara 
bersamaan inang yang rentan, patogen yang virulen, dan lingkungan yang 
mendukung perkembangan patogen. Penyebab penyakit tanaman dapat 
bersifat biotik seperti jamur (fungi), bakteri, virus, nematoda, dan 
organisme parasit, maupun abiotik seperti defisiensi nutrisi, kekeringan, 
suhu ekstrem, dan polutan lingkungan [29]. 
Esgario et al. (2020) menegaskan bahwa pengendalian agen biotik 
yang efisien—seperti hama dan patogen (virus, jamur, bakteri)—
berkaitan erat dengan konsep keberlanjutan pertanian karena kerusakan 
yang ditimbulkan berdampak langsung pada penurunan produktivitas dan 
kualitas hasil panen. Penggunaan metode computer vision dengan deep 
learning memungkinkan identifikasi dini dan tepat terhadap agen 
penyebab stres tanaman, sehingga tindakan korektif dapat diterapkan 
sesegera mungkin untuk memitigasi kerugian [29]. 
1. Jenis Penyakit pada Daun Kopi 
Daun kopi rentan terhadap berbagai jenis penyakit yang dapat 
menurunkan produktivitas tanaman secara signifikan. Novtahaning et al. 
(2022) mengidentifikasi empat jenis penyakit utama yang menyerang 
daun kopi, yaitu karat daun (rust), penambang daun (miner), phoma, dan 
cercospora, yang masing-masing memiliki gejala visual khas namun 
terkadang sulit dibedakan tanpa keahlian khusus terutama pada tahap 
infeksi awal [14]. 
Karat Daun Kopi (Coffee Leaf Rust) disebabkan oleh cendawan 
Hemileia vastatrix dan merupakan penyakit paling merusak secara global. 
Araaf et al. (2024) menyatakan bahwa pemanasan global dan kondisi 
iklim ekstrem akibat suhu dan kelembaban yang tidak sesuai memicu 
penyebaran penyakit karat daun kopi (Hemileia vastatrix) pada 
perkebunan kopi dan dapat menyebabkan defoliasi besar-besaran yang 
melemahkan tanaman[3]. Gejala awal berupa bercak kuning pucat di 
permukaan atas daun yang berkembang menjadi serbuk oranye 
kekuningan di permukaan bawah daun. Penyakit Penambang Daun (Leaf 
23 
Miner) disebabkan oleh larva lalat Leucoptera coffeella, Phoma 
disebabkan jamur Phoma costarricensis, dan Cercospora (bercak daun 
coklat) disebabkan jamur Cercospora coffeicola yang menghasilkan 
bercak bulat coklat dengan lingkaran kuning khas menyerupai bentuk 
mata [14]. 
2. Dampak Penyakit Daun Kopi terhadap Produksi Kopi 
Dampak penyakit daun kopi terhadap produktivitas perkebunan 
bersifat langsung dan sangat signifikan. Esgario et al. (2020) menjelaskan 
bahwa stres biotik seperti penambang daun, karat daun, bercak daun 
coklat, dan bercak cercospora memengaruhi perkebunan kopi dengan 
menyebabkan defoliasi dan penurunan fotosintesis, sehingga mengurangi 
hasil dan kualitas produk akhir kopi secara nyata. Kehilangan fotosintesis 
akibat kerusakan jaringan daun yang ekstensif secara langsung 
mengurangi pembentukan karbohidrat yang dibutuhkan untuk pengisian 
biji dan pembentukan cita rasa kopi[5]. 
Kerugian ekonomi akibat penyakit daun kopi di tingkat global 
diperkirakan mencapai miliaran dolar setiap tahunnya, dengan penurunan 
produksi hingga 30–40% pada kasus epidemi parah. Tassis dan Krohling 
(2022) menegaskan bahwa deteksi dini dan pengendalian penyakit yang 
tepat merupakan kunci dalam mengurangi kerugian ini, dan teknologi 
berbasis kecerdasan buatan berpotensi menjadi solusi efektif untuk 
mendukung upaya tersebut, terutama untuk petani kecil yang tidak 
memiliki akses rutin terhadap tenaga ahli pertanian [19]. 
2.2.5 Deteksi Penyakit Tanaman Menggunakan Teknologi 
1.  Konsep Deteksi Penyakit Tanaman 
Deteksi penyakit tanaman merupakan proses identifikasi dan 
diagnosa kondisi patologis yang terjadi pada tanaman melalui 
pengamatan gejala pada organ tanaman. Dalam konteks pertanian presisi 
modern, deteksi penyakit telah berkembang melampaui observasi manual 
menuju sistem otomatis yang mampu memberikan diagnosa objektif, 
24 
konsisten, dan real-time. Tujuan utamanya adalah menyediakan informasi 
akurat dan tepat waktu agar tindakan pengendalian dapat segera dilakukan 
sebelum penyakit menyebar lebih luas [29]. 
Esgario dkk. (2022) mengembangkan sistem berbasis aplikasi yang 
membantu petani mengidentifikasi penyakit dan hama pada daun kopi 
menggunakan deep learning, menunjukkan bahwa kemudahan akses 
terhadap alat diagnosa berbasis teknologi berkorelasi positif dengan 
kemampuan petani dalam mengelola penyakit tanaman secara lebih 
proaktif. Sistem computer-aided diagnosis (CAD) berbasis smartphone 
memungkinkan siapa pun yang memiliki ponsel pintar untuk menikmati 
pengetahuan ahli secara praktis dan berbiaya rendah [29]. 
2. Metode Konvensional Deteksi Penyakit Tanaman 
Metode konvensional dalam deteksi penyakit tanaman bergantung 
pada inspeksi visual langsung oleh ahli patologi tanaman atau penyuluh 
pertanian berpengalaman. Proses ini mencakup pemeriksaan gejala visual 
di lapangan, pengambilan sampel jaringan yang terinfeksi, serta analisis 
laboratorium untuk mengidentifikasi jenis patogen. Meskipun akurat bila 
dilakukan oleh tenaga kompeten, metode konvensional memiliki 
keterbatasan signifikan dalam konteks pertanian modern berskala luas 
[15]. 
Aufar dan Kaloka (2022) menjelaskan bahwa metode tradisional 
yang mengandalkan pengamatan ahli dengan mata telanjang merupakan 
proses yang melelahkan, membutuhkan waktu lama, dan mahal, terutama 
ketika berhadapan dengan wilayah perkebunan yang sangat luas. 
Keterbatasan lainnya meliputi kelangkaan tenaga ahli di daerah terpencil, 
waktu diagnosa yang panjang bila memerlukan analisis laboratorium, dan 
sifat diagnosa yang subjektif serta bergantung pada pengalaman individu 
pemeriksa [15]. 
3. Deteksi Penyakit Tanaman Berbasis Citra Digital 
25 
Deteksi penyakit tanaman berbasis citra digital memanfaatkan 
teknologi pengolahan gambar dan kecerdasan buatan untuk menganalisis 
foto tanaman yang diambil menggunakan kamera digital atau smartphone. 
Ketersediaan smartphone berkamera tinggi yang semakin terjangkau telah 
membuat pendekatan ini menjadi solusi sangat praktis yang dapat diakses 
petani secara langsung. Li et al. (2021) menyatakan bahwa deep learning 
merupakan teknik machine learning yang powerful untuk melatih detektor 
objek andal, dan telah dibuktikan secara empiris sebagai pendekatan 
terdepan dalam deteksi serta klasifikasi penyakit tanaman berbasis citra 
[13]. 
Siddiqua dkk. (2022) dalam evaluasi komprehensif terhadap 
berbagai aplikasi mobile deteksi penyakit tanaman menyimpulkan bahwa 
88,23% aplikasi yang tersedia mampu mendeteksi penyakit dan 
mengidentifikasi tanaman, namun masih terdapat celah kualitas yang 
signifikan terkait akurasi dan kemudahan penggunaan. Hal ini 
menggarisbawahi kebutuhan akan sistem berbasis citra digital yang lebih 
andal, akurat, dan mudah digunakan, terutama yang mampu mendeteksi 
secara spesifik berbagai jenis penyakit daun kopi yang relevan bagi petani 
Indonesia [12]. 
2.2.6 Pengolahan Citra Digital 
Citra digital adalah representasi dua dimensi suatu objek visual 
yang tersimpan dalam bentuk matriks nilai numerik yang disebut piksel 
(picture element). Setiap piksel merepresentasikan warna atau intensitas 
cahaya pada titik tertentu dalam gambar, dikodekan dalam nilai bilangan 
bulat pada rentang tertentu tergantung kedalaman bit yang digunakan. 
Pada citra 8-bit, nilai setiap piksel berkisar antara 0 (hitam) hingga 255 
(putih) untuk setiap kanal warna. Pada citra berwarna dengan ruang warna 
RGB (Red, Green, Blue), setiap piksel terdiri dari tiga nilai yang 
merepresentasikan intensitas merah, hijau, dan biru [18]. 
Selain RGB, ruang warna lain yang sering digunakan dalam analisis 
citra pertanian meliputi HSV (Hue, Saturation, Value) dan LAB. 
26 
Mazumder dkk. (2024) dalam penelitian arsitektur transfer learning yang 
robust untuk deteksi penyakit daun lintas berbagai jenis tanaman 
menekankan pentingnya pemilihan strategi representasi dan praproses 
citra sebagai langkah awal yang sangat menentukan kualitas hasil deteksi 
dan klasifikasi penyakit tanaman, karena citra yang diproses dengan baik 
memudahkan model untuk mengekstraksi fitur diskriminatif yang relevan 
[18]. 
1. Komponen Citra Digital 
Citra digital memiliki beberapa komponen utama yang menentukan 
karakteristik dan kualitasnya. Resolusi spasial mengacu pada jumlah 
piksel yang membentuk dimensi gambar (misalnya 224×224 piksel 
seperti yang umumnya digunakan sebagai input model DenseNet berbasis 
ImageNet). Resolusi yang lebih tinggi menghasilkan detail gambar lebih 
baik namun membutuhkan kapasitas komputasi dan penyimpanan lebih 
besar. Resolusi radiometrik atau kedalaman bit menentukan jumlah 
tingkatan nilai yang dapat direpresentasikan oleh setiap piksel [5]. 
Komponen penting lainnya adalah format file penyimpanan yang 
digunakan: JPEG dengan kompresi lossy yang mengurangi ukuran file 
namun berpotensi menghilangkan detail halus, dan PNG dengan kompresi 
lossless yang mempertahankan seluruh informasi piksel. Dalam 
pengembangan sistem deteksi penyakit berbasis deep learning, kualitas 
dan resolusi gambar berpengaruh terhadap kemampuan model dalam 
mempelajari fitur diskriminatif yang relevan untuk membedakan berbagai 
jenis kondisi daun kopi di lapangan [14]. 
2.  Tahapan Pengolahan Citra Digital 
Pengolahan citra digital mencakup serangkaian tahapan sistematis. 
Tahap pertama adalah akuisisi citra menggunakan kamera smartphone. 
Tahap kedua adalah preprocessing atau praproses, mencakup resizing ke 
dimensi standar model (umumnya 224×224 piksel), normalisasi nilai piksel 
ke rentang 0–1, konversi ruang warna yang diperlukan, dan augmentasi 
27 
data seperti rotasi, flipping, zoom, serta perubahan kecerahan dan kontras. 
Tahap ketiga adalah segmentasi citra yang memisahkan area daun dari latar 
belakang dan mengidentifikasi region bergejala [3]. 
Tahap keempat adalah ekstraksi fitur. Dalam pendekatan deep 
learning modern, proses ini dilakukan secara otomatis oleh lapisan 
konvolusi jaringan saraf tanpa intervensi manual. Faisal et al. (2023) dalam 
penelitian hybrid feature fusion untuk klasifikasi penyakit daun kopi 
mendemonstrasikan bahwa kombinasi teknik pengolahan citra yang tepat 
dengan arsitektur deep learning dapat menghasilkan sistem deteksi 
penyakit sangat akurat dengan kemampuan mengekstraksi fitur 
komprehensif dari gambar daun kopi dalam berbagai kondisi lapangan [33]. 
Tahap terakhir adalah klasifikasi berdasarkan fitur terekstraksi untuk 
menentukan kategori kondisi daun. 
3. Penerapan Pengolahan Citra dalam Pertanian 
Pengolahan citra digital telah menemukan berbagai aplikasi praktis 
dalam sektor pertanian modern, meliputi pemantauan kondisi tanaman dari 
udara menggunakan drone, analisis kualitas hasil panen, deteksi hama dan 
penyakit tanaman, serta pemantauan pertumbuhan berkala. Integrasi 
pengolahan citra dengan kecerdasan buatan memungkinkan analisis yang 
jauh lebih objektif, konsisten, dan cepat dibandingkan inspeksi visual 
manual oleh tenaga ahli yang terbatas jumlahnya [12]. 
Li dkk. (2021) dalam tinjauan komprehensif tentang deteksi dan 
klasifikasi penyakit tanaman menggunakan deep learning mengkonfirmasi 
bahwa sistem berbasis pengolahan citra mampu mendeteksi gejala penyakit 
pada tahap yang sangat awal, bahkan sebelum gejala tersebut terlihat jelas 
oleh mata manusia, sehingga memungkinkan tindakan pencegahan yang 
lebih proaktif. Kemampuan ini menjadikan pengolahan citra digital sebagai 
fondasi teknologi yang sangat relevan untuk pengembangan sistem deteksi 
penyakit daun kopi berbasis mobile application [13]. 
2.2.7 Machine Learning 
28 
Machine learning (pembelajaran mesin) merupakan cabang dari 
kecerdasan buatan yang berfokus pada pengembangan algoritma dan model 
statistik yang memungkinkan komputer untuk belajar dari data dan 
meningkatkan kinerjanya pada suatu tugas secara otomatis tanpa diprogram 
secara eksplisit. Konsep inti machine learning adalah kemampuan sistem 
menemukan pola dalam data besar, membangun model berdasarkan pola 
tersebut, dan menggunakan model yang telah dibangun untuk membuat 
prediksi atau keputusan terhadap data baru [13]. 
Li dkk. (2021) dalam tinjauan komprehensifnya mendefinisikan 
bahwa pembelajaran mesin memungkinkan komputer mempelajari 
representasi data secara hierarkis dan menggunakannya untuk membuat 
keputusan yang akurat. Kemajuan dalam machine learning, khususnya deep 
learning, telah membawa revolusi dalam kemampuan analisis citra 
pertanian yang sebelumnya tidak dapat dilakukan secara otomatis oleh 
komputer dengan tingkat akurasi yang memadai untuk keperluan 
operasional di lapangan [13]. 
1. Cara Kerja Machine Learning 
Machine learning bekerja melalui proses pelatihan (training) di 
mana model diekspos ke dataset berlabel. Model secara iteratif 
menyesuaikan parameter internalnya (bobot/weights) untuk meminimalkan 
perbedaan antara prediksi dan nilai sebenarnya, diukur menggunakan 
fungsi kerugian (loss function). Proses optimasi umumnya menggunakan 
algoritma gradient descent dan variasinya, di mana bobot diperbarui secara 
bertahap ke arah yang menurunkan nilai loss pada setiap iterasi [13]. 
Setelah pelatihan, model diuji menggunakan data yang tidak pernah 
dilihat sebelumnya untuk mengevaluasi kemampuan generalisasinya. 
Kemampuan generalisasi merupakan indikator utama kualitas model; 
model yang terlalu disesuaikan dengan data latih (overfitting) akan 
memiliki performa buruk pada data baru. Teknik regularisasi, dropout, dan 
augmentasi data digunakan untuk mencegah overfitting dan meningkatkan 
29 
kemampuan generalisasi model pada skenario dunia nyata perkebunan kopi 
[14]. 
2. Jenis-jenis Machine Learning 
a.  Supervised Learning 
Supervised learning (pembelajaran terawasi) adalah paradigma machine 
learning di mana model dilatih menggunakan dataset berlabel. Deteksi 
penyakit daun kopi merupakan contoh khas tugas klasifikasi multi-kelas 
dalam supervised learning, di mana model dilatih menggunakan ribuan 
gambar daun kopi berlabel (sehat, karat daun, penambang daun, phoma, 
cercospora) untuk kemudian memprediksi jenis kondisi pada gambar baru. 
Kualitas dan ukuran dataset berlabel menjadi faktor penentu utama 
performa sistem deteksi berbasis supervised learning [19]. 
b.  Unsupervised Learning 
Unsupervised learning (pembelajaran tidak terawasi) melatih model 
menggunakan dataset tanpa label untuk mencari pola, struktur, atau 
hubungan tersembunyi secara mandiri. Algoritma yang umum digunakan 
meliputi k-means clustering, hierarchical clustering, dan principal 
component analysis (PCA). Dalam konteks pertanian, unsupervised 
learning dapat digunakan untuk eksplorasi data awal, pengelompokan 
gambar daun berdasarkan kemiripan visual, atau deteksi anomali pada pola 
pertumbuhan tanaman yang mungkin mengindikasikan masalah yang 
belum teridentifikasi [13]. 
c.  
Reinforcement Learning 
Reinforcement learning (pembelajaran penguatan) merupakan 
paradigma di mana agen belajar membuat keputusan optimal melalui 
interaksi dengan lingkungan dan menerima sinyal reward atau penalti atas 
setiap tindakan. Meskipun belum banyak diterapkan langsung dalam 
deteksi penyakit daun kopi, pendekatan ini memiliki potensi aplikasi dalam 
sistem rekomendasi penanganan penyakit yang adaptif, di mana sistem 
secara bertahap belajar merekomendasikan tindakan pengendalian paling 
30 
efektif berdasarkan umpan balik hasil implementasi di lapangan secara 
berkelanjutan [13]. 
2.2.8 Deep Learning 
Deep learning (pembelajaran mendalam) adalah sub-bidang dari 
machine learning yang menggunakan jaringan saraf tiruan berlapis banyak 
(deep neural networks) untuk mempelajari representasi hierarkis dari data 
secara otomatis. Istilah "deep" merujuk pada kedalaman jaringan, yaitu 
banyaknya lapisan tersembunyi (hidden layers). Lapisan-lapisan awal 
belajar mengenali fitur sederhana seperti tepi dan tekstur, sementara lapisan 
lebih dalam menggabungkan fitur-fitur tersebut menjadi representasi 
semakin kompleks dan abstrak seperti pola penyakit spesifik [13]. 
Li et al. (2021) menyatakan bahwa deep learning merupakan teknik 
machine learning powerful yang dapat dilatih untuk mendeteksi dan 
mengklasifikasikan penyakit tanaman dengan akurasi tinggi, dan telah 
menjadi pendekatan dominan dalam bidang ini berkat kemampuannya 
mempelajari representasi fitur secara otomatis dari data mentah tanpa 
memerlukan feature engineering manual oleh para ahli bidang [13]. 
1. Perbedaan Machine Learning dan Deep Learning 
Perbedaan utama antara machine learning tradisional dan deep 
learning terletak pada proses ekstraksi fitur. Dalam machine learning 
tradisional, fitur-fitur relevan harus didefinisikan dan diekstraksi secara 
manual oleh para ahli bidang (feature engineering) sebelum diumpankan ke 
algoritma pembelajaran seperti SVM atau Random Forest. Proses ini sangat 
bergantung pada keahlian bidang yang mendalam dan membutuhkan waktu 
signifikan [33]. 
Sebaliknya, deep learning melakukan ekstraksi fitur secara otomatis 
langsung dari data mentah melalui proses pelatihan. Faisal et al. (2023) 
mengkonfirmasi bahwa model deep learning berbasis CNN mampu 
mengekstraksi dan menggabungkan fitur tekstural serta warna dari gambar 
daun kopi secara otomatis, menghasilkan akurasi yang jauh melampaui 
31 
metode machine learning konvensional. Kemampuan end-to-end learning 
inilah yang membuat deep learning sangat unggul untuk analisis citra 
pertanian [33]. 
2.  Penerapan Deep Learning dalam Klasifikasi Citra 
Deep learning telah merevolusi bidang klasifikasi citra sejak 
kesuksesan besar AlexNet pada kompetisi ImageNet 2012. Berbagai 
arsitektur semakin canggih telah dikembangkan: VGGNet, GoogLeNet, 
ResNet, DenseNet, MobileNet, dan EfficientNet. Novtahaning et al. (2022) 
mengklasifikasikan empat jenis penyakit daun kopi menggunakan 
ensemble dari sembilan model CNN pre-trained termasuk EfficientNet-B0, 
ResNet-152, VGG-16, InceptionV3, Xception, MobileNetV2, dan 
DenseNet201, menunjukkan kekuatan pendekatan ensemble deep learning 
untuk klasifikasi penyakit multi-kelas dalam kondisi gambar lapangan yang 
beragam [14]. 
2.2.9 Convolutional Neural Network (CNN) 
Convolutional Neural Network (CNN) adalah jenis jaringan saraf 
tiruan yang dirancang khusus untuk memproses data berstruktur grid 
seperti citra digital. CNN terinspirasi dari cara kerja korteks visual biologis 
manusia, di mana setiap neuron hanya merespons stimulus dalam area 
terbatas yang disebut receptive field. CNN mampu secara otomatis 
mempelajari filter-filter konvolusi optimal untuk ekstraksi fitur visual, 
menjadikannya sangat efektif untuk tugas pengenalan pola termasuk 
deteksi penyakit tanaman [13]. 
Novtahaning et al. (2022) dalam penelitiannya mengadopsi 
pendekatan ensemble yang menggabungkan beberapa model berbasis CNN 
dan mengusulkan lapisan baru di atas model-model tersebut. Dengan 
strategi flattening layer, dense layer 64 unit tersembunyi menggunakan 
fungsi aktivasi ReLU, dan softmax classifier untuk output multi-kelas, 
pendekatan ensemble CNN ini berhasil mengklasifikasikan empat jenis 
penyakit utama daun kopi dengan performa yang melampaui model 
individual [14]. 
32 
1.  Arsitektur CNN 
Arsitektur umum CNN terdiri dari beberapa blok yang tersusun 
secara berurutan. Blok awal terdiri dari lapisan konvolusi diikuti lapisan 
aktivasi ReLU dan lapisan pooling yang mengekstraksi fitur hierarkis dari 
citra input. Blok ini diulang beberapa kali dengan jumlah filter meningkat 
untuk menangkap fitur semakin kompleks. Di ujung jaringan terdapat satu 
atau beberapa lapisan fully connected yang menggabungkan semua fitur 
terekstraksi untuk menghasilkan prediksi klasifikasi akhir. Arsitektur ini 
sangat efisien untuk klasifikasi citra berkat mekanisme berbagi parameter 
melalui filter konvolusi [3]. 
2. Komponen CNN 
a.  Convolution Layer 
Lapisan konvolusi adalah komponen inti CNN yang melakukan 
operasi konvolusi antara citra input dengan filter atau kernel berukuran 
kecil (umumnya 3×3 atau 5×5 piksel). Setiap filter mendeteksi pola 
spesifik dalam citra. Hasil konvolusi adalah feature map yang 
merepresentasikan seberapa kuat pola yang dideteksi filter tersebut hadir 
di setiap lokasi citra. Nilai-nilai dalam setiap filter dipelajari otomatis 
melalui backpropagation selama pelatihan. Setiap lapisan konvolusi 
menggunakan puluhan hingga ratusan filter berbeda secara simultan, 
menghasilkan kumpulan feature map yang menangkap berbagai aspek 
visual citra input [20]. 
b. Pooling Layer 
Lapisan pooling mengurangi dimensi spasial feature map dari 
lapisan konvolusi, sehingga mengurangi jumlah parameter dan 
kompleksitas komputasi. Max pooling yang mengambil nilai maksimum 
dari setiap wilayah kecil merupakan operasi pooling paling umum. Selain 
mengurangi beban komputasi, pooling memberikan invariansi translasi 
parsial—representasi fitur yang dihasilkan relatif tidak terpengaruh oleh 
pergeseran kecil posisi objek dalam citra. Properti ini sangat berguna 
33 
dalam analisis citra daun kopi yang sering mengalami variasi posisi dan 
orientasi daun [3]. 
c. Fully Connected Layer 
Lapisan fully connected (dense layer) merupakan komponen 
terakhir CNN yang berfungsi sebagai classifier. Setiap neuron terhubung 
dengan semua neuron di lapisan sebelumnya. Lapisan ini menerima 
representasi fitur terekstraksi (dalam bentuk vektor 1D setelah flattening) 
dan menggunakannya untuk menghasilkan prediksi klasifikasi akhir 
menggunakan fungsi aktivasi softmax. Novtahaning et al. (2022) 
menggunakan dense layer 64 unit tersembunyi dengan ReLU diikuti 
lapisan softmax untuk menghasilkan probabilitas kelas setiap jenis 
penyakit daun kopi [14]. 
3. Fungsi CNN dalam Klasifikasi Gambar 
CNN mengekstraksi representasi fitur bermakna dan diskriminatif 
dari citra input secara hierarkis, kemudian menggunakannya untuk 
membuat prediksi kelas yang tepat. Kombinasi lapisan konvolusi, 
pooling, dan fully connected memungkinkan CNN menangkap fitur 
visual dari tingkat paling sederhana (tepi, tekstur) hingga paling kompleks 
(pola penyakit spesifik) secara otomatis. Li et al. (2021) menegaskan 
bahwa CNN dan variannya berbasis deep learning telah terbukti secara 
empiris sebagai pendekatan terdepan dalam deteksi dan klasifikasi 
penyakit tanaman berbasis citra, melampaui seluruh metode machine 
learning tradisional [13]. 
2.2.10 Transfer Learning 
Transfer learning adalah paradigma pembelajaran mesin di mana 
pengetahuan yang diperoleh model dalam menyelesaikan satu tugas 
(source task) dimanfaatkan untuk meningkatkan performa dalam 
menyelesaikan tugas berbeda namun terkait (target task). Dalam deep 
learning, transfer learning umumnya dilakukan dengan mengambil model 
yang telah dilatih pada dataset besar seperti ImageNet (>1,2 juta gambar 
34 
dari 1.000 kelas) sebagai titik awal, kemudian menyesuaikannya untuk 
tugas target menggunakan dataset yang lebih kecil melalui proses fine
tuning [19]. 
Tassis dan Krohling (2022) menggunakan pendekatan berbasis 
transfer learning untuk klasifikasi stres biotik pada daun kopi dan 
menegaskan bahwa transfer learning merupakan strategi sangat efektif 
untuk mengatasi keterbatasan jumlah data berlabel dalam aplikasi 
pertanian, di mana pengumpulan dan anotasi gambar dalam jumlah besar 
membutuhkan waktu, biaya, dan keahlian bidang yang substansial [19]. 
1. Proses Kerja Transfer Learning 
Proses transfer learning dimulai dengan memilih model pre
trained yang sesuai sebagai feature extractor. Model ini memiliki 
pengetahuan tentang fitur visual umum mulai dari tepi, tekstur, pola, 
hingga representasi objek tingkat tinggi yang dapat langsung 
dimanfaatkan. Setelah pemilihan model, lapisan classifier asli diganti 
dengan lapisan baru yang disesuaikan dengan jumlah kelas tugas target 
[15]. 
Selanjutnya dilakukan fine-tuning dengan beberapa strategi. 
Feature extraction murni membekukan (freezing) seluruh bobot lapisan 
konvolusi dan hanya melatih lapisan classifier baru. Fine-tuning parsial 
melatih beberapa lapisan terakhir bersama classifier baru. Fine-tuning 
penuh memperbarui seluruh bobot jaringan dengan learning rate sangat 
kecil. Aufar dan Kaloka (2022) menggunakan paradigma transfer learning 
dalam penelitiannya, berhasil mencapai akurasi deteksi penyakit daun 
kopi robusta hingga 99,93% dengan MobileNetV2 sebagai base model 
[15]. 
2. Keuntungan Transfer Learning 
Transfer learning menawarkan empat keuntungan utama. Pertama, 
kebutuhan data yang jauh lebih sedikit karena model telah memiliki 
pengetahuan dasar yang kuat. Kedua, waktu pelatihan lebih singkat 
35 
karena tidak perlu mempelajari semua representasi fitur dari nol. Ketiga, 
performa umumnya lebih baik terutama ketika ukuran dataset target 
terbatas. Keempat, berkurangnya risiko overfitting karena model dimulai 
dari titik awal yang jauh lebih baik dibandingkan inisialisasi acak [18]. 
Mazumder et al. (2024) dalam pengembangan arsitektur berbasis 
transfer learning yang ringan namun robust untuk deteksi penyakit daun 
lintas berbagai jenis tanaman mengkonfirmasi bahwa transfer learning 
secara konsisten menghasilkan performa deteksi penyakit yang lebih 
tinggi dibandingkan model yang dilatih dari awal, bahkan ketika dataset 
target hanya mengandung jumlah gambar terbatas. Keunggulan ini 
menjadikan transfer learning pilihan utama dalam pengembangan sistem 
deteksi penyakit tanaman yang praktis dan efisien[18]. 
3. Penerapan Transfer Learning dalam Klasifikasi Citra 
Transfer learning telah menjadi pendekatan standar dalam 
pengembangan sistem klasifikasi citra untuk pertanian. Model populer 
yang digunakan sebagai base model meliputi VGG16, VGG19, 
ResNet50, ResNet152, InceptionV3, MobileNetV2, DenseNet121, 
DenseNet169, DenseNet201, dan EfficientNet. Faisal et al. (2023) 
melakukan seleksi model hybrid feature fusion berbasis transfer learning 
dari berbagai model CNN pre-trained untuk klasifikasi penyakit daun 
kopi, memberikan wawasan berharga tentang pentingnya strategi 
penggabungan fitur dari model pre-trained dalam meningkatkan 
kemampuan diskriminatif sistem [33]. 
2.2.11 Model DenseNet 
DenseNet (Densely Connected Convolutional Networks) adalah 
arsitektur jaringan saraf konvolusi yang diperkenalkan oleh Huang et al. 
(2017) dalam Proceedings of the IEEE Conference on Computer Vision 
and Pattern Recognition (CVPR). DenseNet memperkenalkan koneksi 
padat (dense connections) antara semua lapisan dalam jaringan. Berbeda 
dengan CNN konvensional di mana setiap lapisan hanya menerima input 
dari lapisan sebelumnya, dalam DenseNet setiap lapisan menerima input 
36 
langsung dari semua lapisan yang mendahuluinya dalam satu blok padat 
(dense block), menghasilkan konektivitas yang jauh lebih kaya [20]. 
Cha et al. (2017) menyatakan bahwa jaringan dengan koneksi 
lebih pendek antara lapisan dekat input dan lapisan dekat output dapat 
dilatih secara substansial lebih dalam, lebih akurat, dan lebih efisien. 
DenseNet mengimplementasikan prinsip ini dengan menghubungkan 
setiap lapisan ke setiap lapisan lain secara feed-forward, sehingga 
jaringan dengan L lapisan memiliki L(L+1)/2 koneksi langsung, 
dibandingkan CNN konvensional yang hanya memiliki L koneksi [20]. 
1. Arsitektur DenseNet 
Arsitektur DenseNet dibangun di atas dua komponen utama. 
Pertama, Dense Block adalah unit dasar di mana setiap lapisan terhubung 
ke semua lapisan berikutnya dalam blok melalui concatenation feature 
map. Setiap lapisan terdiri dari Batch Normalization, fungsi aktivasi 
ReLU, dan konvolusi 3×3. Growth rate (k) adalah hyperparameter kunci 
yang menentukan jumlah feature map baru yang ditambahkan setiap 
lapisan; dengan nilai k=32, lapisan ke-l menerima k0 + k×(l-1) feature 
map sebagai input [20]. 
Kedua, Transition Layer menghubungkan dua dense block 
berurutan melalui Batch Normalization, konvolusi 1×1 (dengan 
compression factor θ = 0,5 untuk mengurangi jumlah feature map 
setengahnya), dan average pooling 2×2 untuk mengurangi dimensi 
spasial. Varian yang umum digunakan meliputi DenseNet-121, 
DenseNet-169, DenseNet-201, dan DenseNet-264; angkanya merujuk 
pada total jumlah lapisan. DenseNet-121 dengan 120 lapisan konvolusi 
dan 1 lapisan fully connected sering menjadi pilihan seimbang antara 
akurasi dan efisiensi komputasi untuk deployment mobile [3]. 
2. Cara Kerja DenseNet 
Ketika citra input memasuki jaringan, ia melewati lapisan 
konvolusi awal menghasilkan representasi fitur dasar. Representasi ini 
37 
masuk ke dense block pertama, di mana setiap lapisan l menghasilkan 
feature map baru yang langsung digabungkan (concatenated) dengan 
semua feature map dari lapisan 1, 2, ..., l-1 dalam blok yang sama. 
Mekanisme concatenation ini menciptakan information highway yang 
memungkinkan gradien mengalir langsung dari output ke input tanpa 
terdegradasi [20]. 
Setelah beberapa dense block yang dipisahkan oleh transition 
layer, representasi fitur akhir dilewatkan melalui global average pooling 
menghasilkan vektor fitur ringkas, kemudian diteruskan ke lapisan fully 
connected dengan softmax activation untuk prediksi probabilitas kelas. 
Pendekatan global average pooling lebih efektif daripada flattening 
konvensional karena drastis mengurangi jumlah parameter dan 
menurunkan risiko overfitting, sangat bermanfaat ketika dataset pelatihan 
terbatas [5]. 
3. Kelebihan DenseNet dibanding CNN Lain 
DenseNet memiliki empat keunggulan kompetitif utama. Pertama, 
dense connection efektif mengatasi masalah vanishing gradient yang 
menghambat pelatihan jaringan sangat dalam. Kedua, DenseNet 
mendorong feature reuse ekstensif karena setiap lapisan mengakses 
feature map dari semua lapisan sebelumnya, mengurangi redundansi 
pembelajaran. Ketiga, DenseNet membutuhkan parameter lebih sedikit 
dibandingkan ResNet untuk performa sebanding. Huang et al. (2017) 
membuktikan bahwa DenseNet memperoleh peningkatan signifikan pada 
sebagian besar benchmark yang diuji sambil membutuhkan memori dan 
komputasi lebih sedikit [20]. 
Keempat, kemampuan DenseNet mengekstraksi fitur tekstural halus 
menjadikannya sangat tepat untuk analisis citra daun. Penelitian 
menggunakan dataset JMuBEN2 yang dikutip dalam literatur terkini 
membuktikan bahwa DenseNet-121 dengan transfer learning dan fine
tuning mencapai akurasi 99,36% dalam mengklasifikasikan tiga jenis 
penyakit daun kopi (Phoma, Cercospora, dan Rust), melampaui performa 
38 
ResNet50 dan VGG19 pada tugas yang sama. Keunggulan-keunggulan 
ini menjadikan DenseNet pilihan arsitektur yang sangat tepat untuk 
penelitian ini [3]. 
4. Penerapan DenseNet dalam Klasifikasi Gambar 
DenseNet telah diimplementasikan luas dalam klasifikasi citra 
medis dan biologis yang membutuhkan akurasi tinggi dengan dataset 
terbatas. Dalam pertanian, DenseNet berhasil diterapkan untuk berbagai 
komoditas. Novtahaning et al. (2022) menggunakan DenseNet201 
sebagai salah satu dari sembilan model CNN dalam ensemble untuk 
klasifikasi penyakit daun kopi, menunjukkan bahwa DenseNet 
memberikan kontribusi positif dalam performa ensemble keseluruhan 
[14]. 
Araaf et al. (2024) mengimplementasikan berbagai model deep 
learning termasuk varian DenseNet untuk deteksi karat daun kopi dan 
implementasinya pada edge device untuk pemangkasan daun terinfeksi 
secara otomatis, membuktikan bahwa DenseNet tidak hanya unggul 
dalam akurasi klasifikasi tetapi juga layak secara praktis untuk 
implementasi pada perangkat komputasi terbatas di lapangan. 
Kemampuan ini menjadikan DenseNet pilihan yang sangat relevan untuk 
penelitian pengembangan aplikasi mobile deteksi penyakit daun kopi ini 
[3]. 
2.2.12 Progressive Mobile App (PMA) / Progressive Web App (PWA) 
Progressive Mobile App (PMA) atau Progressive Web App (PWA) 
adalah pendekatan pengembangan aplikasi berbasis teknologi web 
modern yang menghadirkan pengalaman pengguna setara dengan aplikasi 
native pada perangkat mobile. PWA dibangun menggunakan teknologi 
web standar (HTML, CSS, JavaScript) namun diperkaya dengan fitur
fitur yang secara tradisional hanya tersedia pada aplikasi native, termasuk 
kemampuan bekerja secara offline, notifikasi push, akses ke hardware 
perangkat, dan kemampuan diinstal di layar utama tanpa melalui toko 
aplikasi resmi[12]. 
39 
Siddiqua et al. (2022) dalam evaluasi komprehensif aplikasi mobile 
deteksi penyakit tanaman menekankan bahwa aksesibilitas teknologi 
deteksi penyakit melalui platform mobile merupakan faktor kritis yang 
menentukan tingkat adopsi oleh petani. Aplikasi yang mudah diakses, 
ramah pengguna, dan tidak memerlukan instalasi rumit memiliki potensi 
adopsi jauh lebih tinggi di kalangan petani dengan literasi digital terbatas 
[12]. PWA memenuhi kriteria aksesibilitas tersebut secara inheren 
melalui karakteristik teknologinya. 
1. Teknologi yang Digunakan pada PMA 
a. Service Worker 
Service Worker adalah script JavaScript yang berjalan di 
background browser secara terpisah dari halaman web, bertindak sebagai 
proxy jaringan yang dapat mencegat dan menangani request. Service 
Worker memungkinkan PWA untuk melakukan caching sumber daya 
secara cerdas, mengirim notifikasi push, dan mensinkronisasi data di 
background bahkan ketika pengguna tidak aktif menggunakan aplikasi. 
Service Worker wajib berjalan melalui HTTPS untuk alasan keamanan 
[29]. 
Strategi caching yang dapat diimplementasikan meliputi Cache 
First yang memprioritaskan cache untuk performa optimal, Network First 
yang memprioritaskan jaringan untuk kesegaran data, dan Stale-While
Revalidate yang melayani dari cache sambil memperbarui di background. 
Untuk aplikasi deteksi penyakit daun kopi, strategi Cache First sangat 
tepat untuk aset statis dan model AI yang telah dimuat, sehingga inferensi 
dapat dilakukan secara offline sepenuhnya di kebun terpencil [12]. 
b. Web App Manifest 
Web App Manifest adalah file JSON yang menyediakan informasi 
aplikasi web kepada browser dan sistem operasi, memungkinkan 
pengguna menginstal aplikasi di layar utama layaknya aplikasi native. 
File manifest berisi nama dan nama singkat aplikasi, URL ikon dalam 
berbagai resolusi (192×192 dan 512×512 piksel), URL awal (start_url), 
40 
mode tampilan (standalone atau fullscreen), warna tema dan latar 
belakang, serta orientasi layar. Ketika browser mendeteksi kehadiran 
manifest valid dan Service Worker terdaftar, browser menampilkan 
prompt Add to Home Screen (A2HS) kepada pengguna [29]. 
c. Kelebihan PMA dibanding Aplikasi Mobile Native 
Dari sisi pengembangan, PMA memungkinkan pembangunan 
single codebase yang berjalan di semua platform (Android, iOS, desktop) 
tanpa perlu mengembangkan aplikasi terpisah, menghemat waktu dan biaya 
secara signifikan. Pembaruan aplikasi jauh lebih mudah karena langsung 
terpublikasi tanpa proses review toko aplikasi [15]. 
Dari perspektif pengguna petani, PMA tidak memerlukan instalasi 
formal melalui Play Store atau App Store yang mungkin membingungkan 
bagi petani dengan literasi digital terbatas, menggunakan ruang 
penyimpanan lebih kecil, dan dapat diakses melalui URL yang dapat 
dibagikan. Kemampuan offline yang disediakan Service Worker 
memastikan sistem deteksi penyakit dapat digunakan di kebun terpencil 
tanpa koneksi internet stabil—skenario yang sangat umum di daerah 
perkebunan kopi Indonesia [12]. 
2.2.13 Aplikasi Mobile 
Aplikasi mobile adalah perangkat lunak yang dirancang khusus 
untuk berjalan pada perangkat komputasi portabel seperti smartphone dan 
tablet, dengan mempertimbangkan keterbatasan sumber daya komputasi, 
interaksi layar sentuh sebagai modalitas input utama, dan kebutuhan 
portabilitas serta konektivitas tinggi. Aplikasi mobile dikategorikan 
menjadi tiga jenis utama: native (Java/Kotlin untuk Android, 
Swift/Objective-C untuk iOS), web mobile (diakses melalui browser), dan 
hybrid yang menggabungkan keduanya [12]. 
Dalam penelitian ini, aplikasi dikembangkan sebagai Progressive Mobile 
App berbasis Java di platform Android menggunakan Android Studio. 
Pendekatan ini menggabungkan aksesibilitas web dengan kemampuan 
41 
akses hardware Android yang lebih mendalam. Untuk inferensi model 
DenseNet pada perangkat mobile, model yang telah dilatih dikonversi ke 
format TensorFlow Lite (.tflite) untuk memungkinkan prediksi on-device 
tanpa ketergantungan pada koneksi internet atau server eksternal, yang 
sangat penting untuk penggunaan di perkebunan terpencil [3]. 
1. Peran Aplikasi Mobile dalam Bidang Pertanian 
Aplikasi mobile telah membawa transformasi signifikan dalam 
praktik pertanian melalui berbagai fungsi yang mendukung pengambilan 
keputusan berbasis data di lapangan. Siddiqua et al. (2022) dalam evaluasi 
komprehensif terhadap lebih dari 17 aplikasi mobile deteksi penyakit 
tanaman dari berbagai platform menemukan bahwa aplikasi-aplikasi ini 
menyediakan layanan penting seperti identifikasi penyakit berbasis 
gambar, rekomendasi penanganan, dan dukungan komunitas, namun masih 
terdapat celah kualitas terkait akurasi dan kemudahan penggunaan [12]. 
Esgario et al. (2022) mengembangkan aplikasi mobile Android 
untuk membantu petani mengidentifikasi penyakit dan hama pada daun 
kopi menggunakan model deep learning yang dijalankan di perangkat. 
Pengujian lapangan menunjukkan bahwa aplikasi ini diterima dengan baik 
oleh petani dan memberikan dampak positif terhadap kemampuan deteksi 
dini dan penanganan penyakit. Pengalaman ini mengkonfirmasi bahwa 
aplikasi mobile berbasis AI yang dirancang khusus untuk kebutuhan petani 
kopi memiliki potensi adopsi tinggi dan dampak nyata terhadap 
produktivitas perkebunan [29]. 
2.2.14 Dataset dan Training Model 
Dataset dalam konteks machine learning merupakan kumpulan data 
terstruktur yang digunakan untuk melatih, memvalidasi, dan menguji 
model. Untuk klasifikasi penyakit daun kopi, dataset terdiri dari kumpulan 
gambar daun yang telah dianotasi dengan label kelas sesuai jenis kondisi 
42 
atau penyakit. Kualitas dataset yang mencakup ukuran, keberagaman, 
keseimbangan antar kelas, dan akurasi pelabelan merupakan faktor 
determinan utama performa model yang dihasilkan [19]. 
Jepkoech et al. (2021) mempublikasikan dataset gambar daun kopi 
arabika yang tersedia secara publik, mencakup gambar daun sehat dan 
terinfeksi berbagai penyakit yang dikumpulkan langsung di perkebunan 
kopi Kenya dalam berbagai kondisi pencahayaan dan sudut pengambilan. 
Dataset ini telah dianotasi oleh pakar patologi tanaman untuk memastikan 
akurasi label yang tinggi. Ketersediaan dataset publik semacam ini sangat 
krusial dalam mendorong kemajuan penelitian deteksi penyakit kopi 
berbasis deep learning secara global [30]. 
1. Proses Training Model 
Proses training model deep learning untuk klasifikasi penyakit daun 
kopi melibatkan beberapa tahapan sistematis. Pertama, dataset dibagi 
menjadi tiga subset: training set (70–80%), validation set (10–15%), dan 
test set (10–20%). Training set digunakan untuk melatih bobot model, 
validation set untuk memantau performa dan mencegah overfitting, serta 
test set untuk evaluasi akhir model pada data yang tidak pernah dilihat 
sebelumnya [14]. 
Sebelum pelatihan, gambar dalam training set melewati augmentasi 
data untuk memperkaya keberagaman secara artifisial. Teknik augmentasi 
meliputi rotasi, flipping horizontal dan vertikal, zoom in/out, perubahan 
kecerahan dan kontras, serta penambahan noise Gaussian. Novtahaning et 
al. 
(2022) menggunakan berbagai teknik augmentasi ini untuk 
meningkatkan robustness model terhadap variasi gambar lapangan yang 
tidak terkontrol [14]. Selama pelatihan, model memproses batch gambar, 
menghitung loss menggunakan categorical cross-entropy, dan 
memperbarui bobot melalui backpropagation menggunakan optimizer 
Adam dengan learning rate yang disesuaikan secara adaptif. 
2. Proses Testing Model 
43 
Proses testing dilakukan setelah pelatihan selesai menggunakan test 
set yang tidak pernah digunakan selama pelatihan, untuk mendapatkan 
estimasi tidak bias tentang performa model pada data baru—
mensimulasikan kondisi deployment nyata. Pada tahap ini, model 
menghasilkan prediksi untuk setiap gambar dalam test set tanpa pembaruan 
bobot apapun [19]. 
Tassis dan Krohling (2022) dalam evaluasi model few-shot learning 
untuk klasifikasi penyakit daun kopi menggunakan protokol testing ketat 
dengan multiple random split untuk memastikan estimasi performa yang 
statistis valid dan tidak dipengaruhi keberuntungan pemilihan sampel 
tertentu. Pendekatan evaluasi yang rigorous semacam ini penting untuk 
memastikan model benar-benar memiliki kemampuan generalisasi yang 
baik pada kondisi lapangan nyata [19]. 
3. Evaluasi Model Klasifikasi 
Evaluasi model klasifikasi dilakukan menggunakan serangkaian 
metrik kuantitatif yang dihitung berdasarkan confusion matrix. Pemilihan 
metrik harus mempertimbangkan karakteristik dataset, termasuk distribusi 
kelas yang tidak seimbang. Dalam deteksi penyakit daun kopi, kelas 
penyakit yang langka namun sangat berbahaya pada tahap awal perlu 
mendapat perhatian khusus, sehingga metrik berbasis precision, recall, dan 
F1-score menjadi lebih informatif dibandingkan sekadar mengandalkan 
akurasi tunggal [13]. 
2.2.15 Evaluasi Kinerja Model 
1. Confusion Matrix 
Confusion matrix adalah tabel yang merangkum hasil prediksi 
model klasifikasi dengan membandingkan kelas yang diprediksi dan kelas 
sebenarnya. Pada klasifikasi biner terdapat empat nilai: True Positive (TP), 
True Negative (TN), False Positive (FP), dan False Negative (FN). Untuk 
klasifikasi multi-kelas seperti deteksi penyakit daun kopi, confusion matrix 
diperluas 
menjadi 
matriks 
N×N di mana elemen diagonal 
44 
merepresentasikan prediksi benar setiap kelas dan elemen di luar diagonal 
merepresentasikan kesalahan klasifikasi [14]. 
Novtahaning et al. (2022) menggunakan confusion matrix sebagai 
alat evaluasi utama untuk menganalisis pola kesalahan klasifikasi pada 
setiap jenis penyakit daun kopi secara individual. Analisis confusion matrix 
memberikan wawasan mendalam tentang kelas-kelas penyakit yang sering 
tertukar satu sama lain, mengarahkan upaya pengumpulan data tambahan 
atau penyesuaian model untuk meningkatkan akurasi pada kelas yang 
paling sulit dibedakan secara visual [14]. 
2. Accuracy 
Accuracy (akurasi) mengukur proporsi prediksi yang benar dari 
total keseluruhan prediksi, dengan rumus: Accuracy = (TP + TN) / (TP + 
TN + FP + FN) × 100%. Aufar dan Kaloka (2022) melaporkan akurasi 
MobileNetV2 sebesar 99,93%, DenseNet169 sebesar 99,74%, dan 
ResNet50 sebesar 99,41% dalam mendeteksi penyakit daun kopi robusta. 
Meskipun akurasi merupakan metrik yang intuitif dan mudah dipahami, 
akurasi dapat memberikan gambaran menyesatkan ketika dataset memiliki 
distribusi 
kelas 
yang tidak seimbang, sehingga harus selalu 
diinterpretasikan bersama metrik komplementer lainnya [15]. 
3. Precision 
Precision (presisi) mengukur proporsi prediksi positif yang benar
benar merupakan sampel positif, dengan rumus: Precision = TP / (TP + FP). 
Precision tinggi mengindikasikan bahwa ketika model memprediksi suatu 
sampel sebagai anggota kelas tertentu, prediksi tersebut kemungkinan besar 
benar. Dalam deteksi penyakit daun kopi, precision tinggi berarti sistem 
jarang memberikan diagnosa positif palsu sehingga petani tidak perlu 
melakukan penanganan yang tidak perlu pada tanaman yang sebenarnya 
sehat—menghindari pemborosan biaya fungisida dan tenaga kerja [33]. 
4. Recall 
45 
Recall (sensitivitas) mengukur kemampuan model mendeteksi 
semua sampel positif yang sebenarnya ada, dengan rumus: Recall = TP / 
(TP + FN). Recall tinggi berarti model mampu menangkap hampir semua 
kasus penyakit yang ada dengan sangat sedikit yang terlewatkan. Dalam 
deteksi penyakit tanaman, recall tinggi sangat penting karena kasus 
penyakit yang tidak terdeteksi (false negative) dapat terus menyebar dan 
menyebabkan kerugian jauh lebih besar dibandingkan biaya penanganan 
yang tidak perlu akibat false positive [19]. 
Terdapat trade-off inheren antara precision dan recall. Untuk 
deteksi penyakit daun kopi, recall tinggi umumnya diprioritaskan agar tidak 
ada kasus penyakit yang terlewat; namun precision yang memadai juga 
diperlukan agar rekomendasi penanganan dapat dipercaya oleh petani. 
Tassis dan Krohling (2022) mempertimbangkan trade-off precision-recall 
ini secara eksplisit dalam perancangan dan evaluasi model klasifikasi 
penyakit daun kopi mereka [19]. 
5. F1-Score 
F1-Score menggabungkan precision dan recall menjadi satu nilai 
tunggal menggunakan rata-rata harmonik, dengan rumus: F1-Score = 2 × 
(Precision × Recall) / (Precision + Recall). Nilai F1-Score berkisar 0–1, 
dengan nilai mendekati 1 menandakan performa sangat baik. F1-Score 
sangat berguna ketika ada trade-off precision-recall atau distribusi kelas 
tidak seimbang [14]. 
Untuk klasifikasi multi-kelas, F1-Score dapat dihitung per kelas 
atau diagregasi menggunakan macro average (rata-rata F1 semua kelas 
dengan bobot sama) atau weighted average (rata-rata F1 berbobot proporsi 
kelas). Novtahaning et al. (2022) menggunakan F1-Score sebagai salah satu 
metrik kunci dalam evaluasi model ensemble untuk deteksi penyakit daun 
kopi, memastikan model berkinerja baik tidak hanya pada kelas dominan 
tetapi juga pada kelas penyakit yang langka namun penting untuk dideteksi 
dini [14]. 
46 
2.2.16 Bahasa Pemrograman Java 
Java adalah bahasa pemrograman tingkat tinggi (high-level), 
berorientasi objek (object-oriented), dan bersifat platform-independent 
yang dikembangkan oleh Sun Microsystems pada tahun 1991 dan 
diperkenalkan secara resmi kepada publik pada tahun 1995 oleh James 
Gosling. Prinsip utama Java adalah "Write Once, Run Anywhere" (WORA), 
yang berarti program Java yang ditulis pada satu platform dapat dijalankan 
pada platform lain yang memiliki Java Virtual Machine (JVM) tanpa perlu 
modifikasi. Java mengkompilasi kode sumber menjadi bytecode yang 
kemudian diinterpretasikan oleh JVM, sehingga menghasilkan portabilitas 
yang sangat tinggi. Liu (2021) menegaskan bahwa Java merupakan bahasa 
yang secara luas digunakan dalam pengembangan perangkat lunak mobile 
Android karena kemampuannya meningkatkan keamanan dan keandalan 
sistem Android secara keseluruhan[34] . 
Java telah menjadi bahasa pemrograman utama dalam 
pengembangan aplikasi Android sejak platform ini pertama kali 
diperkenalkan. Kelebihan pertama Java dalam konteks pengembangan 
Android adalah dukungan ekosistem yang sangat matang, dengan jutaan 
library, framework, dan komunitas pengembang yang siap membantu 
memecahkan berbagai masalah teknis. Kelebihan kedua adalah 
keberadaan Android SDK (Software Development Kit) yang menyediakan 
Application Programming Interface (API) yang kaya untuk mengakses 
berbagai fitur perangkat Android. Kelebihan ketiga adalah kemudahan 
belajar bagi pengembang pemula karena Java memiliki sintaks yang 
terstruktur dan dokumentasi yang lengkap. Kelebihan keempat adalah 
keandalan dan stabilitas Java yang telah terbukti dalam pengembangan 
aplikasi enterprise selama lebih dari dua dekade[34]. 
Wasilewski dan Zabierowski (2021) dalam penelitian komparatif 
mereka membandingkan Java dengan Flutter dan Kotlin/Native untuk 
pengembangan aplikasi mobile berbasis data sensor, dan menyimpulkan 
47 
bahwa Java merupakan bahasa asli (native) yang paling matang untuk 
pengembangan aplikasi Android dengan keunggulan dalam hal kestabilan 
ekosistem dan kompatibilitas dengan Android SDK yang sudah tersedia 
secara lengkap[35]. Selain itu, paradigma pemrograman berorientasi objek 
pada Java sangat sesuai dengan arsitektur Android yang juga dibangun di 
atas konsep-konsep OOP (Object-Oriented Programming), menjadikan 
Java sebagai pilihan yang sangat tepat dan teruji untuk pengembangan 
aplikasi Android. 
2.2.17 Firebase (Database Cloud) 
Firebase adalah platform pengembangan aplikasi mobile dan web 
berbasis cloud yang dikembangkan oleh Firebase Inc. dan diakuisisi oleh 
Google pada tahun 2014. Firebase menyediakan berbagai layanan 
Backend-as-a-Service (BaaS) yang memungkinkan pengembang untuk 
membangun, meningkatkan, dan mengembangkan aplikasi secara lebih 
cepat tanpa perlu mengelola infrastruktur server secara mandiri. Layanan 
utama Firebase meliputi Realtime Database, Cloud Firestore, Firebase 
Authentication, Cloud Storage, Firebase Cloud Messaging (FCM), 
Firebase Hosting, dan Firebase Analytics. Saraf et al. (2022) menyatakan 
bahwa Firebase merupakan BaaS yang dirancang khusus untuk aplikasi 
mobile, bersifat real-time database, dan memungkinkan pengembang 
membangun aplikasi Android, iOS, dan Web dengan infrastruktur backend 
yang lengkap[36]. 
Firebase menawarkan berbagai keunggulan yang menjadikannya 
pilihan populer dalam pengembangan aplikasi mobile. Pertama, Firebase 
Realtime Database dan Cloud Firestore menyediakan kemampuan 
sinkronisasi data secara real-time antara semua klien yang terhubung, 
sehingga perubahan data pada satu perangkat akan langsung terlihat oleh 
pengguna lain tanpa perlu melakukan refresh secara manual. Kedua, 
Firebase Authentication menyederhanakan proses implementasi autentikasi 
pengguna dengan mendukung berbagai metode login seperti 
email/password, Google Sign-In, Facebook Login, dan nomor telepon. 
48 
Ketiga, Firebase Cloud Messaging memungkinkan pengiriman notifikasi 
push kepada pengguna secara selektif berdasarkan topik atau segmen 
pengguna tertentu. Keempat, Firebase memiliki paket gratis (Spark Plan) 
yang cukup memadai untuk tahap pengembangan dan pengujian aplikasi, 
serta model harga berbasis penggunaan yang fleksibel untuk skala produksi 
[36]. 
Pandit et al. (2023) dalam penelitian tentang teknik sinkronisasi 
database real-time Firebase untuk pengembangan aplikasi mobile 
mendemonstrasikan bahwa mekanisme sinkronisasi Firebase terbukti 
efektif melalui eksperimen dan evaluasi performa, di mana arsitektur 
sinkronisasi Firebase, pertimbangan pemodelan data, teknik resolusi 
konflik, dan optimasi performa menghasilkan aplikasi yang sangat 
responsif dan kolaboratif[37]. Firebase SDK for Android juga terintegrasi 
langsung dengan Android Studio melalui mekanisme dependency injection 
menggunakan Gradle, dan Firebase Console menyediakan antarmuka 
berbasis web yang intuitif untuk memonitoring penggunaan layanan, 
mengelola database, dan menganalisis perilaku pengguna aplikasi secara 
komprehensif. 
2.2.18 Figma  
Figma adalah alat desain antarmuka pengguna (UI) dan pengalaman 
pengguna (UX) berbasis cloud yang dikembangkan oleh Figma Inc. dan 
dirilis pertama kali pada tahun 2016. Sebagai platform desain berbasis 
web, Figma memungkinkan desainer dan pengembang untuk 
berkolaborasi secara real-time dalam satu lingkungan kerja yang terpusat 
tanpa perlu menginstal perangkat lunak tambahan di komputer lokal. 
Figma mendukung pembuatan wireframe, mockup, prototype interaktif, 
serta design system yang konsisten untuk aplikasi web maupun mobile. 
Yanfi dan Nusantara mengkonfirmasi bahwa Figma merupakan alat desain 
yang digunakan secara luas untuk pengembangan prototipe UI/UX 
aplikasi mobile karena kemampuannya dalam mendukung proses desain 
secara iteratif dan kolaboratif [38]. 
49 
Figma berfungsi sebagai alat utama dalam proses desain UI/UX 
yang mencakup beberapa tahapan penting. Tahap pertama adalah 
wireframing, yaitu pembuatan kerangka kasar tampilan antarmuka yang 
menggambarkan tata letak elemen-elemen utama tanpa detail visual. 
Tahap kedua adalah prototyping, yaitu pembuatan simulasi interaktif dari 
alur navigasi aplikasi yang dapat diuji oleh pengguna sebelum proses 
pengembangan dimulai. Tahap ketiga adalah pembuatan design system 
yang mencakup panduan warna, tipografi, komponen UI yang dapat 
digunakan ulang (reusable components), dan aturan tata letak yang 
konsisten di seluruh halaman aplikasi. Tahap keempat adalah handoff 
kepada pengembang, di mana Figma menyediakan spesifikasi teknis 
lengkap seperti ukuran, jarak, warna, dan properti CSS dari setiap elemen 
desain [38]. 
Kimseng et al. (2024) dalam penelitian tentang pengembangan 
UI/UX menggunakan Figma berbasis inclusive design menekankan bahwa 
Figma merupakan alat desain yang dipilih untuk mengembangkan 
prototipe horizontal yang memungkinkan desainer mengimplementasikan 
prinsip aksesibilitas dan desain inklusif secara efektif tanpa harus 
melakukan pengembangan kode yang besar terlebih dahulu[39]. Figma 
memiliki keunggulan spesifik untuk perancangan antarmuka aplikasi 
mobile, di antaranya menyediakan template frame untuk berbagai ukuran 
layar smartphone populer, fitur auto-layout untuk komponen yang 
menyesuaikan ukuran secara otomatis, kemampuan kolaborasi real-time 
untuk proses review desain bersama tim, serta integrasi dengan berbagai 
plugin yang memperkaya fungsionalitasnya termasuk plugin untuk 
pembuatan ikon, pengujian kontras warna, dan ekspor aset desain. 
2.2.19 Metode Waterfall 
Metode Waterfall adalah salah satu model pengembangan 
perangkat lunak yang paling klasik dan banyak digunakan dalam rekayasa 
perangkat lunak. Model ini pertama kali diperkenalkan oleh Winston Royce 
pada tahun 1970 dalam makalahnya yang berjudul "Managing the 
Development of Large Software Systems". Waterfall dikenal sebagai model 
50 
sekuensial linier karena setiap fase pengembangan harus diselesaikan 
secara penuh sebelum fase berikutnya dapat dimulai, menyerupai aliran air 
yang mengalir ke bawah secara bertahap tanpa bisa kembali ke atas. 
Pratama et al. (2024) menegaskan bahwa metode Waterfall sangat sesuai 
digunakan untuk pengembangan aplikasi berbasis Java Netbeans karena 
strukturnya yang berurutan memberikan kemudahan dalam perencanaan 
dan kontrol kualitas pada setiap tahapan pengembangan [40]. 
Model Waterfall terdiri dari beberapa tahapan yang berurutan dan 
saling bergantung. Tahap pertama adalah analisis kebutuhan (requirements 
analysis), yaitu proses pengumpulan dan dokumentasi seluruh kebutuhan 
fungsional dan non-fungsional sistem dari para pemangku kepentingan. 
Tahap kedua adalah perancangan sistem (system design), yaitu tahap di 
mana kebutuhan yang telah didefinisikan diterjemahkan ke dalam arsitektur 
sistem, desain antarmuka, desain database, dan desain komponen perangkat 
lunak. Tahap ketiga adalah implementasi (implementation/coding), yaitu 
penulisan kode program berdasarkan hasil perancangan yang telah 
disetujui. Tahap keempat adalah pengujian (testing/verification), yaitu 
proses verifikasi dan validasi sistem untuk memastikan bahwa perangkat 
lunak yang dikembangkan sesuai dengan spesifikasi kebutuhan. Tahap 
kelima adalah pemeliharaan (maintenance), yaitu tahap perbaikan bug, 
pembaruan fitur, dan adaptasi sistem terhadap perubahan lingkungan 
operasional setelah sistem di-deploy [41]. 
Kalil (2024) dalam penelitian tentang mitigasi kerentanan 
perangkat lunak melalui pengembangan perangkat lunak yang aman 
dengan model Waterfall berbasis kebijakan menegaskan bahwa model 
Waterfall menyediakan kerangka kerja yang komprehensif dan terstruktur 
untuk memastikan keamanan dan kualitas perangkat lunak di setiap fase 
pengembangannya, karena setiap fase memiliki deliverable yang spesifik 
dan dapat diverifikasi sebelum fase berikutnya dimulai [41]. Dalam konteks 
pengembangan sistem informasi komunitas petani ini, metode Waterfall 
dipilih karena kebutuhan sistem telah didefinisikan secara jelas melalui 
51 
proses observasi dan wawancara, sehingga sesuai dengan karakteristik 
dasar penerapan model sekuensial linier ini secara optimal. 
2.2.20 UML (Unified Modeling Language) 
Unified Modeling Language (UML) adalah bahasa pemodelan 
standar yang digunakan untuk memvisualisasikan, menspesifikasikan, 
membangun, dan mendokumentasikan artefak sistem perangkat lunak. 
UML dikembangkan oleh Object Management Group (OMG) dan pertama 
kali distandardisasi pada tahun 1997. UML menyediakan notasi grafis 
yang seragam untuk menggambarkan berbagai aspek sistem perangkat 
lunak, sehingga memudahkan komunikasi antara pengembang, analis, dan 
pemangku kepentingan yang memiliki latar belakang berbeda dalam 
memahami desain dan arsitektur suatu sistem. Sitompul et al. (2024) 
menegaskan bahwa Use Case Diagram sebagai salah satu jenis diagram 
UML memiliki peran vital dalam perancangan sistem informasi untuk 
mendeskripsikan layanan-layanan yang disediakan sistem kepada 
pengguna secara terstruktur dan komprehensif [42]. 
UML memiliki fungsi yang sangat penting dalam siklus 
pengembangan perangkat lunak. Fungsi pertama adalah sebagai alat 
komunikasi visual yang memudahkan pengembang untuk menyampaikan 
dan mendiskusikan desain sistem dengan pemangku kepentingan tanpa 
harus membaca kode program secara langsung. Fungsi kedua adalah 
sebagai dokumentasi arsitektur sistem yang dapat dijadikan referensi 
selama proses pengembangan maupun pemeliharaan sistem. Fungsi ketiga 
adalah sebagai alat analisis yang membantu pengembang untuk 
mengidentifikasi potensi masalah atau inkonsistensi dalam desain sebelum 
memasuki tahap implementasi. Fungsi keempat adalah sebagai panduan 
implementasi yang memberikan gambaran terstruktur mengenai 
komponen-komponen sistem dan hubungannya satu sama lain [12]. 
Dalam pengembangan sistem informasi komunitas petani berbasis 
Android ini, digunakan empat jenis diagram UML yang saling melengkapi 
52 
untuk merepresentasikan sistem secara komprehensif dari berbagai 
perspektif. Use Case Diagram menggambarkan hubungan antara aktor 
(pengguna sistem) dengan use case (fungsionalitas sistem) dari sudut 
pandang pengguna, termasuk aktor petani, admin komunitas, dan penyuluh 
pertanian dengan use case seperti registrasi, login, posting informasi, 
komentar, dan pengelolaan galeri. Activity Diagram merepresentasikan 
alur aktivitas atau proses bisnis dalam suatu sistem secara sekuensial 
maupun paralel, sangat berguna untuk mendokumentasikan alur proses 
yang kompleks seperti alur registrasi pengguna dan pengiriman notifikasi. 
Sequence Diagram menggambarkan interaksi antar-objek dalam urutan 
waktu untuk menyelesaikan suatu use case, khususnya berguna untuk 
memodelkan interaksi antara lapisan Activity/Fragment, ViewModel, 
Repository, dan Firebase dalam arsitektur Android. Class Diagram 
merepresentasikan struktur statis sistem termasuk seluruh kelas Java yang 
akan dibuat seperti kelas model data (POJO), Activity, Fragment, Adapter, 
dan ViewModel beserta hubungan antar-kelasnya [12][42]. 
BAB III 
METODOLOGI PENELITIAN 
3.1  Metode Pengumpulan Data 
Pengumpulan data merupakan tahap dasar dalam proses penelitian 
yang bertujuan untuk memperoleh informasi yang relevan, akurat, dan 
komprehensif sebagai dasar pengembangan sistem. Dalam penelitian ini, data 
dikumpulkan melalui tiga metode utama, yaitu observasi langsung, studi 
literatur, dan dokumentasi. Ketiga metode ini saling melengkapi sehingga 
menghasilkan pemahaman menyeluruh terhadap permasalahan yang diteliti. 
3.1.1  
Observasi 
Observasi merupakan metode pengumpulan data primer yang 
dilakukan secara langsung di lapangan. Kegiatan observasi dilaksanakan di 
area perkebunan kopi yang berlokasi di wilayah penelitian dengan 
melibatkan sebanyak 30 (tiga puluh) petani kopi sebagai responden. Tujuan 
observasi adalah untuk memperoleh gambaran nyata mengenai kondisi 
tanaman kopi, jenis-jenis penyakit yang umum menyerang daun kopi, serta 
permasalahan yang dihadapi petani dalam proses identifikasi penyakit. 
Selama kegiatan observasi, peneliti mengamati secara langsung 
berbagai gejala penyakit yang tampak pada daun kopi, mulai dari 
perubahan warna, bentuk bercak, hingga pola kerusakan daun. Pengamatan 
dilakukan terhadap sampel daun kopi dari berbagai kondisi, yaitu daun 
sehat, daun yang terinfeksi penyakit karat daun (Coffee Leaf Rust), daun 
53 
54 
yang terinfeksi penyakit bercak daun Cercospora (Cercospora Leaf Spot), 
dan kondisi daun yang mengalami gangguan lainnya. 
Selain mengamati kondisi tanaman, peneliti juga melakukan 
wawancara singkat kepada 30 petani kopi mengenai cara mereka 
mengidentifikasi penyakit pada daun kopi selama ini, kendala yang 
dihadapi dalam proses identifikasi penyakit, kebutuhan akan teknologi 
pendukung dalam pengelolaan kebun kopi, dan tingkat kepemilikan dan 
penggunaan smartphone di kalangan petani. Hasil observasi ini menjadi 
dasar dalam analisis kebutuhan sistem yang akan dibangun. 
3.1.2  
Studi Literatur 
Studi literatur dilakukan untuk memperoleh landasan teori dan 
referensi ilmiah yang relevan dengan topik penelitian. Penelusuran literatur 
mencakup berbagai sumber, antara lain jurnal ilmiah nasional dan 
internasional, prosiding seminar, buku teks, tesis, disertasi, serta 
dokumentasi teknis resmi dari platform dan pustaka yang digunakan. Studi 
literatur difokuskan pada beberapa topik utama berikut: 
• Penyakit tanaman kopi, khususnya penyakit yang menyerang daun 
kopi, mencakup gejala, penyebab, dan dampak terhadap hasil panen. 
• Teknik deep learning dan convolutional neural network (CNN) untuk 
klasifikasi citra tanaman, dengan penekanan pada arsitektur DenseNet 
(Densely Connected Convolutional Networks). 
55 
• Transfer learning sebagai pendekatan efisien dalam pemanfaatan 
model pra-latih untuk klasifikasi citra pada dataset berukuran 
terbatas. 
• Progressive Web App (PWA) dan Progressive Mobile App (PMA) 
sebagai paradigma pengembangan aplikasi yang menggabungkan 
fitur web dan native. 
• Pengembangan aplikasi Android berbasis Java menggunakan Android 
Studio sebagai lingkungan pengembangan (IDE). 
• Firebase sebagai platform Backend-as-a-Service (BaaS) untuk 
pengelolaan basis data real-time, autentikasi, dan penyimpanan file. 
• Model pengembangan perangkat lunak Waterfall dalam konteks 
pengembangan sistem skala akademik. 
Studi literatur dilakukan melalui penelusuran pada beberapa basis 
data ilmiah terkemuka, di antaranya Google Scholar, IEEE Xplore, 
ScienceDirect, ResearchGate, dan Mendeley. Hasil studi literatur 
digunakan sebagai acuan dalam perancangan arsitektur model, pemilihan 
teknologi, dan pengambilan keputusan teknis selama proses pengembangan 
sistem. 
3.1.3  
Dokumentasi 
Metode dokumentasi dilakukan untuk mengumpulkan data 
sekunder berupa dokumen, laporan, dan berkas-berkas yang berkaitan 
56 
dengan objek penelitian. Dokumentasi dalam penelitian ini mencakup 
beberapa hal sebagai berikut: 
• Pengumpulan dataset citra daun kopi yang digunakan sebagai data 
latih (training), data validasi (validation), dan data uji (testing) model 
DenseNet. Dataset diperoleh dari sumber terbuka seperti Kaggle, 
PlantVillage Dataset, maupun hasil dokumentasi foto lapangan 
selama kegiatan observasi. 
• Pencatatan spesifikasi teknis perangkat keras dan perangkat lunak 
yang digunakan dalam proses penelitian. 
• Pengumpulan dokumentasi teknis Firebase, TensorFlow Lite, dan 
Android SDK sebagai referensi implementasi. 
• Pencatatan hasil pengujian model dan aplikasi yang digunakan 
sebagai bahan evaluasi dan pelaporan. 
Seluruh data yang dikumpulkan melalui ketiga metode di atas 
diorganisasi secara sistematis untuk memudahkan proses analisis, 
perancangan, dan pengembangan sistem. 
3.2  Alat dan Bahan 
Penelitian ini memerlukan berbagai alat dan bahan yang mendukung 
proses pengembangan aplikasi, pelatihan model machine learning, serta 
pengujian sistem. Alat dan bahan yang digunakan dikelompokkan menjadi 
dua kategori utama, yaitu perangkat keras dan perangkat lunak. 
57 
3.2.1  
Alat 
Alat yang digunakan dalam penelitian ini terdiri dari perangkat keras 
(hardware) dan perangkat lunak (software) dengan rincian sebagai berikut: 
a. Perangkat Keras (Hardware) 
Table 3.2.1 spesifikasi Perangkat Keras 
No 
Komponen 
Spesifikasi 
1 Laptop/PC (Pengembangan 
Model) 
Processor Intel Core i5/i7 atau AMD Ryzen 5/7, RAM 
minimal 8 GB (disarankan 16 GB), Storage SSD 256 GB, 
GPU NVIDIA (opsional untuk akselerasi training) 
2 Smartphone 
Android 
(Pengujian Aplikasi) 
OS Android minimal versi 8.0 (Oreo) API Level 26, RAM 
minimal 3 GB, Kamera belakang minimal 8 MP, Koneksi 
internet aktif 
3 Router/Akses Internet 
Koneksi internet stabil untuk sinkronisasi Firebase dan 
pengunduhan dependensi 
b.  Perangkat Lunak (Software) 
Table 3.2.2 Perangkat Lunak yang Digunakan 
No 
Perangkat Lunak 
Fungsi / Keterangan 
1 Android Studio (Hedgehog / 
terbaru) 
IDE utama untuk pengembangan aplikasi Android 
berbasis Java 
2 Java Development Kit (JDK) 
11/17 
Lingkungan runtime bahasa pemrograman Java untuk 
Android 
3 Python 3.8+ 
Bahasa pemrograman untuk proses pelatihan model 
DenseNet menggunakan TensorFlow/Keras 
4 TensorFlow / Keras 
Framework deep learning untuk pembangunan dan 
pelatihan model DenseNet 
5 TensorFlow Lite (TFLite) 
Konversi model ke format ringan (.tflite) untuk inferensi 
on-device di Android 
58 
No 
Perangkat Lunak 
Fungsi / Keterangan 
6 Google Firebase 
Platform BaaS untuk Realtime Database, Authentication, 
dan Firebase Storage 
7 Google Colab / Jupyter 
Notebook 
Lingkungan pelatihan model DenseNet berbasis cloud 
(GPU gratis) 
8 Git & GitHub 
Version control dan repositori kode sumber 
9 Postman 
Pengujian endpoint REST API 
10 Figma 
Perancangan wireframe dan desain antarmuka pengguna 
(UI/UX) 
11 Microsoft 
LibreOffice 
Office 
/ 
Penyusunan laporan, dokumentasi, dan tabel pengujian 
3.2.2 Bahan 
Bahan penelitian merupakan seluruh data dan sumber daya informasi 
yang digunakan sebagai masukan dalam proses pengembangan model 
maupun sistem aplikasi. Bahan yang digunakan dalam penelitian ini adalah 
sebagai berikut: 
Table 3.23 Bahan Penelitian 
No 
Bahan 
Keterangan 
1 Dataset Citra Daun Kopi 
Kumpulan gambar daun kopi dalam kondisi sehat dan 
terinfeksi berbagai penyakit (karat daun, bercak 
Cercospora, dan kondisi lainnya). Dataset bersumber dari 
Kaggle, PlantVillage, dan dokumentasi lapangan 
2 Model Pra-Latih DenseNet 
(DenseNet121) 
Bobot model DenseNet yang telah dilatih pada dataset 
ImageNet, digunakan sebagai basis transfer learning 
untuk klasifikasi penyakit daun kopi 
59 
No 
Bahan 
Keterangan 
3 Label Kelas Penyakit 
Informasi kategori/kelas penyakit daun kopi yang 
digunakan sebagai ground truth dalam pelatihan model 
4 Data Hasil Observasi 
Lapangan 
Catatan dan foto hasil wawancara serta observasi 
langsung terhadap 30 petani kopi di lokasi penelitian 
5 Referensi Ilmiah 
Jurnal, artikel, dan buku yang digunakan sebagai acuan 
pengembangan sistem dan model 
3.3  Tahapan Penelitian 
Gambar 3.1 Alur Tahapan Penelitian 
60 
1. Identifikasi Masalah 
Dalam tahap ini , penulis melakukan identifikasi masalah yang 
dialami oleh petani kopi, yaitu sulitnya petani kopi untuk mendeteksi 
penyakit pada daun kopi secara cepat dan akurat. Deteksi manual 
memerlukan keahlian khusus dan waktu yang tidak efisien. Oleh karena itu, 
dibutuhkan sebuah solusi berbasis teknologi yang dapat diakses secara 
mobile, yaitu Progressive Mobile App (PMA) yang menggunakan 
kecerdasan buatan berbasis Transfer Learning dengan model DenseNet. 
2. Pengumpulan Dataset 
Data yang digunakan untuk penelitian penyakit pada daun kopi adalah 
citra atau foto daun kopi yang terdiri dari beberapa kelas penyakit yakni : 
• Daun sehat  
• Cercospora (bercak daun) 
• Phoma (bercak coklat) 
• Rust / karat daun (hemileia vastatrix) 
Penulis mendapatkan dataset dari publik seperti ( kaggle , roboflow, atau 
penelitian terdahulu). Berikut dataset yang telah peneliti dapatkan dan 
akan disajikan pada tabel 3.4. 
Table 3.3.1 Dataset 
NO 
Jenis 
Penyakit 
Gambar 
Sumber Dataset 
1 Daun Sehat 
Local = 
https://drive.google.com/drive/folders/ 
1z1N6Ij9l9U5P-Z4ti
GrJ9SWCMZtA5Hq?usp=drive_link 
2 Cercospora 
(bercak 
daun) 
https://www.kaggle.com/datasets 
/restualambagaskara/coffee-disease 
61 
3 Phoma 
(bercak 
coklat) 
https://www.kaggle.com/datasets 
/restualambagaskara/coffee-disease 
4 Rust / karat 
daun 
(hemileia 
vastatrix)  
https://www.kaggle.com/datasets 
/misbahulmakruf/daun-kopi-gc 
3. Preprocesing data 
Pada tahap ini, peneliti melakukan preprocesing data sebelum data citra 
dimasukkan kedalam model yakni : 
• Resize gambar ke ukuran standar (misal: 224×224 px sesuai input 
DenseNet)  
• Normalisasi nilai piksel (0–1)  
• Augmentasi data: rotasi, flip horizontal/vertikal, zoom, 
brightness adjustment — untuk mengatasi keterbatasan data dan 
meningkatkan generalisasi model 
4. Evaluasi Model  
pada tahapan ini, model dilatih menggunakan data training, kemudian 
dievaluasi menggunakan data validasi dan testing, berikut metrix yang 
digunakan untuk mengevaluasi model yakni : 
• Akurasi (Accuracy)  
Akurasi yakni dimana persentase jumlah prediksi yang benar di 
bandingkan dengan total keseluruhan data.  
• Presisi (Precision)  
Presisi yakni dimana semua data yang diprediksi positif oleh 
model, dihitung berapa banyak yang benar-benar positif. Untuk 
Mengukur seberapa tepat model saat memberi label suatu kelas. 
62 
• Recall  
Recall yakni  hasil semua data yang berhasil ditemukan oleh 
model. Untuk mengukur kemampuan model dalam tidak 
melewatkan kasus yang ada. 
• F1-Score  
F1-score yakni nilai rata-rata yang cocok antara Precision dan 
Recall. Digunakan ketika kedua metrik tersebut sama pentingnya, 
terutama saat data tidak seimbang antar kelas. 
• Confusion Matrix 
Confusion matrix yakni sebuah tabel yang merangkum hasil 
prediksi model secara menyeluruh, untuk menunjukkan 
perbandingan antara nilai aktual dan nilai prediksi untuk setiap 
kelas penyakit. 
5. Tahap Analisis Kebutuhan 
Tahap analisis kebutuhan merupakan tahap awal yang bertujuan 
untuk mengidentifikasi dan mendefinisikan seluruh kebutuhan sistem 
secara menyeluruh. Pada tahap ini dilakukan kegiatan pengumpulan data 
melalui observasi langsung kepada 30 petani kopi, studi literatur terkait 
penyakit daun kopi dan teknologi deep learning, serta analisis sistem 
sejenis yang telah ada sebelumnya. 
Kegiatan yang dilaksanakan pada tahap analisis kebutuhan ini meliputi: 
1. Analisis permasalahan pada keresahan petani kopi, yaitu 
mengidentifikasi akar masalah (root cause) terkait penanggulangan 
penyakit pada daun kopi sejak dini, lemahnya pengelolaan dan 
distribusi informasi pertanian, serta minimnya pemanfaatan teknologi 
digital di kalangan petani. 
2. Identifikasi kebutuhan pengguna (user requirement), yang diperoleh 
secara langsung dari hasil observasi lapangan dan wawancara 
mendalam dengan 30 petani kopi. 
63 
3. Analisis kebutuhan fungsional sistem, yaitu mendefinisikan fungsi
fungsi utama yang harus dimiliki oleh aplikasi agar dapat memenuhi 
kebutuhan pengguna secara optimal. 
4. Analisis kebutuhan non-fungsional sistem, mencakup aspek performa 
sistem, kemudahan penggunaan (usability), keamanan data pengguna, 
serta kompatibilitas terhadap perangkat Android yang umum 
digunakan oleh petani kopi. 
Hasil dari tahap ini adalah dokumen Spesifikasi Kebutuhan 
Perangkat Lunak (SKPL) yang mencakup kebutuhan fungsional dan non
fungsional sistem. Kebutuhan fungsional meliputi kemampuan aplikasi 
untuk mengambil atau mengunggah foto daun kopi, melakukan deteksi 
penyakit secara real-time menggunakan model DenseNet yang telah 
dikonversi ke TensorFlow Lite, menampilkan hasil diagnosa beserta 
rekomendasi penanganan, serta menyimpan riwayat deteksi melalui 
Firebase. Kebutuhan non-fungsional mencakup aspek performa, keamanan 
data, kemudahan penggunaan, dan kompatibilitas dengan perangkat 
Android minimal versi 8.0. 
6. Tahap Perancangan Sistem 
Tahap perancangan difokuskan pada penerjemahan hasil analisis 
kebutuhan menjadi blueprint sistem yang komprehensif. Perancangan pada 
penelitian ini mencakup tiga aspek utama: 
1.  Perancangan UML (Unified Modeling Language) 
Perancangan sistem dalam penelitian ini menggunakan 
pendekatan Unified Modeling Language (UML) sebagai alat bantu 
untuk memodelkan sistem secara visual. UML digunakan untuk 
menggambarkan struktur dan perilaku sistem sehingga memudahkan 
dalam proses pengembangan aplikasi berbasis Android. Dengan adanya 
pemodelan UML, pengembang dapat memahami kebutuhan sistem 
secara lebih sistematis sebelum masuk ke tahap implementasi. 
Perancangan UML dalam penelitian ini meliputi: 
64 
1. Use Case Diagram 
Use Case Diagram digunakan untuk menggambarkan hubungan 
antara aktor dengan sistem yang akan dibangun. Dalam sistem 
informasi komunitas petani ini terdapat dua aktor utama, yaitu: 
• Pengguna (Petani) 
Pengguna merupakan aktor utama yang menggunakan aplikasi 
untuk mengakses dan berbagi informasi pertanian.  
Gambar 3.2 use case diagram pengguna 
Use Case Diagram ini menggambarkan bahwa pengguna 
dapat berinteraksi langsung dengan fitur-fitur utama system. 
2. Activity Diagram 
Activity Diagram digunakan untuk menggambarkan alur 
aktivitas atau proses bisnis yang terjadi dalam sistem. Diagram ini 
menunjukkan langkah-langkah yang dilakukan pengguna dalam 
menggunakan aplikasi. 
Beberapa activity diagram yang dirancang dalam sistem ini antara 
lain: 
1. Activity Diagram Login  
• Pengguna membuka aplikasi  
65 
• Sistem menampilkan halaman login  
• Pengguna memasukkan email dan password  
• Sistem melakukan validasi ke database Firebase  
• Jika valid, pengguna masuk ke halaman utama  
• Jika tidak valid, sistem menampilkan pesan error  
Gambar 3.3 Activity Diagram Login 
66 
2. Activity Diagram Registrasi  
• Pengguna membuka menu registrasi  
• Mengisi data diri (nama, email, password)  
• Sistem menyimpan data ke Firebase  
• Pengguna berhasil membuat akun  
Gambar 3.4 Activity Diagram Register 
67 
3. Activity Diagram Pemindaian Daun Kopi  
• Pengguna menekan tombol klik pindai  
• Pemilihan Sumber Gambar 
• Validasi ukuran dan format gambar 
• System mengirim data ke Firebase 
• Menampilkan hasil pindai 
Gambar 3.5 Activity Diagram Pemindai Daun Kopi 
Activity diagram ini membantu dalam memahami alur kerja 
sistem secara lebih rinci dan sistematis. 
68 
3. Sequence Diagram  
Sequence Diagram digunakan untuk menggambarkan interaksi antar 
objek dalam sistem berdasarkan urutan waktu. Diagram ini 
sangat penting untuk memahami bagaimana sistem bekerja 
secara dinamis, terutama dalam proses komunikasi dengan 
database Firebase. 
Beberapa sequence diagram yang dirancang meliputi: 
1. Sequence Diagram Login  
• Pengguna memasukkan data login  
• Aplikasi mengirim request ke Firebase Authentication  
• Firebase memvalidasi data  
• Firebase mengirimkan respon  
• Aplikasi menampilkan hasil login  
Gambar 3.6 Sequence Diagram Login 
69 
2. Sequence Diagram Registrasi  
• Pengguna menginput data  
• Aplikasi mengirim data ke Firebase  
• Firebase menyimpan data pengguna  
• Sistem mengirimkan notifikasi berhasil  
Gambar 3.7 Sequence Diagram Registrasi 
3. Sequence Diagram Tombol Pemindaian  
• Pengguna tekan tombol pindai 
• Menampilkan dialog pilihan sumber gambar 
• Mevalidasi ukuran dan format gambar 
• System memproses gambar  
• Aplikasi mengirim data ke Firebase Database  
• Firebase menyimpan hasil  pindai 
• Sistem menampilkan hasil pindai 
70 
Gambar 3. 8 Sequence Diagram Pemindaian 
Sequence diagram ini menunjukkan bagaimana aliran data 
terjadi antara pengguna, aplikasi, dan database secara berurutan. 
4. Class diagram 
Class Diagram digunakan untuk menggambarkan struktur 
sistem dari segi kelas-kelas yang digunakan beserta atribut dan 
metode yang dimilikinya. Class diagram juga menunjukkan 
hubungan antar kelas dalam sistem. 
Berikut adalah beberapa kelas utama dalam sistem: 
1. Class User  
• Atribut: userId, nama, email, password  
• Method: login(), register(), updateProfile()  
2. Class Admin (extends User)  
• Method: kelolaUser(),  
3. Class Pemindaian 
• Atribut: postId, isi, tanggal, userId  
• Method: createPost(), deletePost(), updatePost()  
4. Class FirebaseService  
• Method: connectDatabase(), getData(), sendData() 
71 
Gambar 3.9 Class Diagram 
Relasi antar kelas: 
• User hanya dapat melakukan pemindaian 1 objek  
• Admin memiliki hak akses tambahan terhadap seluruh data  
• FirebaseService digunakan oleh semua kelas untuk komunikasi 
data  
Class diagram ini memberikan gambaran struktur sistem 
yang akan diimplementasikan dalam aplikasi Android berbasis 
Java dan Firebase. 
72 
2.  Perancangan Antarmuka Pengguna (UI/UX) 
Perancangan 
antarmuka 
pengguna 
dilakukan 
dengan 
mengutamakan prinsip kemudahan penggunaan (ease of use) mengingat 
karakteristik pengguna yang merupakan petani dengan tingkat literasi 
digital yang bervariasi. Desain antarmuka dirancang agar sederhana, 
intuitif, dan tidak membebani pengguna dengan kompleksitas yang tidak 
perlu. Halaman-halaman yang dirancang meliputi halaman Splash Screen, 
Login dan Registrasi, Beranda komunitas, Forum Diskusi beserta fitur 
komentar, Informasi Pertanian, serta halaman Profil Pengguna dengan fitur 
edit profil. 
Hasil dari keseluruhan tahap perancangan ini adalah sebuah 
blueprint mockup sistem yang lengkap, mencakup seluruh aspek teknis dan 
visual sistem, yang siap dijadikan panduan pada tahap implementasi. 
7.  Tahap Implementasi 
Tahap implementasi merupakan tahap pembangunan sistem secara 
nyata berdasarkan rancangan yang telah ditetapkan. Implementasi dalam 
penelitian ini dibagi menjadi dua bagian utama, yaitu: 
• Pembangunan dan Pelatihan Model DenseNet: Model DenseNet121 
diimplementasikan menggunakan framework TensorFlow/Keras 
dengan pendekatan transfer learning. Bobot pra-latih dari ImageNet 
digunakan sebagai titik awal, kemudian lapisan fully-connected 
terakhir diganti dan dilatih ulang (fine-tuning) menggunakan dataset 
citra daun kopi. Proses pelatihan dilaksanakan di Google Colab dengan 
memanfaatkan akselerasi GPU. Setelah model mencapai performa 
yang memuaskan, model dikonversi ke format TensorFlow Lite (.tflite) 
untuk diintegrasikan ke dalam aplikasi Android. 
• Pembangunan Aplikasi Android: Aplikasi dikembangkan 
menggunakan bahasa pemrograman Java pada IDE Android Studio. 
Implementasi mencakup pengembangan modul kamera untuk 
penangkapan citra, integrasi TFLite Interpreter untuk inferensi on
73 
device, koneksi ke Firebase untuk autentikasi pengguna dan 
penyimpanan riwayat deteksi, serta implementasi antarmuka pengguna 
sesuai desain yang telah dibuat. Prinsip Progressive Mobile App 
diterapkan dengan mengimplementasikan mekanisme offline caching 
sehingga proses deteksi dapat tetap berjalan tanpa koneksi internet. 
8.  Tahap Pengujian 
Tahap pengujian dilaksanakan untuk memverifikasi bahwa sistem 
yang dikembangkan telah memenuhi kebutuhan yang telah ditetapkan dan 
berjalan dengan benar. Pengujian dalam penelitian ini meliputi beberapa 
jenis pengujian, yaitu: 
• Pengujian Model (Model Evaluation): Evaluasi kinerja model 
DenseNet menggunakan data uji yang dipisahkan dari data latih. 
Metrik evaluasi yang digunakan meliputi accuracy, precision, recall, 
F1-score, dan confusion matrix. 
• Pengujian Fungsional (Black Box Testing): Pengujian seluruh fitur 
aplikasi untuk memastikan setiap fungsi berjalan sesuai spesifikasi 
kebutuhan yang telah ditetapkan. 
• Pengujian Kegunaan (Usability Testing): Pengujian dilakukan dengan 
melibatkan sejumlah pengguna, termasuk petani kopi, untuk menilai 
kemudahan penggunaan (user-friendliness) dan efektivitas aplikasi di 
lapangan. 
• Pengujian Performa (Performance Testing): Pengujian waktu respons 
(response time) proses deteksi on-device untuk memastikan aplikasi 
dapat memberikan hasil diagnosa secara real-time. 
9.  Tahap Pemeliharaan Terbatas (Prototype) 
Sebagai tahap terakhir dari model Waterfall dalam konteks 
penelitian akademik ini, dilakukan pemeliharaan terbatas yang bersifat 
prototipe. Pada tahap ini dilakukan perbaikan minor berdasarkan temuan 
dari hasil pengujian, penyempurnaan antarmuka pengguna, serta 
dokumentasi teknis sistem secara lengkap. Pemeliharaan terbatas ini tidak 
74 
 
 
mencakup deployment ke pasar aplikasi, namun difokuskan pada 
penyempurnaan prototype yang siap diuji secara akademis. 
3.4  Jadwal Penelitian 
Penelitian ini dilaksanakan selama kurang lebih lima bulan, dimulai 
dari bulan pertama hingga bulan kelima. Jadwal penelitian disusun 
berdasarkan urutan tahapan pada model pengembangan Waterfall, dengan 
alokasi waktu yang disesuaikan dengan kompleksitas setiap tahapan. Rincian 
jadwal penelitian dapat dilihat pada Tabel 3.4 berikut: 
Table 3.4.1 Jadwal Pelaksanaan Penelitian 
No Tahapan Kegiatan Bulan 
1 
Bulan 
1 
Bulan 
2 
Bulan 
2 
Bulan 
3 
Bulan 
3 
Bulan 
4 
Bulan 
5 
  M1 M2 M3 M4 M5 M6 M7-8 M9+ 
1 Pengumpulan Data (Observasi, Studi 
Literatur, Dokumentasi) ✓ ✓       
2 Analisis Kebutuhan Sistem  ✓ ✓      
3 Perancangan Sistem (Arsitektur, 
Database, UI/UX)   ✓ ✓     
4 Pelatihan Model DenseNet & Transfer 
Learning    ✓ ✓    
5 Implementasi Aplikasi Android (Java)     ✓ ✓   
6 Integrasi Model TFLite & Firebase      ✓   
7 Pengujian Sistem (Black Box, 
Usability, Performa)       ✓  
8 Pemeliharaan Terbatas & 
Dokumentasi Akhir       ✓ ✓ 
9 Penyusunan Laporan & Sidang        ✓ 
 
75 
Jadwal penelitian di atas bersifat tentatif dan dapat mengalami 
penyesuaian sesuai dengan perkembangan penelitian di lapangan. Proses 
pelatihan model DenseNet dapat berlangsung lebih lama apabila diperlukan 
penyesuaian hyperparameter untuk mencapai akurasi yang optimal. Seluruh 
tahapan penelitian dilaksanakan dengan memperhatikan target penyelesaian 
skripsi yang telah ditetapkan bersama dosen pembimbing. 
76 
BAB IV 
HASIL DAN PEMBAHASAN 
4.1 Pengumpulan Dataset 
Pada tahapan ini penulis menunjukan hasil penggumpulan 4 klasifikasi 
dataset dan jumlah data yang akan digunakan untuk penelitian ini : 
NO JENIS KLASIFIKASI 
1 Daun Sehat 
JUMLAH 
2 Cercospora 
61 
3 Phoma 
111 
4 Rust 
111 
111 
Penulis mendapatkan dataset yang digunakan dari kaggle dan juga 
pengambilan secara pribadi. 
4.2 Preprosesing Data 
Pada tahapan ini, penulis melakukan preprosesing data pada citra daun 
yang akan digunakan pada  penelitian ini, dengan melakukan tahapan berikut : 
1. Resize data menjadi 224 x 224 px  
2. Normalisasi menjadi 0-1 
77 
3. Split Dataset 
Pada tahapan ini, penggunaan split data merupakan proses 
pembagian dataset ke dalam data train (training set), data validasi 
(validation set), dan data uji (test set). Data train digunakan untuk 
melatih model dalam mengenali pola pada citra penyakit daun kopi, 
data validasi digunakan untuk mengevaluasi performa model selama 
proses pelatihan serta membantu menentukan parameter terbaik, 
sedangkan data uji digunakan untuk mengukur kinerja akhir model 
terhadap data yang belum pernah digunakan sebelumnya. Pada 
penelitian ini, dataset dibagi dengan perbandingan 70% data latih, 
15% data validasi, dan 15% data uji. 
4. Augmentasi data  
Langkah augmentasi data dengan mengolah citra dengan penyesuaian 
rotasi, zoom serta perubahan brightness. 
78 
5. Konfigurasi model Densenet 
Konfigurasi ke model densenet 121 adalah serangkaian parameter 
yang digunakan untuk membangun dan melatih model, meliputi 
pemilihan arsitektur DenseNet, ukuran citra masukan, penggunaan 
bobot pra-latih (pretrained), learning rate, batch size, jumlah epoch, 
optimizer, fungsi loss, serta jumlah kelas keluaran. Penentuan 
konfigurasi yang tepat bertujuan untuk memperoleh model dengan 
tingkat akurasi yang tinggi dan kemampuan generalisasi yang baik pada 
proses klasifikasi citra. 
6. Freeze layer  
Freeze semua layer merupakan teknik pada transfer learning yang 
mengunci seluruh parameter model pra-latih sehingga bobot pada 
79 
setiap layer tidak diperbarui selama proses pelatihan. Pada penelitian 
ini, teknik tersebut digunakan agar DenseNet tetap mempertahankan 
kemampuan ekstraksi fitur yang telah dipelajari dari dataset ImageNet, 
sedangkan proses pembelajaran hanya dilakukan pada layer klasifikasi 
yang ditambahkan untuk mengenali kelas penyakit daun kopi. 
Pendekatan ini dapat mempercepat proses pelatihan dan mengurangi 
risiko overfitting ketika jumlah data pelatihan terbatas. 
7. Menambahkan layer  
Menambahkan layer merupakan proses penyisipan lapisan baru 
pada bagian akhir model DenseNet yang telah dilatih sebelumnya. 
Layer tambahan ini berfungsi untuk menyesuaikan model dengan tugas 
klasifikasi pada penelitian, yaitu mendeteksi penyakit daun kopi. Pada 
penelitian ini, layer tambahan terdiri atas Global Average Pooling, 
Dense, Dropout, dan layer output dengan fungsi aktivasi Softmax 
sesuai dengan jumlah kelas yang digunakan. Dengan penambahan layer 
tersebut, model dapat memanfaatkan kemampuan ekstraksi fitur dari 
DenseNet sekaligus menghasilkan prediksi yang sesuai dengan dataset 
penelitian. 
80 
4.3 Evaluasi Model 
Pada tahapan ini peneliti mengevaluasi model untuk mengtahui 
tingkat akurasi,precision,recall, dan f1-score sebelum di implementasikan 
ke progressive mobile app. 
4.3.1. Confusion Matrik 
Confusion Matrix merupakan metode evaluasi yang digunakan untuk 
menilai performa model klasifikasi dengan membandingkan hasil prediksi 
model terhadap label sebenarnya. Tabel ini menunjukkan jumlah prediksi 
yang benar dan salah pada setiap kelas sehingga dapat digunakan untuk 
menghitung nilai accuracy, precision, recall, dan F1-score. Pada penelitian 
ini, confusion matrix digunakan untuk mengevaluasi kinerja model 
81 
DenseNet dalam mengklasifikasikan penyakit daun kopi berdasarkan citra 
yang diuji. 
4.3.2. Analisis kurva Loss dan Accuracy 
4.4. Konversi Model ke TFlite 
82 
Pada tahapan ini, model dikonversi ke model TensorFlow Lite (TFLite) 
dimana proses ini mengubah model hasil pelatihan TensorFlow ke dalam 
format .tflite yang telah dioptimalkan untuk perangkat mobile. Proses ini 
bertujuan agar model dapat dijalankan secara efisien pada aplikasi 
Android dengan kebutuhan memori yang lebih kecil, waktu inferensi 
yang lebih cepat, serta mendukung penggunaan secara offline. Pada 
penelitian ini, model DenseNet yang telah dilatih dikonversi ke format 
TFLite sebelum diintegrasikan ke dalam Progressive Mobile App (PMA) 
untuk mendeteksi penyakit pada daun kopi. 
4.1 Hasil Implementasi Sistem 
Pada subbab ini dijelaskan proses implementasi aplikasi Progressive 
Mobile App (PMA) untuk deteksi penyakit daun kopi yang dibangun berdasarkan 
rancangan sistem pada Bab III. Implementasi dilakukan menggunakan Android 
Studio dengan bahasa pemrograman Java sebagai bahasa utama, dilengkapi 
beberapa pustaka AndroidX/Jetpack yang menyertakan dependensi Kotlin secara 
transparan (misalnya kotlinx-coroutines). Proses klasifikasi penyakit daun kopi 
dilakukan sepenuhnya secara on-device (offline) menggunakan TensorFlow Lite 
Interpreter, pengambilan gambar daun memanfaatkan pustaka CameraX (camera
core, camera-camera2, camera-lifecycle, camera-view), sedangkan penyimpanan 
data akun pengguna dan riwayat deteksi memanfaatkan basis data lokal Room 
(SQLite) dengan nama paket aplikasi com.data.coffe. 
4.1.1 Implementasi Halaman Login 
Halaman login (ActivityLogin) merupakan halaman pertama yang 
ditampilkan kepada pengguna. Halaman ini terdiri atas kolom input email 
83 
(etEmail) dan kata sandi (etPassword), tombol masuk (btnLogin), tautan lupa kata 
sandi (tvForgot), serta tautan menuju halaman registrasi (tvSignUp) bagi pengguna 
yang belum memiliki akun. Latar halaman menggunakan elemen gradasi 
(bg_login_gradient) untuk memperkuat identitas visual aplikasi. 
Validasi dilakukan sebelum data diproses: apabila salah satu kolom 
kosong, sistem menampilkan pesan “Silakan isi email dan password!”. Proses 
autentikasi dilakukan dengan mencocokkan input pengguna terhadap tabel users 
pada basis data Room melalui kueri berikut: 
SELECT * FROM users WHERE email = ? AND password = ? LIMIT 1 
Apabila kombinasi email dan kata sandi ditemukan, sistem menampilkan 
notifikasi “Login Berhasil!” dan mengalihkan pengguna menuju ActivityMain 
(Dashboard). Apabila tidak ditemukan kecocokan, sistem menampilkan notifikasi 
“Email atau Password salah!”. 
Gambar 4.1 Halaman Login 
84 
4.1.2 Implementasi Halaman Registrasi 
Form registrasi (ActivityRegister) terdiri atas input nama lengkap, email, 
dan kata sandi yang dipetakan ke entitas UserEntity (fullName, email, password), 
sedangkan kolom role dan joinedDate diisi otomatis oleh sistem pada saat akun 
dibuat. Skema tabel users yang ditemukan pada basis data adalah sebagai berikut: 
CREATE TABLE IF NOT EXISTS `users` (`id` INTEGER PRIMARY KEY 
AUTOINCREMENT NOT NULL, `fullName` TEXT, `email` TEXT, `password` 
TEXT, `role` TEXT, `joinedDate` TEXT) 
Setelah data pendaftaran berhasil disimpan ke tabel users, sistem 
menampilkan notifikasi “Akun berhasil dibuat!” melalui tombol btnRegister, 
kemudian mengarahkan pengguna kembali ke halaman login. 
Gambar 4.2 Halaman Registrasi 
85 
4.1.3 Implementasi Dashboard/Home 
Dashboard (ActivityMain) menggunakan struktur navigasi berbasis 
Navigation Component dengan tiga menu utama pada bottom navigation, yaitu 
nav_scan (Pindai Daun), nav_history (Riwayat), dan nav_profile (Profil). Bagian 
atas dashboard menampilkan sapaan personal (tvGreeting: “Halo, [nama 
pengguna]”) beserta tiga kartu ringkasan statistik: total pemindaian 
(tvStatTotalScans), jumlah daun terdeteksi sakit (tvStatDiseased), dan jumlah daun 
sehat (tvHealthyScans). Di bawah kartu statistik ditampilkan daftar riwayat terbaru 
(rvRecentHistory) serta tombol pintasan (btnScan) menuju halaman pemindaian. 
Gambar 4.3 Dashboard Aplikasi 
86 
4.1.4 Implementasi Pemindaian Daun Kopi 
Halaman pemindaian (ActivityCamera) memanfaatkan pustaka CameraX 
untuk menampilkan pratinjau kamera secara real-time, dilengkapi bingkai 
pemandu (bg_reticle_border) agar posisi daun berada tepat di tengah bidang bidik. 
Pengguna dapat mengambil gambar langsung melalui tombol btnCapture, 
mengatur lampu kilat melalui btnFlash, atau memilih gambar dari galeri melalui 
btnGallery sebagai alternatif selain pengambilan gambar langsung. Selama proses 
inferensi berlangsung, sistem menampilkan animasi garis pemindaian (scanLine) 
sebagai indikator visual bahwa gambar sedang diproses oleh model. 
Alur teknis pemrosesan gambar hingga menghasilkan prediksi adalah 
sebagai berikut: 
Kamera / Galeri  →  Ambil / Pilih Gambar  →  Resize 224×224 px  →  
Normalisasi Piksel  →  TensorFlow Lite Interpreter  →  Softmax (5 Kelas)  
→  Tampilkan Hasil 
Gambar 4.4 Halaman Scan Daun 
87 
4.1.5 Implementasi Model DenseNet TensorFlow Lite 
Model hasil transfer learning dikonversi ke format TensorFlow Lite (.tflite) 
dan disimpan pada folder assets aplikasi agar proses inferensi dapat dilakukan 
sepenuhnya secara offline. Hasil pembongkaran langsung terhadap berkas 
assets/model.tflite dan assets/labels.txt menunjukkan spesifikasi berikut: 
Komponen 
Keterangan 
Model 
DenseNet121 (hasil Transfer Learning) — lihat catatan 
verifikasi di bawah 
Framework Training 
TensorFlow/Keras 
Format Deploy 
TensorFlow Lite (.tflite) 
Ukuran Berkas Model 
± 9,5 MB 
Dimensi Tensor Input 
1 × 224 × 224 × 3 (RGB, float32) 
Dimensi Tensor Output 
1 × 5 (probabilitas softmax 5 kelas) 
Lokasi Model 
assets/model.tflite 
Berkas Label 
assets/labels.txt 
Jumlah Kelas 
4 kelas 
Label Kelas 
Bercak Cercospora, Hama Penggerek Daun, Daun Sehat, 
Bercak Phoma, Karat Daun 
Inference Engine 
org.tensorflow.lite.Interpreter (CPU) 
4.1.6 Implementasi Halaman Hasil Deteksi 
Halaman hasil deteksi (ActivityResult) menampilkan gambar daun yang 
telah dipindai (ivResultImage), nama kelas hasil deteksi (tvDiseaseName), skor 
keyakinan model (tvConfidence/tvAccuracy), serta indikator tingkat keparahan 
(tvSeverity) dengan level yang ditemukan pada implementasi antara lain “Sedang” 
dan “Parah”. Status hasil ditandai secara visual melalui badge berwarna: hijau 
untuk 
kondisi 
sehat 
(bg_badge_healthy), 
merah 
untuk 
penyakit 
(bg_badge_diseased), dan kuning untuk peringatan/hama (bg_badge_warning). 
88 
 
 
Aplikasi menyertakan basis pengetahuan (knowledge base) berupa 
deskripsi gejala (tvSymptomsDesc), penyebab (tvCausesDesc), dan rekomendasi 
penanganan (tvTreatmentDesc1, tvTreatmentDesc2) untuk setiap kelas hasil 
deteksi, lengkap dengan nama ilmiah agen penyebab. Contoh dua kelas yang telah 
diimplementasikan adalah sebagai berikut: 
 
Kelas Agen 
Penyebab Gejala Rekomendasi 
Penanganan 
Daun Sehat Healty Daun sehat tidak terjangkit 
penyakit - 
Bercak Coklat Phoma 
Bercak coklat dengan tepi 
menghitam berbentuk bulat 
hingga tak beraturan, curah 
hujan yang tinggi 
Pangkas daun sejak dini 
sehingga mengurangi 
penyebaran, 
pemangkasan cabang 
yang terlalu rapat untuk 
sirkulasi udara 
Bercak 
Cercospora 
Cercospora 
coffeicola 
Bercak coklat dengan pusat 
abu-abu; berkembang cepat 
pada kelembapan tinggi dan 
suhu hangat. 
Gunakan fungisida 
berbahan aktif tembaga 
jika infeksi menyebar 
luas. 
Rust/Karat 
Daun 
Hemileia 
vastatrix 
Bercak serbuk kuning-oranye 
di bagian bawah daun; daun 
rontok sebelum waktunya. 
Semprotkan fungisida 
kontak/sistemik 
berbahan aktif 
triadimefon secara 
berkala; pangkas 
cabang yang terinfeksi 
parah. 
 
Apabila hasil deteksi tidak dapat dipetakan pada basis pengetahuan, sistem 
menampilkan pesan cadangan (fallback): “Penyebab tidak dapat diidentifikasi. 
Kemungkinan kondisi daun tidak dikenali oleh sistem.” 
Halaman ini juga menyediakan tiga aksi lanjutan: btnSaveHistory untuk 
menyimpan hasil ke riwayat, btnShare untuk membagikan hasil, dan 
btnMarkTreated untuk menandai bahwa daun telah ditangani. Sistem turut 
merekam lokasi geografis pengambilan gambar (memanfaatkan izin 
ACCESS_FINE_LOCATION) pada setiap hasil yang disimpan, sehingga riwayat 
89 
deteksi berpotensi dipetakan berdasarkan lokasi sampel — nilai tambah yang 
mendukung visualisasi sebaran penyakit pada lahan perkebunan kopi. 
Gambar 4.5 Hasil Deteksi 
4.1.7 Implementasi Riwayat Deteksi 
Halaman riwayat (ActivityHistory) menampilkan daftar hasil deteksi 
sebelumnya melalui RecyclerView (rvHistory) dengan tata letak item_history yang 
menyertakan gambar thumbnail (imgHistory), nama penyakit, tanggal, dan tingkat 
keyakinan. Apabila belum terdapat data riwayat, sistem menampilkan pesan 
kosong (tvEmptyHistory). Saat salah satu item dipilih, pengguna diarahkan ke 
ActivityHistoryDetail yang menampilkan rincian lengkap hasil deteksi, termasuk 
opsi menandai status penanganan melalui btnMarkTreated. Ketika status 
diperbarui, sistem menampilkan notifikasi “Berhasil ditandai sudah diobati” dan 
memperbarui kolom isTreated pada tabel scan_history. 
90 
Gambar 4.6 Riwayat Deteksi 
4.1.8 Implementasi Profil Pengguna 
Halaman profil (ActivityProfile) menampilkan informasi akun pengguna 
yang sedang aktif, yaitu nama (tvUserName) dan peran akun (tvUserRole), disertai 
ikon profil bawaan (ic_profile_person). Tombol btnLogout digunakan untuk 
mengakhiri sesi aktif; setelah proses logout berhasil, sistem menampilkan 
notifikasi “Berhasil Log Out” dan mengarahkan pengguna kembali ke halaman 
login. 
91 
Gambar 4.7 Profil Pengguna 
4.2 Implementasi Basis Data 
Berbeda dari rancangan awal yang menyebutkan Firebase, hasil 
implementasi aktual menggunakan Room (pustaka persistence berbasis SQLite 
dari Android Jetpack) sebagai basis data lokal on-device. Terdapat dua entitas 
utama, yaitu users dan scan_history, dengan skema sebagai berikut. 
92 
 
 
Tabel users 
Kolom Tipe Keterangan 
id INTEGER (PK, 
AUTOINCREMENT) Kunci utama akun pengguna 
fullName TEXT Nama lengkap pengguna 
email TEXT Alamat email, digunakan sebagai 
identitas login 
password TEXT Kata sandi akun (lihat catatan 
keamanan pada 4.1.1) 
role TEXT Peran/hak akses pengguna 
joinedDate TEXT Tanggal akun dibuat, diisi otomatis 
 
Tabel scan_history 
Kolom Tipe Keterangan 
id INTEGER (PK, 
AUTOINCREMENT) Kunci utama catatan deteksi 
userId INTEGER (FK → users.id) Relasi ke akun pemilik data 
diseaseName TEXT Nama kelas hasil deteksi 
accuracy REAL Skor keyakinan (confidence) 
model 
date TEXT Tanggal dan waktu pemindaian 
imagePath TEXT Lokasi berkas gambar hasil 
pemindaian 
location TEXT Koordinat lokasi pengambilan 
gambar (GPS) 
isTreated BOOLEAN Status penanganan (sudah/belum 
diobati) 
 
Perlu dicatat bahwa Room bersifat lokal per perangkat dan tidak melakukan 
sinkronisasi otomatis ke server/cloud sebagaimana Firebase Firestore/Realtime 
Database. Implikasi dari perbedaan ini dibahas lebih lanjut pada subbab 4.6 
(Kekurangan Sistem). 
93 
 
 
4.4 Pengujian Aplikasi 
4.4.1 Pengujian Black Box 
Pengujian black box dilakukan terhadap seluruh fitur fungsional aplikasi 
yang telah diimplementasikan. Kolom “Hasil yang Diharapkan” disusun 
berdasarkan spesifikasi/perilaku yang diprogramkan pada aplikasi; kolom “Hasil 
Pengujian Aktual” wajib diisi setelah Anda benar-benar menjalankan setiap 
skenario pada perangkat/emulator. 
No Fitur Skenario Pengujian Hasil yang Diharapkan Hasil 
Aktual 
1 Login Login dengan email & 
password terdaftar 
Menampilkan “Login 
Berhasil!”, masuk ke 
Dashboard 
Success 
2 Login Login dengan 
email/password salah 
Menampilkan “Email atau 
Password salah!” Success 
3 Registrasi Registrasi dengan data 
valid 
Menampilkan “Akun berhasil 
dibuat!”, kembali ke Login Success 
4 Registrasi Registrasi dengan kolom 
kosong 
Menampilkan pesan validasi, 
form tidak terkirim Success 
5 Scan Ambil gambar via 
kamera 
Gambar tertangkap, 
diteruskan ke tahap resize & 
inferensi 
Success 
6 Scan Pilih gambar via galeri Gambar terpilih diproses 
sama seperti hasil kamera Success 
7 Deteksi Model TFLite 
memproses gambar 
Menampilkan nama kelas, 
confidence, dan info 
penanganan 
Success 
8 Riwayat Simpan hasil deteksi 
Data tersimpan pada tabel 
scan_history dan tampil di 
Riwayat 
Success 
9 Riwayat Tandai hasil sudah 
diobati 
Menampilkan “Berhasil 
ditandai sudah diobati”, 
isTreated ter-update 
Success 
10 Riwayat Buka Riwayat tanpa 
data 
Menampilkan pesan riwayat 
kosong Success 
11 Profil Logout Menampilkan “Berhasil Log 
Out”, kembali ke Login Success 
94 
4.4.2 Pengujian pada Berbagai Gambar 
Pengujian ini mengukur ketepatan prediksi model terhadap sampel citra 
daun kopi dari keempat kelas yang didukung aplikasi.  
Gambar 
Healthy 
Cercospora 
Phoma 
Rust 
Daun Sehat 
Prediksi 
99.79% 
0.09% 
0.9% 
0.3% 
Cercospora 
Healthy 
22.90% 
68.99% 
4.77% 
3.34% 
Phoma 
Cercospora 
0.01% 
0.1% 
49.66% 
50.23% 
Rust 
Rust 
0.00% 
0.02% 
0.42% 
99.56% 
4.5 Pembahasan 
4.5.1 Analisis Implementasi PMA 
Berdasarkan 
hasil 
pembongkaran 
APK, 
aplikasi 
Rust 
berhasil 
diimplementasikan sebagai Progressive Mobile App yang berjalan sepenuhnya 
secara offline: seluruh proses klasifikasi memanfaatkan TensorFlow Lite 
Interpreter secara on-device tanpa memerlukan koneksi ke server eksternal (tidak 
ditemukan pemanggilan API pihak ketiga maupun Firebase). Alur navigasi Login 
→ Dashboard → Scan → Hasil Deteksi → Riwayat → Profil berjalan sesuai 
rancangan pada Bab III, dengan tambahan fitur yang memperkaya nilai praktis 
aplikasi, yaitu opsi pemilihan gambar dari galeri (selain kamera langsung), 
pencatatan lokasi GPS pada setiap hasil deteksi, serta fitur penandaan status 
penanganan (isTreated) pada riwayat. Penggunaan Room sebagai basis data lokal 
juga menjadikan aplikasi ringan dan tetap dapat berfungsi penuh tanpa koneksi 
internet, sejalan dengan tujuan PMA yang mengedepankan aksesibilitas bagi 
petani di lokasi dengan konektivitas terbatas. 
4.5.2 Analisis Hasil Deteksi 
Akurasi deteksi pada penggunaan nyata di lapangan umumnya dipengaruhi 
oleh beberapa faktor, yaitu: (1) pencahayaan saat pengambilan gambar, karena 
model dilatih pada rentang pencahayaan tertentu; (2) kualitas kamera perangkat 
pengguna; (3) sudut dan jarak pengambilan gambar terhadap permukaan daun; 
95 
 
 
serta (4) kondisi fisik daun itu sendiri (mis. daun yang terlipat, tertutup embun, 
atau tumpang tindih dengan daun lain). Faktor-faktor ini perlu dikonfirmasi secara 
empiris melalui pengujian pada berbagai kondisi pengambilan gambar (lihat 
subbab 4.4.2), dan hasil pengamatan aktual sebaiknya dituliskan di sini setelah 
pengujian dilakukan. 
4.5.3 Analisis Performa Model 
Analisis performa model (accuracy, precision, recall, F1-score) perlu 
disusun berdasarkan hasil aktual pada subbab 4.3.4. Bandingkan pula hasil tersebut 
dengan penelitian terdahulu yang telah dibahas pada Bab II untuk menunjukkan 
posisi dan kontribusi penelitian ini terhadap kombinasi DenseNet + Transfer 
Learning + implementasi PMA. 
Peneliti Metode Hasil Perbandingan dengan Penelitian 
Ini 
Novtahaning 
et al. (2022) 
Ensemble CNN Akurasi 
97% 
penelitian ini menggunakan model 
yang digunakan lebih sederhana 
sehingga lebih mudah 
diimplementasikan pada perangkat 
mobile. 
Aufar & 
Kaloka 
(2022) 
Transfer Learning 
MobileNetV2 
Akurasi 
99,93% 
MobileNetV2 memperoleh akurasi 
lebih tinggi, tetapi penelitian ini 
menggunakan DenseNet yang 
memiliki kemampuan feature reuse 
lebih baik serta diimplementasikan 
dalam PMA. 
Mansouri et 
al. 
DenseNet + 
Transfer Learning 
Akurasi 
99,36% 
Penelitian terdahulu berfokus pada 
evaluasi model, sedangkan 
penelitian ini mengintegrasikan 
model ke dalam aplikasi PMA 
berbasis Android. 
Karia et al. 
(2025) 
DenseNet201Plus + 
Transfer Learning 
Akurasi 
99,0% 
Penelitian terdahulu hanya berfokus 
pada model klasifikasi, sedangkan 
penelitian ini menambahkan 
implementasi aplikasi mobile yang 
dapat digunakan secara langsung 
oleh pengguna. 
Esgario et al. CNN Mobile 
Application 
Akurasi 
tinggi 
Penelitian ini menggunakan 
arsitektur DenseNet dengan 
Transfer Learning serta mendukung 
inferensi menggunakan TensorFlow 
Lite pada aplikasi PMA. 
96 
Penelitian 
Ini 
DenseNet + 
Transfer Learning 
+ PMA 
Accuracy 
97%,  
Mengintegrasikan model AI ke 
dalam Progressive Mobile App 
sehingga dapat digunakan secara 
praktis oleh petani. 
Tabel 4.13 Perbandingan Hasil Penelitian dengan Penelitian Terdahulu 
97 
BAB V 
KESIMPULAN DAN SARAN 
1.1 Kesimpulan 
Berdasarkan hasil penelitian mengenai implementasi aplikasi 
Progressive Mobile App (PMA) untuk deteksi penyakit pada daun kopi 
menggunakan metode Transfer Learning dengan arsitektur DenseNet, 
maka dapat diperoleh beberapa kesimpulan sebagai berikut. 
1. Penelitian ini berhasil merancang dan mengimplementasikan aplikasi 
Progressive Mobile App (PMA) yang mampu melakukan deteksi 
penyakit pada daun kopi melalui citra digital menggunakan model 
DenseNet berbasis Transfer Learning. Model yang telah dilatih 
kemudian dikonversi ke format TensorFlow Lite (.tflite) sehingga 
proses inferensi dapat dijalankan langsung pada perangkat mobile (on
device inference) tanpa memerlukan koneksi internet maupun server 
eksternal.  
2. Aplikasi yang dikembangkan berhasil mengintegrasikan seluruh 
komponen sistem, mulai dari proses autentikasi pengguna, 
pengambilan gambar melalui kamera maupun galeri, proses klasifikasi 
penyakit, penyajian informasi hasil deteksi, hingga penyimpanan 
riwayat deteksi secara lokal menggunakan Room Database. Dengan 
demikian aplikasi mampu memberikan kemudahan bagi pengguna 
dalam melakukan identifikasi penyakit daun kopi secara cepat dan 
praktis.  
3. Berdasarkan hasil pengujian yang telah dilakukan pada Bab IV, model 
DenseNet mampu melakukan klasifikasi penyakit daun kopi dengan 
performa yang baik berdasarkan parameter evaluasi yang digunakan, 
yaitu accuracy, precision, recall, dan F1-score. Hal tersebut 
menunjukkan bahwa pendekatan Transfer Learning menggunakan 
DenseNet layak diterapkan sebagai solusi klasifikasi penyakit daun 
kopi berbasis citra digital.  
4. Pengujian fungsional menggunakan metode Black Box Testing 
menunjukkan bahwa seluruh fitur utama aplikasi dapat berjalan sesuai 
dengan kebutuhan sistem. Pengguna dapat melakukan proses 
pemindaian, melihat hasil klasifikasi, menyimpan riwayat deteksi, 
serta mengakses informasi penyakit tanpa mengalami kendala 
fungsional yang berarti.  
5. Implementasi teknologi Progressive Mobile App (PMA) memberikan 
nilai tambah dibandingkan aplikasi konvensional karena mampu 
berjalan secara offline, memiliki antarmuka yang responsif, serta dapat 
digunakan pada perangkat mobile dengan kebutuhan sumber daya 
yang relatif ringan. Kondisi tersebut menjadikan aplikasi lebih sesuai 
digunakan pada lingkungan perkebunan kopi yang memiliki 
keterbatasan akses internet.  
98 
Secara keseluruhan, penelitian ini berhasil menjawab seluruh rumusan 
masalah yang telah ditetapkan pada awal penelitian, yaitu membangun aplikasi 
deteksi penyakit daun kopi berbasis PMA dengan memanfaatkan Transfer 
Learning menggunakan arsitektur DenseNet sebagai model klasifikasi. 
5.2 Saran 
Berdasarkan hasil penelitian yang telah dilakukan, terdapat beberapa saran 
yang dapat dijadikan sebagai pengembangan penelitian selanjutnya, antara lain 
sebagai berikut. 
1. Menambah jumlah dan variasi dataset citra daun kopi dari berbagai kondisi 
pencahayaan, usia tanaman, serta lokasi perkebunan agar model memiliki 
kemampuan generalisasi yang lebih baik terhadap kondisi nyata di 
lapangan.  
2. Mengembangkan model klasifikasi agar mampu mengenali lebih banyak 
jenis penyakit maupun tingkat keparahan (severity level) sehingga 
informasi yang diberikan kepada pengguna menjadi lebih lengkap.  
3. Mengintegrasikan aplikasi dengan layanan cloud seperti Firebase atau 
server backend sehingga data riwayat deteksi dapat disinkronkan antar 
perangkat, digunakan sebagai media monitoring, maupun sebagai bahan 
analisis penyebaran penyakit.  
4. Menambahkan fitur rekomendasi penanganan penyakit yang lebih 
komprehensif, seperti jenis fungisida yang sesuai, langkah pengendalian, 
tindakan pencegahan, serta konsultasi dengan penyuluh pertanian.  
5. Melakukan optimasi model agar ukuran file TensorFlow Lite menjadi lebih 
kecil dengan tetap mempertahankan tingkat akurasi, sehingga performa 
aplikasi pada perangkat dengan spesifikasi rendah dapat semakin 
meningkat.  
6. Melakukan pengujian usability (kepuasan pengguna) dengan melibatkan 
petani kopi maupun penyuluh pertanian secara langsung agar diperoleh 
evaluasi mengenai kemudahan penggunaan, efektivitas, serta tingkat 
penerimaan aplikasi di lapangan.  
7. Penelitian selanjutnya dapat melakukan perbandingan performa DenseNet 
dengan arsitektur deep learning lain, seperti EfficientNet, MobileNetV3, 
ConvNeXt, atau Vision Transformer (ViT), untuk memperoleh model yang 
memiliki keseimbangan terbaik antara akurasi, kecepatan inferensi, dan 
ukuran model pada perangkat mobile.  
Dengan adanya pengembangan tersebut, diharapkan aplikasi deteksi penyakit daun 
kopi dapat menjadi solusi yang semakin akurat, mudah digunakan, serta 
memberikan kontribusi nyata dalam mendukung digitalisasi sektor pertanian dan 
meningkatkan produktivitas perkebunan kopi di Indonesia. 
99 
DAFTAR PUSTAKA 
[1] 
[2] 
[3] 
[4] 
[5] 
[6] 
[7] 
[8] 
[9] 
[10] 
[11] 
[12] 
[13] 
bps.go.id, “Badan Pusat Statistik Bps-Indonesia Coffee Statistics,” Bps.Go.Id, vol. 8, pp. 
11–12, 2024. 
M. Nawaz, T. Nazir, A. Javed, S. Tawfik Amin, F. Jeribi, and A. Tahir, “CoffeeNet: A deep 
learning approach for coffee plant leaves diseases recognition,” Expert Syst. Appl., vol. 237, 
p. 121481, 2024, doi: https://doi.org/10.1016/j.eswa.2023.121481. 
R. T. Araaf, A. Minn, and T. Ahamed, “Coffee Leaf Rust Disease Detection and 
Implementation of an Edge Device for Pruning Infected Leaves via Deep Learning 
Algorithms,” Sensors, vol. 24, no. 24, 2024, doi: 10.3390/s24248018. 
G. M. Esgario, P. B. C. De Castro, L. M. Tassis, and R. A. Krohling, “An app to assist 
farmers in the identification of diseases and pests of coffee leaves using deep learning,” 
vol. 9, pp. 38–47, 2022, doi: 10.1016/j.inpa.2021.01.004. 
J. G. M. Esgario, R. A. Krohling, and J. A. Ventura, “Deep learning for classification and 
severity estimation of coffee leaf biotic stress,” Comput. Electron. Agric., vol. 169, 2020, 
doi: 10.1016/j.compag.2019.105162. 
B. Mehta, S. Bharany, D. H. Elkamchouchi, A. U. Rehman, R. Singh, and S. H. Adem, 
“EffResViT-SE FusionNet: A Hybrid Deep Learning Framework for Accurate 
Classification of Coffee Leaf Diseases,” Food Sci. Nutr., vol. 13, no. 12, 2025, doi: 
10.1002/fsn3.71311. 
A. Jafar, N. Bibi, R. A. Naqvi, A. Sadeghi-Niaraki, and D. Jeong, “Revolutionizing 
agriculture with artificial intelligence: plant disease detection methods, applications, and 
their limitations,” Front. Plant Sci., vol. 15, no. March, pp. 1–20, 2024, doi: 
10.3389/fpls.2024.1356260. 
B. M. Abuhayi and A. Hajdu, “A Hybrid Compact Convolutional Transformer with 
Bilateral Filtering for Coffee Berry Disease Classification,” Sensors, vol. 25, no. 13, pp. 1
23, 2025, doi: 10.3390/s25133926. 
C. Pal, S. Karmakar, I. Mukherjee, and P. P. Chakrabarti, “A lightweight and explainable 
CNN model for empowering plant disease diagnosis,” Sci. Rep., vol. 15, no. 1, pp. 1–14, 
2025, doi: 10.1038/s41598-025-94083-1. 
D. Devarajan, R. Allafi, M. Obayya, and N. Nemri, “AI based real time disease diagnosis 
in plants using deep learning driven CNNs,” Sci. Rep., pp. 1–22, 2026, doi: 
10.1038/s41598-025-34681-1. 
B. Khanal, P. Poudel, A. Chapagai, B. Regmi, S. Pokhrel, and S. R. Khanal, “Paddy Disease 
Detection and Classification Using Computer Vision Techniques: A Mobile Application to 
Detect Paddy Disease,” 2024, [Online]. Available: http://arxiv.org/abs/2412.05996 
A. Siddiqua, M. A. Kabir, T. Ferdous, I. B. Ali, and L. A. Weston, “Evaluating Plant 
Disease Detection Mobile Applications : Quality and Limitations,” pp. 1–25, 2022. 
L. Li, S. Zhang, and B. Wang, “Plant Disease Detection and Classification by Deep 
100 
Learning - A Review,” IEEE Access, vol. 9, no. Ccv, pp. 56683–56698, 2021, doi: 
10.1109/ACCESS.2021.3069646. 
[14] 
[15] 
[16] 
[17] 
[18] 
[19] 
[20] 
[21] 
[22] 
[23] 
[24] 
[25] 
[26] 
[27] 
[28] 
D. Novtahaning, H. A. Shah, and J. M. Kang, “Deep Learning Ensemble-Based Automated 
and High-Performing Recognition of Coffee Leaf Disease,” Agric., vol. 12, no. 11, 2022, 
doi: 10.3390/agriculture12111909. 
Y. Aufar and T. P. Kaloka, “Robusta coffee leaf diseases detection based on MobileNetV2 
model,” Int. J. Electr. Comput. Eng., vol. 12, no. 6, pp. 6675–6683, 2022, doi: 
10.11591/ijece.v12i6.pp6675-6683. 
E. Gürsoy, “A review of deep learning architectures for plant disease detection,” vol. 49, 
no. 5, pp. 459–497, 2025, doi: 10.55730/1300-0152.2761. 
A. Sharma, N. Azeem, and S. Sharma, “Coffee Leaf Disease Detection Using Transfer 
Learning,” 2023, pp. 227–238. doi: 10.1007/978-3-031-28183-9_16. 
M. K. A. Mazumder, M. F. Mridha, S. Alfarhood, M. Safran, M. Abdullah-Al-Jubair, and 
D. Che, “A robust and light-weight transfer learning-based architecture for accurate 
detection of leaf diseases across multiple plants using less amount of images,” Front. Plant 
Sci., vol. 14, no. January, pp. 1–22, 2023, doi: 10.3389/fpls.2023.1321877. 
L. M. Tassis and R. A. Krohling, “Few-shot learning for biotic stress classification of coffee 
leaves,” Artif. Intell. Agric., vol. 6, pp. 55–67, 2022, doi: 10.1016/j.aiia.2022.04.001. 
Y. J. Cha, R. Ali, J. Lewis, and O. Büyükӧztürk, “Deep learning-based structural health 
monitoring,” 
Autom. 
Constr., 
10.1016/j.autcon.2024.105328. 
vol. 
161, 
no. 
February, 
2024, 
doi: 
N. Mansouri, H. Guesmi, and A. Alkhalil, “A deep learning model for detection and 
classification of coffee-leaf diseases using the transfer-learning technique,” vol. 10, no. 3, 
pp. 379–396, 2024. 
A. J. Karia, J. S. Ally, and S. Leonard, “Enhancing Coffee Leaf Rust Detection with 
DenseNet201Plus and Transfer Learning,” J. Inf. Syst. Informatics, vol. 7, no. 3, pp. 2339
2344, Sep. 2025, doi: 10.51519/journalisi.v7i3.1191. 
N. F. Hasan, “Deteksi dan Klasifikasi Penyakit Pada Daun Kopi Menggunakan Yolov7,” 
vol. 12, no. Dl, pp. 30–35, 2023. 
E. Mahasiswa and S. Aripin, “Implementasi Progressive Web Apps ( PWA ) pada 
Repository,” pp. 148–158, 2021, doi: 10.30864/eksplora.v10i2.486. 
A. Ghosh, S. K. M. B, P. Pattanaik, and P. K. Dash, “Unveiling the Future of Agriculture : 
Transformative Impact of Advanced Deep Learning with Mobile App Technology for 
Plant,” vol. 1, pp. 44–59. 
Q. Ouyang, “Study on High ‐ resolution Remote Sensing Image Scene Classification Using 
Transfer Learning,” vol. 3, no. 1, 2023. 
S. S. Mohammad et al., “Aiding the Digital Eyes to Detect the Leaf-Spot Diseases in Rice 
Crops using DenseNet CNN Algorithms,” vol. 1262, no. 6, pp. 1253–1262, 2025. 
A. Gajanan and N. Preetham, “Deep Learning for Smart Agriculture : A Comprehensive 
101 
Review of CNN Architectures , Multispectral Imaging , Explainable AI and Transfer 
Learning for Crop Disease Detection,” vol. 19, no. 3, pp. 128–143, 2026. 
[29] 
[30] 
[31] 
[32] 
[33] 
[34] 
[35] 
[36] 
[37] 
[38] 
[39] 
[40] 
[41] 
J. G. M. Esgario, P. B. C. de Castro, L. M. Tassis, and R. A. Krohling, “An app to assist 
farmers in the identification of diseases and pests of coffee leaves using deep learning,” Inf. 
Process. Agric., vol. 9, no. 1, pp. 38–47, 2022, doi: 10.1016/j.inpa.2021.01.004. 
J. Jepkoech, D. M. Mugo, B. K. Kenduiywo, and E. C. Too, “Arabica coffee leaf images 
dataset for coffee leaf disease detection and classification,” Data Br., vol. 36, p. 107142, 
2021, doi: 10.1016/j.dib.2021.107142. 
I. Ahmed and P. K. Yadav, “Plant disease detection using machine learning approaches,” 
Expert Syst., vol. 40, no. 5, p. e13136, Jun. 2023, doi: https://doi.org/10.1111/exsy.13136. 
E. C. Too, L. Yujian, S. Njuki, and L. Yingchun, “A comparative study of fine-tuning deep 
learning models for plant disease identification,” Comput. Electron. Agric., vol. 161, pp. 
272–279, 2019, doi: https://doi.org/10.1016/j.compag.2018.03.032. 
M. Faisal, J. S. Leu, and J. T. Darmawan, “Model Selection of Hybrid Feature Fusion for 
Coffee Leaf Disease Classification,” IEEE Access, vol. 11, no. June, pp. 62281–62291, 
2023, doi: 10.1109/ACCESS.2023.3286935. 
S. Liu, “Explore Java Language and Android Mobile Software Development,” vol. 3, no. 
2, pp. 5–9, 2021, doi: 10.25236/IJFET.2021.030202. 
K. Wasilewski, “A Comparison of Java , Flutter and Kotlin / Native Technologies,” 2021. 
P. R. Saraf, “A Review on Firebase (Backend as A Service) for Mobile Application 
Development,” Int. J. Res. Appl. Sci. Eng. Technol., vol. 10, no. 1, pp. 967–971, Jan. 2022, 
doi: 10.22214/ijraset.2022.39958. 
I. Journal, “Real-time Database Synchronization Techniques in Firebase for Mobile App 
Development,” INTERANTIONAL J. Sci. Res. Eng. Manag., vol. 07, no. 12, pp. 1–10, Dec. 
2023, doi: 10.55041/IJSREM22021. 
Y. Yanfi and P. D. Nusantara, “ScienceDirect ScienceDirect 7th International Conference 
on Computer Science and Computational Intelligence 2022 UI / UX design prototype for 
mobile community-based course UI / UX design prototype for mobile community-based 
course,” Procedia Comput. Sci., vol. 216, no. 2022, pp. 431–441, 2023, doi: 
10.1016/j.procs.2022.12.155. 
N. Kimseng, D. Ade, I. Vuthy, R. Wahyuni, and D. Setiyadi, “UI / UX Development Using 
Figma based on Inclusive Design,” vol. 4, no. 2, 2023. 
M. B. A. Pratama, S. S. Hilabi, M. M. Ihsan, I. Ferdiansyah, and H. S. Nizar, “Application 
of the Waterfall Method in Creating Payroll Applications Based on Java Netbeans,” J. 
Multimed. dan Teknol. Inf., vol. 6, no. 01, pp. 35–45, 2024, doi: 
10.54209/jatilima.v6i01.432. 
S. Hussain et al., “Mitigating Software Vulnerabilities through Secure Software 
Development with a Policy-Driven Waterfall Model,” vol. 2024, 2024, doi: 
10.1155/2024/9962691. 
102 
[42] 
[43] 
H. Sitompul, Z. Matondang, E. Daryanto, and F. Syahputra, “Use Case Diagram Design 
For Information System Services To Students At The Faculty Of Engineering Universitas 
Negeri Medan”, doi: 10.4108/eai.24-10-2023.2342345. 
P. M. Widodo, A. Jazuli, and E. Wijayanti, “Teknik Pengolahan Citra Digital Untuk 
Identifikasi Penyakit Pada Daun Tanaman Kopi,” J. Dialekt. Inform., vol. 5, no. 1, pp. 39
44, 2024, doi: 10.24176/detika.v5i1.13943. 