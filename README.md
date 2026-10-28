# SIAGA — Website Edukasi KKN Mitigasi Gempa Bumi

Portal edukasi warga berbahasa Indonesia berbasis Next.js App Router, TypeScript, React, dan Tailwind CSS v4. Source code ini dikembangkan dari starter `KKN_Project_Pack(3).zip` yang diberikan pengelola. Reference Pack menyimpan inventaris sumber, peta konten, status video, dan catatan verifikasi yang mendasari isi situs.

## Isi website

- `/` — beranda dengan tahap pembelajaran dan ringkasan program.
- `/materi` — katalog materi, pencarian, serta filter topik.
- `/materi/persiapan-sebelum-gempa` — persiapan sebelum gempa.
- `/materi/tindakan-saat-gempa` — perlindungan saat gempa.
- `/materi/langkah-setelah-gempa` — evakuasi dan kewaspadaan setelah gempa.
- `/video` — status video; tidak membuat iframe untuk video yang belum diperiksa.
- `/program-kerja` — program kerja sesuai data pengelola tanpa hasil kegiatan rekaan.
- `/tentang` — profil yang diberikan dan bagian yang perlu dikonfirmasi.
- `/referensi` — sumber resmi dengan klaim yang didukung dan keterbatasan.
- `/kontak` — empty state sampai kontak publik disahkan.
- Halaman 404 khusus.

## Prasyarat dan menjalankan

- Node.js 20.9+ (ditetapkan di `package.json` melalui `engines`).
- npm.

```bash
npm install
npm run dev
```

Buka alamat lokal yang dicetak oleh Next.js. Untuk pemeriksaan produksi:

```bash
npm run lint
npm run typecheck
npm run build
npm run start
```

## Konten dan status

Data berada di `src/data/content.ts`; tipe data berada di `src/types/content.ts`. Konten yang tampil harus berstatus `reviewed` atau `published`. Status `draft` tidak ditampilkan. Materi awal saat ini berstatus `reviewed`: sumber umum sudah diperiksa saat penyusunan, tetapi tim KKN masih perlu menyesuaikan rencana lokal dan menyetujui penggunaannya dalam sosialisasi. Jangan mengubah status menjadi `published` sebelum proses review internal selesai.

Video dari pengelola disimpan sebagai kandidat `needs-verification`. Situs tidak menyematkan video dan menyatakan status secara terbuka sampai judul, kanal, ketersediaan, kecocokan, dan izin embedding dapat diperiksa langsung.

## Status dan hal yang belum siap publikasi

- Periode KKN mengikuti konfirmasi pengelola: **Oktober–Desember 2026**.
- Target deployment telah ditentukan: **Vercel**. Deployment belum dilakukan dan URL produksi belum tersedia.
- Lokasi sementara mengikuti hasil penelusuran sumber pemerintah: **Padukuhan Pucanganom, Kalurahan Sumberagung, Kapanewon Moyudan, Kabupaten Sleman, Daerah Istimewa Yogyakarta**. Karena PDF rujukan SPMB 2026 tidak dapat dibuka langsung oleh alat verifikasi, minta konfirmasi akhir dari tim KKN/pemerintah kalurahan.
- Konfirmasi identitas kelompok dan rincian program oleh pihak KKN.
- Periksa langsung video YouTube yang diberikan; jika gagal, pilih video alternatif dari kanal resmi dan catat buktinya.
- Kontak publik belum diberikan; jangan tampilkan kontak personal tanpa persetujuan.
- Dapatkan persetujuan materi dari tim KKN/pihak kalurahan sebelum status `published`.
- Selesaikan lint, typecheck, production build, dan browser smoke test pada mesin yang memiliki akses registry npm sebelum deployment.

## Privasi dan keamanan

Tidak ada admin, database, autentikasi, analitik, formulir warga, atau pengumpulan data pribadi. Jangan memasukkan nomor pribadi, foto warga, atau dokumen lokal tanpa izin. Jangan menyimpan rahasia atau API key di repository.

## Target deployment: Vercel

Panduan khusus deployment tersedia di `docs/DEPLOYMENT.md`. Vercel dapat mendeteksi Next.js dari `package.json`; tidak ada variabel lingkungan yang diperlukan oleh starter saat ini. Jangan membuat deployment production sebelum pengujian build dan tinjauan konten selesai.

## Paket referensi

Baca `KKN_Reference_Pack.zip` secara terpisah. Gunakan `KKN_Reference_Pack/09_Catatan_Verifikasi/source_register.csv` untuk melacak sumber; lihat `docs/CONTENT_GUIDE.md` untuk mengubah konten dengan aman. `MASTER_PROMPT_WEBSITE_KKN.txt` adalah spesifikasi kerja yang dapat digunakan lagi, bukan bukti bahwa deployment sudah dilakukan.
