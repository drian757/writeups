# Bandit 1 → 2:

[OverTheWire Bandit Level 1 → 2](https://overthewire.org/wargames/bandit/bandit2.html)

## Deskripsi Level
*The password for the next level is stored in a file called - located in the home directory*

## Langkah-langkah
Setelah sebelumnya kita berhasil menemukan password, sekarang kita perlu masuk lagi ke server sebagai `bandit1` dengan password `ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If`.
```bash
$ ssh bandit1@bandit.labs.overthewire.org -p 2220
```

Sekarang kita sudah berhasil masuk ke server sebagai `bandit1`, sama seperti sebelumnya kita harus mencari tahu file apa saja yang ada disini dengan menggunakan *command* `ls`.
```bash
$ ls
```

Disini kita dapat melihat suatu file yaitu `-`, kita dapat mengetahui apa isi dari file tersebut dengan menggunakan *command* `cat` akan tetapi `-` akan dianggap sebagai opsi perintah dan bukan sebagai file. Maka dari itu kita harus menggunakan `./` yang berfungsi untuk menandakan direktori saat ini.
```bash
$ cat ./-
```

Setelah itu kita dapat melihat passwordnya yaitu `263JGJPfgU6LtdEvgfWU1XP5yac29mFx`, ini akan kita gunakan sebagai password untuk di level selanjutnya.