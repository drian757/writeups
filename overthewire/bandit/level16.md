# Bandit 15 → 16:

[OverTheWire Bandit Level 15 → 16](https://overthewire.org/wargames/bandit/bandit16.html)

## Deskripsi Level
*The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL/TLS encryption.*
*Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.*

## Langkah-langkah
Setelah sebelumnya kita berhasil menemukan password, sekarang kita perlu masuk lagi ke server sebagai `bandit15` dengan password `8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo`.
```bash
$ ssh bandit15@bandit.labs.overthewire.org -p 2220
```

Sekarang kita sudah berhasil masuk ke server sebagai `bandit15`, dari deskripsi di atas kita tahu bahwa password dari level selanjutnya bisa kita dapatkan dengan mengirimkan password level ini ke *localhost* port `30001` menggunakan *command* `openssl` yang berfungsi untuk membuat sertifikat, mengenkripsi file, hingga melakukan tes koneksi pada jalur yang aman (SSL/TLS), `s_client` berfungsi untuk mencoba membuka koneksi ke sebuah server yang menggunakan enkripsi, mirip seperti browser web (HTTPS) saat membuka website.
```bash
$ openssl s_client -connect localhost:30001
```

Setelah masuk ke dalam *command* di atas kita hanya perlu memberikan password saat ini untuk mendapatkan password level selanjutnya.
```bash
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
```

Setelah itu kita dapat melihat passwordnya yaitu `kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx`, ini akan kita gunakan sebagai password untuk di level selanjutnya.