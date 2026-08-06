# SIPILCALC v2.5 - Kalkulator Engine Struktur Beton SNI 2847:2019

![Vercel Ready](https://img.shields.io/badge/Vercel-Deployment%20Ready-000000?style=for-the-badge&logo=vercel&logoColor=white)
![SNI 2847:2019](https://img.shields.io/badge/Standard-SNI%202847%3A2019-004AC6?style=for-the-badge)
![TailwindCSS](https://img.shields.io/badge/UI-TailwindCSS%20v3-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

**SIPILCALC** adalah aplikasi web kalkulator estimasi kebutuhan **Volume Cor (Beton)**, **Luas Bekisting (Formwork)**, dan **Pembesian (Rebar & BBS)** untuk elemen struktur **Kolom**, **Balok**, dan **Pelat** yang sepenuhnya mematuhi standar **SNI 2847:2019**.

---

## 🌟 Fitur Utama & Keunggulan

- 🏛️ **Perhitungan Kolom Beton**:
  - Estimasi volume cor otomatis dengan deduksi tebal pelat ($L_{\text{cor}} = L - t_{\text{pelat}}$).
  - Penghitungan sengkang (stirrups) dan crosstie / ikat silang.
  - Visualisasi SVG interaktif penampang kolom lengkap dengan sengkang, tulangan utama, crosstie, dan anotasi dimensi real-time.
- 📏 **Perhitungan Balok Beton**:
  - Estimasi volume cor dengan deduksi tebal pelat netto ($h_{\text{cor}} = h - t_{\text{pelat}}$).
  - Opsi bekisting Brutto (3 Sisi) maupun Netto (dikurangi tebal pelat).
  - Perhitungan tulangan atas menerus, bawah menerus, tumpuan, lapangan, sengkang, dan tulangan pinggang (skin rebar).
  - Visualisasi SVG interaktif penampang balok dengan indikator garis tebal pelat netto.
- 🟦 **Perhitungan Pelat Beton**:
  - Estimasi volume cor dan bekisting pelat dua arah.
  - Penulangan Arah-X (Utama) dan Arah-Y (Sekunder) untuk daerah tumpuan dan lapangan.
  - Visualisasi SVG interaktif potongan pelat lantai dengan lapisan tulangan atas dan bawah.
- 📊 **Rekapitulasi Total Proyek**:
  - Akumulasi otomatis volume cor total ($m^3$), luas bekisting total ($m^2$), dan total berat besi ($kg$).
  - Rekapitulasi kebutuhan pembesian per diameter (D6 s/d D41) beserta konversi jumlah batang standar 12 meter.
- 🎨 **Desain UI Modern & Responsive**:
  - Tampilan Bento Grid modern dengan TailwindCSS dan font JetBrains Mono / Inter.
  - Live preview visual penampang proporsional untuk tiap elemen.

---

## 📝 Catatan Revisi Terbaru (`UPDATE.md`)

Perbaikan dan penyempurnaan terbaru meliputi:
1. **Deduksi Tebal Pelat pada Volume Cor**:
   - Volume Cor Kolom kini secara presisi menghitung $L_{\text{cor}} = L - t_{\text{pelat}}$ untuk menghindari pembengkakan volume akibat tumpang tindih kolom-pelat.
   - Volume Cor Balok secara presisi menghitung $h_{\text{cor}} = h - t_{\text{pelat}}$.
2. **Pembersihan Form Kolom**:
   - Menghapus input `Sambungan / Lap Splice (mm)` dari section Kolom karena panjang tulangan utama kolom dihitung berdasarkan tinggi kolom $L$.
3. **Diagram Visual SVG Interaktif**:
   - Menambahkan diagram penampang SVG yang berfungsi secara real-time pada tab **Kolom**, **Balok**, dan **Pelat**.

---

## 🚀 Panduan Upload ke GitHub & Deploy ke Vercel

### 1. Push ke Repository GitHub
Jalankan perintah berikut pada terminal Anda:

```bash
git init
git add .
git commit -m "feat: release SIPILCALC v2.5 with SNI 2847:2019 updates & SVG drawings"
git branch -M main
git remote add origin https://github.com/USERNAME/NAMA-REPO.git
git push -u origin main
```

### 2. Deploy ke Vercel (1-Click Deployment)
Aplikasi ini sudah dikonfigurasi dengan `vercel.json` untuk hosting statis serba otomatis:

1. Buka [Vercel Dashboard](https://vercel.com/dashboard) dan klik **Add New > Project**.
2. Hubungkan akun GitHub Anda dan pilih repositori `NAMA-REPO`.
3. Vercel akan secara otomatis mendeteksi konfigurasi statis (`index.html`).
4. Klik **Deploy**. Web app Anda akan langsung live dalam beberapa detik!

---

## 💻 Menjalankan Secara Lokal (Local Development)

Anda dapat membuka file `index.html` langsung di browser, atau menggunakan server lokal HTTP:

```bash
# Menggunakan npx serve
npx serve .

# Atau menggunakan Python HTTP Server
python -m http.server 3000
```
Buka browser di `http://localhost:3000`.

---

## 📂 Struktur Repositori

```
VOLUME/
├── index.html          # Kode Utama Web Application (HTML, CSS Tailwind & Engine JS)
├── vercel.json         # Konfigurasi Deployment Vercel
├── package.json        # Manifest Proyek
├── .gitignore          # Pengaturan Pengabaian Git
├── UPDATE.md           # Catatan Revisi Permintaan Update
├── referensi.md        # Knowledge Base Engine SNI 2847:2019
├── info baru.md        # Data Parameter Ekstraksi SNI 2847:2019
├── info.md             # Dokumen Parameter Pendukung
└── README.md           # Dokumentasi Utama Repositori
```

---

## ⚖️ Lisensi
Lisensi MIT - Bebas digunakan dan dikembangkan untuk keperluan akademik, profesional, mau pun komersial.
