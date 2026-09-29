# PKKM Online Madrasah v2

Aplikasi multi-madrasah/multi-pengawas untuk PKKM Kepala Madrasah. Front-end dapat di-host di GitHub Pages; Supabase menangani Auth, PostgreSQL, dan Storage.

## Modul
Dashboard; Data Madrasah; Pengawas & Penugasan; Komponen/Indikator; Upload Bukti Fisik; Verifikasi; Penilaian; Rekap/Laporan.

## Instalasi
1. Buat project Supabase.
2. Jalankan `schema.sql` di SQL Editor.
3. Buat Storage bucket `bukti-pkkm`.
4. Isi `config.js` dengan Project URL dan anon public key.
5. Buat akun pada Supabase Auth, lalu masukkan record `profiles` dengan role `admin`, `pengawas`, atau `madrasah`.
6. Untuk pengawas, buat record pada tabel `pengawas`; untuk madrasah, isi `user_id` pada tabel `madrasah` agar akses terikat akun.
7. Upload seluruh file ke repository GitHub, aktifkan Settings > Pages > Deploy from branch.

## Catatan keamanan
Jangan menaruh `service_role` key di GitHub. Hanya gunakan anon public key dan RLS. Untuk produksi, ubah policy Storage sesuai struktur folder madrasah dan gunakan signed URL bila bukti bersifat privat.

## Skala
Struktur database mendukung banyak madrasah, banyak pengawas, penugasan per Tahun Ajaran, indikator yang dapat ditambah Admin, verifikasi bukti, penilaian berbobot, dan laporan.
