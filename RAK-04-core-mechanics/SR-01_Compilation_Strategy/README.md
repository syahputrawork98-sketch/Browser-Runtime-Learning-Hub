# SR-01: Compilation Strategy - The Speed of Light

Membahas bagaimana V8 mengubah kode JavaScript yang dinamis menjadi instruksi mesin yang sangat cepat melalui strategi kompilasi bertingkat.

## 🎯 The Why (Visi Arsitektural)
JavaScript adalah bahasa tingkat tinggi yang dinamis. Tanpa strategi kompilasi yang cerdas, JS akan berjalan sangat lambat karena harus diinterpretasikan setiap saat. Strategi JIT (Just-In-Time) adalah kunci mengapa web modern bisa secepat aplikasi desktop native.

## 🏗️ The How (Arsitektur Internal)
V8 menggunakan pipeline kompilasi multi-tahap (Multi-tier compilation):
1.  **Ignition**: Interpreter yang menghasilkan bytecode dengan konsumsi memori rendah untuk eksekusi cepat di awal.
2.  **Sparkplug**: Kompiler non-optimizing yang sangat cepat untuk mempercepat eksekusi tanpa menunggu optimasi berat.
3.  **TurboFan**: Kompiler optimasi tingkat tinggi yang menggunakan profil data dari Ignition untuk menghasilkan kode mesin yang sangat efisien.
4.  **Maglev**: Lapisan tengah baru (Tier-2) yang dirancang untuk mengisi celah antara Sparkplug dan TurboFan.

## 🧪 The Practical (Roadmap Buku)
- **BK-01: Bytecode & Ignition**: Membedah struktur instruksi bytecode V8.
- **BK-02: TurboFan Optimization Pipeline**: Bagaimana feedback loops digunakan untuk optimasi tipe data.
- **BK-03: Tiering Strategies**: Memahami kapan dan mengapa V8 memutuskan untuk mengompilasi ulang kode.

## ⚠️ The Pitfalls (Batas & Kerentanan)
- **Bailout / De-optimization**: Jika asumsi tipe data TurboFan salah (misal: variabel tiba-tiba berubah dari `Integer` ke `String`), V8 akan membuang kode mesin yang dioptimalkan dan kembali ke bytecode (sangat lambat).
- **Function Size Overdose**: Fungsi yang terlalu besar seringkali gagal dioptimalkan oleh TurboFan.
- **Micro-benchmarking Trap**: Menguji potongan kode kecil tanpa memahami fase pemanasan JIT dapat memberikan hasil yang menyesatkan.
