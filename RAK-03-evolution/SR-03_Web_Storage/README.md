# SR-03: Web Storage - State & Persistence

Membahas mekanisme penyimpanan data di sisi klien untuk mendukung aplikasi yang persisten dan mampu bekerja secara offline.

## 🎯 The Why (Visi Arsitektural)
Penyimpanan di sisi klien (Client-side Storage) memungkinkan aplikasi untuk mengingat preferensi pengguna, menyimpan status login, dan bahkan berfungsi tanpa koneksi internet (Offline-first). Tanpa ini, setiap kunjungan ke situs akan terasa seperti kunjungan pertama kali.

## 🏗️ The How (Arsitektur Internal)
Terdapat berbagai jenis penyimpanan berdasarkan kegunaannya:
1.  **Cookies**: Data kecil yang dikirim ke server pada setiap permintaan (tujuan otentikasi).
2.  **Web Storage (Local/Session)**: Penyimpanan key-value sederhana untuk data non-sensitif.
3.  **IndexedDB**: Database transaksional berbasis NoSQL untuk data besar dan kompleks.
4.  **Cache API**: Digunakan oleh Service Workers untuk menyimpan sumber daya statis (Aset/HTML).

## 🧪 The Practical (Roadmap Buku)
- **BK-01: LocalStorage & SessionStorage Mastery**: Strategi penyimpanan status UI sederhana.
- **BK-02: IndexedDB Deep Dive**: Mengelola database kompleks di browser.
- **BK-03: Cookie Security & Patterns**: Mengelola sesi dengan aman menggunakan atribut HttpOnly/Secure.

## ⚠️ The Pitfalls (Batas & Kerentanan)
- **Storage Limits**: Setiap browser memiliki batas kapasitas penyimpanan yang berbeda; melebihi batas ini dapat menyebabkan kegagalan aplikasi.
- **XSS Attacks**: Data yang disimpan di LocalStorage rentan dicuri jika aplikasi memiliki celah Cross-Site Scripting.
- **Data Inconsistency**: Tanpa mekanisme sinkronisasi yang baik, data di browser bisa menjadi usang (*stale*) dibanding data di server.
