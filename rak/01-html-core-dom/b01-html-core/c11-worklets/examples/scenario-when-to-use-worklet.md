# Skenario: Kapan Worklet Masuk Akal

Tujuan: memberi intuisi kapan kita memilih worklet dibanding main thread atau worker.

## Situasi

Kita butuh logika kecil yang harus dijalankan pada phase tertentu dari subsistem (mis. rendering atau audio) dengan jitter minimal.

## Pertimbangan (High Level)

- Jika tugas butuh akses DOM dan UI, biasanya tetap di main thread.
- Jika tugas berat dan bisa berjalan terpisah, gunakan worker.
- Jika tugas harus terikat subsistem tertentu dan butuh eksekusi yang lebih deterministik/tepat waktu, pertimbangkan worklet.

## Catatan

Detail API worklet spesifik bisa berada di spec lain; bab ini fokus model runtime dan integration points.
