# Skenario: Main Thread Mengirim Tugas ke Worker

Tujuan: menggambarkan alur dasar dedicated worker.

## Alur

1. Main thread membuat worker dengan URL skrip.
2. Browser memuat skrip worker dan menjalankannya di konteks worker.
3. Main thread mengirim pesan (payload) dengan `postMessage`.
4. Worker menerima event `message`, memproses payload, lalu mengirim hasil balik.
5. Main thread menerima event `message` dari worker dan memperbarui UI.

## Catatan

- Karena worker tidak mengakses DOM, hasil biasanya dikirim kembali untuk diterapkan di main thread.
- Detail structured clone dan security checks terkait C09.
