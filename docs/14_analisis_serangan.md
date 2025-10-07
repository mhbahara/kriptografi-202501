# 14 Analisis Serangan Kriptografi

## Tujuan Pembelajaran
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:  
1. Mengidentifikasi jenis serangan pada sistem informasi nyata.  
2. Mengevaluasi kelemahan algoritma kriptografi yang digunakan.  
3. Memberikan rekomendasi algoritma kriptografi yang sesuai untuk perbaikan keamanan.  

---

## Capaian Kegiatan
Pada akhir sesi ini mahasiswa menghasilkan:  
- Laporan studi kasus analisis serangan sistem nyata.  
- Rekomendasi solusi/algoritma pengganti.  
- Commit Git dengan format `week14-analisis-serangan`.  

---

## Persiapan Lingkungan
1. Buat folder berikut:  
   ```
   praktikum/week14-analisis-serangan/
   ├─ screenshots/
   └─ laporan.md
   ```
2. Diskusikan studi kasus sistem nyata (contoh: serangan brute force pada password lemah, serangan MITM pada komunikasi TLS, serangan replay pada protokol autentikasi).  
3. Materi rujukan: Stallings (2017), Bab 16.  

---

## Panduan Langkah demi Langkah

### Langkah 1 — Identifikasi Serangan
- Pilih salah satu kasus nyata serangan kriptografi (contoh: serangan brute force pada hash MD5, kebocoran SSL/TLS, serangan dictionary password).  
- Identifikasi vektor serangan dan penyebab kelemahan.  

---

### Langkah 2 — Evaluasi Kelemahan
- Analisis kelemahan algoritma yang digunakan.  
- Apakah kelemahan ada pada algoritma kriptografi, implementasi, atau konfigurasi sistem?  

---

### Langkah 3 — Rekomendasi Solusi
- Usulkan algoritma atau mekanisme yang lebih aman.  
  - Contoh: mengganti MD5 → SHA-256, RSA lama → ECC, password plaintext → bcrypt/scrypt/Argon2.  
- Jelaskan alasan pemilihan algoritma dan dampaknya terhadap keamanan sistem.  

---

## Pertanyaan Diskusi
1. Mengapa banyak sistem lama masih rentan terhadap brute force atau dictionary attack?  
2. Apa bedanya kelemahan algoritma dengan kelemahan implementasi?  
3. Bagaimana organisasi dapat memastikan sistem kriptografi mereka tetap aman di masa depan?  

---

## Tugas yang Dikumpulkan
1. Laporan `laporan.md` berisi:  
   - Studi kasus serangan nyata.  
   - Evaluasi kelemahan sistem/algoritma.  
   - Rekomendasi solusi yang relevan.  
   - Jawaban pertanyaan diskusi.  
2. Bukti screenshot (misalnya percobaan brute force sederhana, atau contoh hash lemah).  

Struktur akhir folder:
```
praktikum/week14-analisis-serangan/
 ├─ screenshots/
 │   └─ hasil.png
 └─ laporan.md
```

Commit dengan pesan:  
```
week14-analisis-serangan
```

---

## Rubrik Penilaian
Mengacu pada RPS Minggu 14: **Total bobot 5% (Analisis serangan sistem nyata 3%, Laporan rekomendasi Git 2%)**  

| Aspek Penilaian          | Bobot | Kriteria                                                               |
|---------------------------|-------|------------------------------------------------------------------------|
| Analisis serangan nyata   | 3%    | Kasus nyata jelas, analisis kelemahan tepat, ada bukti/screenshot      |
| Laporan rekomendasi Git   | 2%    | Commit sesuai format, laporan rapi, rekomendasi solusi relevan & logis |
| Evidence Git & repo       | -     | Struktur repo rapi, history commit sesuai instruksi                    |

---