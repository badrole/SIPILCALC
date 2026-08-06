- [x] KONFIGURASI GITIGNORE UNTUK DEPLOYMENT GITHUB & VERCEL:
  - **Pembuatan File `.gitignore` Komprehensif**: Mengonfigurasi aturan `.gitignore` presisi untuk mencegah pengunggahan folder `dist/` (yang berisi paket `.exe` ukuran ~190MB agar tidak terkena error GitHub Limit 100MB), `node_modules/`, `.vercel/`, file `.env`, serta file log/sampah OS.
- [x] PENGEMASAN APLIKASI DESKTOP WINDOWS (.EXE NATIVE APP):
  - **Packaging Desktop Executable (`.exe`)**: Mengonversi web app SIPILCALC menjadi **Aplikasi Desktop Windows (.exe)** mandiri berbasis Electron versi 34.0.0.
  - **Lokasi Executable**: Paket `.exe` tersimpan dan siap dijalankan di `F:\SIPIL\PKL\SIPILCALC\dist\SIPILCALC-Desktop-win32-x64\SIPILCALC-Desktop.exe`.
  - **Performa 100% Offline & Native**: Seluruh fitur (kalkulasi Balok, Kolom, Pelat, visualisasi SVG, export ExcelJS, serta Live Preview PDF & Print Engine) dapat dijalankan 100% offline dengan double-click pada `SIPILCALC-Desktop.exe` tanpa perlu membuka browser internet.
- [x] GENERATOR LAPORAN PDF PROFESIONAL (STANDAR MARGIN KIRI 3cm, ATAS/KANAN/BAWAH 2cm, WEBSITES THEME, REBAR BREAKDOWN & NO EMOJI):
  - **Penyesuaian Margin Laporan**: Mengatur padding halaman cetak A4 (`.print-page`) secara presisi: **Kiri 3 cm (30 mm)** (ruang penjilidan/binding), **Atas 2 cm (20 mm)**, **Kanan 2 cm (20 mm)**, dan **Bawah 2 cm (20 mm)** (`padding: 20mm 20mm 20mm 30mm`).
  - **Halaman Sampul Minimalis & Logo Besar Terpusat**: Mengubah Halaman Sampul menjadi format berskala penuh yang bersih dengan **Logo Terpusat Berukuran Besar** di tengah atas, Judul Sistem & Laporan, serta Tanggal Ekspor di bagian bawah (menghapus total kotak metadata/KPI/emoji).
  - **Revisi Judul & Rumus Konversi M vs MM**: Menghapus frasa "(BAHASA MANUSIA)" menjadi `1. METODOLOGI & RUMUS PERHITUNGAN STRUKTUR` dan memperjelas rumus konversi `mm` ke `m` dengan membagi `1.000` (`Lebar/1.000 × Tinggi/1.000 × Bentang/1.000`).
  - **Perbaikan Total Panjang & Batang Subtotal Besi**: Memperbaiki kalkulasi subtotal pada baris `SUBTOTAL BESI [item.nama]` di tiap tabel elemen sehingga `Total Panjang (m)`, `Total Berat (kg)`, dan `Total Batang 12m` terhitung 100% presisi dan lengkap untuk semua elemen di seluruh lantai (Lantai 1 s/d Lantai N).
  - **Tabel Ringkasan Rekapitulasi Per Lantai**: Menambahkan tabel ringkasan total di akhir setiap bab lantai yang menjumlahkan total Volume Cor Net ($\text{m}^3$), Luas Bekisting Net ($\text{m}^2$), Total Panjang Besi ($\text{m}$), Total Berat Besi ($\text{kg}$), dan Total Batang 12m ($\text{btg}$) untuk lantai tersebut.
  - **Rincian Pembesian Lengkap Per Sub-Item & Rekapitulasi Diameter**: Menambahkan tabel rincian kebutuhan besi per sub-elemen (Tulangan Utama, Sengkang, Crosstie, Lapisan Atas/Bawah) lengkap dengan Diameter, Jumlah Pcs, Panjang/btg, Total Panjang, Berat (kg), dan Batang 12m, serta **Tabel Rekapitulasi Pembesian Per Diameter (D6 s/d D41)** untuk seluruh proyek.
  - **Tema Warna Formal & Tanpa Emoji**: Mengatur skema warna laporan PDF agar seragam dengan tema website (`#004ac6` Primary Navy Blue, `#f0f3ff` Light Container, `#111c2d` Dark Text) dan **menghapus seluruh penggunaan emoji** demi estetika laporan rekayasa teknik sipil profesional.
- [x] OPTIMISASI SKALA VISUALISASI PENAMPANG SVG (KOLOM, BALOK, PELAT UNTUK DIMENSI KECIL): 1. Memperbaiki algoritma proporsi skala SVG canvas agar dimensi kecil (seperti `100mm × 100mm` atau `150mm × 150mm`) tetap digambar dengan luas penampang yang proporsional, jelas, dan tidak mengkerut; 2. Menyesuaikan ketebalan selimut beton (`ccPx`) dan radius besi tulangan (`rUtmPx`) secara adaptif agar sengkang dan posisi tulangan utama tidak pernah saling tumpang tindih; 3. **RUMUS PERHITUNGAN STRUKTUR 100% TIDAK DIUBAH SAMA SEKALI** (murni pembaruan visual penampang SVG).
- [x] DETAIL PERHITUNGAN NET HEIGHT & NET SPAN (BEKISTING & VOLUME COR -TEBAL PLAT -PENOPANG), FITUR EDIT & SAVE ANTI-DUPLIKASI, SERTA EXCEL PAGE BREAK VIEW & FREEZE PANES: 1. Perhitungan Volume Cor & Bekisting Kolom & Balok kini otomatis dikurangi Tebal Pelat ($L - t_{\text{pelat}}$ untuk Kolom dan $h - t_{\text{pelat}}$ untuk Balok) serta Panjang Bentang Balok dikurangi Penopang ($L - \text{penopang}$) dengan rincian rumus substitusi angka transparan di Web UI; 2. Menambahkan fitur Edit pada setiap baris Daftar Terhitung yang secara otomatis mengisi form dan memperbarui item di `store` tanpa membuat duplikasi data baru (*anti-duplikasi*); 3. Memperbarui seluruh worksheet ExcelJS (.xlsx) dengan tampilan **Page Break View** (`pageBreakPreview`) serta **Freeze Panes** presisi pada 3 baris header atas & 4 kolom pertama (No, ID, Lantai, Sub-Kode / Uraian) agar analisis data di Excel lebih nyaman dan profesional.
- [x] AUDIT KETAT 100% SESUAI RUMUS_BACKUP.md (WEBSITE & EXCEL FORMULA MATCH): 1. Menyelaraskan seluruh kalkulasi Balok (Kode A s/d F), Kolom (Utama, Sengkang, Crosstie, Net Concrete), dan Pelat di Website JS & Excel agar 100% presisi identik hingga angka desimal; 2. Menghapus faktor waste tak terdokumentasi pada Balok sehingga Volume Cor Balok murni `(b/1000)*(h/1000)*(L/1000)*qty` & Bekisting murni `(2*(h/1000) + (b/1000))*(L/1000)*qty`; 3. Memperbaiki rumus Excel Sengkang Balok menjadi sum dua ROUNDUP tumpuan & lapangan terpisah `(ROUNDUP(L_tump/sT, 0) + ROUNDUP(L_lap/sLp, 0)) * Qty` agar hasil Excel & Website 100% identik.
- [x] PERBAIKAN TOTAL HAPUS PEMBAGIAN PECAHAN SPASI (MENGHILANGKAN PROBLEM -2 DAN -3): 1. Menghapus penuh pembagian terbalik `L / pcsPerCol` yang sebelumnya menghasilkan pecahan terbalik (seperti `148mm` / kurang 2 dan `297mm` / kurang 3); 2. Menjamin Spasi Sengkang `sS` di Excel murni bulat `150mm` dan Spasi Crosstie `sCross` murni bulat `300mm` (atau `0mm` jika tanpa Crosstie).
- [x] PERBAIKAN SPASI CROSSTIE CUSTOM (MISAL: 300MM DI-INPUT TETAP 300MM DI EXCEL): 1. Memperbaiki *fallback* variabel `sCross` agar mempertahankan nilai input manual murni (misal `300mm`) dari website dan tidak lagi jatuh ke nilai *default* `150mm`; 2. Menginfer nilai spasi Crosstie dari total `pcs / qty` apabila item dihitung sebelum perbaikan sehingga kolom `Spasi Crosstie sCross (mm)` di Excel terisi `300mm` secara presisi dan rumus Excel `=IF(O4>0, ROUNDUP(L4/O4, 0) * F4, Total_Pcs)` menghasilkan pcs yang persis sama.
- [x] PERBAIKAN SPASI CROSSTIE KOLOM DI EXCEL: 1. Kolom `Spasi Crosstie sCross (mm)` di Excel kini murni bernilai **`0`** apabila opsi *Tanpa Crosstie* dipilih di website; 2. Nilai spasi Crosstie hanya ditampilkan apabila Crosstie aktif/diisi secara spesifik di website, sehingga tidak lagi secara keliru mengikuti/meniru spasi Sengkang `150mm`.
- [x] REDESAIN EXCEL TERSTRUKTUR & BERSIH (DATA MENTAH BIASA & FORMULA DI-BOLD): 1. Menghapus seluruh pewarnaan font kuning & background kuning pada sel input manual agar tampilan Excel bersih & profesional; 2. Seluruh sel yang berisi Formula Excel kini diformat **TEBAL (BOLD)** agar mudah dibedakan dengan data mentah; 3. Menambahkan kolom eksplisit `Jml Unit (unit)` pada sheet Balok, Kolom, dan Pelat; 4. Memastikan Spasi Sengkang `sS` di Excel persis bernilai `150mm` dari data manual website (tanpa pembulatan pecahan) dan rumus Excel terhubung 100% presisi.
- [x] PERBAIKAN SINKRONISASI SENGKANG KP/KOLOM (PENGHITUNGAN JUMLAH PCS & SPASI OTOMATIS): 1. Menginfer nilai Spasi Sengkang `sS` secara otomatis dari total `pcs / qty` apabila item dibuat sebelum perbaikan sehingga kolom `Spasi Sengkang sS` di Excel terisi `150mm` secara akurat; 2. Memperbaiki rumus Excel Jumlah Pcs Sengkang Kolom menjadi `=IF(Spasi>0, ROUNDUP(Bentang/Spasi, 0) * Qty, Total_Pcs)` sehingga perkalian kuantitas (misal: 29 unit KP) menghasilkan `870 pcs`, `156.60 m`, dan `14 batang (12m)` di Excel secara 100% presisi dan identik dengan website.
- [x] PERBAIKAN FORMULA BATANG 12M EXCEL (CEGAH D6 / ITEM KOSONG MENGELUARKAN 1 BATANG): 1. Mengubah seluruh rumus Kebutuhan Batang 12m di Excel menjadi `=IF(Total_Panjang>0, ROUNDUP(Total_Panjang/12, 0), 0)`; 2. Menghilangkan nilai *default* 150mm pada spasi Crosstie/Sengkang Kolom jika tidak ada/diisi 0 sehingga Total Panjang dan Batang 12m di Excel 100% presisi dan identik 0 batang seperti di website.
- [x] PERBAIKAN SINKRONISASI SENGKANG KOLOM & FORMULA EXCEL: 1. Menyimpan parameter `cc`, `sS`, `sCross` ke objek data Kolom & `cc`, `penopang`, `sT`, `sLp` ke Balok sehingga Excel 100% terhubung dinamis; 2. Menambahkan kolom eksplisit `Selimut cc (mm)`, `Spasi Sengkang sS (mm)`, `Spasi Crosstie sCross (mm)` pada sheet Kolom & Balok di Excel; 3. Rumus Sengkang Kolom di Excel terhubung otomatis ke `L_net / sS` & `L_net / sCross`; 4. Sengkang Balok saat Penopang 0 menggunakan bentang utuh L tanpa pengurangan.
- [x] REVISI EXCEL FORMULA PCS, HIGHLIGHT KUNING DATA MANUAL, BENTANG BALOK PENOPANG 0, & HAPUS STATUS SNI: 1. Penopang 0 pada Balok otomatis menggunakan panjang bentang bersih L secara utuh; 2. Kolom Jumlah Pcs di Excel diekspor menggunakan Rumus Live Excel (`ROUNDUP(...)`); 3. Seluruh data input manual di Excel diwarnai Font Kuning Emas & background soft-yellow; 4. Hapus kolom "Status STANDAR SNI" pada sheet Rekapitulasi Proyek.
- [x] PEMINDAHAN TOMBOL SIMPAN & RESTORE KE SIDEBAR BAR BAWAH, RESTORE KHUSUS FILE .JSON, & PERSISTENSI AUTO-SAVE (COOKIE & LOCALSTORAGE): Tombol "Simpan & Restore" dipindahkan ke bilah navigasi samping (SideNavBar) bawah agar header atas bersih. Fitur modal disederhanakan khusus Simpan .json, Buka .json, dan Download Excel .xlsx. Dilengkapi auto-save ganda via LocalStorage + Cookie agar data tidak pernah hilang saat refresh page.
- [x] FITUR EXPORT EXCEL (.XLSX) DENGAN RUMUS OTOMATIS TERHUBUNG & STYLING ELEGAN: Tombol "Export Excel (.xlsx)" di Panel Rekap & Modal untuk mengunduh laporan Excel profesional multi-sheet (REKAPITULASI PROYEK, BALOK, KOLOM, PELAT) dengan rumus-rumus Excel live terhubung otomatis.
- [x] BACKUP RUMUS STRUKTUR (BALOK & KOLOM): Seluruh rumus perhitungan tulangan Balok & Kolom disimpan dalam file backup [RUMUS_BACKUP.md](file:///f:/SIPIL/PKL/VOLUME/RUMUS_BACKUP.md) (Read-Only Strict Rule).
- [x] 5. HAPUS TULISAN TULISAN GAPENTING MISAL DI JUMLAH PINGGANG KODE F ITU TIDAK PENTING MENDING GANTI KE SATUAN MISAL BH BTG MM CM M DLL
- [x] 6. DI KOLOM DI DIMENSI KOLOM ADA YG BERNAMA TINGGI PENAMPANG h (mm) GANTI KE PANJANG KOLOM JADI DIMENSI ITU JUMLAH KOLOM LEBAR KOLOM PANJANG KOLOM TINGGI KOLOM SELIMUT BETON
- [x] 7. HAPUS SEMUA TULISAN SNI 2847:2019
- [x] 8. UNTUK BALOK AKU MAU REQUEST TIPE BALOK BISA DIISI B1 B2 B3 BR BK1 DLL TAPI ADA KOLOM BERBEDA MISAL B1 YG BENTANGNYA 6 METER ADA ...BUAH YANG UKURAN 4 METER JUGA ADA ... BUAH
- [x] 9. LOGO UBAH ---
- [x] 11. FITUR PER LANTAI / ELEVASI: Datalist input lokasi lantai pada Kolom, Balok, dan Pelat, badge lantai pada daftar item, dan filter per lantai pada daftar item & Rekapitulasi Proyek.
- [x] 12. FITUR INPUT MULTI-BENTANG BATCH & DUPLIKAT DATA 1-KLIK: Form dynamic variation rows (`+ Tambah Variasi`)- [x] Fitur Pengelompokan & Filter Per Lantai (Elevasi)
- [x] Input Multi-Bentang / Multi-Ukuran Sekaligus (Batch Variation)
- [x] Perhitungan Terpisah Per Variasi (Misal: 3 variasi bentang 6000 3 buah, 5000 9 buah, 4500 2 buah dihitung & disimpan sebagai entri masing-masing)
- [x] Display Luar Daftar Terhitung Menampilkan Ringkasan Jumlah Batang & Total Panjang Per Diameter (D19, D10, D13, dsb)
- [x] Toggle/Collapsible Detail Rincian Perhitungan Sub-Elemen pada setiap card item
- [x] Fitur Duplikat Data 1-Click (Copy ke Form) untuk menyalin data terhitung ke form.
name: SIPILCALC Engineering System
colors:
  surface: '#f9f9ff'
  surface-dim: '#cfdaf2'
  surface-bright: '#f9f9ff'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#f0f3ff'
  surface-container: '#e7eeff'
  surface-container-high: '#dee8ff'
  surface-container-highest: '#d8e3fb'
  on-surface: '#111c2d'
  on-surface-variant: '#434655'
  inverse-surface: '#263143'
  inverse-on-surface: '#ecf1ff'
  outline: '#737686'
  outline-variant: '#c3c6d7'
  surface-tint: '#0053db'
  primary: '#004ac6'
  on-primary: '#ffffff'
  primary-container: '#2563eb'
  on-primary-container: '#eeefff'
  inverse-primary: '#b4c5ff'
  secondary: '#505f76'
  on-secondary: '#ffffff'
  secondary-container: '#d0e1fb'
  on-secondary-container: '#54647a'
  tertiary: '#525657'
  on-tertiary: '#ffffff'
  tertiary-container: '#6b6e70'
  on-tertiary-container: '#eff1f3'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#dbe1ff'
  primary-fixed-dim: '#b4c5ff'
  on-primary-fixed: '#00174b'
  on-primary-fixed-variant: '#003ea8'
  secondary-fixed: '#d3e4fe'
  secondary-fixed-dim: '#b7c8e1'
  on-secondary-fixed: '#0b1c30'
  on-secondary-fixed-variant: '#38485d'
  tertiary-fixed: '#e0e3e5'
  tertiary-fixed-dim: '#c4c7c9'
  on-tertiary-fixed: '#191c1e'
  on-tertiary-fixed-variant: '#444749'
  background: '#f9f9ff'
  on-background: '#111c2d'
  surface-variant: '#d8e3fb'
typography:
  display:
    fontFamily: Inter
    fontSize: 36px
    fontWeight: '700'
    lineHeight: 44px
    letterSpacing: -0.02em
  headline-lg:
    fontFamily: Inter
    fontSize: 24px
    fontWeight: '600'
    lineHeight: 32px
    letterSpacing: -0.01em
  headline-md:
    fontFamily: Inter
    fontSize: 20px
    fontWeight: '600'
    lineHeight: 28px
  body-lg:
    fontFamily: Inter
    fontSize: 16px
    fontWeight: '400'
    lineHeight: 24px
  body-md:
    fontFamily: Inter
    fontSize: 14px
    fontWeight: '400'
    lineHeight: 20px
  label-md:
    fontFamily: Inter
    fontSize: 13px
    fontWeight: '500'
    lineHeight: 18px
    letterSpacing: 0.01em
  label-sm:
    fontFamily: Inter
    fontSize: 11px
    fontWeight: '600'
    lineHeight: 16px
  mono-data:
    fontFamily: monospace
    fontSize: 13px
    fontWeight: '400'
    lineHeight: 20px
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  base: 4px
  xs: 4px
  sm: 8px
  md: 16px
  lg: 24px
  xl: 40px
  gutter: 16px
  sidebar-width: 260px
  sidebar-collapsed: 64px
---

## Brand & Style

The design system is engineered for precision, reliability, and technical clarity. It targets civil and structural engineers who require high-density information environments that remain legible during complex calculation tasks. 

The aesthetic is **Modern Minimalist with a Functionalist edge**, drawing inspiration from high-end CAD and BIM software. The UI prioritizes content over container, utilizing significant whitespace to separate complex datasets. The emotional response is one of "Technical Authority"—the interface should feel like a high-precision tool that is predictable, stable, and efficient. 

Key visual principles:
- **Clarity over Decoration:** Every line and hue must serve a functional purpose.
- **Utility-First:** Interactive elements are clearly distinguished from static data through consistent use of the primary action color.
- **Density Management:** UI elements are compact to maximize the visible data area without sacrificing touch/click targets.

## Colors

The color palette is architected for prolonged focus and high legibility. 

- **Primary Blue (#2563EB):** Reserved exclusively for primary actions, active states, and focus indicators. It signifies "Calculable" or "Actionable" elements.
- **Surface & Background (#F8FAFC):** The foundational canvas. It reduces eye strain compared to pure white while providing enough contrast for subtle depth layering.
- **Functional Semantics:** Success Green and Error Red are used sparingly for validation states and safety factor warnings. 
- **Neutral Scale:** We use a cool-toned slate for typography and borders to maintain a professional, "engineering-grade" atmosphere.

## Typography

This design system utilizes **Inter** for its exceptional legibility in data-heavy contexts and its neutral, systematic character.

- **Scale:** A tight typographic scale ensures that even with large amounts of information, the visual hierarchy remains intact.
- **Data Display:** For numerical outputs and coordinate systems, a monospaced stack is permitted to ensure vertical alignment of digits.
- **Labels:** Use `label-sm` for table headers and input captions to maximize space while maintaining structural clarity.

## Layout & Spacing

The layout uses a **Hybrid Fluid Grid** system optimized for widescreen engineering monitors.

- **Structure:** A collapsible left sidebar houses navigation and project trees, while a right-hand property panel (optional) handles contextual settings.
- **The Main Canvas:** The central area is fluid, allowing data tables and diagrams to expand.
- **Spacing Rhythm:** An 8px linear scale is used for general layout, with a 4px sub-step for tight component internal spacing (e.g., input field padding).
- **Responsive Behavior:** On tablet, the sidebar collapses into a rail. On mobile, calculations stack vertically, and complex tables transition to a "card-list" format.

## Elevation & Depth

Elevation is handled through **Tonal Layering** and **Minimalist Shadows**.

- **Level 0 (Background):** #F8FAFC. The base layer for the application.
- **Level 1 (Cards/Sidebar):** Pure White (#FFFFFF) with a `shadow-sm` (0 1px 2px 0 rgba(0, 0, 0, 0.05)). This provides enough lift to separate content areas without the "floating" feel of consumer apps.
- **Level 2 (Modals/Popovers):** Pure White (#FFFFFF) with a more pronounced shadow to indicate temporary interaction.
- **Borders:** Subtle 1px borders (#E2E8F0) are the primary method of separation, ensuring the UI feels structured and "drafted."

## Shapes

The shape language is **Structured and Geometric**. 

- **Standard Radius:** 0.5rem (8px) is the default for cards, input fields, and buttons. This softens the technical nature of the app just enough to feel modern while maintaining a professional "block" structure.
- **Consistency:** All interactive containers must share the same corner radius to reinforce the systematic nature of the engineering tool.

## Components

### Buttons
- **Primary:** Filled Blue (#2563EB) with white text. High-contrast.
- **Secondary:** White background with #E2E8F0 border and #1E293B text.
- **Size:** Compact (32px height) for toolbars, Standard (40px height) for forms.

### Data-Heavy Tables
- **Headers:** `label-sm` typography with a light gray background (#F1F5F9).
- **Rows:** Zebra striping is discouraged; use subtle hover states (#F8FAFC) and thin horizontal dividers instead.
- **Cells:** Right-align all numerical data to facilitate quick visual comparison of magnitudes.

### Professional Inputs
- **Unit Integration:** Input fields for measurements (kN, mm, m) must feature a persistent right-aligned unit label within the field.
- **Tooltips:** Use a small "info" icon next to labels that triggers a clean, high-contrast tooltip for engineering definitions or formula references.
- **Validation:** Use a 2px left-border highlight (Success or Error) to provide immediate feedback without shifting layout.

### Collapsible Sidebar
- **States:** Fully expanded for navigation clarity; icons-only "Rail" mode for maximizing calculation workspace.
- **Active State:** A vertical blue bar on the left edge indicates the current active module.

### Cards
- **Usage:** Use for grouping calculation parameters or result summaries. 
- **Header:** Cards should include a distinct header section with `headline-md` and an optional toolbar for card-specific actions (e.g., Export, Refresh).
- [x] 10. JANGAN MENGUBAH RUMUS RUMUS YAA CENTANG YANG SUDAH SELESAI DI LAKUKAN