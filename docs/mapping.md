# Pemetaan Knowledge Base (Berdasarkan Referensi Induk)

Pemetaan ini menyusun "rak" (domain/tema) dan "buku" (topik spesifik) untuk **Browser Runtime Knowledgebase**. Fokus utamanya adalah **cara kerja browser**, termasuk **alur dari berbagai bahasa sampai bisa berjalan di browser**. Bahasa boleh dibahas, tetapi hanya untuk menjelaskan **mekanisme runtime**, bukan mempelajari bahasanya.

## Rak Utama (16)

1. **R01 - HTML Core & DOM**
2. **R02 - CSS & Styling**
3. **R03 - Layout & Rendering Pipeline**
4. **R04 - JavaScript Runtime**
5. **R05 - Web APIs & Platform**
6. **R06 - Networking & Fetch**
7. **R07 - URL & Origin**
8. **R08 - Storage & Persistence**
9. **R09 - IndexedDB & Data Stores**
10. **R10 - Workers & Background**
11. **R11 - Streams & File API**
12. **R12 - Realtime & Transport**
13. **R13 - Security & Policies**
14. **R14 - WebAssembly & Language Pathways**
15. **R15 - Performance & Observability**
16. **R16 - Platform Updates & Compatibility**

## Contoh Buku (Topik Spesifik)

- "Alur TypeScript ke Browser: Transpile -> JS -> Engine -> Render"
- "Alur Golang ke Browser: WASM -> JS Bridge -> Web APIs"
- "Event Loop: Render vs Task Queue"
- "Rendering Pipeline: Style -> Layout -> Paint -> Composite"
- "Fetch Pipeline: DNS -> TLS -> HTTP"

## Relasi Lintas Rak

Beberapa buku akan lintas rak (mis. "Alur TS ke Browser" menyentuh Runtime, Networking, dan Web APIs). Keterkaitan ini bisa ditandai di metadata buku.
