# Skenario: Streaming Parse Bertemu Script Yang Memblokir

Tujuan: menunjukkan bahwa parsing HTML berjalan sambil data datang (streaming), tetapi bisa berhenti (block) saat bertemu script tertentu.

## Setup Mental

- HTML datang dari network secara bertahap.
- Browser membangun DOM sambil membaca input.
- Ada `<script>` yang menyebabkan parsing berhenti sampai script selesai.

## Alur

1. Browser menerima chunk HTML pertama dan mulai decode + tokenize.
2. Tree builder membangun DOM awal (mis. `<html>`, `<head>`, beberapa `<meta>`).
3. Chunk berikutnya berisi `<script src="...">`.
4. Browser harus memastikan script tersebut dijalankan pada waktu yang benar (konsep), sehingga parsing bisa berhenti.
5. Setelah script selesai dieksekusi, parsing lanjut dari posisi terakhir.
6. Jika script melakukan `document.write` (konsep), input stream bisa bertambah/berubah saat parsing masih berlangsung.

## Hasil Yang Biasanya Terlihat Saat Debugging

- DOM terlihat "bertumbuh" bertahap.
- Ada titik di mana parsing berhenti sementara (network lanjut, tapi tree builder menunggu).
- Urutan eksekusi script dan hasil DOM menjadi kunci untuk memahami bug.

