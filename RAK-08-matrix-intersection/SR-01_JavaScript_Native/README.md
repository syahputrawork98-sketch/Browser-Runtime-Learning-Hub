# SR-01: JavaScript Native - The Engine's Primary Citizen

Membahas hubungan mendalam antara spesifikasi ECMAScript dan implementasi konkretnya di dalam mesin V8 Browser.

## 🎯 The Why (Visi Arsitektural)
JavaScript adalah satu-satunya bahasa yang dipahami secara native oleh browser tanpa perantara. Memahami bagaimana standar bahasa (TC39) diterjemahkan menjadi eksekusi mesin di V8 adalah kunci untuk menulis kode yang tidak hanya "berjalan", tapi juga "berlari" dengan efisien.

## 🏗️ The How (Arsitektur Internal)
Integrasi native melibatkan:
1.  **Strict Compliance**: Bagaimana browser mengimplementasikan fitur baru (seperti Optional Chaining atau Nullish Coalescing).
2.  **Runtime Built-ins**: Fungsi global like `Array`, `Map`, `Set` yang ditulis di level engine untuk performa maksimal.
3.  **Strict Mode**: Mekanisme isolasi untuk mencegah perilaku error yang tidak terduga.

## 🧪 The Practical (Roadmap Buku)
- **BK-01: ECMAScript Standards Implementation**: Meninjau dukungan fitur modern di berbagai mesin browser.
- **BK-02: Native Object Performance**: Membedah performa struktur data bawaan JS di dalam V8.
- **BK-03: Strict vs Non-Strict Performance**: Mengapa kode yang "bersih" berjalan lebih cepat di mesin modern.

## ⚠️ The Pitfalls (Batas & Kerentanan)
- **Polyfill Bloat**: Menggunakan terlalu banyak polyfill untuk browser lama dapat memperlambat browser modern secara signifikan.
- **Global Scope Pollution**: Variabel global dapat merusak optimalisasi mesin dan menyebabkan tabrakan data antar skrip.
- **Inconsistent Engine Behavior**: Meskipun ada standar, detail implementasi kecil antar browser (Chrome vs Safari) masih bisa menyebabkan bug di kasus tepi (*edge cases*).
