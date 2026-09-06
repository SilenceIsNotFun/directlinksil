# Discord Redirect Web

Website sederhana untuk melakukan instant redirect HTTP (307 Temporary Redirect) ke link invitation Discord, dioptimalkan untuk di-deploy ke **Vercel**.

## 🔗 Endpoint Redirect
- **`/discord`** ➔ Langsung dialihkan secara instan ke `https://discord.gg/gCyhzsY5y2`
- **`/`** ➔ Halaman landing server Discord dengan tombol menuju `/discord`

## 🚀 Cara Kerja
1. **Server-Level Redirect (`vercel.json`)**:
   - Vercel Edge Network akan langsung meredirect pengunjung di route `/discord` secara instan ke URL Discord tanpa render halaman.
   - Menggunakan HTTP status `307` (Temporary Redirect) sehingga browser tidak meng-cache secara permanen jika suatu saat link Discord diganti.
2. **Landing & Fallback Page (`index.html`)**:
   - Ditampilkan saat membuka root domain `/`. Dilengkapi Open Graph meta tag untuk preview tampilan saat dibagikan di media sosial.

## ⚙️ Cara Mengubah Link Discord
1. Buka file [`vercel.json`](./vercel.json) dan ganti URL pada `destination`.
2. Commit dan push ke GitHub, Vercel akan otomatis melakukan update deploy.

## 🌐 Deploy ke Vercel

1. Buka [vercel.com](https://vercel.com) dan login.
2. Klik **"Add New..."** > **"Project"**.
3. Hubungkan akun GitHub dan pilih repository `SilenceIsNotFun/directlinksil`.
4. Framework Preset biarkan **Other**.
5. Klik **"Deploy"**.
