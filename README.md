
# Tahap 1 — Jaringan Dasar dan Linux

## 1.1 Dasar Linux
- `pwd`: melihat direktori aktif.
- `ls`: melihat isi direktori.
- `cd`: berpindah direktori.
- `mkdir`: membuat folder.
- `touch`: membuat file.

## 1.2 Pengelolaan File dan Folder
- `cp`: menyalin file atau folder.
- `mv`: memindahkan atau mengganti nama.
- `rm`: menghapus file.
- `rmdir`: menghapus folder kosong.
- `find`: mencari file atau folder.
- Nama folder dengan spasi dapat menggunakan tanda kutip atau `\`.
- Nama yang diawali titik biasanya tersembunyi secara default.

## 1.3 Permission dan Hak Akses
- `rwx`: read, write, execute.
- `chmod`: mengubah permission.
- `chown`: mengubah pemilik.
- `chgrp`: mengubah grup.
- `whoami` dan `id`: melihat identitas pengguna.
- `sudo`: menjalankan perintah dengan hak administrator jika diizinkan.

## 1.4 Membaca dan Mengedit File
- `cat`, `less`, `head`, `tail`: membaca isi file.
- `nano`: mengedit teks melalui terminal.

## 1.5 Dasar Networking — IP Address

Perintah praktik:

`ip -4 addr show enp0s1`

- `ip`: informasi jaringan.
- `-4`: memilih informasi IPv4.
- `addr`: informasi alamat.
- `show`: menampilkan informasi.
- `enp0s1`: antarmuka jaringan Ubuntu.

Hasil praktik:
- IP Ubuntu di UTM: `192.168.64.4`
- Prefix: `/24`
- Subnet mask: `255.255.255.0`
- IP MacBook pada Wi-Fi: `192.168.0.19`
- Router Wi-Fi MacBook: `192.168.0.1`

Pemahaman:
- Ubuntu berjalan sebagai mesin virtual di UTM.
- IP Ubuntu berbeda dari IP MacBook.
- `/24` menunjukkan panjang prefix jaringan.
- `dynamic` menunjukkan alamat diberikan secara dinamis.
- `UP` menunjukkan antarmuka jaringan aktif secara administratif.

## Materi Berikutnya
- 1.6 Subnet mask dan prefix
- 1.7 Gateway
- 1.8 Routing
- 1.9 DNS
- 1.10 HTTP dan HTTPS
- 1.11 Pengujian konektivitas jaringan
- 1.12 Evaluasi akhir Tahap 1

Status: Sedang mempelajari Tahap 1.
