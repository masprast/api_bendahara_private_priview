# API Transaksi Bendahara

Repositori ini merupakan API untuk transaksi bendahara yang tersimpan di GCP (_Google Cloud Platform_). Dan menggunakan MongoDB sebagai _database_-nya,yang juga tersimpan di cloud dengan alamat yang berbeda.

Klik link 👉 [demo API](https://bendaharaapi-392411.as.r.appspot.com/api/pengguna/1/transaksi?tahun=2023) untuk mencoba API.

## Tech stack

- NodeJS
- GCP
- JWT auth
- MongoDB

## Query

API ini memiliki fungsi _query_ untuk menyaring informasi. _Query_ yang tersedia antara lain:

| _query_   | keterangan                                                       | nilai                      |
| --------- | ---------------------------------------------------------------- | -------------------------- |
| `tahun`   | untuk menyaring transaksi berdasarkan tahun                      | default: `Date.now().year` |
| `halaman` | untuk membagi jumlah transaksi yang ditampilkan menjadi halaman  | default: 1                 |
| `cari`    | untuk mencari transaksi berdasarkan item                         | format: 'seragam'          |
| `hmax`    | untuk mencari transaksi dengan item yang memiliki harga < `hmax` | format: 234500             |
| `hmin`    | untuk mencari transaksi dengan item yang memiliki harga > `hmim` | format: 234500             |
| `unit`    | untuk mencari transaksi berdasarkan unit lembaga                 | format: smp                |
| `tgl`     | untuk mencari transaksi yang dibuat pada tanggal tertentu        | format:                    |
| `bulan`   | untuk mencari transaksi yang dibuat pada bulan tertentu          | format: 09                 |
| `tawal`   | untuk mencari transaksi yang dibuat setelah tanggal tertentu     | format: 2023-09-23         |
| `takhir`  | untuk mencari transaksi yang dibuat sebelum tanggal tertentu     | format: 2023-09-23         |

- jumlah data = 1000 transaksi (generate antara tahun 2020 - 2023)
