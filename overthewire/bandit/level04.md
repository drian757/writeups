# Bandit 3 → 4:

[OverTheWire Bandit Level 3 → 4](https://overthewire.org/wargames/bandit/bandit4.html)

## Deskripsi Level
*The password for the next level is stored in a hidden file in the inhere directory.*

## Langkah-langkah
Setelah sebelumnya kita berhasil menemukan password, sekarang kita perlu masuk lagi ke server sebagai `bandit3` dengan password `MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx`.
```bash
$ ssh bandit3@bandit.labs.overthewire.org -p 2220
```

Sekarang kita sudah berhasil masuk ke server sebagai `bandit3`, sama seperti sebelumnya kita harus mencari tahu file apa saja yang ada disini dengan menggunakan *command* `ls`.
```bash
$ ls
```

Kali ini kita melihat hal yang berbeda yaitu direktori `inhere`, kita dapat berpindah dari direktori ini ke direktori tersebut dengan menggunakan *command* `cd`.
```bash
$ cd inhere/
```

Setelah masuk kedalam direktori `inhere` kita perlu mencari tahu kembali file apa saja yang ada disini dengan menggunakan *command* `ls`, dalam soal kita diberi tahu bahwa *The password for the next level is stored in a hidden file in the inhere directory.* yang menandakan file tersebut dihidden atau disembunyikan cara untuk melihat file tersembunyi kita hanya perlu menambahkan opsi `-a`.
```bash
$ ls -a
```

Disini kita dapat melihat suatu file yaitu `...Hiding-From-You`, kita dapat mengetahui apa isi dari file tersebut dengan menggunakan *command* `cat`.
```bash
$ cat ...Hiding-From-You
```

Setelah itu kita dapat melihat passwordnya yaitu `2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ`, ini akan kita gunakan sebagai password untuk di level selanjutnya.