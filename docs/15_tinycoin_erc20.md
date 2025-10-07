# 15 Proyek Kelompok – TinyCoin ERC20

## Tujuan Pembelajaran
Setelah mengikuti praktikum ini, mahasiswa diharapkan mampu:  
1. Mengembangkan proyek sederhana berbasis algoritma kriptografi.  
2. Mendokumentasikan proses implementasi proyek ke dalam repository Git.  
3. Menyusun laporan teknis hasil proyek akhir.  

---

## Capaian Kegiatan
Pada akhir sesi ini mahasiswa menghasilkan:  
- Implementasi **smart contract ERC20 (TinyCoin)** menggunakan Solidity.  
- Dokumentasi proyek di repository Git (kode, README, laporan).  
- Laporan teknis berisi penjelasan implementasi, hasil pengujian, serta analisis keamanan dasar.  
- Commit Git dengan format `week15-tinycoin-erc20`.  

---

## Persiapan Lingkungan
1. Buat folder berikut:  
   ```
   praktikum/week15-tinycoin-erc20/
   ├─ contracts/
   │   └─ TinyCoin.sol
   ├─ screenshots/
   └─ laporan.md
   ```
2. Gunakan **Remix IDE** atau **Hardhat/Truffle** untuk kompilasi dan deployment smart contract.  
3. Gunakan testnet Ethereum (contoh: Goerli, Sepolia) untuk menguji kontrak ERC20.  
4. Materi rujukan:  
   - Stallings (2017).  
   - Stinson (2019).  

---

## Panduan Langkah demi Langkah

### Langkah 1 — Membuat Kontrak ERC20
Contoh kontrak sederhana `TinyCoin.sol`:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

contract TinyCoin is ERC20 {
    constructor(uint256 initialSupply) ERC20("TinyCoin", "TNC") {
        _mint(msg.sender, initialSupply);
    }
}
```

---

### Langkah 2 — Deploy Kontrak
- Buka **Remix IDE** → buat file `TinyCoin.sol`.  
- Kompilasi dengan Solidity Compiler.  
- Deploy ke jaringan **JavaScript VM** atau testnet Ethereum.  
- Catat alamat kontrak hasil deployment.  

---

### Langkah 3 — Uji Fungsionalitas
- Cek saldo awal dengan fungsi `balanceOf(address)`.  
- Lakukan transfer token dengan fungsi `transfer(address, amount)`.  
- Uji apakah total supply tetap konsisten setelah transaksi.  

---

### Langkah 4 — Dokumentasi
- Simpan tangkapan layar proses deployment & transaksi.  
- Dokumentasikan alur kontrak (fungsi utama: `constructor`, `mint`, `transfer`).  
- Tambahkan analisis singkat tentang potensi keamanan smart contract (contoh: reentrancy, overflow – walaupun mitigasi sudah ada di Solidity >=0.8).  

---

## Pertanyaan Diskusi
1. Apa fungsi utama ERC20 dalam ekosistem blockchain?  
2. Bagaimana mekanisme transfer token bekerja dalam kontrak ERC20?  
3. Apa risiko utama dalam implementasi smart contract dan bagaimana cara mitigasinya?  

---

## Tugas yang Dikumpulkan
1. File `contracts/TinyCoin.sol`.  
2. Screenshot deployment & transaksi token.  
3. Laporan `laporan.md` berisi:  
   - Dokumentasi kontrak ERC20 TinyCoin.  
   - Hasil pengujian fungsi utama.  
   - Jawaban pertanyaan diskusi.  

Struktur akhir folder:
```
praktikum/week15-tinycoin-erc20/
 ├─ contracts/TinyCoin.sol
 ├─ screenshots/
 │   └─ hasil.png
 └─ laporan.md
```

Commit dengan pesan:  
```
week15-tinycoin-erc20
```

---

## Rubrik Penilaian
Mengacu pada RPS Minggu 15: **Total bobot 5% (Implementasi proyek kelompok 3%, Dokumentasi progres Git 2%)**  

| Aspek Penilaian          | Bobot | Kriteria                                                                |
|---------------------------|-------|-------------------------------------------------------------------------|
| Implementasi TinyCoin     | 3%    | Kontrak ERC20 berjalan, deployment sukses, transaksi token valid        |
| Dokumentasi Git           | 2%    | Commit sesuai format, README & laporan teknis rapi, ada screenshot      |
| Evidence Git & repo       | -     | Struktur repo rapi, history commit sesuai instruksi                     |

---