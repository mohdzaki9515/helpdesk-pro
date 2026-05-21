# 📋 Rekod Perubahan (Changelog)

Semua perubahan penting pada projek ini akan direkodkan di sini.

Format mengikut [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

---

## [1.0.0] - 2025

### ✨ Ciri Baru
- **Portal Pengadu** — paparan utama tanpa login, borang aduan lengkap
- **Dashboard Staf/Admin** — paparan gelap profesional, login via overlay
- **Sistem Tiket** — nombor auto TKT-XXXX, keutamaan, kategori, SLA tracking
- **Team Assignment** — assign tiket dengan paparan beban kerja staf
- **Alert WhatsApp & E-mel** — notifikasi terus kepada staf & pengadu
- **Eskalasi SLA Automatik** — alert supervisor bila tiket melepasi had masa
- **Sistem Komen** — perbincangan dalaman + Nota Dalaman dalam tiket
- **Log Audit** — rekod semua tindakan pengguna
- **Tukar & Reset Kata Laluan** — meter kekuatan 4 peringkat
- **Google Sheets Sync** — backup automatik ke Google Sheets
- **Eksport Excel** — rekod tiket dalam format .xlsx
- **PWA Support** — install sebagai app di Android & iPhone
- **QR Code** — jana & cetak QR code portal pengadu
- **Rating ⭐** — pengadu beri penilaian selepas tiket selesai
- **Semak Status Tiket** — pengadu semak status tanpa login
- **Tambah Maklumat** — pengadu boleh tambah maklumat dalam tiket
- **Routing Automatik** — satu fail HTML, dua paparan berbeza

### 🔧 Teknikal
- Satu fail HTML sahaja (~392KB)
- localStorage untuk penyimpanan data
- Tiada framework, tiada server
- Responsive untuk mobile & desktop
- Cross-tab sync via localStorage events

---

## [0.9.0] - Beta

### ✨ Ciri Awal
- Sistem tiket asas
- Login staf
- Dashboard ringkas

---

*Format: `[Versi] - Tarikh`*
*Jenis perubahan: `✨ Ditambah`, `🔄 Diubah`, `🐛 Diperbaiki`, `🗑️ Dibuang`*
