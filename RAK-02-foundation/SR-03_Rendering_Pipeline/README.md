# SR-03: Rendering Pipeline - From HTML to Pixels

Membahas aliran transformasi dari string teks (HTML/CSS) menjadi tumpukan piksel warna-warni yang dirender oleh GPU.

## 🎯 The Why (Visi Arsitektural)
Memahami Rendering Pipeline adalah kunci untuk optimasi performa visual. Tanpa pengetahuan ini, pengembang sering melakukan "Reflow" atau "Repaint" yang tidak perlu, yang menghabiskan daya baterai dan menyebabkan animasi tersendat.

## 🏗️ The How (Arsitektur Internal)
Alur kerja mesin perender (Blink) mengikuti tahapan **Critical Rendering Path**:
1.  **DOM & CSSOM Construction**: Parsing markup menjadi pohon struktur dan gaya.
2.  **Layout/Reflow**: Menghitung geometri (posisi dan ukuran) setiap elemen.
3.  **Paint**: Menggambar visual (warna, bayangan) ke dalam layer.
4.  **Composite**: Menggabungkan layer-layer menggunakan GPU untuk ditampilkan di layar.

## 🧪 The Practical (Roadmap Buku)
- **BK-01: The Layout Engine**: Bagaimana mesin menghitung geometri dan kotak (box model) secara presisi.
- **BK-02: Layers & Compositing**: Menggunakan GPU Acceleration untuk transformasi visual tanpa repaint.
- **BK-03: Visual Metrics**: Profiling performa rendering menggunakan DevTools.

## ⚠️ The Pitfalls (Batas & Kerentanan)
- **Layout Thrashing**: Membaca properti layout (misal `offsetWidth`) segera setelah menulisnya, memaksa browser melakukan layout berulang dalam satu frame.
- **Paint Storms**: Perubahan gaya kecil yang memicu repaint seluruh halaman.
- **Over-layering**: Terlalu banyak layer GPU dapat menguras memori video (VRAM) dan justru memperlambat performa.
