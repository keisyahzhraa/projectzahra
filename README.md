# Cara Menjalankan Project

Panduan ini untuk anggota tim yang **sudah mendapatkan akses ke repository GitHub**.

Project terdiri dari:

* **Frontend:** Next.js
* **Backend:** Python + FastAPI

> Database belum dibahas pada panduan ini.

---

## 1. Yang Harus Sudah Terinstall

Sebelum clone project, pastikan laptop sudah memiliki:

* Git
* Python
* Node.js
* Visual Studio Code

Cek dengan membuka terminal/CMD:

```bash
git --version
python --version
node --version
npm --version
```

Jika semuanya menampilkan versi, lanjut ke langkah berikutnya.

---

# 2. Clone Project dari GitHub

Buka terminal.

Masuk ke lokasi tempat project ingin disimpan, misalnya:

```bash
cd C:\
```

Clone repository:

```bash
git clone https://github.com/USERNAME/REPOSITORY.git
```

> Ganti URL di atas dengan URL repository project yang diberikan.

Setelah selesai, masuk ke folder project:

```bash
cd REPOSITORY
```

Contoh:

```bash
cd projectzahra
```

---

# 3. Setup Backend

Masuk ke folder backend:

```bash
cd backend
```

Buat virtual environment:

```bash
python -m venv venv
```

### Aktifkan virtual environment

Untuk CMD:

```cmd
venv\Scripts\activate
```

Jika berhasil, akan muncul:

```text
(venv)
```

Contoh:

```text
(venv) C:\projectzahra\backend>
```

### Install dependency backend

Jalankan:

```bash
pip install -r requirements.txt
```

Tunggu sampai selesai.

---

# 4. Jalankan Backend

Pastikan masih berada di:

```text
(venv) C:\projectzahra\backend>
```

Jalankan:

```bash
uvicorn main:app --reload
```

Jika berhasil, akan muncul:

```text
Uvicorn running on http://127.0.0.1:8000
```

Backend sekarang berjalan di:

```text
http://127.0.0.1:8000
```

Dokumentasi API:

```text
http://127.0.0.1:8000/docs
```

**Jangan tutup terminal ini.**

---

# 5. Jalankan Frontend

Buka **terminal baru**.

Jangan menggunakan terminal backend yang sedang menjalankan Uvicorn.

Masuk ke folder frontend:

```bash
cd C:\projectzahra\frontend
```

> Sesuaikan path jika project disimpan di lokasi lain.

Install dependency frontend:

```bash
npm install
```

Setelah selesai, jalankan:

```bash
npm run dev
```

Jika berhasil, akan muncul:

```text
Local: http://localhost:3000
```

Buka browser:

```text
http://localhost:3000
```

---

# 6. Jadi Urutannya Seperti Ini

### Pertama — Clone

```bash
git clone https://github.com/USERNAME/REPOSITORY.git
cd REPOSITORY
```

### Kedua — Backend

```bash
cd backend
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
uvicorn main:app --reload
```

**Terminal backend jangan ditutup.**

### Ketiga — Frontend

Buka terminal baru:

```bash
cd frontend
npm install
npm run dev
```

---

# 7. Saat Project Sudah Pernah Di-Setup

Kalau besok ingin menjalankan project lagi, **tidak perlu membuat `venv` dan tidak perlu `npm install` lagi**.

### Terminal 1 — Backend

```bash
cd backend
venv\Scripts\activate
uvicorn main:app --reload
```

### Terminal 2 — Frontend

```bash
cd frontend
npm run dev
```

Kemudian buka:

```text
http://localhost:3000
```

---

# 8. Kenapa Harus Dua Terminal?

Karena frontend dan backend adalah dua server yang berbeda.

```text
Terminal 1
    ↓
FastAPI Backend
Port 8000


Terminal 2
    ↓
Next.js Frontend
Port 3000
```

Keduanya harus berjalan bersamaan agar website dapat berkomunikasi dengan backend.

---

# 9. Hal yang Perlu Diingat

### Backend

Sebelum menjalankan backend:

```bash
cd backend
```

Kemudian:

```bash
venv\Scripts\activate
```

Baru:

```bash
uvicorn main:app --reload
```

### Frontend

Tidak perlu `venv`.

Cukup:

```bash
cd frontend
npm run dev
```

---

# 10. Jika Ingin Menghentikan Server

Untuk menghentikan server, buka terminal server kemudian tekan:

```text
CTRL + C
```

Untuk menjalankannya lagi, ulangi perintah pada langkah sebelumnya.

---

# 11. Ringkasan

```text
CLONE
  ↓
git clone
  ↓
masuk project
  ↓
┌──────────────────────┐
│      BACKEND         │
│                      │
│ cd backend           │
│ python -m venv venv  │
│ activate venv        │
│ pip install -r ...   │
│ uvicorn ...          │
└──────────────────────┘
          │
          │
     Terminal Baru
          │
          ▼
┌──────────────────────┐
│      FRONTEND        │
│                      │
│ cd frontend           │
│ npm install           │
│ npm run dev           │
└──────────────────────┘
          │
          ▼
   localhost:3000
```

# Local Server

| Bagian   | URL                        |
| -------- | -------------------------- |
| Frontend | http://localhost:3000      |
| Backend  | http://127.0.0.1:8000      |
| API Docs | http://127.0.0.1:8000/docs |

Setelah frontend dan backend berjalan, project sudah dapat digunakan di laptop secara lokal.
