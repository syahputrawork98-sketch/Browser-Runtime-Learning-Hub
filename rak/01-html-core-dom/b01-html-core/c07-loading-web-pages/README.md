# Bab: C07 - Loading Web Pages

## Ringkasan

Bab ini membahas lifecycle loading halaman dari sudut pandang browser runtime: navigasi, pembuatan dokumen baru, pemuatan resource utama (HTML), fase-fase kesiapan dokumen, dan bagaimana loading berinteraksi dengan parsing, scripting, dan rendering.

## Tujuan

- Memahami alur high level dari navigasi sampai dokumen dianggap "selesai"
- Menjelaskan state dan milestone yang sering dipakai untuk reasoning (mis. dokumen sudah interaktif)
- Menjadi landasan untuk bab parsing (C13), rendering (C15), dan interaksi user (C06)

## Analogi Singkat

Loading halaman itu seperti proses membuka file besar: ada tahap memuat, tahap siap dipakai, lalu tahap finalisasi ketika semuanya selesai.

## Analogi Panjang

Bayangkan kamu membuka aplikasi yang harus menyiapkan banyak hal sebelum bisa digunakan: aplikasi menampilkan layar loading, lalu sebagian fitur sudah bisa dipakai (misalnya UI tampil dan tombol merespons), dan akhirnya semua data tambahan selesai diunduh sehingga aplikasi benar-benar siap.

Browser melakukan hal serupa saat memuat halaman. Ia melakukan navigasi, membuat dokumen baru, memulai parsing HTML, memuat sub-resource seperti CSS/JS, menjalankan script sesuai aturan, dan menggerakkan rendering pipeline. Spec mendefinisikan milestone dan algoritma agar urutan dan state yang observable konsisten.

## Alur Utama

1. Navigasi dimulai (user klik link / ganti URL / script memicu navigasi)
2. Browser menyiapkan konteks untuk dokumen tujuan dan memulai request HTML
3. Respon diterima, encoding ditentukan, parsing dimulai, DOM tumbuh
4. Sub-resource ditemukan (CSS/JS/images) dan proses loading berjalan paralel sesuai aturan
5. Milestone dokumen tercapai (mis. interaktif) ketika kondisi tertentu terpenuhi
6. Setelah semua yang relevan selesai, dokumen dianggap selesai dimuat

## Istilah Kunci

- Navigation
- Document lifecycle
- Readiness milestone (konsep)
- Render-blocking resource (konsep)
- Parser-blocking script (konsep)

## Batasan dan Perilaku Penting

- Loading dipengaruhi oleh resource blocking (CSS) dan aturan script (async/defer/parser-blocking).
- Browser memiliki optimisasi (preload scanner, heuristics), tetapi milestone dan observable behavior harus mengikuti spec.
- Detail jaringan (DNS/TLS/HTTP) ada di rak Networking; bab ini fokus state dokumen dan hubungan parsing/rendering.

## Sumber Referensi

- Sumber: HTML Standard (WHATWG)
- Versi/Tanggal: 2026-03-12
- Lokasi: `browsing-the-web.html#loading-web-pages` (multipage)

## Lampiran

- Diagram: `assets/overview.svg`
- Contoh: `examples/scenario-navigation-to-load.md`
