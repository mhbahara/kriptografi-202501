# 11 Secret Sharing (Shamir’s Secret Sharing)

## Tujuan Pembelajaran
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:  
1. Menjelaskan konsep **Shamir Secret Sharing** (SSS).  
2. Melakukan simulasi pembagian rahasia ke beberapa pihak menggunakan skema SSS.  
3. Menganalisis keamanan skema distribusi rahasia.  

---

## Capaian Kegiatan
Pada akhir sesi ini mahasiswa menghasilkan:  
- Program Python simulasi pembagian rahasia dengan Shamir Secret Sharing.  
- Hasil rekonstruksi rahasia dari beberapa subset kunci.  
- Laporan singkat analisis keamanan secret sharing.  
- Commit Git dengan format `week11-secret-sharing`.  

---

## Persiapan Lingkungan
1. Buat folder berikut:  
   ```
   praktikum/week11-secret-sharing/
   ├─ src/
   ├─ screenshots/
   └─ laporan.md
   ```
2. Gunakan Python 3.11 atau lebih baru.  
3. Install library tambahan bila perlu:  
   ```bash
   pip install secretsharing
   ```  
   atau gunakan implementasi mandiri dengan operasi aritmetika modular.  
4. Materi rujukan: Stinson (2019), Bab 6.  

---

## Panduan Langkah demi Langkah

### Langkah 1 — Implementasi Shamir Secret Sharing
Contoh sederhana dengan library `secretsharing`:

```python
from secretsharing import SecretSharer

# Rahasia yang ingin dibagi
secret = "KriptografiUPB2025"

# Bagi menjadi 5 shares, ambang batas 3 (minimal 3 shares untuk rekonstruksi)
shares = SecretSharer.split_secret(secret, 3, 5)
print("Shares:", shares)

# Rekonstruksi rahasia dari 3 shares
recovered = SecretSharer.recover_secret(shares[:3])
print("Recovered secret:", recovered)
```

---

### Langkah 2 — Simulasi Manual (Tanpa Library)
Mahasiswa juga dapat mencoba membuat implementasi manual berbasis **polinomial modulo p** untuk memahami konsep matematis.  
- Pilih bilangan prima p yang cukup besar.  
- Bangun polinomial f(x) = a0 + a1x + … + ak-1x^(k-1) mod p, dengan a0 = secret.  
- Bagikan (x, f(x)) sebagai share.  
- Rekonstruksi menggunakan **Lagrange Interpolation**.  

---

### Langkah 3 — Analisis Keamanan
Diskusikan:
- Mengapa skema (k, n) aman meskipun sebagian share bocor?  
- Apa risiko jika threshold k terlalu kecil atau terlalu besar?  
- Bagaimana penerapan SSS di dunia nyata (contoh: manajemen kunci cryptocurrency, recovery password)?  

---

## Pertanyaan Diskusi
1. Apa keuntungan utama Shamir Secret Sharing dibanding membagikan salinan kunci secara langsung?  
2. Apa peran **threshold (k)** dalam keamanan secret sharing?  
3. Berikan satu contoh skenario nyata di mana SSS sangat bermanfaat.  

---

## Tugas yang Dikumpulkan
1. Program Python `src/secret_sharing.py` yang:  
   - Membagi rahasia menjadi n shares dengan ambang k.  
   - Mampu merekonstruksi rahasia dengan tepat dari k shares.  
2. Screenshot hasil pembagian dan rekonstruksi.  
3. Laporan `laporan.md` berisi:  
   - Ringkasan teori Shamir Secret Sharing.  
   - Hasil uji pembagian & rekonstruksi.  
   - Jawaban pertanyaan diskusi.  

Struktur akhir folder:
```
praktikum/week11-secret-sharing/
 ├─ src/secret_sharing.py
 ├─ screenshots/
 │   └─ hasil.png
 └─ laporan.md
```

Commit dengan pesan:  
```
week11-secret-sharing
```

---

## Rubrik Penilaian
Mengacu pada RPS Minggu 11: **Total bobot 5% (Praktikum 3%, Laporan Git 2%)**  

| Aspek Penilaian      | Bobot | Kriteria                                                                 |
|-----------------------|-------|--------------------------------------------------------------------------|
| Praktikum Secret Sharing | 3%    | Program berjalan, rahasia berhasil dibagi & direkonstruksi sesuai teori |
| Laporan Git           | 2%    | Commit sesuai format, laporan rapi, ada screenshot & analisis keamanan   |
| Evidence Git & repo   | -     | Struktur repo rapi, history commit sesuai instruksi                      |

---