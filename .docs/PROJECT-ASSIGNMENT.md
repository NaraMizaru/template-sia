# Project Assignment Guide
## Pengembangan Aplikasi Akuntansi Berbasis Laravel 8

**Mata Kuliah:** Pemrograman Akuntansi  
**Peserta:** Mahasiswa Semester 3 Sistem Informasi Akuntansi  
**Metode:** Project kelompok  
**Starter project:** SIA Template

---

## 1. Tujuan Tugas

Setiap kelompok mengembangkan aplikasi berbasis web menggunakan SIA Template. Tema setiap kelompok boleh berbeda, tetapi harus memiliki hubungan yang jelas dengan proses pencatatan, pengelolaan, atau pelaporan keuangan/akuntansi.

Mahasiswa diharapkan mampu:
1. Mengidentifikasi masalah dan kebutuhan pengguna.
2. Menjelaskan proses bisnis aplikasi.
3. Mengadaptasi template Laravel.
4. Mengelola data menggunakan database.
5. Membuat fitur sesuai tema.
6. Menjelaskan hubungan fitur dengan konsep akuntansi.

## 2. Ketentuan Umum

- Project dikerjakan per kelompok sesuai pembagian dosen.
- Setiap kelompok menentukan satu tema aplikasi.
- Tema harus disetujui dosen/asisten dosen.
- Semua kelompok menggunakan SIA Template sebagai titik awal.
- Tampilan dan fitur boleh berbeda antar kelompok.
- Modul akuntansi yang tersedia di template boleh digunakan, disesuaikan, atau tidak digunakan jika tidak relevan dengan tema.
- Setiap kelompok wajib memahami kode yang dimodifikasi.
- Dilarang hanya mengganti nama/logo tanpa mengembangkan fungsi sesuai tema.

## 3. Contoh Tema

Tema berikut hanya inspirasi:
1. Sistem Informasi Kas Kecil.
2. Sistem Informasi Keuangan UMKM.
3. Sistem Akuntansi Perusahaan Jasa.
4. Sistem Pembayaran Sekolah.
5. Sistem Keuangan Organisasi/Kegiatan.
6. Sistem Penjualan dan Pembelian Toko.
7. Sistem Pencatatan Pendapatan dan Pengeluaran.
8. Sistem Pengelolaan Tagihan dan Piutang.

Kelompok boleh mengusulkan tema lain selama ruang lingkup akuntansinya dapat dijelaskan.

## 4. Tahap Pengerjaan

### Tahap 1 — Penentuan Tema
Kelompok menentukan:
- nama aplikasi;
- objek atau jenis usaha/organisasi;
- calon pengguna;
- masalah yang ingin diselesaikan;
- proses akuntansi yang terlibat.

### Tahap 2 — Analisis Kebutuhan
Kelompok membuat daftar:
- kebutuhan pengguna;
- fitur utama;
- data yang disimpan;
- laporan yang dihasilkan;
- bagian template yang akan dipakai atau diubah.

### Tahap 3 — Adaptasi Template
Kelompok melakukan:
- perubahan nama dan identitas;
- perubahan logo dan tampilan;
- penyesuaian menu;
- penambahan tabel dan relasi;
- pengembangan fitur sesuai tema.

### Tahap 4 — Pengujian
Kelompok menguji:
- login dan navigasi;
- tambah, lihat, ubah, hapus data;
- validasi input;
- perhitungan transaksi;
- laporan;
- skenario penggunaan dari awal sampai akhir.

### Tahap 5 — Demonstrasi
Kelompok mendemonstrasikan masalah, solusi, alur aplikasi, dan contoh data.

## 5. Ketentuan Fitur

Setiap aplikasi minimal memiliki:
1. Dashboard atau halaman ringkasan.
2. Pengelolaan minimal satu jenis data utama.
3. Fitur pencatatan transaksi atau aktivitas keuangan.
4. Penyimpanan data menggunakan MySQL.
5. Minimal satu laporan/ringkasan yang relevan dengan tema.
6. Validasi input.
7. Identitas aplikasi yang sudah dikustomisasi.

Fitur spesifik ditentukan berdasarkan tema dan disetujui dosen/asisten. Tidak semua kelompok harus memiliki jurnal umum, buku besar, atau neraca jika proses bisnis aplikasinya tidak membutuhkan fitur tersebut.

## 6. Dokumen Perencanaan Kelompok

Sebelum coding lebih jauh, setiap kelompok menyiapkan ringkasan satu sampai dua halaman yang berisi:

| Bagian | Isi |
|---|---|
| Nama aplikasi | Nama project kelompok |
| Latar belakang | Masalah yang ingin diselesaikan |
| Tujuan | Hasil yang ingin dicapai |
| Target pengguna | Siapa yang memakai aplikasi |
| Proses bisnis | Alur kerja utama |
| Fitur utama | Daftar fitur |
| Data | Data yang perlu disimpan |
| Laporan | Output keuangan/akuntansi |
| Adaptasi template | Bagian yang digunakan dan diubah |

## 7. Contoh Analisis Tema

**Tema:** Sistem Informasi Kas Kecil

Masalah: pencatatan pengeluaran operasional masih dilakukan secara manual.

Pengguna: admin keuangan.

Fitur:
- kategori pengeluaran;
- pencatatan kas masuk;
- pencatatan kas keluar;
- saldo kas;
- laporan pengeluaran berdasarkan periode.

Data:
- kategori;
- transaksi kas;
- pengguna.

Output:
- total kas masuk;
- total kas keluar;
- saldo;
- laporan transaksi.

Bagian template yang digunakan:
- login;
- dashboard;
- layout;
- contoh CRUD;
- koneksi database.

Bagian yang dikembangkan:
- kategori kas;
- transaksi kas masuk/keluar;
- perhitungan saldo;
- laporan kas.

## 8. Hasil Akhir yang Dikumpulkan

Setiap kelompok menyiapkan:
1. Source code project.
2. Database migration dan seeder atau dump database sesuai arahan dosen.
3. README cara instalasi.
4. Ringkasan kebutuhan dan fitur.
5. Screenshot aplikasi.
6. Data uji.
7. Demonstrasi aplikasi.

Format dan tenggat pengumpulan mengikuti arahan dosen pengampu.

## 9. Checklist Penilaian Mandiri

- [ ] Tema berkaitan dengan akuntansi/keuangan.
- [ ] Masalah dan target pengguna jelas.
- [ ] Fitur sesuai kebutuhan tema.
- [ ] Aplikasi menggunakan SIA Template sebagai dasar.
- [ ] Identitas aplikasi sudah disesuaikan.
- [ ] Database menyimpan data dengan benar.
- [ ] CRUD atau proses utama berjalan.
- [ ] Perhitungan keuangan dapat dijelaskan.
- [ ] Laporan sesuai data transaksi.
- [ ] Kelompok mampu menjelaskan kode yang dibuat.

## 10. Prinsip Penilaian yang Disarankan

Penilaian dapat mempertimbangkan:
- relevansi tema dan pemahaman proses bisnis;
- kesesuaian fitur dengan kebutuhan;
- penerapan Laravel dan database;
- ketepatan logika akuntansi;
- kualitas tampilan dan kemudahan penggunaan;
- pengujian dan kemampuan presentasi.

Bobot penilaian akhir ditetapkan oleh dosen pengampu.
