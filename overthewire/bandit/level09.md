# Bandit 8 → 9:

[OverTheWire Bandit Level 8 → 9](https://overthewire.org/wargames/bandit/bandit9.html)

## Deskripsi Level
*The password for the next level is stored in the file data.txt and is the only line of text that occurs only once*

## Langkah-langkah
Setelah sebelumnya kita berhasil menemukan password, sekarang kita perlu masuk lagi ke server sebagai `bandit8` dengan password `dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc`.
```bash
$ ssh bandit8@bandit.labs.overthewire.org -p 2220
```

Sekarang kita sudah berhasil masuk ke server sebagai `bandit8`, dari deskripsi di atas kita tahu bahwa password dari level selanjutnya ada pada file `data.txt` dan merupakan satu-satunya baris teks yang hanya muncul sekali. Kita dapat menggunakan kombinasi *command* yaitu `sort` yang digunakan untuk mengurutkan baris file teks serta `uniq` yang digunakan untuk melaporkan atau menghilangkan baris yang berulang, untuk menggabungkan kedua *command* kita perlu menggunakan `|` *pipe*.
```bash
$ sort data.txt | uniq -u
```

Setelah itu kita dapat melihat passwordnya yaitu `4CKMh1JI91bUIZZPXDqGanal4xvAg0JM`, ini akan kita gunakan sebagai password untuk di level selanjutnya.