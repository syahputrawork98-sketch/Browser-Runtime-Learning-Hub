# SR-02: Memory & GC - The Orinoco Architecture

Membahas bagaimana browser mengelola alokasi memori dan proses pembersihan sampah (Garbage Collection) untuk menjaga aplikasi tetap responsif.

## 🎯 The Why (Visi Arsitektural)
Aplikasi web sering kali berumur panjang dalam tab browser. Tanpa manajemen memori yang baik, aplikasi akan menghabiskan RAM sistem secara perlahan (memory leaks) dan akhirnya menyebabkan browser crash atau lambat.

## 🏗️ The How (Arsitektur Internal)
V8 menggunakan strategi **Generational Garbage Collection** (Orinoco):
1.  **New Space**: Tempat objek baru berumur pendek (sering dibersihkan dengan Scavenging).
2.  **Old Space**: Tempat objek yang bertahan dari proses pembersihan awal (dikelola dengan Mark-Sweep-Compact).
3.  **Large Object Space**: Untuk objek yang ukurannya melebihi halaman memori standar.
4.  **Concurrent & Parallel Marking**: Proses identifikasi sampah dilakukan di background thread sehingga tidak menghentikan Main Thread (Zero-jank GC).

## 🧪 The Practical (Roadmap Buku)
- **BK-01: Heap Anatomy**: Membedah pembagian ruang memori di V8.
- **BK-02: Orinoco Deep Dive**: Mekanisme Scavenger, Major GC, dan strategi pengurangan jeda.
- **BK-03: Memory Leak Detection**: Menggunakan Chrome DevTools Memory Tab untuk melacak referensi yang bocor.

## ⚠️ The Pitfalls (Batas & Kerentanan)
- **Allocation Failures**: Mengalokasikan terlalu banyak objek besar dalam waktu singkat dapat memicu `Out of Memory` (OOM).
- **GC Thrashing**: Sering membuat dan membuang banyak objek kecil dapat memaksa GC berjalan terus-menerus, menghabiskan siklus CPU.
- **Closure Leaks**: Variabel dalam closure yang tidak sengaja tertahan akan mencegah objek besar di sekitarnya dibersihkan oleh GC.
