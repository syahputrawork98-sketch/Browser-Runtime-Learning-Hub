# Bab: C17 - IANA Considerations

## Ringkasan

Bab ini membahas bagian "IANA considerations" dari perspektif runtime browser: kaitannya dengan registri MIME type, bagaimana `Content-Type` mempengaruhi pemilihan parser (HTML vs XML), dan kenapa standard perlu menyebut registrasi/koordinasi eksternal seperti IANA. Fokusnya bukan proses birokrasi IANA, tetapi dampak praktisnya di browser: resource handling, sniffing (konsep), dan interoperabilitas ketika tipe media salah atau ambigu.

## Tujuan

- Memahami kenapa `Content-Type` adalah sinyal runtime yang sangat penting
- Menghubungkan registri MIME type (IANA) dengan keputusan di browser (parser selection, handling)
- Menjelaskan failure modes umum: server salah MIME type, content sniffing, dan konsekuensi debugging

## Analogi Singkat

IANA considerations itu seperti daftar label resmi di gudang: kalau labelnya benar, barang diproses jalur yang tepat; kalau labelnya salah, barang bisa masuk jalur yang keliru dan hasilnya kacau.

## Alur Utama

1. Resource dikirim lewat HTTP beserta header `Content-Type`
2. Browser memakai MIME type untuk memilih jalur pemrosesan (konsep)
3. Contoh jalur pemrosesan: parsing HTML/XHTML (lihat C13 dan C14) atau handling resource lain (script, CSS, media) (konsep)
4. Jika MIME type salah/ambigu, browser bisa melakukan mitigasi (mis. sniffing) atau memblokir (tergantung kebijakan dan konteks) (konsep)
5. Interoperabilitas bergantung pada "kontrak label" ini; karena itu spec menyebutkan pertimbangan registri/penamaan

## Istilah Kunci

- IANA (konsep)
- MIME type / media type
- `Content-Type`
- Parser selection (konsep)
- Content sniffing (konsep)
- Interoperability (konsep)

## Batasan dan Perilaku Penting

- Detail kebijakan sniffing dan mitigasi sering berada di spec lain (MIME sniffing, Fetch, CSP, dll).
- Bab ini adalah "hub": mengingatkan bahwa label (media type) mempengaruhi banyak subsistem runtime.
- Saat debugging parsing/handling yang aneh, cek `Content-Type` dulu sebelum menyalahkan markup.

## Sumber Referensi

- Sumber: HTML Standard (WHATWG)
- Versi/Tanggal: 2026-03-12
- Lokasi: `iana.html#iana-considerations` (multipage)

## Lampiran

- Diagram: `assets/overview.svg`
- Contoh: `examples/scenario-wrong-content-type-breaks-parser.md`
