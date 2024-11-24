
# Crypto List - Tugas 2 MSIM4401

Aplikasi ini merupakan tugas dari mata kuliah **MSIM4401** yang bertujuan untuk menampilkan daftar cryptocurrency yang diambil dari API [CoinLore](https://api.coinlore.net/api/tickers/). Aplikasi ini dibangun menggunakan **Ionic Framework** dengan **Vue 3** dan menggunakan **TypeScript** untuk menjaga struktur data yang kuat.

## Fitur Utama
- Menampilkan nama, simbol, dan harga (USD) dari cryptocurrency.
- Memuat data secara dinamis melalui API menggunakan tombol **Get Data**.
- Tampilan tabel yang responsif dengan kolom **Name**, **Symbol**, dan **Harga USD**.
- Menampilkan pesan saat data belum dimuat.

## Cara Menjalankan Aplikasi
1. **Clone repository ini**:
   ```bash
   git clone <url-repository>
   cd <nama-folder>
   ```

2. **Install dependensi**:
   Jalankan perintah berikut untuk menginstal semua dependensi yang diperlukan:
   ```bash
   npm install
   ```

3. **Jalankan aplikasi**:
   Gunakan perintah berikut untuk menjalankan aplikasi:
   ```bash
   ionic serve
   ```

4. **Akses aplikasi**:
   Buka browser Anda dan akses aplikasi pada alamat:
   ```
   http://localhost:8100
   ```

## Teknologi yang Digunakan
- **Ionic Framework**: Untuk membangun aplikasi dengan desain responsif dan elemen-elemen UI yang modern.
- **Vue 3**: Framework JavaScript untuk membangun antarmuka pengguna.
- **TypeScript**: Untuk memastikan tipe data yang konsisten di seluruh aplikasi.
- **Axios**: Untuk melakukan permintaan HTTP ke API.


## Cara Kerja
1. Klik tombol **Get Data** untuk memuat data cryptocurrency.
2. Aplikasi akan mengirimkan permintaan ke API CoinLore untuk mendapatkan data cryptocurrency.
3. Data yang berhasil dimuat akan ditampilkan dalam tabel dengan kolom:
   - **Name**: Nama cryptocurrency.
   - **Symbol**: Simbol cryptocurrency.
   - **Harga USD**: Harga cryptocurrency dalam USD.

## Contoh Tampilan
**Tampilan saat data berhasil dimuat**:
```
| Name         | Symbol | Harga USD  |
|--------------|--------|------------|
| Bitcoin      | BTC    | 98389.96   |
| Ethereum     | ETH    | 1702.54    |
| Binance Coin | BNB    | 220.00     |
```

**Pesan jika data belum dimuat**:
```
Belum ada data. Silahkan klik "Get Data" untuk mendapatkan cryptocurrency list.
```

## Catatan
- Pastikan Anda memiliki koneksi internet yang aktif untuk memuat data dari API.
- Anda dapat memodifikasi proyek ini untuk menambahkan fitur lainnya, seperti pagination atau filter data cryptocurrency.

---
