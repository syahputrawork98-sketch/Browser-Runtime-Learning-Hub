# Docs

Folder ini berisi seluruh dokumentasi lanjutan dan aturan monorepo.

## Konsep Monorepo (Analogi Perpustakaan)

- **Monorepo** = Perpustakaan
- **Rak** = Domain/tema besar
- **Buku** = Modul/topik spesifik di dalam rak

```mermaid
flowchart TB
    subgraph Library[Monorepo = Perpustakaan]
        R01[Rak: Domain A]
        R02[Rak: Domain B]
        R03[Rak: Domain C]

        R1 --> B01[Buku: Topik A1]
        R1 --> B02[Buku: Topik A2]

        R2 --> B01[Buku: Topik B1]
        R2 --> B02[Buku: Topik B2]

        R3 --> B01[Buku: Topik C1]
    end
```

## Pemetaan

- [mapping.md](mapping.md)

## Tata Kelola

- [root-governance.md](root-governance.md)

## Catatan

`docs/` berisi penjelasan tambahan yang merujuk ke README di tiap level (root, rak, buku).

## Panduan Sumber Bab

- [chapter-sourcing.md](chapter-sourcing.md)

## Referensi

- [references.md](references.md)

## Pemetaan Referensi

- [reference-mapping.md](reference-mapping.md)

