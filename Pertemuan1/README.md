*Nama: Windi Sulaiman Ismansa
*NIM: H2H024005
*Shift Awal: 
*Shift Akhir:

1.5 Pertanyaan Praktikum
Pada kondisi apa program masuk ke blok if? Program masuk ke blok if ketika nilai timeDelay <= 100. Artinya, setelah LED berkedip cukup cepat (delay sudah berkurang dari 1000ms hingga mencapai 100ms atau kurang), program akan masuk ke blok tersebut — menjalankan jeda 3 detik lalu mereset timeDelay kembali ke 1000.

Pada kondisi apa program masuk ke blok else? Program masuk ke blok else ketika timeDelay > 100. Selama kondisi itu terpenuhi, setiap akhir siklus kedip akan mengurangi timeDelay sebesar 100ms, sehingga LED semakin cepat berkedip dari waktu ke waktu.

Apa fungsi dari perintah delay(timeDelay)? delay(timeDelay) berfungsi untuk menghentikan eksekusi program selama timeDelay milidetik. Digunakan dua kali dalam satu siklus: pertama saat LED menyala, kedua saat LED mati — sehingga lamanya LED ON dan OFF sama persis, dan bersama-sama menentukan kecepatan kedip.

Jika program yang dibuat memiliki alur mati → lambat → cepat → reset (mati), ubah menjadi LED tidak langsung reset → tetapi berubah dari cepat → sedang → mati dan berikan penjelasan disetiap baris kode nya dalam bentuk README.md!

