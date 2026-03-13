# Skenario: Elemen Memicu Side Effects

Tujuan: menunjukkan bahwa elemen bukan hanya "markup", tapi bisa memicu aksi di browser.

## Contoh Alur

1. Parser membaca `<link rel="stylesheet" href="style.css">` di `head`.
2. Browser memulai request CSS (resource discovery) dan menandai sebagai render-blocking (tergantung konteks).
3. Parser membaca `<script src="app.js"></script>`.
4. Browser memulai request JS, dan jika script parser-blocking, parsing berhenti sampai script siap dan dieksekusi.
5. Setelah CSS/JS diproses, rendering pipeline memakai DOM + CSS untuk menghasilkan tampilan.

## Catatan

- Detail parsing dan blocking behavior ada di `C13 - The HTML Syntax`.
- Detail loading lifecycle ada di `C07 - Loading Web Pages`.
- Detail rendering ada di `C15 - Rendering`.
