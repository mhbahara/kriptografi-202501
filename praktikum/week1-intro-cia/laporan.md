# Laporan Praktikum Kriptografi
Minggu ke-: X  
Topik: [PRAKTIKUM 1]  
Nama: [Zalsabilah nur aeni]  
NIM: [230202793]  
Kelas: [5IKKA]  

---

 1. Tujuan
**1.Menjelaskan sejarah dan evolusi kriptografi dari masa klasik hingga modern.
2.Menyebutkan prinsip Confidentiality, Integrity, Availability (CIA) dengan benar.
3.Menyimpulkan peran kriptografi dalam sistem keamanan informasi modern.
4.Menyiapkan repositori GitHub sebagai media kerja praktikum.
---

## 2. Dasar Teori
Cipher klasik adalah metode penyandian pesan yang digunakan sebelum munculnya teknologi komputer modern. Prinsipnya yaitu mengubah huruf-huruf dalam teks asli (plaintext) menjadi huruf lain (ciphertext) menggunakan pola tertentu agar pesan sulit dipahami oleh pihak lain. Contoh cipher klasik yang terkenal adalah Caesar Cipher yang menggeser huruf beberapa langkah, dan Vigenère Cipher yang menggunakan kunci kata untuk menentukan pergeseran. Meskipun sederhana, metode ini menjadi dasar perkembangan kriptografi selanjutnya.

Konsep modular aritmetika merupakan perhitungan dengan hasil yang dibatasi oleh suatu bilangan tertentu yang disebut modulus. Misalnya, 
10mod3=1, karena sisa hasil bagi 10 dibagi 3 adalah 1. Dalam kriptografi, konsep ini digunakan untuk menjaga agar hasil pergeseran huruf tetap berada dalam alfabet. Modular aritmetika juga menjadi dasar bagi berbagai algoritma kriptografi modern seperti RSA dan Diffie-Hellman.

Hubungan antara cipher klasik dan modular aritmetika dapat dilihat dari cara enkripsinya. Misalnya pada Caesar Cipher digunakan rumus 
𝐶=(𝑃+𝑘)mod26C=(P+k)mod26, di mana P adalah huruf asli, k jumlah pergeseran, dan C huruf hasil enkripsi. Dengan sistem ini, jika pergeseran melebihi jumlah huruf alfabet, hasilnya akan kembali ke awal secara otomatis. Jadi, modular aritmetika berperan penting dalam menjaga agar proses enkripsi dan dekripsi berjalan dengan benar.

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
# encrypt.py

def encrypt(text, key):
    result = ""
    for char in text:
        if char.isalpha():  # hanya huruf yang dienkripsi
            shift = 65 if char.isupper() else 97
            result += chr((ord(char) - shift + key) % 26 + shift)
        else:
            result += char  # karakter non-huruf tidak berubah
    return result

# Contoh penggunaan
plaintext = input("Masukkan teks yang ingin dienkripsi: ")
key = int(input("Masukkan kunci (angka): "))

ciphertext = encrypt(plaintext, key)
print("Hasil enkripsi:", ciphertext)
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
![Hasil Input](screenshots 1/input.png)
![Hasil Output](screenshots 2/output.png)
)

---

## 7. Jawaban Pertanyaan
1. Tokoh yang dianggap sebagai bapak kriptografi modern
Tokoh yang dikenal sebagai bapak kriptografi modern adalah Claude E. Shannon tokoh tersebut  merupakan ilmuan yang pertama kali mengembangkan dasar-dasar teori informasi dan keamanan data melalui penelitiannya yang berjudul “Communication Theory of Secrecy Systems” pada tahun 1949. pemikiran Shannon menjadi dasar berkembangnya sistem kriptografi modern yang digunakan sampai sekarang.
2. Algoritma kunci publik yang populer digunakan saat ini
Beberapa algoritma kunci publik yang paling populer dan banyak digunakan saat ini antara lain:
•	RSA (Rivest–Shamir–Adleman)
•	ECC (Elliptic Curve Cryptography)
•	DSA (Digital Signature Algorithm)
•	Diffie–Hellman Key Exchange
Algoritma-algoritma tersebut biasanya digunakan untuk menjaga keamanan data digital, seperti dalam transaksi online, enkripsi pesan, serta tanda tangan digital.
3. Perbedaan utama antara kriptografi klasik dan kriptografi modern
Perbedaan mendasar antara kriptografi klasik dan modern terletak pada cara kerja dan tingkat keamanannya. Kriptografi klasik umumnya masih menggunakan teknik sederhana seperti penggantian huruf (substitution) dan pergeseran (transposition), serta hanya menggunakan satu kunci yang sama untuk enkripsi dan dekripsi.
Sementara itu, kriptografi modern menggunakan algoritma matematika yang lebih kompleks dan sudah berbasis komputer. Dalam kriptografi modern, dikenal adanya sistem kunci publik dan kunci privat (asimetris) yang membuat keamanannya jauh lebih tinggi.


## 8. Kesimpulan
**Berdasarkan kode pada gambar tersebut, dapat disimpulkan bahwa program Python tersebut merupakan implementasi sederhana dari Caesar Cipher, yaitu salah satu jenis cipher klasik yang digunakan untuk melakukan enkripsi teks dengan cara menggeser huruf-huruf pada teks asli berdasarkan kunci (key) tertentu.

Program bekerja dengan memeriksa setiap karakter pada teks. Jika karakter tersebut merupakan huruf, maka huruf tersebut akan digeser sesuai nilai kunci menggunakan konsep modular aritmetika agar hasilnya tetap berada dalam rentang alfabet (A–Z atau a–z). Sementara itu, karakter non-huruf seperti angka atau tanda baca tidak akan diubah.

Secara keseluruhan, program ini menunjukkan bagaimana algoritma Caesar Cipher dapat diterapkan menggunakan bahasa Python dengan logika sederhana, dan bagaimana modular aritmetika digunakan untuk mengatur pergeseran huruf secara berulang dalam proses enkripsi.
---**

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
Author: Zalsabilah nur aeni <zalsabilahna@gmail.com>
Date:   2025-09-20

    week2-cryptosystem: implementasi Caesar Cipher dan laporan )
```
