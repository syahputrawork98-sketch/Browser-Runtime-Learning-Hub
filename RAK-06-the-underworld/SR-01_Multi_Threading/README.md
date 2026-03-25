# SR-01: Multi-Threading - Parallel Execution in CSS/JS

Membahas bagaimana browser mengatasi batasan single-thread melalui Web Workers dan mekanisme berbagi memori yang aman.

## 🎯 The Why (Visi Arsitektural)
Aplikasi modern seringkali harus melakukan kalkulasi berat (misal: pengolahan citra atau enkripsi) tanpa menghentikan kelancaran UI (60FPS). Multi-threading di browser memungkinkan kita memindahkan beban kerja tersebut ke thread latar belakang, menjaga agar tab tetap responsif.

## 🏗️ The How (Arsitektur Internal)
Multi-threading di browser dikelola melalui isolasi ketat:
1.  **Web Workers**: Thread terpisah yang memiliki Isolate V8 sendiri (tanpa akses langsung ke DOM).
2.  **Message Passing (PostMessage)**: Komunikasi antar thread melalui pengiriman pesan (salinan data).
3.  **Shared Memory (SharedArrayBuffer)**: Memori yang dapat diakses langsung oleh beberapa thread secara bersamaan.
4.  **Atomics**: Operasi tingkat rendah untuk mencegah "Race Conditions" saat mengakses SharedArrayBuffer.

## 🧪 The Practical (Roadmap Buku)
- **BK-01: Web Workers Lifecycle**: Memulai, mengelola, dan mematikan thread pekerja secara efisien.
- **BK-02: Transferable Objects**: Mengirimkan data besar (misal `ArrayBuffer`) antar thread tanpa biaya penyalinan (zero-copy).
- **BK-03: Shared Memory Architecture**: Implementasi sinkronisasi data antar thread menggunakan Atomics.

## ⚠️ The Pitfalls (Batas & Kerentanan)
- **Deadlocks & Race Conditions**: Kesalahan sinkronisasi pada Shared Memory dapat mengakibatkan crash atau data korup yang sulit dideteksi.
- **No DOM Access**: Mencoba mengakses elemen UI dari dalam Worker akan menyebabkan error seketika; semua manipulasi visual harus tetap di Main Thread.
- **Worker Overhead**: Menjalankan terlalu banyak Worker secara bersamaan dapat menghabiskan memori perangkat, terutama pada ponsel dengan spesifikasi rendah.
