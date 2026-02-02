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

**File: `database/user.json`**
Ini adalah akun untuk login ke panel web.
Default user:
- **Username:** `7890825241`
- **Password (Key):** `admin`

Anda bisa mengubahnya di file tersebut. Format:
```json
[
  {
    "username": "7890825241",
    "key": "admin",
    "expired": 9999999999999
  }
]
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
2.  Login dengan kredensial yang ada di `database/user.json`.
3.  Setelah login, Anda akan diarahkan ke Dashboard.
4.  Hubungkan sesi WhatsApp terlebih dahulu melalui Bot Telegram (gunakan command `/addbot` atau `/addsender`).
5.  Di Dashboard, masukkan nomor target dan pilih jenis serangan.

## ⚠️ Peringatan Keamanan
- **JANGAN** membagikan file `database/config.js` atau `database/user.json` ke orang lain karena berisi token rahasia dan password.
- Script ini untuk tujuan edukasi/testing. Penyalahgunaan tanggung jawab pengguna.
