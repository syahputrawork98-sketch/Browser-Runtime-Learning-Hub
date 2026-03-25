# SR-02: Background Tasks - The Service Worker Ecosystem

Membahas kemampuannya browser untuk menjalankan tugas di latar belakang, bahkan saat halaman web sedang tidak dibuka oleh pengguna.

## 🎯 The Why (Visi Arsitektural)
Service Workers adalah fondasi dari Progressive Web Apps (PWA). Mereka memberikan kemampuan layaknya aplikasi native (Offline-first, Push Notifications, Background Sync) pada web, memungkinkan aplikasi tetap berguna tanpa koneksi internet atau interaksi pengguna aktif.

## 🏗️ The How (Arsitektur Internal)
Service Worker bekerja sebagai proksi jaringan yang persisten:
1.  **Registration & Lifecycle**: Alur instalasi, aktivasi, dan pembaharuan SW secara independen dari siklus hidup tab.
2.  **Fetch Interception**: Kemampuan untuk mencegat permintaan jaringan dan menyajikannya dari Cache API.
3.  **Push API & Notification**: Komunikasi server-ke-browser yang tetap aktif melalui sistem notifikasi OS.
4.  **Background Sync API**: Menunda tindakan (misal: kirim pesan) hingga koneksi internet tersedia kembali.

## 🧪 The Practical (Roadmap Buku)
- **BK-01: Offline-First Strategy**: Implementasi strategi caching (Stale-While-Revalidate, Cache-First).
- **BK-02: Push Notifications & Messaging**: Mengirim dan menerima pesan di latar belakang.
- **BK-03: Background Sync & Periodic Sync**: Menjaga data tetap segar di latar belakang tanpa menguras baterai.

## ⚠️ The Pitfalls (Batas & Kerentanan)
- **Caching Bugs**: Kesalahan strategi caching dapat menyebabkan pengguna terjebak dengan versi aplikasi yang lama selamanya (Zombie SW).
- **HTTPS Mandatory**: Service Workers hanya berfungsi pada lingkungan aman (HTTPS/localhost).
- **No Persistent State**: Service Worker bisa dimatikan oleh browser kapan saja untuk menghemat sumber daya; status penting tidak boleh disimpan di memori variabel SW.
