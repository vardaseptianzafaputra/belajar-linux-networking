# Belajar Linux & Networking

Repositori ini berisi catatan belajar mandiri tentang Linux dan dasar jaringan komputer sebagai fondasi untuk mempelajari cybersecurity.

## 🎯 Tujuan Belajar

- Memahami penggunaan terminal Linux.
- Memahami pengelolaan file, folder, dan permission.
- Memahami IP address, subnet, gateway, dan routing.
- Memahami DNS, HTTP/HTTPS, serta pengujian koneksi jaringan.
- Mempersiapkan fondasi untuk belajar Python, SQL, dan cybersecurity.

---

## 📚 Tahap 1 — Linux Dasar & Networking

### 1.1 Terminal dan Navigasi

| Perintah | Fungsi |
|---|---|
| `pwd` | Menampilkan direktori saat ini |
| `ls` | Menampilkan isi direktori |
| `ls -a` | Menampilkan isi termasuk file tersembunyi |
| `cd` | Berpindah direktori |
| `mkdir` | Membuat folder |
| `touch` | Membuat file kosong |
| `cat` | Menampilkan isi file |
| `less` | Membaca file dengan navigasi |
| `head` | Menampilkan bagian awal file |
| `tail` | Menampilkan bagian akhir file |
| `nano` | Membuka editor teks di terminal |
| `find` | Mencari file atau folder |
| `cp` | Menyalin file atau folder |
| `mv` | Memindahkan atau mengganti nama |
| `rm` | Menghapus file |
| `rmdir` | Menghapus folder kosong |

### 1.2 File, Folder, dan Path

- `.` berarti direktori saat ini.
- `..` berarti direktori induk.
- Nama yang diawali titik, misalnya `.config`, biasanya merupakan file atau folder tersembunyi.
- `mv catatan.txt catatan-baru.txt` mengganti nama file.
- `mv catatan.txt Dokumen/` memindahkan file ke folder `Dokumen`.
- Tanda `/` di akhir tujuan bisa memperjelas bahwa tujuan adalah folder, tetapi tidak selalu wajib.

### 1.3 Permission Linux

Permission dasar:

- `r` = read (membaca).
- `w` = write (menulis atau mengubah).
- `x` = execute (menjalankan file atau mengakses direktori).
- `u` = user/owner (pemilik).
- `g` = group (grup).
- `o` = others (pengguna lain).

Nilai numerik:

- `r = 4`
- `w = 2`
- `x = 1`

Contoh:

- `chmod 644 catatan.txt` memberikan pemilik hak baca/tulis dan grup serta pengguna lain hak baca.
- `chmod 755 skrip.sh` memberikan pemilik hak baca/tulis/jalankan dan grup serta pengguna lain hak baca/jalankan.
- `chmod` mengubah permission.
- `chown` mengubah pemilik file.
- `sudo` menjalankan perintah dengan hak administratif jika diizinkan.

> Hindari memakai `chmod 777` tanpa alasan yang jelas karena memberikan hak luas kepada semua pengguna.

### 1.4 IP Address dan Interface

IP Ubuntu di mesin virtual saat latihan:

`192.168.64.4/24`

Interface jaringan:

`enp0s1`

Perintah untuk melihat alamat IPv4:

```bash
ip -4 addr show enp0s1
```

IP mesin virtual dapat berbeda dari IP Mac karena menggunakan jaringan virtual UTM.

### 1.5 Subnet dan CIDR

`/24` berarti 24 bit digunakan untuk prefix jaringan.

Contoh `192.168.64.4/24`:

- IP host: `192.168.64.4`
- Prefix: `/24`
- Subnet mask: `255.255.255.0`
- Network address: `192.168.64.0`
- Broadcast address: `192.168.64.255`
- Host bit: 8

Rentang alamat host yang umum dapat digunakan pada subnet tersebut adalah `192.168.64.1` sampai `192.168.64.254`, dengan mempertimbangkan konfigurasi jaringan.

### 1.6 Gateway dan Routing

Gateway Ubuntu saat latihan:

`192.168.64.1`

Perintah untuk memeriksa routing:

```bash
ip route
```

Gateway biasanya menjadi jalur keluar menuju jaringan lain jika tidak ada rute yang lebih spesifik.

### 1.7 DNS

DNS menerjemahkan nama domain menjadi alamat IP.

Perintah yang sudah dipraktikkan:

```bash
getent hosts google.com
nslookup google.com
```

Jika akses menggunakan alamat IP berhasil tetapi nama domain gagal diresolusikan, DNS merupakan salah satu hal yang perlu diperiksa.

### 1.8 Pengujian Koneksi

Perintah yang sudah dipraktikkan:

```bash
ping -c 4 192.168.64.1
ping -c 4 8.8.8.8
ping -c 4 google.com
```

- `-c 4` membatasi pengiriman menjadi empat paket.
- `0% packet loss` berarti semua paket yang dikirim mendapat balasan.
- `100% packet loss` berarti tidak ada paket yang mendapat balasan. Ini tidak selalu membuktikan bahwa seluruh koneksi internet mati karena tujuan atau jaringan dapat memblokir ping.

### 1.9 HTTP dan HTTPS

Perintah yang sudah dipraktikkan:

```bash
curl -I https://www.google.com/
curl -IL https://google.com
```

- `curl` digunakan untuk melakukan permintaan ke URL.
- `-I` meminta header respons.
- `-L` mengikuti pengalihan (redirect).
- HTTP `301` menunjukkan pengalihan permanen.
- HTTP `200` menunjukkan permintaan berhasil diproses.

---

## 📝 Evaluasi Tahap 1

Hasil evaluasi utama: **10/12 (83,3%)**.

Materi yang perlu diperkuat:

1. Memahami arti `100% packet loss`.
2. Membedakan IP host dengan network address.

Latihan tambahan juga mencakup `chmod`, `sudo`, `chown`, `find`, `cat`, `mv`, dan `ls -a`.

## 🚧 Materi Lanjutan

Materi berikutnya yang perlu dipelajari dan dipraktikkan secara bertahap:

- Memperkuat subnet dan perhitungan network address.
- Routing lebih lanjut.
- Pemeriksaan koneksi dan troubleshooting jaringan.
- Evaluasi akhir dengan praktik langsung.

Catatan: perintah `traceroute` belum dipraktikkan dalam sesi belajar ini.

---

## 📌 Prinsip Belajar

- Praktik langsung di Ubuntu melalui UTM.
- Memahami fungsi perintah sebelum menggunakannya.
- Tidak menjalankan perintah berisiko tanpa memahami dampaknya.
- Memperbarui catatan setelah materi benar-benar dipelajari.
