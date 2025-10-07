# Praktikum Kriptografi – TinyCoin (20251)

Repositori ini merupakan **template praktikum** untuk mata kuliah *Kriptografi* semester Gasal 2025/2026, dengan studi kasus **TinyCoin** – mulai dari **CIA Triad**, cipher klasik, kriptografi modern, tanda tangan digital, hingga implementasi cryptocurrency sederhana berbasis **TinyChain** (blockchain PoW) dan token ERC-20 (**TinyCoin**).

Mahasiswa diharapkan membangun pemahaman menyeluruh tentang kriptografi, dimulai dari konsep dasar hingga aplikasi modern dalam bentuk prototipe blockchain dan smart contract.

---

## Instruksi Praktikum
1. **Fork** repositori ini ke akun GitHub masing-masing.
2. Ubah nama hasil fork dengan format:
   ```
   kriptografi-202501-<nim>
   ```
   Contoh: `kriptografi-202501-2310112345`
3. **Clone** repositori ke komputer lokal:
   ```bash
   git clone https://github.com/<username>/kriptografi-202501-<nim>.git
   ```
4. Tambahkan **remote upstream** untuk sinkronisasi dengan repositori dosen:
   ```bash
   git remote add upstream https://github.com/mhbahara/kriptografi-202501.git
   ```
5. Lakukan **sinkronisasi** secara berkala:
   ```bash
   git fetch upstream
   git merge upstream/main
   git push origin main
   ```
6. Kerjakan tugas mingguan sesuai instruksi pada folder [docs/](docs/).
7. Simpan kode program di folder [praktikum/](praktikum/) dengan struktur rapi.
8. Gunakan format pesan commit sesuai minggu, misalnya:
   - `week1-intro-cia`
   - `week3-modmath-gcd`
   - `week6-cipher-modern`
   - `week13-tinychain`
   - `week15-tinycoin-erc20`
9. Setiap tugas wajib dilengkapi dengan:
   - Kode program  
   - Screenshot hasil eksekusi  
   - Commit log sesuai instruksi  
   - Laporan singkat dalam Markdown/PDF  

---

## Struktur Folder
```
kriptografi-202501/
 ├─ README.md                       # Panduan umum repositori
 ├─ docs/                           # Panduan praktikum mingguan (Markdown)
 │   ├─ 00_pendahuluan.md
 │   ├─ 01_CIA.md
 │   ├─ 02_cryptosystem_intro.md
 │   ├─ 03_modular_math.md
 │   ├─ 04_entropy_unicity.md
 │   ├─ 05_cipher_klasik.md
 │   ├─ 06_cipher_modern.md
 │   ├─ 07_diffie_hellman.md
 │   ├─ 08_uts.md
 │   ├─ 09_digital-signature.md
 │   ├─ 10_pki.md
 │   ├─ 11_secret-sharing.md
 │   ├─ 12_aplikasi_tls.md
 │   ├─ 13_tinychain_pow.md
 │   ├─ 14_analisis_serangan.md
 │   ├─ 15_tinycoin_erc20.md
 │   └─ 16_uas_demo.md
 ├─ praktikum/                      # Folder tugas mingguan
 │   ├─ week1-intro-cia/
 │   ├─ week2-cryptosystem/
 │   ├─ week3-modmath-gcd/
 │   ├─ week4-entropy-unicity/
 │   ├─ week5-cipher-klasik/
 │   ├─ week6-cipher-modern/
 │   ├─ week7-diffie-hellman/
 │   ├─ week8-uts/
 │   ├─ week9-digital-signature/
 │   ├─ week10-pki/
 │   ├─ week11-secret-sharing/
 │   ├─ week12-aplikasi-tls/
 │   ├─ week13-tinychain/
 │   ├─ week14-analisis-serangan/
 │   ├─ week15-tinycoin-erc20/
 │   └─ week16-uas/
 ├─ blockchain/                     # Proyek DIY Blockchain (TinyChain)
 ├─ contracts/                      # Proyek Smart Contract (TinyCoin ERC-20)
 ├─ frontend/                       # DApp sederhana (opsional)
 └─ report/                         # Laporan akhir tim
```

---

## Sistem Penilaian
Praktikum berkontribusi **60–70%** dari total penilaian mata kuliah, dengan rincian:  
- Proyek (TinyChain & TinyCoin): 35%  
- Tugas individu (kuis, laporan mingguan, commit): 25%  
- Partisipasi kelas: 5%  
- **Ujian Tengah Semester (UTS): 15%**  
- **Ujian Akhir Semester (UAS): 20%**  

---

## Referensi Utama
- Katz, J., & Lindell, Y. *Introduction to Modern Cryptography*  
- Stallings, W. *Cryptography and Network Security*  
- Narayanan, A. et al. *Bitcoin and Cryptocurrency Technologies*  
- Antonopoulos, A. M. *Mastering Bitcoin*  
- Ethereum & Solidity Documentation (OpenZeppelin, Hardhat, Foundry)  

---

## Lisensi
Repositori ini menggunakan lisensi MIT. Pemanfaatan dan modifikasi diperbolehkan dengan tetap mencantumkan atribusi.
