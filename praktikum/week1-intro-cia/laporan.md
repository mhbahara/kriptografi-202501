# Laporan Minggu 1 - Intro CIA

# Laporan: CIA Triad dan Peran Kriptografi dalam Kehidupan Sehari-hari

## 1. Konsep Dasar Confidentiality, Integrity, Availability (CIA)

Dalam keamanan informasi, terdapat tiga prinsip utama yang disebut **CIA Triad**: Confidentiality, Integrity, dan Availability. Prinsip ini menjadi dasar dalam menjaga data dan sistem informasi agar tetap aman.

### a. Confidentiality (Kerahasiaan)
- **Definisi**: Menjamin bahwa informasi hanya dapat diakses oleh pihak yang berhak.
- **Tujuan**: Melindungi data sensitif dari akses tidak sah.
- **Contoh**:  
  - Penggunaan password atau autentikasi biometrik.  
  - Enkripsi pesan di WhatsApp (end-to-end encryption).  

### b. Integrity (Integritas)
- **Definisi**: Menjaga keaslian dan konsistensi data agar tidak diubah tanpa izin.
- **Tujuan**: Memastikan data tetap valid dan tidak dimanipulasi.
- **Contoh**:  
  - Tanda tangan digital pada dokumen elektronik.  
  - Hashing (misalnya SHA-256) untuk memverifikasi keutuhan file.  

### c. Availability (Ketersediaan)
- **Definisi**: Menjamin data atau layanan selalu tersedia untuk pihak yang berhak.
- **Tujuan**: Memastikan pengguna dapat mengakses informasi kapanpun dibutuhkan.
- **Contoh**:  
  - Server dengan backup dan load balancing.  
  - Sistem perlindungan terhadap serangan DDoS.  

Singkatnya:  
- **Confidentiality** → menjaga informasi tetap rahasia.  
- **Integrity** → memastikan data tetap utuh/asli.  
- **Availability** → menjamin aksesibilitas data/layanan.  


## 2. Peran Kriptografi dalam Kehidupan Sehari-hari

**Kriptografi** adalah ilmu yang digunakan untuk mengamankan informasi melalui proses enkripsi, dekripsi, hashing, dan tanda tangan digital. Perannya sangat penting dalam menjaga kerahasiaan, keaslian, serta keamanan data.

### a. Password Hashing (Login Sistem)
- Password yang disimpan di database tidak dalam bentuk asli, melainkan diubah menjadi **hash**.  
- Dengan demikian, meskipun database bocor, password asli sulit diketahui.  
- Contoh: login akun email, e-commerce, atau media sosial.  

### b. Chip pada Kartu ATM & Kartu Kredit (EMV)
- Kartu ATM/kredit modern menggunakan **chip EMV** dengan kriptografi untuk menghasilkan kode unik tiap transaksi.  
- Mencegah cloning kartu dan menjaga integritas transaksi.  

### c. Face ID / Fingerprint pada Smartphone
- Sistem biometrik menyimpan data dalam bentuk terenkripsi, bukan gambar asli.  
- Menggunakan kriptografi kunci publik agar hanya perangkat sah yang bisa mengaksesnya.  
- Contoh: membuka HP, otorisasi pembayaran di aplikasi banking.  

### d. E-Commerce & Payment Gateway
- Transaksi online diamankan dengan kriptografi.  
- Menjamin kerahasiaan data transaksi, autentikasi identitas, serta mencegah manipulasi harga.  
- Contoh: QRIS, pembayaran di marketplace.  

### e. DRM (Digital Rights Management)	
- Konten digital (game, film, musik) dienkripsi agar hanya pengguna sah yang bisa mengaksesnya.  
- Mencegah pembajakan.  
- Contoh: Netflix, Spotify, Steam.  

### f. Sistem Navigasi GPS
- GPS modern menggunakan kriptografi agar sinyal asli tidak bisa dipalsukan (*anti-spoofing*).  
- Penting untuk navigasi pesawat, kapal, hingga kendaraan otonom.  

---

## 3. Kesimpulan
- **CIA Triad** (Confidentiality, Integrity, Availability) adalah prinsip dasar keamanan informasi.  
- **Kriptografi** mendukung penerapan CIA Triad melalui berbagai aplikasi nyata: **password hashing, chip ATM/kredit, biometrik smartphone, e-commerce, DRM, hingga GPS**.  
- Tanpa kriptografi, layanan digital modern akan sangat rentan terhadap pencurian data, manipulasi informasi, dan serangan siber.  

