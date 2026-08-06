# 🔒 RUMUS BACKUP - DOKUMENTASI PERHITUNGAN STRUKTUR
**SIPILCALC Engineering System**
*Tanggal Update Backup: 5 Agustus 2026*

> 🚨 **PERATURAN PENTING / STRICT RULE:**
> 1. **FILE INI MERUPAKAN ARSIP BACKUP DAN DOKUMENTASI UTAMA SELURUH RUMUS PERHITUNGAN STRUKTUR (BALOK, KOLOM, DLL).**
> 2. **DILARANG KERAS MENGUBAH, MENGHAPUS, ATAU MENGOTAK-ATIK RUMUS YANG SUDAH ADA DI DALAM FILE INI.**
> 3. **FILE INI BERSIFAT READ-ONLY SEBAGAI BACKUP ACUAN JIKA SUATU SAAT RUMUS DI APLIKASI BERUBAH ATAU TERHAPUS.**

---

# 1. PERHITUNGAN ELEMEN BALOK (BEAM)

## 1.1 Parameter Input Balok
| Parameter | Simbol | Satuan | Keterangan |
|---|---|---|---|
| Lebar Balok | `b` | mm | Dimensi lebar penampang balok |
| Tinggi Balok | `h` | mm | Dimensi tinggi penampang balok |
| Selimut Beton | `cc` | mm | Clear cover |
| Penopang / Lebar Kolom | `penopang` | mm | Lebar penopang tumpuan (kolom) |
| Panjang Bentang Total | `L` | mm | Panjang bentang as-ke-as balok |
| Diameter Utama | `dU` | mm | Diameter besi tulangan utama |
| Diameter Sengkang | `dS` | mm | Diameter besi sengkang |
| Diameter Pinggang | `dP` | mm | Diameter besi pinggang |
| Jumlah Atas Menerus | `nB` | btg | Jumlah batang tulangan atas menerus (Kode B) |
| Jumlah Tumpuan Extra | `nC` | btg | Jumlah batang tulangan tumpuan ekstra (Kode C) |
| Jumlah Lapangan Extra | `nD` | btg | Jumlah batang tulangan lapangan ekstra (Kode D) |
| Jumlah Bawah Menerus | `nE` | btg | Jumlah batang tulangan bawah menerus (Kode E) |
| Jumlah Pinggang | `nF` | btg | Jumlah batang tulangan pinggang (Kode F) |
| Spasi Sengkang Tumpuan | `sT` | mm | Jarak antar sengkang daerah tumpuan |
| Spasi Sengkang Lapangan | `sLp` | mm | Jarak antar sengkang daerah lapangan |

## 1.2 Formula Bantuan (Kait & Penyaluran Balok)
- **Panjang Kait Excel (Meter)**:
  ```excel
  =ROUNDUP(7,5 * DIAMETER / 1000; 2)
  ```
  `k_sgk = Math.ceil((7.5 * dS / 1000) * 100) / 100`
  `k_utm = Math.ceil((7.5 * dU / 1000) * 100) / 100`
- **Penyaluran Tumpuan (15d)**: `l_dev_tump = (15 * dU) / 1000` (m)
- **Penyaluran Lapangan (20d)**: `l_dev_lap = (20 * dU) / 1000` (m)

## 1.3 Rumus Sub-Elemen Balok (Kode A - F)

### A. Kode A: Sengkang Balok (Stirrup)
- **Jumlah Sengkang (btg)**:
  ```excel
  =ROUNDUP(((((BENTANG-PENOPANG)*0,5)/JARAK SENGKANG TUMPUAN)+(((BENTANG-PENOPANG)*0,5)/JARAK SENGKANG LAPANGAN));0)
  ```
  *JS*: `nA = Math.ceil((((L - penopang) * 0.5) / sT) + (((L - penopang) * 0.5) / sLp))`
- **Panjang 1 Batang (m)**: `(2 * k_sgk) + (2 * (b - 2*cc)/1000) + (2 * (h - 2*cc)/1000)`

### B. Kode B: Tulangan Atas Menerus
- **Panjang 1 Batang (m)**:
  ```excel
  =2 * (ROUNDUP(7,5 * DIAMETER BESI / 1000; 2) + (0,5 * BENTANG TOTAL))
  ```
  *JS*: `pjgB = 2 * (k_utm + (0.5 * (L / 1000)))`

### C. Kode C: Tulangan Tumpuan Extra
- **Panjang 1 Batang (m)**:
  ```excel
  =2 * (ROUNDUP(7,5*d/1000;2) + (0,25*L - penopang) + (15*d/1000) + ROUNDUP(7,5*d/1000;2))
  ```
  *JS*: `pjgC = 2 * (k_utm + Math.max(0, (0.25*L - penopang)/1000) + l_dev_tump + k_utm)`

### D. Kode D: Tulangan Lapangan Extra
- **Panjang 1 Batang (m)**:
  ```excel
  =2 * (ROUNDUP(7,5*d/1000;2) + (20*d/1000)) + (0,25*L - penopang)
  ```
  *JS*: `pjgD = 2 * (k_utm + l_dev_lap) + Math.max(0, (0.25*L - penopang)/1000)`

### E. Kode E: Tulangan Bawah Menerus
- **Panjang 1 Batang (m)**:
  ```excel
  =2 * (ROUNDUP(7,5 * DIAMETER BESI / 1000; 2) + (0,5 * BENTANG TOTAL))
  ```
  *JS*: `pjgE = 2 * (k_utm + (0.5 * (L / 1000)))`

### F. Kode F: Tulangan Pinggang (Skin Reinforcement)
- **Panjang 1 Batang (m)**:
  ```excel
  =BENTANG TOTAL (dalam meter)
  ```
  *JS*: `pjgF = L / 1000`

## 1.4 Volume Beton & Bekisting Balok (Net / Clean Takeoff)
- **Tinggi Balok Bersih (m)**:
  `h_cor = Math.max(0, h - tPlt) / 1000` (Tinggi Balok dikurangi Tebal Pelat Netto `tPlt`)
- **Bentang Balok Bersih (m)**:
  `L_cor = Math.max(0, L - penopang) / 1000` (Panjang Bentang dikurangi Lebar Penopang / Kolom)
- **Volume Cor Balok Net (m³)**:
  ```excel
  =(LEBAR / 1000) * ((TINGGI BALOK - TEBAL PELAT) / 1000) * ((BENTANG - PENOPANG) / 1000) * JUMLAH
  ```
  *JS*: `volTotal = (b / 1000) * (Math.max(0, h - tPlt) / 1000) * (Math.max(0, L - penopang) / 1000) * qty`
- **Luas Bekisting Balok Net (m²)**:
  ```excel
  =(2 * ((TINGGI BALOK - TEBAL PELAT) / 1000) + (LEBAR / 1000)) * ((BENTANG - PENOPANG) / 1000) * JUMLAH
  ```
  *JS*: `fwTotal = (2 * (Math.max(0, h - tPlt) / 1000) + (b / 1000)) * (Math.max(0, L - penopang) / 1000) * qty`

---

# 2. PERHITUNGAN ELEMEN KOLOM (COLUMN)

## 2.1 Parameter Input Kolom
| Parameter | Simbol | Satuan | Keterangan |
|---|---|---|---|
| Lebar Kolom | `b` | mm | Lebar sisi penampang kolom |
| Panjang Kolom | `h` | mm | Panjang sisi penampang kolom |
| Tinggi Kolom | `L` | mm | Tinggi total kolom per lantai |
| Selimut Beton | `cc` | mm | Clear cover (default 40 mm) |
| Diameter Utama | `dU` | mm | Diameter besi tulangan utama kolom |
| Jumlah Utama | `nU` | btg | Jumlah total batang tulangan utama kolom |
| Diameter Sengkang | `dS` | mm | Diameter besi sengkang kolom |
| Spasi Sengkang | `sS` | mm | Spasi/jarak antar sengkang kolom |
| Diameter Crosstie | `dCross` | mm | Diameter besi ikat silang / crosstie |
| Spasi Crosstie | `sCross` | mm | Spasi ikat silang / crosstie |

## 2.2 Rumus Sub-Elemen Kolom

### A. Tulangan Utama Kolom
- **Jumlah Total (btg)**: `nU * qty`
- **Panjang 1 Batang (m)**: `L / 1000`
- **Total Panjang (m)**: `(nU * qty) * (L / 1000)`
- **Total Berat (kg)**: `Total_Panjang * W_besi[dU]`

### B. Sengkang Kolom (Stirrup)
- **Jumlah Sengkang Per Kolom (btg)**:
  ```excel
  =ROUNDUP(TINGGI KOLOM / SPASI SENGKANG; 0)
  ```
  *JS*: `nS_perKolom = Math.ceil(L / sS)`
- **Panjang Kait Sengkang (m)**:
  ```excel
  =ROUNDUP(7,5 * dS / 1000; 2)
  ```
  *JS*: `pjgKaitS = Math.ceil((7.5 * dS / 1000) * 100) / 100`
- **Panjang 1 Batang Sengkang (m)**:
  ```excel
  =(2 * pjgKaitS) + (2 * (b - 2*cc)/1000) + (2 * (h - 2*cc)/1000)
  ```
- **Total Panjang & Berat**: `tLenS = (nS_perKolom * qty) * pjgS`, `wS = tLenS * W_besi[dS]`

### C. Crosstie / Ikat Silang Kolom
- **Jumlah Crosstie Per Kolom (btg)**:
  ```excel
  =ROUNDUP(TINGGI KOLOM / SPASI CROSSTIE; 0)
  ```
  *JS*: `nCross_perKolom = Math.ceil(L / sCross)`
- **Panjang Kait Crosstie (m)**: `0.075` m (75 mm)
- **Panjang 1 Batang Crosstie (m)**:
  ```excel
  =((b - 2*cc - dCross) / 1000) + (2 * 0,075)
  ```
- **Total Panjang & Berat**: `tLenCross = (nCross_perKolom * qty) * pjgCross`, `wCross = tLenCross * W_besi[dCross]`

## 2.3 Volume Beton & Bekisting Kolom (Net / Clean Takeoff)
- **Tinggi Kolom Bersih (m)**:
  `L_cor = Math.max(0, L - tPlt) / 1000` (Tinggi Kolom dikurangi Tebal Pelat Netto `tPlt`)
- **Volume Cor Kolom (m³)**:
  ```excel
  =(LEBAR / 1000) * (PANJANG / 1000) * ((TINGGI KOLOM - TEBAL PELAT) / 1000) * JUMLAH
  ```
  *JS*: `volTotal = (b / 1000) * (h / 1000) * (Math.max(0, L - tPlt) / 1000) * qty`
- **Luas Bekisting Kolom (m²)**:
  ```excel
  =2 * ((LEBAR / 1000) + (PANJANG / 1000)) * ((TINGGI KOLOM - TEBAL PELAT) / 1000) * JUMLAH
  ```
  *JS*: `fwTotal = (2 * (b / 1000 + h / 1000)) * (Math.max(0, L - tPlt) / 1000) * qty`
