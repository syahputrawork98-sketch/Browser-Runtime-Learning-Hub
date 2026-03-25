# SR-03: Rust WASM Bridge - Systems Power in the Browser

Membahas integrasi antara Rust (bahasa sistem) dan Browser melalui WebAssembly untuk performa dan keamanan memori tingkat tinggi.

## 🎯 The Why (Visi Arsitektural)
Rust menawarkan performa mentah tanpa Garbage Collector. Melalui WASM, kita bisa membawa pustaka Rust yang hebat ke web, menjanjikan kecepatan aplikasi native dengan keamanan yang tak tertandingi oleh JavaScript murni.

## 🏗️ The How (Arsitektur Internal)
Jembatan ini dibangun di atas:
1.  **Wasm-bindgen**: Alat yang secara otomatis menghasilkan "lem" (glue code) JavaScript untuk memanggil fungsi Rust.
2.  **Wasm-pack**: Alur kerja build profesional untuk mengemas kode Rust menjadi paket NPM.
3.  **Direct Memory Access**: Bagaimana Rust mengelola memori linier di dalam sandbox WASM.

## 🧪 The Practical (Roadmap Buku)
- **BK-01: Rust-WASM Toolchain Essentials**: Menyiapkan lingkungan pengembangan Rust untuk Web.
- **BK-02: Struct & Function Interop**: Bagaimana mengirimkan objek kompleks antara Rust dan JS.
- **BK-03: Real-world Use Cases**: Implementasi algoritma berat (seperti kompresi atau kriptografi) di browser.

## ⚠️ The Pitfalls (Batas & Kerentanan)
- **Serialized Objects Performance**: Mengonversi objek besar menjadi JSON atau biner saat melewati jembatan JS-Rust bisa menjadi sangat lambat jika terlalu sering dilakukan.
- **Code Size Bloat**: Pustaka Rust yang besar dapat menghasilkan file `.wasm` berukuran megabyte yang memperlambat waktu muat halaman.
- **Debugging Complexity**: Menelusuri error di dalam WebAssembly jauh lebih sulit dibandingkan debugging JavaScript biasa.
