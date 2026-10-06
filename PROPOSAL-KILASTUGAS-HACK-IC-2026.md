# PROPOSAL INOVASI DIGITAL
### INFORMATICS CHAMPIONSHIP x CATALYST HACKATHON 2026
**Tema:** Digital Solutions for Everyday Problems

---

<p align="center">
  <img src="./logo_unsoed.png" alt="Logo Universitas Jenderal Soedirman" width="180"/>
</p>

# KILASTUGAS
### *Smart Actionable Task Breakdown & Micro-Pacing for Students*
> *"Ubah Beban Tugas Kompleks Menjadi Aksi Harian yang Jelas, Ringan, dan Tereksekusi"*

**Disusun oleh: Tim kata najmi gini doang sambil tidur bisa**
- Adridinan Najmi Faza (Ketua Tim)
- Timotius Willy Narendra
- Fardizza Finda Rahman

**FAKULTAS TEKNIK**  
**UNIVERSITAS JENDERAL SOEDIRMAN**  
**PURWOKERTO**  
**2026**  

---

### 1. DESKRIPSI PERMASALAHAN

#### 1.1 Fenomena Nyata Penugasan Mahasiswa
Di jenjang perguruan tinggi, mahasiswa rata-rata menempuh 4 hingga 7 mata kuliah aktif per semester. Setiap mata kuliah membebankan penugasan dengan karakteristik beragam: penyusunan makalah riset, laporan praktikum laboratorium, proyek pemrograman perangkat lunak, telaah jurnal ilmiah, hingga presentasi kelompok.

Tuntutan tersebut sering kali diserahkan oleh pengajar dalam bentuk silabus atau deskripsi instruksi yang panjang, padat, dan abstrak (misal: *"Susun laporan akhir perancangan jaringan VLSM 5 bab lengkap dengan simulasi Packet Tracer"*). Ketika beban tugas rumit datang bersamaan, mayoritas mahasiswa mengalami kebuntuan kognitif. Fenomena psikologis ini dikenal sebagai **Task Paralysis** atau **Overwhelm Freeze**: kondisi di mana seseorang justru tidak memulai pengerjaan bukan karena malas atau abai, melainkan karena otak mengalami *cognitive overload* dan bingung menentukan titik awal tindakan (*"where to start"*).

#### 1.2 Gap Analisis Alat Manajemen Tugas Konvensional
Mahasiswa saat ini telah menggunakan berbagai platform produktivitas populer (Notion, Google Keep, Todoist, Trello, Google Tasks). Namun instrumen-instrumen tersebut menyisakan *critical gap*:
1. **Hanya Bersifat Pasif (Deadline-Centric, Bukan Action-Centric):** Aplikasi mencatat nama tugas dan tanggal tenggat, namun menyerahkan 100% beban pemecahan langkah kerja kepada pengguna yang sedang kewalahan kognitif.
2. **Ketiadaan Micro-Pacing:** Pengguna tidak dipandu secara harian berapa porsi kerja aman yang harus dicicil per hari berdasarkan jarak tanggal pengumpulan. Akibatnya timbul ilusi waktu luang semu yang berujung pada *panic working* di malam H-1/H-0.
3. **Friksi Awal Terlalu Tinggi:** Aplikasi manajemen proyek formal menuntut konfigurasi manual yang rumit (pembuatan database board, tagging, estimasi manual), sehingga energi mahasiswa terkuras sebelum sempat bekerja.

#### 1.3 Rumusan Masalah Utama
> *"Bagaimana merancang platform digital yang mampu mengeliminasi Task Paralysis pada mahasiswa dengan mentransformasi instruksi tugas kuliah yang panjang menjadi rencana aksi harian yang mikro, konkret, terdistribusi merata, serta terintegrasi langsung dengan mesin fokus eksekusi?"*

---

### 2. TARGET USER
1. **Mahasiswa Aktif:** Khususnya mahasiswa teknik/informatika dan sains yang menghadapi beban tugas berbasis praktikum, penulisan makalah, atau proyek teknis berskala besar.
2. **Kelompok Belajar & Praktikan Kampus:** Tim mahasiswa yang membutuhkan standardisasi pembagian beban kerja dan target harian yang terukur.
3. **Pelajar & Akademisi:** Pengguna yang membutuhkan manajemen waktu berbasis micro-tasking untuk mengatasi prokrastinasi.

---

### 3. SOLUSI YANG DIUSULKAN
KilasTugas menghadirkan platform web produktivitas yang mengubah deskripsi tugas kuliah yang panjang/kompleks menjadi daftar sub-tugas harian konkret (*actionable micro-tasks*) secara instan melalui sistem **Tri-Engine Breakdown**:
- **Otomasi Breakdown Cerdas:** Menganalisis instruksi tugas dan memecahnya menjadi langkah kerja berdurasi realistis (25–45 menit) yang dipetakan secara proporsional dari hari pendaftaran hingga sebelum deadline.
- **Visual Micro-Pacing:** Indikator visual real-time yang memantau apakah progres belajar mahasiswa *On Track*, *Behind Schedule*, atau *Overdue* berdasarkan target tanggal sub-tugas harian.
- **Persistent Focus Timer (Pomodoro):** Timer fokus berbasis sinkronisasi timestamp absolut dan Web Audio API untuk eksekusi langkah kerja tanpa distraksi.
- **One-Click Blueprint Cloning:** Kemampuan mengekspor dan membagikan skema langkah tugas kepada mahasiswa lain melalui URL instan `/p/:id` tanpa registrasi akun yang rumit.

![Alur Solusi KilasTugas](./Diagram_KilasTugas-1.%20Alur%20Solusi%20KilasTugas%20(1).jpg)  
*Gambar 1: Alur Kerja dan Solusi Sistem KilasTugas*

---

### 4. GAMBARAN FITUR UTAMA
1. **Tri-Engine Task Breakdown:**
   - *Smart Cache Lookup:* Pencocokan tugas serupa pada database relasional untuk respon instan (<20ms).
   - *AI Inference Breakdown:* Mesin inferensi AI terstruktur untuk dekomposisi langkah tugas kompleks menjadi format JSON mikro-langkah.
   - *Deterministic Fallback:* Template kurikulum siap pakai saat kondisi koneksi internet terbatas.
2. **Dynamic Task & Micro-Pacing Dashboard:**
   - Visualisasi gauge persentase progres total.
   - Penjadwalan tanggal target per sub-tugas harian.
   - Indikator status ritme pengerjaan (*On Track* vs *Behind Schedule*).
3. **Built-in Focus Engine (Pomodoro Session):**
   - Stopwatch fokus 25 menit anti-drifting (akurasi timestamp sistem).
   - Indikator sisa waktu langsung pada title bar peramban web.
   - Dual-tone synthesizer alert lokal via Web Audio API.
4. **Export & Sync Integration:**
   - Ekspor berkas standar kalender RFC 5545 (`.ics`) dengan alarm otomatis H-15 menit.
   - Direct Google Calendar Intent URL untuk integrasi instan ke gawai Android/iOS.
5. **Blueprint Sharing & Cloning (`/p/:id`):**
   - Berbagi alur langkah pengerjaan tugas via tautan ringkas.
   - Pengguna lain dapat mengkloning rantai tugas ke sesi mereka dengan penyesuaian deadline otomatis dalam 1 transaksi basis data.

---

### 5. TEKNOLOGI YANG DIRENCANAKAN
- **Frontend Layer:**
  - Framework: React 18 + Vite 5 (SPA ringan, output <90KB gzip)
  - Styling: Tailwind CSS (Clean Editorial Light Theme)
  - Ikonografi & Umpan Balik: Lucide Icons, Canvas Confetti
  - HTTP Client: Axios (Interceptors & Error Boundary)
  - Deployment: Vercel Global Edge Network
- **Backend Layer:**
  - Runtime: Python 3.12
  - Framework: FastAPI (Asynchronous ASGI, Pydantic v2 data validation)
  - Server: Uvicorn Standard + Nginx Reverse Proxy (SSL Let's Encrypt TLS)
  - Host: Ubuntu Cloud VPS
- **Basis Data:**
  - RDBMS: MariaDB 10.11 Enterprise (ACID compliant, UTF8mb4, connection pooling via `aiomysql`)
- **AI Gateway & Inference:**
  - 9Router Inference Gateway (OpenAI-compatible protocol)
  - Model: Gemini 3.7 Flash Medium (Output valid JSON Schema, low latency <2.0s)

![Arsitektur Sistem KilasTugas](./Diagram_KilasTugas-2.%20Arsitektur%20Sistem%20KilasTugas%20(1).jpg)  
*Gambar 2: Topologi Arsitektur Terdistribusi KilasTugas*

---

### 6. DAMPAK / MANFAAT YANG DIHARAPKAN
1. **Penurunan Beban Kognitif Mahasiswa:** Menghilangkan kebingungan langkah awal (*blank page syndrome* / *Task Paralysis*) saat memulai tugas kuliah berskala besar.
2. **Pemberantasan Budaya Sistem Kebut Semalam (SKS):** Mendorong distribusi pengerjaan tugas secara bertahap dan teratur setiap hari melalui micro-deadlines.
3. **Efisiensi Waktu & Kolaborasi Akademik:** Memfasilitasi pertukaran standar langkah kerja yang terbukti efektif antar mahasiswa, memangkas waktu perencanaan tugas kelompok.
4. **Aksesibilitas Tanpa Hambatan:** Pengguna dapat langsung memanfaatkan aplikasi tanpa wajib login rumit (*guest-mode session*) dengan latensi responsif di berbagai perangkat (desktop, tablet, mobile).
