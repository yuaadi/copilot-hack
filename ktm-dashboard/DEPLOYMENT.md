# KTM Dashboard Deployment Guide

## 🌐 Akses URL

Setelah deployment, akses dashboard di salah satu URL berikut:

### Opsi 1: RawGit CDN (Paling Mudah)
```
https://raw.githack.com/yuaadi/copilot-hack/yuaadi-ktm-shared-dashboard/ktm-dashboard/index.html
```

### Opsi 2: GitHub Pages
```
https://yourusername.github.io/copilot-hack/ktm-dashboard/index.html
```
*(Sesuaikan username GitHub Anda)*

### Opsi 3: Server Sendiri
```
http://domain-anda.com/ktm-dashboard/index.html
```

## 📱 Bagikan Link

Bagikan salah satu URL di atas kepada semua pengguna. Mereka dapat:
- Membuka di browser desktop atau mobile
- Tidak perlu install aplikasi
- Data tersimpan di browser mereka

## ⚡ Quick Start

1. **Clone repository**
   ```bash
   git clone https://github.com/yuaadi/copilot-hack.git
   cd copilot-hack
   git checkout yuaadi-ktm-shared-dashboard
   ```

2. **Buka di browser lokal**
   ```bash
   cd ktm-dashboard
   # Option A: Python 3
   python -m http.server 8000
   
   # Option B: Python 2
   python -m SimpleHTTPServer 8000
   
   # Option C: Node.js
   npx http-server
   ```

3. **Akses di browser**
   ```
   http://localhost:8000
   ```

## 🔒 Security Tips

1. **Ganti default password**
   - Hapus user default (admin, operator1, operator2)
   - Tambah user baru dengan password kuat

2. **Gunakan HTTPS**
   - Jika hosted di server, gunakan SSL/TLS
   - RawGit dan GitHub Pages sudah menggunakan HTTPS

3. **Backup rutin**
   - Minta semua user untuk backup JSON secara berkala
   - Simpan di cloud storage atau hard drive

## 📊 Monitoring

Data disimpan **lokal di setiap browser**. Untuk monitoring terpusat:

1. Minta sopir export data Excel secara berkala
2. Kumpulkan di spreadsheet Google Sheets atau Excel
3. Buat dashboard laporan di Excel/Sheets

## 🔄 Update

Untuk update aplikasi:

1. Edit file `index.html`
2. Commit dan push ke git
3. User perlu refresh browser (Ctrl+F5) untuk mendapat versi terbaru

---

**Ready to deploy?** Pilih salah satu URL di atas dan bagikan ke semua pengguna! 🚀
