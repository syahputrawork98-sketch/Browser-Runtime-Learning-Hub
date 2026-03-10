# Browser Processes

Status: Draft
Last reviewed: 2026-03-10
Version log: [docs/book-log.md](./docs/book-log.md)

## Tujuan

Menjelaskan peran proses-proses utama di browser dan bagaimana proses ini bekerja sama menjalankan aplikasi web.

## Konsep Utama

- Browser process mengatur UI browser dan orkestrasi global.
- Renderer process menjalankan dokumen web dan JavaScript.
- Utility/GPU/Network process menangani tugas spesifik agar sistem lebih aman dan terisolasi.

## Penjelasan

Implementasi tiap browser berbeda, tetapi pola umumnya serupa:

1. Browser process
Menangani tab management, navigasi, permission, session, dan kebijakan keamanan level aplikasi.

2. Renderer process
Menjalankan pipeline dokumen web: parse HTML/CSS, eksekusi JavaScript, pembentukan render tree, dan koordinasi update frame.

3. GPU process
Mengelola komposisi layer dan rendering yang memanfaatkan akselerasi GPU.

4. Network/utility process
Memisahkan layanan seperti networking, decoding media, atau service khusus lain untuk mengurangi blast radius saat terjadi bug.

Pemisahan ini membuat kegagalan di satu komponen lebih terlokalisasi, dan kebijakan privilege bisa diterapkan lebih ketat.

## Implikasi Praktis

- Memory usage meningkat seiring banyaknya proses/tab/site instance.
- Profiling harus mengecek proses yang tepat (renderer vs GPU vs browser process).
- Crash tab tidak selalu berarti browser process bermasalah.

## Referensi

- Chromium Process Models: https://chromium.googlesource.com/chromium/src/+/main/docs/process_model_and_site_isolation.md
- Chromium GPU Architecture: https://chromium.googlesource.com/chromium/src/+/main/docs/gpu/
- Mozilla Multiprocess Architecture (Electrolysis/Fission): https://wiki.mozilla.org/Project_Fission

