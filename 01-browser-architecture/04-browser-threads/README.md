# Browser Threads

Status: Draft
Last reviewed: 2026-03-10
Version log: [docs/book-log.md](./docs/book-log.md)

## Tujuan

Menjelaskan pembagian thread penting dalam runtime browser dan dampaknya terhadap eksekusi JavaScript serta rendering.

## Konsep Utama

- Main thread renderer menjalankan JavaScript, style, layout, dan event handling utama.
- Compositor thread membantu menjaga kelancaran animasi/scrolling.
- Worker thread memungkinkan kerja paralel di luar main thread.

## Penjelasan

Pada renderer process, main thread biasanya menjadi jalur kritis karena sebagian besar logika aplikasi berjalan di sini. Jika JavaScript melakukan kerja sinkron berat, event input dan rendering update dapat tertunda (jank).

Browser modern memindahkan sebagian pekerjaan ke thread lain:

1. Compositor thread
Memproses komposisi layer dan dapat menjalankan sebagian animasi/scrolling tanpa menunggu main thread penuh.

2. Raster/paint worker threads
Melakukan rasterisasi konten visual agar pipeline rendering lebih paralel.

3. Web Worker threads
Memberi ruang komputasi background untuk aplikasi (misalnya parsing data besar) tanpa memblokir UI thread.

Pembagian ini menurunkan contention, tetapi sinkronisasi data dan komunikasi antarthread tetap punya biaya.

## Implikasi Praktis

- Long task di main thread adalah penyebab utama UI lag.
- Offloading ke Worker efektif untuk CPU-bound tasks.
- Tidak semua operasi DOM bisa dipindahkan dari main thread.

## Referensi

- HTML Standard (workers): https://html.spec.whatwg.org/multipage/workers.html
- Chromium Rendering Architecture Notes: https://chromium.googlesource.com/chromium/src/+/main/docs/
- MDN Web Workers: https://developer.mozilla.org/docs/Web/API/Web_Workers_API

