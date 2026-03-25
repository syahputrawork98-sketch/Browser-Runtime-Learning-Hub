# SR-01: DOM & CSSOM - The Structural Evolution

Membahas bagaimana browser membangun representasi internal dari dokumen web dan bagaimana ia berevolusi untuk mendukung aplikasi dinamis.

## 🎯 The Why (Visi Arsitektural)
DOM (Document Object Model) dan CSSOM (CSS Object Model) adalah antarmuka utama yang memungkinkan kode (JS) berinteraksi dengan struktur visual. Tanpa sinkronisasi yang baik antara keduanya, pembaruan UI akan menjadi lambat dan tidak konsisten, terutama pada aplikasi skala besar.

## 🏗️ The How (Arsitektur Internal)
Proses ini melibatkan transformasi data mentah menjadi pohon objek:
1.  **DOM Tree**: Hasil parsing HTML menjadi node-node yang saling berhubungan.
2.  **CSSOM Tree**: Hasil parsing CSS yang menentukan gaya untuk setiap node.
3.  **Render Tree**: Gabungan DOM dan CSSOM (hanya menyertakan elemen yang terlihat) yang siap dikirim ke pipeline layout.

## 🧪 The Practical (Roadmap Buku)
- **BK-01: DOM Mutation Mastery**: Strategi manipulasi DOM yang efisien tanpa memicu reflow berlebih.
- **BK-02: CSSOM & Computed Styles**: Bagaimana browser menghitung gaya final yang diwariskan.
- **BK-03: Shadow DOM & Encapsulation**: Isolasi komponen UI dalam pengembangan modular.

## ⚠️ The Pitfalls (Batas & Kerentanan)
- **Extensive DOM Depth**: Pohon DOM yang terlalu dalam (elemen bersarang berlebihan) memperlambat setiap operasi akses dan gaya.
- **Zombie Nodes**: Elemen DOM yang dihapus dari tampilan tetapi masih tertahan oleh referensi JavaScript (kebocoran memori).
- **Selector Performance**: Selector CSS yang terlalu kompleks atau bersifat universal (`*`) memaksa browser melakukan pencarian rekursif yang mahal.
