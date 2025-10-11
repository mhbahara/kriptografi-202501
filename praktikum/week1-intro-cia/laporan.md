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
