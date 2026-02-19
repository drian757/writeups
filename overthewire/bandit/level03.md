# Bandit 2 → 3:

[OverTheWire Bandit Level 2 → 3](https://overthewire.org/wargames/bandit/bandit3.html)

## Deskripsi Level
*The password for the next level is stored in a file called --spaces in this filename-- located in the home directory*

## Langkah-langkah
Setelah sebelumnya kita berhasil menemukan password, sekarang kita perlu masuk lagi ke server sebagai `bandit2` dengan password `263JGJPfgU6LtdEvgfWU1XP5yac29mFx`.
```bash
$ ssh bandit2@bandit.labs.overthewire.org -p 2220
```

Sekarang kita sudah berhasil masuk ke server sebagai `bandit2`, sama seperti sebelumnya kita harus mencari tahu file apa saja yang ada disini dengan menggunakan *command* `ls`.
```bash
$ ls
```

Disini kita dapat melihat suatu file yaitu `--spaces in this filename--`, kita dapat mengetahui apa isi dari file tersebut dengan menggunakan *command* `cat` sama seperti sebelumnya `-` akan dianggap sebagai opsi perintah dan bukan sebagai file dan karena ini terdapat space, sistem akan membacanya sebagai beberapa file yang berbeda. Maka dari itu kita harus menggunakan `./` yang berfungsi untuk menandakan direktori saat ini serta menggunakan `\` di setiap akhir kata yang berguna sebagai penghubung setiap kata dan di anggap sebagai 1 file.
```bash
$ cat ./--spaces\ in\ this\ filename--
```

Setelah itu kita dapat melihat passwordnya yaitu `MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx`, ini akan kita gunakan sebagai password untuk di level selanjutnya.