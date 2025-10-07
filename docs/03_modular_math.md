# 03 Modular Math (Aritmetika Modular, GCD, Bilangan Prima, Logaritma Diskrit)

## Tujuan Pembelajaran
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:  
1. Menyelesaikan operasi aritmetika modular.  
2. Menentukan bilangan prima dan menghitung GCD (Greatest Common Divisor).  
3. Menerapkan logaritma diskrit sederhana dalam simulasi kriptografi.  

---

## Capaian Kegiatan
Pada akhir sesi ini mahasiswa menghasilkan:  
- Perhitungan modular arithmetic & GCD menggunakan Python.  
- Identifikasi bilangan prima dan penerapan algoritma Euclidean.  
- Simulasi sederhana logaritma diskrit.  
- Commit kode perhitungan ke repositori dengan format `week3-modmath-gcd`.  

---

## Persiapan Lingkungan
1. Pastikan folder berikut sudah ada:  
   ```
   praktikum/week3-modmath-gcd/
   ├─ src/
   ├─ screenshots/
   └─ laporan.md
   ```
2. Gunakan Python 3.11 atau lebih baru.  
3. Editor kode (Visual Studio Code atau setara).  

---

## Panduan Langkah demi Langkah

### Langkah 1 — Aritmetika Modular
Tuliskan fungsi untuk menghitung operasi modular dasar.  
```python
def mod_add(a, b, n): return (a + b) % n
def mod_sub(a, b, n): return (a - b) % n
def mod_mul(a, b, n): return (a * b) % n
def mod_exp(base, exp, n): return pow(base, exp, n)  # eksponensiasi modular

print("7 + 5 mod 12 =", mod_add(7, 5, 12))
print("7 * 5 mod 12 =", mod_mul(7, 5, 12))
print("7^128 mod 13 =", mod_exp(7, 128, 13))
```

### Langkah 2 — GCD & Algoritma Euclidean
Implementasikan fungsi GCD dengan algoritma Euclidean.  
```python
def gcd(a, b):
    while b != 0:
        a, b = b, a % b
    return a

print("gcd(54, 24) =", gcd(54, 24))
```

### Langkah 3 — Extended Euclidean Algorithm
Tambahkan fungsi untuk mencari invers modular.  
```python
def egcd(a, b):
    if a == 0:
        return b, 0, 1
    g, x1, y1 = egcd(b % a, a)
    return g, y1 - (b // a) * x1, x1

def modinv(a, n):
    g, x, _ = egcd(a, n)
    if g != 1:
        return None
    return x % n

print("Invers 3 mod 11 =", modinv(3, 11))  # hasil: 4
```

### Langkah 4 — Logaritma Diskrit (Discrete Log)
Simulasikan logaritma diskrit sederhana: mencari `x` sehingga `a^x ≡ b (mod n)`.  
```python
def discrete_log(a, b, n):
    for x in range(n):
        if pow(a, x, n) == b:
            return x
    return None

print("3^x ≡ 4 (mod 7), x =", discrete_log(3, 4, 7))  # hasil: 4
```

---

## Pertanyaan Diskusi
1. Apa peran aritmetika modular dalam kriptografi modern?  
2. Mengapa invers modular penting dalam algoritma kunci publik (misalnya RSA)?  
3. Apa tantangan utama dalam menyelesaikan logaritma diskrit untuk modulus besar?  

---

## Tugas yang Dikumpulkan
1. Program Python (`src/`) berisi implementasi:  
   - Modular arithmetic (add, sub, mul, exp).  
   - GCD & Euclidean Algorithm.  
   - Extended Euclidean & modular inverse.  
   - Discrete log sederhana.  
2. Screenshot hasil eksekusi program.  
3. Laporan `laporan.md` berisi:  
   - Ringkasan teori modular arithmetic & GCD.  
   - Hasil pengujian dengan contoh kasus.  
   - Jawaban pertanyaan diskusi.  

Struktur akhir folder:
```
praktikum/week3-modmath-gcd/
 ├─ src/modular_math.py
 ├─ screenshots/
 │   └─ hasil.png
 └─ laporan.md
```

Commit dengan pesan:  
```
week3-modmath-gcd
```

---

## Rubrik Penilaian
Mengacu pada RPS Minggu 3: **Total bobot 5% (Latihan Modular & GCD 3%, Hasil Git 2%)**  

| Aspek Penilaian                  | Bobot | Kriteria                                                                 |
|----------------------------------|-------|--------------------------------------------------------------------------|
| Latihan Modular & GCD (program)  | 3%    | Program modular arithmetic, GCD, invers modular, logaritma diskrit benar |
| Hasil Git & laporan              | 2%    | Commit sesuai format, folder rapi, laporan singkat dengan bukti screenshot|
| Evidence Git & repo              | -     | History commit jelas, sesuai instruksi                                    |

---

