# KuliahKu — Manajemen Perkuliahan

Aplikasi web siap hosting untuk:
- Login dan daftar akun dengan Supabase Auth
- Dashboard agenda
- Jadwal perkuliahan
- Jadwal praktikum
- Tugas dan deadline
- Tambah, lihat, edit, dan hapus data
- Data setiap akun terpisah dan diamankan dengan Row Level Security (RLS)
- Tampilan responsif untuk laptop dan HP

## 1. Buat project Supabase
Buka https://supabase.com/ lalu buat project baru.

## 2. Buat database
Masuk ke **SQL Editor**, buka file `schema.sql`, lalu jalankan seluruh isinya.

## 3. Ambil URL dan key
Di Supabase buka **Project Settings > API**.
Salin:
- Project URL
- Publishable/anon key

Masukkan ke `config.js`:

```js
window.SUPABASE_URL = "https://xxxx.supabase.co";
window.SUPABASE_ANON_KEY = "eyJ...";
```

Jangan masukkan `service_role` key ke website.

## 4. Jalankan
Karena aplikasi ini memakai file HTML/CSS/JS biasa, tidak perlu npm/build.

Bisa:
- Netlify: drag & drop folder ini ke Netlify
- GitHub Pages: upload semua file ke repository lalu aktifkan Pages
- Hosting cPanel: upload semua file ke `public_html`

## 5. Pengaturan email Supabase
Untuk testing, Anda dapat mengatur Authentication > Providers > Email.
Jika "Confirm email" aktif, pengguna perlu melakukan konfirmasi email setelah daftar.

## Struktur
- `index.html` — halaman aplikasi
- `style.css` — tampilan
- `app.js` — fungsi login dan CRUD
- `config.js` — konfigurasi Supabase
- `schema.sql` — tabel + RLS
- `README.md` — panduan hosting

Catatan: akun dan data tidak disimpan di browser. Akun memakai Supabase Auth dan data memakai PostgreSQL Supabase.
