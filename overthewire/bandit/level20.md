# Bandit 19 → 20:

[OverTheWire Bandit Level 19 → 20](https://overthewire.org/wargames/bandit/bandit20.html)

## Deskripsi Level
*To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.*

## Langkah-langkah
Setelah sebelumnya kita berhasil menemukan password, sekarang kita perlu masuk lagi ke server sebagai `bandit19` dengan password `cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8`. 
```bash
$ ssh bandit19@bandit.labs.overthewire.org -p 2220
```

Sekarang kita sudah berhasil masuk ke server sebagai `bandit19`, sama seperti sebelum-sebelumnya kita harus mencari tahu file apa saja yang ada disini dengan menggunakan *command* `ls`.
```bash
$ ls -l
```

Dapat kita lihat file yang ada hanya satu yaitu `bandit20-do` yang merupakan file *SetUID*, yaitu siapapun yang menjalankan file ini, sistem akan menganggapnya dijalankan oleh pemilik file tersebut (bandit20).
```bash
$ ./bandit20-do cat /etc/bandit_pass/bandit20
```

Setelah itu kita dapat melihat passwordnya yaitu `0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO`, ini akan kita gunakan sebagai password untuk di level selanjutnya.