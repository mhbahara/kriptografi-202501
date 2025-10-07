# 01 Sejarah Kriptografi & Prinsip CIA

## Tujuan Pembelajaran
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:  
1. Menjelaskan **sejarah dan evolusi kriptografi** dari masa klasik hingga modern.  
2. Menyebutkan **prinsip Confidentiality, Integrity, Availability (CIA)** dengan benar.  
3. Menyimpulkan **peran kriptografi** dalam sistem keamanan informasi modern.  
4. Menyiapkan repositori GitHub sebagai media kerja praktikum.  

---

## Capaian Kegiatan
Pada akhir sesi ini mahasiswa menghasilkan:  
- Repositori individu GitHub `kripto-20251-<nim>` yang sudah disiapkan.  
- Ringkasan individu (1–2 halaman) mengenai sejarah kriptografi dan prinsip CIA.  
- Jawaban quiz singkat tentang sejarah kriptografi & CIA.  
- Commit pertama dengan pesan `week1-intro-cia`.  

---

## Persiapan Lingkungan
1. Pastikan akun GitHub aktif.  
2. Fork repositori template dosen:  
   ```
   https://github.com/mhbahara/kriptografi-202501
   ```
3. Ubah nama hasil fork menjadi:  
   ```
   kripto-20251-<nim>
   ```  
   Contoh: `kripto-20251-2310112345`  
4. Clone ke komputer lokal:  
   ```bash
   git clone https://github.com/<username>/kripto-20251-<nim>.git
   ```
5. Buat folder untuk tugas minggu 1:  
   ```
   praktikum/week1-intro-cia/
   ├─ screenshots/
   └─ laporan.md
   ```

---

## Panduan Langkah demi Langkah

### Langkah 1 — Ringkasan Sejarah Kriptografi
Tuliskan ringkasan (maks. 1 halaman) yang mencakup:  
- Era **kriptografi klasik** (contoh: Caesar Cipher, Vigenere).  
- Perkembangan **kriptografi modern** (contoh: AES, RSA).  
- Evolusi menuju **kriptografi kontemporer** (misalnya: blockchain, cryptocurrency).  

### Langkah 2 — Prinsip CIA
Jelaskan tiga pilar keamanan informasi:  
- **Confidentiality** → menjaga kerahasiaan data.  
- **Integrity** → menjaga keutuhan data dari modifikasi tidak sah.  
- **Availability** → menjamin ketersediaan layanan sistem.  

Tambahkan contoh nyata minimal 1 untuk tiap aspek.  

### Langkah 3 — Dokumentasi
- Simpan ringkasan di `laporan.md`.  
- Buat screenshot evidence setup repo GitHub (`repo name`, `initial commit`). Simpan di folder `screenshots/`.  
- Lampirkan screenshot di laporan menggunakan sintaks Markdown:  
  ```markdown
  ![Setup GitHub](screenshots/repo_setup.png)
  ```

### Langkah 4 — Quiz Singkat
Jawab pertanyaan berikut di laporan:  
1. Siapa tokoh yang dianggap sebagai bapak kriptografi modern?  
2. Sebutkan algoritma kunci publik yang populer digunakan saat ini.  
3. Apa perbedaan utama antara kriptografi klasik dan kriptografi modern?  

---

## Tugas yang Dikumpulkan
1. Repositori GitHub individu sudah disetup (`kripto-20251-<nim>`).  
2. Folder `praktikum/week1-intro-cia/` berisi:  
   - `laporan.md` (ringkasan + jawaban quiz).  
   - `screenshots/` (bukti repo setup & contoh CIA).  
3. Commit dengan pesan:  
   ```
   week1-intro-cia
   ```

---

## Rubrik Penilaian
Mengacu pada RPS Minggu 1: **Total bobot 5% (Quiz 3%, Ringkasan 2%)**  

| Aspek Penilaian         | Bobot | Kriteria                                                                 |
|--------------------------|-------|--------------------------------------------------------------------------|
| Quiz singkat             | 3%    | Jawaban benar, singkat, sesuai konsep sejarah & CIA                      |
| Ringkasan individu       | 2%    | Menjelaskan sejarah kripto, prinsip CIA, dan contoh peran kripto         |
| Evidence Git & laporan   | -     | Struktur repo rapi, ada screenshot, commit sesuai format (syarat sah)    |

---
