# Bandit 14 → 15:

[OverTheWire Bandit Level 14 → 15](https://overthewire.org/wargames/bandit/bandit15.html)

## Deskripsi Level
*The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.*

## Langkah-langkah
Setelah sebelumnya kita berhasil menemukan password, sekarang kita perlu masuk lagi ke server sebagai `bandit14` dengan password `MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS`.
```bash
$ ssh bandit14@bandit.labs.overthewire.org -p 2220
```

Sekarang kita sudah berhasil masuk ke server sebagai `bandit14`, dari deskripsi di atas kita tahu bahwa password dari level selanjutnya bisa kita dapatkan dengan mengirimkan password level ini ke *localhost* port `30000` menggunakan *command* `nc` yang berfungsi untuk membaca dan menulis data melalui koneksi jaringan menggunakan protokol TCP atau UDP.
```bash
$ cat /etc/bandit_pass/bandit14 | nc localhost 30000
```

Setelah itu kita dapat melihat passwordnya yaitu `8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo`, ini akan kita gunakan sebagai password untuk di level selanjutnya.