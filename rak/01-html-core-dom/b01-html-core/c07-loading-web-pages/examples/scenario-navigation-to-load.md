# Skenario: Navigasi Sampai Halaman Siap

Tujuan: memberi alur mental end-to-end dari navigasi sampai dokumen dianggap siap.

## Alur

1. User klik link.
2. Browser memulai navigasi dan membuat dokumen target.
3. Browser request HTML dan menerima respons.
4. Parser membangun DOM dan menemukan CSS/JS.
5. CSS bisa menahan render; script tertentu bisa menahan parsing.
6. Setelah kondisi milestone terpenuhi, dokumen menjadi lebih "siap" (interaktif).
7. Setelah semua yang relevan selesai, dokumen dianggap selesai dimuat.

## Catatan

- Detail parsing ada di `C13 - The HTML Syntax`.
- Detail rendering ada di `C15 - Rendering`.
- Detail jaringan ada di rak `R06 - Networking & Fetch`.
