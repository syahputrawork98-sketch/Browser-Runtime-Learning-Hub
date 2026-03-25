# SR-02: TypeScript Erasure - Type Safety at Runtime

Membahas bagaimana TypeScript berinteraksi dengan runtime browser yang hanya memahami JavaScript, dan strategi penghapusan tipe (erasure) untuk eksekusi.

## 🎯 The Why (Visi Arsitektural)
Browser tidak bisa menjalankan `.ts` secara langsung. TypeScript memberikan keamanan saat pengembangan, namun ia harus "menghilang" saat runtime. Memahami proses ini membantu kita memisahkan antara beban pengembangan dan performa eksekusi nyata.

## 🏗️ The How (Arsitektur Internal)
TypeScript di browser melibatkan siklus:
1.  **Transpilation**: Proses mengubah sintaks TS menjadi JS (melalui TSC, SWC, atau ESBuild).
2.  **Type Erasure**: Menghapus seluruh informasi tipe, antarmuka, dan dekorator yang tidak valid di JavaScript.
3.  **Source Maps**: Jembatan yang memungkinkan kita menelusuri bug di kode `.ts` asli meskipun browser sedang menjalankan `.js` hasil kompilasi.

## 🧪 The Practical (Roadmap Buku)
- **BK-01: Efficient Transpilation Pipelines**: Membangun workflow build kilat menggunakan ESBuild/Vite.
- **BK-02: Debugging with Source Maps**: Teknik pelacakan error produksi kembali ke sumber asli.
- **BK-03: Runtime Type Validation**: Menggunakan pustaka (seperti Zod/Valibot) untuk keamanan data di runtime yang tidak dimiliki TS.

## ⚠️ The Pitfalls (Batas & Kerentanan)
- **The "False Security" Trap**: Lupa bahwa TypeScript tidak memberikan keamanan tipe pada data yang datang dari API (Runtime input).
- **Transpilation Overhead**: Proses build yang lambat dapat menghambat produktivitas jika tidak dikonfigurasi dengan benar.
- **Decorator Metadata Issues**: Beberapa fitur TS (seperti Reflect Metadata) memerlukan polyfill besar yang menambah berat beban awal (*initial load*).
