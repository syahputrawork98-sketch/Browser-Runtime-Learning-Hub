# Aturan Pengambilan Bab dari Referensi

Bab di dalam repositori ini **diambil dari buku besar atau dokumen referensi resmi** yang relevan, lalu dipindahkan/dipecah sesuai pengelompokan rak dan buku.

## Prinsip Utama

- Struktur bab **mengikuti referensi** (tidak dipaksa oleh struktur buatan).
- Semua bab dari referensi **boleh dimasukkan**.
- Repositori **terus berkembang** mengikuti update referensi.

## Penomoran Bab

- Kode bab: `C01`, `C02`, `C03`, ...
- Nama folder bab memakai `kebab-case` dengan awalan kode (contoh: `c01-event-loop`).

## Lokasi Bab

Folder bab berada di root folder buku (sejajar dengan `docs/`) dengan pola `c01-...`, `c02-...`, dst.

## Metadata Wajib per Bab

Setiap bab harus mencatat:

- Sumber referensi (judul dokumen/buku besar)
- Versi atau tanggal rilis referensi
- Lokasi bab di referensi (misalnya bab/section)

## Contoh Metadata

```text
Sumber: HTML Living Standard
Versi/Tanggal: 2026-03-01
Lokasi: 8.1.2 Event loops
```

## Isi Minimum Bab

Setiap bab minimal berisi:
- Ringkasan
- Tujuan
- Alur utama (langkah-langkah)
- Istilah kunci
- Sumber referensi (dengan versi/tanggal)

## Analogi (Opsional)

Setiap bab boleh memiliki analogi untuk membantu pemahaman. Analogi tidak wajib, dan bisa berbeda per bab:

- `## Analogi Singkat`: 1-3 kalimat yang langsung mengunci intuisi.
- `## Analogi Panjang`: 1-3 paragraf untuk gambaran yang lebih naratif.

Aturan:

- Satu bab boleh punya keduanya, atau hanya salah satu, sesuai kebutuhan.
- Analogi tidak boleh mengubah fakta teknis; setelah analogi tetap jelaskan alur/istilah/batasan dengan bahasa yang presisi.

## Struktur Folder Bab

Di dalam folder bab (contoh: `c01-.../`):

- `README.md` (isi utama bab)
- `docs/` (penjelasan pendukung untuk `README.md`)
- `assets/` (gambar, SVG)
- `examples/` (contoh kode/skenario)

## Aturan SVG

Setiap bab boleh memiliki SVG (mis. `assets/overview.svg`) untuk menjelaskan alur/komponen. Aturannya:

- **SVG dibuat terakhir**: kerjakan `README.md` + `docs/` + `examples/` terlebih dulu sampai alur dan istilahnya stabil. Setelah itu baru bikin SVG, supaya diagram mengikuti isi (bukan sebaliknya).
- SVG disesuaikan dengan kebutuhan bab; isi diagram harus relevan dan tidak sekadar copy-paste template bab lain.
- Konsistensi gaya visual (font/box/warna) boleh sama agar repo terasa satu keluarga, tetapi struktur dan isi diagram relatif berbeda antar bab.

