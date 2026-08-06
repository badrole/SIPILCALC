
[
  {
    "kategori": "Durabilitas",
    "subkategori": "Selimut Beton",
    "parameter": "Selimut beton beton nonprategang cor di tempat",
    "nilai": "75",
    "satuan": "mm",
    "syarat": "Beton dicor permanen dan kontak dengan tanah",
    "pengecualian": "Tidak terdapat pada dokumen",
    "rumus": "Tidak terdapat pada dokumen",
    "variabel": "Tidak terdapat pada dokumen",
    "referensi": "Bab 20 Tabel 20.6.1.3.1 Halaman 460"
  },
  {
    "kategori": "Durabilitas",
    "subkategori": "Selimut Beton",
    "parameter": "Selimut beton komponen balok dan kolom",
    "nilai": "40",
    "satuan": "mm",
    "syarat": "Kondisi tidak terpapar cuaca atau kontak dengan tanah; untuk tulangan utama, sengkang, ikat, dan spiral",
    "pengecualian": "Tidak terdapat pada dokumen",
    "rumus": "Tidak terdapat pada dokumen",
    "variabel": "Tidak terdapat pada dokumen",
    "referensi": "Bab 20 Tabel 20.6.1.3.1 Halaman 460"
  },
  {
    "kategori": "Geometri",
    "subkategori": "Kait Standar",
    "parameter": "Perpanjangan lurus (lext) kait 90°",
    "nilai": "12 * db",
    "satuan": "mm",
    "syarat": "Penyaluran batang ulir dalam kondisi tarik",
    "pengecualian": "Tidak terdapat pada dokumen",
    "rumus": "lext = 12 * db",
    "variabel": "lext = perpanjangan lurus; db = diameter nominal batang",
    "referensi": "Bab 25 Tabel 25.3.1 Halaman 561"
  },
  {
    "kategori": "Geometri",
    "subkategori": "Kait Standar",
    "parameter": "Perpanjangan lurus (lext) kait 180°",
    "nilai": "Terbesar dari (4 * db) atau (65 mm)",
    "satuan": "mm",
    "syarat": "Penyaluran batang ulir dalam kondisi tarik",
    "pengecualian": "Tidak terdapat pada dokumen",
    "rumus": "lext = max(4*db, 65)",
    "variabel": "lext = perpanjangan lurus; db = diameter nominal batang",
    "referensi": "Bab 25 Tabel 25.3.1 Halaman 561"
  },
  {
    "kategori": "Pendetailan",
    "subkategori": "Diameter Bengkokan",
    "parameter": "Diameter sisi dalam bengkokan minimum (batang utama)",
    "nilai": "6 * db",
    "satuan": "mm",
    "syarat": "Untuk batang ulir D10 hingga D25",
    "pengecualian": "D29-D36 menggunakan 8db; D43-D57 menggunakan 10db",
    "rumus": "D_min = 6 * db",
    "variabel": "D_min = diameter bengkokan minimum; db = diameter nominal batang",
    "referensi": "Bab 25 Tabel 25.3.1 Halaman 561"
  },
  {
    "kategori": "Pelat Satu Arah",
    "subkategori": "Dimensi Minimum",
    "parameter": "Ketebalan minimum (h) pelat solid satu arah",
    "nilai": "l / 28",
    "satuan": "mm",
    "syarat": "Kondisi kedua ujung menerus; beton berat normal; fy = 420 MPa",
    "pengecualian": "Bila fy selain 420 MPa, kalikan dengan (0,4 + fy/700)",
    "rumus": "h_min = l / 28",
    "variabel": "h_min = tebal minimum; l = panjang bentang",
    "referensi": "Bab 7 Tabel 7.3.1.1 Halaman 120"
  },
  {
    "kategori": "Balok",
    "subkategori": "Dimensi Minimum",
    "parameter": "Tinggi minimum (h) balok",
    "nilai": "l / 18,5",
    "satuan": "mm",
    "syarat": "Kondisi satu ujung menerus; nonprategang; fy = 420 MPa",
    "pengecualian": "Untuk beton ringan, nilai dikalikan terbesar dari (1,65 - 0,0003wc) atau 1,09",
    "rumus": "h_min = l / 18,5",
    "variabel": "h_min = tinggi minimum; l = panjang bentang",
    "referensi": "Bab 9 Tabel 9.3.1.1 Halaman 180"
  },
  {
    "kategori": "Kolom",
    "subkategori": "Batasan Tulangan",
    "parameter": "Rasio tulangan longitudinal (Ast/Ag)",
    "nilai": "0,01 hingga 0,08",
    "satuan": "rasio",
    "syarat": "Berlaku untuk kolom nonprategang dan prategang dengan fpe < 1,6 MPa",
    "pengecualian": "Untuk SRPMK, batas atas biasanya 0,06",
    "rumus": "0,01 * Ag <= Ast <= 0,08 * Ag",
    "variabel": "Ast = luas total tulangan longitudinal; Ag = luas bruto penampang beton",
    "referensi": "Bab 10 Pasal 10.6.1.1 Halaman 215"
  },
  {
    "kategori": "Pendetailan",
    "subkategori": "Panjang Penyaluran",
    "parameter": "Panjang penyaluran tarik batang ulir (ld)",
    "nilai": "Dihitung",
    "satuan": "mm",
    "syarat": "Nilai ld minimal 300 mm; faktor modifikasi diperhitungkan",
    "pengecualian": "Kait dan kepala tulangan dilarang untuk menyalurkan tulangan tekan",
    "rumus": "ld = [ (fy / (1,1 * lambda * sqrt(f'c))) * (psi_t * psi_e * psi_s * psi_g / ((cb + Ktr)/db)) ] * db",
    "variabel": "ld = panjang penyaluran; fy = leleh baja; f'c = tekan beton; psi_t = faktor lokasi; psi_e = faktor pelapis; psi_s = faktor ukuran; psi_g = faktor mutu; cb = faktor selimut; Ktr = indeks transversal; db = diameter batang",
    "referensi": "Bab 25 Pasal 25.4.2.3 Halaman 567"
  },
  {
    "kategori": "Pendetailan",
    "subkategori": "Sambungan Lewatan",
    "parameter": "Panjang sambungan lewatan tarik (lst) Kelas B",
    "nilai": "1,3 * ld",
    "satuan": "mm",
    "syarat": "Rasio As terpasang / As perlu < 2,0 atau seluruh batang disambung pada satu lokasi",
    "pengecualian": "Minimal 300 mm",
    "rumus": "lst = 1,3 * ld",
    "variabel": "lst = panjang sambungan lewatan tarik; ld = panjang penyaluran tarik",
    "referensi": "Bab 25 Tabel 25.5.2.1 Halaman 586"
  },
  {
    "kategori": "Fondasi",
    "subkategori": "Kriteria Desain",
    "parameter": "Tinggi efektif tulangan bawah pile cap",
    "nilai": "300",
    "satuan": "mm",
    "syarat": "Ketebalan total pile cap harus menjamin d minimum terpenuhi",
    "pengecualian": "Tidak terdapat pada dokumen",
    "rumus": "d_min = 300",
    "variabel": "d_min = tinggi efektif minimum",
    "referensi": "Bab 13 Pasal 13.4.2.1 Halaman 267"
  },
  {
    "kategori": "Kekuatan",
    "subkategori": "Faktor Reduksi",
    "parameter": "Faktor reduksi kekuatan (phi) Geser",
    "nilai": "0,75",
    "satuan": "konstanta",
    "syarat": "Untuk geser dan torsi pada komponen struktur",
    "pengecualian": "Untuk SRPMK di KDS tinggi, phi bisa menjadi 0,60 jika kekuatan geser nominal kurang dari geser desain",
    "rumus": "phi = 0,75",
    "variabel": "phi = faktor reduksi",
    "referensi": "Bab 21 Tabel 21.2.1 Halaman 469"
  },
  {
    "kategori": "Material",
    "subkategori": "Beton",
    "parameter": "Modulus Elastisitas Beton (Ec)",
    "nilai": "4700 * sqrt(f'c)",
    "satuan": "MPa",
    "syarat": "Untuk beton normal",
    "pengecualian": "Untuk wc antara 1440 dan 2560 kg/m3 gunakan rumus khusus",
    "rumus": "Ec = 4700 * sqrt(f'c)",
    "variabel": "Ec = modulus elastisitas; f'c = kekuatan tekan beton",
    "referensi": "Bab 19 Pasal 19.2.2.1 Halaman 434"
  },
  {
    "kategori": "SRPMK",
    "subkategori": "Balok",
    "parameter": "Batas rasio penulangan (rho)",
    "nilai": "0,025",
    "satuan": "rasio",
    "syarat": "Maksimum rasio tulangan tarik pada sebarang penampang balok SRPMK",
    "pengecualian": "Tidak terdapat pada dokumen",
    "rumus": "rho <= 0,025",
    "variabel": "rho = As / (bw * d)",
    "referensi": "Bab 18 Pasal 18.6.3.1 Halaman 378"
  },
  {
    "kategori": "SRPMK",
    "subkategori": "Kolom",
    "parameter": "Dimensi penampang terkecil",
    "nilai": "300",
    "satuan": "mm",
    "syarat": "Diukur pada garis lurus yang melalui pusat geometri",
    "pengecualian": "Tidak terdapat pada dokumen",
    "rumus": "b_min = 300",
    "variabel": "b_min = lebar terkecil kolom",
    "referensi": "Bab 18 Pasal 18.7.2.1 Halaman 385"
  }
]
Respons tersimpan tidak dapat diedit
Karena dokumen SNI 2847:2019 sangat tebal (695 halaman), ekstraksi ini akan dilakukan secara bertahap dan sistematis. Berikut adalah Batch 1 yang berfokus pada data fundamental untuk database aplikasi: Properti Material Beton, Selimut Beton, dan Geometri Pembengkokan (Kait/Bend).
1. Properti Material Beton (Kekuatan & Elastisitas)
Tabel 19.2.1.1 - Batasan nilai f 
c
′
​
 
Kegunaan
Jenis beton
Nilai f 
c
′
​
  minimum (MPa)
Nilai f 
c
′
​
  maksimum (MPa)
Umum
Berat normal dan berat ringan
17
Tidak ada batasan
SRPMK dan Dinding Struktural Khusus
Berat normal
21
Tidak ada batasan
SRPMK dan Dinding Struktural Khusus
Berat ringan
21
35
JSON Output:
[
  {
    "kategori": "Material",
    "subkategori": "Beton",
    "parameter": "Kekuatan tekan minimum (f'c)",
    "nilai": "17",
    "satuan": "MPa",
    "syarat": "Penggunaan umum beton berat normal dan ringan",
    "pengecualian": "Untuk SRPMK dan Dinding Struktural Khusus minimal 21 MPa",
    "rumus": "Tidak terdapat pada dokumen",
    "variabel": "Tidak terdapat pada dokumen",
    "referensi": "Pasal 19 Tabel 19.2.1.1 Halaman 433"
  },
  {
    "kategori": "Material",
    "subkategori": "Beton",
    "parameter": "Modulus elastisitas (Ec)",
    "nilai": "4700 * sqrt(f'c)",
    "satuan": "MPa",
    "syarat": "Beton normal",
    "pengecualian": "Untuk wc antara 1440 dan 2560 kg/m3 gunakan rumus (a)",
    "rumus": "Ec = 4700 * sqrt(f'c)",
    "variabel": "Ec = Modulus elastisitas beton (MPa); f'c = kekuatan tekan beton yang disyaratkan (MPa)",
    "referensi": "Pasal 19.2.2.1 Halaman 434"
  }
]
2. Durabilitas: Selimut Beton Minimum
Tabel 20.6.1.3.1 - Ketebalan selimut beton untuk komponen beton nonprategang cor di tempat
Paparan
Komponen struktur
Tulangan
Selimut (mm)
Permanen kontak tanah
Semua
Semua
75
Terpapar cuaca / kontak tanah
Semua
D19 hingga D57
50
Terpapar cuaca / kontak tanah
Semua
D16, kawat D13 ke bawah
40
Tidak terpapar cuaca
Pelat, dinding
D43 dan D57
40
Tidak terpapar cuaca
Pelat, dinding
D36 ke bawah
20
Tidak terpapar cuaca
Balok, kolom, pedestal
Utama, sengkang, spiral
40
JSON Output:
[
  {
    "kategori": "Durabilitas",
    "subkategori": "Selimut Beton",
    "parameter": "Selimut beton cor permanen kontak tanah",
    "nilai": "75",
    "satuan": "mm",
    "syarat": "Beton dicor langsung dan secara permanen kontak dengan tanah",
    "pengecualian": "Tidak terdapat pada dokumen",
    "rumus": "Tidak terdapat pada dokumen",
    "variabel": "Tidak terdapat pada dokumen",
    "referensi": "Pasal 20 Tabel 20.6.1.3.1 Halaman 460"
  },
  {
    "kategori": "Durabilitas",
    "subkategori": "Selimut Beton",
    "parameter": "Selimut beton balok/kolom tidak terpapar cuaca",
    "nilai": "40",
    "satuan": "mm",
    "syarat": "Komponen balok, kolom, pedestal, dan batang tarik",
    "pengecualian": "Tidak terdapat pada dokumen",
    "rumus": "Tidak terdapat pada dokumen",
    "variabel": "Tidak terdapat pada dokumen",
    "referensi": "Pasal 20 Tabel 20.6.1.3.1 Halaman 460"
  }
]
3. Detail Penulangan: Kait Standar & Diameter Bengkokan
Tabel 25.3.1 - Geometri kait standar untuk penyaluran batang ulir pada kondisi Tarik
Tipe Kait
Ukuran Batang
Diameter Sisi Dalam Minimum
Perpanjangan Lurus (l 
ext
​
 )
90°
D10 - D25
6d 
b
​
 
12d 
b
​
 
90°
D29 - D36
8d 
b
​
 
12d 
b
​
 
90°
D43 - D57
10d 
b
​
 
12d 
b
​
 
180°
D10 - D25
6d 
b
​
 
Terbesar (4d 
b
​
 ; 65 mm)
180°
D29 - D36
8d 
b
​
 
Terbesar (4d 
b
​
 ; 65 mm)
180°
D43 - D57
10d 
b
​
 
Terbesar (4d 
b
​
 ; 65 mm)
Tabel 25.3.2 - Diameter sisi dalam bengkokan & geometri kait sengkang/ikat silang
Tipe Kait
Ukuran Batang
Diameter Sisi Dalam Minimum
Perpanjangan Lurus (l 
ext
​
 )
90°
D10 - D16
4d 
b
​
 
Terbesar (6d 
b
​
 ; 75 mm)
90°
D19 - D25
6d 
b
​
 
12d 
b
​
 
135°
D10 - D16
4d 
b
​
 
Terbesar (6d 
b
​
 ; 75 mm)
135°
D19 - D25
6d 
b
​
 
Terbesar (6d 
b
​
 ; 75 mm)
JSON Output:
[
  {
    "kategori": "Detail Penulangan",
    "subkategori": "Kait Standar",
    "parameter": "Perpanjangan kait 90 derajat",
    "nilai": "12 * db",
    "satuan": "mm",
    "syarat": "Berlaku untuk semua ukuran batang ulir",
    "pengecualian": "Kait sengkang (Stirrup) mengikuti Tabel 25.3.2",
    "rumus": "Lext = 12 * db",
    "variabel": "Lext = Panjang perpanjangan lurus (mm); db = diameter nominal batang tulangan (mm)",
    "referensi": "Pasal 25 Tabel 25.3.1 Halaman 561"
  },
  {
    "kategori": "Detail Penulangan",
    "subkategori": "Geometri Bengkokan",
    "parameter": "Diameter bengkokan minimum sengkang D10-D16",
    "nilai": "4 * db",
    "satuan": "mm",
    "syarat": "Untuk batang yang digunakan sebagai tulangan transversal",
    "pengecualian": "Batang D19-D25 menggunakan 6 * db",
    "rumus": "D_bend = 4 * db",
    "variabel": "D_bend = Diameter sisi dalam bengkokan (mm); db = diameter nominal batang (mm)",
    "referensi": "Pasal 25 Tabel 25.3.2 Halaman 562"
  }
]
4. Panjang Penyaluran (Development Length)
Pasal 25.4.2.3 - Panjang penyaluran tarik batang ulir
Rumus Utama:
l 
d
​
 = 

​
  
1,1λ 
f 
c
′
​
 

​
 
f 
y
​
 
​
  
( 
d 
b
​
 
c 
b
​
 +K 
tr
​
 
​
 )
ψ 
t
​
 ψ 
e
​
 ψ 
s
​
 ψ 
g
​
 
​
  

​
 d 
b
​
 
Batasan:
(c 
b
​
 +K 
tr
​
 )/d 
b
​
 ≤2,5
l 
d
​
 ≥300 mm
f 
c
′
​
 

​
 ≤8,3 MPa
Variabel:
l 
d
​
  = panjang penyaluran tarik (mm)
f 
y
​
  = kekuatan leleh tulangan (MPa)
f 
c
′
​
  = kekuatan tekan beton (MPa)
ψ 
t
​
  = faktor lokasi pengecoran (1,3 untuk tulangan atas, 1,0 lainnya)
ψ 
e
​
  = faktor pelapis (1,0 untuk tanpa pelapis)
ψ 
s
​
  = faktor ukuran tulangan (0,8 untuk D19 ke bawah, 1,0 untuk D22 ke atas)
ψ 
g
​
  = faktor mutu tulangan (1,0 untuk mutu 420)
λ = faktor modifikasi beton ringan (1,0 beton normal, 0,75 beton ringan)
c 
b
​
  = dimensi selimut beton (mm)
K 
tr
​
  = indeks tulangan transversal (dapat diambil 0 untuk penyederhanaan)
JSON Output:
{
  "kategori": "Detail Penulangan",
  "subkategori": "Panjang Penyaluran",
  "parameter": "Panjang penyaluran tarik batang ulir (ld)",
  "nilai": "Dihitung berdasarkan rumus",
  "satuan": "mm",
  "syarat": "Nilai ld minimal 300 mm",
  "pengecualian": "Kait dan kepala tulangan dilarang untuk menyalurkan tulangan tekan",
  "rumus": "ld = [ (fy / (1.1 * lambda * sqrt(f'c))) * (psi_t * psi_e * psi_s * psi_g / ((cb + Ktr)/db)) ] * db",
  "variabel": "ld = panjang penyaluran; fy = leleh baja; f'c = tekan beton (max 70MPa); psi_t = faktor lokasi; psi_e = faktor pelapis; psi_s = faktor ukuran; psi_g = faktor mutu; cb = faktor selimut; Ktr = indeks transversal",
  "referensi": "Bab 25 Pasal 25.4.2.3 Halaman 567"
  {
  "balok_beton_struktural": {
    "dimensi_minimum": {
      "lebar_bw_minimum": {
        "umum": "Tidak ada batas minimum absolut, ditentukan oleh syarat spasi tulangan dan selimut beton [25.2, 20.6]",
        "srpmk": "Minimal 250 mm atau 0,3h (pilih yang terkecil) [18.6.2.1]",
        "referensi": "Pasal 18.6.2.1, 20.6, 25.2"
      },
      "tinggi_minimum_h": {
        "tumpuan_sederhana": "l/16",
        "satu_ujung_menerus": "l/18,5",
        "dua_ujung_menerus": "l/21",
        "kantilever": "l/8",
        "modifikasi_fy": "Untuk fy selain 420 MPa, nilai dikalikan dengan (0,4 + fy/700)",
        "modifikasi_beton_ringan": "Kalikan dengan terbesar dari (1,65 - 0,0003wc) atau 1,09",
        "referensi": "Tabel 9.3.1.1, Pasal 9.3.1.1.1"
      },
      "batasan_srpmk": {
        "bentang_bersih_ln": "Minimal 4d",
        "proyeksi_lebar": "Lebar balok tidak boleh melebihi lebar kolom + minimal (c2; 0,75c1) pada tiap sisi",
        "referensi": "Pasal 18.6.2.1"
      }
    },
    "selimut_beton": {
      "tidak_terpapar_cuaca_kontak_tanah": {
        "tulangan_utama_sengkang_spiral": "40 mm",
        "referensi": "Tabel 20.6.1.3.1"
      },
      "terpapar_cuaca_kontak_tanah": {
        "D19_hingga_D57": "50 mm",
        "D16_dan_lebih_kecil": "40 mm",
        "referensi": "Tabel 20.6.1.3.1"
      },
      "cor_permanen_kontak_tanah": "75 mm [Tabel 20.6.1.3.1]"
    },
    "tulangan_longitudinal": {
      "diameter_minimum": "Mengikuti SNI 2052:2017 (umumnya D10)",
      "jumlah_minimum": {
        "umum": "Minimal 2 batang menerus pada sisi atas dan bawah [9.7.7.1, 18.3.2]",
        "srpmk": "Minimal 2 batang menerus pada sisi atas dan bawah [18.6.3.1]"
      },
      "luas_minimum_as_min": "Terbesar dari (0,25 * sqrt(f'c) / fy) * bw * d atau (1,4 / fy) * bw * d [9.6.1.2]",
      "rasio_maksimum": {
        "srpmk": "0,025 untuk tulangan tarik [18.6.3.1]"
      },
      "spasi_minimum": "Terbesar dari 25 mm, db, atau (4/3) d_agg [25.2.1]",
      "spasi_maksimum_kontrol_retak": "Terkecil dari 380*(280/fs) - 2,5*cc dan 300*(280/fs) [Tabel 24.3.2]"
    },
    "tulangan_transversal_sengkang": {
      "diameter_minimum": {
        "longitudinal_le_D32": "D10",
        "longitudinal_ge_D36_atau_bundel": "D13",
        "referensi": "Pasal 25.7.2.2"
      },
      "spasi_maksimum_geser_umum": {
        "Vs_le_0.33_sqrt_fc_bw_d": "Terkecil dari d/2 atau 600 mm",
        "Vs_gt_0.33_sqrt_fc_bw_d": "Terkecil dari d/4 atau 300 mm",
        "referensi": "Tabel 9.7.6.2.2"
      },
      "tumpuan_vs_lapangan": {
        "srpmk_daerah_sendi_plastis_2h": "Spasi (so) terkecil dari: d/4, 6db longitudinal terkecil, atau 150 mm [18.6.4.4]",
        "srpmm_daerah_2h": "Spasi terkecil dari: d/4, 8db longitudinal, 24db sengkang, atau 300 mm [18.4.2.4]",
        "luar_sendi_plastis": "Maksimal d/2 [18.6.4.6, 18.4.2.5]"
      }
    },
    "geometri_bengkokan_dan_kait": {
      "kait_standar_90_derajat": "Bengkokan 90° + perpanjangan 12db [Tabel 25.3.1]",
      "kait_standar_180_derajat": "Bengkokan 180° + perpanjangan terbesar dari 4db dan 65 mm [Tabel 25.3.1]",
      "kait_seismik": "Bengkokan 135° + perpanjangan terbesar dari 6db dan 75 mm [Pasal 2.3, 25.3.4]",
      "diameter_sisi_dalam_bengkokan_min": {
        "D10_D25": "6db",
        "D29_D36": "8db",
        "D43_D57": "10db",
        "sengkang_D10_D16": "4db",
        "referensi": "Tabel 25.3.1, Tabel 25.3.2"
      }
    },
    "penyaluran_dan_sambungan": {
      "panjang_penyaluran_ld": "Dihitung sesuai Pasal 25.4.2.3",
      "lap_splice_tarik": {
        "kelas_a": "1,0 ld (min. 300 mm)",
        "kelas_b": "1,3 ld (min. 300 mm)",
        "referensi": "Tabel 25.5.2.1"
      },
      "lap_splice_tekan": {
        "fy_le_420": "0,071 * fy * db",
        "fy_gt_420": "(0,13 * fy - 24) * db",
        "minimum": "300 mm",
        "referensi": "Pasal 25.5.5.1"
      },
      "mechanical_splice": "Tipe 1 (mampu mencapai 1,25fy) atau Tipe 2 (mampu mencapai kuat tarik spesifikasi batang) [18.2.7.1, 25.5.7.1]"
    },
    "persyaratan_khusus_torsi": {
      "ambang_torsi_solid": "0,083 * lambda * sqrt(f'c) * (Acp^2 / Pcp)",
      "spasi_maksimum_sengkang_torsi": "Terkecil dari Ph/8 atau 300 mm",
      "referensi": "Pasal 22.7.4.1, 9.7.6.3.3"
    },
    "syarat_sistem_rangka": {
      "srpmk": {
        "kekuatan_momen": "Momen positif tumpuan >= 1/2 momen negatif tumpuan; Momen positif/negatif sepanjang bentang >= 1/4 momen tumpuan maks [18.6.3.2]",
        "sambungan_lewatan": "Dilarang di daerah joint dan sejarak 2h dari muka tumpuan [18.6.3.3]"
      },
      "srpmm": {
        "sengkang_tertutup": "Dipasang sepanjang 2h dari muka tumpuan [18.4.2.4]"
      },
      "srpmb": {
        "longitudinal": "Minimal 2 batang menerus sisi atas dan bawah [18.3.2]"
      }
    }
  }
}
{
  "kolom_beton_struktural": {
    "dimensi_minimum": {
      "umum": "Tidak ditentukan batas minimum eksplisit untuk beban ringan (seperti rumah tinggal), namun harus memperhatikan ketelitian pengerjaan dan tegangan susut.",
      "srpmk": "Dimensi penampang terkecil minimal 300 mm; Rasio dimensi penampang terkecil terhadap dimensi tegak lurusnya tidak kurang dari 0,4.",
      "referensi": "Pasal 10.3.1, 18.7.2.1"
    },
    "rasio_tulangan": {
      "umum": "Minimum 0,01 Ag dan Maksimum 0,08 Ag.",
      "srpmk": "Minimum 0,01 Ag dan Maksimum 0,06 Ag.",
      "catatan": "Rasio > 0,04 tidak disarankan jika menggunakan sambungan lewatan karena kerapatan tulangan di zona sambungan.",
      "referensi": "Pasal 10.6.1.1, 18.7.4.1, R10.6.1.1"
    },
    "jumlah_minimum_batang": {
      "sengkang_ikat_segitiga": 3,
      "sengkang_ikat_segi_empat_atau_lingkaran": 4,
      "sengkang_spiral": 6,
      "srpmk_bundar": 6,
      "referensi": "Pasal 10.7.3.1, 18.7.4.2"
    },
    "diameter_minimum_dan_maksimum": {
      "tulangan_longitudinal": "Sesuai spesifikasi baja tulangan beton (SNI 2052:2017), umumnya D10 hingga D57.",
      "tulangan_spiral_cor_di_tempat": "Minimal 9,5 mm (D10 atau 8).",
      "referensi": "Pasal 20.2, 25.7.3.2"
    },
    "selimut_beton": {
      "tidak_terpapar_cuaca_atau_kontak_tanah": "40 mm",
      "terpapar_cuaca_atau_kontak_tanah": "D19-D57: 50 mm; D16 kebawah: 40 mm",
      "permanen_kontak_tanah": "75 mm",
      "referensi": "Tabel 20.6.1.3.1"
    },
    "diameter_sengkang": {
      "untuk_longitudinal_le_D32": "D10",
      "untuk_longitudinal_ge_D36_atau_bundel": "D13",
      "kolom_komposit_inti_baja": "Minimal 0,02 kali sisi terbesar kolom (D10 s.d D16).",
      "referensi": "Pasal 25.7.2.2, 10.7.6.1.4"
    },
    "crosstie_ikat_silang": {
      "detail": "Batang tulangan menerus dengan kait gempa di satu ujung dan kait minimal 90 derajat dengan perpanjangan 6db di ujung lainnya. Kait harus memegang batang longitudinal tepi.",
      "pemasangan": "Ujung kait 90 derajat harus diselang-seling pada sisi yang berlawanan.",
      "referensi": "Pasal 2.3, 25.3.5"
    },
    "spiral": {
      "spasi_bersih": "Antara 25 mm hingga 75 mm.",
      "angkur": "1,5 putaran tambahan di setiap ujung.",
      "sambungan_lewatan": "48db (untuk batang tanpa pelapis) atau 72db (untuk batang berlapis epoksi), minimal 300 mm.",
      "referensi": "Pasal 25.7.3.1, 25.7.3.4, Tabel 25.7.3.6"
    },
    "kait_standar": {
      "90_derajat": "Bengkokan 90 derajat + perpanjangan lurus 12db.",
      "180_derajat": "Bengkokan 180 derajat + perpanjangan lurus terbesar dari 4db dan 65 mm.",
      "diameter_bengkokan_min": "D10-D25: 6db; D29-D36: 8db; D43-D57: 10db.",
      "referensi": "Tabel 25.3.1"
    },
    "lap_splice_sambungan_lewatan": {
      "umum": "Tidak diizinkan untuk batang > D36 (kecuali ke fondasi dengan syarat tertentu).",
      "tekan": "fy <= 420 MPa: Terbesar dari 0,071 fy db atau 300 mm; fy > 420 MPa: (0,13 fy - 24) db.",
      "tarik": "Kelas A (1.0 ld) atau Kelas B (1.3 ld).",
      "srpmk": "Hanya diizinkan di tengah tinggi kolom; didesain sebagai sambungan tarik; harus dilingkupi sengkang pengekang.",
      "referensi": "Pasal 25.5.1.1, 25.5.5.1, 10.7.5.2.2, 18.7.4.3"
    },
    "development_length_panjang_penyaluran": {
      "rumus_tarik_ulir": "ld = [ (fy / (1,1 * lambda * sqrt(f'c))) * (psi_t * psi_e * psi_s * psi_g / ((cb + Ktr)/db)) ] * db",
      "tekan_ulir": "ldc = Terbesar dari (0,24 fy psi_r / (lambda * sqrt(f'c))) * db atau 0,043 fy psi_r db. Minimal 200 mm.",
      "kait_tarik": "ldh = (0,24 fy psi_e psi_c psi_r / (lambda * sqrt(f'c))) * db. Minimal terbesar dari 8db atau 150 mm.",
      "referensi": "Pasal 25.4.2.3, 25.4.9.1, 25.4.3.1"
    },
    "confinement_pengekangan": {
      "srpmk_ash_sbc_persegi": "Terbesar dari: 0,3*((Ag/Ach)-1)*(f'c/fyt) atau 0,09*(f'c/fyt). Jika Pu > 0.3Agf'c, gunakan tambahan rumus (c) di Tabel 18.7.5.4.",
      "srpmk_rho_s_spiral": "Terbesar dari: 0,45*((Ag/Ach)-1)*(f'c/fyt) atau 0,12*(f'c/fyt).",
      "referensi": "Tabel 18.7.5.4"
    },
    "spasi_sengkang": {
      "umum": "Minimal (4/3) d_agg. Maksimal terkecil dari: 16db longitudinal, 48db sengkang, atau dimensi terkecil kolom.",
      "srpmk_so": "Sepanjang lo, spasi tidak melebihi terkecil dari: 1/4 dimensi min kolom, 6db longitudinal terkecil, atau so = 100 + (350 - hx)/3 (antara 100-150 mm).",
      "referensi": "Pasal 25.7.2.1, 18.7.5.3"
    },
    "daerah_sendi_plastis_lo": {
      "srpmk": "lo minimal terbesar dari: tinggi kolom pada muka joint, 1/6 tinggi bersih kolom, atau 450 mm.",
      "srpmm": "lo minimal terbesar dari: seperenam tinggi bersih kolom, dimensi maksimum penampang kolom, atau 450 mm.",
      "referensi": "Pasal 18.7.5.1, 18.4.3.3"
    },
    "syarat_srpmk": {
      "kekuatan_lentur": "Jumlah kekuatan lentur nominal kolom (Mnc) >= 1,2 kali jumlah kekuatan lentur nominal balok (Mnb) pada joint.",
      "geser_desain": "Ve dihitung berdasarkan Mpr pada ujung-ujung kolom.",
      "transversal": "Harus memenuhi detail pengekangan ketat (hoops/spiral) di sepanjang lo.",
      "referensi": "Pasal 18.7.3.2, 18.7.5, 18.7.6.1.1"
    },
    "syarat_srpmm": {
      "geser_desain": "Ve diambil dari nilai terkecil antara: (a) geser akibat M_nominal di ujung kolom (kurvatur ganda), atau (b) geser maksimum dari kombinasi beban gempa dengan faktor Omega_0.",
      "transversal": "Sengkang tertutup dengan spasi so sepanjang lo di kedua ujung kolom.",
      "referensi": "Pasal 18.4.3.1, 18.4.3.3"
    },
    "syarat_srpmb": {
      "umum": "Kolom dengan panjang tak tertumpu lu <= 5c1 harus memiliki kekuatan geser desain phi Vn minimal sesuai ketentuan 18.3.3.",
      "referensi": "Pasal 18.3.3"
    }
  }
}
Respons tersimpan tidak dapat diedit
{
  "pelat_beton_struktural": {
    "tebal_minimum": {
      "pelat_satu_arah_non_prategang": {
        "tumpuan_sederhana": "l/20",
        "satu_ujung_menerus": "l/24",
        "kedua_ujung_menerus": "l/28",
        "kantilever": "l/10",
        "catatan": "Berlaku untuk fy = 420 MPa. Untuk fy > 420 MPa, nilai dikalikan (0,4 + fy/700). Untuk beton ringan, nilai dikalikan dengan terbesar dari (1,65 - 0,0003wc) atau 1,09.",
        "referensi": "Tabel 7.3.1.1, Pasal 7.3.1.1.1, 7.3.1.1.2"
      },
      "pelat_dua_arah_non_prategang": {
        "tanpa_balok_interior": {
          "tanpa_drop_panel": "125 mm",
          "dengan_drop_panel": "100 mm",
          "referensi": "Pasal 8.3.1.1"
        },
        "dengan_balok_interior": {
          "alfa_fm_le_0.2": "Gunakan ketentuan pelat tanpa balok interior",
          "0.2_lt_alfa_fm_le_2.0": "ln(0,8 + fy/1400) / (36 + 5 * beta * (alfa_fm - 0,2)) dan tidak boleh < 125 mm",
          "alfa_fm_gt_2.0": "ln(0,8 + fy/1400) / (36 + 9 * beta) dan tidak boleh < 90 mm",
          "referensi": "Tabel 8.3.1.2"
        }
      }
    },
    "tebal_maksimum": {
      "keterangan": "Tidak dibatasi secara numerik tunggal; dibatasi oleh persyaratan kekuatan geser, lendutan, dan batasan spasi/regangan.",
      "referensi": "Pasal 7.5, 8.5"
    },
    "selimut_beton": {
      "cor_di_tempat_non_prategang": {
        "permanen_kontak_tanah": "75 mm",
        "terpapar_cuaca_kontak_tanah": "D16 kebawah: 40 mm; D19 - D57: 50 mm",
        "tidak_terpapar_cuaca": "D36 kebawah: 20 mm; D43 - D57: 40 mm",
        "referensi": "Tabel 20.6.1.3.1"
      },
      "cor_di_tempat_prategang": {
        "permanen_kontak_tanah": "75 mm",
        "terpapar_cuaca_kontak_tanah": "25 mm (Pelat/Dinding)",
        "tidak_terpapar_cuaca": "20 mm (Pelat/Dinding)",
        "referensi": "Tabel 20.6.1.3.2"
      }
    },
    "tulangan_lentur": {
      "arah_x_dan_y": "Dihitung berdasarkan momen terfaktor Mu sesuai prosedur analisis Pasal 6.",
      "pelat_dua_arah_lajur_kolom": "Dibatasi oleh lebar efektif c1 + 3h atau sesuai distribusi lajur kolom.",
      "referensi": "Pasal 7.4.2, 8.4.2, 8.10.5"
    },
    "tulangan_susut_dan_temperatur": {
      "fungsi": "Menahan tegangan akibat penyusutan dan perubahan suhu, dipasang tegak lurus tulangan lentur (untuk pelat satu arah).",
      "referensi": "Pasal 24.4, 7.6.4"
    },
    "rasio_penulangan_minimum": {
      "batang_ulir_fy_lt_420_mpa": "0.0020 * Ag",
      "batang_ulir_fy_ge_420_mpa": "Terbesar dari (0,0018 * 420 / fy) * Ag atau 0,0014 * Ag",
      "pelat_prategang": "Tegangan tekan rata-rata minimum 0,7 MPa untuk susut/suhu; 0,9 MPa untuk kekuatan desain pelat dua arah.",
      "referensi": "Tabel 7.6.1.1, Tabel 8.6.1.1, Pasal 8.6.2.1, 24.4.4.1"
    },
    "rasio_penulangan_maksimum": {
      "kriteria": "Dibatasi oleh regangan tarik neto minimum (epsilon_t) sebesar 0,004 pada kekuatan nominal.",
      "referensi": "Pasal 7.3.3.1, 8.3.3.1"
    },
    "spasi_maksimum_tulangan": {
      "tulangan_lentur_ulir": {
        "pelat_satu_arah": "Terkecil dari 3h dan 450 mm",
        "pelat_dua_arah_kritis": "Terkecil dari 2h dan 450 mm",
        "pelat_dua_arah_non_kritis": "Terkecil dari 3h dan 450 mm",
        "referensi": "Pasal 7.7.2.3, 8.7.2.2"
      },
      "tulangan_susut_dan_suhu": {
        "spasi": "Terkecil dari 5h dan 450 mm",
        "referensi": "Pasal 24.4.3.3"
      }
    },
    "panjang_penyaluran_development_length": {
      "rumus_umum_tarik": "ld = [ (fy / (1,1 * lambda * sqrt(f'c))) * (psi_t * psi_e * psi_s * psi_g / ((cb + Ktr)/db)) ] * db",
      "syarat_minimum": "ld >= 300 mm (untuk sambungan lewatan tarik)",
      "referensi": "Pasal 25.4.2.3, 25.5.2.1"
    },
    "sambungan_lewatan_lap_splice": {
      "tarik": {
        "kelas_a": "1,0 * ld",
        "kelas_b": "1,3 * ld",
        "minimum": "300 mm",
        "referensi": "Tabel 25.5.2.1"
      },
      "tekan": {
        "fy_le_420_mpa": "Terbesar dari (0,071 * fy * db) dan 300 mm",
        "fy_gt_420_mpa": "Terbesar dari (0,13 * fy - 24) * db dan 300 mm",
        "referensi": "Pasal 25.5.5.1"
      }
    },
    "kait_standar": {
      "kait_90_derajat": {
        "perpanjangan_lurus": "12 * db",
        "referensi": "Tabel 25.3.1"
      },
      "kait_180_derajat": {
        "perpanjangan_lurus": "Terbesar dari 4 * db dan 65 mm",
        "referensi": "Tabel 25.3.1"
      },
      "diameter_bengkokan_minimum": {
        "D10_D25": "6 * db",
        "D29_D36": "8 * db",
        "referensi": "Tabel 25.3.1"
      }
    }
  }
}
``` [1-20]
Berikut adalah data teknis dari SNI 2847:2019 yang diperlukan untuk pembuatan software Bar Bending Schedule (BBS):
1. Kait Standar (Standard Hook) dan Geometri
Data ini digunakan untuk menghitung panjang tambahan tulangan akibat pembengkokan di ujung.
Nama Aturan
Syarat / Kondisi
Rumus / Nilai (Perpanjangan Lurus l 
ext
​
 )
Referensi
Kait 90°
Batang Ulir (Tarik)
12d 
b
​
 
Tabel 25.3.1
Kait 180°
Batang Ulir (Tarik)
Terbesar dari: 4d 
b
​
  atau 65 mm
Tabel 25.3.1
Kait Sengkang 90°
Batang D10 - D16
Terbesar dari: 6d 
b
​
  atau 75 mm
Tabel 25.3.2
Kait Sengkang 90°
Batang D19 - D25
12d 
b
​
 
Tabel 25.3.2
Kait Sengkang 135°
Batang D10 - D25
Terbesar dari: 6d 
b
​
  atau 75 mm
Tabel 25.3.2
Kait Seismik
Semua kondisi gempa
Terbesar dari: 6d 
b
​
  atau 75 mm (Bengkokan ≥135 
∘
 )
Pasal 2.3
, 18.6.4.3
2. Diameter Bengkokan Minimum (Minimum Bending Diameter)
Data ini menentukan radius lekukan agar baja tidak patah dan beton tidak hancur di sisi dalam.
Nama Aturan
Ukuran Batang (d 
b
​
 )
Diameter Sisi Dalam Minimum
Referensi
Tulangan Utama
D10 s.d D25
6d 
b
​
 
Tabel 25.3.1
D29 s.d D36
8d 
b
​
 
Tabel 25.3.1
D43 s.d D57
10d 
b
​
 
Tabel 25.3.1
Sengkang / Ikat Silang
D10 s.d D16
4d 
b
​
 
Tabel 25.3.2
D19 s.d D25
6d 
b
​
 
Tabel 25.3.2
3. Panjang Penyaluran (Development Length)
Data dasar untuk menentukan panjang penanaman minimum batang baja agar mampu mengembangkan kekuatan lelehnya.
Nama Aturan
Rumus Utama
Parameter Penting
Referensi
Batang Ulir (Tarik)
l 
d
​
 =[ 
1.1λ 
f 
c
′
​
 

​
 
f 
y
​
 
​
  
( 
d 
b
​
 
c 
b
​
 +K 
tr
​
 
​
 )
ψ 
t
​
 ψ 
e
​
 ψ 
s
​
 ψ 
g
​
 
​
 ]d 
b
​
 
ψ 
t
​
  (posisi), ψ 
e
​
  (epoksi), ψ 
s
​
  (ukuran), c 
b
​
  (selimut), K 
tr
​
  (pengkang)
Pasal 25.4.2.3
Kait Standar (Tarik)
l 
dh
​
 =( 
λ 
f 
c
′
​
 

​
 
0.24f 
y
​
 ψ 
e
​
 ψ 
c
​
 ψ 
r
​
 
​
 )d 
b
​
 
Min. terbesar dari 8d 
b
​
  atau 150 mm
Pasal 25.4.3.1
Batang Ulir (Tekan)
l 
dc
​
 =terbesar dari  
λ 
f 
c
′
​
 

​
 
0.24f 
y
​
 ψ 
r
​
 
​
 d 
b
​
  atau 0.043f 
y
​
 ψ 
r
​
 d 
b
​
 
Min. 200 mm
Pasal 25.4.9.2
Kait Seismik (Pasal 18)
l 
dh
​
 = 
5.4λ 
f 
c
′
​
 

​
 
f 
y
​
 d 
b
​
 
​
 
Khusus Rangka Momen Khusus (KDS D-F)
Pasal 18.8.5.1
4. Sambungan Lewatan (Lap Splice)
Nama Aturan
Syarat / Nilai
Rumus / Ketentuan
Referensi
Sambungan Tarik
Kelas A
1.0l 
d
​
  (Min. 300 mm)
Tabel 25.5.2.1
Kelas B
1.3l 
d
​
  (Min. 300 mm)
Tabel 25.5.2.1
Sambungan Tekan
f 
y
​
 ≤420 MPa
0.071f 
y
​
 d 
b
​
  (Min. 300 mm)
Pasal 25.5.5.1
f 
y
​
 >420 MPa
(0.13f 
y
​
 −24)d 
b
​
  (Min. 300 mm)
Pasal 25.5.5.1
5. Sengkang, Ikat Silang, dan Spiral
Komponen
Nama Aturan / Syarat
Nilai / Batasan
Referensi
Sengkang (Stirrup)
Spasi Maksimum (s)
Terkecil dari d/2 atau 600 mm (Non-Seismik)
Tabel 9.7.6.2.2
Ikat Silang (Crosstie)
Detail
Kait 135° di satu ujung, kait 90° di ujung lain (selang-seling)
Pasal 25.3.5
Spiral
Diameter Min / Spasi
Min. D10; Spasi bersih 25 mm s.d 75 mm
Pasal 25.7.3
Angkur Ujung
1.5 putaran tambahan
Pasal 25.7.3.4
6. Pengekangan (Confinement) pada Struktur Seismik
Penting untuk menghitung spasi sengkang pada daerah "sendi plastis" kolom (daerah l 
o
​
 ).
Nama Aturan
Rumus Spasi (s 
o
​
 )
Parameter
Referensi
Spasi Sengkang Pengekang
s 
o
​
 =100+( 
3
350−h 
x
​
 
​
 )
h 
x
​
  = spasi horizontal maksimum kaki sengkang
Pasal 18.7.5.3
Batas Spasi s 
o
​
 
100 mm≤s 
o
​
 ≤150 mm
Dimensi penampang kolom
Pasal 18.7.5.3
Catatan Tambahan untuk Developer:
Bend Deduction: SNI tidak memberikan nilai "pengurangan panjang akibat tekukan" secara eksplisit dalam mm. Namun, software BBS biasanya menghitung ini secara geometris berdasarkan diameter sisi dalam bengkokan (poin 2 di atas) dan tebal tulangan.
Beton Ringan (λ): Jika menggunakan beton ringan, panjang penyaluran harus dikalikan faktor modifikasi λ=0.75 atau sesuai hasil uji
.