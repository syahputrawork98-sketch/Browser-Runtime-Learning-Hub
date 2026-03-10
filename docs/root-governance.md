# Root Governance

Dokumen ini mengatur aturan level root saja.

## Wewenang Root

- Menentukan tujuan dan batas ruang lingkup repositori.
- Menentukan konvensi struktur direktori lintas rak.
- Menentukan kebijakan sistem log versi lintas repositori.

## Batasan Root

- Root tidak mengatur isi detail domain di dalam rak.
- Root tidak mengatur gaya penulisan spesifik tiap buku.
- Root tidak mengatur urutan penjelasan internal sebuah buku.

## Konvensi Struktur

Setiap level mengikuti pola:

1. `README.md` untuk orientasi cepat level tersebut.
2. `docs/` untuk aturan dan penjelasan detail level tersebut.

## Aturan Lintas Level

- Root hanya mengatur root.
- Rak hanya mengatur rak.
- Buku hanya mengatur buku.
- Aturan dari level di atas tidak boleh memaksa format isi detail level di bawah.

## Patokan Identitas dan Versi Buku

- Satu-satunya patokan identitas buku adalah `docs/book-log.md` pada buku tersebut.
- Kode buku, versi aktif, perubahan kerja, dan riwayat versi disimpan di file log buku.

## Standar Log Versi Buku

Setiap buku wajib memiliki `docs/book-log.md`.

Isi minimum log:

1. identitas buku (kode + judul)
2. versi aktif (latest stable)
3. `Perubahan Kerja (Belum Rilis)`
4. `Riwayat Versi`

Format versi:

- gunakan `major.minor.patch` (contoh `v1.2.0`)
- perubahan yang masih dikerjakan ditulis dulu di `Perubahan Kerja`
- saat perubahan dianggap cukup, pindahkan ringkasannya ke entri versi baru di `Riwayat Versi`
