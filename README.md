# Discord Redirect Web

Website sederhana untuk melakukan instant redirect HTTP (307 Temporary Redirect) ke link invitation Discord, dioptimalkan untuk di-deploy ke **Vercel**.

## 🚀 Cara Kerja
1. **Server-Level Redirect (`vercel.json`)**:
   - Vercel Edge Network akan langsung meredirect pengunjung secara instan ke URL Discord tanpa perlu render halaman terlebih dahulu.
   - Menggunakan HTTP status `307` (Temporary Redirect) sehingga browser tidak meng-cache secara permanen jika suatu saat link Discord diganti.
2. **Fallback HTML (`index.html`)**:
   - Berfungsi saat dibuka secara lokal atau jika browser memblokir header redirect. Dilengkapi meta refresh, JavaScript redirect, serta Open Graph meta tag untuk preview tampilan di media sosial.

## ⚙️ Cara Mengubah Link Discord
1. Buka file [`vercel.json`](./vercel.json) dan ganti `https://discord.gg/YOUR_INVITE_CODE` dengan link Discord kamu.
2. Buka file [`index.html`](./index.html) dan ganti `https://discord.gg/YOUR_INVITE_CODE` dengan link Discord kamu.

## 🌐 Deploy ke Vercel

### Opsi 1: Lewat Dashboard Vercel (Paling Mudah)
1. Buka [vercel.com](https://vercel.com) dan login.
2. Klik **"Add New..."** > **"Project"**.
3. Hubungkan akun GitHub dan pilih repository `SilenceIsNotFun/directlinksil`.
4. Framework Preset biarkan **Other**.
5. Klik **"Deploy"**.

### Opsi 2: Menggunakan Vercel CLI
```bash
npm i -g vercel
vercel
```
