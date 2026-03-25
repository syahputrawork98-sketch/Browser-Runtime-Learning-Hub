# SR-04: Go WASM Interop - Cloud Skills on the Web

Membahas penggunaan bahasa Go di dalam browser melalui WebAssembly, memungkinkan portabilitas logika server ke sisi klien.

## 🎯 The Why (Visi Arsitektural)
Go sangat populer untuk logika bisnis dan mikrolayanan. Dengan WASM, kita bisa menggunakan kembali (re-use) logika validasi atau algoritma yang sama di server dan browser sekaligus, menjamin konsistensi sistem tanpa duplikasi kode.

## 🏗️ The How (Arsitektur Internal)
Integrasi Go melibatkan:
1.  **Syscall JS Package**: Pustaka standar Go untuk berinteraksi langsung dengan lingkungan DOM/JS browser.
2.  **WASM Exec Runtime**: Skrip JS pendukung (`wasm_exec.js`) yang disediakan oleh Go untuk menjalankan modul binernya.
3.  **Goroutines in Browser**: Bagaimana penjadwal (scheduler) Go berjalan di atas single-threaded JavaScript.

## 🧪 The Practical (Roadmap Buku)
- **BK-01: Go WASM Compilation**: Mengompilasi kode Go menjadi `.wasm`.
- **BK-02: DOM Manipulation from Go**: Mengontrol elemen web langsung dari kode Go.
- **BK-03: Shared Logic Patterns**: Berbagi kode (shared packages) antara backend Go dan frontend WASM.

## ⚠️ The Pitfalls (Batas & Kerentanan)
- **Binary Size (The MVP Trap)**: Ukuran biner WASM hasil kompilasi Go secara default sangat besar (minimal ~2MB untuk "Hello World") karena menyertakan runtime Go yang lengkap.
- **Blocking the Main Thread**: Tanpa penanganan hati-hati, fungsi Go yang sinkron dapat menghentikan Event Loop browser.
- **Pointers in JS Space**: Mengelola pointer Go di dalam lingkungan dinamis JavaScript memerlukan kehati-hatian ekstra agar tidak crash.
