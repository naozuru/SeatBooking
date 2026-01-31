# 🎟️ Theater Seat Booking System

Sistem pemesanan kursi teater berbasis web yang terintegrasi dengan **Google Spreadsheet** dan **Google Apps Script**.  
Digunakan untuk keperluan acara sekolah (teater, pentas seni, seminar) dengan sistem login masing-masing peserta.

---

## ✨ Fitur Utama

- 🔐 Login menggunakan **username & password** (data dari Spreadsheet)
- 🪑 Pemilihan kursi secara visual (seperti bioskop)
- ⭐ **Kursi VIP** (diatur dari Spreadsheet)
- 🚶 **Aisle / jalan tengah** (layout fleksibel)
- 📊 Batas maksimal kursi per user (2, 3, atau custom)
- 🏫 Multi level peserta: **ECC, ES, JHS, SHS**
- 📱 Responsive (desktop & mobile)
- ☁️ Tanpa database tambahan (cukup Google Sheets)

---

## 🧱 Teknologi yang Digunakan

- **Frontend**  
  - HTML  
  - CSS (Grid & Flexbox)  
  - JavaScript (Vanilla)

- **Backend**  
  - Google Apps Script (Web App)
  - Google Spreadsheet sebagai database

---

## 📂 Struktur Spreadsheet

### 1️⃣ Sheet: `CONFIG`

Digunakan untuk mengatur layout dan aturan sistem.

| KEY | VALUE |
|---|---|
| ROWS | 10 |
| COLUMNS | 12 |
| AISLE_COLUMN | 6 |
| VIP_ROWS | A,B |
| VIP_COLUMNS | 4,5,6 |
| ACTIVE_LEVELS | ECC,ES,JHS,SHS |
| MAX_SEAT_PER_USER | 2 |

---

### 2️⃣ Sheet: `DATA-SISWA-[LEVEL]`

Contoh: `DATA-SISWA-SHS`, `DATA-SISWA-ES`

| Kolom | Keterangan |
|---|---|
| A | Fullname |
| H | Username |
| I | Password |
| J | Max Seat |
| K | Seat Taken |

📌 **Max Seat bisa berbeda tiap orang**

---

### 3️⃣ Sheet: `SEATS`

Digunakan untuk menyimpan kursi yang sudah dibooking.

| SEAT_CODE | STATUS | USERNAME | LEVEL |
|---|---|---|---|
| A1 | BOOKED | user01 | SHS |

---

## 🚀 Cara Deploy Google Apps Script

1. Buka Google Spreadsheet
2. Extensions → Apps Script
3. Paste seluruh kode backend
4. Deploy → New Deployment
5. Pilih **Web App**
6. Set:
   - Execute as: **Me**
   - Who has access: **Anyone**
7. Salin URL Web App dan tempel ke frontend:

```js
const WEBAPP_URL = "https://script.google.com/macros/s/XXXXX/exec";
```

---
## Demo

https://naozuru.github.io/SeatBooking/

