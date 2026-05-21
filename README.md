# 🎫 HelpDesk Pro

> Sistem Pengurusan Tiket & Aduan — Portal Pengadu + Dashboard Staf dalam **Satu Fail HTML**

[![Live Demo](https://img.shields.io/badge/Live-Demo-4f8ef7?style=flat-square&logo=github)](https://yourusername.github.io/helpdesk-pro)
[![Versi](https://img.shields.io/badge/Versi-1.0.0-29d99e?style=flat-square)](https://github.com/yourusername/helpdesk-pro)
[![Lesen](https://img.shields.io/badge/Lesen-MIT-f5a623?style=flat-square)](LICENSE)

---

## 📋 Tentang Sistem

HelpDesk Pro adalah sistem pengurusan tiket aduan teknikal yang lengkap, dibina sebagai **satu fail HTML sahaja** — tiada server diperlukan, tiada pemasangan framework, tiada database. Semua data disimpan dalam browser (`localStorage`) dan boleh di-sync ke **Google Sheets** untuk backup cloud.

### Ciri Utama

| Modul | Fungsi |
|-------|--------|
| 🌐 **Portal Pengadu** | Paparan lalai — pengadu hantar aduan tanpa log masuk |
| 🎫 **Sistem Tiket** | Nombor tiket auto (TKT-0001), keutamaan, kategori, SLA |
| 🔧 **Team Assignment** | Assign ke staf teknikal dengan paparan beban kerja |
| 📣 **Alert WA & Email** | Notifikasi terus kepada staf & pengadu via WhatsApp |
| ⏱️ **SLA Tracking** | Monitor had masa — Kritikal(4j), Tinggi(8j), Sederhana(24j), Rendah(72j) |
| 🚨 **Eskalasi Automatik** | Alert supervisor bila tiket melepasi had masa SLA |
| 💬 **Sistem Komen** | Komunikasi dalaman dalam tiket + Nota Dalaman |
| 📜 **Log Audit** | Rekod semua tindakan pengguna dalam sistem |
| 🔐 **Tukar Kata Laluan** | Self-service + admin reset dengan meter kekuatan |
| 📊 **Google Sheets Sync** | Backup automatik ke Google Sheets |
| 📲 **PWA Support** | Install sebagai app di Android & iPhone |
| 📋 **QR Code** | Jana & cetak QR code untuk portal pengadu |

---

## 🚀 Mula Guna (Cara Pantas)

### Pilihan 1 — GitHub Pages (Percuma)

```bash
# 1. Fork repo ini
# 2. Pergi ke Settings → Pages → pilih branch: main, folder: / (root)
# 3. Save → URL anda: https://yourusername.github.io/helpdesk-pro
```

### Pilihan 2 — Muat Turun & Guna Terus

```bash
# Muat turun index.html sahaja
# Buka dalam Chrome/Safari — terus boleh guna!
```

### Pilihan 3 — Host di Server Sendiri (cPanel)

```
1. Upload index.html ke public_html/
2. Akses via https://domain.com/index.html
```

---

## 📁 Struktur Projek

```
helpdesk-pro/
│
├── index.html                  ← Sistem utama (Portal + Dashboard dalam 1 fail)
│
├── scripts/
│   └── google-sheets-sync.gs   ← Google Apps Script untuk sync ke Sheets
│
├── docs/
│   └── Manual_Pengguna.pdf     ← Manual lengkap 9 bab (BM)
│
├── .github/
│   └── workflows/
│       └── deploy.yml          ← Auto-deploy ke GitHub Pages
│
├── README.md                   ← Fail ini
├── LICENSE                     ← Lesen MIT
└── .gitignore                  ← Fail yang diabaikan Git
```

---

## 👥 Peranan Pengguna

| Peranan | Akses | Akaun Demo |
|---------|-------|-----------|
| 🌐 **Pengadu** | Portal sahaja (tanpa login) | — |
| 👑 **Admin** | Akses penuh semua fungsi | `admin` / `admin123` |
| 🔧 **Teknikal** | Terima & selesai tiket | `tech1` / `tech123` |
| 👤 **Staf** | Buka & pantau tiket | `staf1` / `staf123` |

> ⚠️ **PENTING:** Tukar semua kata laluan demo sebelum guna secara live!

---

## ⚙️ Setup Google Sheets Sync

1. Buka [Google Sheets](https://sheets.new) → buat helaian baru
2. **Extensions → Apps Script** → tampal kandungan `scripts/google-sheets-sync.gs`
3. Jalankan fungsi `setupSheet()` → beri kebenaran
4. **Deploy → New Deployment → Web App** → Execute as: Me, Access: Anyone → Copy URL
5. Tampal URL dalam sistem: Dashboard → bar atas → kotak webhook

---

## 📱 Pemasangan PWA (App di Telefon)

### Android
1. Buka URL dalam **Chrome**
2. Ketik banner "Pasang HelpDesk Pro" atau Menu → "Install app"

### iPhone / iPad
1. Buka URL dalam **Safari** (mesti Safari!)
2. Ketik Share ⬆ → "Add to Home Screen" → "Add"

---

## 🔧 Tetapan SLA

Ubah had masa SLA di: **Dashboard → Butang ⚙️ SLA**

| Keutamaan | Had Lalai | Situasi |
|-----------|-----------|---------|
| 🔴 Kritikal | 4 jam | Sistem tidak berfungsi |
| 🟠 Tinggi | 8 jam | Masalah utama tanpa workaround |
| 🟡 Sederhana | 24 jam | Masalah dengan workaround |
| 🟢 Rendah | 72 jam | Pertanyaan / permintaan kecil |

---

## 📊 Data & Privasi

- **Data disimpan dalam browser** (`localStorage`) — tidak dihantar ke mana-mana server
- **Google Sheets Sync** adalah opsional — data hanya keluar bila anda tetapkan webhook
- **Tiada tracking, tiada analytics, tiada cookies pihak ketiga**
- Selamat untuk kegunaan dalaman organisasi

---

## 🛠️ Pembangunan (Development)

```bash
# Clone repo
git clone https://github.com/yourusername/helpdesk-pro.git
cd helpdesk-pro

# Buka dalam pelayar
open index.html
# atau
python3 -m http.server 8080
# Akses: http://localhost:8080
```

### Teknologi Digunakan

- **HTML5** + **CSS3** (tiada framework)
- **Vanilla JavaScript** (tiada library — kecuali XLSX & QRCode)
- [SheetJS (xlsx)](https://sheetjs.com/) — eksport Excel
- [QRCode.js](https://davidshimjs.github.io/qrcodejs/) — jana QR Code
- [Google Fonts](https://fonts.google.com/) — Syne + DM Sans
- **localStorage** — penyimpanan data browser

---

## 🤝 Sumbangan (Contributing)

Pull request dan isu dialu-alukan! Sila:

1. Fork repo ini
2. Buat branch baru: `git checkout -b feature/nama-ciri`
3. Commit: `git commit -m 'Tambah: nama ciri'`
4. Push: `git push origin feature/nama-ciri`
5. Buka Pull Request

---

## 📄 Lesen

Dilesenkan di bawah **Lesen MIT** — lihat [LICENSE](LICENSE) untuk butiran.

---

## 📞 Sokongan

- 📖 **Manual Pengguna**: [docs/Manual_Pengguna.pdf](docs/Manual_Pengguna.pdf)
- 🐛 **Laporkan Isu**: [GitHub Issues](https://github.com/yourusername/helpdesk-pro/issues)

---

<div align="center">
  <strong>HelpDesk Pro</strong> — Dibina dengan ❤️ untuk memudahkan pengurusan aduan teknikal
</div>
