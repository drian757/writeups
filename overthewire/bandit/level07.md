# Bandit 6 → 7:

[OverTheWire Bandit Level 6 → 7](https://overthewire.org/wargames/bandit/bandit7.html)

## Deskripsi Level
*The password for the next level is stored somewhere on the server and has all of the following properties:*
    *owned by user `bandit7`*
    *owned by group `bandit6`*
    *33 bytes in size*

## Langkah-langkah
Setelah sebelumnya kita berhasil menemukan password, sekarang kita perlu masuk lagi ke server sebagai `bandit6` dengan password `HWasnPhtq9AVKe0dmk45nxy20cvUa6EG`.
```bash
$ ssh bandit6@bandit.labs.overthewire.org -p 2220
```

Sekarang kita sudah berhasil masuk ke server sebagai `bandit6`, kali ini sedikit berbeda yaitu mencari file di user `bandit7` dan group `bandit6` dengan menggunakan *command* `find`.
```bash
$ find / -type f -size 33c -user bandit7 -group bandit6
```
-`-type f`: Hanya menentukan file
-`-size 33c`: Membatasi hasil pada file yang berukuran tepat 33 byte,
-`-user bandit7`: Memastikan file tersebut dimiliki oleh pengguna yang benar
-`-group bandit6`: Memastikan file tersebut dimiliki oleh grup yang benar

Dari *command* di atas akan memperlihatkan banyak sekali file, kita hanya perlu mencari file yang aksesnya tidak di tolak yaitu `/var/lib/dpkg/info/bandit7.password`. Setelah itu kita dapat langsung melihat isi file tersebut dengan *command* `cat`.
```bash
$ cat /var/lib/dpkg/info/bandit7.password
```

Setelah itu kita dapat melihat passwordnya yaitu `morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj`, ini akan kita gunakan sebagai password untuk di level selanjutnya.