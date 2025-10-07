# 13 TinyChain – Proof of Work (PoW)

## Tujuan Pembelajaran
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:  
1. Menjelaskan peran **hash function** dalam blockchain.  
2. Melakukan simulasi sederhana **Proof of Work (PoW)**.  
3. Menganalisis keamanan cryptocurrency berbasis kriptografi.  

---

## Capaian Kegiatan
Pada akhir sesi ini mahasiswa menghasilkan:  
- Program Python mini blockchain sederhana dengan hash function & Proof of Work.  
- Screenshot hasil mining blok.  
- Laporan singkat analisis keamanan blockchain dan PoW.  
- Commit Git dengan format `week13-tinychain`.  

---

## Persiapan Lingkungan
1. Buat folder berikut:  
   ```
   praktikum/week13-tinychain/
   ├─ src/
   ├─ screenshots/
   └─ laporan.md
   ```
2. Gunakan Python 3.11 atau lebih baru.  
3. Materi rujukan:  
   - Stallings (2017), Bab 16.  
   - Stinson (2019), Bab 8.  

---

## Panduan Langkah demi Langkah

### Langkah 1 — Membuat Struktur Blok
```python
import hashlib
import time

class Block:
    def __init__(self, index, previous_hash, data, timestamp=None):
        self.index = index
        self.timestamp = timestamp or time.time()
        self.data = data
        self.previous_hash = previous_hash
        self.nonce = 0
        self.hash = self.calculate_hash()

    def calculate_hash(self):
        value = str(self.index) + str(self.timestamp) + str(self.data) + str(self.previous_hash) + str(self.nonce)
        return hashlib.sha256(value.encode()).hexdigest()

    def mine_block(self, difficulty):
        while self.hash[:difficulty] != "0" * difficulty:
            self.nonce += 1
            self.hash = self.calculate_hash()
        print(f"Block mined: {self.hash}")
```

---

### Langkah 2 — Membuat Blockchain
```python
class Blockchain:
    def __init__(self):
        self.chain = [self.create_genesis_block()]
        self.difficulty = 4

    def create_genesis_block(self):
        return Block(0, "0", "Genesis Block")

    def get_latest_block(self):
        return self.chain[-1]

    def add_block(self, new_block):
        new_block.previous_hash = self.get_latest_block().hash
        new_block.mine_block(self.difficulty)
        self.chain.append(new_block)

# Uji coba blockchain
my_chain = Blockchain()
print("Mining block 1...")
my_chain.add_block(Block(1, "", "Transaksi A → B: 10 Coin"))

print("Mining block 2...")
my_chain.add_block(Block(2, "", "Transaksi B → C: 5 Coin"))
```

---

### Langkah 3 — Analisis Proof of Work
- Perhatikan bahwa proses mining membutuhkan waktu (bergantung pada `difficulty`).  
- Analisis: semakin tinggi difficulty, semakin lama proses mining.  
- Diskusikan bagaimana hal ini menjamin keamanan blockchain.  

---

## Pertanyaan Diskusi
1. Mengapa fungsi hash sangat penting dalam blockchain?  
2. Bagaimana Proof of Work mencegah double spending?  
3. Apa kelemahan dari PoW dalam hal efisiensi energi?  

---

## Tugas yang Dikumpulkan
1. Program Python `src/tinychain.py` yang:  
   - Membuat blockchain sederhana dengan hash function.  
   - Mengimplementasikan Proof of Work.  
2. Screenshot hasil mining blok.  
3. Laporan `laporan.md` berisi:  
   - Penjelasan teori hash function & PoW.  
   - Hasil simulasi mining.  
   - Jawaban pertanyaan diskusi.  

Struktur akhir folder:
```
praktikum/week13-tinychain/
 ├─ src/tinychain.py
 ├─ screenshots/
 │   └─ hasil.png
 └─ laporan.md
```

Commit dengan pesan:  
```
week13-tinychain
```

---

## Rubrik Penilaian
Mengacu pada RPS Minggu 13: **Total bobot 5% (Praktikum blockchain hash/PoW 3%, Repo Git 2%)**  

| Aspek Penilaian        | Bobot | Kriteria                                                                 |
|-------------------------|-------|--------------------------------------------------------------------------|
| Praktikum hash/PoW      | 3%    | Program blockchain berjalan, hash sesuai, PoW berhasil                  |
| Repo Git & laporan      | 2%    | Commit sesuai format, laporan rapi, ada screenshot & analisis keamanan  |
| Evidence Git & repo     | -     | Struktur repo rapi, history commit sesuai instruksi                      |

---