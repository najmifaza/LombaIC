# KilasTugas: Repositori Kompetisi Informatics Championship 2026

Repositori resmi pengumpulan proposal dan dokumentasi teknis inovasi KilasTugas untuk ajang Informatics Championship x Catalyst Hackathon 2026, Universitas Jenderal Soedirman.

## Informasi Tim dan Produk

* Nama Tim: Tim kata najmi gini doang sambil tidur bisa
* Institusi: Universitas Jenderal Soedirman
* Kategori Lomba: Catalyst Hackathon 2026
* Tema: Digital Solutions for Everyday Problems
* Judul Produk: KilasTugas (Smart Actionable Task Breakdown and Micro-Pacing for Students)
* Repositori Kode Sumber Aplikasi: https://github.com/najmifaza/KilasTugas_SIFest_KmHarkatNegri_JadiH-1
* Implementasi Langsung (Live Demo): https://kilastugas.vercel.app
* Antarmuka Pemrograman Aplikasi (API Endpoint): https://api-kilastugas.najmifaza.my.id

### Anggota Pengembang

1. Adridinan Najmi Faza (Ketua Tim / Pengembang Sistem)
2. Timotius Willy Narendra (Pengembang Perangkat Lunak)
3. Fardizza Finda Rahman (Analis Sistem)

## Ringkasan Masalah

Mahasiswa aktif rata-rata menempuh 4 hingga 7 mata kuliah per semester dengan variasi penugasan teknis dan akademis yang padat. Instruksi tugas yang panjang dan abstrak memicu kondisi Task Paralysis, yaitu kebuntuan kognitif saat menentukan titik awal pengerjaan.

Aplikasi pencatat tugas konvensional memiliki tiga batasan:
1. Bersifat pasif dan hanya berorientasi pada tenggat waktu tanpa memecah langkah kerja konkret.
2. Tidak menyediakan panduan ritme harian (micro-pacing), sehingga memicu penumpukan kerja pada malam sebelum pengumpulan (SKS).
3. Memerlukan konfigurasi awal yang rumit sebelum pengguna dapat mulai bekerja.

## Solusi KilasTugas

KilasTugas mengonversi instruksi tugas kuliah menjadi rencana aksi harian terukur dengan durasi 25 hingga 45 menit per langkah. Sistem bekerja melalui empat pilar utama:

1. Dekomposisi Tugas Tri-Engine
Sistem memproses instruksi melalui tiga lapisan redundansi:
* Pencarian Cache Relasional: Mencocokkan teks tugas pada basis data untuk waktu respons di bawah 20 milidetik.
* Inferensi Kecerdasan Artifisial: Mengurai instruksi baru menjadi urutan sub-tugas terstruktur dalam skema JSON terstandarisasi.
* Pola Baku Terprogram: Menyediakan templat instruksi kurikulum siap pakai jika koneksi jaringan terputus.

2. Pemantauan Ritme Kerja Harian (Visual Micro-Pacing)
Sistem menghitung rasio penyelesaian tugas harian terhadap sisa hari menuju tenggat waktu. Status pengerjaan ditampilkan secara objektif:
* On Track: Sub-tugas harian terselesaikan sesuai jadwal.
* Behind Schedule: Terdapat sub-tugas tertunda yang melewati tanggal target.
* Overdue: Tenggat akhir tugas telah terlewati.

3. Mesin Fokus Pomodoro Terintegrasi
Pewaktu fokus 25 menit berjalan menggunakan sinkronisasi stempel waktu absolut (Date.now) untuk mencegah desinkronisasi saat tab peramban berada di latar belakang. Audio notifikasi diproduksi secara lokal melalui Web Audio API tanpa beban aset eksternal.

4. Berbagi Rencana Tugas (Blueprint Sharing)
Pengguna dapat membagikan struktur rencana tugas ke rekan satu kelompok melalui tautan ringkas /p/:id. Penerima dapat menyalin seluruh rangkaian sub-tugas ke sesi kerja lokal dalam satu transaksi basis data.

## Arsitektur Sistem

KilasTugas memisahkan antarmuka pengguna, pemrosesan logika, basis data relasional, dan gerbang inferensi model:

```
[ Klien Web / Ponsel Pintar ]
               │
          Permintaan HTTPS
               ▼
[ Proksi Terbalik Nginx & Sertifikat SSL Let's Encrypt ]
               │
         Port Lokal 8001
               ▼
[ Layanan Backend: FastAPI (Python 3.12) ]
        │                             │
  Koneksi TCP 3306              HTTP Port 20128
        ▼                             ▼
[ Basis Data MariaDB 10.11 ]    [ Gerbang Inferensi 9Router ]
                                      │
                                      ▼
                                [ Gemini AI Model ]
```

### Spesifikasi Tumpukan Teknologi

| Lapisan Sistem | Perangkat Lunak | Keterangan Implementasi |
| :--- | :--- | :--- |
| Antarmuka Klien | React 18, Vite 5, Tailwind CSS | Aplikasi satu halaman, tema terang kontras tinggi |
| Layanan Backend | FastAPI, Python 3.12, Uvicorn | Server asinkronus, validasi data Pydantic v2 |
| Penyimpanan Data | MariaDB 10.11 Enterprise | Skema relasional ACID dengan pooling aiomysql |
| Gerbang Inferensi | 9Router Gateway | Protokol kompatibel OpenAI untuk inferensi terstruktur |
| Infrastruktur | Ubuntu Cloud VPS dan Vercel Edge | Penyaluran konten statis global dan API privat |

## Berkas Dokumentasi dalam Repositori

Repositori ini memuat berkas resmi pengajuan inovasi:
* PROPOSAL-KILASTUGAS-HACK-IC-2026.pdf: Berkas proposal lengkap format resmi kompetisi.
* PROPOSAL-KILASTUGAS-HACK-IC-2026.docx: Berkas naskah sumber pengolah kata.
* PROPOSAL-KILASTUGAS-HACK-IC-2026.md: Naskah teks terstruktur proposal.
* PrdUpdate.md: Dokumen spesifikasi teknis arsitektur, skema data DDL, dan kontrak endpoint API.
* HACK-IC-2026.md: Salinan panduan resmi dan rubrik penilaian kompetisi.
* Diagram_KilasTugas-1. Alur Solusi KilasTugas (1).jpg: Diagram alur solusi sistem.
* Diagram_KilasTugas-2. Arsitektur Sistem KilasTugas (1).jpg: Diagram topologi arsitektur sistem.
