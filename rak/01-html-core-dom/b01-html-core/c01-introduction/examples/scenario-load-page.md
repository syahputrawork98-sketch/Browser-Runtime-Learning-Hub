# Skenario: User Membuka Halaman

Tujuan skenario ini adalah memberi "anchor mental" saat membaca bab-bab berikutnya.

## Alur Ringkas

1. User memasukkan URL atau klik link.
2. Browser melakukan navigasi dan memulai request dokumen utama (HTML).
3. Browser menerima respons (bytes), menentukan encoding, lalu memulai parsing HTML.
4. Selama parsing, browser membangun DOM dan menemukan sub-resource (CSS/JS/images).
5. Browser menjalankan aturan terkait script (blocking/async/defer) dan melanjutkan parsing.
6. Rendering pipeline menggunakan DOM + CSS untuk menampilkan halaman.

## Catatan Untuk Bab Lain

- Detail parsing masuk ke `C13 - The HTML Syntax`.
- Detail loading lifecycle masuk ke `C07 - Loading Web Pages`.
- Detail rendering masuk ke `C15 - Rendering`.
