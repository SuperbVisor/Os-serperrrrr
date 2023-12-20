# FINAL PROJECT OS SERVER DAN SYSTEM ADMIN

# Langkah-langkah Instalasi Ubuntu Server dan Nginx untuk Web Server

>[!NOTE]
>Bahan yang saya gunakan di Web server saya yaitu:
>
> ![ubuntu](https://github.com/SuperbVisor/Os-serperrrrr/assets/144216485/fb574446-e32d-4ce0-9803-93ad9d5f2501) ![nginx](https://github.com/SuperbVisor/Os-serperrrrr/assets/144216485/25b0b5b0-4a8f-41b3-b2bf-35438fc68bbc)  ![winswcp](https://github.com/SuperbVisor/Os-serperrrrr/assets/144216485/9c14bc51-cebd-4d1f-bb3f-91c4c6d8e556)  ![vscode]()









## Instalasi Ubuntu Server

1. **Unduh ISO Ubuntu Server:** Kunjungi situs resmi Ubuntu dan unduh ISO Ubuntu Server terbaru.

2. **Buat Media Bootable:** Gunakan perangkat lunak seperti Rufus (Windows) atau balenaEtcher (Mac/Linux) untuk membuat media bootable menggunakan ISO yang telah diunduh.

3. **Boot dari Media:** Boot komputer atau server dari media yang telah dibuat. Pilih opsi untuk menginstal Ubuntu Server.

4. **Ikuti Wizard Instalasi:** Ikuti langkah-langkah instalasi yang terdapat pada layar. Pilih konfigurasi jaringan, partisi disk, dan buat pengguna serta kata sandi untuk akun administrator.

5. **Perbarui Sistem:** Setelah instalasi selesai, lakukan pembaruan sistem dengan perintah:
```
#sudo apt update
#sudo apt upgrade
```
   

## Instalasi dan Konfigurasi Nginx

1. **Instalasi Nginx:** Gunakan package manager untuk menginstal Nginx.
```
#sudo apt install nginx
```

2. **Mulai Layanan Nginx:** Setelah instalasi selesai, mulai layanan Nginx dan aktifkan agar berjalan saat boot.
```
#sudo systemctl start nginx
#sudo systemctl enable nginx
```

3. **Konfigurasi Firewall:** Jika menggunakan firewall (misalnya UFW), izinkan lalu lintas HTTP dan HTTPS.
```
#sudo ufw allow 'Nginx Full'
#sudo ufw enable
```

4. **Cek Status Nginx:** Pastikan Nginx berjalan tanpa masalah.
```
#sudo systemctl status Nginx
```
5. **Uji Web Server:** Buka browser dan akses alamat IP server atau nama domain jika sudah dikonfigurasi. Jika semuanya berjalan dengan baik, akan muncul halaman selamat datang Nginx.

6. **Konfigurasi Situs:** Untuk menambahkan situs web, buat konfigurasi di direktori `/etc/nginx/sites-available/`. Contoh konfigurasi:
```
server {
listen 80;
server_name Webegar.com www.Webegar.com;
```
```
   location / {
       root /var/www/html;
       browny.html;
   }

```

7. **Aktifkan Situs:** Buat symlink dari konfigurasi yang dibuat ke direktori `sites-enabled`.
```
#sudo ln -s /etc/nginx/sites-available/example.com /etc/nginx/sites-enabled/
```

8. **Restart Nginx:** Setelah mengkonfigurasi situs baru, restart Nginx untuk menerapkan perubahan.
```
#sudo systemctl restart nginx
```
