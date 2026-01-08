# 📝 Revisi Format Halaman Pengesahan

## 🎯 Tujuan
Memperbaiki format halaman pengesahan di template LaTeX agar sesuai dengan format yang digunakan di laporan mahasiswa (referensi: Laporan TA Anis Sulala).

## 🔍 Masalah yang Ditemukan

### Format Lama (Template LaTeX):
- ❌ Menggunakan format **tabel** dengan 3 kolom: Nama/Jabatan | Tanda Tangan | Tanggal
- ❌ Tidak ada bagian "**Tanggal Ujian**"
- ❌ Tidak ada kata "**Menyetujui**" sebelum daftar pembimbing
- ❌ Tidak ada kata "**Mengesahkan**" sebelum ketua jurusan
- ❌ Tidak ada **Ketua Program Studi** (hanya Ketua Jurusan)
- ❌ Format tanda tangan menggunakan titik-titik biasa

### Format Baru (Sesuai DOCX):
- ✅ Layout **side-by-side** (2 kolom) untuk pembimbing dan penguji
- ✅ Ada **Tanggal Ujian** setelah NIM
- ✅ Ada kata "**Menyetujui**" sebelum pembimbing/penguji
- ✅ Ada kata "**Mengesahkan**" sebelum ketua jurusan/prodi
- ✅ Ada **Ketua Jurusan** dan **Ketua Program Studi** berdampingan
- ✅ Tanda tangan menggunakan kurung dengan titik-titik: `(..........)`

## 📋 Perubahan yang Dilakukan

### File: `laporan/untouch/xx-pengesahan.tex`

#### 1. **Header dan Judul**
```latex
HALAMAN PENGESAHAN
[JUDUL TUGAS AKHIR]

Tugas Akhir ini disusun untuk Memenuhi Salah Satu Syarat Memperoleh
Gelar Sarjana Terapan Komputer (S.Tr.Kom)
Politeknik Negeri Banyuwangi
```

#### 2. **Informasi Mahasiswa**
```latex
Oleh:
[Nama Mahasiswa]
NIM. [NIM]

Tanggal Ujian : [Tanggal]
```

#### 3. **Bagian Pembimbing dan Penguji**
```latex
Menyetujui,

[Layout 2 Kolom]
Pembimbing 1          Pembimbing 2
[Nama]                [Nama]
(............)        (............)

Penguji 1             Penguji 2
[Nama]                [Nama]
(............)        (............)
```

#### 4. **Bagian Pengesahan**
```latex
Mengesahkan,

[Layout 2 Kolom]
Ketua Jurusan                    Ketua Program Studi
Bisnis dan Informatika           Teknologi Rekayasa Perangkat Lunak
[Nama]                           [Nama]
NIP. [NIP]                       NIP. [NIP]
```

## 🔧 Implementasi Teknis

### Menggunakan `minipage` untuk Layout Side-by-Side
```latex
\begin{minipage}[t]{0.45\textwidth}
    \centering
    Pembimbing 1\\[2cm]
    \pembimbingsatu\\
    (\makebox[4cm]{\dotfill})
\end{minipage}
\hfill
\begin{minipage}[t]{0.45\textwidth}
    \centering
    Pembimbing 2\\[2cm]
    \pembimbingdua\\
    (\makebox[4cm]{\dotfill})
\end{minipage}
```

### Tanda Tangan dengan Kurung
```latex
(\makebox[4cm]{\dotfill})
```
Menghasilkan: `(....................)`

## ✅ Hasil

Format halaman pengesahan sekarang **100% sesuai** dengan format yang digunakan di laporan mahasiswa Poliwangi.

### Struktur Lengkap:
1. ✅ Judul "HALAMAN PENGESAHAN"
2. ✅ Judul Tugas Akhir (uppercase)
3. ✅ Keterangan tujuan tugas akhir
4. ✅ Nama dan NIM mahasiswa
5. ✅ Tanggal Ujian
6. ✅ "Menyetujui" + Pembimbing 1 & 2 (side-by-side)
7. ✅ Penguji 1 & 2 (side-by-side)
8. ✅ "Mengesahkan" + Ketua Jurusan & Ketua Prodi (side-by-side)

## 📝 Catatan Penting

### Variabel yang Digunakan dari `a0-identitas.tex`:
- `\judulid` - Judul Tugas Akhir (Bahasa Indonesia)
- `\penulis` - Nama Mahasiswa
- `\nim` - NIM Mahasiswa
- `\tglpengesahan` - Tanggal Ujian/Pengesahan
- `\pembimbingsatu` - Nama Pembimbing 1
- `\pembimbingdua` - Nama Pembimbing 2
- `\pengujisatu` - Nama Penguji 1
- `\pengujidua` - Nama Penguji 2
- `\dekan` - Nama Ketua Jurusan
- `\NIPdekan` - NIP Ketua Jurusan
- `\koorprodi` - Nama Ketua Program Studi
- `\NIPkoorprodi` - NIP Ketua Program Studi

### Pastikan Mengisi Data di `a0-identitas.tex`
Semua variabel di atas harus diisi dengan data yang benar agar halaman pengesahan tampil dengan sempurna.

## 🎨 Preview Format

```
                    HALAMAN PENGESAHAN
        
        SISTEM KLASIFIKASI KOLEKSI PERPUSTAKAAN BERBASIS
         DEWEY DECIMAL CLASSIFICATION MENGGUNAKAN
            ALGORITMA TF-RF DAN K-NEAREST NEIGHBOR

    Tugas Akhir ini disusun untuk Memenuhi Salah Satu Syarat Memperoleh
                Gelar Sarjana Terapan Komputer (S.Tr.Kom)
                    Politeknik Negeri Banyuwangi

                            Oleh:
                        Anis Sulala
                      NIM. 362155401156

                  Tanggal Ujian : 17 Juni 2025

Menyetujui,

    Pembimbing 1                        Pembimbing 2
    Lutfi Hakim, S.Pd., M.T.           Sepyan P. K., S.Kom., M.Kom
    (...................)               (...................)

    Penguji 1                           Penguji 2
    Ruth Ema Febrita, S.Pd., M.Kom.    Khoirul Umam, S.Pd., M.Kom
    (...................)               (...................)

Mengesahkan,

    Ketua Jurusan                       Ketua Program Studi
    Bisnis dan Informatika              Teknologi Rekayasa Perangkat Lunak
    
    [Nama Ketua Jurusan]                [Nama Koordinator Prodi]
    NIP. [NIP]                          NIP. [NIP]
```

## 🚀 Testing

Untuk melihat hasil perubahan:

1. **Isi data di `a0-identitas.tex`** dengan data yang benar
2. **Compile laporan**:
   ```bash
   cd laporan/
   pdflatex laporan.tex
   ```
3. **Cek halaman pengesahan** di PDF yang dihasilkan

## 📚 Referensi

- Format diambil dari: `Laporan Tugas Akhir_Anis Sulala_362155401156.docx`
- Mahasiswa: Anis Sulala (NIM: 362155401156)
- Program Studi: Sarjana Terapan Teknologi Rekayasa Perangkat Lunak
- Politeknik Negeri Banyuwangi

---

**Tanggal Revisi:** 8 Januari 2026  
**Direvisi oleh:** Sepyan Purnama Kristanto
