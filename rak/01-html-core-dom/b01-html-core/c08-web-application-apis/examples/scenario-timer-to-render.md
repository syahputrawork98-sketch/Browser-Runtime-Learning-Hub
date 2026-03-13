# Skenario: Timer Sampai Render

Tujuan: menunjukkan pola umum scheduling di browser runtime.

## Alur

1. Script memanggil timer (mis. setTimeout).
2. Browser menjadwalkan callback dan menaruhnya ke antrian task saat waktunya tiba.
3. Event loop mengambil task dan menjalankan callback.
4. Callback memodifikasi DOM (mis. menambahkan elemen atau mengubah teks).
5. Browser menjadwalkan rendering update dan tampilan berubah.

## Catatan

- Detail task/microtask ada di rak JavaScript Runtime.
- Ini contoh pola; API lain punya variasi aturan dan batasan.
