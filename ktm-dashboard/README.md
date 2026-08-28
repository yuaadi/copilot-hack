# KTM Kebun Tebu Mas — Dashboard Sistem Data Pengiriman Tebu MBS

Aplikasi web yang responsif untuk mengelola data pengiriman tebu dengan sistem bonus berdasarkan jumlah pengiriman. Setiap sopir yang mencapai 5 kali pengiriman MBS mendapatkan bonus gula 1 kg, dan setiap kelipatan 5 pengiriman berikutnya mendapat tambahan 1 kg lagi.

## 🌐 Akses Online

Dashboard dapat diakses oleh semua orang di:
- **URL**: `https://raw.githack.com/yuaadi/copilot-hack/yuaadi-ktm-shared-dashboard/ktm-dashboard/index.html`

Atau jika di-deploy di GitHub Pages:
- Sesuaikan dengan URL GitHub Pages repository Anda

## ✨ Fitur Utama

- **Dashboard Interaktif** 📊
  - Statistik real-time: Total sopir, pengiriman, bonus gula
  - Daftar sopir yang mencapai bonus
  - Ringkasan progres per sopir

- **Input Data** ➕
  - Form lengkap untuk input data pengiriman
  - Unggah hingga 4 foto per pengiriman
  - Validasi data otomatis

- **Manajemen Data** 🚚
  - Lihat semua data pengiriman dalam tabel
  - Export ke Excel (.xls) untuk laporan
  - Backup/Import JSON untuk keamanan data

- **Multi-User** 👥
  - Setiap akun memiliki data terpisah per browser
  - 3 akun default (admin, operator1, operator2)
  - Login/Logout yang aman

## 🔐 Akun Default

| Username | Password | Role |
|----------|----------|------|
| admin | admin123 | Admin |
| operator1 | 123456 | User |
| operator2 | 123456 | User |

⚠️ **Ganti password default untuk keamanan!**

## 💾 Penyimpanan Data

- **Penyimpanan Lokal**: Data disimpan di browser menggunakan LocalStorage + IndexedDB
- **Per Browser**: Setiap browser/device memiliki penyimpanan terpisah
- **Per Akun**: Setiap akun menyimpan data tersendiri

### Backup Data

1. Klik tombol **💾 Backup JSON** di tab "Data Pengiriman"
2. File JSON akan otomatis terunduh
3. Simpan file di tempat yang aman

### Import Data

1. Klik tombol **↥ Import JSON** di tab "Data Pengiriman"
2. Pilih file backup JSON
3. Data akan dimuat dan ditampilkan

## 📋 Fitur Bonus Gula

### Program MBS (Manis Bersih Segar)

- **Pencapaian**: Setiap sopir mencapai 5 kali pengiriman MBS = 1 kg gula
- **Kelipatan**: 10 pengiriman = 2 kg, 15 pengiriman = 3 kg, dst.
- **Tracking**: Progress bonus ditampilkan di dashboard dengan visual bar

### Dashboard Bonus

Sopir yang mencapai minimal 5 pengiriman akan tampil di bagian **"🎁 Sopir Otomatis Mendapat Bonus Gula"** dengan:
- Nama sopir
- Nomor polisi kendaraan
- Jumlah bonus yang didapatkan
- Total kilogram gula

## 🎯 Cara Menggunakan

### 1. Akses Dashboard
- Buka link URL di browser (desktop, tablet, atau mobile)
- Login dengan akun yang tersedia

### 2. Tambah Data Pengiriman
- Klik tab **➕ Tambah Pengiriman**
- Isi semua field yang diperlukan:
  - Nama Sopir
  - Nomor Polisi Kendaraan
  - Nama Mitra
  - Nomor TTA / Nomor TTA
- Unggah 4 foto (minimal 1 foto)
- Klik **Simpan Pengiriman**

### 3. Lihat Data
- Klik tab **🚚 Data Pengiriman**
- Lihat tabel lengkap semua pengiriman
- Hapus data dengan tombol **Hapus** jika diperlukan

### 4. Export & Backup
- **Export Excel**: Klik **⬇ Simpan Excel (.xls)** untuk laporan
- **Backup JSON**: Klik **💾 Backup JSON** untuk backup
- **Import JSON**: Klik **↥ Import JSON** untuk restore data

## 🔧 Teknis

### Persyaratan
- Browser modern (Chrome, Firefox, Safari, Edge)
- JavaScript diaktifkan
- Minimal 50MB storage browser (untuk foto)

### Kompatibilitas
- ✅ Desktop (Windows, Mac, Linux)
- ✅ Tablet (iPad, Android Tablet)
- ✅ Mobile (iPhone, Android Phone)
- ✅ Offline setelah dimuat pertama kali

### Storage
- **LocalStorage**: Menyimpan user accounts & metadata
- **IndexedDB**: Menyimpan data pengiriman & foto (format Base64)

## ⚙️ Konfigurasi

### Menambah User Baru

Edit di browser console atau modifikasi kode:

```javascript
// Di console browser setelah login
let users = JSON.parse(localStorage.getItem('ktm_mbs_users_v2'));
users.push({username: 'user_baru', password: 'password123', role: 'user'});
localStorage.setItem('ktm_mbs_users_v2', JSON.stringify(users));
```

### Mengganti Password

```javascript
let users = JSON.parse(localStorage.getItem('ktm_mbs_users_v2'));
let user = users.find(u => u.username === 'admin');
if(user) user.password = 'password_baru';
localStorage.setItem('ktm_mbs_users_v2', JSON.stringify(users));
```

## 🚀 Deployment

### GitHub Pages
1. Push ke branch yang sesuai
2. Aktifkan GitHub Pages di settings
3. Akses via: `https://yourusername.github.io/copilot-hack/ktm-dashboard/`

### RawGit/GitHack
Gunakan CDN untuk akses langsung:
- `https://raw.githack.com/yuaadi/copilot-hack/branch/ktm-dashboard/index.html`

### Server Lokal
```bash
# Python 3
python -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000

# Node.js (dengan http-server)
npx http-server
```

## 📧 Support

Untuk pertanyaan atau laporan bug, hubungi tim KTM.

## 📄 Lisensi

Aplikasi ini dibuat untuk KTM Kebun Tebu Mas.

---

**Catatan**: Data disimpan di browser lokal. Untuk akses data terpusat di berbagai device, diperlukan database dan API backend.
