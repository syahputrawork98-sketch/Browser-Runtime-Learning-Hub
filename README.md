# Browser Runtime Knowledge Base

Repositori ini adalah **basis pengetahuan terstruktur** untuk memahami **bagaimana JavaScript berjalan di dalam browser**.

Repositori ini disusun seperti **sebuah perpustakaan pembelajaran**, di mana konsep-konsep dikelompokkan ke dalam **sub-rak (domain)** dan **buku (topik)**.
Tujuannya adalah membangun **model mental yang jelas tentang sistem runtime browser**, mulai dari arsitektur browser hingga proses rendering.

Proyek ini dirancang sebagai **dokumentasi yang hidup (living documentation)** yang dapat terus berkembang seiring perubahan teknologi browser.

---

# Tujuan

Aplikasi web modern sangat bergantung pada **lingkungan runtime browser**.
Namun memahami bagaimana JavaScript benar-benar berjalan di dalam browser membutuhkan pemahaman dari berbagai sistem yang saling berkaitan.

Basis pengetahuan ini bertujuan menjelaskan:

* bagaimana browser disusun secara arsitektural
* bagaimana JavaScript engine bekerja
* bagaimana memori dikelola
* bagaimana eksekusi asynchronous terjadi
* bagaimana runtime berinteraksi dengan sistem browser
* bagaimana proses rendering terjadi

Tujuan akhirnya adalah membangun **pemahaman menyeluruh tentang cara kerja runtime browser**.

---

# Ruang Lingkup

Repositori ini berfokus khusus pada **runtime JavaScript di dalam browser**.

Topik yang dibahas meliputi:

* Arsitektur browser
* JavaScript engine
* Sistem memori
* Model eksekusi JavaScript
* Scheduling dan koordinasi runtime
* Rendering pipeline

Repositori ini **tidak bertujuan mendokumentasikan seluruh Web APIs** secara lengkap.

Web APIs dipisahkan karena ruang lingkupnya sangat luas dan lebih cocok didokumentasikan dalam repositori atau sistem dokumentasi tersendiri.

---

# Struktur Repositori

Repositori ini disusun seperti **struktur perpustakaan**.

```
Browser Runtime Knowledge Base
│
├─ Sub-rak 1 — Browser Architecture
│
├─ Sub-rak 2 — JavaScript Engine
│
├─ Sub-rak 3 — Memory System
│
├─ Sub-rak 4 — Web APIs
│
├─ Sub-rak 5 — Execution Model
│
├─ Sub-rak 6 — Scheduling & Runtime Interaction
│
└─ Sub-rak 7 — Rendering System
```

Setiap **sub-rak** mewakili satu domain utama dalam runtime browser.

Setiap **buku** di dalam sub-rak membahas satu konsep spesifik secara lebih mendalam.

---

# Sub-Rak

## 1. Browser Architecture

Menjelaskan arsitektur dasar browser modern.

Topik yang dibahas:

* Web Platform Overview
* Browser Architecture
* Browser Processes
* Browser Threads

---

## 2. JavaScript Engine

Menjelaskan bagaimana kode JavaScript diproses dan dijalankan.

Topik yang dibahas:

* JavaScript Engine Overview
* Parsing & Compilation
* Execution Context
* Call Stack

---

## 3. Memory System

Menjelaskan bagaimana memori dikelola dalam runtime JavaScript.

Topik yang dibahas:

* Memory Model
* Garbage Collection

---

## 4. Web APIs

Menjelaskan sistem browser yang dapat diakses oleh JavaScript.

Topik yang dibahas:

* DOM APIs
* Fetch & Network APIs
* Timers API
* Web Workers

---

## 5. Execution Model

Menjelaskan bagaimana eksekusi JavaScript dikoordinasikan.

Topik yang dibahas:

* Event Loop
* Task Queue
* Microtask Queue
* Asynchronous Execution Model

---

## 6. Scheduling & Runtime Interaction

Menjelaskan bagaimana browser menjadwalkan dan mengoordinasikan berbagai proses runtime.

Topik yang dibahas:

* Timers & Scheduling
* Runtime Interaction with Browser Systems

---

## 7. Rendering System

Menjelaskan bagaimana operasi runtime akhirnya menghasilkan tampilan visual di layar.

Topik yang dibahas:

* Rendering Pipeline
* Runtime Performance

---

# Alur Pembelajaran

Urutan pembelajaran yang direkomendasikan mengikuti **alur alami bagaimana JavaScript berjalan di dalam browser**:

```
Browser Architecture
        ↓
JavaScript Engine
        ↓
Memory System
        ↓
Web APIs
        ↓
Execution Model
        ↓
Scheduling
        ↓
Rendering
```

Urutan ini membantu membangun pemahaman bertahap tentang **siklus hidup eksekusi JavaScript di browser**.

---

# Living Knowledge Base

Repositori ini dirancang sebagai **basis pengetahuan yang terus berkembang**.

Setiap topik diharapkan memuat:

* penjelasan konsep
* referensi ke spesifikasi resmi
* sumber pembelajaran tambahan
* tanggal peninjauan atau pembaruan jika diperlukan

Jika standar browser atau implementasi engine berubah, dokumentasi di repositori ini juga dapat diperbarui mengikuti perkembangan tersebut.

---

# Sumber Referensi

Sumber utama yang digunakan dalam basis pengetahuan ini antara lain:

* WHATWG Specifications
* W3C Specifications
* Dokumentasi Chromium
* Dokumentasi V8
* MDN Web Docs
* Blog engineering resmi dari vendor browser

Jika memungkinkan, setiap penjelasan konsep sebaiknya merujuk pada **spesifikasi atau dokumentasi implementasi resmi**.

---

# Panduan Kontribusi

Untuk menjaga kualitas dokumentasi:

* Setiap topik sebaiknya menyertakan **sumber referensi yang jelas**
* Penjelasan difokuskan pada **pemahaman konsep**
* Hindari menyalin dokumentasi eksternal secara berlebihan
* Gunakan referensi spesifikasi jika tersedia

---

# Filosofi Proyek

Repositori ini dibangun berdasarkan tiga prinsip utama.

### Pengetahuan yang Terstruktur

Informasi disusun secara hierarkis agar sistem yang kompleks lebih mudah dipahami.

### Pembelajaran Berbasis Sumber

Setiap konsep dihubungkan dengan spesifikasi atau dokumentasi implementasi resmi.

### Evolusi Berkelanjutan

Ekosistem browser terus berkembang.
Basis pengetahuan ini dirancang untuk berkembang mengikuti perubahan tersebut.

---

# Tujuan Jangka Panjang

Tujuan jangka panjang repositori ini adalah menjadi **peta konseptual yang komprehensif tentang sistem runtime browser**.

Repositori ini diharapkan membantu pengembang memahami bukan hanya **cara menulis JavaScript**, tetapi juga **bagaimana JavaScript benar-benar dijalankan di dalam browser**.
