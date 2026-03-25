# SR-02: Network APIs - The External Gateway

Membahas berbagai protokol dan API yang memungkinkan browser berkomunikasi dengan server dan sumber daya eksternal.

## 🎯 The Why (Visi Arsitektural)
Aplikasi web modern bergantung pada data dinamis. Memahami bagaimana browser mengelola permintaan jaringan (Network Requests) sangat penting untuk membangun aplikasi yang cepat, andal, dan mampu menangani kondisi jaringan yang buruk.

## 🏗️ The How (Arsitektur Internal)
Browser menyediakan beberapa lapisan komunikasi:
1.  **XMLHttpRequest (XHR)**: Standar lama untuk permintaan asinkron (AJAX).
2.  **Fetch API**: Standar modern berbasis Promise yang lebih bersih dan fleksibel.
3.  **WebSockets (WS)**: Komunikasi dua arah (full-duplex) secara real-time.
4.  **CORS & Security**: Mekanisme browser untuk melindungi pengguna dari permintaan lintas domain yang berbahaya.

## 🧪 The Practical (Roadmap Buku)
- **BK-01: Fetch & Error Handling**: Menguasai pengambilan data dengan pola asinkron modern.
- **BK-02: Real-time with WebSockets**: Membangun saluran komunikasi dua arah.
- **BK-03: Network Interceptors & Service Workers**: Mengontrol permintaan jaringan di tingkat browser.

## ⚠️ The Pitfalls (Batas & Kerentanan)
- **Network Latency**: Mengabaikan waktu tunggu jaringan dapat merusak pengalaman pengguna jika tidak ditangani dengan *loading states*.
- **CORS Headaches**: Konfigurasi server yang salah sering menjadi penghalang utama dalam integrasi API.
- **Payload Bloat**: Mengambil data terlalu besar dapat menghabiskan kuota pengguna dan memperlambat render halaman.
