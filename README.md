# Panduan Tugas Akhir (Situs Dokumentasi)

Situs dokumentasi digital dari Buku Panduan Tugas Akhir Mahasiswa, dibangun dengan [MkDocs](https://www.mkdocs.org/) + tema [Material](https://squidfunk.github.io/mkdocs-material/).

## Cara Publish ke GitHub Pages

1. Buat repository baru di GitHub (bisa **public** atau **private** — kalau private, GitHub Pages butuh plan berbayar; kalau public, gratis)
2. Upload/push semua isi folder ini ke repo tersebut:
   ```bash
   cd ta-docs
   git init
   git add .
   git commit -m "Initial commit - Panduan TA"
   git branch -M main
   git remote add origin https://github.com/USERNAME/NAMA-REPO.git
   git push -u origin main
   ```
3. Buka repo di GitHub → **Settings** → **Pages** (menu kiri)
4. Di bagian **Source**, pilih branch **gh-pages** (branch ini akan otomatis dibuat oleh GitHub Actions setelah push pertama, tunggu 1-2 menit dan refresh)
5. Situs akan tersedia di: `https://USERNAME.github.io/NAMA-REPO/`

Setiap kali ada perubahan (edit file .md, tambah bab baru, dsb) dan di-push ke branch `main`, situs akan **otomatis ter-update** lewat GitHub Actions (lihat `.github/workflows/deploy.yml`).

## Cara Coba di Komputer Sendiri (opsional, sebelum push)

```bash
pip install -r requirements.txt
mkdocs serve
```

Lalu buka `http://localhost:8000` di browser.

## Struktur Folder

```
docs/               → semua konten dalam format Markdown (.md)
mkdocs.yml           → konfigurasi situs (judul, navigasi, tema)
.github/workflows/   → otomasi build & deploy ke GitHub Pages
```

## Catatan Penting: Perlu Dirapikan Manual

Isi tiap bab di folder `docs/` diekstrak otomatis dari PDF asli, sehingga:
- Tabel kompleks mungkin belum rapi (perlu dirapikan manual ke format tabel Markdown)
- Ada kemungkinan baris kosong atau spasi berlebih yang perlu dibersihkan
- Gambar/diagram dari PDF **belum ikut ter-extract** — perlu ditambahkan manual jika ada

Disarankan untuk membaca ulang tiap file `.md` dan merapikan sebelum dipublikasikan resmi ke mahasiswa.
