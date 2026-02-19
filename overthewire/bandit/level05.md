# Bandit 4 → 5:

[OverTheWire Bandit Level 4 → 5](https://overthewire.org/wargames/bandit/bandit5.html)

## Deskripsi Level
*The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.*

## Langkah-langkah
Setelah sebelumnya kita berhasil menemukan password, sekarang kita perlu masuk lagi ke server sebagai `bandit4` dengan password `2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ`.
```bash
$ ssh bandit4@bandit.labs.overthewire.org -p 2220
```

Sekarang kita sudah berhasil masuk ke server sebagai `bandit4`, sama seperti sebelumnya kita harus mencari tahu file apa saja yang ada disini dengan menggunakan *command* `ls`.
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

Disini kita dapat melihat beberapa file, untuk kita mengetahui passwordnya kita dapat menggunakan cara termudah yaitu dengan *command* `file` yang berguna untuk mengidentifikasi jenis atau tipe data dari sebuah file.
```bash
$ file ./*
```

Kita sudah menemukan file `-file07` yang mungkin berisi password karena file tersebut menggunakan format ASCII text yaitu jenis file yang dapat kita baca, selanjutnya kita perlu mengetahui apa isi dari file tersebut dengan menggunakan *command* `cat`.
```bash
$ cat ./-file07
```

Setelah itu kita dapat melihat passwordnya yaitu `4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw`, ini akan kita gunakan sebagai password untuk di level selanjutnya.