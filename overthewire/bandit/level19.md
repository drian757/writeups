# Bandit 18 → 19:

[OverTheWire Bandit Level 18 → 19](https://overthewire.org/wargames/bandit/bandit19.html)

## Deskripsi Level
*The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.*

## Langkah-langkah
Setelah sebelumnya kita berhasil menemukan password, sekarang kita perlu masuk lagi ke server sebagai `bandit18` dengan password `x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO`. Namun kali ini sedikit berbeda kita tidak bisa masuk ke server karena file `.bashrc` di modifikasi yang membuat kita tidak dapat masuk melalui ssh, namun kita mengetahui bahwa password untuk level selanjutnya berada pada file `readme` di *home* direktori. Maka dari itu kita dapat langsung melihat isi file tersebut dengan menggunakan *command* `cat`.
```bash
$ ssh bandit18@bandit.labs.overthewire.org -p 2220 "cat readme"
```

Setelah itu kita dapat melihat passwordnya yaitu `cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8`, ini akan kita gunakan sebagai password untuk di level selanjutnya.