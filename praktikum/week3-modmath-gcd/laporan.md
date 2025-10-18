# Laporan Praktikum Kriptografi
Minggu ke-: 3
Topik: [Modular Math (Aritmetika Modular, GCD, Bilangan Prima, Logaritma Diskrit)]
Nama: [Nanda Erdi Pratama]  
NIM: [230202770]  
Kelas: [5IKRB]  

---

## 1. Tujuan
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:  
1. Menyelesaikan operasi aritmetika modular.  
2. Menentukan bilangan prima dan menghitung GCD (Greatest Common Divisor).  
3. Menerapkan logaritma diskrit sederhana dalam simulasi kriptografi.  

---

## 2. Dasar Teori
Aritmetika modular adalah sistem bilangan sirkular yang bekerja dengan modulus tertentu, seperti operasi pada jam. Dalam kriptografi, konsep ini menjadi fondasi cipher klasik seperti Caesar cipher, dimana enkripsi dinyatakan sebagai C ≡ (P + k) mod 26 dan dekripsi sebagai P ≡ (C - k) mod 26. Operasi modular memastikan bahwa hasil perhitungan selalu berada dalam rentang terbatas, sehingga cocok untuk merepresentasikan huruf alfabet atau bit data. Konsep matematika lain yang vital dalam kriptografi modern meliputi GCD (Greatest Common Divisor) untuk menentukan kunci relatif prima, bilangan prima sebagai fondasi sistem asimetris seperti RSA, dan logaritma diskrit yang menjadi basis keamanan protokol pertukaran kunci Diffie-Hellman. Sifat-sifat matematis ini dimanfaatkan untuk membangun fungsi satu-arah (one-way function) yang mudah dihitung tetapi sangat sulit dibalikkan tanpa informasi rahasia tertentu, sehingga menjamin keamanan sistem kriptografi terhadap serangan.

---

## 3. Alat dan Bahan
(- Python 3.x  
- Visual Studio Code / editor lain  
- Git dan akun GitHub  
- Library tambahan (misalnya pycryptodome, jika diperlukan)  )

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

![Hasil Eksekusi](Screenshots/Eksekusi.png)
![Hasil Input](screenshots/input.png)
![Hasil Output](screenshots/output.png)
)

---

## 7. Jawaban Pertanyaan
(Jawab pertanyaan diskusi yang diberikan pada modul.  
- Pertanyaan 1: Fondasi Keamanan: Membentuk masalah matematika sulit (faktorisasi bilangan prima & logaritma diskrit) yang melindungi RSA, Diffie-Hellman, dan ECC. Efisiensi Komputasi: Membatasi hasil operasi dalam rentang tertentu, cocok untuk implementasi komputer yang cepat dan hemat memori. Fungsi Satu-Arah: Memudahkan enkripsi.
- Pertanyaan 2: Pentingnya Invers Modular dalam Kriptografi Kunci Publik (RSA):
1. Fungsi Dasar:
- Invers modular memungkinkan dekripsi dengan "membalikkan" proses enkripsi
- Tanpanya, pesan terenkripsi tidak bisa dikembalikan ke bentuk asli

2. Dalam Pembuatan Kunci RSA:
- Kunci privat `d` adalah invers modular dari kunci publik `e` modulo `φ(n)`
- `d ≡ e⁻¹ (mod φ(n))` atau `e × d ≡ 1 (mod φ(n))`

3. Mekanisme Kerja:
- Enkripsi: `C ≡ Mᵉ (mod n)`
- Dekripsi: `M ≡ Cᵈ (mod n)`
- Dekripsi berhasil karena `Mᵉᵈ ≡ M (mod n)` berkat sifat `e × d ≡ 1 (mod φ(n))`

4. Keamanan:
- Menciptakan "one-way trapdoor"
- Mudah menghitung `Mᵉ mod n` tapi sulit menghitung `Cᵈ mod n` tanpa `d`
- Untuk dapat `d` dari `e`, harus tahu `φ(n) = (p-1)(q-1)` yang setara dengan memfaktorkan `n` - masalah komputasi yang sangat sulit

Invers modular adalah jantung mekanisme pembalikan yang memungkinkan kriptografi kunci publik bekerja - satu kunci untuk mengunci (enkripsi), satu kunci untuk membuka kunci (dekripsi).
- Pertanyaan 3: Tantangan Utama Logaritma Diskrit untuk Modulus Besar:

1. Tidak Ada Algoritma Efisien
   - Tidak seperti perpangkatan modular yang cepat, tidak ada algoritma waktu polinomial untuk logaritma diskrit
   - Semua algoritma yang ada bersifat eksponensial atau sub-eksponensial

2. Kompleksitas Komputasi Tinggi
   - Bruteforce: O(p) → tidak praktis untuk p besar
   - Algoritma terbaik: O(√p) atau O(exp(c·(log p)¹/³)) → tetap tidak feasible untuk modulus >2048 bit

3. Kebutuhan Sumber Daya Massive
   - Membutuhkan waktu komputasi sangat lama
   - Memori besar dan jaringan komputer masif

4. Kesenjangan Komputasi
   - Maju: `g^x mod p` → cepat (waktu polinomial)
   - Mundur: cari `x` dari `g^x mod p` → sangat lambat (waktu eksponensial)

Keamanan kriptografi modern bergantung pada kesenjangan ini. Jika ditemukan algoritma cepat (seperti Algoritma Shor di komputer kuantum), sistem keamanan ini akan runtuh.
)
---

## 8. Kesimpulan
Berdasarkan percobaan dan analisis, dapat disimpulkan bahwa aritmetika modular merupakan fondasi matematis yang essential bagi kriptografi klasik maupun modern. Konsep GCD dan bilangan prima membentuk dasar keamanan sistem asimetris, sementara masalah logaritma diskrit yang sulit dipecahkan menjadi kunci pertahanan algoritma pertukaran kunci. Pemanfaatan sifat-sifat matematika ini memungkinkan pembangunan sistem kriptografi yang secara komputasi aman untuk aplikasi praktis.

Aritmetika Modular - Dasar cipher klasik (Caesar) dan modern
GCD & Bilangan Prima - Fondasi sistem asimetris seperti RSA
Logaritma Diskrit - Keamanan Diffie-Hellman dan DSA
Integrasi Simetris-Asimetris - Solusi optimal untuk keamanan & kinerja
Masalah Distribusi Kunci - Kelemahan utama simetris yang diatasi oleh asimetris

 Contoh 
Caesar Cipher: C ≡ (P + k) mod 26
Pertukaran Kunci: Diffie-Hellman menggunakan logaritma diskrit
RSA: Menggunakan faktorisasi bilangan prima yang sulit

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
commit 3f3984e2f78fd6f769c809fa774ed3ddc8c16606 (HEAD -> main, origin/main, origin/HEAD)
Author: Nanda0218 <nandaerdipratama29@gmail.com>
Date:   Thu Oct 16 12:18:29 2025 +0700

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
