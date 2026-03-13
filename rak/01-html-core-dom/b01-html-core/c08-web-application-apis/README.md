# Bab: C08 - Web Application APIs

## Ringkasan

Bab ini membahas Web Application APIs yang didefinisikan di HTML Standard dan menjadi bagian dari runtime browser: API yang dipakai aplikasi web untuk scheduling (timers), messaging, dan perilaku platform yang berpengaruh ke dokumen dan interaksi. Bab ini bukan katalog API lengkap; fokusnya adalah alur, state, dan integration points.

## Tujuan

- Memahami bagaimana API platform di HTML Standard terhubung ke event loop dan dokumen
- Menjelaskan pola umum: scheduling -> callback -> efek ke DOM/rendering
- Menjadi jembatan ke bab Communication (C09) dan Workers (C10)

## Analogi Singkat

Web Application APIs itu seperti "tools" standar yang disediakan browser: kamu memanggil tool, browser mengatur kapan dan bagaimana hasilnya kembali.

## Analogi Panjang

Bayangkan kamu bekerja di dapur dengan peralatan standar: timer oven, bel pemanggil, dan meja kerja. Kamu bisa menaruh tugas untuk dikerjakan nanti (timer), mengirim pesan ke rekan (messaging), dan saat hasilnya siap, kamu kembali mengolahnya di meja kerja (DOM).

Di browser, banyak API platform bekerja dengan pola yang mirip: kita minta sesuatu, browser menjadwalkan pekerjaan, dan nanti callback dijalankan pada waktu yang tepat. Di situlah event loop, task/microtask, dan state dokumen ikut menentukan kapan kode berjalan dan apa dampaknya ke rendering.

## Alur Utama

1. Script memanggil API platform (mis. timer atau messaging)
2. Browser menjadwalkan pekerjaan dan menyimpan state yang diperlukan
3. Pada waktu yang tepat, browser mengantrikan task/microtask untuk callback
4. Callback berjalan, dapat memodifikasi DOM dan memicu rendering
5. Untuk komunikasi lintas konteks, pesan diserialisasi dan dikirim, lalu di-dispatch pada penerima

## Istilah Kunci

- Task / microtask (konteks)
- Callback
- Scheduling
- PostMessage (konsep)
- Timer (konsep)
- Event loop integration

## Batasan dan Perilaku Penting

- Banyak detail scheduling berada di bab runtime/event loop (rak JavaScript Runtime); di sini kita fokus integration points dari sisi HTML Standard.
- Beberapa API memiliki batasan keamanan dan membutuhkan user activation; catat jika relevan.
- Beberapa mekanisme komunikasi dan serialization punya aturan khusus; detailnya diperdalam di C09.

## Sumber Referensi

- Sumber: HTML Standard (WHATWG)
- Versi/Tanggal: 2026-03-12
- Lokasi: `webappapis.html#webappapis` (multipage)

## Lampiran

- Diagram: `assets/overview.svg`
- Contoh: `examples/scenario-timer-to-render.md`
