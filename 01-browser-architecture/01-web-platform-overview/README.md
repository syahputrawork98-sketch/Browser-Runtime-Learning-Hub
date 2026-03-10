# Web Platform Overview

Status: Draft
Last reviewed: 2026-03-10
Version log: [docs/book-log.md](./docs/book-log.md)

## Tujuan

Membangun gambaran besar tentang komponen web platform, posisi JavaScript engine, dan batas tanggung jawab browser runtime.

## Konsep Utama

- Browser runtime adalah gabungan engine JavaScript + subsistem browser.
- JavaScript language semantics didefinisikan oleh ECMAScript, bukan oleh browser vendor.
- Web APIs (DOM, Fetch, Timers, Worker) didefinisikan oleh spesifikasi web platform.

## Penjelasan

Saat kode JavaScript berjalan di browser, engine JavaScript menangani parsing, compilation, dan eksekusi instruksi bahasa. Namun aplikasi web bergantung pada sistem lain yang tidak berada di inti bahasa, seperti DOM tree, network stack, event system, dan rendering pipeline.

Karena itu, memahami runtime browser harus membedakan:

1. Bahasa JavaScript: sintaks, scope, object model, async primitives.
2. Host environment (browser): event loop host, task scheduling, Web APIs.
3. Rendering system: layout, paint, compositing.

Model mental ini penting agar jelas kenapa kode yang valid secara ECMAScript tetap bisa punya perilaku berbeda jika host scheduling, throttling timer, atau kebijakan rendering berubah.

## Implikasi Praktis

- Bug aplikasi sering berasal dari interaksi antarsubsistem, bukan dari sintaks JavaScript saja.
- Optimisasi performa perlu melihat biaya scripting + rendering + network secara bersamaan.
- Dokumentasi teknis harus memisahkan mana aturan language dan mana aturan host.

## Referensi

- ECMAScript Language Specification: https://tc39.es/ecma262/
- HTML Standard (event loop, tasks, timers): https://html.spec.whatwg.org/
- DOM Standard: https://dom.spec.whatwg.org/
- Fetch Standard: https://fetch.spec.whatwg.org/
- MDN Web Docs: https://developer.mozilla.org/

