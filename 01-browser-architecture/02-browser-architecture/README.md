# Browser Architecture

Status: Draft
Last reviewed: 2026-03-10
Version log: [docs/book-log.md](./docs/book-log.md)

## Tujuan

Menjelaskan arsitektur tingkat tinggi browser modern dan alasan desain utamanya: isolasi, stabilitas, keamanan, dan responsivitas UI.

## Konsep Utama

- Browser modern bersifat multi-process, bukan single-process.
- Tiap tab/site umumnya dipisah untuk isolasi kegagalan dan keamanan.
- Rendering dipisahkan dari kontrol UI browser.

## Penjelasan

Secara umum, browser memiliki proses utama (browser process) yang mengelola UI browser, lifecycle tab, izin, dan koordinasi proses lain. Konten web dirender di proses terpisah (renderer process). Pendekatan ini membantu mencegah satu halaman rusak menyebabkan seluruh browser crash.

Arsitektur ini juga mendukung sandboxing. Renderer process menjalankan kode dari web yang tidak tepercaya, sehingga akses langsung ke resource sensitif sistem dibatasi. Komunikasi antarpoces dilakukan lewat IPC (inter-process communication) dengan boundary yang ketat.

Sebagai konsekuensi, operasi yang tampak sederhana dari perspektif JavaScript sering melibatkan koordinasi lintas proses, misalnya request network, akses storage, atau pembaruan frame ke layar.

## Implikasi Praktis

- Isolasi proses meningkatkan reliability, tetapi menambah overhead IPC.
- Debugging performa harus mempertimbangkan biaya lintas proses.
- Kebijakan site isolation berdampak pada memory footprint per tab.

## Referensi

- Chromium Multi-process Architecture: https://www.chromium.org/developers/design-documents/multi-process-architecture/
- Chromium Architecture Overview: https://www.chromium.org/developers/how-tos/trace-event-profiling-tool/
- Site Isolation (Chromium): https://www.chromium.org/Home/chromium-security/site-isolation/

