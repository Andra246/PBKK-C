# Pertemuan 1

Sistem Database Mahasiswa sederhana menggunakan .NET.

## Fitur

Program memiliki beberapa pilihan menu:

1. Tambah Mahasiswa — Menambahkan data mahasiswa baru.

2. Tampilkan Mahasiswa — Menampilkan semua data mahasiswa yang sudah dimasukkan.

3. Cari Mahasiswa — Mencari data mahasiswa berdasarkan NIM.

4. Hapus Mahasiswa — Menghapus data mahasiswa berdasarkan NIM.

5. Keluar — Mengakhiri program.

## Data Mahasiswa

Setiap mahasiswa memiliki empat data utama:

1. NIM — Nomor Induk Mahasiswa

2. Nama — Nama mahasiswa

3. Prodi — Program studi mahasiswa

4. IPK — Indeks Prestasi Kumulatif mahasiswa

Data tersebut dibuat menggunakan class Mahasiswa.

```
class Mahasiswa
{
    public string NIM { get; set; }
    public string Nama { get; set; }
    public string Prodi { get; set; }
    public double IPK { get; set; }
}
```

Class ini merupakan template untuk membuat data mahasiswa.

## Penyimpanan Data

Data mahasiswa disimpan menggunakan `List<Mahasiswa>`:

```
static List<Mahasiswa> daftarMahasiswa =
    new List<Mahasiswa>();
```

Setiap kali mahasiswa baru ditambahkan, data tersebut akan dimasukkan ke dalam list.

## Cara Kerja Program

Ketika program dijalankan, pengguna akan melihat menu utama. Pengguna kemudian memilih salah satu pilihan dengan memasukkan angka.

Pilihan tersebut diproses menggunakan `switch`.

Contohnya:

1 → Tambah Mahasiswa

2 → Tampilkan Mahasiswa

3 → Cari Mahasiswa

4 → Hapus Mahasiswa

5 → Keluar

Setelah suatu proses selesai, program akan kembali ke menu utama selama pengguna belum memilih pilihan 5.

## Menambahkan Data

Pada menu Tambah Mahasiswa, pengguna akan diminta memasukkan NIM, nama, program studi, dan IPK.

Program juga melakukan validasi pada IPK. Nilai IPK harus berada di antara 0 sampai 4.

Setelah data selesai dimasukkan, program membuat object Mahasiswa dan menyimpannya ke dalam daftarMahasiswa.

## Menampilkan Data

Menu Tampilkan Mahasiswa digunakan untuk melihat semua data yang sudah tersimpan.

Program menggunakan `foreach` untuk mengambil setiap mahasiswa dari list dan menampilkannya dalam bentuk tabel.

Jika belum ada mahasiswa yang dimasukkan, program akan menampilkan pesan bahwa belum ada data mahasiswa.

## Mencari Data

Menu Cari Mahasiswa digunakan untuk mencari mahasiswa berdasarkan NIM.

Program akan memeriksa setiap data mahasiswa yang ada di dalam list. Jika NIM yang dicari ditemukan, informasi mahasiswa tersebut akan ditampilkan.

Jika tidak ditemukan, program akan memberikan pesan bahwa mahasiswa tersebut tidak ditemukan.

## Menghapus Data

Menu Hapus Mahasiswa juga menggunakan NIM sebagai dasar pencarian.

Setelah mahasiswa ditemukan, data tersebut akan dihapus dari daftarMahasiswa menggunakan:

```
daftarMahasiswa.Remove(mahasiswaDitemukan);
```

Jika NIM tidak ditemukan, program akan menampilkan pesan bahwa data mahasiswa tidak ditemukan.
