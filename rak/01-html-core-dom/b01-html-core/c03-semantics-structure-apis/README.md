# Bab: C03 - Semantics, Structure, and APIs

## Ringkasan

Bab ini membahas "apa itu dokumen HTML" dari sudut pandang runtime browser: bagaimana struktur dokumen diwakili sebagai DOM, bagaimana metadata dan state dokumen berubah selama loading, dan bagaimana API dokumen digunakan oleh browser dan oleh script.

## Tujuan

- Menjelaskan model dokumen HTML: struktur, state, dan lifecycle
- Menghubungkan konsep dokumen di HTML Standard dengan DOM dan rendering
- Menjadi landasan untuk bab parsing (C13), loading (C07), dan rendering (C15)

## Analogi Singkat

Dokumen HTML itu seperti "ruang kerja" di browser: ada struktur (meja dan laci), ada status (sedang loading atau sudah siap), dan ada alat-alat (API) untuk memanipulasi isi ruang kerja tersebut.

## Analogi Panjang

Bayangkan browser seperti kantor yang sedang menerima berkas proyek baru. Berkas proyek itu adalah dokumen HTML. Saat berkas masuk, kantor belum langsung "siap dipakai"; ada proses administrasi: membuat folder, menempel label, menaruh bagian-bagian ke tempatnya, dan mencatat statusnya.

Struktur berkas itu diwujudkan menjadi DOM (struktur pohon). Sambil proses berlangsung, status dokumen berubah (mis. masih memuat, sudah interaktif, atau sudah selesai). Lalu ada seperangkat alat (API) yang dipakai untuk membaca/mengubah isi dokumen. Spec di bagian ini menjelaskan aturan normatif yang membuat semua browser memahami dokumen dengan cara yang konsisten.

## Alur Utama

1. Dokumen HTML dibentuk sebagai struktur DOM (tree) dan memiliki metadata serta state internal
2. Selama lifecycle loading, state dokumen berubah dan mempengaruhi apa yang bisa terjadi (mis. kapan script berjalan, kapan render bisa terjadi)
3. API dokumen menjadi jembatan antara spec dan perilaku observable di browser (akses oleh script dan oleh internal browser)
4. Banyak aturan di sini punya integration points ke DOM/URL/Fetch/Encoding dan ke rendering pipeline

## Istilah Kunci

- Document
- Document tree (DOM tree)
- Document metadata
- Loading lifecycle
- Readiness state (konsep)
- Integration point (HTML <-> DOM/CSS/Fetch/URL)

## Batasan dan Perilaku Penting

- Model dokumen melibatkan beberapa state yang observable; detail spesifik harus mengikuti algoritma di spec.
- Banyak konsep "dokumen HTML" merujuk ke DOM Standard; di repo ini kita tautkan silang, bukan menggandakan definisi DOM.
- Beberapa perilaku bergantung pada environment (window vs worker) dan pada kebijakan keamanan; catat tautan ke rak terkait.

## Sumber Referensi

- Sumber: HTML Standard (WHATWG)
- Versi/Tanggal: 2026-03-12
- Lokasi: `document-lifecycle.html#semantics-structure-and-apis-of-html-documents` (multipage)

## Lampiran

- Diagram: `assets/overview.svg`
- Contoh: `examples/scenario-document-lifecycle.md`
