# 06 Cipher Modern (DES, AES, RSA)

## Tujuan Pembelajaran
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:  
1. Mengimplementasikan algoritma **DES** untuk blok data sederhana.  
2. Menerapkan algoritma **AES** dengan panjang kunci 128 bit.  
3. Menjelaskan proses pembangkitan kunci publik dan privat pada algoritma **RSA**.  

---

## Capaian Kegiatan
Pada akhir sesi ini mahasiswa menghasilkan:  
- Program Python untuk implementasi AES dan RSA (DES opsional atau simulasi).  
- Screenshot hasil enkripsi dan dekripsi.  
- Laporan singkat mengenai hasil implementasi dan dokumentasi langkah coding.  
- Commit Git dengan format `week6-cipher-modern`.  

---

## Persiapan Lingkungan
1. Buat folder berikut:  
   ```
   praktikum/week6-cipher-modern/
   ├─ src/
   ├─ screenshots/
   └─ laporan.md
   ```
2. Gunakan Python 3.11 atau lebih baru.  
3. Install library tambahan:  
   ```bash
   pip install pycryptodome
   ```
4. Materi rujukan: Stallings (2017), Bab 3–4.  

---

## Panduan Langkah demi Langkah

### Langkah 1 — Implementasi DES (Opsional, Simulasi)
```python
from Crypto.Cipher import DES
from Crypto.Random import get_random_bytes

key = get_random_bytes(8)  # kunci 64 bit (8 byte)
cipher = DES.new(key, DES.MODE_ECB)

plaintext = b"ABCDEFGH"
ciphertext = cipher.encrypt(plaintext)
print("Ciphertext:", ciphertext)

decipher = DES.new(key, DES.MODE_ECB)
decrypted = decipher.decrypt(ciphertext)
print("Decrypted:", decrypted)
```
---

### Langkah 2 — Implementasi AES-128
```python
from Crypto.Cipher import AES
from Crypto.Random import get_random_bytes

key = get_random_bytes(16)  # 128 bit key
cipher = AES.new(key, AES.MODE_EAX)

plaintext = b"Modern Cipher AES Example"
ciphertext, tag = cipher.encrypt_and_digest(plaintext)

print("Ciphertext:", ciphertext)

# Dekripsi
cipher_dec = AES.new(key, AES.MODE_EAX, nonce=cipher.nonce)
decrypted = cipher_dec.decrypt(ciphertext)
print("Decrypted:", decrypted.decode())
```
---

### Langkah 3 — Implementasi RSA
```python
from Crypto.PublicKey import RSA
from Crypto.Cipher import PKCS1_OAEP

# Generate key pair
key = RSA.generate(2048)
private_key = key
public_key = key.publickey()

# Enkripsi dengan public key
cipher_rsa = PKCS1_OAEP.new(public_key)
plaintext = b"RSA Example"
ciphertext = cipher_rsa.encrypt(plaintext)
print("Ciphertext:", ciphertext)

# Dekripsi dengan private key
decipher_rsa = PKCS1_OAEP.new(private_key)
decrypted = decipher_rsa.decrypt(ciphertext)
print("Decrypted:", decrypted.decode())
```
---

## Pertanyaan Diskusi
1. Apa perbedaan mendasar antara DES, AES, dan RSA dalam hal kunci dan keamanan?  
2. Mengapa AES lebih banyak digunakan dibanding DES di era modern?  
3. Mengapa RSA dikategorikan sebagai algoritma asimetris, dan bagaimana proses pembangkitan kuncinya?  

---

## Tugas yang Dikumpulkan
1. Program Python (`src/`) berisi implementasi:  
   - AES-128 (wajib).  
   - RSA (wajib).  
   - DES (opsional/simulasi).  
2. Screenshot hasil eksekusi program.  
3. Laporan `laporan.md` berisi:  
   - Ringkasan teori algoritma modern.  
   - Hasil uji implementasi.  
   - Jawaban pertanyaan diskusi.  

Struktur akhir folder:
```
praktikum/week6-cipher-modern/
 ├─ src/aes.py
 ├─ src/rsa.py
 ├─ src/des.py (opsional)
 ├─ screenshots/
 │   └─ hasil.png
 └─ laporan.md
```

Commit dengan pesan:  
```
week6-cipher-modern
```

---

## Rubrik Penilaian
Mengacu pada RPS Minggu 6: **Total bobot 5% (Praktikum 3%, Laporan Git 2%)**  

| Aspek Penilaian           | Bobot | Kriteria                                                                  |
|----------------------------|-------|---------------------------------------------------------------------------|
| Praktikum DES/AES/RSA      | 3%    | Program berjalan benar, hasil enkripsi-dekripsi sesuai teori               |
| Laporan Git                | 2%    | Commit sesuai format, laporan rapi, ada screenshot dan dokumentasi langkah |
| Evidence Git & repo        | -     | History commit jelas, sesuai instruksi                                    |

---