# Ruang Nilai SEMPIA · Portal Hasil TKA

## Isi paket
- `index.html` — portal publik.
- `assets/hero-literasi.png` — ilustrasi besar Literasi (gambar referensi yang Anda kirim).
- `assets/hero-numerasi.png` — ilustrasi besar Numerasi.
- `assets/icon-literasi.png` — ikon kartu Literasi.
- `assets/icon-numerasi.png` — ikon kartu Numerasi.
- `template-data-tka-satu-sheet.xlsx` — template spreadsheet satu sheet.
- `template-data-tka-satu-sheet.csv` — template CSV.

## Mengganti gambar
Semua gambar menggunakan format PNG agar mudah diganti.
1. Buka folder `assets`.
2. Ganti gambar yang ingin diubah dengan gambar baru.
3. Pertahankan nama file yang sama:
   - `hero-literasi.png`
   - `hero-numerasi.png`
   - `icon-literasi.png`
   - `icon-numerasi.png`
4. Commit folder `assets` yang sudah diperbarui ke GitHub.

Gunakan gambar hero dengan rasio mendekati 382:306 dan ikon dengan rasio persegi agar tampil proporsional. Tidak perlu mengedit HTML selama nama file tetap sama.

## Tampilan mobile
Pada layar ponsel, ilustrasi besar di bagian header otomatis berada di tengah. Kartu pilihan Literasi dan Numerasi tetap berdampingan dan tabel hasil berubah menjadi kartu peserta. Bagian indikator langkah dan judul pengantar pilihan ujian sudah dihapus.

## Menghubungkan spreadsheet
1. Gunakan satu sheet dengan kolom: `Jenis Ujian`, `Tanggal Pelaksanaan`, `Nama Lengkap`, `Sisa Waktu`, `Nilai`.
2. Publikasikan sheet sebagai CSV melalui File → Share → Publish to web.
3. Tempel URL CSV pada konstanta `DATA_SOURCE` di `index.html`.
4. Website memfilter baris `Literasi` dan `Numerasi` berdasarkan kolom `Jenis Ujian`.
5. Data diperbarui otomatis setiap 10 detik saat halaman aktif.

## Deploy
Upload `index.html`, folder `assets`, dan file template ke repository GitHub. Pertahankan struktur folder.

## Privasi
CSV yang dipublikasikan dapat dibaca publik. Jangan masukkan NISN, alamat, nomor telepon, atau data sensitif lainnya.
