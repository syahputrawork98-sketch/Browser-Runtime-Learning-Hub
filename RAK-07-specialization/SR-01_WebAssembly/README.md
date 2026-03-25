# SR-01: WebAssembly - The High-Performance Sandbox

Membahas bagaimana menjalankan kode tingkat rendah (Low-level) di browser untuk mencapai performa komputasi yang mendekati native.

## 🎯 The Why (Visi Arsitektural)
Meskipun JavaScript sangat cepat, ia memiliki batasan performa karena sifat dinamisnya. WebAssembly (WASM) memberikan alternatif biner yang didesain untuk kecepatan maksimal, memungkinkan aplikasi seperti video editing, game 3D, dan simulasi fisika berjalan dengan performa tinggi langsung di web.

## 🏗️ The How (Arsitektur Internal)
WASM adalah format instruksi biner yang berjalan di mesin yang sama dengan JavaScript:
1.  **Compact Binary Format**: Format data kecil yang dapat diunduh dan diparsing jauh lebih cepat daripada teks JS.
2.  **Linear Memory**: Ruang memori biner yang efisien dan dapat diakses bersama oleh JS dan WASM.
3.  **Sandbox Isolation**: WASM berjalan di lingkungan yang terisolasi ketat demi keamanan sistem pengguna.
4.  **Language Interop**: Bagaimana Rust, C++, atau Go dikompilasi menjadi modul `.wasm`.

## 🧪 The Practical (Roadmap Buku)
- **BK-01: Rust to WASM Mastery**: Membangun algoritma performa tinggi dengan Rust dan `wasm-bindgen`.
- **BK-02: WASM Performance Profiling**: Mengidentifikasi keuntungan performa WASM dibanding JS pada kasus spesifik.
- **BK-03: Shared Memory Interop**: Komunikasi data besar antar JS dan WASM tanpa overhead.

## ⚠️ The Pitfalls (Batas & Kerentanan)
- **JS-WASM Bridge Cost**: Memanggil fungsi WASM dari JS memiliki biaya komunikasi kecil; jika fungsi WASM terlalu kecil, overhead pemanggilan bisa melampaui keuntungan performanya.
- **No Direct DOM Access**: WASM tidak bisa menyentuh DOM secara langsung; ia harus meminta bantuan JavaScript untuk segala hal yang bersifat visual.
- **Instruction Set Limits**: WASM belum mendukung semua fitur CPU secara penuh (seperti SIMD tingkat lanjut atau Threads di semua browser).
