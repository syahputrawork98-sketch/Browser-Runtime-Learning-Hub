# Browser Runtime Knowledge Base

Repositori ini adalah basis pengetahuan terstruktur untuk memahami bagaimana JavaScript berjalan di dalam browser, dari fondasi arsitektur sampai dampaknya ke rendering dan performa runtime.

## Tujuan

Repositori ini dibangun untuk:

1. Membantu membangun model mental runtime browser secara utuh.
2. Menyusun pengetahuan secara terstruktur agar mudah dipelajari bertahap.
3. Menjaga dokumentasi tetap bisa berkembang seiring perubahan browser platform.

Fokus utama repositori ini adalah hubungan antarsistem, bukan sekadar daftar API.

## Prinsip Struktur

Pengetahuan dipisah berdasarkan level:

1. Root
2. Rak (domain)
3. Buku (topik)

Setiap level memiliki pola yang sama:

1. `README.md` untuk orientasi cepat.
2. `docs/` untuk aturan dan detail level tersebut.

Aturan batas level:

- Root hanya mengatur root.
- Rak hanya mengatur rak.
- Buku hanya mengatur buku.

## Struktur Repositori

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

## Daftar Rak

1. [Browser Architecture](./01-browser-architecture/README.md)
2. [Javascript Engine](./02-javascript-engine/README.md)
3. [Memory System](./03-memory-system/README.md)
4. [Web Apis](./04-web-apis/README.md)
5. [Execution Model](./05-execution-model/README.md)
6. [Scheduling Runtime Interaction](./06-scheduling-runtime-interaction/README.md)
7. [Rendering System](./07-rendering-system/README.md)

## Cara Navigasi

Urutan baca yang direkomendasikan:

1. Baca `README.md` root untuk konteks global.
2. Masuk ke `README.md` rak untuk memilih buku.
3. Baca `README.md` buku untuk materi utama.
4. Buka `docs/` jika butuh aturan detail level tersebut.

Dokumen aturan root ada di [`docs/root-governance.md`](./docs/root-governance.md).

## Sistem Log Buku (Patokan Resmi)

Patokan identitas dan versi buku ditetapkan hanya melalui `docs/book-log.md` pada masing-masing buku.

Setiap `book-log.md` minimal memuat:

1. Identitas buku (termasuk kode buku).
2. `Latest version`.
3. `Perubahan Kerja (Belum Rilis)`.
4. `Riwayat Versi`.

## Alur Update Konten Buku

Alur kerja yang dipakai:

1. Ubah materi di `README.md` buku.
2. Catat progres perubahan di `Perubahan Kerja (Belum Rilis)` pada `docs/book-log.md`.
3. Saat perubahan dianggap cukup, buat entri versi baru di `Riwayat Versi`.
4. Perbarui `Latest version` di log buku.

Format versi mengikuti `major.minor.patch` (contoh `v1.2.0`).

## Panduan Penulisan

Aturan dasar penulisan konten:

1. Tidak ada template wajib lintas buku.
2. Struktur isi setiap buku boleh berbeda sesuai karakter topik.
3. Gunakan referensi yang jelas dan dapat dilacak.
4. Bedakan antara konsep, mekanisme, dan implikasi praktis.
5. Hindari duplikasi isi lintas buku; gunakan rujukan silang jika perlu.

## Kontribusi

Jika ingin menambah atau mengubah materi:

1. Tentukan level perubahan: root, rak, atau buku.
2. Edit hanya level yang menjadi kewenangan perubahan.
3. Jika perubahan menyentuh buku, wajib update `docs/book-log.md` buku tersebut.
4. Pastikan link antar dokumen tetap valid.

## Ruang Lingkup

Ruang lingkup utama repositori:

1. Arsitektur browser dan komponen runtime.
2. Cara JavaScript engine memproses dan mengeksekusi kode.
3. Memory system dan implikasi performa.
4. Web APIs yang relevan dengan model eksekusi runtime.
5. Event loop, queue, scheduling, dan rendering interaction.

Repositori ini tidak ditujukan menjadi daftar lengkap semua Web APIs.

## Status Proyek

Repositori ini adalah dokumentasi hidup (living knowledge base).
Setiap buku dapat dikembangkan bertahap sesuai kebutuhan pembelajaran dan prioritas pengisian materi.
