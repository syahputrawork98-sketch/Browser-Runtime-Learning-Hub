# Browser Runtime Knowledge Base

Repositori ini adalah basis pengetahuan terstruktur untuk memahami bagaimana JavaScript berjalan di browser.

## Pola Navigasi Level

Setiap level memakai pola yang sama:

1. `README.md` untuk ringkasan level tersebut.
2. `docs/` untuk aturan dan penjelasan detail level tersebut.

Level yang digunakan:

1. Root
2. Rak (domain)
3. Buku (topik)

Aturan penting:

- Root hanya mengatur root.
- Rak hanya mengatur rak.
- Buku hanya mengatur buku.

## Root

Mulai dari `README.md` ini untuk orientasi.
Detail aturan root ada di [`docs/root-governance.md`](./docs/root-governance.md).

## Struktur

```text
Browser Runtime Knowledge Base/
|-- README.md
|-- docs/
|   `-- root-governance.md
|-- 01-browser-architecture/
|-- 02-javascript-engine/
|-- 03-memory-system/
|-- 04-web-apis/
|-- 05-execution-model/
|-- 06-scheduling-runtime-interaction/
`-- 07-rendering-system/
```

## Sistem Log Buku

- Patokan identitas dan versi buku ada di `docs/book-log.md` milik tiap buku.
- Perubahan dikerjakan dulu di buku, dicatat di `Perubahan Kerja`, lalu dirilis sebagai versi saat sudah dianggap cukup.

## Daftar Rak

1. [Browser Architecture](./01-browser-architecture/README.md)
2. [Javascript Engine](./02-javascript-engine/README.md)
3. [Memory System](./03-memory-system/README.md)
4. [Web Apis](./04-web-apis/README.md)
5. [Execution Model](./05-execution-model/README.md)
6. [Scheduling Runtime Interaction](./06-scheduling-runtime-interaction/README.md)
7. [Rendering System](./07-rendering-system/README.md)

## Catatan Penulisan Buku

Tidak ada template wajib lintas buku.
Setiap buku boleh memiliki struktur penjelasan berbeda sesuai kebutuhan topik.
Yang wajib adalah referensi yang jelas dan log versi per buku.
