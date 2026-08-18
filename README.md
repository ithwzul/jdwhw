# 🚀 Jadwalin HW - Setup & Deployment Guide (GitHub + Google Apps Script)

Panduan integrasi **Frontend di GitHub (GitHub Pages)** dengan **Backend di Google Apps Script (Google Sheets)**.

---

## 🔗 Endpoint Google Apps Script Aktif
- **Web App URL**: `https://script.google.com/a/macros/fdcdentalclinic.co.id/s/AKfycbyG4bQql49IVq5pRUOgXdQKoRrh4VczvBb40fyJCyXF8k3FlIr9j2_I7rFz_LgY7I31/exec`

---

## 📋 Langkah 1: Update Kode di Google Apps Script (`code.gs`)
1. Buka [Google Sheets](https://sheets.google.com) database Anda.
2. Klik menu **Extensions > Apps Script** (Ekstensi > Apps Script).
3. Salin seluruh isi file [`code.gs`](./code.gs) ke file `Code.gs` di editor Apps Script.
4. **PENTING (Perizinan Web App)**:
   - Klik tombol **Deploy** (Terapkan) > **Manage deployments** (Kelola penerapan).
   - Klik ikon **Edit (pensil)** pada deployment aktif Anda.
   - Ubah **Version** menjadi **New version** (Versi baru).
   - Pastikan **Who has access** diatur ke **"Anyone"** (Siapa saja, bahkan anonim) agar frontend GitHub dapat mengirim dan menerima data via REST API tanpa terblokir autentikasi akun Google di browser.
   - Klik **Deploy**.

---

## 📋 Langkah 2: Upload ke GitHub & Aktifkan GitHub Pages

### Opsi A: Lewat Git Terminal / Command Prompt
Buka terminal di folder ini (`jadwalin-hw`), lalu jalankan perintah:

```bash
git init
git add .
git commit -m "feat: initial commit jadwalin-hw frontend & backend"
git branch -M main
git remote add origin https://github.com/<USERNAME-GITHUB-ANDA>/<NAMA-REPOSITORY>.git
git push -u origin main
```

### Opsi B: Lewat Web GitHub (Drag & Drop)
1. Buat repository baru di [github.com/new](https://github.com/new) (misal: `jadwalin-hw`).
2. Klik tombol **"uploading an existing file"**.
3. Drag & drop file `index.html`, `code.gs`, dan `README.md`.
4. Klik **Commit changes**.

---

## 🌐 Langkah 3: Aktifkan GitHub Pages (Hosting Gratis)
1. Buka repository Anda di GitHub.
2. Klik tab **Settings** (Pengaturan) > pilih menu **Pages** di sebelah kiri.
3. Di bagian **Build and deployment > Branch**:
   - Pilih branch `main`
   - Folder: `/ (root)`
   - Klik tombol **Save**.
4. Tunggu 1–2 menit, link website Anda akan aktif di:
   `https://<USERNAME-GITHUB-ANDA>.github.io/<NAMA-REPOSITORY>/`

---

## 🔑 Akun Default untuk Login

| Email / Username | Password | Role | Keterangan |
|---|---|---|---|
| `admin@jadwalinhw.com` | `admin123` | **Admin** | Akses penuh (Dashboard, Master Aset, Master Checklist, New Schedule, Wo) |
| `budi@jadwalinhw.com` | `tech123` | **Technician** | Khusus teknisi (Hanya melihat jadwal/tugas atas nama Budi Teknisi) |
| `andi@jadwalinhw.com` | `tech123` | **Technician** | Khusus teknisi (Tugas atas nama Andi Teknisi) |
| `deni@jadwalinhw.com` | `tech123` | **Technician** | Khusus teknisi (Tugas atas nama Deni Teknisi) |

---

## ✨ Fitur Utama yang Terintegrasi
- 📸 **Camera Direct Capture**: Langsung membuka hardware kamera belakang smartphone via browser untuk dokumentasi.
- ✍️ **Digital Canvas Signature**: Tanda tangan digital teknisi yang langsung tersimpan ke Google Drive.
- 📅 **Jadwalin Kuy**: Agenda kalender interaktif dengan date strip & filter terpadu.
- 📋 **TugasKu Kanban**: Papan Kanban drag-and-drop untuk manajemen status Work Order.
- 📄 **Cetak PDF & Dispatch Email**: Sertifikat laporan resmi langsung terkirim via Gmail API.
