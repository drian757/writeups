# Bandit 5 → 6:

[OverTheWire Bandit Level 5 → 6](https://overthewire.org/wargames/bandit/bandit6.html)

## Deskripsi Level
*The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:*
    *human-readable*
    *1033 bytes in size*
    *not executable*

## Langkah-langkah
Setelah sebelumnya kita berhasil menemukan password, sekarang kita perlu masuk lagi ke server sebagai `bandit5` dengan password `4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw`.
```bash
$ ssh bandit5@bandit.labs.overthewire.org -p 2220
```

Sekarang kita sudah berhasil masuk ke server sebagai `bandit5`, sama seperti sebelumnya kita harus mencari tahu file apa saja yang ada disini dengan menggunakan *command* `ls`.
```bash
$ ls
```

Kali ini kita melihat hal yang berbeda yaitu direktori `inhere`, kita dapat berpindah dari direktori ini ke direktori tersebut dengan menggunakan *command* `cd`.
```bash
$ cd inhere/
```

Setelah masuk kedalam direktori `inhere` kita perlu mencari tahu kembali file apa saja yang ada disini dengan menggunakan *command* `ls`.
```bash
$ ls
```

Disini kita dapat melihat banyak folder, untuk kita mengetahui passwordnya kita dapat menggunakan cara termudah yaitu dengan *command* `find` yang berguna untuk mengidentifikasi jenis atau tipe data dari sebuah file banyaknya folder.
```bash
$ find . -type f -size 1033c ! -executable -exec file {} \;
```
-`.`:Pencarian dimulai dari direktori ini
-`-type f`: Batasi pencarian hanya pada file.
-`-size 1033c`: Cari file yang berukuran tepat 1033 byte (c singkatan dari byte).
-`! -executable`: Kecualikan file yang dapat dieksekusi.
-`-exec file {} \;`: Untuk setiap file yang ditemukan, jalankan perintah file untuk memastikan tipenya.

*Command* di atas akan menghasilkan `./maybehere07/.file2: ASCII text, with very long lines (1000)` yang mungkin berisi password karena file tersebut menggunakan format ASCII text yaitu jenis file yang dapat kita baca, selanjutnya kita perlu mengetahui apa isi dari file tersebut dengan menggunakan *command* `cat`.
```bash
$ cat ./maybehere07/.file2
```

Setelah itu kita dapat melihat passwordnya yaitu `HWasnPhtq9AVKe0dmk45nxy20cvUa6EG`, ini akan kita gunakan sebagai password untuk di level selanjutnya.