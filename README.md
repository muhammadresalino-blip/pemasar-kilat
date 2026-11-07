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
- **Opsi jawaban diacak** setiap kuis dibuka — posisi jawaban benar tidak selalu A, jadi tidak bisa ditembak
- **Catatan pribadi per bab** (tersimpan otomatis)
- **Mode Fokus Belajar** — sembunyikan navigasi & kartu lain, perbesar teks, fokus satu bab, plus timer Pomodoro 25 menit dengan bunyi bip di akhir sesi

### Planner & Tracker
- **Planner mingguan bertanggal** — tiap hari punya tanggal nyata, status **Selesai**, navigasi minggu sebelumnya/berikutnya, dan tombol **Minggu ini**; tersimpan per minggu (`pk_planner_YYYY-MM-DD`)
- **Tracker harian** — tambah, ubah, hapus entry; tanggal yang sama otomatis digabung (tidak dobel); hapus bisa **diurungkan**
- **Streak** — hitung hari berturut-turut mencatat
- **Grafik profit 14 hari** (hijau untung, merah rugi)
- **Ringkasan mingguan** — minggu ini vs minggu lalu
- **Export gambar mingguan** — PNG 1080×1080 berisi profit, biaya, revenue, perbandingan minggu lalu, dan grafik 7 hari
- **Tombol Bagikan** — kirim PNG langsung ke WhatsApp/Instagram/Telegram lewat Web Share API di HP; di desktop otomatis unduh gambar + salin teks ringkasan
- **Target revenue bulanan** + progress bar
- **Checklist marketing mingguan** (7 tugas, reset per minggu)

### Riwayat Bulanan
- Pilih bulan → total profit, revenue, biaya iklan, hari tercatat, rata-rata per hari, hari terbaik & terburuk
- Perbandingan dengan bulan sebelumnya + progress target
- Grafik profit harian sebulan penuh + rincian harian yang bisa dibuka
- **Export CSV bulanan** (rincian harian + baris TOTAL)

### Integrasi & Data
- **Import CSV** dari Facebook/TikTok/Shopee Ads Manager (header: Tanggal, Spend, Revenue); format tanggal `YYYY-MM-DD` atau `DD/MM/YYYY`; tanggal dobel digabung, bukan diduplikasi
- **Export CSV** (planner & tracker & bulanan) dan **JSON backup lengkap**
- **Laporan bulanan** → cetak / simpan PDF (total, progress target, rincian harian)
- **Notifikasi browser** untuk reminder
- **Dark mode** hangat (hijau/krem) dan layout responsif (mobile friendly)
- **Design system** konsisten: token radius/shadow, transisi halaman halus, dukungan `prefers-reduced-motion`, fokus keyboard terlihat
- **Undo hapus** — hapus tracker/produk/semua data bisa dibatalkan lewat tombol **Urungkan** di toast
- **Banner offline** — status offline/online tanpa mengganggu; menegaskan data tetap aman di perangkat

### Navigasi Cepat
- **Pencarian Ctrl+K** (atau tombol 🔍 di header) — lompat ke fitur/aksi: tracker, export, kuis, mode fokus, planner, bagikan gambar, ganti tema, dan lainnya
- **Onboarding 3 langkah** saat pertama buka — pilih tujuan, isi target revenue, dan isi contoh planner minggu ini; bisa diulang dari tab **Data**

### PWA & Penyimpanan
- **Installable PWA** dengan ikon hijau 192/512 (termasuk maskable), works offline penuh
- **Shortcuts** di dialog install: Kalkulator, Tracker, Planner
- **Screenshots** wide & narrow untuk tampilan install yang lebih kaya
- **IndexedDB** sebagai penyimpanan utama + salinan localStorage (kompatibel data lama); snapshot lama tidak menimpa data/tema terbaru
- **Sinkron antar-tab** lewat BroadcastChannel
- **Service worker** stale-while-revalidate, jadi update tetap masuk tanpa hapus cache manual

## Cara Pakai

1. Buka `index.html` di browser (atau buka URL hasil deploy)
2. Klik tab navigasi untuk pindah fitur
3. Data tersimpan otomatis di browser (IndexedDB + localStorage)
4. Export JSON sebelum ganti browser/device
5. Tekan **Ctrl+K** untuk mencari fitur dengan cepat

## Struktur

```
PemasarKilat/
├── index.html            (semua fitur dalam satu file)
├── manifest.json         (PWA config + shortcuts + screenshots)
├── sw.js                 (service worker untuk offline)
├── icon-192.png          (ikon PWA)
├── icon-512.png          (ikon PWA)
├── screenshot-wide.png   (screenshot desktop untuk dialog install)
├── screenshot-narrow.png (screenshot HP untuk dialog install)
└── README.md
```

## Install PWA

Di Chrome/Edge/Samsung Internet:
1. Buka halaman ini (butuh http/https, bukan `file://`)
2. Klik tombol **Install** di header
3. Atau: menu → "Add to Home Screen"

Setelah terinstall, bisa dipakai offline seperti app native. Tekan lama ikon di home screen untuk shortcut Kalkulator/Tracker/Planner.

## Deploy (opsional)

Semua file statis. Upload folder ini ke GitHub Pages, Netlify, atau Cloudflare Pages — tidak butuh server/backend.
