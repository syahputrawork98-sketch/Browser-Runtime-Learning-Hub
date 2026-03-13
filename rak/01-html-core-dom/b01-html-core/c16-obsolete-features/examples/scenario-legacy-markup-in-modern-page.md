# Skenario: Markup Obsolete Muncul Di Halaman Modern

Tujuan: menunjukkan bahwa browser tetap memproses markup legacy, tetapi konsekuensinya muncul di rendering/semantik dan maintenance.

## Alur

1. Sebuah halaman modern memakai layout CSS baru, tetapi ada potongan konten lama (mis. hasil copy-paste atau CMS) yang memasukkan markup obsolete (konsep).
2. Browser mem-parsing HTML dan tetap membangun DOM untuk markup tersebut.
3. Rendering terlihat "jalan", tetapi styling jadi sulit karena markup tidak semantik atau punya default behavior legacy (konsep).
4. A11y tooling sering memberi peringatan karena struktur/semantik tidak ideal (konsep).
5. Developer akhirnya menambah CSS workaround yang memperumit codebase (konsep).

## Catatan

Bab obsolete berguna sebagai "peta" untuk memahami apa yang mungkin masih diproses browser, lalu menentukan strategi perbaikan yang realistis.
