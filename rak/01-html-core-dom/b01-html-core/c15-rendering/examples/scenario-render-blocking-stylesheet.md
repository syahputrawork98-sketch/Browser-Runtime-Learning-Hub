# Skenario: Stylesheet Render-Blocking Membuat Halaman Terasa "Nunggu"

Tujuan: memetakan gejala runtime yang umum: DOM sudah terbentuk sebagian, tetapi first render tertahan karena stylesheet.

## Alur

1. Browser mulai parsing HTML dan membangun DOM bertahap.
2. Parser menemukan `<link rel="stylesheet" href="...">` (konsep).
3. Browser memulai fetch stylesheet.
4. Karena stylesheet mempengaruhi perhitungan style dan layout, browser menunda tahap tertentu sampai stylesheet tersedia (konsep render-blocking).
5. Setelah stylesheet didapat, browser menghitung style, melakukan layout, lalu paint.

## Hasil Yang Terlihat

- Halaman tampak putih lebih lama, lalu tiba-tiba muncul.
- Atau konten muncul tanpa style sebentar (tergantung strategi engine dan kondisi resource), lalu reflow/repaint.

## Catatan

Detail aturan persis dan optimisasi (preload scanner, scheduling, dll) dibahas di rak Networking/Fetch dan Rendering Pipeline.

