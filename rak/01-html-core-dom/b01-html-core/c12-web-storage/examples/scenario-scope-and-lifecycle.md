# Skenario: Scope dan Lifecycle Web Storage

Tujuan: menunjukkan bahwa storage terikat scope dan lifecycle tertentu.

## Alur

1. Halaman A (origin X) menyimpan key `theme=dark` ke localStorage.
2. Halaman B (origin X) membaca key yang sama dan mendapatkan `dark`.
3. Halaman C (origin Y) tidak dapat mengakses data origin X.
4. sessionStorage: halaman membuka tab baru; data sessionStorage tidak otomatis terbawa (tergantung konteks) dan hilang ketika sesi berakhir.

## Catatan

Detail isolasi storage yang lebih luas ada di rak Storage & Persistence.
