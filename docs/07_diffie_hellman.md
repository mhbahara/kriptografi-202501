# 07 Diffie-Hellman Key Exchange

## Tujuan Pembelajaran
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:  
1. Melakukan simulasi protokol **Diffie-Hellman** untuk pertukaran kunci publik.  
2. Menjelaskan mekanisme pertukaran kunci rahasia menggunakan bilangan prima dan logaritma diskrit.  
3. Menganalisis potensi serangan pada protokol Diffie-Hellman (termasuk serangan **Man-in-the-Middle / MITM**).  

---

## Capaian Kegiatan
Pada akhir sesi ini mahasiswa menghasilkan:  
- Program Python simulasi pertukaran kunci Diffie-Hellman.  
- Analisis keamanan (kelemahan dan potensi serangan).  
- Laporan singkat hasil percobaan dan analisis.  
- Commit Git dengan format `week7-diffie-hellman`.  

---

## Persiapan Lingkungan
1. Buat folder berikut:  
   ```
   praktikum/week7-diffie-hellman/
   ├─ src/
   ├─ screenshots/
   └─ laporan.md
   ```
2. Gunakan Python 3.11 atau lebih baru.  
3. Materi rujukan: Stallings (2017), Bab 10.  

---

## Panduan Langkah demi Langkah

### Langkah 1 — Simulasi Diffie-Hellman
```python
import random

# parameter umum (disepakati publik)
p = 23  # bilangan prima
g = 5   # generator

# private key masing-masing pihak
a = random.randint(1, p-1)  # secret Alice
b = random.randint(1, p-1)  # secret Bob

# public key
A = pow(g, a, p)
B = pow(g, b, p)

# exchange public key
shared_secret_A = pow(B, a, p)
shared_secret_B = pow(A, b, p)

print("Kunci bersama Alice :", shared_secret_A)
print("Kunci bersama Bob   :", shared_secret_B)
```

Ekspektasi hasil: nilai `shared_secret_A` dan `shared_secret_B` harus sama.

---

### Langkah 2 — Analisis Serangan MITM (Man-in-the-Middle)
Tambahkan simulasi sederhana:  
- Pihak ketiga (Eve) mencegat dan mengganti public key.  
- Alice dan Bob berakhir memiliki **kunci berbeda**, tetapi Eve mengetahui keduanya.  

Diskusikan hasil ini di laporan.  

---

## Pertanyaan Diskusi
1. Mengapa Diffie-Hellman memungkinkan pertukaran kunci di saluran publik?  
2. Apa kelemahan utama protokol Diffie-Hellman murni?  
3. Bagaimana cara mencegah serangan MITM pada protokol ini?  

---

## Tugas yang Dikumpulkan
1. Program Python `src/diffie_hellman.py` berisi simulasi Diffie-Hellman.  
2. Screenshot hasil eksekusi program.  
3. Laporan `laporan.md` berisi:  
   - Penjelasan mekanisme Diffie-Hellman.  
   - Hasil simulasi MITM.  
   - Jawaban pertanyaan diskusi.  

Struktur akhir folder:
```
praktikum/week7-diffie-hellman/
 ├─ src/diffie_hellman.py
 ├─ screenshots/
 │   └─ hasil.png
 └─ laporan.md
```

Commit dengan pesan:  
```
week7-diffie-hellman
```

---

## Rubrik Penilaian
Mengacu pada RPS Minggu 7: **Total bobot 5% (Simulasi 3%, Analisis keamanan Git 2%)**  

| Aspek Penilaian              | Bobot | Kriteria                                                                 |
|-------------------------------|-------|--------------------------------------------------------------------------|
| Simulasi Diffie-Hellman       | 3%    | Implementasi benar, kunci rahasia sama, kode berjalan sesuai teori       |
| Analisis keamanan & laporan   | 2%    | Diskusi kelemahan MITM, laporan rapi, commit Git sesuai format           |
| Evidence Git & repo           | -     | Struktur folder rapi, history commit sesuai instruksi                    |

---

