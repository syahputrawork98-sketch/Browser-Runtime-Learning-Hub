# Bab: C01 - Introduction

## Ringkasan

Bab ini menjelaskan apa itu HTML Standard (WHATWG) sebagai "buku besar" kita: ruang lingkupnya, cara membacanya, dan cara memetakan istilah/struktur spec ke rak-buku-bab di repo ini. Tujuannya agar kita tidak tersesat saat membaca spec yang panjang, tetapi tetap akurat saat menulis ulang pengetahuan tentang cara kerja browser.

## Tujuan

- Menetapkan definisi "buku besar" untuk B01 dan cara kita mengambil bab darinya
- Membuat strategi membaca spec: dari konsep besar ke bagian yang benar-benar dipakai browser runtime
- Menjelaskan bagaimana spec ini terhubung dengan bab lain (parsing, elements, loading, rendering, workers, dsb.)

## Analogi Singkat

HTML Standard itu seperti peta kota resmi: bukan mengajari cara berjalan, tapi menjelaskan aturan jalan dan rambu. Repo ini memecah peta itu menjadi rute-rute kecil agar kita bisa memahami perjalanan browser langkah demi langkah.

## Analogi Panjang

Bayangkan kamu punya buku petunjuk cara kerja sebuah bandara internasional. Buku itu menjelaskan aturan-aturan: bagaimana penumpang masuk, bagaimana bagasi diproses, kapan pesawat boleh berangkat, dan apa yang terjadi jika ada kondisi khusus. HTML Standard mirip seperti itu untuk browser: ia menjelaskan aturan normatif yang membuat browser dari vendor berbeda bisa berperilaku konsisten.

Monorepo ini adalah perpustakaan yang menata ulang buku petunjuk itu. Kita buat rak, buku, dan bab supaya saat kita butuh memahami satu proses (misalnya parsing HTML atau lifecycle loading), kita tidak harus membaca seluruh buku dari awal. Kita ambil bagian yang paling sering dipakai, kita beri konteks runtime, dan kita catat sumbernya supaya selalu bisa disinkronkan ketika spec berubah.

## Alur Utama

1. Pahami posisi HTML Standard dalam ekosistem web: apa yang diatur HTML vs spec lain (DOM, CSS, Fetch, URL)
2. Pakai struktur/TOC spec untuk membagi pekerjaan jadi bab-bab yang bisa ditulis dan direview
3. Saat menulis bab, selalu jawab: "bagaimana browser melakukannya?" (state, algorithm, side effects), bukan "cara menulis HTML"
4. Jika topik lebih cocok di rak lain, catat tautannya dan pindahkan (mis. Workers/Storage/Communication)

## Istilah Kunci

- Living Standard
- User agent (browser)
- Document
- DOM
- Conformance (conforming/non-conforming)
- Algorithm (langkah-langkah normatif di spec)
- Integration point (hubungan antar spec)

## Batasan dan Perilaku Penting

- HTML Standard itu "living": judul section bisa berubah; yang kita kunci adalah (1) tanggal/versi snapshot, (2) URL section.
- Spec menjelaskan perilaku normatif, tapi implementasi browser bisa memiliki detail tambahan (optimizations, heuristics).
- Banyak konsep inti HTML bergantung pada spec lain (DOM, URL, Fetch, Encoding, CSS); di repo ini kita tautkan silang, bukan menggandakan semuanya.

## Cara Menggunakan Bab Ini Saat Menulis Bab Lain

- Mulai dari TOC: pilih satu bab, lalu turunkan ke section yang benar-benar sering dipakai di browser runtime.
- Di setiap bab/section, buat 1 skenario nyata (mis. load halaman, parse HTML, jalankan script) dan jelaskan alurnya.
- Simpan detail panjang/ekstra di `docs/` bab agar `README.md` tetap fokus.

## Sumber Referensi

- Sumber: HTML Standard (WHATWG)
- Versi/Tanggal: 2026-03-12
- Lokasi: `introduction.html#introduction` (multipage), terutama "Where does this specification fit?", "Scope", dan "How to read this specification"

## Lampiran

- Diagram: `assets/overview.svg`
- Contoh: `examples/scenario-load-page.md`
