# 🛒 Toko Sembako Berbasis FIFO

## 📌 Deskripsi

Toko Sembako Berbasis FIFO adalah aplikasi sistem informasi berbasis web yang dirancang untuk membantu proses pengelolaan barang, persediaan, pembelian, dan penjualan pada toko sembako.

Aplikasi ini menggunakan metode **FIFO (First In, First Out)** dalam pengelolaan persediaan. Setiap barang yang masuk dicatat sebagai batch dengan tanggal masuk, jumlah stok, dan harga beli. Ketika terjadi penjualan, sistem akan mengambil stok dari batch yang paling lama masuk terlebih dahulu.

Aplikasi dikembangkan menggunakan **Java dengan Spring Boot** dan menggunakan **MySQL** sebagai database.

---

## 🎯 Tujuan

Aplikasi ini dibuat untuk membantu pengelolaan persediaan dan transaksi pada toko sembako dengan menerapkan metode FIFO.

Tujuan utama aplikasi:

- Mengelola data barang.
- Mengelola kategori barang.
- Mencatat barang atau stok yang masuk.
- Mencatat transaksi penjualan.
- Mengelola stok berdasarkan batch.
- Menerapkan algoritma FIFO pada pengeluaran stok.
- Menghitung Harga Pokok Penjualan (HPP) berdasarkan batch stok yang digunakan.
- Menyediakan riwayat stok dan transaksi penjualan.

---

## ✨ Fitur Aplikasi

### 📊 Dashboard
Menampilkan halaman utama aplikasi sebagai pusat navigasi menuju fitur-fitur pengelolaan toko.

### 📦 Data Barang
Digunakan untuk mengelola data barang yang tersedia di toko.

### 🏷️ Kategori Barang
Digunakan untuk mengelola kategori barang.

### 📥 Pembelian / Stok Masuk
Mencatat barang yang masuk ke dalam persediaan.

Setiap stok masuk dicatat sebagai batch yang memiliki:

- Barang
- Tanggal masuk
- Jumlah
- Harga beli
- Sisa stok

### 🔄 Stok FIFO
Menampilkan dan mengelola persediaan berdasarkan metode **First In, First Out (FIFO)**.

### 🛒 Penjualan
Mencatat transaksi penjualan barang.

Saat transaksi dilakukan, sistem akan:

1. Memeriksa ketersediaan stok.
2. Mengambil stok dari batch paling lama.
3. Menggunakan batch berikutnya jika stok batch sebelumnya tidak mencukupi.
4. Mengurangi jumlah stok.
5. Menghitung total penjualan.
6. Menghitung HPP berdasarkan batch yang digunakan.
7. Menyimpan detail batch yang digunakan dalam transaksi.

### 📋 Riwayat Penjualan
Menampilkan riwayat transaksi penjualan yang telah dilakukan.

### 📑 Kartu / Riwayat Stok
Menampilkan riwayat stok masuk berdasarkan barang dan urutan tanggal masuk.

---

## 🔄 Implementasi Algoritma FIFO

Metode yang digunakan dalam aplikasi adalah:

**FIFO (First In, First Out)**

Prinsip FIFO adalah barang yang pertama kali masuk akan diprioritaskan untuk keluar atau dijual terlebih dahulu.

Contoh:

| Batch | Tanggal Masuk | Stok |
|---|---|---:|
| Batch 1 | 1 Agustus | 10 |
| Batch 2 | 5 Agustus | 15 |
| Batch 3 | 10 Agustus | 20 |

Jika terjadi penjualan sebanyak **12 barang**, sistem akan:

- Mengambil 10 barang dari Batch 1.
- Mengambil 2 barang dari Batch 2.

Sehingga:

- Batch 1 → sisa 0
- Batch 2 → sisa 13
- Batch 3 → sisa 20

Dengan cara tersebut, sistem memastikan stok yang lebih dahulu masuk digunakan terlebih dahulu.

---

## 💰 Perhitungan HPP

Selain mengurangi stok menggunakan FIFO, aplikasi juga mencatat batch yang digunakan dalam transaksi penjualan.

Hal ini memungkinkan sistem menghitung **Harga Pokok Penjualan (HPP)** berdasarkan harga beli dari masing-masing batch.

Jika satu transaksi menggunakan lebih dari satu batch dengan harga beli berbeda, HPP dihitung berdasarkan jumlah barang yang diambil dari setiap batch.

---

## 🏗️ Arsitektur Aplikasi

Project menggunakan struktur aplikasi Spring Boot dengan pemisahan beberapa bagian utama:

```text
src/
└── main/
    ├── java/
    │   └── com.tokosembako.tokosembako/
    │       ├── controller/
    │       ├── dto/
    │       ├── entity/
    │       ├── repository/
    │       └── service/
    │
    └── resources/
        ├── templates/
        └── application.properties
Status Project

Project ini masih dalam tahap pengembangan dan penyempurnaan fitur serta dokumentasi.
