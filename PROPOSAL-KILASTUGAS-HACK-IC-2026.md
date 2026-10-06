# PROPOSAL PROYEK
## INFORMATICS CHAMPIONSHIP x CATALYST HACKATHON 2026
**Tema:** *Digital Solutions for Everyday Problems*

---

### 1. INFORMASI TIM
- **Nama Tim:** kata najmi gini doang sambil tidur bisa
- **Ketua Tim:** Adridinan Najmi Faza (Informatika, Universitas Jenderal Soedirman)
- **Anggota Tim:**
  1. Timotius Willy Narendra (Informatika, Universitas Jenderal Soedirman)
  2. Fardizza Finda Rahman (Informatika, Universitas Jenderal Soedirman)

---

### 2. JUDUL / NAMA PROYEK
**KilasTugas: Smart Actionable Task Breakdown & Micro-Pacing Web Platform**

---

### 3. DESKRIPSI PERMASALAHAN
Mahasiswa sering mengalami penundaan tugas (*procrastination*) dan beban kognitif berlebih (*cognitive overload*). Akar masalah utama di lingkungan akademik sehari-hari mencakup:
1. **Instruksi Tugas Terlalu Luas & Ambigu:** Tugas kuliah kompleks (laporan lab praktikum, makalah riset, proyek coding) sering kali tidak memiliki panduan langkah kerja yang runtut. Mahasiswa bingung memulai dari mana (*task paralysis*).
2. **Keterbatasan Aplikasi To-Do Konvensional:** Aplikasi pencatat to-do konvensional hanya menyimpan judul tugas dan deadline akhir tanpa menyediakan breakdown langkah teknis dan durasi realistis.
3. **Dead-End Scheduling & Panik H-1:** Ketiadaan alokasi target mikro harian menyebabkan akumulasi beban kerja di hari menjelang deadline (*cramming*), berujung pada penurunan mutu akademik dan stres berlebih.
4. **Hambatan Kolaborasi & Reusable Blueprint:** Ketika satu mahasiswa berhasil menyusun alur kerja tugas yang efektif, cara kerja tersebut tidak dapat dibagikan secara instan ke rekan sekelas lain yang mengerjakan tugas serupa.

---

### 4. TARGET USER
1. **Mahasiswa Aktif:** Khususnya mahasiswa teknik/informatika dan sains yang menghadapi beban tugas berbasis praktikum, penulisan makalah, atau proyek teknis berskala besar.
2. **Kelompok Belajar & Praktikan Kampus:** Tim mahasiswa yang membutuhkan standardisasi pembagian beban kerja dan target harian yang terukur.
3. **Pelajar & Akademisi:** Pengguna yang membutuhkan manajemen waktu berbasis micro-tasking untuk mengatasi prokrastinasi.

---

### 5. SOLUSI YANG DIUSULKAN
KilasTugas menghadirkan platform web produktivitas yang mengubah deskripsi tugas kuliah yang panjang/kompleks menjadi daftar sub-tugas harian konkret (*actionable micro-tasks*) secara instan melalui sistem **Tri-Engine Breakdown**:
- **Otomasi Breakdown Cerdas:** Menganalisis instruksi tugas dan memecahnya menjadi langkah kerja berdurasi realistis (25–45 menit) yang dipetakan secara proporsional dari hari pendaftaran hingga sebelum deadline.
- **Visual Micro-Pacing:** Indikator visual real-time yang memantau apakah progres belajar mahasiswa *On Track*, *Behind Schedule*, atau *Overdue* berdasarkan target tanggal sub-tugas harian.
- **Persistent Focus Timer (Pomodoro):** Timer fokus berbasis sinkronisasi timestamp absolut dan Web Audio API untuk eksekusi langkah kerja tanpa distraksi.
- **One-Click Blueprint Cloning:** Kemampuan mengekspor dan membagikan skema langkah tugas kepada mahasiswa lain melalui URL instan `/p/:id` tanpa registrasi akun yang rumit.

![Alur Solusi KilasTugas](./Diagram_KilasTugas-1.%20Alur%20Solusi%20KilasTugas%20(1).jpg)  
*Gambar 1: Alur Kerja dan Mekanisme Solusi KilasTugas*

---

### 6. GAMBARAN FITUR UTAMA
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

### 7. TEKNOLOGI YANG DIRENCANAKAN
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

### 8. DAMPAK / MANFAAT YANG DIHARAPKAN
1. **Penurunan Beban Kognitif Mahasiswa:** Menghilangkan kebingungan langkah awal (*blank page syndrome*) saat memulai tugas kuliah berskala besar.
2. **Pemberantasan Budaya Sistem Kebut Semalam (SKS):** Mendorong distribusi pengerjaan tugas secara bertahap dan teratur setiap hari melalui micro-deadlines.
3. **Efisiensi Waktu & Kolaborasi Akademik:** Memfasilitasi pertukaran standar langkah kerja yang terbukti efektif antar mahasiswa, memangkas waktu perencanaan tugas kelompok.
4. **Aksesibilitas Tanpa Hambatan:** Pengguna dapat langsung memanfaatkan aplikasi tanpa wajib login rumit (*guest-mode session*) dengan latensi responsif di berbagai perangkat (desktop, tablet, mobile).
