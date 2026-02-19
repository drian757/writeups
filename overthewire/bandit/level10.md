# Bandit 9 → 10:

[OverTheWire Bandit Level 9 → 10](https://overthewire.org/wargames/bandit/bandit10.html)

## Deskripsi Level
*The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.*

## Langkah-langkah
Setelah sebelumnya kita berhasil menemukan password, sekarang kita perlu masuk lagi ke server sebagai `bandit9` dengan password `4CKMh1JI91bUIZZPXDqGanal4xvAg0JM`.
```bash
$ ssh bandit9@bandit.labs.overthewire.org -p 2220
```

Sekarang kita sudah berhasil masuk ke server sebagai `bandit9`, dari deskripsi di atas kita tahu bahwa password dari level selanjutnya ada pada file `data.txt` dan merupakan satu-satunya baris teks yang hanya muncul sekali. Kita dapat menggunakan kombinasi *command* yaitu `strings` yang digunakan untuk mencetak urutan karakter yang dapat dicetak dalam file serta `grep` yang digunakan untuk mencari sebuah kata, untuk menggabungkan kedua *command* kita perlu menggunakan `|` *pipe*.
```bash
$ strings data.txt | grep ==
```

Setelah itu kita dapat melihat passwordnya yaitu `FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey`, ini akan kita gunakan sebagai password untuk di level selanjutnya.