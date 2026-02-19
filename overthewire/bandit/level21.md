# Bandit 20 → 21:

[OverTheWire Bandit Level 20 → 21](https://overthewire.org/wargames/bandit/bandit21.html)

## Deskripsi Level
*There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).*

*NOTE: Try connecting to your own network daemon to see if it works as you think*

## Langkah-langkah
Setelah sebelumnya kita berhasil menemukan password, sekarang kita perlu masuk lagi ke server sebagai `bandit20` dengan password `0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO`. 
```bash
$ ssh bandit20@bandit.labs.overthewire.org -p 2220
```

Sekarang kita sudah berhasil masuk ke server sebagai `bandit20`, sama seperti sebelum-sebelumnya kita harus mencari tahu file apa saja yang ada disini dengan menggunakan *command* `ls`.
```bash
$ ls -l
```

Sebelum kita menjalankan file tersebut kita harus membuat listener pada port tertentu. Kita menggunakan *command* `nc` untuk mendengarkan pada port 3445 dan mengirimkan password bandit20 dengan menggunakan *command* `echo`.
```bash
echo -n "0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO" | nc -l -p 3445 &
```

Setelah itu kita menjalankan file tersebut serta menghubungi port `3445` yang sudah kita buka.
```bash
$ ./suconnect 3445
```

Setelah itu kita dapat melihat passwordnya yaitu `EeoULMCra2q0dSkYj561DX7s1CpBuOBt`, ini akan kita gunakan sebagai password untuk di level selanjutnya.