# Browser Runtime Knowledge Base

Repository ini adalah monorepo berbentuk "perpustakaan" yang membahas **cara kerja browser runtime**. Fokus utamanya bukan belajar bahasa pemrograman, melainkan memahami **bagaimana browser bekerja**, bagaimana alur eksekusi terjadi, dan bagaimana berbagai sumber/teknologi masuk ke runtime browser.

## Apa Itu Repo Ini

Repo ini menyimpan pengetahuan terstruktur tentang runtime browser dalam bentuk:

- **Rak**: domain/tema besar (misalnya runtime, rendering, networking)
- **Buku**: topik spesifik di dalam satu rak
- **Bab**: bagian-bagian detail dari buku, mengikuti referensi utama

Dengan struktur ini, pengetahuan bisa bertumbuh pelan-pelan, konsisten, dan mudah di-update ketika referensi utama berubah.

## Tujuan

- Menjadi sumber belajar dan rujukan internal tentang cara kerja browser
- Mengurangi kebingungan dari "buku besar" dengan memecahnya ke buku-buku kecil
- Menjaga dokumentasi tetap hidup sesuai perkembangan browser

## Cara Kerja (Ringkas)

1. Referensi utama dianggap sebagai **buku besar**.
2. Isi buku besar dipecah menjadi **buku** dan **bab** berdasarkan rak yang relevan.
3. Perubahan pada referensi utama dicatat pada **CHANGELOG** di level buku.

## Struktur Root

- `README.md` adalah pendahuluan ini.
- `docs/` berisi dokumentasi pendukung (pemetaan, aturan, referensi).
- `rak/` berisi semua rak utama.

## Dokumentasi

- [docs/README.md](i:/Workspace/Workspace-Syahputrawork/Browser-Runtime-Knowledge-Base/docs/README.md)
- [docs/root-governance.md](i:/Workspace/Workspace-Syahputrawork/Browser-Runtime-Knowledge-Base/docs/root-governance.md)
- [docs/references.md](i:/Workspace/Workspace-Syahputrawork/Browser-Runtime-Knowledge-Base/docs/references.md)

## Prinsip Utama

- Fokus pada **cara kerja browser** (bukan belajar bahasa).
- Struktur mengikuti **referensi induk**.
- Perubahan dicatat di **buku** (CHANGELOG per buku).
- Jumlah rak/buku/bab **fleksibel** dan mengikuti referensi.
