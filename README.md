# API Transaksi Bendahara (private backend project)

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
    {
      "key_transaksi": "SMK0120231228-05",
      "pengguna": {
        "id_pengguna": 1,
        "nama_pengguna": "Suparniningsih",
        "unit": "SMK"
      },
      "unit": "SMK",
      "item": "item ke",
      "jumlah": 2,
      "harga": 909402,
      "total": 1818804,
      "keterangan": "keterangan item ke",
      "dibuat": "2023-12-28T19:12:27.597Z",
      "yg_diperbarui": []
    },
    {
      "key_transaksi": "SMK0220231224-02",
      "pengguna": {
        "id_pengguna": 2,
        "nama_pengguna": "Suyati",
        "unit": "SMP"
      },
      "unit": "SMK",
      "item": "lain-lain",
      "jumlah": 7,
      "harga": 420171,
      "total": 2941197,
      "keterangan": "keterangan lain-lain",
      "dibuat": "2023-12-24T09:48:47.642Z",
      "yg_diperbarui": []
    },
    {
      "key_transaksi": "SMK0220231220-02",
      "pengguna": {
        "id_pengguna": 2,
        "nama_pengguna": "Suyati",
        "unit": "SMP"
      },
      "unit": "SMK",
      "item": "makanan",
      "jumlah": 2,
      "harga": 42953,
      "total": 85906,
      "keterangan": "keterangan makanan",
      "dibuat": "2023-12-20T14:12:40.939Z",
      "yg_diperbarui": []
    },
    {
      "key_transaksi": "SMK0220231216-01",
      "pengguna": {
        "id_pengguna": 2,
        "nama_pengguna": "Suyati",
        "unit": "SMP"
      },
      "unit": "SMK",
      "item": "lain-lain",
      "jumlah": 10,
      "harga": 455130,
      "total": 4551300,
      "keterangan": "keterangan lain-lain",
      "dibuat": "2023-12-16T13:04:35.811Z",
      "yg_diperbarui": []
    },
    {
      "key_transaksi": "SMK0220231214-02",
      "pengguna": {
        "id_pengguna": 2,
        "nama_pengguna": "Suyati",
        "unit": "SMP"
      },
      "unit": "SMK",
      "item": "bensin",
      "jumlah": 8,
      "harga": 350599,
      "total": 2804792,
      "keterangan": "keterangan bensin",
      "dibuat": "2023-12-14T12:53:10.315Z",
      "yg_diperbarui": []
    },
    {
      "key_transaksi": "SMK0220231206-01",
      "pengguna": {
        "id_pengguna": 2,
        "nama_pengguna": "Suyati",
        "unit": "SMP"
      },
      "unit": "SMK",
      "item": "cemilan",
      "jumlah": 5,
      "harga": 718283,
      "total": 3591415,
      "keterangan": "keterangan cemilan",
      "dibuat": "2023-12-06T16:35:31.956Z",
      "yg_diperbarui": []
    },
    {
      "key_transaksi": "SMK0120231202-02",
      "pengguna": {
        "id_pengguna": 1,
        "nama_pengguna": "Suparniningsih",
        "unit": "SMK"
      },
      "unit": "SMK",
      "item": "seragam",
      "jumlah": 8,
      "harga": 912507,
      "total": 7300056,
      "keterangan": "keterangan seragam",
      "dibuat": "2023-12-02T13:35:49.238Z",
      "yg_diperbarui": []
    },
    {
      "key_transaksi": "SMK0120231201-04",
      "pengguna": {
        "id_pengguna": 1,
        "nama_pengguna": "Suparniningsih",
        "unit": "SMK"
      },
      "unit": "SMK",
      "item": "cemilan",
      "jumlah": 3,
      "harga": 272471,
      "total": 817413,
      "keterangan": "keterangan cemilan",
      "dibuat": "2023-12-01T21:18:44.067Z",
      "yg_diperbarui": []
    },
    {
      "key_transaksi": "SMK0120231201-03",
      "pengguna": {
        "id_pengguna": 1,
        "nama_pengguna": "Suparniningsih",
        "unit": "SMK"
      },
      "unit": "SMK",
      "item": "cemilan",
      "jumlah": 7,
      "harga": 485123,
      "total": 3395861,
      "keterangan": "keterangan cemilan",
      "dibuat": "2023-12-01T10:25:35.154Z",
      "yg_diperbarui": []
    },
    {
      "key_transaksi": "SMK0120231130-05",
      "pengguna": {
        "id_pengguna": 1,
        "nama_pengguna": "Suparniningsih",
        "unit": "SMK"
      },
      "unit": "SMK",
      "item": "lain-lain",
      "jumlah": 6,
      "harga": 635330,
      "total": 3811980,
      "keterangan": "keterangan lain-lain",
      "dibuat": "2023-11-30T14:40:40.779Z",
      "yg_diperbarui": []
    },
    {
      "key_transaksi": "SMK0120231129-02",
      "pengguna": {
        "id_pengguna": 1,
        "nama_pengguna": "Suparniningsih",
        "unit": "SMK"
      },
      "unit": "SMK",
      "item": "item ke",
      "jumlah": 5,
      "harga": 589868,
      "total": 2949340,
      "keterangan": "keterangan item ke",
      "dibuat": "2023-11-29T11:20:37.431Z",
      "yg_diperbarui": []
    },
    {
      "key_transaksi": "SMK0220231128-01",
      "pengguna": {
        "id_pengguna": 2,
        "nama_pengguna": "Suyati",
        "unit": "SMP"
      },
      "unit": "SMK",
      "item": "lain-lain",
      "jumlah": 9,
      "harga": 511864,
      "total": 4606776,
      "keterangan": "keterangan lain-lain",
      "dibuat": "2023-11-28T08:19:02.617Z",
      "yg_diperbarui": []
    },
    {
      "key_transaksi": "SMK0120231124-02",
      "pengguna": {
        "id_pengguna": 1,
        "nama_pengguna": "Suparniningsih",
        "unit": "SMK"
      },
      "unit": "SMK",
      "item": "cemilan",
      "jumlah": 9,
      "harga": 83430,
      "total": 750870,
      "keterangan": "keterangan cemilan",
      "dibuat": "2023-11-24T03:51:40.347Z",
      "yg_diperbarui": []
    },
    {
      "key_transaksi": "SMK0220231120-04",
      "pengguna": {
        "id_pengguna": 2,
        "nama_pengguna": "Suyati",
        "unit": "SMP"
      },
      "unit": "SMK",
      "item": "makanan",
      "jumlah": 4,
      "harga": 236693,
      "total": 946772,
      "keterangan": "keterangan makanan",
      "dibuat": "2023-11-20T15:16:17.197Z",
      "yg_diperbarui": []
    },
    {
      "key_transaksi": "SMK0120231116-05",
      "pengguna": {
        "id_pengguna": 1,
        "nama_pengguna": "Suparniningsih",
        "unit": "SMK"
      },
      "unit": "SMK",
      "item": "item ke",
      "jumlah": 10,
      "harga": 826218,
      "total": 8262180,
      "keterangan": "keterangan item ke",
      "dibuat": "2023-11-16T16:28:50.961Z",
      "yg_diperbarui": []
    },
    {
      "key_transaksi": "SMK0220231113-05",
      "pengguna": {
        "id_pengguna": 2,
        "nama_pengguna": "Suyati",
        "unit": "SMP"
      },
      "unit": "SMK",
      "item": "seragam",
      "jumlah": 6,
      "harga": 559748,
      "total": 3358488,
      "keterangan": "keterangan seragam",
      "dibuat": "2023-11-13T08:37:22.402Z",
      "yg_diperbarui": []
    },
    {
      "key_transaksi": "SMK0220231104-03",
      "pengguna": {
        "id_pengguna": 2,
        "nama_pengguna": "Suyati",
        "unit": "SMP"
      },
      "unit": "SMK",
      "item": "seragam",
      "jumlah": 7,
      "harga": 405433,
      "total": 2838031,
      "keterangan": "keterangan seragam",
      "dibuat": "2023-11-04T11:16:23.589Z",
      "yg_diperbarui": []
    },
    {
      "key_transaksi": "SMK0120231026-04",
      "pengguna": {
        "id_pengguna": 1,
        "nama_pengguna": "Suparniningsih",
        "unit": "SMK"
      },
      "unit": "SMK",
      "item": "alat",
      "jumlah": 2,
      "harga": 683132,
      "total": 1366264,
      "keterangan": "keterangan alat",
      "dibuat": "2023-10-26T08:09:56.340Z",
      "yg_diperbarui": []
    }
  ]
}
```
