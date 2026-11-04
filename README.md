# PemasarKilat

Aplikasi belajar & kalkulator digital marketing. Gratis, offline-first, tanpa akun.

## Fitur

### Kalkulator & Analisis
- **ROAS, CPA, CTR/CPM, Break-Even Point** — dengan validasi input dan tooltip rumus
- **Multi-platform**: TikTok Ads (engagement rate, CPM, ROAS), Shopee (komisi, profit bersih), Facebook (CTR, CPC, frequency, CPA), Google (CTR, CPC, conversion rate, CPA)
- **Margin & Markup Multi-Produk** — bandingkan profit beberapa produk, warna indikator (merah <20%, kuning 20-50%, hijau >50%)

### Konten & Template
- **8 template caption** (promo, tips, testimoni, behind the scenes, launch, fakta unik, storytelling, CTA)
- **Brief iklan** + preset per industri (F&B, fashion, jasa, skincare)
- **Chat sales response**
- **AI Caption Generator** — OpenAI atau Gemini dengan API key sendiri; cache 20 hasil terakhir supaya hemat biaya; tombol **Alternatif Offline** untuk generate tanpa API

### Belajar
- **4 bab materi** + studi kasus nyata
- **Kuis per bab** (3 soal) + **kuis campur** (10 soal acak dari 21 bank soal)
- **Catatan pribadi per bab** (tersimpan otomatis)
- **Mode Fokus Belajar** — sembunyikan navigasi & kartu lain, perbesar teks, fokus satu bab, plus timer Pomodoro 25 menit dengan bunyi bip di akhir sesi

### Planner & Tracker
- **Planner mingguan** — content calendar auto-save + auto-generate jadwal
- **Tracker harian** — tambah, ubah, hapus entry; ringkasan total profit
- **Streak** — hitung hari berturut-turut mencatat
- **Grafik profit 14 hari** (hijau untung, merah rugi)
- **Ringkasan mingguan** — minggu ini vs minggu lalu
- **Export gambar mingguan** — PNG 1080×1080 berisi profit, biaya, revenue, perbandingan minggu lalu, dan grafik 7 hari; siap dibagikan
- **Target revenue bulanan** + progress bar
- **Checklist marketing mingguan** (7 tugas, reset per minggu)

### Integrasi & Data
- **Import CSV** dari Facebook/TikTok/Shopee Ads Manager (header: Tanggal, Spend, Revenue)
- **Export CSV** (planner & tracker) dan **JSON backup lengkap**
- **Laporan bulanan** → cetak / simpan PDF (total, progress target, rincian harian)
- **Gambar ringkasan mingguan** (PNG 1080×1080) untuk story/feed atau laporan klien
- **Notifikasi browser** untuk reminder
- **Dark mode** hangat (hijau/krem) dan layout responsif (mobile friendly)
- **Design system** konsisten: token radius/shadow, transisi halaman halus, dukungan `prefers-reduced-motion`, fokus keyboard terlihat

### PWA & Penyimpanan
- **Installable PWA** dengan ikon 192/512, works offline penuh
- **IndexedDB** sebagai penyimpanan utama + salinan localStorage (kompatibel data lama)
- **Service worker** stale-while-revalidate, jadi update tetap masuk tanpa hapus cache manual

## Cara Pakai

1. Buka `index.html` di browser (atau buka URL hasil deploy)
2. Klik tab navigasi untuk pindah fitur
3. Data tersimpan otomatis di browser (IndexedDB + localStorage)
4. Export JSON sebelum ganti browser/device

## Struktur

```
PemasarKilat/
├── index.html      (semua fitur dalam satu file)
├── manifest.json   (PWA config)
├── sw.js           (service worker untuk offline)
├── icon-192.png    (ikon PWA)
├── icon-512.png    (ikon PWA)
└── README.md
```

## Install PWA

Di Chrome/Edge/Samsung Internet:
1. Buka halaman ini (butuh http/https, bukan `file://`)
2. Klik tombol **Install** di header
3. Atau: menu → "Add to Home Screen"

Setelah terinstall, bisa dipakai offline seperti app native.

## Deploy (opsional)

Semua file statis. Upload folder ini ke GitHub Pages, Netlify, atau Cloudflare Pages — tidak butuh server/backend.
