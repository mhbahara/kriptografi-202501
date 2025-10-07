# 10 Public Key Infrastructure (PKI & Certificate Authority)

## Tujuan Pembelajaran
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:  
1. Membuat sertifikat digital sederhana.  
2. Menjelaskan peran Certificate Authority (CA) dalam sistem PKI.  
3. Mengevaluasi fungsi PKI dalam komunikasi aman (contoh: HTTPS, TLS).  

---

## Capaian Kegiatan
Pada akhir sesi ini mahasiswa menghasilkan:  
- Program simulasi pembuatan sertifikat digital menggunakan Python/OpenSSL.  
- Laporan singkat yang menjelaskan peran CA dan PKI dalam komunikasi aman.  
- Commit Git dengan format `week10-pki`.  

---

## Persiapan Lingkungan
1. Buat folder berikut:  
   ```
   praktikum/week10-pki/
   ├─ src/
   ├─ screenshots/
   └─ laporan.md
   ```
2. Gunakan Python 3.11 atau lebih baru.  
3. Install library tambahan jika diperlukan:  
   ```bash
   pip install cryptography pyopenssl
   ```
4. Materi rujukan: Stallings (2017), Bab 14.  

---

## Panduan Langkah demi Langkah

### Langkah 1 — Membuat Sertifikat Digital Sederhana
Contoh dengan Python `cryptography`:
```python
from cryptography import x509
from cryptography.x509.oid import NameOID
from cryptography.hazmat.primitives import hashes, serialization
from cryptography.hazmat.primitives.asymmetric import rsa
from datetime import datetime, timedelta

# Generate key pair
key = rsa.generate_private_key(public_exponent=65537, key_size=2048)

# Buat subject & issuer (CA sederhana = self-signed)
subject = issuer = x509.Name([
    x509.NameAttribute(NameOID.COUNTRY_NAME, u"ID"),
    x509.NameAttribute(NameOID.ORGANIZATION_NAME, u"UPB Kriptografi"),
    x509.NameAttribute(NameOID.COMMON_NAME, u"example.com"),
])

# Buat sertifikat
cert = (
    x509.CertificateBuilder()
    .subject_name(subject)
    .issuer_name(issuer)
    .public_key(key.public_key())
    .serial_number(x509.random_serial_number())
    .not_valid_before(datetime.utcnow())
    .not_valid_after(datetime.utcnow() + timedelta(days=365))
    .sign(key, hashes.SHA256())
)

# Simpan sertifikat
with open("cert.pem", "wb") as f:
    f.write(cert.public_bytes(serialization.Encoding.PEM))

print("Sertifikat digital berhasil dibuat: cert.pem")
```

---

### Langkah 2 — Memverifikasi Sertifikat
- Gunakan public key untuk memverifikasi tanda tangan sertifikat.  
- Jelaskan bagaimana CA digunakan untuk menjamin keaslian sertifikat.  

---

### Langkah 3 — Analisis PKI
Diskusikan kasus nyata:  
- Bagaimana browser memverifikasi sertifikat HTTPS?  
- Apa yang terjadi jika CA palsu menerbitkan sertifikat?  
- Mengapa PKI penting dalam komunikasi aman (misalnya transaksi online)?  

---

## Pertanyaan Diskusi
1. Apa fungsi utama Certificate Authority (CA)?  
2. Mengapa self-signed certificate tidak cukup untuk sistem produksi?  
3. Bagaimana PKI mencegah serangan MITM dalam komunikasi TLS/HTTPS?  

---

## Tugas yang Dikumpulkan
1. Program Python `src/pki_cert.py` yang:  
   - Membuat self-signed certificate sederhana.  
   - Menyimpan sertifikat dalam format `.pem`.  
2. Screenshot hasil pembuatan sertifikat.  
3. Laporan `laporan.md` berisi:  
   - Ringkasan konsep PKI dan CA.  
   - Hasil pembuatan sertifikat.  
   - Jawaban pertanyaan diskusi.  

Struktur akhir folder:
```
praktikum/week10-pki/
 ├─ src/pki_cert.py
 ├─ screenshots/
 │   └─ hasil.png
 └─ laporan.md
```

Commit dengan pesan:  
```
week10-pki
```

---

## Rubrik Penilaian
Mengacu pada RPS Minggu 10: **Total bobot 5% (Praktikum sertifikat 3%, Laporan Git 2%)**  

| Aspek Penilaian        | Bobot | Kriteria                                                                 |
|-------------------------|-------|--------------------------------------------------------------------------|
| Praktikum sertifikat CA | 3%    | Sertifikat digital berhasil dibuat, kode berjalan tanpa error            |
| Laporan Git             | 2%    | Commit sesuai format, laporan rapi, ada screenshot & analisis PKI        |
| Evidence Git & repo     | -     | Struktur repo rapi, history commit sesuai instruksi                      |

---