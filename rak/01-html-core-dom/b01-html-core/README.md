# Buku: B01 - HTML Core

Buku ini membahas inti HTML sebagai fondasi runtime browser: bagaimana dokumen HTML diparse, dibangun menjadi DOM, dipakai untuk membangun tree render, dan menjadi pusat interaksi antara markup, skrip, styling, serta networking. Fokusnya **cara kerja browser**, bukan belajar HTML dari sisi sintaks.

## Tujuan Buku

- Menjelaskan alur kerja browser saat memproses HTML dari network ke DOM
- Memetakan komponen inti HTML runtime (parser, tree builder, DOM integration)
- Menjadi basis bagi buku DOM, CSS, dan Rendering Pipeline

## Cara Kerja (Gambaran Besar)

1. Browser menerima respon HTML dari jaringan (resource utama).
2. HTML parser memecah bytes menjadi token dan membangun DOM tree.
3. Parser berinteraksi dengan tokenizer, tree builder, dan DOM APIs.
4. Sub-resource (CSS, JS, gambar) dipicu selama parsing.
5. DOM tree dipakai oleh rendering pipeline untuk menghasilkan tampilan.

## Ruang Lingkup

- Parsing HTML dan pembentukan DOM
- Integrasi HTML dengan DOM, CSS, dan scripting
- Resource discovery (script, stylesheet, image) selama parsing
- Dampak parsing terhadap rendering dan event loop

## Aturan Bab

- Bab diambil dari buku besar/dokumen referensi terkait.
- Struktur bab mengikuti referensi, bukan ditentukan manual.
- Semua bab dari referensi dapat dimasukkan ke buku ini.
- Penamaan folder bab memakai `kebab-case` dengan awalan kode (contoh: `c01-...`).
- Catat sumber dan versi referensi di setiap bab.

## Prinsip Fleksibilitas

- Jumlah bab di buku ini **mengikuti referensi utama**, tidak dipatok.
- Bab boleh bertambah jika referensi bertambah.
- Targetnya sekomplit mungkin dan terus dikembangkan.

## Sumber Utama

- HTML Standard (WHATWG)


## File Buku

- `README.md`: ringkasan dan aturan buku
- `CHANGELOG.md`: catatan rilis dan perubahan
- `docs/`: dokumen pendukung untuk buku ini
- `c01-.../`, `c02-.../`: folder bab (sejajar dengan `docs/`)

