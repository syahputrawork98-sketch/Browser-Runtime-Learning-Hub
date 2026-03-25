# SR-02: Profiling & Optimization - Performance Engineering

Membahas metodologi ilmiah untuk mengukur, menganalisis, dan meningkatkan performa aplikasi melalui alat profiling mendalam.

## 🎯 The Why (Visi Arsitektural)
Performa bukan sebuah kebetulan, melainkan hasil rekayasa. Di dunia yang sangat kompetitif, kelambatan milidetik dapat berarti kehilangan pengguna. Profiling memungkinkan kita menemukan bottleneck yang tepat alih-alih melakukan optimasi prematur yang sia-sia.

## 🏗️ The How (Arsitektur Internal)
Proses profiling di browser mencakup:
1.  **CPU Profiling**: Rekaman tumpukan panggilan fungsi (Flame Charts) untuk melihat fungsi mana yang paling banyak menghabiskan waktu.
2.  **Memory Snapshots**: Mengambil potret penggunaan heap untuk mencari objek yang tidak terpakai (Unused Objects).
3.  **Timeline Monitoring**: Melacak jeda rendering (Long Tasks) dan interaksi pengguna.

## 🧪 The Practical (Roadmap Buku)
- **BK-01: Performance Tab Mastery**: Membaca Flame Charts dan identifikasi "Long Tasks".
- **BK-02: Memory Profiling & Analysis**: Mencari kebocoran memori menggunakan Comparison View.
- **BK-03: Auditing with Lighthouse**: Menggabungkan metrik teknis dengan indikator bisnis (Core Web Vitals).

## ⚠️ The Pitfalls (Batas & Kerentanan)
- **Premature Optimization**: Mengoptimalkan bagian kode yang jarang dijalankan tanpa data profiling yang valid.
- **Ignoring Low-end Devices**: Profiling hanya di laptop high-end tidak akan menunjukkan masalah yang dialami pengguna dengan perangkat terbatas.
- **Data Noise**: Terlalu banyak tab browser atau ekstensi yang berjalan dapat merusak akurasi data profiling.
