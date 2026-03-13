# Bab: C01 - HTML Core

## Ringkasan

Bab ini menjelaskan alur inti ketika browser menerima HTML, mem-parsing dokumen, membangun DOM, dan memicu pemuatan resource lain. Ini adalah fondasi dari seluruh runtime browser.

## Tujuan

- Memahami alur HTML dari network hingga DOM
- Menjelaskan peran parser, tokenizer, dan tree builder
- Menghubungkan proses parsing dengan rendering dan skrip

## Alur Utama

1. Respon HTML diterima dari jaringan sebagai bytes
2. Bytes di-decode menjadi karakter (encoding detection)
3. Tokenizer memecah karakter menjadi token HTML
4. Tree builder membangun DOM tree dari token
5. Parser mengeksekusi aturan khusus (script, style, template)
6. Browser memicu loading sub-resource (CSS, JS, images)
7. DOM tree dipakai untuk proses rendering

## Istilah Kunci

- HTML parser
- Tokenizer
- Tree builder
- DOM tree
- Resource discovery
- Parsing blocking script

## Batasan dan Perilaku Penting

- Script tertentu dapat menghentikan parsing sampai selesai dieksekusi
- CSS mempengaruhi render dan bisa memblokir paint
- Kesalahan markup dipulihkan oleh parser (error recovery)

## Contoh Skenario

Pengguna membuka halaman. Browser menerima HTML, mulai membangun DOM, menemukan tag `<link rel="stylesheet">` sehingga memulai download CSS, menemukan `<script>` yang harus dijalankan sebelum lanjut parsing, lalu melanjutkan parsing setelah script selesai.

## Sumber Referensi

- Sumber: HTML Standard (WHATWG)
- Versi/Tanggal: (isi versi atau tanggal rilis referensi)
- Lokasi: (isi lokasi bab di referensi)
