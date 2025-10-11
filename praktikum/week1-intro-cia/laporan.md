# Laporan Praktikum Kriptografi
Minggu ke-: 1 
Topik: Sejarah Kriptografi & Prinsip CIA
Nama: Nanda Erdi Pratama  
NIM: [230202770]
Kelas: [5IKRB]  

---

## 1. Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:

Menjelaskan sejarah dan evolusi kriptografi dari masa klasik hingga modern.
Menyebutkan prinsip Confidentiality, Integrity, Availability (CIA) dengan benar.
Menyimpulkan peran kriptografi dalam sistem keamanan informasi modern.
Menyiapkan repositori GitHub sebagai media kerja praktikum.

---

## 2. Dasar Teori

Dasar-Dasar Cipher Klasik dan Kriptografi Simetris
Teori dasar cipher klasik seperti Caesar dan Vigenère berakar pada dua konsep operasi: substitusi dan transposisi. Caesar Cipher adalah bentuk murni substitusi, di mana setiap huruf dalam plaintext digantikan oleh huruf lain dalam alfabet. Operasi ini secara matematis mengandalkan aritmetika modular, khususnya modulo 26 (jumlah huruf alfabet). Misalnya, enkripsi Caesar dengan geseran 3 dapat dinyatakan sebagai `C = (P + 3) mod 26`, di mana `C` adalah huruf ciphertext dan `P` adalah huruf plaintext. Cipher Vigenère memperluas ini dengan menggunakan substitusi polialfabetik, di mana multiple cipher substitusi sederhana (seperti Caesar) diterapkan secara bergantian berdasarkan huruf-huruf dalam sebuah kunci. Kekuatan dan kelemahan cipher-cipher ini pada akhirnya dapat dianalisis melalui analisis frekuensi, yang memanfaatkan fakta bahwa dalam suatu bahasa, huruf atau kombinasi huruf tertentu muncul dengan frekuensi yang dapat diprediksi.

Transisi ke Kriptografi Modern: Kunci Publik dan Prinsip Kerckhoffs
Lompatan teori terbesar terjadi dengan pergeseran dari kriptografi simetris (kunci rahasia bersama) ke kriptografi asimetris (kunci publik). Fondasinya adalah Prinsip Kerckhoffs, yang menyatakan bahwa suatu sistem cipher harus aman meskipun segala hal tentang sistem, kecuali kuncinya, diketahui publik. Prinsip ini memastikan keamanan tidak bergantung pada kerahasiaan algoritma yang rentan terbongkar. Kriptografi kunci publik, seperti RSA, mengatasi masalah distribusi kunci yang menjadi kelemahan utama sistem simetris. Teori inti RSA terletak pada teori bilangan, khususnya kesulitan memfaktorkan bilangan bulat besar yang merupakan hasil kali dua bilangan prima besar. Operasi enkripsi dan dekripsi RSA sendiri juga menggunakan fungsi aritmetika modular yang one-way: mudah dihitung dalam satu arah (enkripsi), tetapi sangat sulit dibalik (dekripsi) tanpa informasi rahasia (kunci privat), yang dalam hal ini adalah bilangan prima faktor tersebut.

---

## 3. Alat dan Bahan
(- Python 3.x  
- Visual Studio Code 
- Git dan akun GitHub  
  )

---

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
- Pertanyaan 1: Claude Shannon secara luas diakui sebagai bapak kriptografi modern. Kontribusinya yang paling signifikan adalah memberikan landasan matematis yang kuat pada bidang tersebut, beralih dari pendekatan linguistik sebelumnya ke metode yang lebih ketat dan dapat diandalkan. 
- Pertanyaan 2: Algoritma kunci publik yang populer digunakan saat ini adalah RSA (Rivest–Shamir–Adleman) dan ECC (kriptografi kurva eliptik).
- Pertanyaan 3: Perbedaan utama adalah kriptografi klasik menggunakan metode manual (pena dan kertas) yang beroperasi pada mode karakter dan sangat mudah dipecahkan, sedangkan kriptografi modern memanfaatkan komputer dengan algoritma kompleks yang beroperasi pada mode bit untuk keamanan yang jauh lebih kuat.  
)
---

## 8. Kesimpulan
Kesimpulan Materi: Sejarah Kriptografi & Prinsip CIA

Sejarah kriptografi menunjukkan sebuah perkembangan yang dinamis, dari seni rahasia menjadi ilmu pengetahuan yang kompleks, yang didorong oleh perlombaan senjata antara pembuat dan pemecah kode.
Dari Simpel ke Kompleks:Kriptografi berevolusi dari teknik substitusi dan transposisi manual (seperti Scytale, Caesar Cipher) menjadi algoritma matematis yang sangat rumit yang dijalankan oleh komputer.
Dari Kerahasiaan ke Keamanan Menyeluruh:Awalnya fokus hanya pada kerahasiaan (menyembunyikan isi pesan). Seiring waktu, terutama di era digital, kriptografi berkembang untuk menjamin integritas, autentikasi, dan non-repudiasi (contoh: tanda tangan digital).
Peran Kunci yang Berubah: Dari being part of the algorithm (cipher klasik) menjadi elemen terpisah yang sangat vital. Prinsip Kerckhoffs menegaskan bahwa keamanan sistem harus terletak pada kerahasiaan kunci, bukan kerahasiaan algoritma.Revolusi Digital:** Penemuan kriptografi kunci publik (asimertris) oleh Diffie-Hellman dkk. adalah lompatan besar, yang memecahkan masalah distribusi kunci simetris dan membuka pintu bagi keamanan e-commerce, internet, dan komunikasi modern.Perang vs Perlindungan:Sepanjang sejarah, kriptografi telah menjadi alat strategis dalam peperangan, diplomasi, dan intelijen. Hari ini, kriptografi adalah tameng penting untuk melindungi privasi, data keuangan, dan kedaulatan digital setiap individu dan organisasi.Inti dari sejarah kriptografi adalah: Apa yang dulunya adalah alat bagi kalangan terbatas (militer, diplomat) kini telah menjadi kebutuhan dasar untuk melindungi kemanusiaan di dunia digital.

Kesimpulan Prinsip CIA Triad

Prinsip CIA Triad (Confidentiality, Integrity, Availability) adalah fondasi dan tujuan utama dari segala upaya keamanan informasi, termasuk penerapan kriptografi.
C (Confidentiality / Kerahasiaan): Memastikan informasi hanya dapat diakses oleh pihak yang berwenang. Kriptografi adalah tulang punggung prinsip ini, melalui teknik enkripsi.
I (Integrity / Integritas):Memastikan informasi tidak diubah, dirusak, atau dirusak oleh pihak yang tidak berwenang selama transmisi atau penyimpanan. Kriptografi mendukungnya melalui hash function dan tanda tangan digital.
A (Availability / Ketersediaan): Memastikan informasi dan sistem dapat diakses oleh pihak yang berwenang ketika dibutuhkan. Meskipun lebih terkait dengan keamanan jaringan dan redundansi sistem, serangan yang memanfaatkan kriptografi (seperti Ransomware) justru mengancam Availability dengan mengenkripsi data dan meminta tebusan.

Inti dari CIA Triad adalah: Sebuah sistem informasi yang aman harus secara seimbang menjamin ketiga pilar ini. Mengabaikan satu saja dapat menyebabkan kerugian besar.**
 Kesimpulan Hubungan Keduanya
Sejarah Kriptografi dan Prinsip CIA adalah dua sisi dari koin yang sama.
Kriptografi adalah "Bagaimana"-nya (How), yaitu alat dan teknik yang dikembangkan sepanjang sejarah untuk mewujudkan tujuan keamanan.
CIA Triad adalah "Mengapa"-nya(Why), yaitu kerangka kerja filosofis yang mendefinisikan apa yang ingin kita capai dengan alat-alat tersebut.

Hubungan Simbiosis:
Kebutuhan untuk mencapai Confidentiality dan Integrity dalam dunia digital yang rentan telah mendorong evolusi kriptografi menjadi lebih kuat dan serba guna.
Di sisi lain, penemuan-penemuan dalam kriptografi (seperti kriptografi kunci publik) memungkinkan kita untuk mendefinisikan dan menerapkan prinsip Integrity dan Authentication dengan cara yang sebelumnya tidak mungkin.

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
