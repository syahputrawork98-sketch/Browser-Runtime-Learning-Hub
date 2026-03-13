# Bab: C02 - Common Infrastructure

## Ringkasan

Bab ini adalah fondasi lintas bab di HTML Standard: istilah, pola penulisan algoritma, microsyntaxes, serta konsep umum yang dipakai berulang-ulang ketika browser memproses dokumen HTML, memuat resource, dan menjalankan API terkait.

## Tujuan

- Menyatukan istilah dan konsep dasar agar bab lain tidak perlu mengulang-ulang definisi
- Menjelaskan cara membaca algoritma di spec (state, input, output, side effects)
- Menjadi kamus mini untuk topik yang sering muncul: encoding, resources, policies, microsyntaxes

## Analogi Singkat

Common Infrastructure itu seperti "bahasa dan aturan main" di awal buku: definisi istilah, format penulisan, dan konvensi yang dipakai di semua bab berikutnya.

## Analogi Panjang

Bayangkan kamu membaca buku manual mesin yang sangat besar. Kalau setiap bab menjelaskan ulang arti kata "sensor", "kalibrasi", atau "mode", kamu akan cepat capek dan rawan salah paham. Karena itu, manual biasanya punya bagian "Terminology" dan "Common rules" di depan.

HTML Standard juga begitu. Common Infrastructure adalah tempat spec menyepakati istilah, pola, dan building blocks yang akan dipakai terus-menerus. Kalau kita memahami bagian ini dengan baik, membaca bab-bab lain jadi jauh lebih cepat, karena kita tahu apa maksud istilah, apa yang dianggap "resource", dan bagaimana membaca algoritma yang ditulis di spec.

## Alur Utama

1. Samakan istilah: apa yang dimaksud spec dengan dokumen, resources, parsing, user agent, dsb.
2. Pahami pola algoritma: langkah-langkah normatif yang mengubah state browser atau state dokumen
3. Pahami microsyntaxes: format teks yang muncul di atribut/URL/dates, dan bagaimana browser mem-parsingnya
4. Catat integration points: kapan HTML merujuk ke URL/Fetch/Encoding/DOM, dan kapan kita pindahkan detailnya ke rak lain

## Istilah Kunci

- Terminology
- Resource
- Parallelism (konsep, bukan thread model tertentu)
- Character encoding
- Conformance classes
- Policy-controlled features
- Microsyntaxes (boolean, enumerated, dates, numbers, etc.)

## Batasan dan Perilaku Penting

- Common Infrastructure bukan "fitur" yang terlihat oleh pengguna, tetapi mempengaruhi cara kita membaca dan menafsirkan bab lain.
- Banyak konsep di sini punya batasan yang ditentukan spec lain (mis. URL/Fetch/Encoding). Kita gunakan bagian ini untuk konteks, lalu detailnya kita taruh di rak yang tepat.
- Implementasi browser bisa berbeda dalam optimisasi, tapi hasil normatif (observable behavior) harus konsisten dengan algoritma.

## Sumber Referensi

- Sumber: HTML Standard (WHATWG)
- Versi/Tanggal: 2026-03-12
- Lokasi: `infrastructure.html#infrastructure` (multipage), termasuk Terminology, Policy-controlled features, dan Common microsyntaxes

## Lampiran

- Diagram: `assets/overview.svg`
- Contoh: `examples/microsyntaxes.md`
