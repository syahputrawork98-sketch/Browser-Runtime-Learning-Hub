# Bab: C12 - Web Storage

## Ringkasan

Bab ini membahas Web Storage (localStorage dan sessionStorage) dari sisi runtime browser: model penyimpanan key-value sederhana, ruang lingkupnya (per origin), lifecycle data, dan batasan keamanan/privasi yang umum. Fokusnya bukan API usage tutorial, tetapi bagaimana browser mengelola storage sebagai bagian dari platform.

## Tujuan

- Memahami model penyimpanan dan scoping (origin / browsing context)
- Menjelaskan perbedaan localStorage vs sessionStorage secara konseptual
- Menjadi jembatan ke rak Storage & Persistence untuk detail yang lebih luas

## Analogi Singkat

Web Storage itu seperti laci catatan kecil: cepat diakses, isinya sederhana (key-value), tapi punya aturan siapa yang boleh membuka dan kapan isinya bertahan.

## Analogi Panjang

Bayangkan kamu punya dua jenis catatan: catatan yang disimpan di lemari kantor (tetap ada besok), dan catatan yang hanya disimpan di meja kerja hari ini (hilang ketika kamu pulang). localStorage mirip lemari kantor: data bertahan lintas sesi. sessionStorage mirip catatan di meja: bertahan selama sesi/browsing context tertentu.

Di browser, storage tidak berdiri sendiri; ia dipengaruhi origin, kebijakan keamanan, dan kadang mode privasi. Bab ini merangkum model runtime dan integration points, sementara detail aturan isolasi storage yang lebih luas kita tautkan ke rak Storage & Persistence.

## Alur Utama

1. Script membaca/menulis pasangan key-value
2. Browser memetakan storage ke scope yang tepat (origin + konteks yang relevan)
3. Data diserialisasi sebagai string dan disimpan
4. Pada akses berikutnya, browser mengambil data sesuai scope
5. Lifecycle data berbeda: localStorage bertahan, sessionStorage mengikuti sesi/konteks

## Istilah Kunci

- localStorage
- sessionStorage
- Origin (konsep)
- Storage area (konsep)
- Persistence (konsep)

## Batasan dan Perilaku Penting

- Web Storage umumnya sinkron dan bisa berdampak performa jika disalahgunakan.
- Kebijakan privasi/isolasi bisa mempengaruhi kapan storage tersedia (mis. mode privat, partitioning). Detail luas ada di rak Storage & Persistence.
- Data disimpan sebagai string; tipe kompleks perlu serialisasi manual (JSON, dll).

## Sumber Referensi

- Sumber: HTML Standard (WHATWG)
- Versi/Tanggal: 2026-03-12
- Lokasi: `webstorage.html#webstorage` (multipage)

## Lampiran

- Diagram: `assets/overview.svg`
- Contoh: `examples/scenario-scope-and-lifecycle.md`
