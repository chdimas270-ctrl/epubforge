# EPUBForge v3.5 — Konverter, OCR & Validator EPUB 3.3

Aplikasi web modern untuk mengonversi naskah dokumen (.PDF, .DOCX, .TXT, .MD, .HTML) menjadi berkas **EPUB 3.3** standar industri yang valid, dilengkapi mesin OCR Tesseract, penataan XHTML strict, sampul otomatis, dan pratinjau e-reader interaktif. Berjalan 100% di sisi klien (Client-Side) tanpa memerlukan backend server.

---

## 🚀 Panduan Deploy ke Vercel

Proyek ini telah dikonfigurasi lengkap dengan file [`vercel.json`](./vercel.json), [`package.json`](./package.json), dan [`.gitignore`](./.gitignore) sehingga siap dideploy ke Vercel secara instan.

Pilih salah satu metode di bawah ini:

### Metode 1: Deploy via GitHub & Dashboard Vercel (Rekomendasi)

Metode ini paling praktis karena setiap kali Anda memperbarui kode dan melakukan `git push`, Vercel akan otomatis melakukan build dan deploy ulang (Continuous Deployment).

1. **Inisialisasi Git dan Commit:**
   ```bash
   git init
   git add .
   git commit -m "Feat: Siap deploy ke Vercel"
   ```

2. **Buat Repository Baru di GitHub:**
   - Kunjungi [github.com/new](https://github.com/new).
   - Beri nama repository (misalnya `epubforge`).
   - Jangan centang "Add README" (karena sudah ada).
   - Klik **Create repository**.

3. **Hubungkan & Push ke GitHub:**
   ```bash
   git branch -M main
   git remote add origin https://github.com/USERNAME-ANDA/epubforge.git
   git push -u origin main
   ```

4. **Deploy di Vercel:**
   - Buka [vercel.com](https://vercel.com) dan login dengan akun GitHub Anda.
   - Di dashboard Vercel, klik tombol **"Add New..."** lalu pilih **"Project"**.
   - Cari dan pilih repository `epubforge` yang baru Anda buat, lalu klik **"Import"**.
   - Pada bagian konfigurasi:
     - **Framework Preset**: Pilih **"Other"** (otomatis terdeteksi).
     - **Root Directory**: `./` (biarkan default).
     - **Build Command**: Kosongkan atau biarkan default.
     - **Output Directory**: Kosongkan atau biarkan default.
   - Klik **"Deploy"**.
   - Tunggu beberapa detik, website Anda sudah aktif di domain seperti `https://epubforge.vercel.app`! 🎉

---

### Metode 2: Deploy Cepat via Terminal (Vercel CLI)

Jika Anda ingin langsung menerbitkan website tanpa menghubungkan GitHub terlebih dahulu:

1. **Jalankan Vercel CLI via `npx`:**
   ```bash
   npx vercel
   ```

2. **Ikuti petunjuk di terminal:**
   - Masukkan email akun Vercel Anda jika diminta untuk login.
   - Set up and deploy? Tekan `Y`.
   - Which scope? Pilih akun Vercel Anda.
   - Link to existing project? Tekan `N`.
   - What's your project's name? Ketik `epubforge` (atau nama lain) lalu Enter.
   - In which directory is your code located? Tekan `Enter` (default `./`).
   - Want to modify settings? Tekan `N`.

3. **Deploy ke Production Domain:**
   ```bash
   npx vercel --prod
   ```
   Terminal akan langsung memberikan URL produksi HTTPS Anda.

---

## 💻 Menjalankan Secara Lokal (Development)

Untuk menguji aplikasi di komputer lokal:

### Opsi A: Menggunakan `npx serve`
```bash
npx serve .
```
Buka browser di `http://localhost:3000`.

### Opsi B: Menggunakan Python
```bash
python -m http.server 8080
```
Buka browser di `http://localhost:8080`.

### Opsi C: VS Code Live Server
Klik kanan pada file `index.html` dan pilih **"Open with Live Server"**.

---

## 📁 Struktur Berkas

```text
├── index.html        # Seluruh aplikasi (UI Tailwind, PDF Engine, Mammoth, JSZip, Tesseract)
├── favicon.svg       # Favicon SVG modern
├── vercel.json       # Konfigurasi header keamanan & cache untuk Vercel
├── package.json      # Metadata proyek & skrip lokal
├── .gitignore        # Berkas yang diabaikan oleh Git
└── README.md         # Dokumentasi proyek & panduan deploy
```

---

## ✨ Fitur Unggulan

- **Multi-Format Input**: Mendukung berkas `.pdf`, `.docx`, `.txt`, `.md`, dan `.html`.
- **Smart PDF Extraction**: Ekstraksi teks berdasarkan koordinat vertikal dengan pembersihan spasi dan nomor halaman otomatis.
- **Deteksi PDF Scan (OCR & Image EPUB)**: Pilihan cerdas untuk PDF hasil pemindaian kamera/scanner dengan Tesseract OCR atau kompilasi lembar gambar utuh.
- **Validitas Standar EPUB 3.3**: Menghasilkan kontainer OCF, `mimetype` uncompressed, paket `content.opf`, `nav.xhtml`, `toc.ncx`, serta validasi XHTML self-closing.
- **Live E-Reader Simulator**: Pratinjau langsung bab buku dengan pemilihan font (Serif/Sans), margin, perataan teks, dan indentasi.
