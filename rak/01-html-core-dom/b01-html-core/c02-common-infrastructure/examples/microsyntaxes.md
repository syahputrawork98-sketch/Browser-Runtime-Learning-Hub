# Contoh: Microsyntaxes Yang Sering Muncul

Microsyntaxes adalah cara spec mendefinisikan format teks yang dipakai berulang, misalnya di attribute values.

Contoh kategori (high level):

- Boolean attributes: ada/tidak ada attribute mempengaruhi state.
- Enumerated attributes: nilai string tertentu memetakan ke state tertentu.
- Numbers/dates/times: parsing string -> angka/waktu, termasuk error handling.

Catatan: detail parsing spesifik harus mengikuti section referensi di HTML Standard, dan jika topiknya lebih cocok di rak lain (mis. URL parsing), cukup tautkan.
