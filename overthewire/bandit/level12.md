# Bandit 11 → 12:

[OverTheWire Bandit Level 11 → 12](https://overthewire.org/wargames/bandit/bandit12.html)

## Deskripsi Level
*The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions.*

## Langkah-langkah
Setelah sebelumnya kita berhasil menemukan password, sekarang kita perlu masuk lagi ke server sebagai `bandit11` dengan password `dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr`.
```bash
$ ssh bandit11@bandit.labs.overthewire.org -p 2220
```

Sekarang kita sudah berhasil masuk ke server sebagai `bandit11`, dari deskripsi di atas kita tahu bahwa password dari level selanjutnya ada pada file `data.txt` dan isi file tersebut sudah di *encoded* ke ROT13. Sekarang kita perlu melihat isi file tersebut dengan menggunakan *command* `cat` serta langsung *decode* isi file tersebut dengan *command* `tr` dan opsi `'A-Za-z' 'N-ZA-Mn-za-m'` untuk urutan alfabet setelah di rotasi 13x.
```bash
$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

Setelah itu kita dapat melihat passwordnya yaitu `7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4`, ini akan kita gunakan sebagai password untuk di level selanjutnya.