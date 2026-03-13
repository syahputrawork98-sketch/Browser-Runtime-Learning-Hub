# Bab: C13 - The HTML Syntax

## Ringkasan

Bab ini membahas "HTML syntax" dari sisi runtime browser: bagaimana byte/karakter diubah menjadi token, lalu menjadi node DOM, sambil tetap menjaga kompatibilitas web melalui error-recovery. Fokusnya adalah alur parsing (tokenizer + tree builder), insertion modes (konsep), dan integration points yang paling sering membuat parsing "tidak lurus" seperti script yang memblokir, `document.write` (konsep), dan parsing pada saat network streaming.

## Tujuan

- Memahami model mental parsing HTML: tokenizer -> tree builder -> DOM
- Menjelaskan mengapa HTML parsing punya banyak state (compat, error-recovery, insertion modes)
- Mengaitkan parsing dengan subsistem lain (network streaming, scripting, rendering) pada titik-titik kritis

## Analogi Singkat

Parsing HTML itu seperti petugas input data yang bekerja sambil membaca kertas yang masih keluar dari mesin fax: dia harus bisa memproses sebagian demi sebagian, memperbaiki typo yang umum, dan berhenti sebentar ketika ada instruksi khusus yang harus dijalankan sekarang juga (script).

## Alur Utama

1. Browser menerima bytes HTML dari network (seringnya streaming)
2. Bytes didekode (encoding) menjadi character stream
3. Tokenizer mengubah character stream menjadi token (start tag, end tag, text, comment, doctype)
4. Tree builder mengonsumsi token dengan "insertion mode" tertentu dan membangun node DOM
5. Error-recovery terjadi di berbagai titik: missing end tags, malformed markup, dan kasus-kasus kompatibilitas
6. Ketika bertemu `<script>` yang memblokir, parsing dapat berhenti sampai script selesai dieksekusi (konsep)
7. Parsing bisa re-enter via `document.write` (konsep), yang mengubah input stream saat parsing berjalan
8. Token tertentu memicu perubahan mode (mis. raw text states, foreign content) (konsep)

## Istilah Kunci

- Tokenizer
- Tree builder
- Insertion mode (konsep)
- Error recovery / parse error (konsep)
- Blocking script (konsep)
- Re-entrancy (konsep)

## Batasan dan Perilaku Penting

- HTML parsing didesain untuk kompatibilitas: hasil DOM "masuk akal" meski input markup buruk.
- Parsing bersifat stateful: hasil akhir tidak hanya tergantung token, tetapi juga mode saat token dikonsumsi.
- Script dapat mempengaruhi parsing secara signifikan (blok, re-enter, atau mengubah DOM saat parsing).
- Detail state/token sangat panjang; bab ini menekankan alur yang paling sering muncul saat debugging runtime.

## Sumber Referensi

- Sumber: HTML Standard (WHATWG)
- Versi/Tanggal: 2026-03-12
- Lokasi: `parsing.html#parsing` (multipage)

## Lampiran

- Diagram: `assets/overview.svg`
- Contoh: `examples/scenario-streaming-parse-and-script.md`
