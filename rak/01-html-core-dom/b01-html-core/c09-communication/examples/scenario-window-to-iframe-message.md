# Skenario: Window Mengirim Pesan ke Iframe

Tujuan: menggambarkan alur `postMessage` secara konseptual.

## Alur

1. Halaman utama membuat iframe (bisa same-origin atau cross-origin).
2. Halaman utama memanggil `postMessage(payload, targetOrigin)` ke `contentWindow` iframe.
3. Browser men-serialize `payload` (structured clone) dan menjadwalkan task untuk target.
4. Iframe menerima event `message`.
5. Handler `message` memeriksa origin, lalu memproses payload.

## Catatan

- Validasi origin adalah bagian penting untuk keamanan.
- Detail event loop (task queue) ada di rak JavaScript Runtime.
