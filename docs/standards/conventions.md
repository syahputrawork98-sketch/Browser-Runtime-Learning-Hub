# Konvensi Penamaan & Struktur Folder (Browser Runtime Edition)

## 1. Penamaan Direktori
| Level | Prefix | Format | Contoh |
| :--- | :--- | :--- | :--- |
| **Rak** | `RAK-` | `RAK-XX-slug` | `RAK-02-foundation` |
| **Sub-Rak** | `SR-` | `SR-XX-slug` | `SR-01-v8-engine` |
| **Buku** | `BK-` | `BK-XX_Slug` | `BK-01_EventLoop` |
| **Bab** | `CH-` | `CH-XX_Slug` | `CH-01_Microtasks` |
| **Section** | `SEC-` | `SEC-XX_Slug` | `SEC-01_Promise` |

---

## 2. Struktur Internal Unit
```text
CH- atau SEC-/
├── README.md        <- Materi inti & Mermaid.
├── examples/        <- Kode lab (.js / .html).
└── assets/          <- Media statis.
```

## 3. Aturan Lab Praktis (`examples/`)
File wajib menggunakan prefix numerik: `01_script.js`, `02_dom_manipulation.html`.
