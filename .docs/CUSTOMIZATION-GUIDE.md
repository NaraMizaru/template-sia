# Customization Guide
## Panduan Mengubah dan Mengembangkan SIA Template

**Untuk:** Mahasiswa Pemrograman Akuntansi

Panduan ini menjelaskan urutan aman untuk mengubah template menjadi aplikasi sesuai tema kelompok. Nama file di bawah merupakan contoh pola Laravel; cocokkan dengan struktur project yang dibagikan.

---

## 1. Sebelum Mengubah

1. Duplikasi project atau buat branch Git baru.
2. Pastikan aplikasi awal berjalan.
3. Catat halaman dan fitur yang sudah tersedia.
4. Tentukan tema dan kebutuhan pengguna.
5. Ubah satu bagian, lalu uji.

Jangan mulai dengan menghapus modul yang belum dipahami.

## 2. Mengubah Nama Aplikasi

Buka file `.env` dan ubah:

```env
APP_NAME="SIA Kelompok 1"
```

Pastikan konfigurasi tidak tersimpan dalam cache lama:

```bash
php artisan config:clear
```

Jika nama aplikasi ditulis langsung di Blade, ubah juga bagian layout terkait atau arahkan agar membaca konfigurasi aplikasi.

## 3. Mengubah Logo

1. Siapkan logo kelompok dalam format PNG, JPG, atau SVG yang aman.
2. Simpan file pada folder asset publik yang digunakan project, misalnya `public/images/`.
3. Cari pemanggilan logo pada layout Blade.
4. Ganti path gambar.
5. Periksa tampilan pada sidebar, navbar, dan halaman login.

Contoh:

```html
<img src="{{ asset('images/logo-kelompok.png') }}" alt="Logo">
```

Jangan menggunakan path file lokal komputer seperti `/Users/nama/...`.

## 4. Mengubah Warna dan Tampilan

Cari file CSS utama atau konfigurasi Bootstrap yang digunakan project. Ubah warna secara konsisten:
- warna utama;
- warna sidebar;
- warna tombol;
- warna status;
- warna latar.

Jika menggunakan CSS biasa, contoh:

```css
:root {
    --primary-color: #4f46e5;
}

.btn-primary {
    background-color: var(--primary-color);
}
```

Pastikan warna teks tetap terbaca dan tampilan responsif.

## 5. Mengubah Identitas Perusahaan

Jika tersedia halaman pengaturan, gunakan halaman tersebut. Jika belum tersedia, mahasiswa dapat menambahkan data identitas perusahaan melalui konfigurasi atau tabel pengaturan.

Identitas yang dapat ditampilkan:
- nama perusahaan/organisasi;
- alamat;
- logo;
- nama aplikasi;
- periode laporan.

Jangan membuat tabel baru jika informasi tersebut cukup disimpan dalam konfigurasi sederhana.

## 6. Mengubah Menu Navigasi

1. Buka layout/sidebar Blade.
2. Identifikasi menu yang sudah ada.
3. Ganti label menu sesuai tema.
4. Ubah route tujuan agar mengarah ke halaman yang benar.
5. Hapus menu yang tidak digunakan hanya setelah memastikan tidak ada ketergantungan.

Contoh tema:
- Kas kecil: Kas Masuk, Kas Keluar, Laporan Kas.
- UMKM: Transaksi, Kategori, Buku Kas, Laba Rugi.
- Pembayaran sekolah: Data Siswa, Tagihan, Pembayaran, Tunggakan.
- Akuntansi jasa: Daftar Akun, Jurnal Umum, Buku Besar, Laporan.

## 7. Menambah Fitur CRUD

Gunakan pola CRUD yang sudah ada di template sebagai referensi.

Urutan umum:
1. Buat migration.
2. Buat model.
3. Buat controller.
4. Tambahkan route.
5. Buat Blade untuk daftar, tambah, dan edit.
6. Tambahkan validasi.
7. Uji tambah, lihat, ubah, dan hapus.

Contoh perintah:

```bash
php artisan make:model Customer -m
php artisan make:controller CustomerController
```

Contoh migration sederhana:

```php
Schema::create('customers', function (Blueprint $table) {
    $table->id();
    $table->string('name');
    $table->string('phone')->nullable();
    $table->timestamps();
});
```

Contoh route resource:

```php
Route::resource('customers', CustomerController::class);
```

Gunakan nama tabel, kolom, dan validasi yang sesuai kebutuhan tema kelompok.

## 8. Mengubah Database

Sebelum menambah tabel, buat daftar data yang perlu disimpan. Untuk setiap tabel tentukan:
- nama tabel;
- tujuan;
- kolom;
- tipe data;
- primary key;
- foreign key;
- relasi.

Jangan mengubah migration yang sudah pernah dijalankan pada database bersama tanpa memahami konsekuensinya. Untuk perubahan baru, buat migration tambahan.

Perintah:

```bash
php artisan make:migration create_customers_table
php artisan migrate
```

Gunakan `decimal` untuk nominal uang, bukan `float`.

## 9. Menggunakan Modul Akuntansi

Modul COA, jurnal, buku besar, dan laporan merupakan modul contoh. Kelompok dapat:
- menggunakan modul yang relevan;
- mengganti nama akun atau kategori;
- menyesuaikan form transaksi;
- menambah laporan yang dibutuhkan;
- tidak menggunakan modul yang tidak sesuai tema.

Jangan mengubah rumus debit/kredit atau persamaan akuntansi tanpa memahami dampaknya. Lihat `ACCOUNTING-MODULE-GUIDE.md`.

## 10. Contoh Pemetaan Tema

| Tema | Bagian yang dapat dipakai | Pengembangan |
|---|---|---|
| Kas kecil | Login, dashboard, layout, CRUD | Kas masuk/keluar dan saldo |
| Keuangan UMKM | Login, dashboard, COA, jurnal | Kategori transaksi dan laporan |
| Pembayaran sekolah | Login, dashboard, CRUD | Tagihan, pembayaran, piutang |
| Akuntansi toko | Login, dashboard, COA | Penjualan, pembelian, persediaan sederhana |

Pemetaan ini merupakan contoh awal, bukan batasan tema.

## 11. Checklist Setelah Kustomisasi

- [ ] Nama aplikasi sudah sesuai.
- [ ] Logo tampil dengan benar.
- [ ] Warna dan layout konsisten.
- [ ] Menu mengarah ke halaman yang benar.
- [ ] Form memiliki validasi.
- [ ] CRUD berjalan.
- [ ] Relasi database benar.
- [ ] Data lama tidak rusak.
- [ ] Laporan sesuai dengan proses bisnis.
- [ ] Aplikasi diuji dari awal sampai akhir.
