# Bab: C11 - Worklets

## Ringkasan

Bab ini membahas Worklets sebagai model eksekusi ringan yang terintegrasi dengan subsistem tertentu di browser. Fokusnya adalah cara kerja runtime: kapan worklet dijalankan, bagaimana ia dimuat, bagaimana ia berbeda dari worker, dan apa batasan pentingnya.

## Tujuan

- Memahami posisi worklets di ekosistem runtime browser (berbeda dari main thread dan worker)
- Menjelaskan pola umum: register module -> engine menjalankan callback di waktu/phase tertentu
- Menjadi pengantar sebelum membahas integrasi spesifik (mis. rendering pipeline atau audio)

## Analogi Singkat

Worklet itu seperti "plugin kecil" yang ditempel ke mesin tertentu: ia tidak mengendalikan seluruh aplikasi, tetapi dipanggil tepat saat mesin itu membutuhkan fungsi khusus.

## Analogi Panjang

Bayangkan browser itu seperti pabrik dengan beberapa mesin: mesin rendering, mesin audio, dan lain-lain. Kadang kita butuh logika kecil yang berjalan sangat dekat dengan mesin tersebut, misalnya untuk menghasilkan output yang halus atau tepat waktu. Kalau logika itu diproses di kantor pusat (main thread), bisa terlambat karena antrian pekerjaan lain.

Worklets memberi cara untuk memasang modul kecil yang dieksekusi oleh subsistem tertentu. Modelnya biasanya: kita registrasi sebuah module, lalu browser memanggil entry point tertentu sesuai phase. Karena berada dekat subsistem, worklets biasanya punya batasan akses (tidak bebas akses DOM) dan aturan keamanan/performance yang ketat.

## Alur Utama

1. Script mendaftarkan module worklet (register/addModule)
2. Browser memuat module worklet dan melakukan inisialisasi
3. Subsistem (mis. rendering/audio) memanggil callback worklet pada phase tertentu
4. Worklet menghasilkan output/efek yang dibutuhkan subsistem
5. Lifecycle worklet mengikuti lifecycle subsistem; teardown saat konteks berakhir

## Istilah Kunci

- Worklet
- Module registration
- Execution phase (konsep)
- Subsystem integration
- Isolation (konsep)

## Batasan dan Perilaku Penting

- Worklet bukan pengganti worker: worklet biasanya lebih spesifik, lebih terikat subsistem, dan lebih dibatasi.
- Akses langsung ke DOM umumnya tidak tersedia; worklet dirancang untuk performa dan determinisme.
- Detail implementasi dapat berbeda antar browser, tetapi model/konsep dari spec tetap jadi rujukan kita.

## Sumber Referensi

- Sumber: HTML Standard (WHATWG)
- Versi/Tanggal: 2026-03-12
- Lokasi: `worklets.html#worklets` (multipage)

## Lampiran

- Diagram: `assets/overview.svg`
- Contoh: `examples/scenario-when-to-use-worklet.md`
