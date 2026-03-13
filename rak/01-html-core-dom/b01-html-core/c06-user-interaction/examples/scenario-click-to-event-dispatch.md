# Skenario: Klik Sampai Handler Jalan

Tujuan: memberi alur mental sederhana dari input device sampai kode handler berjalan.

## Alur

1. User klik di posisi tertentu di viewport.
2. Browser melakukan hit testing untuk menentukan elemen target.
3. Browser membentuk event (mis. `click`) dan menyiapkan jalur propagation.
4. Event di-dispatch: capturing -> target -> bubbling.
5. Event listener pada target/ancestor dipanggil.
6. Handler dapat memanggil `preventDefault()` atau memodifikasi DOM.

## Catatan

- Detail aturan event banyak berada di DOM Standard; di sini kita fokus kaitannya dengan dokumen dan interaksi user.
