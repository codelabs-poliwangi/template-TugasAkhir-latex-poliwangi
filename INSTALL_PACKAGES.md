# 📦 Instalasi Package LaTeX yang Diperlukan

## Masalah yang Ditemukan

Saat compile `laporan.tex`, ditemukan beberapa package yang belum terinstall:

1. ❌ `babel-indonesian` - Package bahasa Indonesia
2. ❌ `tocloft` - Package untuk format daftar isi
3. ⚠️ Kemungkinan package lain yang diperlukan

## ✅ Solusi 1: Install Package Manual (Recommended)

Jalankan command berikut di terminal:

```bash
# Install package yang diperlukan
sudo tlmgr install babel-indonesian tocloft titlesec caption subcaption \
  natbib cleveref listings xcolor tikz pgfplots pgf-pie rotating \
  enumitem longtable tabularx multirow geometry amsmath float \
  ragged2e setspace

# Update semua package
sudo tlmgr update --self
sudo tlmgr update --all
```

**Note:** Anda akan diminta password sudo.

## ✅ Solusi 2: Install TeX Live Full (Lebih Mudah)

Jika Anda menggunakan BasicTeX, pertimbangkan untuk upgrade ke TeX Live Full yang sudah include semua package:

```bash
# Uninstall BasicTeX (opsional)
brew uninstall basictex

# Install TeX Live Full (~4.5 GB)
brew install --cask mactex

# Atau download manual dari:
# https://www.tug.org/mactex/
```

## ✅ Solusi 3: Gunakan Overleaf (Paling Mudah)

Overleaf sudah include semua package LaTeX yang diperlukan:

1. Buka [Overleaf](https://www.overleaf.com/)
2. Login/Daftar akun gratis
3. Upload project ini sebagai ZIP
4. Set main document: `laporan.tex`
5. Compile langsung tanpa install apapun!

## 🔍 Cara Cek Package yang Terinstall

```bash
# Cek apakah package terinstall
tlmgr info tocloft
tlmgr info babel-indonesian

# List semua package yang terinstall
tlmgr list --only-installed
```

## 📝 Package yang Dibutuhkan Template Ini

Berdasarkan `untouch/xx-preambles.tex`:

| Package | Fungsi |
|---------|--------|
| `babel-indonesian` | Bahasa Indonesia |
| `tocloft` | Format daftar isi |
| `titlesec` | Format judul bab |
| `caption`, `subcaption` | Format caption gambar/tabel |
| `natbib` | Bibliografi (APA style) |
| `cleveref` | Referensi otomatis |
| `listings` | Syntax highlighting kode |
| `tikz`, `pgfplots` | Diagram dan grafik |
| `geometry` | Margin halaman |
| `amsmath` | Persamaan matematika |
| `tabularx`, `multirow` | Tabel kompleks |
| `longtable` | Tabel panjang |
| `enumitem` | List formatting |
| `hyperref` | Hyperlink dalam PDF |

## 🚀 Quick Start

Setelah install package, compile dengan:

```bash
cd laporan/
pdflatex laporan.tex
bibtex laporan
pdflatex laporan.tex
pdflatex laporan.tex
```

Atau gunakan editor seperti TeXstudio dan klik tombol "Build & View" (F5).
