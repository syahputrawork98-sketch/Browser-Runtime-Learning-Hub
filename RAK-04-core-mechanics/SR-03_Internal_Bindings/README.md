# SR-03: Internal Bindings - The Engine Bridge

Membahas bagaimana V8 (JavaScript) berkomunikasi dengan mesin perender Blink (C++) secara internal.

## 🎯 The Why (Visi Arsitektural)
V8 hanyalah mesin eksekusi logika. Segala hal visual (menggambar kotak, memutar video) dilakukan oleh Blink. Tanpa jembatan bindings yang efisien, komunikasi antara keduanya akan menjadi lambat dan menghancurkan interaktivitas aplikasi.

## 🏗️ The How (Arsitektur Internal)
Mekanisme ini ditenagai oleh **V8 Bindings Generator**:
1.  **IDL (Interface Definition Language)**: Definisi antarmuka Web API yang standard.
2.  **Glue Code**: Kode C++ yang secara otomatis dihasilkan untuk menjembatani panggilan fungsi dari JS ke implementasi internal Blink.
3.  **Object Wrapping**: Bagaimana objek JavaScript (seperti `HTMLDivElement`) mewakili objek C++ di balik layar.

## 🧪 The Practical (Roadmap Buku)
- **BK-01: V8 API & Contexts**: Membedah bagaimana V8 Isolate dan Context dikelola.
- **BK-02: Web API Implementations**: Bagaimana `Window` dan `Document` diimplementasikan di sisi C++.
- **BK-03: IPC (Inter-Process Communication)**: Bagaimana instruksi dikirimkan antar proses browser (Mojo IPC).

## ⚠️ The Pitfalls (Batas & Kerentanan)
- **Crossing the Bridge Overhead**: Memanggil API DOM ribuan kali dalam loop sangat mahal karena biaya komunikasi antara dunia JS dan C++.
- **Security Scoping**: Bug pada bindings seringkali menjadi pintu masuk serangan (sandbox escape).
- **Strict Typing Mismatch**: Kesalahan tipe data saat passing argumen ke Web API dapat memicu error internal yang sulit didebug.
