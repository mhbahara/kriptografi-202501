# 12 Aplikasi TLS & E-commerce

## Tujuan Pembelajaran
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:  
1. Menganalisis penggunaan kriptografi pada **email** dan **SSL/TLS**.  
2. Menjelaskan enkripsi dalam transaksi **e-commerce**.  
3. Mengevaluasi isu **etika & privasi** dalam penggunaan kriptografi di kehidupan sehari-hari.  

---

## Capaian Kegiatan
Pada akhir sesi ini mahasiswa menghasilkan:  
- Laporan studi kasus tentang penerapan SSL/TLS pada email dan e-commerce.  
- Analisis isu privasi dan etika penggunaan kriptografi.  
- Commit Git dengan format `week12-aplikasi-tls`.  

---

## Persiapan Lingkungan
1. Buat folder berikut:  
   ```
   praktikum/week12-aplikasi-tls/
   ├─ screenshots/
   └─ laporan.md
   ```
2. Siapkan koneksi internet untuk mengamati penggunaan SSL/TLS (misalnya HTTPS pada browser).  
3. Materi rujukan: Stallings (2017), Bab 15.  

---

## Panduan Langkah demi Langkah

### Langkah 1 — Analisis SSL/TLS pada Email & Web
- Gunakan browser (Chrome/Firefox) untuk mengecek **sertifikat digital** pada website e-commerce (contoh: Tokopedia, Shopee, Bukalapak).  
- Catat informasi berikut:  
  - Issuer CA (Certificate Authority).  
  - Masa berlaku sertifikat.  
  - Algoritma enkripsi yang digunakan (RSA, AES, dll).  
- Bandingkan perbedaan antara website **dengan HTTPS** dan **tanpa HTTPS**.  

---

### Langkah 2 — Studi Kasus E-commerce
- Analisis bagaimana enkripsi digunakan untuk melindungi transaksi online (misalnya saat login atau melakukan pembayaran).  
- Diskusikan potensi ancaman jika TLS tidak digunakan (contoh: serangan Man-in-the-Middle).  

---

### Langkah 3 — Analisis Etika & Privasi
- Identifikasi isu privasi dalam penggunaan email terenkripsi (PGP, S/MIME).  
- Diskusikan dilema etika:  
  - Apakah perusahaan boleh melakukan dekripsi email karyawan untuk audit?  
  - Bagaimana kebijakan pemerintah dalam pengawasan komunikasi terenkripsi?  

---

## Pertanyaan Diskusi
1. Apa perbedaan utama antara HTTP dan HTTPS?  
2. Mengapa sertifikat digital menjadi penting dalam komunikasi TLS?  
3. Bagaimana kriptografi mendukung privasi dalam komunikasi digital, tetapi sekaligus menimbulkan tantangan hukum dan etika?  

---

## Tugas yang Dikumpulkan
1. Laporan `laporan.md` berisi:  
   - Studi kasus penerapan SSL/TLS (email & e-commerce).  
   - Screenshot sertifikat digital dari minimal 2 website berbeda.  
   - Analisis isu etika & privasi.  
   - Jawaban pertanyaan diskusi.  
2. Screenshot hasil observasi TLS/SSL disimpan di folder `screenshots/`.  

Struktur akhir folder:
```
praktikum/week12-aplikasi-tls/
 ├─ screenshots/
 │   └─ sertifikat.png
 └─ laporan.md
```

Commit dengan pesan:  
```
week12-aplikasi-tls
```

---

## Rubrik Penilaian
Mengacu pada RPS Minggu 12: **Total bobot 5% (Studi kasus email/SSL/TLS 3%, Analisis privasi 2%)**  

| Aspek Penilaian       | Bobot | Kriteria                                                                 |
|------------------------|-------|--------------------------------------------------------------------------|
| Studi kasus TLS/email  | 3%    | Sertifikat berhasil dianalisis, laporan jelas, bukti screenshot ada      |
| Analisis privasi/etika | 2%    | Analisis kritis, relevan dengan kasus nyata, laporan rapi                |
| Evidence Git & repo    | -     | Commit sesuai format, struktur repo rapi, history commit jelas           |

---