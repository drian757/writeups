# Bandit 0 → 1:

[OverTheWire Bandit Level 0 → 1](https://overthewire.org/wargames/bandit/bandit1.html)

## Deskripsi Level
*The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.*

## Langkah-langkah
Pada level sebelumnya kita sudah berhasil masuk ke server. Hal pertama yang bisa kita lakukan adalah melihat file-file yang ada dengan menggunakan *command* `ls`.
```bash
$ ls
```

Disini kita dapat melihat suatu file yaitu `readme`, kita dapat mengetahui apa isi dari file tersebut dengan menggunakan *command* `cat`.
```bash
$ cat readme
```

Setelah itu kita dapat melihat passwordnya yaitu `ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If`, ini akan kita gunakan sebagai password untuk di level selanjutnya.