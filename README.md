# Ruang Nilai SEMPIA · Portal Hasil TKA

Website statis untuk GitHub Pages. Desain responsif putih dan gradasi biru, dua menu ujian, ilustrasi SVG yang berubah sesuai menu, pencarian, statistik, dan pengurutan hasil.

## File
- `index.html` — portal publik.
- `template-spreadsheet-hasil-tka.xlsx` — template sumber data dengan sheet Panduan, Literasi, Numerasi.

## Alur data (admin)
1. Isi template Excel.
2. Upload ke Google Drive, lalu buka sebagai Google Sheets.
3. Pastikan spreadsheet boleh dibaca publik jika hasil memang akan ditampilkan ke umum.
4. Di Google Sheets, buka **File → Share → Publish to web**.
5. Pilih tab **Literasi**, pilih format **Comma-separated values (.csv)**, lalu Publish. Salin URL CSV yang diberikan.
6. Ulangi untuk tab **Numerasi**.
7. Buka `index.html`, cari `const DATA_SOURCES` di bagian JavaScript, lalu tempel URL CSV pada:
   - `literasi`
   - `numerasi`
8. Commit `index.html` dan template ke repository GitHub. Pengaturan URL cukup dilakukan satu kali.
9. Setelah itu admin hanya memperbarui spreadsheet. Pengunjung dapat menekan tombol **Perbarui** untuk mengambil data terbaru.

## Format kolom
Setiap tab harus memiliki header persis:
- `Nama Lengkap`
- `Sisa Waktu`
- `Nilai`
- `Tanggal Pelaksanaan`

Tanggal pelaksanaan diisi pada setiap baris peserta dalam tab masing-masing. Semua peserta pada satu tab sebaiknya menggunakan tanggal yang sama.

## Deploy ke GitHub Pages
1. Buat repository GitHub.
2. Upload `index.html` dan `template-spreadsheet-hasil-tka.xlsx`.
3. Buka Settings → Pages.
4. Pilih Deploy from a branch, branch `main`, folder `/ (root)`, lalu Save.

## Catatan
- Website tidak menyediakan panel admin atau upload spreadsheet publik.
- Data CSV yang dipublikasikan bisa dibaca publik. Jangan masukkan NISN, alamat, nomor telepon, atau data pribadi sensitif.
- Bila URL CSV belum ditempel di `DATA_SOURCES`, halaman akan menampilkan status bahwa data sedang disiapkan.
- Website menggunakan Google Fonts dari CDN; bila tidak tersedia, font sistem akan digunakan.
