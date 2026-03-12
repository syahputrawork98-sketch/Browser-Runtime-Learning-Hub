# Pemetaan Knowledge Base (Berdasarkan Referensi Induk)

Pemetaan ini menyusun "rak" (domain/tema) dan "buku" (topik spesifik) untuk **Browser Runtime Knowledgebase**. Fokus utamanya adalah **cara kerja browser**, termasuk **alur dari berbagai bahasa sampai bisa berjalan di browser**. Bahasa boleh dibahas, tetapi hanya untuk menjelaskan **mekanisme runtime**, bukan mempelajari bahasanya.

## Rak Utama (16) dan Buku

1. **R01 - HTML Core & DOM**
   - B01: HTML Core
   - B02: DOM Standard

2. **R02 - CSS & Styling**
   - B01: CSSOM
   - B02: Selectors
   - B03: CSS Cascade

3. **R03 - Layout & Rendering Pipeline**
   - B01: Rendering Pipeline
   - B02: Layout & Visual Formatting

4. **R04 - JavaScript Runtime**
   - B01: Event Loop
   - B02: Task vs Microtask
   - B03: Agents & Realms

5. **R05 - Web APIs & Platform**
   - B01: Web APIs Overview
   - B02: Web IDL

6. **R06 - Networking & Fetch**
   - B01: Fetch Pipeline
   - B02: Request/Response & Caching

7. **R07 - URL & Origin**
   - B01: URL & Origin

8. **R08 - Storage & Persistence**
   - B01: Storage Overview
   - B02: Cookies & Storage Isolation

9. **R09 - IndexedDB & Data Stores**
   - B01: IndexedDB
   - B02: Cache Storage

10. **R10 - Workers & Background**
    - B01: Workers Overview
    - B02: Service Worker Lifecycle

11. **R11 - Streams & File API**
    - B01: Streams
    - B02: File API

12. **R12 - Realtime & Transport**
    - B01: WebSocket
    - B02: WebRTC
    - B03: WebTransport

13. **R13 - Security & Policies**
    - B01: Same-Origin Policy
    - B02: CORS
    - B03: CSP
    - B04: Permissions API
    - B05: MIME Sniffing

14. **R14 - WebAssembly & Language Pathways**
    - B01: JavaScript Pathway
    - B02: TypeScript Pathway
    - B03: Golang WASM Pathway
    - B04: Python WASM Pathway

15. **R15 - Performance & Observability**
    - B01: DevTools Overview
    - B02: Engine Observability

16. **R16 - Platform Updates & Compatibility**
    - B01: Release Notes
    - B02: Platform Status

## Contoh Buku (Topik Spesifik)

- "Alur TypeScript ke Browser: Transpile -> JS -> Engine -> Render"
- "Alur Golang ke Browser: WASM -> JS Bridge -> Web APIs"
- "Event Loop: Render vs Task Queue"
- "Rendering Pipeline: Style -> Layout -> Paint -> Composite"
- "Fetch Pipeline: DNS -> TLS -> HTTP"

## Relasi Lintas Rak

Beberapa buku akan lintas rak (mis. "Alur TS ke Browser" menyentuh Runtime, Networking, dan Web APIs). Keterkaitan ini bisa ditandai di metadata buku.
