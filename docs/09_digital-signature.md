# 09 Digital Signature (RSA/DSA)

## Tujuan Pembelajaran
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:  
1. Mengimplementasikan tanda tangan digital menggunakan algoritma RSA/DSA.  
2. Memverifikasi keaslian tanda tangan digital.  
3. Menjelaskan manfaat tanda tangan digital dalam otentikasi pesan dan integritas data.  

---

## Capaian Kegiatan
Pada akhir sesi ini mahasiswa menghasilkan:  
- Program Python untuk pembuatan dan verifikasi tanda tangan digital.  
- Demo hasil verifikasi tanda tangan digital.  
- Laporan singkat yang menjelaskan implementasi, hasil uji coba, serta manfaat tanda tangan digital.  
- Commit Git dengan format `week9-digital-signature`.  

---

## Persiapan Lingkungan
1. Buat folder berikut:  
   ```
   praktikum/week9-digital-signature/
   ├─ src/
   ├─ screenshots/
   └─ laporan.md
   ```
2. Gunakan Python 3.11 atau lebih baru.  
3. Install library tambahan:  
   ```bash
   pip install pycryptodome
   ```
4. Materi rujukan: Stinson (2019), Bab 5.  

---

## Panduan Langkah demi Langkah

### Langkah 1 — Generate Key dan Buat Tanda Tangan
```python
from Crypto.PublicKey import RSA
from Crypto.Signature import pkcs1_15
from Crypto.Hash import SHA256

# Generate pasangan kunci RSA
key = RSA.generate(2048)
private_key = key
public_key = key.publickey()

# Pesan yang akan ditandatangani
message = b"Hello, ini pesan penting."
h = SHA256.new(message)

# Buat tanda tangan dengan private key
signature = pkcs1_15.new(private_key).sign(h)
print("Signature:", signature.hex())
```

---

### Langkah 2 — Verifikasi Tanda Tangan
```python
try:
    pkcs1_15.new(public_key).verify(h, signature)
    print("Verifikasi berhasil: tanda tangan valid.")
except (ValueError, TypeError):
    print("Verifikasi gagal: tanda tangan tidak valid.")
```

---

### Langkah 3 — Uji Modifikasi Pesan
```python
# Modifikasi pesan
fake_message = b"Hello, ini pesan palsu."
h_fake = SHA256.new(fake_message)

try:
    pkcs1_15.new(public_key).verify(h_fake, signature)
    print("Verifikasi berhasil (seharusnya gagal).")
except (ValueError, TypeError):
    print("Verifikasi gagal: tanda tangan tidak cocok dengan pesan.")
```

---

## Pertanyaan Diskusi
1. Apa perbedaan utama antara enkripsi RSA dan tanda tangan digital RSA?  
2. Mengapa tanda tangan digital menjamin integritas dan otentikasi pesan?  
3. Bagaimana peran Certificate Authority (CA) dalam sistem tanda tangan digital modern?  

---

## Tugas yang Dikumpulkan
1. Program Python `src/signature.py` yang:  
   - Membuat tanda tangan digital dengan RSA.  
   - Memverifikasi tanda tangan digital.  
   - Menunjukkan kasus verifikasi gagal pada pesan yang diubah.  
2. Screenshot hasil eksekusi program.  
3. Laporan `laporan.md` berisi:  
   - Ringkasan teori tanda tangan digital.  
   - Hasil uji verifikasi pesan asli vs pesan modifikasi.  
   - Jawaban pertanyaan diskusi.  

Struktur akhir folder:
```
praktikum/week9-digital-signature/
 ├─ src/signature.py
 ├─ screenshots/
 │   └─ hasil.png
 └─ laporan.md
```

Commit dengan pesan:  
```
week9-digital-signature
```

---

## Rubrik Penilaian
Mengacu pada RPS Minggu 9: **Total bobot 5% (Praktikum 3%, Laporan Git 2%)**  

| Aspek Penilaian             | Bobot | Kriteria                                                                 |
|------------------------------|-------|--------------------------------------------------------------------------|
| Praktikum tanda tangan digital | 3%    | Implementasi RSA/DSA benar, tanda tangan valid, uji verifikasi berjalan  |
| Laporan Git                  | 2%    | Commit sesuai format, laporan rapi, ada screenshot, analisis manfaat CA  |
| Evidence Git & repo          | -     | Struktur repo rapi, history commit sesuai instruksi                      |

---