# Bandit 7 → 8:

[OverTheWire Bandit Level 7 → 8](https://overthewire.org/wargames/bandit/bandit8.html)

## Deskripsi Level
*The password for the next level is stored in the file data.txt next to the word millionth*

## Langkah-langkah
Setelah sebelumnya kita berhasil menemukan password, sekarang kita perlu masuk lagi ke server sebagai `bandit7` dengan password `morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj`.
```bash
$ ssh bandit7@bandit.labs.overthewire.org -p 2220
```

Sekarang kita sudah berhasil masuk ke server sebagai `bandit7`, dari deskripsi di atas kita tahu bahwa password dari level selanjutnya ada pada file `data.txt` dan tepat berada setelah kata `millionth`. Kita dapat menggunakan kombinasi *command* yaitu `cat` yang digunakan untuk mencari isi file serta `grep` yang digunakan untuk mencari sebuah kata, untuk menggabungkan kedua *command* kita perlu menggunakan `|` *pipe*.
```bash
$ cat data.txt | grep millionth
```

Setelah itu kita dapat melihat passwordnya yaitu `dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc`, ini akan kita gunakan sebagai password untuk di level selanjutnya.