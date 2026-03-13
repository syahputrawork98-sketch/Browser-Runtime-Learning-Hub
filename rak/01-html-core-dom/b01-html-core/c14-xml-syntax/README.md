# Bab: C14 - The XML Syntax

## Ringkasan

Bab ini membahas XML syntax (XHTML) sebagai jalur parsing yang berbeda dari HTML parsing. Fokusnya: bagaimana browser memilih parser berdasarkan MIME type, bagaimana XML parsing bersifat "strict" (fatal error) dibanding HTML yang error-tolerant, dan implikasinya terhadap DOM yang terbentuk, namespace, serta debugging runtime ketika dokumen diparse sebagai XML.

## Tujuan

- Memahami perbedaan mendasar: HTML parser (error recovery) vs XML parser (well-formedness)
- Menjelaskan kapan dokumen akan diparse sebagai XML (umumnya tergantung Content-Type)
- Mengaitkan efeknya ke DOM, script, dan tooling (mis. kesalahan kecil bisa membuat dokumen gagal tampil)

## Analogi Singkat

Kalau HTML parsing itu seperti pembaca yang tetap paham walau ada typo, XML parsing itu seperti compiler ketat: satu kesalahan kecil bisa menghentikan semuanya.

## Alur Utama

1. Server mengirim respons beserta `Content-Type`
2. Jika bertipe XML/XHTML (konsep), gunakan XML parser
3. Jika bertipe HTML, gunakan HTML parser (C13)
4. Parser membangun DOM dengan aturan yang berbeda (XML menekankan well-formedness dan namespace)
5. Jika ada fatal parse error (XML path), proses parsing berhenti dan hasilnya bisa sangat berbeda dari HTML
6. Setelah DOM terbentuk, subsistem berikutnya (CSS, layout, script) berjalan di atas hasil DOM tersebut

## Istilah Kunci

- XHTML (konsep)
- MIME type / Content-Type (konsep)
- XML parser
- Well-formedness (konsep)
- Namespace (konsep)
- Fatal parse error (konsep)

## Batasan dan Perilaku Penting

- Perbedaan utama bukan "tag apa yang boleh", tapi mesin parsing yang dipilih dan konsekuensinya.
- Pada XML parsing, kesalahan well-formedness biasanya fatal; ini sering mengejutkan jika terbiasa dengan HTML error recovery.
- Untuk runtime debugging, langkah pertama adalah memastikan dokumen diparse sebagai HTML atau XML sesuai niat.

## Sumber Referensi

- Sumber: HTML Standard (WHATWG)
- Versi/Tanggal: 2026-03-12
- Lokasi: `xhtml.html#xhtml` (multipage)

## Lampiran

- Diagram: `assets/overview.svg`
- Contoh: `examples/scenario-content-type-selects-parser.md`
