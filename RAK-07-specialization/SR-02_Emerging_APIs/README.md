# SR-02: Emerging APIs - The Future of the Web

Membahas antarmuka baru dan eksperimental yang memberikan browser kekuatan untuk berinteraksi lebih dalam dengan perangkat keras.

## 🎯 The Why (Visi Arsitektural)
Web Platform terus berevolusi untuk menutupi celah dengan aplikasi native desktop. API baru memungkinkan kita mengakses GPU secara langsung, berkomunikasi dengan perangkat USB, atau mengelola berkas lokal secara profesional tanpa batasan sandbox tradisional yang kaku.

## 🏗️ The How (Arsitektur Internal)
API Masa Depan ini mencakup:
1.  **WebGPU**: Akses rendah tingkat ke kartu grafis untuk rendering dan komputasi (penerus WebGL).
2.  **File System Access API**: Izin baca/tulis berkas langsung di komputer pengguna (untuk editor teks/gambar).
3.  **WebUSB / WebBluetooth**: Komunikasi langsung dengan perangkat keras fisik eksternal.
4.  **WebHID**: Berhubungan dengan perangkat input khusus seperti gamepad atau instrumen musik.

## 🧪 The Practical (Roadmap Buku)
- **BK-01: WebGPU Architecture**: Memahami pipeline grafis modern dan shader (WGSL).
- **BK-02: Local File Management**: Membangun aplikasi "Desktop-class" yang mengelola folder pengguna secara aman.
- **BK-03: Hardware InterFacing**: Integrasi browser dengan perangkat fisik menggunakan USB/Bluetooth.

## ⚠️ The Pitfalls (Batas & Kerentanan)
- **Browser Compatibility**: Fitur-fitur ini seringkali hanya tersedia di keluarga Chrome/Chromium dan belum didukung secara universal.
- **User Privacy Risks**: Akses perangkat keras memiliki risiko keamanan tinggi; browser memberlakukan sistem izin (Permissions) yang sangat ketat.
- **API Volatility**: Karena masih bersifat "Emerging", spesifikasi API dapat berubah sewaktu-waktu dan mematahkan kode lama.
