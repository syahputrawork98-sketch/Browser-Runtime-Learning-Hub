# Arsitektur & Hierarki Struktur (Browser Runtime Edition)

Proyek **Browser Runtime Knowledge Base** disusun dengan standar **Unified Gold Standard (PPM V4)**.

## 1. Hirarki 6-Level
| Tingkatan | Nama | Prefix | Contoh |
| :--- | :--- | :--- | :--- |
| **Level 1** | **Root** | `/` | `/` |
| **Level 2** | **Rak** | `RAK-` | `RAK-01-anatomy/` |
| **Level 3** | **Sub-Rak** | `SR-` | `SR-01-v8-engine/` |
| **Level 4** | **Buku** | `BK-` | `BK-01_EventLoop/` |
| **Level 5** | **Bab** | `CH-` | `CH-01_Microtasks/` |
| **Level 6** | **Section** | `SEC-` | `SEC-01_PromiseHandling/` |

> [!IMPORTANT]
> **Pengecualian RAK-01 (Anatomy)**: hierarki menggunakan **Flat Structure** (RAK > BK > CH > SEC).

---

## 2. Karakteristik 8-RAK Architecture
*Struktur ini dirancang untuk menampung **5 Bahasa Utama (JS, TS, Rust, Go, Python)** dalam ekosistem Browser.*

1. **RAK-01-anatomy**: Sejarah Browser & Evolusi Engine.
2. **RAK-02-foundation**: V8, Event Loop, & Rendering Pipeline.
3. **RAK-03-evolution**: Web APIs: DOM, CSSOM, Fetch, Storage.
4. **RAK-04-core-mechanics**: JIT, TurboFan, Ignition, & Memory.
5. **RAK-05-ecosystem**: DevTools, Profiling, & Debugging.
6. **RAK-06-the-underworld**: Shared Memory, Workers, & Low-level.
7. **RAK-07-specialization**: PWA, Streams, & Advanced APIs.
8. **RAK-08-matrix-intersection**: The Bridge Between Languages & Browser.

---

## 3. Kriteria Gold Standard
Setiap unit materi (CH/SEC) wajib memiliki:
1. **Source Link** (Akurasi Spec V8 / MDN / WHATWG).
2. **Dual Definition** (Formal + Model Mental).
3. **Mermaid Diagram**.
4. **Mekanisme Detil** (Under-the-hood).
5. **Lab Praktis** (Relasi ke kode `.js` di `examples/`).
