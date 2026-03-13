# Bab: C15 - Rendering

## Ringkasan

Bab ini membahas titik temu HTML dengan rendering pipeline: kapan DOM yang dibangun dari parsing mulai mempengaruhi tampilan, resource apa yang bisa "menghalangi" render (render-blocking), dan bagaimana browser mengoordinasikan parsing, style calculation, layout, dan paint secara bertahap. Fokusnya bukan mengajari CSS, tetapi menjelaskan mekanisme runtime yang membuat halaman tampak "muncul sedikit-sedikit" atau justru "tertahan".

## Tujuan

- Memahami hubungan DOM (hasil parsing) dengan tahap-tahap rendering (style -> layout -> paint)
- Menjelaskan konsep render-blocking dan kenapa beberapa resource menunda first render
- Menghubungkan ke rak CSS Styling dan Layout/Rendering Pipeline untuk detail lebih dalam

## Analogi Singkat

Rendering itu seperti tim panggung: naskah (DOM) sudah ada, tapi lampu (style), tata letak panggung (layout), dan pengecatan set (paint) harus siap sebelum penonton melihat hasilnya.

## Alur Utama

1. Parsing HTML membangun DOM bertahap (C13)
2. Browser mengumpulkan sumber style yang relevan (mis. stylesheet)
3. Browser menghitung style (CSSOM/style computation) untuk node DOM yang ada
4. Browser membangun struktur render yang dipakai untuk layout (konsep)
5. Layout menghitung posisi/ukuran
6. Paint dan komposit menampilkan hasil ke layar
7. Selama itu, resource tertentu dapat menunda tahap tertentu (mis. render-blocking stylesheet), sehingga pengalaman pengguna berubah

## Istilah Kunci

- DOM (hasil parsing)
- Style calculation (konsep)
- Layout (konsep)
- Paint (konsep)
- Composite (konsep)
- Render-blocking (konsep)

## Batasan dan Perilaku Penting

- Spec HTML memberi integration points, tetapi detail pipeline (kompositing, layerization, scheduling) bisa berbeda antar engine.
- Render-blocking bukan cuma "lambat", tapi "ditunda dengan sengaja" agar hasil yang tampil konsisten.
- Bab ini hanya menempatkan konsep inti; detail algoritmik ada di rak khusus rendering dan CSS.

## Sumber Referensi

- Sumber: HTML Standard (WHATWG)
- Versi/Tanggal: 2026-03-12
- Lokasi: `rendering.html#rendering` (multipage)

## Lampiran

- Diagram: `assets/overview.svg`
- Contoh: `examples/scenario-render-blocking-stylesheet.md`

