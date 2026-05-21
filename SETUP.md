# ⚙️ Panduan Setup Lengkap — HelpDesk Pro

## 📋 Isi Kandungan

1. [Cara Paling Mudah — GitHub Pages](#1-cara-paling-mudah--github-pages)
2. [Setup Google Sheets Sync](#2-setup-google-sheets-sync)
3. [Tetapkan Maklumat Organisasi](#3-tetapkan-maklumat-organisasi)
4. [Tambah Pengguna Baru](#4-tambah-pengguna-baru)
5. [Konfigurasi SLA](#5-konfigurasi-sla)
6. [Pemasangan PWA](#6-pemasangan-pwa)
7. [Tips Deployment Lain](#7-tips-deployment-lain)

---

## 1. Cara Paling Mudah — GitHub Pages

### Langkah 1: Fork atau Upload ke GitHub

**Kaedah A — Fork (jika pakai repo ini):**
```
1. Klik butang "Fork" di atas kanan
2. Pilih akaun GitHub anda
3. Klik "Create fork"
```

**Kaedah B — Upload manual:**
```
1. Buat repo baru di github.com/new
2. Namakan: helpdesk-pro (atau nama lain)
3. Pilih "Public" (untuk GitHub Pages percuma)
4. Klik "Create repository"
5. Upload semua fail dari folder ini
```

### Langkah 2: Aktifkan GitHub Pages

```
1. Pergi ke repo → Settings → Pages (panel kiri)
2. Source: "Deploy from a branch"
3. Branch: main  |  Folder: / (root)
4. Klik Save
5. Tunggu 1-2 minit
6. URL anda: https://[username].github.io/[repo-name]
```

### Langkah 3: Test

```
Buka URL di atas — Portal Pengadu akan muncul terus!
Klik "🔐 Log Masuk Staf" → masukkan admin / admin123
```

---

## 2. Setup Google Sheets Sync

### Langkah 1: Buat Google Sheets

```
1. Pergi ke sheets.new
2. Namakan fail: "HelpDesk Pro - Rekod Tiket"
```

### Langkah 2: Buka Apps Script

```
1. Menu: Extensions → Apps Script
2. Tetingkap editor baru terbuka
3. Padam semua kod yang ada
```

### Langkah 3: Tampal Kod

```
1. Buka fail: scripts/google-sheets-sync.gs
2. Salin semua kandungan
3. Tampal dalam editor Apps Script
4. Klik 💾 Save (Ctrl+S)
```

### Langkah 4: Jalankan Setup

```
1. Pilih fungsi: setupSheet (dari dropdown)
2. Klik ▶ Run
3. Dialog kebenaran muncul → Klik "Review permissions"
4. Pilih akaun Google anda
5. Klik "Allow"
6. Header Sheets dikonfigurasi automatik ✅
```

### Langkah 5: Deploy sebagai Web App

```
1. Klik Deploy → New deployment
2. Type: Web app
3. Execute as: Me
4. Who has access: Anyone
5. Klik Deploy
6. Salin URL yang diberikan (panjang, bermula dengan https://script.google.com/...)
```

### Langkah 6: Tetapkan dalam HelpDesk Pro

```
1. Buka HelpDesk Pro → Log Masuk sebagai Admin
2. Di bar atas → kotak URL yang ada "Paste Google Sheets webhook URL..."
3. Tampal URL tadi
4. Klik "🔗 Uji" — patut dapat "✅ Berjaya"
5. Klik "🔄 Sync" untuk hantar semua data
```

---

## 3. Tetapkan Maklumat Organisasi

Buka `index.html` dalam text editor, cari dan tukar:

```html
<!-- Cari baris ini (dalam hero portal) -->
🎯 HelpDesk Pro

<!-- Tukar kepada nama organisasi anda, contoh: -->
🎯 Jabatan IT - Syarikat ABC
```

Cari `HelpDesk Pro` dalam fail dan ganti dengan nama organisasi anda di tempat yang sesuai.

---

## 4. Tambah Pengguna Baru

### Via Dashboard (Cara Mudah)

```
1. Log masuk sebagai Admin
2. Menu: ⚙️ Pengguna & Team
3. Klik "+ Pengguna"
4. Isi: Username, Kata Laluan, Nama, Peranan
5. Klik Simpan
```

### Peranan Yang Ada

| Peranan | Akses |
|---------|-------|
| admin | Semua fungsi |
| tech | Terima & selesai tiket yang diassign |
| staf | Buka tiket sahaja |

### Padam Akaun Demo

```
1. Log masuk sebagai admin
2. Pengguna & Team → Cari staf1, tech1
3. Klik 🗑 Padam
4. Tukar kata laluan akaun admin anda sendiri!
```

---

## 5. Konfigurasi SLA

```
1. Dashboard → Klik butang "⚙️ SLA" (kanan atas)
2. Ubah had masa mengikut keperluan organisasi
3. Isi maklumat Supervisor (untuk eskalasi)
4. Pilih selang semakan automatik
5. Klik "💾 Simpan Tetapan"
```

**Cadangan had masa mengikut organisasi:**

| Jenis Organisasi | Kritikal | Tinggi | Sederhana | Rendah |
|-----------------|---------|--------|-----------|--------|
| IT Syarikat Kecil | 4j | 8j | 24j | 72j |
| Jabatan Kerajaan | 2j | 4j | 8j | 24j |
| Hospital/Klinik | 1j | 2j | 4j | 8j |
| Pendidikan | 8j | 24j | 48j | 168j |

---

## 6. Pemasangan PWA

### Android

```
1. Buka URL sistem dalam Chrome Android
2. Tunggu beberapa saat — banner akan muncul di bawah
3. Ketik "Pasang" atau "Install"
4. Ikon muncul di Home Screen
```

**Jika banner tidak muncul:**
```
Chrome → Menu (⋮) → "Add to Home Screen" atau "Install app"
```

### iPhone / iPad (MESTI SAFARI)

```
1. Buka URL dalam Safari (BUKAN Chrome/Firefox)
2. Ketik ikon Share (⬆) di bar bawah
3. Scroll ke bawah → "Add to Home Screen"
4. Ketik "Add" (atas kanan)
5. Ikon muncul di Home Screen
```

---

## 7. Tips Deployment Lain

### Netlify (Percuma, HTTPS automatik)

```
1. Pergi ke app.netlify.com
2. "Add new site" → "Deploy manually"
3. Drag & drop folder helpdesk-pro ke kawasan upload
4. URL automatik: https://[nama-rawak].netlify.app
5. Boleh tukar domain di Settings → Domain management
```

### cPanel Hosting

```
1. Log masuk cPanel
2. File Manager → public_html
3. Upload index.html (dan fail lain jika perlu)
4. Akses via: https://domain.com/ atau https://domain.com/index.html
```

### Vercel

```bash
npm i -g vercel
cd helpdesk-pro
vercel
# Ikut arahan, URL automatik diberikan
```

### Cloudflare Pages

```
1. Cloudflare Dashboard → Pages → Create a project
2. "Direct Upload" → Upload folder helpdesk-pro
3. URL: https://[nama].pages.dev
```

---

## ❓ Soalan Lazim

**Q: Boleh guna offline?**
A: Ya! Selepas PWA dipasang, sistem boleh digunakan tanpa internet. Data disimpan dalam telefon/komputer.

**Q: Data hilang bila clear cache?**
A: Ya — sebab itu setup Google Sheets Sync adalah penting untuk backup.

**Q: Boleh guna lebih dari satu peranti?**
A: Data tidak auto-sync antara peranti. Guna Google Sheets Sync sebagai pusat data bersama.

**Q: Berapa ramai pengguna boleh guna serentak?**
A: localStorage adalah per-peranti. Untuk penggunaan bersama, setiap peranti ada salinan data sendiri. Sync via Google Sheets untuk keselarasan.

**Q: HTTPS diperlukan?**
A: Untuk PWA — Ya. GitHub Pages, Netlify, Vercel semua ada HTTPS percuma.

---

*Masalah lain? Buka [GitHub Issue](https://github.com/yourusername/helpdesk-pro/issues)*
