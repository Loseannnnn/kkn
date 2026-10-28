# Memindahkan website ke GitHub

Paket ini berisi source code website. Ekstrak ZIP terlebih dahulu; jangan mengunggah file ZIP ke dalam repository lalu berharap GitHub mengekstraknya otomatis.

## Cara 1 — GitHub lewat browser

1. Buat repository baru di GitHub. Untuk proyek baru, `README` bawaan GitHub boleh tidak dicentang agar tidak bertabrakan dengan file lokal.
2. Ekstrak `Website_KKN_Mitigasi_Gempa_Siap_GitHub.zip`.
3. Buka folder hasil ekstraksi `website-kkn-mitigasi-gempa`.
4. Masuk ke repository GitHub, pilih **Add file → Upload files**.
5. Unggah isi folder proyek, termasuk `src`, `public`, `docs`, `package.json`, `tsconfig.json`, dan `.gitignore`. Pastikan `package.json` berada di root repository.
6. Commit perubahan.

Catatan: unggah isi folder proyek, bukan folder pembungkusnya. Jangan unggah `node_modules`, `.next`, file `.env`, atau rahasia apa pun.

## Cara 2 — Git dari terminal

Setelah membuat repository kosong di GitHub, buka terminal di folder `website-kkn-mitigasi-gempa`, lalu jalankan:

```bash
git init
git add .
git commit -m "Initial commit: KKN earthquake mitigation website"
git branch -M main
git remote add origin https://github.com/USERNAME/NAMA-REPOSITORY.git
git push -u origin main
```

Ganti `USERNAME/NAMA-REPOSITORY` dengan alamat repository milik Anda. Jangan menuliskan token atau password langsung ke source code.

## Setelah source code masuk GitHub

1. Periksa bahwa `package.json` berada di root repository.
2. Impor repository tersebut ke Vercel.
3. Biarkan Vercel mendeteksi Next.js secara otomatis.
4. Sebelum Production, pastikan `npm install`, `npm run lint`, `npm run typecheck`, dan `npm run build` sukses pada lingkungan dengan akses npm. Lingkungan pembuatan paket ini belum berhasil menjalankan tes framework penuh karena registry npm tidak dapat dijangkau.

Deployment belum dilakukan dan website belum memiliki URL produksi terverifikasi.
