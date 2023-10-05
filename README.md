# API Transaksi Bendahara

Repositori ini merupakan API untuk transaksi bendahara yang tersimpan di GCP (_Google Cloud Platform_). Dan menggunakan MongoDB sebagai _database_-nya,yang juga tersimpan di cloud dengan alamat yang berbeda.

Klik link 👉 [demo API](https://bendaharaapi-392411.as.r.appspot.com/api/pengguna/1/transaksi?tahun=2023) untuk mencoba API.

## Tech stack

- NodeJS
- Express
- GCP
- JWT auth
- MongoDB

## Query

API ini memiliki fungsi _query_ untuk menyaring informasi. _Query_ yang tersedia antara lain:

| _query_   | keterangan                                                       | nilai                         |
| --------- | ---------------------------------------------------------------- | ----------------------------- |
| `tahun`   | untuk menyaring transaksi berdasarkan tahun                      | _default_ : `Date.now().year` |
| `halaman` | untuk membagi jumlah transaksi yang ditampilkan menjadi halaman  | _default_ : 1                 |
| `cari`    | untuk mencari transaksi berdasarkan item                         | _format_ : seragam            |
| `hmax`    | untuk mencari transaksi dengan item yang memiliki harga < `hmax` | _format_ : 234500             |
| `hmin`    | untuk mencari transaksi dengan item yang memiliki harga > `hmim` | _format_ : 234500             |
| `unit`    | untuk mencari transaksi berdasarkan unit lembaga                 | _format_ : smp                |
| `tgl`     | untuk mencari transaksi yang dibuat pada tanggal tertentu        | _format_ : 2023-09-23         |
| `bulan`   | untuk mencari transaksi yang dibuat pada bulan tertentu          | _format_ : 9                  |
| `tawal`   | untuk mencari transaksi yang dibuat setelah tanggal tertentu     | _format_ : 2023-09-23          |
| `takhir`  | untuk mencari transaksi yang dibuat sebelum tanggal tertentu     | _format_ : 2023-09-23          |

- jumlah data = 1000 transaksi (rentang waktu antara 2020 - 2023)
