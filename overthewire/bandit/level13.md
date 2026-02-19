# Bandit 12 → 13:

[OverTheWire Bandit Level 12 → 13](https://overthewire.org/wargames/bandit/bandit13.html)

## Deskripsi Level
*The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!).*

## Langkah-langkah
Setelah sebelumnya kita berhasil menemukan password, sekarang kita perlu masuk lagi ke server sebagai `bandit12` dengan password `7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4`.
```bash
$ ssh bandit12@bandit.labs.overthewire.org -p 2220
```

Sekarang kita sudah berhasil masuk ke server sebagai `bandit12`, dari deskripsi di atas kita tahu bahwa file `data.txt` berisi hexdump dari file yang sudah di compress berulang kali. Seperti pada deskripsi juga kita harus membuat direktori di `/tmp` dengan *menggunakan *command* `mktemp -d`.
```bash
$ mktemp -d
```

Kemudian kita pindah direktori ke direktori yang sudah berhasil kita buat.
```bash
$ cd /tmp/tmp.Xgz9BBLy4Y/
```

Setelah masuk ke direktori `/tmp.Xgz9BBLy4Y/` kita *copy* file `data.txt` dari direktori home ke direktori saat ini.
```bash
$ cp /home/bandit12/data.txt /tmp/tmp.Xgz9BBLy4Y/
```

Karena file tersebut tampaknya dalam format hex dump, kita menggunakan perintah `xxd -r` untuk mengonversinya kembali ke biner.
```bash
$ xxd -r data.txt > data.bin
```

Sekarang kita cari tahu tipe file tersebut dengan menggunakan *command* `file`.
```bash
$ file data.bin
```

Setelah dicari tahu, ternyata tipe filenya `gzip` jadi kita rename file tersebut dengan *command* `mv` menjadi `.gz` serta kita *unzip* file tersebut dengan *command* `gunzip` karena format filenya `gzip`.
```bash
$ mv data.bin data.gz
$ gunzip data.gz
$ file data
```

Setelah dicari tahu lagi, ternyata tipe filenya `bzip2` jadi kita rename file tersebut dengan *command* `mv` menjadi `.bz2` serta kita *unzip* file tersebut dengan *command* `bunzip2` karena format filenya `bzip2`.
```bash
$ mv data data.bz2
$ bunzip2 data.bz2
$ file data
```

Lanjut lagi, ternyata tipe filenya `gzip` jadi kita rename file tersebut dengan *command* `mv` menjadi `.gz` serta kita *unzip* file tersebut dengan *command* `gunzip` karena format filenya `gzip`.
```bash
$ mv data data.gz
$ gunzip data.gz
$ file data
```

Selanjutnya, ternyata tipe filenya `.tar` jadi kita rename file tersebut dengan *command* `mv` menjadi `.tar` serta kita *unzip* file tersebut dengan *command* `tar -xvf` karena format filenya `.tar`.
```bash
$ mv data data.tar
$ tar -xvf data.tar
$ file data5
```

Kali ini sedikit berbeda, ternyata tipe filenya `.tar` dan nama filenya sudah menjadi `data5` jadi kita rename file tersebut dengan *command* `mv` menjadi `.tar` serta kita *unzip* file tersebut dengan *command* `tar -xvf` karena format filenya `.tar`.
```bash
$ mv data5.bin data5.tar
$ tar -xvf data5.tar
$ file data6
```

Kali ini berbeda lagi, ternyata tipe filenya `bzip2` dan nama filenya sudah menjadi `data6` jadi kita rename file tersebut dengan *command* `mv` menjadi `.bz2` serta kita *unzip* file tersebut dengan *command* `bunzip2` karena format filenya `bzip2`.
```bash
$ mv data6.bin data6.bz2
$ bunzip2 data6.bz2
$ file data6
```

Selanjutnya, ternyata tipe filenya `.tar` jadi kita rename file tersebut dengan *command* `mv` menjadi `.tar` serta kita *unzip* file tersebut dengan *command* `tar -xvf` karena format filenya `.tar`.
```bash
$ mv data6 data6.tar
$ tar -xvf data6.tar
$ file data8.bin
```

Sekarang, ternyata tipe filenya `gzip` jadi kita rename file tersebut dengan *command* `mv` menjadi `.gz` serta kita *unzip* file tersebut dengan *command* `gunzip` karena format filenya `gzip`.
```bash
$ mv data8.bin data8.gz
$ gunzip data8.gz
$ file data8
```

Akhirnya, tipe file kali ini berbeda yaitu ASCII text dan sekarang kita hanya perlu melihat apa isi dari file tersebut dengan *command* `cat`.
```bash
$ cat data8
```

Setelah itu kita dapat melihat passwordnya yaitu `FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn`, ini akan kita gunakan sebagai password untuk di level selanjutnya.