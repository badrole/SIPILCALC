# KNOWLEDGE BASE & RULE ENGINE: REFERENSI STRUKTUR BETON SNI 2847:2019

Dokumen ini adalah **Knowledge Base & Rule Engine** resmi yang mengompilasi seluruh ketentuan dari **SNI 2847:2019** (diperbarui penuh dari `info.md` dan `info baru.md`, serta aturan implementasi berlabel `application_rule` dan `default_application`). Dokumen ini dirancang khusus agar dapat dibaca dan dieksekusi secara langsung oleh aplikasi web penghitung kebutuhan **Cor (Beton)**, **Bekisting (Formwork)**, dan **Pembesian (Rebar & BBS)** untuk **Balok**, **Kolom**, dan **Pelat** berbasis **React + NextJS + Supabase**.

---

# 1 MATERIAL

## 1.1 Beton (Concrete)

### 1.1.1 Mutu Beton ($f'_c$)
- **Beton Berat Normal & Ringan Umum**: $f'_c \ge 17\text{ MPa}$ [SNI 2847:2019 Pasal 19.2.1.1]
- **SRPMK & Dinding Struktural Khusus (Normal)**: $f'_c \ge 21\text{ MPa}$ [SNI 2847:2019 Pasal 19.2.1.1]
- **SRPMK & Dinding Struktural Khusus (Ringan)**: $21\text{ MPa} \le f'_c \le 35\text{ MPa}$ [SNI 2847:2019 Pasal 19.2.1.1]
- **Batas Atas $f'_c$ untuk Perhitungan $l_d$**: $\sqrt{f'_c} \le 8.3\text{ MPa}$ ($f'_c \le 68.89\text{ MPa}$, dibulatkan $70\text{ MPa}$) [SNI 2847:2019 Pasal 25.4.1.4]
- **Mutu Beton Intersection Kolom-Lantai**: Jika $f'_c$ kolom $> 1.4 f'_c$ lantai/pelat, beton mutu tinggi kolom harus diteruskan masuk ke dalam sistem pelat/balok lantai sejauh **600 mm** dari muka kolom untuk menjamin transfer gaya aksial. [SNI 2847:2019 Pasal 15.3.1, 26.5.7.2(c)]
- **Default Mutu Beton Aplikasi**: $f'_c = 25\text{ MPa}$ [`default_application`]

### 1.1.2 Modulus Elastisitas Beton ($E_c$)
- **Beton Berat Normal**: 
  $$E_c = 4700 \sqrt{f'_c} \quad (\text{MPa})$$ [SNI 2847:2019 Pasal 19.2.2.1]
- **Beton Densitas $w_c$ ($1440 \le w_c \le 2560 \text{ kg/m}^3$)**:
  $$E_c = w_c^{1.5} \times 0.043 \sqrt{f'_c} \quad (\text{MPa})$$ [SNI 2847:2019 Pasal 19.2.2.1]

### 1.1.3 Faktor Modifikasi Beton Ringan ($\lambda$)
- **Beton Normal**: $\lambda = 1.00$ [SNI 2847:2019 Pasal 19.2.4.2]
- **Beton Ringan**: $\lambda = 0.75$ [SNI 2847:2019 Pasal 19.2.4.2]

### 1.1.4 Berat Jenis Beton ($w_c$)
- **Beton Normal Default**: $w_c = 2400\text{ kg/m}^3$ ($24\text{ kN/m}^3$) [`application_rule`]
- **Beton Ringan Default**: $w_c = 1800\text{ kg/m}^3$ ($18\text{ kN/m}^3$) [`default_application`]

### 1.1.5 Faktor Waste Beton
- **Faktor Waste Beton Default**: $W_{\text{concrete}} = 3\%$ ($1.03$) [`application_rule`]

---

## 1.2 Baja Tulangan (Rebar)

### 1.2.1 Mutu Leleh Baja ($f_y$)
- **Mutu Leleh Tulangan Utama Default**: $f_y = 420\text{ MPa}$ (BJTS 420B) [SNI 2052:2017 / SNI 2847:2019]
- **Mutu Leleh Tulangan Sengkang Default**: $f_{yt} = 280\text{ MPa}$ atau $420\text{ MPa}$ [`default_application`]
- **Modulus Elastisitas Baja ($E_s$)**: $E_s = 200,000\text{ MPa}$ [SNI 2847:2019 Pasal 20.2.2.2]

### 1.2.2 Tabel Properti Standar Tulangan Ulir & Polos [`application_rule`]

| Kode Diameter | Diameter Nominal $d_b$ (mm) | Luas Penampang $A_b = \frac{\pi}{4}d_b^2$ (mm²) | Berat per Meter $W$ (kg/m) | Label Status |
|---|---|---|---|---|
| **D6** | 6.0 | 28.27 | 0.222 | `application_rule` |
| **D8** | 8.0 | 50.27 | 0.395 | `application_rule` |
| **D10** | 10.0 | 78.54 | 0.617 | `application_rule` |
| **D12** | 12.0 | 113.10 | 0.888 | `application_rule` |
| **D13** | 13.0 | 132.73 | 1.040 | `application_rule` |
| **D16** | 16.0 | 201.06 | 1.580 | `application_rule` |
| **D19** | 19.0 | 283.53 | 2.226 | `application_rule` |
| **D22** | 22.0 | 380.13 | 2.984 | `application_rule` |
| **D25** | 25.0 | 490.87 | 3.853 | `application_rule` |
| **D29** | 29.0 | 660.52 | 5.040 | `application_rule` |
| **D32** | 32.0 | 804.25 | 6.313 | `application_rule` |
| **D36** | 36.0 | 1017.88 | 7.990 | `application_rule` |
| **D41** | 41.0 | 1320.25 | 10.380 | `application_rule` |

### 1.2.3 Radius & Diameter Bengkok Minimum ($D_{\text{bend}}$)
- **Tulangan Utama D10 - D25**: $D_{\text{bend}} = 6 d_b$ (Radius $r_{\text{bend}} = 3 d_b$) [SNI 2847:2019 Tabel 25.3.1]
- **Tulangan Utama D29 - D36**: $D_{\text{bend}} = 8 d_b$ (Radius $r_{\text{bend}} = 4 d_b$) [SNI 2847:2019 Tabel 25.3.1]
- **Tulangan Utama D43 - D57**: $D_{\text{bend}} = 10 d_b$ (Radius $r_{\text{bend}} = 5 d_b$) [SNI 2847:2019 Tabel 25.3.1]
- **Sengkang & Ikat Silang D10 - D16**: $D_{\text{bend}} = 4 d_b$ (Radius $r_{\text{bend}} = 2 d_b$) [SNI 2847:2019 Tabel 25.3.2]
- **Sengkang & Ikat Silang D19 - D25**: $D_{\text{bend}} = 6 d_b$ (Radius $r_{\text{bend}} = 3 d_b$) [SNI 2847:2019 Tabel 25.3.2]
- **Jaring Kawat Las (WWR $> D6$)**: $D_{\text{bend}} = 4 d_b$ [Pasal 25.3.3]

### 1.2.4 Panjang Standar Batang & Faktor Waste Besi
- **Panjang Batang Standar Pabrik ($L_{\text{stock}}$)**: $12.0\text{ meter}$ [`application_rule`]
- **Faktor Waste Besi Default**: $W_{\text{rebar}} = 5\%$ ($1.05$) [`application_rule`]

---

## 1.3 Bekisting (Formwork)

### 1.3.1 Standar Perancangan vs Metode Pengukuran (Takeoff Method)
SNI 2847:2019 Pasal 26.11 mengatur perancangan keamanan bekisting, beban konstruksi, kerapatan pencegahan kebocoran pasta, dan prosedur pelepasan. SNI **tidak mengatur metode kuantitas (deduksi luas)**. Oleh karena itu, aplikasi web menyediakan **2 Opsi Perhitungan**: [`application_rule`]

- **Opsi A: Estimasi Brutto (Gross Method)**:
  - Kolom: $A_f = 2(b + h) \times H$ (4 sisi penuh).
  - Balok: $A_f = (2h + b_w) \times L$ (3 sisi penuh).
  - Pelat: $A_f = p \times l$ (Luas bersih lantai).
- **Opsi B: Takeoff Presisi SMM (Net Method)**:
  - Kolom: $A_f = 2(b + h) \times (H - h_{\text{balok}})$.
  - Balok Samping: $A_f = \left(2(h - t_{\text{pelat}}) + b_w\right) \times L$.
  - Pelat Netto: $A_f = (p \times l) - \sum A_{\text{kolom}} - \sum A_{\text{balok}}$.

### 1.3.2 Faktor Waste Bekisting
- **Faktor Waste Bekisting Default**: $W_{\text{formwork}} = 5\%$ ($1.05$) [`application_rule`]

---

# 2 COVER (SELIMUT BETON)

Ketebalan selimut beton bersih (*clear cover* $c_c$) dihitung dari permukaan terluar beton sampai ke sisi luar tulangan terluar (sengkang/ikat silang). [SNI 2847:2019 Tabel 20.6.1.3.1]

```
+-------------------------------------------------------------------------------+
| KONDISI LINGKUNGAN / PAPARAN       | ELEMEN STRUKTUR | TULANGAN   | COVER(mm) |
+------------------------------------+-----------------+------------+-----------+
| Cor Permanen Kontak Tanah          | Semua Elemen    | Semua      | 75        |
+------------------------------------+-----------------+------------+-----------+
| Terpapar Cuaca / Kontak Tanah      | Balok & Kolom   | D19 - D57  | 50        |
|                                    |                 | <= D16     | 40        |
|                                    | Pelat & Dinding | D19 - D57  | 50        |
|                                    |                 | <= D16     | 40        |
+------------------------------------+-----------------+------------+-----------+
| Tidak Terpapar Cuaca (Interior)    | Balok & Kolom   | Utama,Stirrup| 40      |
|                                    | Pelat & Dinding | D43 & D57  | 40        |
|                                    |                 | <= D36     | 20        |
|                                    | Fondasi (Top)   | Semua      | 50        |
|                                    | Fondasi (Bottom)| Terhubung  | 75        |
+------------------------------------+-----------------+------------+-----------+
```

## 2.1 Balok (Beam Cover)
- **Permanen Kontak Tanah**: $75\text{ mm}$ [Tabel 20.6.1.3.1]
- **Terpapar Cuaca / Kontak Tanah**: $50\text{ mm}$ ($D19-D57$), $40\text{ mm}$ ($\le D16$) [Tabel 20.6.1.3.1]
- **Tidak Terpapar Cuaca (Interior)**: $40\text{ mm}$ [Tabel 20.6.1.3.1]

## 2.2 Kolom (Column Cover)
- **Permanen Kontak Tanah**: $75\text{ mm}$ [Tabel 20.6.1.3.1]
- **Terpapar Cuaca / Kontak Tanah**: $50\text{ mm}$ ($D19-D57$), $40\text{ mm}$ ($\le D16$) [Tabel 20.6.1.3.1]
- **Tidak Terpapar Cuaca (Interior)**: $40\text{ mm}$ [Tabel 20.6.1.3.1]

## 2.3 Pelat (Slab Cover)
- **Permanen Kontak Tanah**: $75\text{ mm}$ [Tabel 20.6.1.3.1]
- **Tidak Terpapar Cuaca (Interior)**: $20\text{ mm}$ ($\le D36$), $40\text{ mm}$ ($D43-D57$) [Tabel 20.6.1.3.1]

## 2.4 Pondasi (Footing / Pile Cap Cover)
- **Cor Permanen Kontak Tanah**: $75\text{ mm}$ [Tabel 20.6.1.3.1]

---

# 3 REINFORCEMENT (PENULANGAN)

## 3.1 Tulangan Longitudinal & Lentur

### 3.1.1 Tulangan Balok
- **Jumlah Minimum Batang Menerus**: Minimal 2 batang menerus di sisi atas dan 2 batang di sisi bawah. [Pasal 9.7.7.1, 18.6.3.1]
- **Luas Tulangan Tarik Minimum ($A_{s,\min}$)**:
  $$A_{s,\min} = \max \left( \frac{0.25 \sqrt{f'_c}}{f_y} b_w d , \, \frac{1.4}{f_y} b_w d \right)$$ [Pasal 9.6.1.2]
- **Rasio Tulangan Maksimum Balok SRPMK ($\rho_{\max}$)**:
  $$\rho_{\max} = 0.025$$ [Pasal 18.6.3.1]
- **Kekuatan Lentur Tumpuan SRPMK**: Momen positif tumpuan minimal $\ge \frac{1}{2}$ Momen negatif tumpuan. Momen positif/negatif sepanjang bentang minimal $\ge \frac{1}{4}$ Momen maksimum tumpuan. [Pasal 18.6.3.2]

### 3.1.2 Lokasi Sambungan Lewatan Balok SRPMK (Beam Lap Splice Rules)
Sambungan lewatan tulangan lentur balok SRPMK memiliki batasan ketat: [SNI 2847:2019 Pasal 18.6.3.3]
1. **DILARANG** dipasang di dalam pertemuan balok-kolom (joint).
2. **DILARANG** dipasang sejarak $2h$ dari muka joint tumpuan.
3. **DILARANG** dipasang di lokasi yang berpotensi terjadi pelelehan inelastik.
4. **WAJIB** dilingkupi sengkang pengekang tertutup di sepanjang sambungan dengan spasi maksimum:
   $$s_{\text{lap}} \le \min \left( \frac{d}{4} , \, 100\text{ mm} \right)$$ [Pasal 18.6.3.3]

### 3.1.3 Batasan Pemutusan Tulangan Balok (Bar Cutoff Rules)
1. **Perpanjangan Melewati Titik Teoritis Pemutusan**: $L_{\text{ext}} = \max(d, \, 12 d_b)$. [Pasal 9.7.3.3]
2. **Tulangan Bawah Tumpuan Sederhana**: Minimal $\frac{1}{3} A_{s,\text{pos}}$ menerus sampai tumpuan. [Pasal 9.7.3.8.1]
3. **Tulangan Bawah Tumpuan Menerus**: Minimal $\frac{1}{4} A_{s,\text{pos}}$ menerus masuk tumpuan min $150\text{ mm}$. [Pasal 9.7.3.8.2]
4. **Tulangan Atas Tumpuan Menerus**: Minimal $\frac{1}{3} A_{s,\text{neg}}$ melewati titik balik (PI) sejarak $L_{\text{ext,PI}} = \max(d, \, 12 d_b, \, \frac{l_n}{16})$. [Pasal 9.7.3.8.4]

### 3.1.4 Tulangan Pinggang Balok Tinggi (Skin Reinforcement)
Untuk balok dengan $h > 900\text{ mm}$, dipasang terdistribusi merata sejarak $\frac{h}{2}$ dari muka tarik dengan spasi $s \le 380\left(\frac{280}{f_s}\right) - 2.5 c_c$. [Pasal 9.7.2.3]

### 3.1.5 Balok Tinggi / Deep Beam ($l_n / h \le 4$)
Harus dilengkapi tulangan transversal minimal $A_v \ge 0.0025 b_w s$ dengan spasi $s \le \min(\frac{d}{5}, \, 300\text{ mm})$. [Pasal 9.9.3.1, 9.9.4.3]

### 3.1.6 Tulangan Torsi Balok
- **Longitudinal Torsi**: Min 1 batang di setiap sudut sengkang tertutup, spasi $\le 300\text{ mm}$, $d_b \ge \max(0.042 s, \, 10\text{ mm})$. [Pasal 9.7.5.1, 9.7.5.2]
- **Transversal Torsi**: Sengkang tertutup, spasi $s \le \min(\frac{p_h}{8}, \, 300\text{ mm})$. [Pasal 9.7.6.3.3]

---

## 3.2 Tulangan Kolom

### 3.2.1 Rasio & Jumlah Batang Kolom
- **Rasio Tulangan Longitudinal ($A_{st} / A_g$)**:
  - **Umum**: $0.01 \le \frac{A_{st}}{A_g} \le 0.08$ [Pasal 10.6.1.1]
  - **SRPMK**: $0.01 \le \frac{A_{st}}{A_g} \le 0.06$ [Pasal 18.7.4.1]
- **Jumlah Batang Minimum ($N_{\min}$)**:
  - Penampang segiempat: $4$ batang [Pasal 10.7.3.1]
  - Penampang segitiga: $3$ batang [Pasal 10.7.3.1]
  - Penampang lingkaran / spiral / SRPMK bundar: $6$ batang [Pasal 10.7.3.1, 18.7.4.2]

### 3.2.2 Lokasi Sambungan Lewatan Kolom SRPMK (Column Lap Splice Rules)
Pada struktur SRPMK, sambungan lewatan tulangan utama kolom **DILARANG** dipasang di level lantai (muka balok). Sambungan lewatan **HANYA DIINZINKAN** dipasang pada:
- **Lokasi**: **Daerah Tengah Tinggi Kolom (Mid-height of Column)**. [SNI 2847:2019 Pasal 18.7.4.3]
- **Karakteristik**: Harus didesain sebagai sambungan lewatan tarik (Kelas B) dan dilingkupi tulangan transversal pengekang. [Pasal 18.7.4.3]

### 3.2.3 Pengekangan Ganda Kolom (Double Cross Tie / Overlapping Ties)
Bila $P_u > 0.3 A_g f'_c$ atau $f'_c > 70\text{ MPa}$, spasi horizontal kaki penumpu lateral $h_x \le 200\text{ mm}$. Untuk kondisi umum $h_x \le 350\text{ mm}$. [Pasal 18.7.5.2]

---

## 3.3 Tulangan Susut & Temperatur (Pelat)
- **Batang Ulir $f_y < 420\text{ MPa}$**: $A_{s,\text{susut}} = 0.0020 A_g$ [Tabel 7.6.1.1]
- **Batang Ulir $f_y \ge 420\text{ MPa}$**: $A_{s,\text{susut}} = \max \left( \frac{0.0018 \times 420}{f_y} A_g , \, 0.0014 A_g \right)$ [Tabel 7.6.1.1]
- **Spasi Maksimum**: $s_{\max} = \min(5h, \, 450\text{ mm})$ [Pasal 24.4.3.3]
- **Tahanan Sudut Pelat 2-Arah**: Disediakan sejarak $\frac{L_{\text{panjang}}}{5}$ dari sudut. [Pasal 8.7.3.1]

---

## 3.4 Batasan Spasi Bersih Tulangan ($s_{clear}$)
- **Balok & Pelat**: $s_{clear,\min} = \max(25\text{ mm}, \, d_b, \, \frac{4}{3} d_{\text{agg}})$ [Pasal 25.2.1]
- **Kolom**: $s_{clear,\min} = \max(40\text{ mm}, \, 1.5 d_b, \, \frac{4}{3} d_{\text{agg}})$ [Pasal 25.2.3]

---

# 4 DEVELOPMENT LENGTH (PANJANG PENYALURAN)

## 4.1 Panjang Penyaluran Tarik Batang Ulir ($l_d$)
$$l_d = \left[ \frac{f_y}{1.1 \lambda \sqrt{f'_c}} \times \frac{\psi_t \psi_e \psi_s \psi_g}{\left(\frac{c_b + K_{tr}}{d_b}\right)} \right] d_b \ge 300\text{ mm}$$ [Pasal 25.4.2.3]

---

## 4.2 Panjang Penyaluran Tekan ($l_{dc}$) & Kait ($l_{dh}$)
- **Panjang Penyaluran Tekan ($l_{dc}$)**:
  $$l_{dc} = \max \left( \frac{0.24 f_y \psi_r}{\lambda \sqrt{f'_c}} d_b , \, 0.043 f_y \psi_r d_b , \, 200\text{ mm} \right)$$ [Pasal 25.4.9.2]
- **Panjang Penyaluran Kait Tarik ($l_{dh}$)**:
  $$l_{dh} = \max \left( \left[ \frac{0.24 f_y \psi_e \psi_c \psi_r}{\lambda \sqrt{f'_c}} \right] d_b , \, 8 d_b , \, 150\text{ mm} \right)$$ [Pasal 25.4.3.1]
- **Kait Seismik SRPMK ($l_{dh,\text{seismik}}$)**:
  $$l_{dh} = \frac{f_y d_b}{5.4 \lambda \sqrt{f'_c}}$$ [Pasal 18.8.5.1]

---

## 4.3 Sambungan Lewatan (Lap Splice)
- **Tarik Kelas A**: $l_{st} = 1.0 \, l_d \ge 300\text{ mm}$
- **Tarik Kelas B**: $l_{st} = 1.3 \, l_d \ge 300\text{ mm}$ (Default Aplikasi) [Tabel 25.5.2.1]
- **Tekan ($f_y \le 420\text{ MPa}$)**: $l_{sc} = \max(0.071 f_y d_b, \, 300\text{ mm})$ [Pasal 25.5.5.1]
- **Tekan ($f_y > 420\text{ MPa}$)**: $l_{sc} = \max((0.13 f_y - 24) d_b, \, 300\text{ mm})$ [Pasal 25.5.5.1]

---

# 5 HOOK (KAIT STANDAR & BENGKOKAN)

- **Kait 90° Batang Utama**: $l_{ext} = 12 d_b$ [Tabel 25.3.1]
- **Kait 180° Batang Utama**: $l_{ext} = \max(4 d_b, \, 65\text{ mm})$ [Tabel 25.3.1]
- **Kait Sengkang 90° ($D10-D16$)**: $l_{ext} = \max(6 d_b, \, 75\text{ mm})$ [Tabel 25.3.2]
- **Kait Seismik 135° (Gempa)**: $l_{ext} = \max(6 d_b, \, 75\text{ mm})$ [Pasal 2.3, Tabel 25.3.2]

---

# 6 STIRRUP (SENGKANG, IKAT SILANG, SPIRAL)

## 6.1 Sengkang Balok & Kolom
- **Diameter Minimum Sengkang**: $D10$ (Utama $\le D32$), $D13$ (Utama $\ge D36$) [Pasal 25.7.2.2]
- **Posisi Sengkang Pertama SRPMK**: Maksimal $50\text{ mm}$ dari muka komponen penumpu. [Pasal 18.6.4.4, 18.7.5.3]
- **Overlap Sengkang-U Ganda (Double U-Stirrup Splice)**:
  Sengkang tertutup diizinkan dibuat dari sepasang sengkang-U yang disambung lewat dengan panjang sambungan lewatan minimal:
  $$L_{\text{splice}} = 1.3 \, l_d$$ [SNI 2847:2019 Pasal 25.7.1.7]
  *(Catatan: Dilarang digunakan untuk tulangan torsi atau integritas struktur).* [Pasal 25.7.1.6]
- **Spasi Sengkang Balok SRPMK (Daerah 2h)**: $s_o = \min \left( \frac{d}{4} , \, 6 d_{b,\text{long}} , \, 150\text{ mm} \right)$ [Pasal 18.6.4.4]
- **Spasi Sengkang Kolom SRPMK (Daerah $l_o$)**: $s_o = \min \left( \frac{b_{\min}}{4} , \, 6 d_{b,\text{long}} , \, 100 + \frac{350 - h_x}{3} \right)$ [Pasal 18.7.5.3]

## 6.2 Toleransi Fabrikasi Pembengkokan [`application_rule`]
- **Sengkang & Ikat Silang**: Toleransi dimensi luar $\pm 13\text{ mm}$.
- **Lokasi Pembengkokan Lainnya**: Toleransi $\pm 50\text{ mm}$.

---

# 7 BEAM (BALOK)

- **Lebar Min SRPMK**: $b_w \ge \min(0.3h, \, 250\text{ mm})$, $l_n \ge 4d$. [Pasal 18.6.2.1]
- **Balok SRPMM (Daerah 2h)**: Spasi sengkang $s = \min(\frac{d}{4}, 8d_b, 24d_{bs}, 300\text{ mm})$. [Pasal 18.4.2.4]
- **Balok Kopel ($l_n/h \ge 4$)**: Harus memenuhi syarat balok SRPMK. [Pasal 18.10.7.1]

---

# 8 COLUMN (KOLOM)

- **Dimensi Min SRPMK**: $b_{\min} \ge 300\text{ mm}$, rasio penampang $\ge 0.4$. [Pasal 18.7.2.1]
- **Kapasitas Geser Joint Balok-Kolom SRPMK ($V_n$)**:
  - Terkekang 4 sisi: $V_n = 1.7 \lambda \sqrt{f'_c} A_j$
  - Terkekang 3 sisi / 2 sisi berlawanan: $V_n = 1.2 \lambda \sqrt{f'_c} A_j$
  - Lainnya: $V_n = 1.0 \lambda \sqrt{f'_c} A_j$ [Tabel 18.8.4.1]

---

# 9 SLAB (PELAT)

- **Tebal Min Pelat 1-Arah**: $l/20$ (Sederhana), $l/24$ (1 ujung menerus), $l/28$ (2 ujung menerus), $l/10$ (Kantilever). [Tabel 7.3.1.1]
- **Tebal Min Pelat 2-Arah Tanpa Balok**: $125\text{ mm}$ (Tanpa drop panel), $100\text{ mm}$ (Dengan drop panel). [Pasal 8.3.1.1]

---

# 10 FOOTING (PONDASI FOOTING / PILE CAP)

- **Tinggi Efektif Min Pile Cap ($d_{\min}$)**: $d_{\min} \ge 300\text{ mm}$ [Pasal 13.4.2.1]
- **Selimut Beton Cor Tanah**: $75\text{ mm}$ [Tabel 20.6.1.3.1]

---

# 11 FORMULA ENGINE & KATALOG SHAPE CODE BBS

## 11.1 Katalog Shape Code Standar BBS (Bar Bending Schedule) [`application_rule`]

```
SHAPE CODE 00 (STRAIGHT)         SHAPE CODE 11 (HOOK 90°)       SHAPE CODE 21 (CLOSED TIE)
+------------------------+      +------------------------+     +---------A---------+
| L = A                  |      | L = A + B - Deduction  |     |                   |
+------------------------+      +------------------------+     D                   B
                                                               |                   |
                                                               +---------C---------+
                                                                (Hook 135° overlap)
```

1. **Straight Bar (Batang Lurus)**: $L_{\text{cut}} = A$
2. **Hooked Bar 90°**: $L_{\text{cut}} = A + B - \Delta L_{90}$
3. **Hooked Bar 180°**: $L_{\text{cut}} = A + l_{ext} + \pi(r + \frac{d_b}{2}) - \Delta L_{180}$
4. **Closed Tie / Hoop (Sengkang Rectangular)**:
   $$L_{\text{cut}} = 2(A + B) + 2 \times l_{ext,135} - 4 \times \Delta L_{135}$$
5. **Double U-Stirrup Splice (Sengkang-U Ganda)**:
   $$L_{\text{cut,U}} = A + 2B + 1.3 l_d - 2 \Delta L_{90}$$
6. **Cross Tie (Ikat Silang)**: $L_{\text{cut}} = A + l_{ext,135} + l_{ext,90} - 2 \Delta L_{\text{bend}}$
7. **Spiral (Tulangan Spiral Kolom)**: $L_{\text{total}} = \pi D_c \sqrt{N_{\text{turns}}^2 + \left(\frac{H}{s}\right)^2} + 1.5 \times 2 \pi D_c$
8. **L-Bar / Hooked Bolt (Angkur-L)**: $L_{\text{cut}} = A + B - \Delta L_{90}$ ($e_h \ge 3 d_a$)
9. **Bent Bar / Offset Bar (Tulangan Miring Kolom)**: Kemiringan max $1:6$.
10. **Hairpin Bar**: $L_{\text{cut}} = 2A + B - 2 \Delta L_{\text{bend}}$.

---

# 12 VALIDATION ENGINE

Engine validasi memeriksa seluruh batasan input pengguna terhadap SNI 2847:2019 secara otomatis:

- `FAIL` jika $c_c < 40\text{mm}$ (balok/kolom) atau $< 20\text{mm}$ (pelat) atau $< 75\text{mm}$ (cor tanah).
- `FAIL` jika $b_w < 250\text{mm}$ atau $b_{\min} < 300\text{mm}$ pada SRPMK.
- `FAIL` jika sambungan lewatan kolom SRPMK diletakkan di luar daerah tengah tinggi kolom.
- `FAIL` jika sambungan lewatan balok SRPMK diletakkan di dalam joint atau daerah $2h$ dari muka joint.
- `FAIL` jika $s_{clear} < \max(25\text{mm}, d_b)$ (balok) atau $< \max(40\text{mm}, 1.5 d_b)$ (kolom).

---

# 13 OUTPUT ENGINE (WEBSITE OUTPUT SPECIFICATION)

Website kalkulator menghasilkan output komprehensif:

1. **Volume Beton ($m^3$)**: Netto & Brutto (+ waste 3%), dipisah per mutu jika $f'_c$ kolom $> 1.4 f'_c$ pelat (extended 600 mm).
2. **Luas Bekisting ($m^2$)**: Pilihan Opsi A (Brutto / Simpel) atau Opsi B (Takeoff Presisi Netto SMM).
3. **Panjang Total Besi ($m$)**: Per diameter (D6 s.d D41) & total.
4. **Berat Total Besi ($kg$)**: Per diameter & total.
5. **Jumlah Batang 12m (batang)**: Ceiling $(\frac{L_{\text{gross}}}{12.0})$.
6. **Bar Bending Schedule (BBS)**: Pemotongan besi lengkap dengan Shape Code & aturan posisi sambungan SRPMK.
7. **Cutting List Optimization**: Efisiensi pemotongan besi 12m untuk meminimalkan sisa besi (*off-cut*).

---

# 14 DATABASE (JSON ENGINE SCHEMA)

```json
[
  {
    "id": "MAT_CONC_001",
    "category": "Material",
    "subcategory": "Beton",
    "name": "Kekuatan Tekan Minimum Umum",
    "value": "17",
    "unit": "MPa",
    "formula": "fc >= 17",
    "condition": "Beton berat normal dan ringan penggunaan umum",
    "reference": "SNI 2847:2019 Pasal 19.2.1.1"
  },
  {
    "id": "MAT_CONC_INTERSECTION_001",
    "category": "Material",
    "subcategory": "Beton",
    "name": "Mutu Beton Intersection Kolom-Lantai",
    "value": "600",
    "unit": "mm",
    "formula": "L_extend = 600",
    "condition": "Bila fc kolom > 1.4 fc lantai, teruskan beton kolom 600 mm ke pelat",
    "reference": "SNI 2847:2019 Pasal 15.3.1 & 26.5.7.2(c)"
  },
  {
    "id": "FORM_METHOD_001",
    "category": "Bekisting",
    "subcategory": "Metode Perhitungan",
    "name": "Metode Bekisting Takeoff",
    "value": "Opsi A (Gross) / Opsi B (Net SMM)",
    "unit": "Pilihan",
    "formula": "Opsi A: 2(b+h)H; Opsi B: 2(b+h)(H - h_balok)",
    "condition": "SNI 26.11 tidak mengatur SMM kuantitas; aplikasi menyediakan 2 opsi",
    "reference": "application_rule"
  },
  {
    "id": "COL_LAP_SPLICE_MIDHEIGHT_001",
    "category": "Kolom",
    "subcategory": "Sambungan Lewatan",
    "name": "Lokasi Sambungan Lewatan Kolom SRPMK",
    "value": "Tengah Tinggi Kolom",
    "unit": "Lokasi",
    "formula": "Mid-height of column only",
    "condition": "Kolom SRPMK; Dilarang di level muka lantai/balok",
    "reference": "SNI 2847:2019 Pasal 18.7.4.3"
  },
  {
    "id": "BEAM_LAP_SPLICE_FORBIDDEN_001",
    "category": "Balok",
    "subcategory": "Sambungan Lewatan",
    "name": "Larangan Lokasi Sambungan Balok SRPMK",
    "value": "2 * h dari muka joint",
    "unit": "mm",
    "formula": "Forbidden inside joint & within 2h from joint face",
    "condition": "Balok SRPMK; s_sengkang_lap <= min(d/4, 100 mm)",
    "reference": "SNI 2847:2019 Pasal 18.6.3.3"
  },
  {
    "id": "STIRRUP_DOUBLE_U_001",
    "category": "Sengkang",
    "subcategory": "Sambungan Lewatan",
    "name": "Overlap Sengkang-U Ganda",
    "value": "1.3 * ld",
    "unit": "mm",
    "formula": "L_splice = 1.3 * ld",
    "condition": "Sepasang sengkang-U tertutup; Dilarang untuk torsi/integritas",
    "reference": "SNI 2847:2019 Pasal 25.7.1.7"
  }
]
```

---

# 15 AUDIT KEBUTUHAN WEBSITE KALKULATOR (STATUS FIX & RESOLVED)

Berikut adalah status akhir dari seluruh kuis/missing data untuk kebutuhan pengembangan software:

```
+-------------------------------------------------------------------------------------------------------+
| KATEGORI WEB KALKULATOR | STATUS & SOLUSI ATURAN APLIKASI                       | REFERENSI           |
+-------------------------+-------------------------------------------------------+---------------------+
| 1. BEKISTING (FORMWORK) | - SNI 26.11 tidak mengatur SMM kuantitas takeoff.     | Pasal 26.11         |
|                         | - Aplikasi menyediakan 2 opsi tombol pengguna:        | application_rule    |
|                         |   * Opsi A (Gross/Simpel): Tanpa pengurangan.         |                     |
|                         |   * Opsi B (Net SMM): Dikurangi tinggi balok/pelat.   |                     |
+-------------------------+-------------------------------------------------------+---------------------+
| 2. PEMBESIAN (REBAR/BBS)| - Sambungan Kolom SRPMK: HANYA di Tengah Tinggi Kolom.| Pasal 18.7.4.3      |
|                         | - Sambungan Balok SRPMK: Dilarang di joint & 2h.      | Pasal 18.6.3.3      |
|                         | - Overlap Sengkang-U Ganda: 1.3 ld.                   | Pasal 25.7.1.7      |
+-------------------------+-------------------------------------------------------+---------------------+
| 3. COR (BETON)          | - Jika fc kolom > 1.4 fc lantai, beton kolom          | Pasal 15.3.1        |
|                         |   diteruskan 600 mm ke dalam sistem lantai.           | Pasal 26.5.7.2(c)   |
+-------------------------+-------------------------------------------------------+---------------------+
```
