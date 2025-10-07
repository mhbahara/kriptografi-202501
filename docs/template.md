# Soal Praktikum Kriptografi
Minggu ke-: X  
Topik: [judul praktikum]  
Capaian Sub-CPMK: [tuliskan sesuai RPS, contoh: Sub-CPMK03 – Mahasiswa mampu mengimplementasikan algoritma cipher klasik]

---

## 1. Tujuan
(Tuliskan tujuan pembelajaran untuk minggu ini.  
Contoh: Mahasiswa memahami konsep dasar cryptosystem dan dapat mengimplementasikan algoritma enkripsi-dekripsi sederhana.)

---

## 2. Dasar Teori Singkat
(Berikan ringkasan teori yang relevan.  
Contoh: Cryptosystem terdiri atas plaintext, ciphertext, algoritma enkripsi, algoritma dekripsi, dan kunci.  
Caesar Cipher merupakan algoritma kriptografi klasik yang menggunakan pergeseran huruf sederhana.)

---

## 3. Instruksi Praktikum
1. Buat folder:
   ```
   praktikum/weekX-[nama-topik]/src/
   ```
2. Tulis program sesuai instruksi berikut:
   - Implementasikan fungsi `encrypt(plaintext, key)` dan `decrypt(ciphertext, key)`.
   - Jalankan program dengan input contoh.
   - Dokumentasikan hasil eksekusi (screenshot).
3. Simpan kode program di folder `src/`.
4. Buat laporan `laporan.md` sesuai template laporan praktikum.
5. Lakukan commit Git dengan pesan:
   ```
   weekX-[nama-topik]
   ```

---

## 4. Contoh Implementasi Kode
Gunakan contoh berikut sebagai referensi dasar (boleh dimodifikasi/ditingkatkan):

```python
# file: praktikum/weekX-[nama-topik]/src/caesar_cipher.py

def encrypt(plaintext, key):
    result = ""
    for char in plaintext:
        if char.isalpha():
            shift = 65 if char.isupper() else 97
            result += chr((ord(char) - shift + key) % 26 + shift)
        else:
            result += char
    return result

def decrypt(ciphertext, key):
    result = ""
    for char in ciphertext:
        if char.isalpha():
            shift = 65 if char.isupper() else 97
            result += chr((ord(char) - shift - key) % 26 + shift)
        else:
            result += char
    return result

if __name__ == "__main__":
    message = "Kriptografi"
    key = 3
    encrypted = encrypt(message, key)
    decrypted = decrypt(encrypted, key)

    print("Plaintext :", message)
    print("Ciphertext:", encrypted)
    print("Decrypted :", decrypted)
```

Ekspektasi keluaran:
```
Plaintext : Kriptografi
Ciphertext: Nulswrjudil
Decrypted : Kriptografi
```

---

## 5. Tugas yang Dikumpulkan
Mahasiswa wajib mengumpulkan dalam repositori GitHub masing-masing:
- Berkas program di folder `src/`.
- Screenshot hasil eksekusi di folder `screenshots/`.
- Laporan `laporan.md` sesuai template laporan praktikum.
- Bukti commit log Git.

---

## 6. Pertanyaan Diskusi
1. Mengapa Caesar Cipher dianggap tidak aman untuk digunakan di era modern?  
2. Jika kunci Caesar Cipher adalah 13, jelaskan hubungannya dengan algoritma ROT13.  
3. Jelaskan perbedaan mendasar antara kriptografi simetris dan asimetris dari sisi penggunaan kunci.  

---
