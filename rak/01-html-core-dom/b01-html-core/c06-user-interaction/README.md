# Bab: C06 - User Interaction

## Ringkasan

Bab ini membahas bagaimana interaksi user (klik, keyboard, pointer, fokus) mengalir melalui browser runtime: dari input device -> event dispatch -> perubahan state (focus/selection) -> dampak ke dokumen dan elemen. Fokusnya bukan UI framework, tapi mekanisme browser yang membuat interaksi menjadi perilaku yang bisa diobservasi.

## Tujuan

- Memahami alur event dari input user sampai ke DOM event handlers
- Menjelaskan konsep state yang sering berubah saat interaksi (focus, active element, selection)
- Menjadi landasan untuk topik form controls, editing, dan navigasi

## Analogi Singkat

User interaction itu seperti antrian pesan: perangkat input mengirim "pesan" (events) ke browser, lalu browser mendistribusikannya ke target yang tepat di dokumen.

## Analogi Panjang

Bayangkan sebuah sistem call center. Setiap panggilan masuk (klik, keypress, pointer movement) dicatat, diberi konteks (siapa yang menerima, di bagian mana dokumen), lalu diteruskan ke agen yang tepat (event listeners). Di saat yang sama, sistem juga memperbarui status internalnya: agen mana yang sedang aktif, antrian mana yang diprioritaskan, dan apa yang terakhir dipilih.

Di browser, interaksi user menghasilkan events. Browser melakukan hit testing untuk menentukan target, mengatur urutan dispatch (capturing/target/bubbling), memperbarui state seperti fokus dan selection, lalu menjalankan handler. Spec di bagian ini menjelaskan aturan normatif agar perilaku event dan fokus konsisten di semua browser.

## Alur Utama

1. Input user terjadi (pointer/keyboard/gesture)
2. Browser menentukan target (hit testing / fokus) dan membentuk event
3. Event di-dispatch melalui fase capturing -> target -> bubbling
4. Browser memperbarui state terkait (focus/active element/selection) bila relevan
5. Script handler berjalan dan dapat memodifikasi DOM, memicu lebih banyak events, atau memulai navigasi

## Istilah Kunci

- Event target
- Capturing / bubbling
- Focus
- Active element
- Hit testing (konsep)
- User activation (konsep)

## Batasan dan Perilaku Penting

- Interaksi user sering bergantung pada state dan security policy (mis. "user gesture" untuk membuka popup). Catat integration points jika topik melebar.
- Implementasi browser bisa berbeda pada detail UI native, tapi urutan dispatch event dan state yang observable harus mengikuti spec.
- Banyak detail eventing didefinisikan oleh DOM Standard; bab ini fokus pada bagian yang dibahas di HTML Standard dan hubungannya ke dokumen.

## Sumber Referensi

- Sumber: HTML Standard (WHATWG)
- Versi/Tanggal: 2026-03-12
- Lokasi: `interaction.html#user-interaction` (multipage)

## Lampiran

- Diagram: `assets/overview.svg`
- Contoh: `examples/scenario-click-to-event-dispatch.md`
