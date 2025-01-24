# API Transaksi Bendahara (private mock backend project)

Repositori ini merupakan API untuk transaksi bendahara yang tersimpan di ~~**GCP** (_Google Cloud Platform_)~~ ~~**Heroku**~~ ~~**AWS ECS**~~ **railway.app**. Dan menggunakan MongoDB sebagai _database_-nya,yang juga tersimpan di _cloud_ dengan layanan [MongoDB Atlas]().

Klik link 👉 [demo API](apibendahara-production.up.railway.app/api/pengguna/1/transaksi?tahun=2023&unit=smk) untuk mencoba API.

## Tech stack

- NodeJS
- ExpressJS
- ~~GAE (Google App Engine)~~ ~~Heroku~~ ~~AWS ECS~~
- JWT
- MongoDB Atlas

## Query

API ini memiliki fungsi _query_ untuk menyaring informasi. _Query_ yang tersedia antara lain:

| _QUERY_   | KETERANGAN                                                       | NILAI                                            |
| --------- | ---------------------------------------------------------------- | ------------------------------------------------ |
| `tahun`   | untuk menyaring transaksi berdasarkan tahun                      | _default_ : `new Date(Date.now()).getFullYear()` |
| `unit`    | untuk mencari transaksi berdasarkan unit lembaga                 | _format_ : smp                                   |
| `halaman` | untuk membagi jumlah transaksi yang ditampilkan menjadi halaman  | _default_ : 1                                    |
| `batas`   | untuk menentukan batasan jumlah item yang diambil                | _default_ : 20                                   |
| `cari`    | untuk mencari transaksi berdasarkan item                         | _format_ : seragam                               |
| `hmax`    | untuk mencari transaksi dengan item yang memiliki harga < `hmax` | _format_ : 234500                                |
| `hmin`    | untuk mencari transaksi dengan item yang memiliki harga > `hmin` | _format_ : 234500                                |
| `tgl`     | untuk mencari transaksi yang dibuat pada tanggal tertentu        | _format_ : 2023-09-23                            |
| `bulan`   | untuk mencari transaksi yang dibuat pada bulan tertentu          | _format_ : 9                                     |
| `tawal`   | untuk mencari transaksi yang dibuat **setelah** tanggal tertentu     | _format_: 2023-09-23                             |
| `takhir`  | untuk mencari transaksi yang dibuat **sebelum** tanggal tertentu     | _format_: 2023-09-23                             |

- jumlah data = 1000 transaksi (rentang waktu antara Januari 2020 - April 2024)

## Output
* dengan query default : `?tahun=2023&unit=smk`
```json
{
  "total": 256,
  "halaman": 1,
  "dari": 13,
  "per_halaman": 20,
  "transaksi": [
    {
      "key_transaksi": "SMK0220231231-03",
      "pengguna": {
        "id_pengguna": 2,
        "nama_pengguna": "Suyati",
        "unit": "SMP"
      },
      "unit": "SMK",
      "item": "lain-lain",
      "jumlah": 7,
      "harga": 892613,
      "total": 6248291,
      "keterangan": "keterangan lain-lain",
      "dibuat": "2023-12-31T18:34:57.284Z",
      "yg_diperbarui": []
    },
    {
      "key_transaksi": "SMK0220231230-04",
      "pengguna": {
        "id_pengguna": 2,
        "nama_pengguna": "Suyati",
        "unit": "SMP"
      },
      "unit": "SMK",
      "item": "lain-lain",
      "jumlah": 1,
      "harga": 777105,
      "total": 777105,
      "keterangan": "keterangan lain-lain",
      "dibuat": "2023-12-30T01:41:18.579Z",
      "yg_diperbarui": []
    },
    .
    .
    .
  ]
}
```
