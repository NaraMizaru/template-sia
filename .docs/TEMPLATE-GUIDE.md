# Template Guide
## Panduan Mengenal dan Menjalankan SIA Template

**Untuk:** Mahasiswa Pemrograman Akuntansi  
**Project dasar:** SIA Template — Laravel 8

---

## 1. Apa itu SIA Template?

SIA Template adalah project awal Laravel yang disediakan sebagai fondasi pengerjaan project kelompok. Template memiliki struktur aplikasi, autentikasi, layout dashboard, contoh pengelolaan data, dan modul akuntansi dasar sebagai referensi.

Setiap kelompok memiliki tema aplikasi sendiri. Karena itu, template tidak harus digunakan persis sama oleh semua kelompok.

## 2. Cara Kerja Pembelajaran

1. Setiap kelompok menerima salinan repository/template.
2. Kelompok menjalankan aplikasi di komputer masing-masing.
3. Kelompok mempelajari halaman dan struktur kode.
4. Kelompok menentukan bagian yang akan dipakai, diubah, atau ditambahkan.
5. Kelompok mengembangkan aplikasi sesuai tema yang disetujui dosen/asisten dosen.

Jangan mengubah semua file sekaligus. Lakukan perubahan sedikit demi sedikit dan uji setelah setiap perubahan.

## 3. Persiapan Lingkungan

Siapkan:
- PHP dengan versi yang kompatibel dengan dependency project.
- Composer.
- MySQL atau MariaDB.
- Node.js dan npm jika asset frontend memerlukan proses build.
- Git (disarankan).
- Code editor.

**Penting:** ikuti versi PHP dan ekstensi yang tercantum di `composer.json` serta README repository. Jangan mengasumsikan semua versi PHP kompatibel dengan Laravel 8.

## 4. Cara Instalasi

Sesuaikan nama database dan versi lingkungan dengan konfigurasi lokal.

```bash
git clone <URL-REPOSITORY>
cd <NAMA-FOLDER-PROJECT>

composer install
cp .env.example .env
php artisan key:generate
```

Buat database MySQL, lalu atur bagian berikut di `.env`:

```env
DB_DATABASE=nama_database
DB_USERNAME=root
DB_PASSWORD=
```

Jalankan migration dan seeder:

```bash
php artisan migrate --seed
```

Jika project memiliki asset frontend yang perlu dibangun:

```bash
npm install
npm run dev
```

Jalankan aplikasi:

```bash
php artisan serve
```

Buka alamat lokal yang ditampilkan Artisan, biasanya `http://127.0.0.1:8000`.

Jika perintah atau script berbeda pada repository aktual, ikuti README project.

## 5. Mengenal Struktur Laravel

```text
app/
  Http/Controllers/   # Mengatur alur request
  Models/             # Representasi tabel dan relasi
database/
  migrations/         # Struktur tabel
  seeders/            # Data awal/demo
resources/views/      # Tampilan Blade
routes/web.php        # Daftar URL aplikasi
public/               # Asset publik
```

Ringkasnya:
- **Route** menentukan URL dan controller yang dipanggil.
- **Controller** memproses request dan mengambil/menyimpan data.
- **Model** berinteraksi dengan tabel database.
- **Migration** mendefinisikan struktur tabel.
- **Seeder** mengisi data awal.
- **Blade** menampilkan halaman HTML.

## 6. Bagian Aplikasi yang Perlu Dikenali

| Bagian | Tujuan |
|---|---|
| Login | Contoh autentikasi |
| Dashboard | Contoh halaman ringkasan |
| Sidebar/navbar | Contoh navigasi |
| Halaman daftar data | Contoh tampilan tabel |
| Form tambah/edit | Contoh input dan validasi |
| Database | Contoh tabel dan relasi |
| Modul akuntansi | Contoh proses bisnis akuntansi |

Nama file dan lokasi persis dapat berbeda mengikuti implementasi repository. Periksa route dan controller sebelum mengedit.

## 7. Cara Mempelajari Satu Fitur

Gunakan satu fitur CRUD sebagai contoh:
1. Buka `routes/web.php` dan cari route fitur.
2. Buka controller yang dipanggil route.
3. Buka model yang digunakan controller.
4. Periksa migration tabel.
5. Buka Blade untuk halaman daftar dan form.
6. Jalankan fitur dan amati perubahan database.

Pahami alurnya sebelum menyalin pola tersebut untuk fitur baru.

## 8. Aturan Penggunaan Template

- Simpan salinan template asli sebelum melakukan perubahan.
- Gunakan Git atau backup folder.
- Jangan menghapus migration atau tabel tanpa memahami dampaknya.
- Jangan menyimpan password asli di source code.
- Jangan mengunggah file `.env`.
- Gunakan data dummy untuk demonstrasi.
- Konsultasikan perubahan besar pada struktur akuntansi dengan dosen/asisten.

## 9. Checklist Awal Kelompok

- [ ] Project berhasil diunduh/disalin.
- [ ] Dependency berhasil dipasang.
- [ ] Database berhasil dibuat.
- [ ] Migration berhasil dijalankan.
- [ ] Seeder berhasil dijalankan.
- [ ] Aplikasi berhasil dibuka.
- [ ] Login berhasil.
- [ ] Kelompok memahami satu alur CRUD.
- [ ] Tema project kelompok sudah ditentukan.

## 10. Jika Mengalami Kendala

Sebelum meminta bantuan, siapkan:
1. Perintah yang dijalankan.
2. Pesan error lengkap.
3. Versi PHP dan Composer.
4. Langkah yang sudah dicoba.
5. Screenshot jika error berasal dari tampilan.

Jangan hanya mengirim tulisan “Laravel error”. Informasi yang lengkap mempercepat proses pencarian masalah.
