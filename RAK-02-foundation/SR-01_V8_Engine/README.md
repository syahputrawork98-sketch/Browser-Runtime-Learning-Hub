# SR-01: V8 Engine - The Heart of Execution

Membahas mekanisme internal V8 dalam memproses JavaScript di sisi klien, dari kode sumber hingga eksekusi mesin tingkat tinggi.

## 🎯 The Why (Visi Arsitektural)
V8 bukan sekadar interpreter, melainkan mesin kompilasi JIT (Just-In-Time) yang memungkinkan JavaScript berjalan hampir secepat kode native. Tanpa V8, aplikasi web modern yang kompleks (seperti Editor foto online atau Google Maps) tidak akan mungkin terjadi karena keterbatasan performa eksekusi.

## 🏗️ The How (Arsitektur Internal)
Secara garis besar, V8 bekerja melalui saluran pipa (*pipeline*) berikut:
1.  **Ignition (Interpreter)**: Mengonversi kode JS menjadi bytecode cepat untuk eksekusi awal.
2.  **TurboFan (Optimizing Compiler)**: Mengambil data profil dari Ignition untuk mengompilasi ulang bagian kode yang "panas" (sering dijalankan) menjadi kode mesin yang dioptimalkan secara ekstrem.
3.  **Orinoco (Garbage Collector)**: Mengelola alokasi memori secara paralel dan asinkron untuk meminimalkan jeda UI (*jank*).

## 🧪 The Practical (Roadmap Buku)
Fungsi Sub-Rack ini adalah rumah bagi buku-buku teknis berikut:
- **BK-01: JIT Pipeline Mastery**: Membedah detail Ignition, TurboFan, dan Maglev.
- **BK-02: Memory & GC Architecture**: Strategi alokasi Heap, Stack, dan mekanisme Scavenging/Major GC.
- **BK-03: V8 Hidden Classes & Inline Caching**: Bagaimana V8 merekayasa struktur objek dinamis untuk performa statis.

## ⚠️ The Pitfalls (Batas & Kerentanan)
- **De-optimization Hell**: Menulis kode yang berubah tipe datanya secara dinamis dapat memaksa TurboFan membuang optimasi dan kembali ke Ignition (lambat).
- **Hidden Class Mutations**: Menambahkan properti objek secara acak merusak optimalisasi memori V8.
- **Memory Leaks**: Penutupan (*closures*) yang tidak tepat dapat menahan referensi objek besar selamanya.
