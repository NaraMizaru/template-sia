# Product Requirements Document (PRD)
## SIA Template — Laravel 8 Accounting Management Starter

**Versi:** 1.0  
**Status:** Baseline spesifikasi  
**Target:** Template praktikum Pemrograman Akuntansi, Semester 3 Sistem Informasi Akuntansi  
**Stack:** Laravel 8, PHP, MySQL, Blade, Bootstrap 5

---

## 1. Ringkasan Produk

SIA Template adalah aplikasi web berbasis Laravel 8 yang menyediakan fondasi sistem informasi akuntansi. Template memiliki autentikasi sederhana, dashboard, pengaturan identitas aplikasi/perusahaan, pengelolaan daftar akun, pencatatan jurnal umum, serta contoh laporan akuntansi dasar.

Template digunakan sebagai project awal bersama. Setiap kelompok mahasiswa dapat mengadaptasi tema, tampilan, data, dan fitur sesuai kebutuhan project mereka. Modul akuntansi yang tersedia berfungsi sebagai contoh sekaligus fondasi; kelompok tidak diwajibkan menggunakan seluruh modul jika tema project membutuhkan alur yang berbeda.

## 2. Latar Belakang dan Masalah

Mahasiswa perlu mempelajari hubungan antara proses akuntansi dan implementasi aplikasi web. Memulai dari project kosong dapat menyita waktu untuk konfigurasi dasar, layout, autentikasi, dan struktur CRUD. Template ini menyediakan fondasi yang dapat dijalankan dan dipelajari sehingga waktu praktikum lebih banyak digunakan untuk memahami proses bisnis dan mengembangkan fitur sesuai tema kelompok.

## 3. Tujuan

1. Menyediakan satu starter project Laravel yang dapat digunakan seluruh kelompok.
2. Menunjukkan contoh penerapan Laravel MVC, migration, model, controller, Blade, validasi, dan relasi database.
3. Memberikan contoh alur pencatatan akuntansi dasar.
4. Memudahkan mahasiswa mengubah identitas dan tampilan aplikasi.
5. Memungkinkan tiap kelompok mengembangkan aplikasi dengan tema berbeda tanpa membuat fondasi dari nol.

## 4. Bukan Tujuan (Non-goals)

Versi template ini bukan software akuntansi komersial atau sistem ERP. Di luar cakupan awal:
- Multi-perusahaan dan multi-cabang.
- Multi-role dan approval bertingkat.
- Payroll, perpajakan, persediaan kompleks, manufaktur.
- Integrasi bank, payment gateway, dan layanan pihak ketiga.
- Audit trail tingkat lanjut.
- Standar pelaporan/regulasi khusus.
- Akuntansi multi-mata uang.

## 5. Pengguna dan Hak Akses

### 5.1 Admin
Pengguna tunggal untuk kebutuhan template dan demonstrasi. Admin dapat:
- Login dan logout.
- Melihat dashboard.
- Mengelola identitas aplikasi/perusahaan.
- Mengelola daftar akun.
- Mengelola jurnal dan melihat laporan contoh.

### 5.2 Mahasiswa Pengembang
Mahasiswa menerima source code dan mengembangkan salinan project untuk kelompoknya. Mahasiswa bukan role aplikasi tambahan; mereka adalah pengguna template dalam konteks praktikum.

## 6. Ruang Lingkup Fitur

### 6.1 Fitur fondasi (wajib tersedia pada template)
| Modul | Kebutuhan |
|---|---|
| Authentication | Login/logout admin sederhana |
| Dashboard | Ringkasan dan tautan ke modul |
| App/Company Settings | Nama aplikasi, nama perusahaan, alamat, logo, warna tema bila diimplementasikan |
| Navigation | Sidebar/navbar yang mudah diubah |
| Example CRUD | Minimal satu contoh CRUD lengkap |
| Database | Migration, relasi, dan seeder contoh |
| Documentation | README dan panduan praktikum |

### 6.2 Modul akuntansi contoh (tersedia, penggunaannya opsional per kelompok)
| Modul | Fungsi |
|---|---|
| Chart of Accounts (COA) | Mengelola kode, nama, tipe, dan saldo normal akun |
| Jurnal Umum | Mencatat transaksi dalam baris debit/kredit |
| Buku Besar | Mengelompokkan detail jurnal per akun |
| Neraca Saldo | Menampilkan saldo debit/kredit setiap akun |
| Laporan Laba Rugi | Menghitung pendapatan dikurangi beban |
| Laporan Perubahan Modal | Menghitung perubahan ekuitas |
| Neraca | Menampilkan aset, liabilitas, dan ekuitas |

Kelompok boleh memilih modul yang relevan, menyesuaikan struktur, atau menggantinya dengan proses bisnis lain yang tetap berkaitan dengan akuntansi. Penghapusan modul harus dilakukan setelah memahami ketergantungan data dan kode.

## 7. Kebutuhan Fungsional

### FR-01 — Autentikasi
- Admin dapat login menggunakan email dan password.
- Admin dapat logout.
- Halaman internal hanya dapat diakses setelah login.
- Kredensial contoh hanya untuk lingkungan pembelajaran dan wajib diganti sebelum distribusi final.

### FR-02 — Dashboard
- Menampilkan identitas aplikasi/perusahaan.
- Menyediakan ringkasan data yang relevan.
- Menampilkan tautan navigasi ke modul.
- Jika data belum tersedia, sistem menampilkan nilai kosong/nol secara aman.

### FR-03 — Pengaturan Identitas
- Admin dapat mengubah nama aplikasi dan nama perusahaan.
- Admin dapat mengubah alamat dan logo jika fitur upload diimplementasikan.
- Nilai pengaturan digunakan pada layout dan dokumen/laporan yang relevan.
- Warna tema dapat dikelola melalui konfigurasi sederhana atau pengaturan, sesuai implementasi.

### FR-04 — Daftar Akun
- Admin dapat melihat, menambah, mengubah, dan menghapus akun yang belum dipakai.
- Kode akun harus unik.
- Tipe akun dibatasi pada aset, liabilitas, ekuitas, pendapatan, dan beban.
- Saldo normal ditentukan berdasarkan tipe akun atau pilihan yang tervalidasi.

### FR-05 — Jurnal Umum
- Admin dapat membuat jurnal dengan tanggal, referensi, keterangan, dan minimal dua detail akun.
- Setiap detail memiliki akun serta nilai debit atau kredit.
- Satu detail tidak boleh memiliki debit dan kredit sekaligus.
- Total debit harus sama dengan total kredit.
- Jurnal disimpan secara atomik menggunakan database transaction.
- Jurnal dapat dilihat, diedit, dan dihapus sesuai aturan aplikasi.

### FR-06 — Buku Besar
- Menampilkan detail jurnal berdasarkan akun.
- Menampilkan tanggal, referensi, keterangan, debit, kredit, dan saldo berjalan.
- Filter akun dan periode tersedia jika termasuk dalam implementasi awal.

### FR-07 — Neraca Saldo
- Mengakumulasi saldo akun dari jurnal.
- Menampilkan saldo pada sisi debit atau kredit sesuai saldo normal.
- Total debit dan kredit harus sama untuk data jurnal yang valid.

### FR-08 — Laporan Keuangan
- Laba rugi dihitung dari akun pendapatan dan beban.
- Perubahan modal dihitung dari modal awal, laba/rugi, dan prive jika akun prive digunakan.
- Neraca menghitung aset, liabilitas, dan ekuitas.
- Laporan dapat difilter berdasarkan periode jika fitur periode diterapkan.

## 8. Aturan Bisnis Akuntansi

1. Jurnal harus memiliki minimal dua detail.
2. Total debit wajib sama dengan total kredit.
3. Nilai debit dan kredit tidak boleh negatif.
4. Setiap detail harus terhubung ke akun yang aktif.
5. Satu detail hanya boleh berisi debit atau kredit.
6. Akun yang telah digunakan dalam jurnal tidak boleh dihapus sembarangan.
7. Buku besar dan laporan dihitung dari data jurnal, bukan diisi manual.
8. Saldo normal aset dan beban umumnya debit; liabilitas, ekuitas, dan pendapatan umumnya kredit.
9. Persamaan dasar akuntansi adalah aset = liabilitas + ekuitas.
10. Perubahan atau penghapusan jurnal harus tercermin pada laporan karena laporan dihitung dari data sumber.

**Catatan ruang lingkup:** jurnal penyesuaian, penutupan, pembalik, dan saldo awal dapat ditambahkan sebagai pengembangan. Jangan mengklaim laporan sebagai laporan final satu siklus akuntansi lengkap sebelum fitur penyesuaian dan penutupan yang diperlukan benar-benar tersedia.

## 9. Rancangan Data Konseptual

Tabel minimum yang disarankan:

| Tabel | Fungsi |
|---|---|
| users | Akun admin (dapat menggunakan migration autentikasi Laravel) |
| company_settings | Identitas aplikasi/perusahaan |
| accounts | Daftar akun |
| journal_entries | Header jurnal |
| journal_details | Baris debit/kredit jurnal |

Relasi:
- `journal_entries` memiliki banyak `journal_details`.
- `accounts` memiliki banyak `journal_details`.
- `journal_details` dimiliki satu `journal_entry` dan satu `account`.

Kolom utama yang disarankan:
- `accounts`: `id`, `code`, `name`, `type`, `normal_balance`, timestamps.
- `journal_entries`: `id`, `date`, `reference`, `description`, timestamps.
- `journal_details`: `id`, `journal_entry_id`, `account_id`, `debit`, `credit`, timestamps.
- `company_settings`: `id`, `company_name`, `app_name`, `address`, `logo`, `primary_color`, timestamps.

Gunakan tipe decimal untuk nominal uang, bukan float. Detail skema harus diselaraskan dengan kode aktual sebelum implementasi.

## 10. Kebutuhan Non-Fungsional

- Kode mengikuti pola Laravel MVC standar.
- Gunakan Eloquent ORM dan Blade.
- Gunakan validasi Laravel pada input.
- Gunakan CSRF protection bawaan Laravel.
- Gunakan database transaction untuk menyimpan header dan detail jurnal.
- Hindari pola arsitektur berlebihan untuk kebutuhan praktikum.
- Tampilan responsif dan konsisten.
- Pesan validasi dan error mudah dipahami mahasiswa.
- Data demo tidak boleh menggunakan informasi pribadi atau keuangan nyata.

## 11. Batasan Teknis dan Prinsip Kode

- Framework: Laravel 8.
- Frontend: Blade dan Bootstrap 5.
- Database: MySQL.
- JavaScript: Vanilla JavaScript seperlunya.
- Chart: Chart.js hanya jika grafik diperlukan.
- Gunakan controller, model, migration, seeder, route, dan Blade standar.
- Tidak wajib menggunakan API, React, Inertia, Repository Pattern, Service Layer, atau package admin panel.
- Utamakan kode yang pendek, eksplisit, dan mudah dijelaskan di kelas.
- Jangan menonaktifkan pemeriksaan keamanan dependency secara permanen untuk deployment production. Jika Composer memblokir dependency Laravel 8 karena advisory, keputusan untuk melanjutkan hanya untuk lingkungan pembelajaran harus disertai pemahaman risiko dan pembatasan penggunaan.

## 12. Acceptance Criteria

Template siap dibagikan jika:
- [ ] Project dapat di-install mengikuti README.
- [ ] Migration berjalan dari database kosong.
- [ ] Seeder membuat data demo yang dapat digunakan.
- [ ] Admin dapat login dan logout.
- [ ] Dashboard dapat dibuka setelah login.
- [ ] Identitas aplikasi dapat diubah atau titik kustomisasinya terdokumentasi.
- [ ] Minimal satu CRUD contoh berjalan.
- [ ] Jika modul jurnal disertakan, validasi debit/kredit berjalan.
- [ ] Buku besar dan laporan menggunakan data jurnal.
- [ ] Tidak ada tautan navigasi utama yang rusak.
- [ ] Panduan template dan kustomisasi sesuai dengan kode aktual.

## 13. Risiko dan Mitigasi

| Risiko | Mitigasi |
|---|---|
| Tema kelompok sangat berbeda | Jadikan modul akuntansi contoh bersifat opsional dan sediakan panduan adaptasi |
| Mahasiswa mengubah kode inti hingga rusak | Ajarkan backup/branch dan tandai file inti |
| Data laporan tidak seimbang | Validasi jurnal dan siapkan data demo yang teruji |
| Perbedaan versi PHP/dependency | Cantumkan versi lingkungan yang sudah diuji pada README |
| Laravel 8 memiliki dependency usang | Batasi untuk pembelajaran lokal dan evaluasi risiko sebelum publikasi |

## 14. Deliverables

1. Source code SIA Template.
2. Migration dan seeder.
3. Data demo.
4. README instalasi.
5. Template Guide.
6. Customization Guide.
7. Project Assignment Guide.
8. Accounting Module Guide.
9. Checklist pengujian sebelum template dibagikan.

## 15. Prinsip Keberhasilan

Keberhasilan template bukan diukur dari banyaknya fitur, tetapi dari kemudahan mahasiswa:
- menjalankan project;
- memahami struktur Laravel;
- mengubah identitas aplikasi;
- memahami contoh proses akuntansi;
- mengembangkan fitur sesuai tema kelompok.
