Nama: Windi Sulaiman Ismansa
NIM: H2H024005
Shift Awal: B
Shift Akhir: A

1.5 Pertanyaan Praktikum
1. Pada kondisi apa program masuk ke blok if?
   Program masuk ke blok if ketika nilai timeDelay <= 100. Maksudnya, setelah LED berkedip cukup cepat (delay sudah berkurang dari 1000ms hingga mencapai 100ms atau kurang), program akan masuk ke blok tersebut — menjalankan jeda 3 detik lalu mereset timeDelay kembali ke 1000.
2. Pada kondisi apa program masuk ke blok else?
   Program masuk ke blok else ketika timeDelay > 100. Selama kondisi itu terpenuhi, setiap akhir siklus kedip akan mengurangi timeDelay sebesar 100ms, sehingga LED semakin cepat berkedip dari waktu ke waktu.
3. Apa fungsi dari perintah delay(timeDelay)?
   delay(timeDelay) berfungsi untuk menghentikan eksekusi program selama timeDelay milidetik. Digunakan dua kali dalam satu siklus: pertama saat LED menyala, kedua saat LED mati — sehingga lamanya LED ON dan OFF sama persis, dan bersama-sama menentukan kecepatan kedip.
4. Jika program yang dibuat memiliki alur mati → lambat → cepat → reset (mati), ubah menjadi LED tidak langsung reset → tetapi berubah dari cepat → sedang → mati dan berikan penjelasan disetiap baris kode nya dalam bentuk README.md!

   <img width="502" height="768" alt="image" src="https://github.com/user-attachments/assets/dcb13c83-5e3b-4e41-b611-41a7ce172404" />

1.6 Pertanyaan Praktikum
1. Schematic 5 LED Running

   <img width="502" height="300" alt="runningLED" src="https://github.com/user-attachments/assets/a3df6734-de75-4382-a1eb-51e2101ce84d" />

2. Bagaimana program membuat efek LED berjalan kiri ke kanan?
   -Loop for pertama menjalankan ledPin dari 2 naik ke 7 (ledPin++). Setiap iterasi menyalakan satu pin dengan digitalWrite(ledPin, HIGH), menunggu timer ms, lalu mematikannya. Karena hanya satu LED menyala pada satu waktu dan urutannya naik, efek visualnya adalah cahaya berjalan dari kiri (pin 2) ke kanan (pin 7).
3. Bagaimana program membuat LED kembali dari kanan ke kiri?
   Loop for kedua menjalankan ledPin dari 7 turun ke 2 (ledPin--). Dengan urutan terbalik, LED yang menyala berpindah dari pin 7 kembali ke pin 2 — sehingga efeknya adalah LED berjalan dari kanan ke kiri, menciptakan gerakan bolak-balik seperti efek Knight Rider.
4. Buatkan program agar LED menyala tiga LED kanan dan tiga LED kiri secara bergantian dan berikan penjelasan disetiap baris kode nya dalam bentuk README.md!

   <img width="502" height="768" alt="image" src="https://github.com/user-attachments/assets/2fe11f7c-388a-4ceb-a08f-63b263faca55" />

1.7 Pertanyaan Analisis
1. Uraian Hasil Setiap Percobaan
 - Percobaan 1 — LED Blink dengan Percepatan Bertahap
Pada percobaan ini digunakan satu buah LED yang terhubung ke pin 6 dengan variabel *timeDelay* sebagai pengatur jeda waktu. Nilai *timeDelay* akan berkurang sebesar 100 ms pada setiap siklus melalui blok *else*, sehingga kedipan LED berubah dari lambat (1000 ms) menjadi semakin cepat hingga mencapai 100 ms. Setelah mencapai batas tersebut, program memberikan jeda selama 3 detik sebelum mengatur ulang nilai ke kondisi awal.  
Pada versi modifikasi, logika dibalik, di mana *timeDelay* dimulai dari 100 ms dan bertambah 100 ms setiap siklus hingga mencapai 1000 ms. Perubahan ini menghasilkan pola kedipan dari cepat, kemudian melambat, hingga berhenti sejenak, lalu kembali ke kondisi awal.

- Percobaan 2 — LED Running
Percobaan kedua memanfaatkan enam LED yang terhubung pada pin 2 hingga 7, dengan proses inisialisasi dilakukan menggunakan satu perulangan *for*. Program menggunakan dua buah loop secara berurutan, yaitu loop menaik dan menurun, untuk menciptakan efek cahaya yang bergerak bolak-balik.
Pada modifikasi yang dilakukan, LED dikelompokkan menjadi dua bagian, yaitu sisi kiri (pin 2–4) dan sisi kanan (pin 5–7). Kedua kelompok tersebut dinyalakan secara bergantian, sehingga menghasilkan efek visual berupa dua blok cahaya yang aktif secara bergantian antara kiri dan kanan.

2. Pengaruh Struktur Perulangan terhadap Jalannya Program
Struktur perulangan seperti *for* dan *while* berperan penting dalam mengeksekusi instruksi secara berulang tanpa perlu menuliskan kode yang sama berkali-kali. Dalam praktikum ini, penggunaan *for* memungkinkan inisialisasi enam pin dilakukan secara ringkas dan efisien.
Selain itu, arah perulangan juga memengaruhi perilaku LED, di mana iterasi menaik menghasilkan pergerakan ke arah kanan, sedangkan iterasi menurun mengarah ke kiri. Secara konsep, *for* lebih sesuai digunakan ketika jumlah pengulangan telah diketahui, sedangkan *while* digunakan untuk kondisi yang bergantung pada perubahan nilai tertentu, seperti pembacaan sensor.  
Dengan demikian, perulangan menjadi dasar utama dalam menjaga program Arduino tetap berjalan secara kontinu dan terstruktur.

4. Cara Kerja Percabangan (if-else) dalam Menentukan Kondisi LED
Percabangan *if-else* berfungsi sebagai mekanisme pengambilan keputusan dengan cara mengevaluasi suatu kondisi bernilai benar atau salah. Berdasarkan hasil evaluasi tersebut, program akan menjalankan salah satu blok kode yang sesuai.  
Pada praktikum ini, kondisi `if (timeDelay <= 100)` diperiksa pada setiap akhir siklus kedipan. Jika kondisi terpenuhi, maka nilai *timeDelay* akan diatur ulang, sedangkan jika tidak, nilainya akan dikurangi sebesar 100 ms. Penempatan logika ini setelah satu siklus selesai bertujuan agar proses kedipan tidak terganggu.  

5. Kombinasi Perulangan dan Percabangan untuk Sistem yang Responsif
Perulangan dan percabangan merupakan dua konsep yang saling melengkapi dalam membangun sistem Arduino yang responsif. Perulangan memastikan program berjalan secara terus-menerus dalam memantau kondisi, sementara percabangan menentukan tindakan yang harus diambil berdasarkan kondisi tersebut.  
Dalam praktikum ini, kombinasi keduanya terlihat jelas, di mana *for* digunakan untuk mengatur urutan LED, sedangkan *if-else* mengatur perubahan kecepatan kedipan.  
Pada penerapan yang lebih kompleks, seperti sistem lampu otomatis berbasis sensor cahaya atau alarm suhu, pola yang sama digunakan. Program akan membaca data secara berkala melalui perulangan, kemudian mengambil keputusan menggunakan percabangan.  
Untuk meningkatkan responsivitas sistem, penggunaan fungsi `millis()` lebih dianjurkan dibandingkan `delay()`, karena `delay()` dapat menghentikan sementara proses lain, sedangkan `millis()` memungkinkan pengaturan waktu tanpa menghambat eksekusi program secara keseluruhan.
