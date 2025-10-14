# Laporan Praktikum Kriptografi
Minggu ke-: 1 
Topik: intp CIA  
Nama: AZKIYA FE SABELLA  
NIM: 230202802  
Kelas: IKKA  

---

## 1. Tujuan
Pemahaman dasar tentang sejarah perkembangan kriptografi. mulai dari kripto klasik yang digunakan pada romawi kuno hingga kriptografi modern seperti blokchain.

## 2. Dasar Teori
Kriptografi klasik
awal mula kerahasian informasi sudah menjadi keunggulan. manusia sudah mulai memanfaatkan informasi untuk mendapatkan keuntungan. pada zaman mesir kuno digunakan oleh Julius Caesar untuk menginformasikan pesan rahasia dalam sebuah perang. dan terus berkambang pada masa itu hingga terciptanya teknik kriptografi yang sulit dipecahkan pada masa itu. diantaranya kriptografi pada masa itu:

Caesar Chiper
Metode enkripsi yang dilakukan pada raja mesir yaitu Julius Caesar untuk mengirimkan pesan rahasia pada militernya. cara ini memiliki kunci agar bisa dibaca atau diterjemahkan. metode ini berkerja dengan menggeser huruf alfabet ke kanan atau ke kiri dengan jumlah pergeseran yang sudah ditentukan diawal.

Scytale Spartan
Telah digunakan oleh orang Sparta untuk merahasiakan pesan penting. dengan menggunakan tongkat yang berdiamter sama dan sebuah kertas metode ini bisa jadi cara yang cukup aman. melihat dari masa itu pesan yang dikertas secara naluri orang akan membacanya langsung. mereka tidak tau kalo huruf yang di gulungan itu sudah acak. tapi dengan gulunan benda yang sama pesan baru bisa terdekripsi. metode ini menggunakan alat fisik untuk ekripsi atau dekripsi.

Vigenere Ciper
Metode ini merupakan lanjutan dari caesar chiper. menggunakan key yang dikombinasikan dari huruf alfabet. metode ini termasuk metode yang mudah diimlmentasikan dengan keamanan yang cukup sulit di dekrip.

Kriptografi Modern
Era dimana komputer menjadi senjata paling mematikan seteelah senapan. perang tanpa suara—perang menggunakan informasi dan otak. peperangan tidak lagi soal menembak dengan senapan tapi perang untuk perbanyak informasi.

Mesin Enigma
Mesin yang dikembangkan oleh oran jerman Arthur Scherbius sebagai penemu mesin ini. dikembangkan untuk keperluan militer perang dunia 2. mengirm pesan rahasia ke sarang musuh sangat rentan informasi terputus atau terdengar di tengah jalan. tentara jerman menggunakan alat rahasia yang dinamakana enigma. mesin enkripsi pertama yang menggunakan teknologi komputer. pada masa itu tentara inggris kualahan mengatasi mesin ini. dan akhirnya bisa di pecahkan oleh alan turing pada masa itu.

RSA
Sebuah algoritma yang ditemukan oleh Ron Rivest, Andi Shamir, dan Leonardo Adleman. metode ini memiliki dua kunci, privat dan public. metode ini menarik karena kunci disebarluaskan. siapapun dapat mengetahui kunci dan menggunaakanya. singkatnya gini, ibarat memiliki sebuah gembok dan kuncinya. kemudian kunci disimpan dan gembok disebarluaskan. gembok ini bebas dicopy. ketika gembok ini digunakan untuk mengunci sesuatu hanya pemilik kunci yang bisa membukanya. yang aku tangkap kunci publik dihasilkan dari kunci privat. dan kunci publuk ini digunakn untuk mengunci brankas atau file. tapi tidak bisa untuk membuka kunci. hanya menggunakan kunci privat untuk bisa membukanya.

CIA
Confidentiality (Kerahasiaan)
Penjelasan: Menjaga agar data hanya dapat diakses oleh pihak yang berwenang dan mencegah akses oleh pihak yang tidak berhak. Contoh:

Penerapan pengiriman pesan end to end seperti whatsApp. Hanya pengirim dan penerima yang bisa membaca isi pesan. Bahkan WhatsApp atau pihak ketiga (termasuk peretas) tidak dapat mengakses konten percakapan tersebut.

Integrity (Integritas)
Penjelasan: Memastikan bahwa data tidak diubah, dihapus, atau dirusak secara tidak sah selama disimpan, diproses, atau dikirim. Contoh:

Penerapan signature dan hase pada sistem perbankan untuk verefikasi transaksi. Misalnya, saat Anda mentransfer uang, sistem memastikan jumlah dan rekening tujuan tidak diubah di tengah jalan oleh peretas. Jika ada perubahan, transaksi akan ditolak.

Availability (Ketersediaan)
Penjelasan: Menjamin bahwa sistem, layanan, dan data tersedia dan dapat diakses oleh pengguna sah kapan pun dibutuhkan. Contoh:

Sistem e-commerce seperti Tokopedia dan Shopee menggunakan sever cadangan dan proteksi DDoS Saat ada lonjakan pengunjung di masa promo (misalnya Harbolnas), sistem tetap berjalan lancar dan tidak down, sehingga pelanggan tetap bisa berbelanja.


## 3. Alat dan Bahan
(- Python 3.x  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Library tambahan (misalnya pycryptodome, jika diperlukan)  )

## 4. Langkah Percobaan
(Tuliskan langkah yang dilakukan sesuai instruksi.  
Contoh format:
1. Membuat file `caesar_cipher.py` di folder `praktikum/week2-cryptosystem/src/`.
2. Menyalin kode program dari panduan praktikum.
3. Menjalankan program dengan perintah `python caesar_cipher.py`.)

---

## 5. Source Code
(Salin kode program utama yang dibuat atau dimodifikasi.  
Gunakan blok kode:

```python
# contoh potongan kode
def encrypt(text, key):
    return ...
```
)

---

## 6. Hasil dan Pembahasan
(- Lampirkan screenshot hasil eksekusi program (taruh di folder `screenshots/`).  
- Berikan tabel atau ringkasan hasil uji jika diperlukan.  
- Jelaskan apakah hasil sesuai ekspektasi.  
- Bahas error (jika ada) dan solusinya. 

Hasil eksekusi program Caesar Cipher:

![Hasil Eksekusi](screenshots/output.png)
![Hasil Input](screenshots/input.png)
![Hasil Output](screenshots/output.png)
)

---

## 7. Jawaban Pertanyaan
(Jawab pertanyaan diskusi yang diberikan pada modul.  
- Pertanyaan 1: …  
- Pertanyaan 2: …  
)
---

## 8. Kesimpulan
(Tuliskan kesimpulan singkat (2–3 kalimat) berdasarkan percobaan.  )

---

## 9. Daftar Pustaka
(Cantumkan referensi yang digunakan.  
Contoh:  
- Katz, J., & Lindell, Y. *Introduction to Modern Cryptography*.  
- Stallings, W. *Cryptography and Network Security*.  )

---

## 10. Commit Log
(Tuliskan bukti commit Git yang relevan.  
Contoh:
```
commit abc12345
Author: Nama Mahasiswa <email>
Date:   2025-09-20

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
