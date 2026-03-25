# Pemetaan Knowledge Base (Berdasarkan Referensi Induk)

Pemetaan ini menyusun "rak" (domain/tema) dan "buku" (topik spesifik) untuk **Browser Runtime Knowledgebase**. Fokus utamanya adalah **cara kerja browser**, termasuk **alur dari berbagai bahasa sampai bisa berjalan di browser**. Bahasa boleh dibahas, tetapi hanya untuk menjelaskan **mekanisme runtime**, bukan mempelajari bahasanya.

## Rak Utama (8) dan Sub-Rack

1. **RAK-01 - Anatomy & Landscape** (Directly to Books)
   - BK-01: Market Share & Engines
   - BK-02: Spec & Standards (WHATWG/W3C)

2. **RAK-02 - Foundation & Core Rules**
   - SR-01: V8 Engine
   - SR-02: Event Loop
   - SR-03: Rendering Pipeline

3. **RAK-03 - Evolution & Interfacing**
   - SR-01: DOM & CSSOM
   - SR-02: Network APIs
   - SR-03: Web Storage

4. **RAK-04 - Core Mechanics**
   - SR-01: Compilation Strategy
   - SR-02: Memory & GC
   - SR-03: Internal Bindings

5. **RAK-05 - Ecosystem & Tooling**
   - SR-01: DevTools Mastery
   - SR-02: Profiling & Optimization

6. **RAK-06 - The Underworld**
   - SR-01: Multi-Threading
   - SR-02: Background Tasks

7. **RAK-07 - Specialization & Edge**
   - SR-01: WebAssembly
   - SR-02: Emerging APIs

8. **RAK-08 - Matrix Intersection**
   - SR-01: JavaScript Native
   - SR-02: TypeScript Erasure
   - SR-03: Rust WASM Bridge
   - SR-04: Go WASM Interop
   - SR-05: Python Pyodide WASM

## Relasi Lintas Rak

Setiap modul dapat berinteraksi lintas rak (mis. WebAssembly di RAK-07 berhubungan erat dengan Matrix Intersection di RAK-08).
