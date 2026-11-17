# MOTIONFY — Latest Safe Package

## Isi ZIP
- `public/index.html` — halaman MOTIONFY.
- `server.js` — backend Express untuk menyajikan website.
- `scraper-review.js` — catatan pemeriksaan struktur scraper yang kamu kirim; sengaja tidak menjalankan request autentikasi.
- `package.json` — dependensi dan perintah.
- `README.md` — panduan.

## Menjalankan
Pastikan Node.js sudah terpasang. Dari folder hasil ekstrak, jalankan:

```bash
npm install
npm start
```

Lalu buka `http://localhost:3000`.

Tes backend:
`http://localhost:3000/health`

Untuk melihat ringkasan scraper (tanpa menghubungi endpoint atau memproses kredensial):
```bash
node scraper-review.js
```

## Hasil pemeriksaan scraper
Kode yang dikirim menggunakan Node.js + Axios dan memanggil endpoint Netlify dengan tiga action: `send-magiclink`, `verify-account`, dan `apply-premium`.

ZIP ini tidak menjalankan bagian yang mengumpulkan atau meneruskan Magic Link (`rawLink`) maupun `idToken`, karena keduanya merupakan kredensial autentikasi. Sebelum integrasi backend, perlu dokumentasi API resmi dan bukti izin dari pemilik layanan. Gunakan API resmi yang tidak meminta pengguna menyerahkan tautan login atau token sesi.

Catatan: paket ini belum membuktikan endpoint pihak ketiga aktif dan belum menghubungkan scraper ke layanan tersebut.
