# Root Governance

Dokumen ini memuat aturan tingkat root untuk monorepo.

## Prinsip Aturan Berjenjang

Aturan hanya berlaku **di level folder tempat aturan itu berada** dan **tidak mengatur isi yang lebih dalam**.

- **Root**: hanya mengatur isi di root.
- **Rak**: aturan hanya berlaku untuk isi di rak tersebut.
- **Buku**: aturan hanya berlaku untuk isi di buku tersebut.
- Jika ada **subfolder di dalam buku**, maka subfolder itu boleh memiliki aturan sendiri untuk levelnya.

Pengecualian hanya untuk `docs/`: dokumen di `docs/` adalah penjelasan tambahan yang merujuk ke README pada setiap level.

## Struktur Root

- `README.md` sebagai pendahuluan singkat
- `docs/` untuk dokumentasi pendukung
- `rak/` sebagai kumpulan rak (domain/tema)

## Konvensi Penomoran

- **Rak**: `R01`, `R02`, `R03`, ...
- **Buku**: `B01`, `B02`, `B03`, ...
- **Bab**: `C01`, `C02`, `C03`, ...

Kode tersebut digunakan untuk mempermudah diskusi dan penamaan folder.

## Ruang Lingkup Root

- Konvensi penamaan folder di root
- Struktur folder tingkat root
- Prinsip aturan berjenjang
- Konvensi penomoran

## Status

Aktif. Detail untuk rak/buku akan ditulis di README masing-masing.

## Changelog

Changelog hanya ada di level buku. Rak dan root tidak memiliki changelog.

## Rilis & Versi Buku

- Rilis dilakukan ketika pembuat merasa isi buku sudah cukup.
- Changelog hanya dicatat di buku tersebut.
- Format versi: Rxx-Bxx-vN (contoh: R01-B01-v1, R02-B03-v2).
- Rxx diambil dari nomor rak, Bxx diambil dari nomor buku.

## Struktur Buku

Di level buku, struktur foldernya seperti ini:

- `README.md`
- `CHANGELOG.md`
- `docs/` (dokumen pendukung untuk buku ini)
- `c01-.../`, `c02-.../`, dst (bab; sejajar dengan `docs/`)

Catatan: bab tidak diletakkan di dalam `docs/`.

## Prinsip Fleksibilitas

- Jumlah rak, buku, dan bab **tidak dipatok**.
- Jumlah mengikuti buku besar/dokumen referensi yang menjadi sumber.
- Jika referensi bertambah bab, struktur ikut bertambah.
- Tujuan: sekomplit mungkin dan terus berkembang.

## Konvensi Penamaan Judul

- Judul rak dan buku memakai Title Case (contoh: Rendering Pipeline).
- Judul bab boleh Title Case atau Kalimat Normal, tetapi konsisten di dalam satu buku.
- Bahasa judul: Indonesia (boleh pakai istilah teknis Inggris jika sudah umum).

