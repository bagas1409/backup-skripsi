Majalah Ilmiah UNIKOM       
Vol.21  No. 1 
BIDANG 
ILMU KOMPUTER & TIK 
APRIL 2023, 3 - 8  
p-ISSN : 1411-9374, e-ISSN : 2527-7030  
ANALISIS SYSTEM USABILITY SCALE (SUS) DAN PERANCANGAN  
SISTEM SELF SERVICE PEMESANAN MENU DI RESTORAN BERBASIS WEB   
ANAK AGUNG NGURAH HARY SUSILA1, DEWA MADE SRI ARSA2 
Universitas Udayana1, 2 
harysusila@unud.ac.id  
ABSTRACT 
COVID-19 is a global pandemic with 220 countries infected with this virus and 55,326,907 
confirmed cases. In Indonesia, from March to November 2021, there were 478,720 positive 
cases, where these cases were identified from clusters of offices, factories, educational 
establishments, hospitals/health centers, and finally a new cluster was found in a restaurant. 
The Ministry of Tourism and Creative Economy has issued guidelines for preventing COVID-19 in 
restaurants by providing menu lists and ordering food or drinks based online. The purpose of the 
study was to design an architectural model for the application of self service menus and orders 
at restaurants. The method used for designing this system is the Waterfall method with the 
System Usability Scale (SUS) method for testing application usability. The results of the research 
are the self-service architectural model of the menu and order application, there are two user 
actors, namely visitors and restaurant admins. The self service menu and order application 
architecture model has a menu page that can be accessed by guests and admins, namely the 
main system page, food and beverage menu, order check out page, admin order page and to 
access the system you can use a QR Code. The results of the application usability test using the 
System Usability Scale (SUS) method get an average value of 70 or the Good category (good). 
Key Words: Architecture Models, COVID-19, Restaurant, Self Service Application, System 
Usability Scale 
ABSTRAK 
COVID-19 merupakan pandemi global dengan jumlah Negara yang  terjangkit virus ini sebanyak 
220 dan jumlah kasus terkonfirmasi sebanyak 55.326.907 jiwa. Di Indonesia sejak bulan Maret 
sampai November 2021 terdapat kasus positif sebanyak 478.720 jiwa, dimana kasus ini 
teridentifikasi dari klaster perkantoran, pabrik, tempat pendidikan, rumah sakit/puskesmas, 
dan terakhir ditemukan klaster baru pada restoran. Kementerian Pariwisata dan Ekonomi 
Kreatif telah mengeluarkan panduan untuk pencegahan COVID-19 pada restoran dengan 
menyediakan daftar menu dan pemesanan makanan atau minuman berbasis online. Tujuan 
penelitian adalah merancang model arsitektur aplikasi self service  menu dan order pada 
restoran. Metode yang digunakan untuk perancangan sistem ini adalah metode Waterfall 
dengan metode System Usability Scale (SUS) untuk pengujian kegunaan aplikasi. Hasil dari 
penelitian yaitu model arsitektur self service aplikasi menu dan order terdapat dua aktor 
pengguna yaitu pengunjung dan admin restoran. Model arsitektur aplikasi self service menu 
dan order memiliki menu halaman yang dapat diakses tamu dan admin yaitu halaman utama 
sistem, menu makanan minuman, halaman check out pesanan, halaman order admin dan 
untuk mengakses sistem dapat menggunakan QR Code. Hasil dari pengujian kegunaan aplikasi 
dengan metode System Usability Scale (SUS) mendapatkan rata-rata nilai 70 atau kategori 
Good (baik).  
Kata Kunci: Aplikasi Self Service, COVID-19,  Restoran, System Usability Scale  
H  a  l  a  m a  n 
3 
Majalah Ilmiah UNIKOM     
Vol.21  No. 1 
Anak Agung Ngurah Hary Susila, Dewa Made Sri Arsa 
PENDAHULUAN 
COVID-19 merupakan pandemi global yang 
sudah ditetapkan oleh World Health Organization 
(WHO). Di Indonesia sejak bulan Maret sampai No
vember 2021 terdapat kasus positif sebanyak 
478.720 jiwa, dengan jumlah kesembuhan 
sebanyak 402.347 jiwa dan jumlah kematian 
sebanyak 15.503 jiwa [1]. Klaster atau sumber 
penyebaran COVID-19 di Indonesia terjadi pada ru
ang publik seperti perkantoran, pabrik, tempat pen
didikan, rumah sakit/puskesmas dan terakhir 
ditemukan klaster pada restoran. 
Pemerintah Indonesia melalui Kementerian 
Pariwisata dan Ekonomi Kreatif telah mengeluarkan 
Panduan Pelaksanaan Kebersihan, Kesehatan, 
Keselamatan dan Kelestarian Lingkungan di 
Restoran guna pencegahan dan pengendalian 
COVID-19 [2]. Salah satu panduan khusus mengenai 
pelayanan makan dan minum bagi pengelola 
restoran/rumah makan yaitu menyediakan daftar 
menu dan pemesanan makanan atau minuman 
yang berbasis online. Dengan menyiapkan daftar 
menu dan pemesanan berbasis online, tamu akan 
dapat melayani dirinya secara mandiri (Self Service) 
untuk memesan makan atau minum tanpa harus 
kontak secara langsung dengan pelayan. 
Penggunaan self service technology mem
berikan pengalaman yang menarik untuk perus
ahaan penyedia jasa karena dapat meningkatkan 
pelayanan operasional, meningkatkan efisiensi pela
yanan, menyediakan manfaat lebih bagi pelanggan, 
dan memperbanyak pilihan akses pelayanan [3] 
(Curran & Meuter, 2005). Konsep pelayanan yang 
awal mulanya secara konvensional bertemu secara 
langsung dengan pelayan, sekarang berubah men
jadi pelayanan dapat difasilitasi dengan pemanfaa
tan teknologi [4] (Fitzsimmons, 2003). Penelitian 
terdahulu terkait self service technology telah dil
akukan pada tempat usaha restoran dan kedai kopi 
[5]-[8]. Penelitian terdahulu merancang aplikasi self 
service berbasis android [5,8], web [5,6] dan 
dekstop [7]. Penelitian lainnya yang terkait dengan 
Pengujian sistem menggunakan metode System 
Usability Scale  (SUS) dilakukan pada studi kasus 
aplikasi E-Commerce Indomaret dan Alfamart [9].  
Adanya klaster COVID-19 di restoran yang 
ditemukan di Indonesia dan dikeluarkannya pan
duan khusus pelayanan di restoran selama masa 
pandemi COVID-19 dari Kementerian, berangkat dari 
latar belakang tersebut maka perlu dilakukan 
penelitian dengan memanfaatkan teknologi Self 
Service yang saat ini sedang banyak dimanfaatkan 
oleh 
masyarakat. Penelitian ini melakukan 
perancangan sistem self service technology  menu 
dan order di restoran agar tamu dapat mengakses 
secara mandiri tanpa harus kontak secara langsung 
dengan pelayan. Hal ini bertujuan untuk mengurangi 
kontak fisik dengan menu dan pelayan sehingga 
4 
dapat mencegah penularan Virus COVID-19 di 
restoran.  Selain merancang sistem self service 
menu dan order di restoran, penelitian akan 
menguji tingkat usabillity sistem agar mengetahui 
tingkat kebergunaan sistem ini pada restoran dan 
tamu restoran. 
METODE 
Kerangka Penelitian 
Kerangka penelitian yang digunakan untuk 
menyelesaikan masalah yaitu model pengem
bangan perangkat lunak Waterfall. Model Waterfall 
digunakan karena model ini menyediakan proses 
secara sekuensial linier atau berurutan yang dimu
lai dari analisis data, perancangan sistem, imple
mentasi, pengujian dan evaluasi [10]. Berikut pen
jelasan mengenai kerangka penelitian pada Gam
bar 1:  
Gambar 1. Kerangka Penelitian 
a. Tahap Analisis Data 
Tahap awal analisis data dilakukan dengan 
cara wawancara, observasi dan pengamatan secara 
langsung mengenai permasalahan dan proses 
bisnis pada restoran. 
H  a  l  a  m  a  n 
Anak Agung Ngurah Hary Susila, Dewa Made Sri Arsa 
Majalah Ilmiah UNIKOM       
Vol.21  No. 1 
b. Tahap Perancangan Sistem 
Tahap perancangan sistem adalah proses 
perancangan desain aplikasi seperti Use Case Dia
gram, perancangan database dan perancangan de
sain interface. 
c. Implementasi 
Tahap ini akan dilaksanakan implementasi 
aplikasi yang ada pada tahap perancangan sistem 
untuk menjadi aplikasi. 
d. Pengujian 
Tahap pengujian aplikasi menggunakan 
metode System Usability Scale (SUS). Metode Sys
tem Usability Scale (SUS) yaitu untuk mengetahui 
tingkat efektifitas, efisiensi dan kepuasan pengguna 
[11].   
Metode 
SUS 
memiliki 
tahapan 
yang 
digunakan untuk mengevaluasi sistem. Tahapan 
pertama yaitu membuat daftar pertanyaan yang 
terdiri dari 10 pertanyaan dan 5 jawaban. Jawaban 
memiliki rentang dari setuju sampai tidak setuju. 
Setelah daftar pertanyaan dibuat maka selanjutnya 
menyebarkan kepada responden. Responden yang 
digunakan pada penelitian ini sebanyak 10 respond
en.  
Menghitung hasil kuisioner menggunakan 
aturan persamaan 1.1  sebagai berikut: 
Keterangan: 
= skor rata-rata. 
= jumlah skor SUS. 
n = jumlah responden. 
(1.1) 
Analisis untuk kesimpulan hasil perhitungan 
SUS menggunakan SUS Score. SUS Score memiliki 
range nilai dari 0 – 50 Not Acceptable, 50 – 70 mar
ginal dan 70 – 100 Acceptable. 
Gambaran Umum Aplikasi 
Gambaran umum aplikasi Self Service Menu 
dan Order dapat dilihat pada Gambar 2. 
Berikut penjelasan Gambar 2 penggunaan 
umum dari aplikasi yang dirancang: 
a) Pertama pengunjung menggunakan smartphone 
untuk mengakses menu dan order online.  
b) Tamu dapat memilih scan QR Code atau me
masukkan link yang disediakan pada browser 
untuk mendapatkan data menu makanan/
minuman.  
c) Sistem akan me-request data menu ke server 
dan mendapatkan respon berupa data menu 
online.  
d) Menu online akan muncul pada smartphone dan 
pengunjung dapat melakukan order makanan/
minuman.  
e) Data pesanan makanan/minuman tamu akan 
masuk ke halaman admin restoran dan 
pengelola restoran menyediakan pesanan. 
HASIL DAN PEMBAHASAN 
Analisis Kebutuhan Sistem 
Sistem yang dibangun adalah sistem yang 
dapat membantu pengunjung dengan mudah 
melakukan proses melihat menu dan memesan 
menu tanpa berinteraksi secara langsung dengan 
pelayan. Pengunjugn hanya cukup menggunakan 
smartphone yang dimiliki untuk memindai atau 
menuliskan link yang sudah disediakan. Pengguna 
sistem ini yaitu pengunjung dan admin restoran. 
Untuk analisis kebutuhan masing-masing pengguna 
sebagai berikut: 
1. Pengunjung 
Pengunjung merupakan pengguna yang akan 
memesan makanan dan minuman. Adapun analisis 
pengunjung antara lain: 
a. Pengunjung akan diberikan QR Code untuk 
memindai pada kamera smartphone dan men
ampilkan sistem menu digital.  
b. Pengunjung dapat melakukan pesanan ma
kanan dan minuman.  
c. Data yang diinput oleh pengunjung berupa data 
nomor meja data makanan minuman yang di
pesan beserta jumlah pesanan.  
d. Pengunjung yang ingin menambah pesanan 
maupun membatalkan pesanan dapat dil
akukan pada sistem ini sebelum tamu 
melakukan proses check out. 
e. Pengunjung yang telah selesai melakukan 
pemesanan akan ditampilkan daftar pesanan 
makanan dan minuman beserta jumlah dan 
total belanja sebelum melakukan proses check 
out. Jika pengunjung akan menambah atau 
membatalkan pesanan masih dapat dilakukan 
pada sistem. 
f. 
Pengunjung yang pesanannya sudah lengkap 
dapat melakukan proses selanjutnya yaitu 
check out pesanan. 
g. Pengunjung yang telah melakukan proses check 
Gambar 2. Gambaran Umum Aplikasi 
H  a  l  a  m a  n 
5 
Majalah Ilmiah UNIKOM     
Vol.21  No. 1 
Anak Agung Ngurah Hary Susila, Dewa Made Sri Arsa 
out pesanan akan mendapatkan bukti transaksi 
digital yang berisi data nomor meja, nomor pe
sanan, daftar makanan minuman yang dipesan, 
jumlah pesanan dan total harga pesanan  
2. Admin Restoran 
Admin merupakan pengguna yang dapat 
mengelola sistem. Admin dapat melihat data pesan
an yang masuk dari hasil pesanan pengunjung. 
Perancangan Sistem 
Use case diagram sistem self service menu 
dan order makanan dan minuman dapat dilihat 
pada Gambar 3 berikut. 
Gambar 3. Use Case Diagram Sistem Self Service 
Gambar 3 menunjukkan terdapat dua aktor 
yaitu aktor pengunjung dan aktor admin. Aktor 
pengunjung dapat berinteraksi ke sistem untuk me
mesan makanan minuman dan menerima konfirma
si pesanan. Aktor admin berinteraksi ke sistem yaitu 
mengelola data pesanan. 
Implementasi Sistem 
Implementasi sistem menampilkan hasil dari 
rancangan sistem yang sudah dikerjakan. Imple
mentasi sistem yang telah berhasil dikerjakan yaitu 
halaman utama sistem, halaman daftar menu ma
kanan dan minuman, halaman order admin, hala
man checkout pesanan dan implementasi Qr Code 
6 
untuk mengakses aplikasi. Halaman utama sistem 
dapat dilihat pada Gambar 4. 
Gambar 4. Halaman Utama Sistem 
Halaman utama sistem seperti pada Gambar 
4 menampilkan logo restoran dan nama tempat 
restoran, kontak restoran dan button untuk 
melakukan pemesanan. Pada header juga terdapat 
button menu untuk pilihan Dessert, Drinks, Main 
Course dan Snack yang dapat dipilih oleh tamu. 
Bagian body terdapat foto-foto menu makanan dan 
minuman. Pengunjung yang akan memesanan ma
kanan dan minuman akan ditampilkan halaman 
menu seperti pada Gambar 5. 
Gambar 5. Halaman Menu Makanan dan Minuman 
Gambar 5 merupakan tampilan halaman 
menu makanan dan minuman. Halaman ini mem
berikan informasi mengenai nama menu, harga dan 
foto menu. 
Setelah pengunjung selesai memesan ma
kanan dan minuman, maka dilanjutkan pada proses 
checkout pesanan. Halaman checkout pesanan 
seperti pada Gambar 6 berikut. 
H  a  l  a  m  a  n 
Anak Agung Ngurah Hary Susila, Dewa Made Sri Arsa 
Majalah Ilmiah UNIKOM       
Vol.21  No. 1 
Gambar 6. Halaman Checkout Pesanan 
Halaman checkout pesanan menampilkan 
beberapa informasi kepada pengunjung yaitu infor
masi nomor order, tanggan pesanan, jumlah pesan
an, jumlah total transaksi, detail pesanan makanan 
dan minuman, nama tamu dan nomor meja tempat 
duduk pengunjung. Setelah pengunjung selesai 
melakukan proses checkout pesanan, maka pesan
an makanan dan minuman akan ditampilkan pada 
halaman order pada admin restoran. Halaman order 
pada admin dapat dilihat pada Gambar 7. 
Gambar 7. Halaman Order pada Admin 
Analisis Hasil Pengujian System Usability Scale 
(SUS) 
Pengujian sistem menggunakan metode Sys
tem Usability Scale (SUS). Pengujian sistem dengan 
menyebarkan kuisioner kepada 10 pengguna sis
tem. Kuisioner terdiri dari 10 pertanyaan yaitu: 
1. Q1: Saya berpikir akan menggunakan sistem 
Self Service Order ini lagi. 
2. Q2: Menurut saya, sistem Self Service Order  
terlalu rumit untuk digunakan. 
3. Q3: Menurut saya, sistem Self Service Order  
mudah digunakan. 
4. Q4: Menurut saya, dalam menggunkan sistem 
Self Service Order  ini  membutuhkan bantuan 
dari orang lain atau teknisi. 
5. Q5: Menurut saya, fitur-fitur sistem Self Service 
Order  berjalan dengan semestinya. 
6. Q6: Menurut saya, sistem Self Service Order  
tidak konsisten (tidak serasi pada sistem ini). 
7. Q7: Menurut saya, orang lain akan memahami 
cara menggunakan sistem Self Service Order  
dengan cepat. 
8. Q8: Menurut saya, sistem Self Service Order  
membingungkan. 
9. Q9: Menurut saya, tidak ada hambatan dalam 
menggunakan sistem Self Service Order. 
10. Q10: Menurut saya, perlu mempelajari banyak 
hal terlebih dahulu sebelum menggunakan sis
tem Self Service Order. 
Menghitung rata-rata nilai SUS menggunakan 
perhitungan untuk setiap pertanyaan ganjil nilai 
hasil kuisoner responden dikurangi 1, sedangkan 
untuk setiap pertanyaan genap skor hasil responden 
dikurangi 5. Tabel 1 berikut hasil penyebaran kui
sioner SUS dan skor rata-rata untuk pengujian sis
tem. 
Tabel 1: Hasil Kuisioner SUS 
H  a  l  a  m a  n 
7 
Majalah Ilmiah UNIKOM     
Vol.21  No. 1 
Anak Agung Ngurah Hary Susila, Dewa Made Sri Arsa 
Berdasarkan hasil pengujian SUS dengan 
menyebarkan kuisioner kepada 10 responden 
pengguna sistem maka didapatkan skor rata-rata 
yaitu 70. Berdasarkan skala SUS skor 70 termasuk 
kategori Good (baik) dalam efektivitas, efisiensi dan 
kepuasan pengguna. 
KESIMPULAN 
Kesimpulan yang didapat dari penelitian ini 
adalah sebagai berikut: 
1. Rancangan model arsitektur self service menu 
dan order berdasarkan kebutuhan aplikasi yaitu 
terdapat dua aktor pengguna yaitu aktor 
pengunjung dan aktor admin restoran. Model 
arsitektur aplikasi terdapat halaman menu yang 
dapat diakses oleh aktor pengunjung yaitu 
halaman utama sistem, halaman menu 
makanan dan minuman, halaman check out 
pesanan dan QR Code untuk mengakses sistem 
dari smartphone pengunjung. Aktor admin dapat 
mengakses halaman data order admin untuk 
mengetahui pesanan dari pengunjung. 
2. Hasil pengujian sistem untuk mengetahui 
kegunaan aplikasi mengggunakan metode 
System Usability Scale (SUS) mendapatkan hasil 
rata-rata skor yaitu 70 dengan kategori Good 
(baik). 
Saran untuk penelitian selanjutnya adalah 
merancang dan mengintegrasikan modul untuk 
pembayaran transaksi pesanan makanan dan 
minuman yang dilakukan oleh pengunjung restoran. 
Pada akhir berisi kesimpulan dari hasil 
penelitian baik berupa angka numerik, kebijakan 
kualitatif atau variabel model hasil penelitian. 
Kesimpulan berisikan naskah teks paragraf atau 
narasi dan tidak diperkenankan adanya gambar, 
persamaan (equation), dan tabel. 
UCAPAN TERIMA KASIH 
Terimakasih disampaikan kepada Lembaga 
Penelitian 
Pengabdian 
Masyarakat 
(LPPM) 
Universitas Udayana, Program Studi Teknologi 
Informasi dan Fakultas Teknik Universitas Udayana 
yang telah membantu terlaksananya penelitian ini. 
DAFTAR PUSTAKA 
[1] 
[2] 
Satgas Penanganan COVID-19. 2020. Data 
Sebaran. https://covid19.go.id/. [Nov, 19, 
2020]. 
Kementerian Pariwisata dan Ekonomi Kreatif. 
2020. Panduan Pelaksanaan Kebersihan, 
Kesehatan, Keselamatan, dan Kelestarian 
Lingkungan di Restoran/Rumah Makan Edisi 
Juli. Jakarta. 
8 
[3] 
[4] 
[5] 
[6] 
[7] 
[8] 
[9] 
Curran, J. M., & Meuter, M. L. (2005). Self
service technology adoption: comparing three 
technologies. Journal of services marketing. 
Fitzsimmons, J. A. (2003). Is self‐service the 
future of services?. Managing Service Quality: 
An International Journal. 
Tompoh, J. F., Sentinuwo, S. R., & Sinsuw, A. 
A. 
(2016). Rancang Bangun Aplikasi 
Pemesanan Menu Makanan Restoran 
Berbasis Android. Jurnal Teknik Informatika, 
9(1). 
Ummah, S. F., & Widya, M. A. A. (2018). 
Rancang Bangun Sistem Informasi E-Order di 
Pujasera Kertosono. SAINTEKBU, 10(2), 69
77. 
Alfarobi, I., Tutupoly, T. A., Safudin, M., Hadi, 
S. W., Rusdi, M. S. Z., Andriansyah, F., & 
Fandy, F. (2020). Rancang Bangun Sistem 
Informasi 
Pemesanan 
Kopi 
dengan 
Menggunakan Metode Waterfall. IJNS
Indonesian Journal on Networking and 
Security, 9(1). 
Prastio, C. E. (2018). Aplikasi Self-Service 
Menu Menggunakan Metode Scrum Berbasis 
Android. PETIR: Jurnal Pengkajian dan 
Penerapan Teknik Informatika, 11(2), 203
220. 
M. S. Setiawan. Analisis Tingkat Usabilitas 
Menggunakan 
Metode 
Performance 
Measurement dan System Usability Scale 
(SUS) pada Aplikasi E-Commerce Indomaret 
dan Alfamart., vol. 1 no. 1, pp. 209-336. 
2021. 
[10] Pressman, R. Rekayasa Perangkat Lunak: 
Pendekatan Praktisi Buku 1. Yogyakarta, 
ANDI, 2015. 
[11] Sanjaya, M. R., Saputra, A., Kurniawan, D. 
Penerapan Metode System Usability Scale 
(Sus) Perangkat Lunak Daftar Hadir di 
Pondok Pesantren Miftahul Jannah Berbasis 
Website. Jurnal Politeknik Caltex Riau, 7(1), 
120-132. 2021.  
H  a  l  a  m  a  n 