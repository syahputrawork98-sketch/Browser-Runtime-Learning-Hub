# Skenario: Content-Type Menentukan Parser (HTML vs XML)

Tujuan: menunjukkan bahwa dokumen yang isinya "mirip HTML" bisa diparse sangat berbeda tergantung MIME type.

## Alur

1. Server mengirim dokumen dengan `Content-Type: text/html`.
2. Browser memilih HTML parser.
3. Jika ada markup yang tidak rapi (mis. tag tidak ditutup), browser biasanya tetap membangun DOM lewat error-recovery.
4. Ulangi permintaan yang sama tetapi server mengirim `Content-Type: application/xhtml+xml` (konsep).
5. Browser memilih XML parser.
6. Markup yang sama dapat memicu fatal parse error (konsep), dan hasilnya tidak seperti saat diparse sebagai HTML.

## Catatan Debugging

- Saat ada laporan "di browser A blank/putih", cek dulu mode parsing dan `Content-Type`.
- Perbedaan jalur parser sering lebih menentukan daripada "tag mana yang dipakai".

