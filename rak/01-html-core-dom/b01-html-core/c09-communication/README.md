# Bab: C09 - Communication

## Ringkasan

Bab ini membahas komunikasi antar konteks eksekusi di browser (mis. antar window/iframe/worker) dari sisi runtime: bagaimana pesan dibentuk, diserialisasi, dikirim, dan akhirnya di-dispatch sebagai event ke penerima. Fokusnya adalah alur dan aturan browser, bukan library messaging.

## Tujuan

- Memahami pola komunikasi lintas konteks yang didefinisikan di HTML Standard
- Menjelaskan alur `postMessage`-style: serialize -> queue -> dispatch
- Menjadi jembatan ke C10 (Workers) dan topik security (origin) di rak lain

## Analogi Singkat

Communication itu seperti kirim paket: pesan dibungkus (serialize), dikirim lewat jalur (queue), lalu dibuka di tujuan (dispatch event).

## Analogi Panjang

Bayangkan kamu mengirim dokumen antar ruangan di kantor. Dokumen harus dimasukkan amplop (serialisasi), diberi alamat (target), lalu masuk antrian kurir (queue). Saat sampai, penerima membuka amplop dan memprosesnya (event dispatch). Kalau alamatnya salah atau aturan keamanan tidak mengizinkan, dokumen tidak diproses.

Di browser, komunikasi lintas konteks memakai mekanisme yang serupa: pesan harus bisa diserialisasi (structured clone), lalu browser menjadwalkan pengiriman dan dispatch. Pada saat yang sama, kebijakan seperti origin mempengaruhi apakah pesan diterima/diproses.

## Alur Utama

1. Pengirim memanggil API komunikasi (mis. `postMessage`)
2. Browser melakukan serialisasi pesan (structured clone) dan memvalidasi target
3. Browser menjadwalkan pengiriman (task) ke target context
4. Penerima menerima event message dan handler berjalan
5. Handler dapat mengubah DOM, memicu render, atau mengirim balasan

## Istilah Kunci

- Browsing context (konsep)
- Message event
- Structured clone (konsep)
- Task queue (konteks)
- Origin / target origin (konsep)

## Batasan dan Perilaku Penting

- Komunikasi lintas konteks memiliki batasan security (origin). Detail origin ada di rak URL & Origin / Security.
- Serialisasi pesan memiliki batasan tipe data; beberapa object tidak bisa diserialisasi.
- Pengiriman dan dispatch bergantung pada scheduling/event loop (rak JavaScript Runtime).

## Sumber Referensi

- Sumber: HTML Standard (WHATWG)
- Versi/Tanggal: 2026-03-12
- Lokasi: `web-messaging.html#web-messaging` (multipage)

## Lampiran

- Diagram: `assets/overview.svg`
- Contoh: `examples/scenario-window-to-iframe-message.md`
