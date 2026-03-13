# Bab: C16 - Obsolete Features

## Ringkasan

Bab ini membahas "obsolete features" dari sisi runtime browser: kenapa sebagian fitur lama masih ada di spec (sebagai dokumentasi interoperabilitas), bagaimana browser tetap mem-parsing dan membangun DOM untuk markup legacy, dan apa dampaknya pada rendering, aksesibilitas, serta keamanan/performa. Fokusnya bukan nostalgia tag lama, melainkan cara browser mempertahankan kompatibilitas web tanpa mendorong penggunaan fitur tersebut.

## Tujuan

- Memahami peran bab obsolete: dokumentasi perilaku yang masih ditemui di web
- Menjelaskan efek runtime: parsing masih menerima, DOM masih terbentuk, rendering/semantik bisa berbeda
- Membantu membuat keputusan engineering: kapan harus refactor, kapan cukup mitigasi

## Analogi Singkat

Obsolete features itu seperti adaptor lama yang masih disediakan karena banyak perangkat lama di lapangan, tapi bukan rekomendasi untuk dipakai di instalasi baru.

## Alur Utama

1. Browser mem-parsing HTML (C13) dan tetap mengenali markup legacy
2. DOM dibangun seperti biasa, sering kali dengan mapping rendering/semantik yang sudah "dibekukan" demi kompatibilitas
3. Tooling modern (lint, accessibility audit, CSP, dll) biasanya memberi sinyal bahwa ini tidak disarankan
4. Pada runtime, isu yang sering muncul: layout/rendering sulit diprediksi karena perilaku legacy (konsep)
5. Isu lain yang sering muncul: semantik/accessibility yang buruk (konsep)
6. Biaya maintenance naik karena harus menambah workaround saat bercampur dengan modern HTML/CSS (konsep)

## Istilah Kunci

- Obsolete (konsep)
- Legacy markup (konsep)
- Backward compatibility (konsep)
- Rendering mapping (konsep)
- A11y (konsep)

## Batasan dan Perilaku Penting

- "Obsolete" tidak selalu berarti "tidak bekerja"; seringnya tetap bekerja untuk kompatibilitas.
- Browser bisa berbeda dalam detail minor, tetapi arah besarnya sama: mendukung untuk web lama, bukan untuk web baru.
- Bab ini jadi rujukan saat menemukan markup lawas di codebase atau konten pihak ketiga.

## Sumber Referensi

- Sumber: HTML Standard (WHATWG)
- Versi/Tanggal: 2026-03-12
- Lokasi: `obsolete.html#obsolete` (multipage)

## Lampiran

- Diagram: `assets/overview.svg`
- Contoh: `examples/scenario-legacy-markup-in-modern-page.md`
