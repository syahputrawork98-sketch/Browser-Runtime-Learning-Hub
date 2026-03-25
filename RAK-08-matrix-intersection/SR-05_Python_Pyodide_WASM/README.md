# SR-05: Python Pyodide WASM - Data Science on the Web

Membahas membawa ekosistem Python yang kaya akan ilmu data (Data Science) langsung ke dalam browser melalui proyek Pyodide.

## 🎯 The Why (Visi Arsitektural)
Python adalah raja data. Pyodide memungkinkan kita menjalankan NumPy, Pandas, dan Matplotlib langsung di web tanpa perlu server Python di belakang. Ini merevolusi cara kita membangun dashboard data interaktif dan alat analisis lokal.

## 🏗️ The How (Arsitektur Internal)
Pyodide bekerja dengan cara yang unik:
1.  **Full CPython in WASM**: Seluruh interpreter Python dikompilasi ke WebAssembly.
2.  **JS-Python Proxy**: Objek yang memungkinkan pemanggilan timbal balik antara fungsi Python dan JavaScript secara transparan.
3.  **Package Management (Micropip)**: Mengunduh dan memasang paket Python langsung di memori browser.

## 🧪 The Practical (Roadmap Buku)
- **BK-01: Setting up Pyodide**: Menjalankan skrip Python pertama di browser.
- **BK-02: Data Processing with Pandas**: Analisis dataset besar di sisi klien.
- **BK-03: Visualizations with Matplotlib**: Merender grafik Python ke dalam elemen Canvas HTML.

## ⚠️ The Pitfalls (Batas & Kerentanan)
- **Huge Initial Download**: Pyodide memerlukan unduhan aset biner yang sangat besar (>10MB) sebelum aplikasi bisa mulai berjalan.
- **Slow Execution compared to Native**: Eksekusi Python di WASM masih jauh lebih lambat dibanding Python native di desktop.
- **Limited Package Support**: Tidak semua paket Python (terutama yang memiliki ekstensi C kompleks) sudah didukung oleh Pyodide.
