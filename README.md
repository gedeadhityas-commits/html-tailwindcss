# IGAS STORE — Tailwind CSS v4.3 CLI Project

Proyek landing page e-commerce toko urban yang menggunakan arsitektur **Tailwind CSS versi 4.3 (v4.3.5)** resmi menggunakan **Tailwind CLI Ahead-of-Time (AOT)**.

---

## 🚀 Perintah Cepat (NPM Scripts)

### 1. Mode Development (Live Watch CSS)
Otomatis mengompilasi CSS setiap kali Anda mengedit HTML atau styling:
```bash
npm run dev
```

### 2. Mode Produksi (Minified CSS)
Menghasilkan bundle CSS bersih dan terkompresi ke `dist/output.css`:
```bash
npm run build
```

### 3. Menjalankan Server Lokal
Menjalankan local web server di port 3000:
```bash
npm start
```
Buka di browser: **[http://localhost:3000](http://localhost:3000)**

---

## 📁 Struktur Berkas

* `style.css`: File CSS master dengan direktif Tailwind v4 (`@import "tailwindcss";` dan `@theme { ... }`).
* `dist/output.css`: Hasil kompilasi akhir dari Tailwind CLI v4.3 yang dipanggil oleh seluruh file HTML.
* `index.html`: Halaman utama / landing page.
* `detail-produk.html`: Halaman detail produk sepatu.
* `detail-tas.html`: Halaman detail produk tas ransel.
* `server.js`: Web server lokal berbasis Node.js.
* `package.json`: Konfigurasi dependensi (`@tailwindcss/cli` dan `tailwindcss`).

