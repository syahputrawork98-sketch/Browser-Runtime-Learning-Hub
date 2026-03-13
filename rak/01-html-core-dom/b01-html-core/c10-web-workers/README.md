# Bab: C10 - Web Workers

## Ringkasan

Bab ini membahas Web Workers sebagai cara browser menjalankan JavaScript di konteks terpisah dari halaman (main thread). Fokusnya adalah model runtime: pembuatan worker, lifecycle, komunikasi (message passing), dan hubungan worker dengan event loop dan scheduling.

## Tujuan

- Memahami kapan dan kenapa workers dipakai (isolasi konteks, non-blocking UI)
- Menjelaskan alur worker: create -> run -> message -> terminate
- Menjadi jembatan ke C09 (Communication), C08 (Web APIs), dan rak JavaScript Runtime

## Analogi Singkat

Worker itu seperti asisten di ruangan lain: kamu memberi tugas lewat pesan, asisten mengerjakan, lalu mengirim hasil balik tanpa mengganggu pekerjaan utama.

## Analogi Panjang

Bayangkan kamu sedang mengerjakan dokumen di meja utama (main thread). Kalau kamu sekaligus harus menghitung sesuatu yang berat, kamu bisa meminta rekan di ruangan lain mengerjakan perhitungan itu. Kamu kirim instruksi (message), rekan menghitung di ruangnya sendiri (worker context), lalu mengirim balik hasilnya (message event). Meja utama tetap responsif.

Di browser, worker memberikan konteks eksekusi terpisah. Tidak ada akses langsung ke DOM; komunikasi dilakukan lewat message passing. Spec mendefinisikan bagaimana worker dibuat, bagaimana skrip worker dimuat, bagaimana event loop worker berjalan, dan bagaimana pesan dijadwalkan.

## Alur Utama

1. Main thread membuat worker (mis. `new Worker(url)`)
2. Browser memuat dan menjalankan skrip worker di konteks terpisah
3. Main dan worker saling kirim pesan (`postMessage`) melalui structured clone
4. Worker memproses pesan (task), lalu mengirim hasil balik
5. Worker dapat dihentikan (terminate) atau berhenti saat kondisi tertentu

## Istilah Kunci

- Worker
- Worker global scope (konsep)
- Message passing
- Structured clone (konteks)
- Termination
- Event loop (konteks worker)

## Batasan dan Perilaku Penting

- Worker tidak bisa mengakses DOM secara langsung; ini menjaga isolasi dan mencegah race dengan UI.
- Pengiriman pesan bergantung pada structured clone dan scheduling task; detailnya terkait C09 dan rak JS runtime.
- Ada jenis worker lain (Service Worker) yang punya lifecycle berbeda; catat dan tautkan ke rak Workers & Background jika perlu.

## Sumber Referensi

- Sumber: HTML Standard (WHATWG)
- Versi/Tanggal: 2026-03-12
- Lokasi: `workers.html#workers` (multipage)

## Lampiran

- Diagram: `assets/overview.svg`
- Contoh: `examples/scenario-main-to-worker-message.md`
