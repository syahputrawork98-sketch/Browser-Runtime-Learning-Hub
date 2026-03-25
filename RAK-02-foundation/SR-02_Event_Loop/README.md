# SR-02: The Web Event Loop - The Rhythm of the UI

Membahas bagaimana browser mengoordinasikan antara eksekusi JavaScript, penanganan event, dan rendering UI untuk mencapai pengalaman yang mulus (60FPS).

## 🎯 The Why (Visi Arsitektural)
JavaScript adalah bahasa *single-threaded*. Tanpa Event Loop, satu operasi sinkron yang berat akan membekukan seluruh antarmuka (UI Freeze). Event Loop adalah "dirigen" yang memastikan browser tetap responsif dengan mengatur kapan kode dijalankan dan kapan layar dilukis.

## 🏗️ The How (Arsitektur Internal)
Mekanisme koordinasi ini melibatkan beberapa antrean prioritas:
1.  **Macrotasks (Task Queue)**: Timers (`setTimeout`), I/O, UI Events.
2.  **Microtasks**: Promises (`.then`, `async/await`), `MutationObserver`. Microtasks selalu dikuras habis sebelum browser melanjutkan ke tugas lain.
3.  **RequestAnimationFrame (rAF)**: Jendela khusus sebelum tahap *Paint* untuk logika animasi yang sinkron dengan refresh rate layar.

## 🧪 The Practical (Roadmap Buku)
- **BK-01: Task Prioritization & Micromanagement**: Memahami urutan eksekusi antara Macro dan Micro tasks.
- **BK-02: Animation & Scheduling**: Teknik rAF dan `requestIdleCallback` untuk animasi tanpa *jank*.
- **BK-03: Web Workers Intersection**: Memparallelkan tugas berat keluar dari Main Thread.

## ⚠️ The Pitfalls (Batas & Kerentanan)
- **Microtask Starvation**: Deretan Promises yang tak berujung dapat memblokir rendering layar selamanya.
- **Main Thread Blocking**: Menjalankan loop berat di main thread akan menyebabkan "Page Unresponsive".
- **Timer Inaccuracy**: `setTimeout` tidak menjamin waktu eksekusi yang presisi karena ketergantungan pada beban task queue.
