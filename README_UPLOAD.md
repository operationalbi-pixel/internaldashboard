# Cara Upload GitHub/WebView

## 1. Pasang backend Apps Script

1. Buka project Google Apps Script yang terhubung ke spreadsheet dashboard.
2. Ganti isi `Code.gs` dengan file `Code.gs` dari paket ini.
3. Pilih **Deploy → Manage deployments**.
4. Buat deployment Web App versi baru.
5. Gunakan **Execute as: Me**.
6. Pilih tingkat akses yang dapat digunakan oleh pengguna WebView Anda.
7. Salin URL deployment yang berakhiran `/exec`.

## 2. Pasang link pada index.html

Buka `index.html`, lalu cari:

```javascript
const GAS_WEB_APP_URL = 'PASTE_LINK_APPS_SCRIPT_DI_SINI';
```

Ganti menjadi:

```javascript
const GAS_WEB_APP_URL = 'https://script.google.com/macros/s/DEPLOYMENT_ID/exec';
```

Gunakan URL `/exec`, bukan URL `/dev`.

## 3. Upload ke GitHub/WebView

Upload `index.html` ke root repository atau folder yang digunakan WebView. Untuk GitHub Pages, file harus tetap bernama `index.html`.

Setiap kali `Code.gs` berubah, buat deployment Apps Script versi baru. Link `/exec` biasanya tetap sama apabila Anda mengedit deployment yang sudah ada.

## Catatan keamanan

Dashboard mengambil data internal melalui Apps Script. Jangan gunakan GitHub Pages publik atau deployment API publik tanpa memastikan tingkat aksesnya sesuai kebijakan perusahaan.
