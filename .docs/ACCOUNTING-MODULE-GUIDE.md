# Accounting Module Guide
## Panduan Memahami Modul Akuntansi pada SIA Template

**Untuk:** Mahasiswa dan pengembang template

Dokumen ini menjelaskan konsep modul akuntansi contoh yang dapat digunakan atau diadaptasi kelompok. Modul ini bukan kewajiban untuk semua tema.

---

## 1. Gambaran Siklus Akuntansi Dasar

Alur contoh:

1. Menyiapkan daftar akun.
2. Mencatat transaksi ke jurnal umum.
3. Mem-posting detail jurnal ke buku besar.
4. Menyusun neraca saldo.
5. Menyusun laporan keuangan.

Jurnal penyesuaian dan penutupan dapat menjadi pengembangan berikutnya. Pastikan ruang lingkup laporan dinyatakan dengan jelas.

## 2. Chart of Accounts (COA)

COA adalah daftar akun yang digunakan untuk mengelompokkan transaksi.

Kategori umum:
- Aset.
- Liabilitas/kewajiban.
- Ekuitas/modal.
- Pendapatan.
- Beban.

Contoh akun:
| Kode | Nama | Tipe | Saldo Normal |
|---|---|---|---|
| 101 | Kas | Aset | Debit |
| 102 | Piutang Usaha | Aset | Debit |
| 201 | Utang Usaha | Liabilitas | Kredit |
| 301 | Modal Pemilik | Ekuitas | Kredit |
| 401 | Pendapatan Jasa | Pendapatan | Kredit |
| 501 | Beban Gaji | Beban | Debit |

Kode dan daftar akun dapat disesuaikan dengan studi kasus.

## 3. Jurnal Umum

Jurnal mencatat dampak transaksi terhadap akun.

Contoh: pemilik menyetorkan modal tunai Rp5.000.000.

| Akun | Debit | Kredit |
|---|---:|---:|
| Kas | 5.000.000 | 0 |
| Modal Pemilik | 0 | 5.000.000 |
| Total | 5.000.000 | 5.000.000 |

Validasi minimum:
- Setiap jurnal memiliki minimal dua detail.
- Total debit sama dengan total kredit.
- Nilai tidak negatif.
- Satu detail hanya memiliki debit atau kredit.
- Akun yang dipilih tersedia dan aktif.

Saat menyimpan header dan detail jurnal, gunakan database transaction agar tidak ada jurnal setengah tersimpan.

## 4. Saldo Normal dan Saldo Akun

Saldo normal:
- Aset: debit.
- Beban: debit.
- Liabilitas: kredit.
- Ekuitas: kredit.
- Pendapatan: kredit.

Untuk tampilan saldo bersih:
- Akun bersaldo normal debit: total debit dikurangi total kredit.
- Akun bersaldo normal kredit: total kredit dikurangi total debit.

Jika hasilnya negatif, tampilkan saldo pada sisi berlawanan atau beri penanganan yang konsisten dan terdokumentasi.

## 5. Buku Besar

Buku besar mengelompokkan seluruh detail jurnal berdasarkan akun.

Kolom:
- tanggal;
- nomor referensi;
- keterangan;
- debit;
- kredit;
- saldo berjalan.

Saldo berjalan dihitung berurutan berdasarkan tanggal dan urutan transaksi yang konsisten. Buku besar tidak boleh memiliki input transaksi terpisah dari jurnal jika desain sistem menggunakan jurnal sebagai sumber data utama.

## 6. Neraca Saldo

Neraca saldo merangkum saldo setiap akun setelah posting.

Total debit harus sama dengan total kredit jika semua jurnal valid dan saldo awal dimasukkan secara seimbang.

Neraca saldo bukan pengganti laporan keuangan. Ia merupakan ringkasan saldo akun untuk membantu pemeriksaan sebelum penyusunan laporan.

## 7. Laporan Keuangan Dasar

### 7.1 Laporan Laba Rugi

Laba bersih = total pendapatan - total beban.

Hanya akun pendapatan dan beban pada periode yang dipilih yang dihitung.

### 7.2 Laporan Perubahan Modal

Modal akhir = modal awal + investasi tambahan + laba bersih - prive.

Jika tidak ada transaksi tambahan atau prive, komponen tersebut bernilai nol.

### 7.3 Neraca

Aset = Liabilitas + Ekuitas.

Ekuitas pada neraca harus memperhitungkan hasil periode berjalan dan komponen ekuitas lain sesuai ruang lingkup aplikasi. Jangan menjumlahkan modal awal saja jika laba/rugi periode belum dimasukkan.

## 8. Contoh Transaksi Uji

Gunakan transaksi sederhana berikut untuk menguji konsep:

1. Pemilik menyetor modal tunai Rp5.000.000.
2. Membeli perlengkapan tunai Rp500.000.
3. Menerima pendapatan jasa tunai Rp2.000.000.
4. Membayar beban listrik Rp200.000.
5. Membayar beban gaji Rp700.000.

Dampak ringkas:
- Kas akhir: Rp5.600.000.
- Perlengkapan: Rp500.000.
- Pendapatan jasa: Rp2.000.000.
- Total beban: Rp900.000.
- Laba bersih: Rp1.100.000.
- Total aset: Rp6.100.000.
- Ekuitas akhir: Rp6.100.000.
- Liabilitas: Rp0.

Dengan asumsi tidak ada transaksi lain, neraca seimbang.

## 9. Pengujian yang Wajib Dilakukan

- Jurnal debit/kredit seimbang dapat disimpan.
- Jurnal tidak seimbang ditolak.
- Detail dengan debit dan kredit sekaligus ditolak.
- Jurnal yang diedit memperbarui saldo dan laporan.
- Jurnal yang dihapus tidak lagi muncul di buku besar.
- Filter periode tidak mencampur transaksi di luar periode.
- Data uji menghasilkan laporan yang seimbang.

## 10. Batasan dan Catatan

- Contoh ini berfokus pada perusahaan jasa sederhana.
- Belum mencakup seluruh siklus akuntansi.
- Belum mencakup penyesuaian penyusutan, beban dibayar di muka, pendapatan diterima di muka, dan penutupan kecuali dikembangkan.
- Untuk aplikasi dengan kebutuhan berbeda, kelompok harus menganalisis proses bisnisnya sendiri.
- Konsultasikan perlakuan akuntansi yang digunakan dengan dosen pengampu.
