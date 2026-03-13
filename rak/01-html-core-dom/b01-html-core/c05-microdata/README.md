# Bab: C05 - Microdata

## Ringkasan

Bab ini membahas Microdata sebagai fitur spesifik di HTML Standard: bagaimana data terstruktur dapat di-embed di DOM melalui atribut tertentu, bagaimana model item/properties dibentuk, dan apa batasan serta penggunaan yang realistis di browser.

## Tujuan

- Memahami Microdata sebagai model data berbasis DOM (item, property, scope)
- Menjelaskan apa yang "dibuat" browser (representasi/algoritma) ketika microdata dipakai
- Menempatkan Microdata secara proporsional: kapan berguna, kapan sebaiknya pakai pendekatan lain

## Analogi Singkat

Microdata itu seperti menempelkan label dan kartu indeks ke elemen DOM: label tersebut membuat elemen punya makna data tertentu tanpa mengubah tampilan.

## Analogi Panjang

Bayangkan kamu punya dokumen cetak, lalu kamu menempelkan sticky notes yang berisi kategori dan nilai. Dokumen utamanya tetap sama, tapi sticky notes itu membuat seseorang (atau sistem) bisa mengekstrak informasi terstruktur: mana yang dianggap "produk", mana "harga", mana "penjual".

Microdata melakukan hal serupa di HTML. Dengan atribut tertentu, elemen DOM bisa membentuk "item" dan "property" yang dapat diekstrak. Spec menjelaskan cara menentukan hubungan antar item, cara membaca property, dan bagaimana scope dibangun di dalam tree.

## Alur Utama

1. Author menambahkan atribut microdata pada elemen (mis. itemtype/itemscope/itemprop)
2. Browser membentuk model item/properties berdasarkan posisi elemen di DOM tree
3. Konsumen data (script, crawler, tooling) dapat mengekstrak data terstruktur dari dokumen
4. Perubahan DOM dapat mengubah hasil ekstraksi (karena model mengikuti tree)

## Istilah Kunci

- Microdata
- Item
- Item properties
- Item scope
- itemtype / itemprop (konsep)
- Extraction (proses konseptual)

## Batasan dan Perilaku Penting

- Microdata adalah metadata berbasis markup; banyak penggunaan modern bergeser ke JSON-LD atau format lain. Kita bahas dari sisi spec dan runtime, bukan rekomendasi SEO.
- Model microdata mengikuti struktur DOM; perubahan DOM bisa mengubah hasil ekstraksi.
- Microdata tidak "menjalankan" sesuatu di browser secara visual; dampaknya lebih ke representasi data.

## Sumber Referensi

- Sumber: HTML Standard (WHATWG)
- Versi/Tanggal: 2026-03-12
- Lokasi: `microdata.html#microdata` (multipage)

## Lampiran

- Diagram: `assets/overview.svg`
- Contoh: `examples/scenario-microdata-extraction.md`
