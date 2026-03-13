# Skenario: Lifecycle Dokumen (Ringkas)

Tujuan: menghubungkan struktur dokumen (DOM) dengan status loading dan efeknya ke perilaku browser.

## Alur

1. Browser mulai navigasi dan membuat dokumen baru untuk halaman tujuan.
2. HTML mulai diparse dan DOM tree tumbuh (node ditambah/diubah).
3. Sub-resource ditemukan dan dimuat (CSS/JS/images) selama parsing.
4. Saat kondisi tertentu terpenuhi, dokumen masuk fase yang lebih \"siap\" (mis. interaktif).
5. Setelah semua yang relevan selesai, dokumen dianggap selesai dimuat (phase final).

## Catatan

- Detail parsing ada di `C13 - The HTML Syntax`.
- Detail loading ada di `C07 - Loading Web Pages`.
- Detail rendering ada di `C15 - Rendering`.
