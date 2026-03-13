# Skenario: Content-Type Salah Membuat Jalur Pemrosesan Salah

Tujuan: menunjukkan kenapa "label" (media type) sering menentukan hasil akhir lebih dari isi dokumennya.

## Alur

1. Server mengirim dokumen yang sebenarnya HTML, tetapi header-nya keliru (mis. tipe XML) (konsep).
2. Browser memilih jalur parser/handler berdasarkan `Content-Type`.
3. Karena parser yang dipilih berbeda, dokumen bisa:
   gagal diparse (fatal error di XML path), atau diparse dengan hasil DOM yang tidak sesuai ekspektasi.
4. Developer melihat gejala: halaman blank, error parsing, atau behavior yang beda antar browser.

## Checklist Debugging Cepat

- Periksa `Content-Type` respons.
- Pastikan server dan CDN tidak mengubah header.
- Bandingkan hasil saat dipaksa menjadi `text/html` (untuk investigasi) (konsep).
