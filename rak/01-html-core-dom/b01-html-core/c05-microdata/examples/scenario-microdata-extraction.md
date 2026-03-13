# Skenario: Microdata Diekstrak Dari DOM

Tujuan: menunjukkan bahwa model microdata dibangun dari DOM tree, dan perubahan DOM mempengaruhi hasilnya.

## Alur

1. Dokumen punya elemen dengan `itemscope` dan `itemtype` sebagai root item.
2. Elemen anak memiliki `itemprop` sebagai property dari item.
3. Konsumen melakukan ekstraksi: membaca item dan property berdasarkan aturan spec.
4. Script menambah/menghapus node yang memiliki `itemprop`.
5. Ekstraksi ulang menghasilkan data yang berbeda karena tree berubah.

## Catatan

- Fokusnya cara kerja model berbasis DOM, bukan best practice SEO.
