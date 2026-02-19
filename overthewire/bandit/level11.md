# Bandit 10 → 11:

[OverTheWire Bandit Level 10 → 11](https://overthewire.org/wargames/bandit/bandit11.html)

## Deskripsi Level
*The password for the next level is stored in the file data.txt, which contains base64 encoded data.*

## Langkah-langkah
Setelah sebelumnya kita berhasil menemukan password, sekarang kita perlu masuk lagi ke server sebagai `bandit10` dengan password `FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey`.
```bash
$ ssh bandit10@bandit.labs.overthewire.org -p 2220
```

Sekarang kita sudah berhasil masuk ke server sebagai `bandit10`, dari deskripsi di atas kita tahu bahwa password dari level selanjutnya ada pada file `data.txt` dan isi file tersebut sudah di *encoded* ke base64. Sekarang kita perlu melihat isi file tersebut dengan menggunakan *command* `cat` serta langsung decode isi file tersebut dengan *command* `base64` dan opsi `-d` untuk decode.
```bash
$ cat data.txt | base64 -d
```

Setelah itu kita dapat melihat passwordnya yaitu `dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr`, ini akan kita gunakan sebagai password untuk di level selanjutnya.