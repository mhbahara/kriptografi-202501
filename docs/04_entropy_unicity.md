# 04 Entropy & Unicity Distance (Evaluasi Kekuatan Kunci dan Brute Force)

## Tujuan Pembelajaran
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:  
1. Menyelesaikan perhitungan sederhana terkait entropi kunci.  
2. Menggunakan teorema Euler pada contoh perhitungan modular & invers.  
3. Menghitung **unicity distance** untuk ciphertext tertentu.  
4. Menganalisis kekuatan kunci berdasarkan entropi dan unicity distance.  
5. Mengevaluasi potensi serangan brute force pada kriptosistem sederhana.  

---

## Capaian Kegiatan
Pada akhir sesi ini mahasiswa menghasilkan:  
- Perhitungan manual/komputasi entropi dan unicity distance.  
- Analisis sederhana model brute force attack.  
- Laporan singkat tentang evaluasi kekuatan kunci.  
- Commit ke GitHub dengan format `week4-entropy-unicity`.  

---

## Persiapan Lingkungan
1. Buat folder berikut:  
   ```
   praktikum/week4-entropy-unicity/
   ├─ src/
   ├─ screenshots/
   └─ laporan.md
   ```
2. Gunakan Python 3.11 atau lebih baru.  
3. Materi rujukan: Stallings (2017), Bab 3.  

---

## Panduan Langkah demi Langkah

### Langkah 1 — Perhitungan Entropi
Gunakan rumus:  
\[
H(K) = \log_2 |K|
\]  
dengan \(|K|\) adalah ukuran ruang kunci.  

Contoh implementasi Python:  
```python
import math

def entropy(keyspace_size):
    return math.log2(keyspace_size)

print("Entropy ruang kunci 26 =", entropy(26), "bit")
print("Entropy ruang kunci 2^128 =", entropy(2**128), "bit")
```

### Langkah 2 — Menghitung Unicity Distance
Gunakan rumus:  
\[
U = \frac{H(K)}{R \cdot \log_2 |A|}
\]  
dengan:  
- \(H(K)\): entropi kunci,  
- \(R\): redundansi bahasa (misal bahasa Inggris \(R \approx 0.75\)),  
- \(|A|\): ukuran alfabet (26 untuk A–Z).  

Contoh implementasi Python:  
```python
def unicity_distance(HK, R=0.75, A=26):
    return HK / (R * math.log2(A))

HK = entropy(26)
print("Unicity Distance untuk Caesar Cipher =", unicity_distance(HK))
```

### Langkah 3 — Analisis Brute Force
Simulasikan waktu brute force dengan asumsi kecepatan komputer tertentu.  

```python
def brute_force_time(keyspace_size, attempts_per_second=1e6):
    seconds = keyspace_size / attempts_per_second
    days = seconds / (3600*24)
    return days

print("Waktu brute force Caesar Cipher (26 kunci) =", brute_force_time(26), "hari")
print("Waktu brute force AES-128 =", brute_force_time(2**128), "hari")
```

---

## Pertanyaan Diskusi
1. Apa arti dari nilai **entropy** dalam konteks kekuatan kunci?  
2. Mengapa unicity distance penting dalam menentukan keamanan suatu cipher?  
3. Mengapa brute force masih menjadi ancaman meskipun algoritma sudah kuat?  

---

## Tugas yang Dikumpulkan
1. Program Python (`src/`) berisi perhitungan:  
   - Entropi kunci.  
   - Unicity distance.  
   - Estimasi brute force attack.  
2. Screenshot hasil eksekusi program.  
3. Laporan `laporan.md` berisi:  
   - Ringkasan teori entropi & unicity distance.  
   - Hasil analisis brute force.  
   - Jawaban pertanyaan diskusi.  

Struktur akhir folder:
```
praktikum/week4-entropy-unicity/
 ├─ src/entropy_unicity.py
 ├─ screenshots/
 │   └─ hasil.png
 └─ laporan.md
```

Commit dengan pesan:  
```
week4-entropy-unicity
```

---

## Rubrik Penilaian
Mengacu pada RPS Minggu 4: **Total bobot 5% (Analisis Entropi/Unicity 3%, Laporan singkat 2%)**  

| Aspek Penilaian                | Bobot | Kriteria                                                                 |
|--------------------------------|-------|--------------------------------------------------------------------------|
| Analisis entropi & unicity     | 3%    | Perhitungan tepat, implementasi Python berjalan benar, analisis sesuai teori |
| Laporan singkat                | 2%    | Penjelasan ringkas, ada screenshot, jawaban diskusi sesuai pertanyaan     |
| Evidence Git & repo            | -     | Commit sesuai format, struktur folder rapi, laporan jelas                 |

---
