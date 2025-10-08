# 02 Cryptosystem (Komponen, Enkripsi & Dekripsi, Simetris & Asimetris)

## Tujuan Pembelajaran
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:  
1. Mengidentifikasi komponen dasar kriptosistem (plaintext, ciphertext, kunci, algoritma).  
2. Menggambarkan proses enkripsi dan dekripsi sederhana.  
3. Mengklasifikasikan jenis kriptosistem (simetris dan asimetris).  

---

## Capaian Kegiatan
Pada akhir sesi ini mahasiswa menghasilkan:  
- Diagram/skema kriptosistem dasar.  
- Program sederhana simulasi enkripsi–dekripsi.  
- Laporan singkat berisi penjelasan, skema, dan hasil uji.  
- Commit ke GitHub dengan format `week2-cryptosystem`.  

---

## Persiapan Lingkungan
1. Pastikan folder berikut sudah tersedia di repositori individu:  
   ```
   praktikum/week2-cryptosystem/
   ├─ src/
   ├─ screenshots/
   └─ laporan.md
   ```
2. Gunakan Python 3.11 atau lebih baru.  
3. Editor kode (Visual Studio Code atau setara).  

---

## Panduan Langkah demi Langkah

### Langkah 1 — Membuat Skema Kriptosistem
- Buat diagram sederhana (bisa pakai draw.io, excalidraw, atau digambar lalu screenshot) dengan elemen:  
  - Plaintext → [Algoritma + Kunci] → Ciphertext  
  - Ciphertext → [Algoritma + Kunci] → Plaintext  
- Simpan diagram di folder `screenshots/diagram_kriptosistem.png`.  
- Lampirkan ke laporan menggunakan Markdown:  
  ```markdown
  ![Diagram Kriptosistem](screenshots/diagram_kriptosistem.png)
  ```

### Langkah 2 — Implementasi Program Sederhana
Tulis program Python untuk simulasi enkripsi & dekripsi menggunakan substitusi sederhana (misalnya Caesar Cipher).  

```python
# file: praktikum/week2-cryptosystem/src/simple_crypto.py

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
    message = "<nim><nama>"
    key = 5

    enc = encrypt(message, key)
    dec = decrypt(enc, key)

    print("Plaintext :", message)
    print("Ciphertext:", enc)
    print("Decrypted :", dec)
```

Ekspektasi keluaran:  
```
Plaintext : Cryptosystem Test
Ciphertext: Hwduytxzjxytr Yjxy
Decrypted : Cryptosystem Test
```

### Langkah 3 — Klasifikasi Simetris & Asimetris
- Tambahkan penjelasan di laporan mengenai perbedaan kriptografi simetris dan asimetris.  
- Sertakan minimal 1 contoh algoritma dari masing-masing:  
  - Simetris → AES, DES  
  - Asimetris → RSA, ECC  

---

## Pertanyaan Diskusi
1. Sebutkan komponen utama dalam sebuah kriptosistem.  
2. Apa kelebihan dan kelemahan sistem simetris dibandingkan asimetris?  
3. Mengapa distribusi kunci menjadi masalah utama dalam kriptografi simetris?  

---

## Tugas yang Dikumpulkan
1. Diagram/skema kriptosistem dasar.  
2. Program Python `simple_crypto.py` beserta hasil eksekusi (screenshot terminal).  
3. Laporan singkat (`laporan.md`) berisi:  
   - Ringkasan komponen kriptosistem.  
   - Penjelasan perbedaan simetris vs asimetris.  
   - Jawaban pertanyaan diskusi.  

Struktur akhir folder:
```
praktikum/week2-cryptosystem/
 ├─ src/simple_crypto.py
 ├─ screenshots/
 │   ├─ diagram_kriptosistem.png
 │   └─ hasil_eksekusi.png
 └─ laporan.md
```

Commit dengan pesan:  
```
week2-cryptosystem
```

---

## Rubrik Penilaian
Mengacu pada RPS Minggu 2: **Total bobot 5% (Praktikum 3%, Laporan 2%)**  

| Aspek Penilaian             | Bobot | Kriteria                                                                 |
|------------------------------|-------|--------------------------------------------------------------------------|
| Praktikum (program + skema)  | 3%    | Program berjalan benar, diagram sesuai konsep enkripsi–dekripsi           |
| Laporan ringkas              | 2%    | Penjelasan komponen, klasifikasi simetris & asimetris, jawaban diskusi    |
| Evidence Git & repo          | -     | Commit sesuai format, folder rapi, screenshot lengkap (syarat sah)        |

---
