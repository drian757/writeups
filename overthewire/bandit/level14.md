# Bandit 13 → 14:

[OverTheWire Bandit Level 13 → 14](https://overthewire.org/wargames/bandit/bandit14.html)

## Deskripsi Level
*The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Look at the commands that logged you into previous bandit levels, and find out how to use the key for this level.*

## Langkah-langkah
Setelah sebelumnya kita berhasil menemukan password, sekarang kita perlu masuk lagi ke server sebagai `bandit13` dengan password `FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn`.
```bash
$ ssh bandit13@bandit.labs.overthewire.org -p 2220
```

Sekarang kita sudah berhasil masuk ke server sebagai `bandit13`, dari deskripsi di atas kita tahu bahwa password dari level selanjutnya hanya dapat diketahui oleh *user* `bandit14` namun kita sebagai *user* `bandit13` memiliki `sshkey.private` yang dapat digunakan untuk masuk ke *user* `bandit14` tanpa menggunakan password.
```bash
$ ssh -i sshkey.private bandit14@localhost
```

Namun kita dapat masalah yaitu `bandit14@localhost: Permission denied (publickey).`, disini kita dapat menggunakan cara yang sedikit berbeda yaitu dengan menyalin isi dari `sshkey.private` ke laptop atau komputer kita sendiri. Caranya kita perlu melihat terlebih dahulu isi dari file `sshkey.private` dengan *command* `cat`.
```bash
$ cat sshkey.private 
-----BEGIN RSA PRIVATE KEY-----
MIIEpAIBAAKCAQEAxkkOE83W2cOT7IWhFc9aPaaQmQDdgzuXCv+ppZHa++buSkN+
gg0tcr7Fw8NLGa5+Uzec2rEg0WmeevB13AIoYp0MZyETq46t+jk9puNwZwIt9XgB
ZufGtZEwWbFWw/vVLNwOXBe4UWStGRWzgPpEeSv5Tb1VjLZIBdGphTIK22Amz6Zb
ThMsiMnyJafEwJ/T8PQO3myS91vUHEuoOMAzoUID4kN0MEZ3+XahyK0HJVq68KsV
ObefXG1vvA3GAJ29kxJaqvRfgYnqZryWN7w3CHjNU4c/2Jkp+n8L0SnxaNA+WYA7
jiPyTF0is8uzMlYQ4l1Lzh/8/MpvhCQF8r22dwIDAQABAoIBAQC6dWBjhyEOzjeA
J3j/RWmap9M5zfJ/wb2bfidNpwbB8rsJ4sZIDZQ7XuIh4LfygoAQSS+bBw3RXvzE
pvJt3SmU8hIDuLsCjL1VnBY5pY7Bju8g8aR/3FyjyNAqx/TLfzlLYfOu7i9Jet67
xAh0tONG/u8FB5I3LAI2Vp6OviwvdWeC4nOxCthldpuPKNLA8rmMMVRTKQ+7T2VS
nXmwYckKUcUgzoVSpiNZaS0zUDypdpy2+tRH3MQa5kqN1YKjvF8RC47woOYCktsD
o3FFpGNFec9Taa3Msy+DfQQhHKZFKIL3bJDONtmrVvtYK40/yeU4aZ/HA2DQzwhe
ol1AfiEhAoGBAOnVjosBkm7sblK+n4IEwPxs8sOmhPnTDUy5WGrpSCrXOmsVIBUf
laL3ZGLx3xCIwtCnEucB9DvN2HZkupc/h6hTKUYLqXuyLD8njTrbRhLgbC9QrKrS
M1F2fSTxVqPtZDlDMwjNR04xHA/fKh8bXXyTMqOHNJTHHNhbh3McdURjAoGBANkU
1hqfnw7+aXncJ9bjysr1ZWbqOE5Nd8AFgfwaKuGTTVX2NsUQnCMWdOp+wFak40JH
PKWkJNdBG+ex0H9JNQsTK3X5PBMAS8AfX0GrKeuwKWA6erytVTqjOfLYcdp5+z9s
8DtVCxDuVsM+i4X8UqIGOlvGbtKEVokHPFXP1q/dAoGAcHg5YX7WEehCgCYTzpO+
xysX8ScM2qS6xuZ3MqUWAxUWkh7NGZvhe0sGy9iOdANzwKw7mUUFViaCMR/t54W1
GC83sOs3D7n5Mj8x3NdO8xFit7dT9a245TvaoYQ7KgmqpSg/ScKCw4c3eiLava+J
3btnJeSIU+8ZXq9XjPRpKwUCgYA7z6LiOQKxNeXH3qHXcnHok855maUj5fJNpPbY
iDkyZ8ySF8GlcFsky8Yw6fWCqfG3zDrohJ5l9JmEsBh7SadkwsZhvecQcS9t4vby
9/8X4jS0P8ibfcKS4nBP+dT81kkkg5Z5MohXBORA7VWx+ACohcDEkprsQ+w32xeD
qT1EvQKBgQDKm8ws2ByvSUVs9GjTilCajFqLJ0eVYzRPaY6f++Gv/UVfAPV4c+S0
kAWpXbv5tbkkzbS0eaLPTKgLzavXtQoTtKwrjpolHKIHUz6Wu+n4abfAIRFubOdN
/+aLoRQ0yBDRbdXMsZN/jvY44eM+xRLdRVyMmdPtP8belRi2E2aEzA==
-----END RSA PRIVATE KEY-----
```

Sekarang pada terminal kita sendiri, kita buat file key baru dengan menggunakan *command* `nano` yang berfungsi untuk buat file baru serta langsung membuat isi dari file tersebut. Dalam file tersebut kita menyimpan isi file tadi ke file ini.
```bash
$ nano kunci.txt
```

Setelah itu kita perlu mengubah permission dari file ini dengan menggunakan *command* `chmod` menjadi `600` yang berfungsi untuk mengatur hak akses file kunci agar hanya dapat dibaca dan ditulis oleh pemiliknya.
```bash
$ chmod 600 kunci.txt
```

Selanjutnya kita dapat langsung masuk ke server sebagai `bandit14` dengan menggunakan key tersebut.
```bash
$ ssh -i kunci.txt bandit14@bandit.labs.overthewire.org -p 2220
```

Dan sekarang kita sudah berhasil masuk ke dalam server sebagai `bandit14`, lalu kita hanya perlu mencari tahu password sebenarnya dengan melihat isi dari file `cat /etc/bandit_pass/bandit14` seperti yang ada di deskripsi level dengan *command* `cat`.
```bash
$ cat /etc/bandit_pass/bandit14
```

Setelah itu kita dapat melihat passwordnya yaitu `MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS`, ini akan kita gunakan sebagai password untuk di level selanjutnya.