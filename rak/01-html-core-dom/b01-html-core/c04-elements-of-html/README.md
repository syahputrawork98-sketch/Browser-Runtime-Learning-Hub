# Bab: C04 - The Elements of HTML

## Ringkasan

Bab ini membahas elemen HTML dari sisi runtime browser: bagaimana elemen direpresentasikan sebagai node DOM, bagaimana aturan-aturan di spec menentukan perilaku elemen, dan bagaimana elemen berinteraksi dengan parsing, rendering, dan scripting.

## Tujuan

- Memahami elemen sebagai "unit perilaku" (bukan sekadar tag)
- Menghubungkan definisi elemen di HTML Standard dengan DOM tree dan rendering
- Menjadi pengantar sebelum masuk ke detail parsing (C13) dan rendering (C15)

## Analogi Singkat

Elemen HTML itu seperti komponen di sebuah sistem: bentuknya terlihat sederhana, tapi tiap komponen punya state, aturan, dan efek samping yang bisa mempengaruhi sistem lain.

## Analogi Panjang

Bayangkan kamu merakit sebuah mesin dari banyak komponen. Ada komponen yang hanya "wadah", ada yang mengubah perilaku aliran (misalnya valve), ada yang memicu aksi (tombol), dan ada yang menyimpan data (sensor). Di HTML, elemen punya peran yang mirip: beberapa hanya menstrukturkan dokumen, beberapa memicu loading resource, beberapa berinteraksi dengan user input, dan sebagian punya state internal.

Spec menjelaskan aturan normatif setiap elemen: kapan elemen dianggap valid, bagaimana elemen mempengaruhi parsing dan DOM, dan apa konsekuensi perilakunya di browser. Repo ini merangkum aturan-aturan itu dengan fokus ke cara kerja browser runtime.

## Alur Utama

1. Elemen dibuat saat parsing (atau lewat API) dan masuk ke DOM tree
2. Elemen dapat memicu side effects (mis. discovery resource, perubahan state form, event)
3. Elemen ikut mempengaruhi rendering (semantics -> style/layout) melalui integration points
4. Script berinteraksi dengan elemen melalui DOM APIs dan event

## Istilah Kunci

- Element
- DOM node
- Custom element (konteks)
- Content model (konsep)
- Global attributes
- Side effects (resource discovery, state changes)

## Batasan dan Perilaku Penting

- Perilaku elemen ditentukan algoritma di spec; implementasi browser bisa berbeda dalam optimisasi, tetapi hasil observable harus konsisten.
- Banyak detail elemen terkait rendering dan UI native; kita catat yang relevan dan tautkan ke bab rendering/CSS bila perlu.
- Beberapa elemen mempengaruhi loading/parsing (mis. script/style/link); detailnya akan diperdalam di bab parsing dan loading.

## Sumber Referensi

- Sumber: HTML Standard (WHATWG)
- Versi/Tanggal: 2026-03-12
- Lokasi: `semantics.html#semantics` (multipage)

## Lampiran

- Diagram: `assets/overview.svg`
- Contoh: `examples/scenario-element-side-effects.md`
