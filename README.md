# API Transaksi Bendahara (private backend project)

Repositori ini merupakan API untuk transaksi bendahara yang tersimpan di ~~GCP (_Google Cloud Platform_)~~ ~~Heroku~~ AWS ECS. Dan menggunakan MongoDB sebagai _database_-nya,yang juga tersimpan di _cloud_ dengan layanan [MongoDB Atlas]().

Klik link 👉 [demo API](http://bendahara-load-balancer-1366339097.ap-southeast-3.elb.amazonaws.com/api/pengguna/1/transaksi) untuk mencoba API.

## Tech stack

- NodeJS
- ExpressJS
- ~~GAE (Google App Engine)~~ ~~Heroku~~ AWS ECS
- JWT
- MongoDB Atlas

## Query

API ini memiliki fungsi _query_ untuk menyaring informasi. _Query_ yang tersedia antara lain:

| _QUERY_   | KETERANGAN                                                       | NILAI                                            |
| --------- | ---------------------------------------------------------------- | ------------------------------------------------ |
| `tahun`   | untuk menyaring transaksi berdasarkan tahun                      | _default_ : `new Date(Date.now()).getFullYear()` |
| `halaman` | untuk membagi jumlah transaksi yang ditampilkan menjadi halaman  | _default_ : 1                                    |
| `cari`    | untuk mencari transaksi berdasarkan item                         | _format_ : seragam                               |
| `hmax`    | untuk mencari transaksi dengan item yang memiliki harga < `hmax` | _format_ : 234500                                |
| `hmin`    | untuk mencari transaksi dengan item yang memiliki harga > `hmin` | _format_ : 234500                                |
| `unit`    | untuk mencari transaksi berdasarkan unit lembaga                 | _format_ : smp                                   |
| `tgl`     | untuk mencari transaksi yang dibuat pada tanggal tertentu        | _format_ : 2023-09-23                            |
| `bulan`   | untuk mencari transaksi yang dibuat pada bulan tertentu          | _format_ : 9                                     |
| `tawal`   | untuk mencari transaksi yang dibuat setelah tanggal tertentu     | _format_: 2023-09-23                             |
| `takhir`  | untuk mencari transaksi yang dibuat sebelum tanggal tertentu     | _format_: 2023-09-23                             |

- jumlah data = 1000 transaksi (rentang waktu antara Januari 2020 - April 2024)

* Note: GCP Free trial periode has ended
