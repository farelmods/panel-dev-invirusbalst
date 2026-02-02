# TOXIV - WhatsApp Attack Panel

Project ini adalah panel web untuk mengelola dan mengirim pesan "attack" (prank/testing) melalui bot WhatsApp menggunakan library `@whiskeysockets/baileys`.

## 📂 Struktur Project

```text
project/
├── index.js                # Server backend utama (Node.js/Express/Telegraf)
├── package.json            # Daftar dependensi
├── database/               # Folder penyimpanan data
│   ├── config.js           # Konfigurasi Token, Owner ID, Port
│   ├── user.json           # Data user untuk login web
│   └── akses.json          # Hak akses (owner, reseller, dll)
└── dewa_verse/             # Frontend HTML
    ├── websitev_4.html     # Halaman Login
    └── dashboard.html      # Halaman Dashboard Utama
```

## 🔑 Informasi Login (Cara Mendapatkan Username & Password)

### 1. Akun Default
Secara default, project ini sudah menyertakan satu akun admin yang bisa langsung digunakan:

- **Username:** `7890825241`
- **Password:** `admin`

*(Anda bisa mengubahnya langsung di file `database/user.json`)*

### 2. Membuat Akun Baru (Via Bot Telegram)
Jika Anda ingin membuat akun login baru tanpa mengedit file, gunakan bot Telegram yang sudah dikonfigurasi.

**Format Command:**
`/ckey <username>,<durasi>,<password_custom>`

**Contoh:**
- `/ckey budi,30d` (Membuat user "budi" aktif 30 hari dengan password acak)
- `/ckey admin2,1d,12345` (Membuat user "admin2" aktif 1 hari dengan password "12345")

**Catatan:**
- Command ini hanya bisa dijalankan oleh **Owner** (ID Telegram yang ada di `database/config.js`).
- Gunakan command `/listkey` untuk melihat semua akun yang aktif.

## 🚀 Cara Menjalankan

### 1. Prasyarat
Pastikan sudah terinstall:
- **Node.js** (Versi 16 atau terbaru disarankan)
- **NPM**

### 2. Instalasi
Jalankan perintah ini di terminal root project untuk menginstall semua library yang dibutuhkan:

```bash
npm install
```

### 3. Konfigurasi
Sebelum menjalankan, pastikan file konfigurasi sudah benar.

**File: `database/config.js`**
Edit file ini untuk mengubah Token Bot, ID Owner, Port, dan IP VPS.
```javascript
module.exports = {
  tokens: "TOKEN_BOT_TELEGRAM",
  owner: "ID_TELEGRAM_OWNER",
  port: "1466",
  ipvps: "IP_VPS_ANDA"
};
```

### 4. Run Server
Jalankan server dengan perintah:

```bash
npm start
```
atau
```bash
node index.js
```

Jika berhasil, akan muncul pesan:
`✓ Server aktif di port 1466`

### 5. Penggunaan
1.  Buka browser dan akses: `http://localhost:1466` (atau IP VPS Anda).
2.  Login menggunakan Username dan Password (lihat bagian **Informasi Login** di atas).
3.  Setelah login, Anda akan diarahkan ke Dashboard.
4.  Hubungkan sesi WhatsApp terlebih dahulu melalui Bot Telegram (gunakan command `/addbot` atau `/addsender`).
5.  Di Dashboard, masukkan nomor target dan pilih jenis serangan.

## ⚠️ Peringatan Keamanan
- **JANGAN** membagikan file `database/config.js` atau `database/user.json` ke orang lain karena berisi token rahasia dan password.
- Script ini untuk tujuan edukasi/testing. Penyalahgunaan tanggung jawab pengguna.
