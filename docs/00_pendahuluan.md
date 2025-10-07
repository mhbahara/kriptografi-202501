# 00 Pendahuluan  

## Tujuan  
Dokumen ini merupakan panduan umum pelaksanaan praktikum mata kuliah **Kriptografi** pada semester gasal 2025/2026. Mahasiswa diharapkan memahami:  
- Alur kerja praktikum berbasis *growth assignment* (bertumbuh dari dasar ke proyek akhir).  
- Tata cara penggunaan GitHub sebagai media utama penyimpanan dan pengumpulan tugas.  
- Mekanisme penilaian praktikum yang terintegrasi dengan Rencana Pembelajaran Semester (RPS).  

---

## Tata Cara Praktikum  
1. **Sistem Praktikum Bertumbuh**  
   - Praktikum dilaksanakan selama 16 minggu.  
   - Setiap minggu mahasiswa menyelesaikan tugas berbasis topik yang membangun keterampilan secara bertahap, mulai dari cipher klasik hingga implementasi cryptocurrency (TinyCoin).  
   - Praktikum individu fokus pada pemahaman dasar; praktikum tim (akhir) berorientasi pada integrasi proyek.  

2. **Repositori GitHub Individu**  
   - Setiap mahasiswa wajib memiliki repositori pribadi hasil fork dari repositori template dosen.  
   - Nama repo mengikuti format:  
     ```
     kripto-20251-<nim>
     ```  
     Contoh: `kripto-20251-2310112345`  

3. **Repositori Tim**  
   - Untuk proyek akhir (TinyCoin), setiap kelompok menggunakan repositori tim dengan format:  
     ```
     tinycoin-<nama-tim>
     ```  

4. **Konten yang Dikumpulkan Setiap Minggu**  
   - Kode program (`src/`)  
   - Screenshot hasil eksekusi (`screenshots/`)  
   - Laporan singkat (`laporan.md`)  
   - Commit log dengan format standar  

5. **Format Commit Git**  
   Setiap minggu menggunakan pesan commit:  
   ```
   weekX-[nama-topik]
   ```  
   Contoh:  
   - `week1-intro-cia`  
   - `week2-cryptosystem`  
   - `week3-modmath-gcd`  
   - `week13-tinychain`  
   - `week15-tinycoin-erc20`  

---

## Struktur Folder  
Contoh struktur direktori praktikum:  

```
praktikum/
 ├─ week1-intro-cia/
 │   ├─ src/                # kode program
 │   ├─ screenshots/        # hasil eksekusi
 │   └─ laporan.md          # laporan
 ├─ week2-cryptosystem/
 ├─ week3-modmath-gcd/
 ├─ week4-entropy-unicity/
 ├─ ...
 ├─ week15-tinycoin-erc20/
 └─ week16-uas/
```

---

## Mekanisme Penilaian  
Penilaian praktikum mengacu pada RPS Kriptografi dan dibagi menjadi beberapa komponen:  

| Komponen Penilaian                  | Bobot | Bentuk Evidence                                                                 |
|-------------------------------------|-------|---------------------------------------------------------------------------------|
| **Tugas Individu (Quiz, Laporan, Praktikum mingguan)** | 27%  | Laporan mingguan (`laporan.md`), kode program, screenshot hasil, commit log      |
| **Partisipasi & Sikap**             | 5%    | Keaktifan di kelas/lab, kontribusi diskusi, konsistensi push ke GitHub          |
| **Ujian Tengah Semester (UTS)**     | 14%   | Teori + praktik (coding dasar RSA, AES, DH, atau analisis kasus sederhana)      |
| **Proyek Praktikum (TinyChain & TinyCoin ERC-20)** | 34%  | Repositori tim: modul blockchain, kontrak ERC-20, dokumentasi & laporan kelompok|
| **Ujian Akhir Semester (UAS)**      | 20%   | Presentasi & demo proyek tim, tanya jawab, analisis keamanan proyek             |
| **Total**                           | 100%  |                                                                                 |

---

## Aturan Tambahan  
1. **Plagiarisme dilarang.** Jika ada kesamaan kode/laporan tanpa sumber jelas, nilai 0 untuk semua pihak terkait.  
2. **Keterlambatan pengumpulan** tanpa alasan sah → pengurangan nilai 10% per minggu.  
3. **Diskusi diperbolehkan**, tetapi hasil laporan & kode harus ditulis sendiri.  
4. **Standarisasi**: penamaan file, folder, dan commit log wajib mengikuti instruksi; jika tidak, nilai akan dikurangi.  
5. **Bahasa laporan** menggunakan Bahasa Indonesia yang baik, singkat, dan jelas.  

---

## Catatan  
- Mahasiswa diharapkan melakukan commit secara rutin, bukan hanya sekali di akhir.  
- Dosen akan memantau perkembangan melalui **history commit** di GitHub.  
- Untuk proyek akhir, setiap anggota tim wajib berkontribusi. Kontribusi akan dinilai berdasarkan commit, pull request, dan dokumentasi tim.  
