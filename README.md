# klontong-licenses — Registry Lisensi Kelontong POS

Repositori ini adalah **server lisensi resmi** untuk aplikasi Kasir & Manajemen Retail **Kelontong POS**.

Aplikasi pelanggan secara berkala membaca file `registry.json` dari repositori ini
(via `raw.githubusercontent.com`) untuk memverifikasi status lisensi: aktif, kedaluwarsa,
atau dicabut.

## ⚠️ Jangan Edit File Ini Secara Manual

`registry.json` **ditandatangani digital RSA-2048** oleh developer. Perubahan sekecil
apa pun (satu karakter saja) akan membuat verifikasi tanda tangan **GAGAL** dan seluruh
aplikasi pelanggan menolak registry ini.

Untuk menambah / memperpanjang / mencabut lisensi, developer menjalankan:

```
php tools/license_builder.php issue|renew|revoke ...   # di mesin developer
php tools/license_builder.php registry                 # tandatangani ulang
git add registry.json && git commit -m "update registry" && git push
```

## Isi Registry

Hanya berisi **hash** dari license key (bukan key-nya), metadata paket, binding
perangkat/domain, dan tanda tangan. Tidak ada rahasia di repositori ini —
keamanan dijamin oleh tanda tangan digital, bukan kerahasiaan file.

