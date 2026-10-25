# PRD: DompetKampus — Website Manajemen Keuangan untuk Mahasiswa

**Versi:** 0.1 (Draft) | **Status:** Untuk review | **Tanggal:** 25 Oktober 2026 | **Nama produk:** DompetKampus (nama sementara)

## 1. Ringkasan Eksekutif

DompetKampus adalah aplikasi web (responsive, mobile-first) yang membantu mahasiswa mencatat pemasukan dan pengeluaran, membuat anggaran, mengelola uang saku bulanan, menabung untuk tujuan tertentu, serta belajar literasi keuangan dasar. Fokus utama produk adalah **kesederhanaan, kebiasaan harian, dan edukasi kontekstual**, bukan sekadar pencatatan.

Produk dirancang untuk kondisi keuangan khas mahasiswa: pemasukan tidak tetap (kiriman orang tua, beasiswa, kerja paruh waktu, freelance), pengeluaran dominan untuk makan, kos, transportasi, pulsa/kuota, dan gaya hidup, serta rendahnya pengalaman mengelola uang.

## 2. Latar Belakang dan Masalah

### 2.1 Latar Belakang

- Mayoritas mahasiswa pertama kali mengelola uang sendiri saat merantau atau kuliah, tanpa bekal literasi keuangan yang memadai.
- Indeks literasi keuangan generasi muda masih tertinggal dibanding tingkat inklusi keuangannya; kemudahan e-wallet, paylater, dan pinjaman online meningkatkan risiko perilaku konsumtif dan utang.
- Aplikasi pencatat keuangan yang ada umumnya terlalu kompleks, berbayar, atau tidak sesuai dengan pola uang mahasiswa (misalnya uang kiriman yang harus cukup sampai akhir bulan).

*Catatan: angka statistik literasi/inklusi keuangan (mis. survei OJK) perlu diverifikasi dan dicantumkan dengan sumber terbaru sebelum PRD difinalkan.*

### 2.2 Pernyataan Masalah

1. Mahasiswa kerap kehabisan uang sebelum akhir bulan tanpa tahu penyebabnya.
2. Mencatat pengeluaran terasa merepotan sehingga tidak konsisten.
3. Tidak ada kebiasaan menabung atau dana darurat.
4. Minim pemahaman tentang paylater, bunga, inflasi, investasi dasar, dan penipuan keuangan (pinjol ilegal, investasi bodong).

## 3. Tujuan dan Metrik Keberhasilan

### 3.1 Tujuan Produk

- Membantu mahasiswa memahami ke mana uangnya pergi.
- Membentuk kebiasaan mencatat dan menganggarkan yang konsisten.
- Meningkatkan kebiasaan menabung dan kesiapan dana darurat.
- Meningkatkan pengetahuan literasi keuangan dasar.

### 3.2 Metrik Keberhasilan (6 bulan setelah peluncuran)

| Metrik | Target | Cara Ukur |
| --- | --- | --- |
| Pengguna aktif (kunjungan unik) | 5.000 | Analitik privacy-friendly (mis. Plausible) |
| Aktivasi (mencatat ≥3 transaksi dalam 7 hari pertama) | ≥ 50% | Analitik event |
| Retensi D30 | ≥ 25% | Analitik cohort |
| Pengguna aktif mingguan (WAU) / terdaftar | ≥ 30% | Analitik |
| Pengguna yang membuat anggaran bulanan | ≥ 40% | Analitik |
| Pengguna yang punya ≥1 target tabungan | ≥ 35% | Analitik |
| Skor kepuasan (CSAT) | ≥ 4,0 / 5 | Survei in-app |
| Peningkatan skor kuis literasi (pre vs post) | ≥ +20% | Kuis in-app |

## 4. Target Pengguna

### 4.1 Segmen Utama

Mahasiswa S1/D3/D4 berusia 18–24 tahun di Indonesia, terutama yang tinggal terpisah dari orang tua (anak kos/perantau), memakai smartphone sebagai perangkat utama.

### 4.2 Persona

**Persona 1 — Rani, 19 tahun, mahasiswa baru perantau** Menerima uang saku Rp1.500.000/bulan dari orang tua. Sering kehabisan uang di minggu ketiga. Butuh cara sederhana membagi uang per minggu dan melihat kategori pemborosan.

**Persona 2 — Dimas, 21 tahun, mahasiswa dengan kerja paruh waktu** Pemasukan campuran: uang saku, honor freelance desain, dan beasiswa. Butuh mencatat banyak sumber pemasukan dan memisahkan uang kuliah dari uang pribadi.

**Persona 3 — Sinta, 22 tahun, mahasiswa tingkat akhir** Mau menabung untuk biaya wisuda dan persiapan kerja. Tertarik belajar investasi dasar dan dana darurat, tetapi takut tertipu.

## 5. Ruang Lingkup

### 5.1 Dalam Lingkup (MVP)

- Profil lokal tanpa login (data tersimpan di browser)
- Pencatatan transaksi (pemasukan, pengeluaran, transfer antar dompet)
- Dompet/akun (tunai, rekening bank, e-wallet)
- Kategori transaksi khas mahasiswa
- Anggaran bulanan dan mingguan
- Target tabungan
- Dashboard dan laporan sederhana
- Pengingat dan notifikasi dasar
- Modul edukasi literasi keuangan singkat + kuis
- Ekspor data (CSV), backup/restore JSON, dan resume keuangan oleh AI (Gemini)

### 5.2 Di Luar Lingkup MVP (Backlog)

- Integrasi otomatis ke rekening bank/e-wallet (open banking)
- Fitur patungan/split bill dan catatan utang-piutang antar teman
- Scan struk dengan OCR
- Fitur investasi/transaksi sungguhan
- Aplikasi native iOS/Android (MVP berupa PWA)
- Gamifikasi lanjutan dan papan peringkat sosial
- Konsultasi dengan perencana keuangan

### 5.3 Non-Tujuan

Produk **bukan** penyedia layanan keuangan, tidak menyimpan atau memindahkan dana pengguna, dan tidak memberikan rekomendasi produk investasi tertentu.

## 6. Fitur dan Kebutuhan Fungsional

Prioritas: **P0** = wajib MVP, **P1** = penting, bisa fase berikutnya, **P2** = nice to have.

### 6.1 Profil dan Penyimpanan Lokal (P0)

- FR-1: Tanpa akun dan tanpa server: pengguna langsung memakai aplikasi, profil dan data disimpan lokal di browser (localStorage/IndexedDB).
- FR-2: PIN opsional untuk mengunci aplikasi, serta backup dan restore data lewat file JSON.
- FR-3: Onboarding 3 langkah: sumber pemasukan, pola uang saku (bulanan/mingguan), tujuan utama (hemat, menabung, lunasi utang).
- FR-4: Pengaturan mata uang (default IDR), tema terang/gelap, dan penghapusan seluruh data lokal.

### 6.2 Dompet / Akun (P0)

- FR-5: Pengguna dapat membuat beberapa dompet (Tunai, Bank, E-wallet, Tabungan) dengan saldo awal.
- FR-6: Transfer antar dompet tidak dihitung sebagai pemasukan/pengeluaran.
- FR-7: Total saldo ditampilkan di dashboard.

### 6.3 Pencatatan Transaksi (P0)

- FR-8: Tambah transaksi dalam ≤ 3 ketukan/klik: nominal, kategori, dompet (tanggal default hari ini, catatan opsional).
- FR-9: Edit, hapus, dan filter transaksi (tanggal, kategori, dompet, kata kunci).
- FR-10: Kategori bawaan khas mahasiswa: Makan, Kos/Sewa, Transportasi, Kuota/Pulsa, Fotokopi/Buku/Alat Kuliah, UKT/SPP, Organisasi, Nongkrong/Hiburan, Belanja Online, Kesehatan, Tabungan, Lainnya. Pengguna dapat menambah kategori sendiri.
- FR-11: Transaksi berulang (mis. bayar kos, langganan) — P1.
- FR-12: Pintasan cepat (quick add) untuk transaksi yang sering dilakukan — P1.

### 6.4 Anggaran (P0)

- FR-13: Pengguna menetapkan batas anggaran per kategori per bulan.
- FR-14: Fitur **Jatah Harian/Mingguan**: sistem menghitung sisa uang dibagi sisa hari sehingga mahasiswa tahu batas aman pengeluaran harian.
- FR-15: Template anggaran berdasarkan prinsip sederhana (mis. 50/30/20 yang disesuaikan: kebutuhan/keinginan/tabungan) yang dapat diubah.
- FR-16: Notifikasi saat anggaran mencapai 80% dan 100%.

### 6.5 Target Tabungan (P0)

- FR-17: Buat target (nama, nominal, tenggat), mis. laptop, wisuda, dana darurat.
- FR-18: Sistem menghitung setoran yang disarankan per minggu/bulan.
- FR-19: Progres divisualisasikan dengan bar progres dan estimasi tanggal tercapai.
- FR-20: Template khusus **Dana Darurat** (target awal 1–3 kali pengeluaran bulanan) — P1.

### 6.6 Dashboard dan Laporan (P0)

- FR-21: Ringkasan bulan berjalan: pemasukan, pengeluaran, sisa, dan persentase anggaran terpakai.
- FR-22: Grafik pengeluaran per kategori (donat/bar) dan tren harian/bulanan (garis).
- FR-23: Insight otomatis berbasis aturan, mis. "Pengeluaran Nongkrong naik 35% dibanding bulan lalu" — P1.
- FR-24: Ekspor transaksi ke CSV — P1.

### 6.7 Edukasi Literasi Keuangan (P1, sebagian P0)

- FR-25: Modul pembelajaran singkat (3–5 menit per materi) dengan topik: dasar anggaran, dana darurat, bunga dan inflasi, bahaya pinjol ilegal dan paylater, mengenali investasi bodong, pengantar investasi (reksa dana, SBN, saham) secara netral dan edukatif, pajak dasar dan NPWP bagi pemula kerja.
- FR-26: Kuis singkat di akhir modul dan lencana penyelesaian.
- FR-27: Tip kontekstual: mis. saat pengguna membuat target tabungan, muncul tip tentang dana darurat.
- FR-28: **Kalkulator**: bunga majemuk, simulasi cicilan paylater, dan target tabungan — P1.
- FR-29: Disclaimer jelas bahwa konten bersifat edukasi, bukan nasihat investasi.

### 6.8 Pengingat dan Kebiasaan (P1)

- FR-30: Pengingat harian untuk mencatat (waktu dapat diatur) lewat Notification API browser (saat aplikasi terbuka atau terpasang sebagai PWA).
- FR-31: Streak mencatat harian dan ringkasan mingguan.
- FR-32: Pengingat tagihan/jatuh tempo (kos, UKT, langganan).

### 6.9 Resume Keuangan oleh AI — Gemini (P0)

Pengguna dapat meminta resume otomatis kondisi keuangannya dalam bahasa Indonesia yang santai dan mudah dipahami, dibuat oleh Gemini API.

- FR-33: Section "Resume AI" di halaman Laporan/Dashboard dengan tombol "Buat Resume" dan pilihan periode (minggu ini, bulan ini, bulan lalu).
- FR-34: JavaScript merangkum data lokal menjadi data agregat (total pemasukan, total pengeluaran, sisa saldo, pengeluaran per kategori, status anggaran, progres tabungan), menyusunnya menjadi prompt, lalu mengirimnya langsung dari browser ke Gemini API memakai fetch().
- FR-35: Hasil resume berisi gambaran singkat, 3 temuan utama, dan 2–3 saran praktis dengan nada suportif; ditampilkan dengan loading state, pesan error yang jelas, dan tombol salin.
- FR-36: API key Gemini diisi sendiri oleh pengguna di halaman Pengaturan, disimpan lokal di browser, dapat diganti atau dihapus, dan disertai petunjuk cara mendapatkan key di Google AI Studio.
- FR-37: Hanya data agregat dan nama kategori yang dikirim, bukan catatan teks bebas; pengguna melihat pemberitahuan sebelum data pertama kali dikirim ke Google dan dapat mematikan fitur ini.
- FR-38: Penanganan kuota dan error (mis. kode 429, key tidak valid, tidak ada internet), cooldown tombol agar tidak dipencet berulang, dan disclaimer bahwa resume AI bersifat edukatif, bukan nasihat keuangan profesional.
- FR-39: Nama model Gemini disimpan sebagai konstanta konfigurasi sehingga mudah diganti tanpa mengubah logika aplikasi.

### 6.10 Fitur Lanjutan (Backlog, P2)

- Catatan utang-piutang dan split bill dengan teman
- Mode "Akhir Bulan" (hemat darurat)
- Impor mutasi rekening (CSV/PDF)
- Kolaborasi dengan orang tua (laporan read-only opsional)
- Dukungan multibahasa (Indonesia/Inggris)

## 7. User Flow Utama

### 7.1 Onboarding

Landing page → Pilih profil keuangan (jenis pemasukan, nominal uang saku) → Buat dompet pertama → Buat anggaran awal (template) → Dashboard dengan tur singkat.

### 7.2 Mencatat Transaksi Harian

Buka dashboard → Tombol "+" → Isi nominal → Pilih kategori → Simpan → Dashboard otomatis memperbarui jatah harian dan progres anggaran.

### 7.3 Menetapkan Target Tabungan

Menu Tabungan → Buat target → Isi nama, nominal, tenggat → Sistem menyarankan setoran → Pengguna menyetor (transfer dari dompet ke target) → Progres terupdate.

### 7.4 Meminta Resume AI

Dashboard → Resume AI → Pilih periode → (jika API key belum ada, diarahkan ke Pengaturan untuk mengisinya) → Buat Resume → Loading → Hasil resume tampil dan dapat disalin.

## 8. Kebutuhan Non-Fungsional

| Aspek | Kebutuhan |
| --- | --- |
| Performa | Largest Contentful Paint < 2,5 detik pada jaringan 4G; penambahan transaksi terasa instan (optimistic UI) |
| Responsif | Mobile-first (lebar 360px ke atas), tetap nyaman di desktop |
| Aksesibilitas | Mengacu WCAG 2.1 AA: kontras warna, navigasi keyboard, label form |
| PWA | Dapat dipasang di layar utama, caching dasar, dukungan offline terbatas untuk input transaksi (sinkron saat online) — P1 |
| Ketersediaan | Target uptime ≥ 99,5% |
| Skalabilitas | Mampu melayani 10.000 pengguna aktif tanpa perubahan arsitektur besar |
| Kompatibilitas | Dua versi terbaru Chrome, Safari, Firefox, Edge; Android dan iOS browser |
| Lokalisasi | Bahasa Indonesia, format Rupiah (Rp1.500.000), zona waktu WIB/WITA/WIT |
| Hemat data | Ukuran aset ringan karena banyak pengguna memakai kuota terbatas |

## 9. Keamanan, Privasi, dan Kepatuhan

- Data keuangan bersifat sensitif: seluruh data hanya disimpan di perangkat pengguna (localStorage/IndexedDB) dan tidak dikirim ke server kami. Satu-satunya data yang keluar adalah ringkasan agregat ke Gemini API, atas permintaan pengguna.
- Situs wajib berjalan di HTTPS (hosting statis dengan TLS).
- API key Gemini dimasukkan sendiri oleh pengguna dan disimpan lokal. Key tidak boleh ditulis di kode atau di-commit ke repositori, karena JavaScript di browser dapat dilihat siapa saja. Jika kelak memakai key milik pengembang, gunakan proxy serverless dengan pembatasan kuota.
- Cegah XSS: tampilkan input pengguna dan teks hasil AI memakai textContent (bukan innerHTML tanpa sanitasi) dan terapkan Content Security Policy.
- PIN opsional di-hash dengan Web Crypto API. Ini pengaman ringan, bukan enkripsi penuh.
- Produk tidak meminta kredensial perbankan/e-wallet pengguna.
- Kepatuhan pada UU Pelindungan Data Pribadi (UU PDP No. 27 Tahun 2022): kebijakan privasi yang mudah dibaca, persetujuan eksplisit sebelum data dikirim ke Gemini, dan tombol hapus seluruh data.
- Peringatan kepada pengguna bahwa data bisa hilang jika cache/data browser dihapus, sehingga backup JSON rutin dianjurkan.
- Syarat dan ketentuan menegaskan bahwa konten edukasi dan resume AI bukan nasihat keuangan profesional.

## 10. Rekomendasi Teknologi

*Pendekatan sederhana tanpa framework dan tanpa backend: seluruh aplikasi berjalan di browser.*

| Lapisan | Teknologi | Keterangan |
| --- | --- | --- |
| Struktur | HTML5 semantik | Satu halaman dengan beberapa tampilan (dashboard, transaksi, anggaran, tabungan, belajar, pengaturan) |
| Gaya | CSS3 murni (Flexbox, Grid, CSS variables) | Mobile-first; tema terang/gelap lewat CSS variables |
| Logika | JavaScript vanilla (ES6+ modules) | Tanpa framework dan tanpa build tool |
| Penyimpanan | localStorage dan IndexedDB | Pengaturan di localStorage, transaksi dan data besar di IndexedDB; ekspor/impor JSON |
| Grafik | Chart.js via CDN | Satu-satunya library; alternatif: canvas/SVG manual |
| Resume AI | Gemini API via fetch() | API key milik pengguna, disimpan lokal |
| Offline / PWA | manifest.json + service worker | Prioritas P1 |
| Hosting | GitHub Pages, Netlify, atau Vercel (statis) | HTTPS gratis, tanpa server |
| Versioning | Git + GitHub |  |
| Pengujian | Manual, Lighthouse, uji di beberapa perangkat |  |

**Catatan teknis penting:** tidak ada backend maupun database server, sehingga data hanya ada di browser pengguna dan backup JSON menjadi fitur penting. Simpan nominal uang sebagai bilangan bulat rupiah (bukan floating point) agar tidak terjadi kesalahan pembulatan, dan gunakan soft-delete pada transaksi. Struktur file yang disarankan: index.html, css/style.css, js/app.js, js/storage.js, js/ui.js, js/charts.js, js/ai.js (pemanggilan Gemini), serta manifest.json dan sw.js. Panggilan ke Gemini memakai endpoint generateContent dengan API key dikirim lewat header.

## 11. Model Data (Garis Besar)

- **settings** (localStorage): nama panggilan, tema, mata uang, PIN hash, API key Gemini, versi skema
- **wallets** (id, nama, tipe, saldo\_awal)
- **categories** (id, nama, tipe \[income/expense\], ikon, warna, bawaan/kustom)
- **transactions** (id, wallet\_id, category\_id, tipe, jumlah, tanggal, catatan, recurring\_id, deleted\_at)
- **budgets** (id, category\_id, periode, batas\_nominal)
- **savings\_goals** (id, nama, target\_nominal, tenggat, terkumpul)
- **goal\_contributions** (id, goal\_id, wallet\_id, jumlah, tanggal)
- **recurring\_rules** (id, pola, jumlah, kategori)
- **learning\_progress** (modul selesai, skor kuis)
- **ai\_summaries** (opsional: id, periode, teks resume, dibuat\_pada)

## 12. Desain dan UX

### 12.1 Prinsip Desain

1. **Cepat:** mencatat transaksi tidak lebih dari 5 detik.
2. **Ramah dan tidak menghakimi:** bahasa santai dan suportif, bukan menyalahkan saat pengeluaran berlebih.
3. **Visual jelas:** warna konsisten (hijau = pemasukan/aman, kuning = waspada, merah = melebihi batas).
4. **Edukasi yang terintegrasi:** belajar sambil menggunakan, bukan terpisah.
5. **Mobile-first:** navigasi bawah (bottom nav) dengan tombol aksi utama "+".

### 12.2 Halaman Utama

Landing page, Daftar/Masuk, Onboarding, Dashboard, Transaksi, Anggaran, Tabungan, Laporan, Belajar (edukasi), Pengaturan.

### 12.3 Tone of Voice

Santai, memotivasi, dan jelas. Contoh: "Jatah hari ini Rp45.000. Yuk, masih aman!"

## 13. Strategi Peluncuran dan Pertumbuhan

- **Pilot:** 1–2 kampus atau komunitas mahasiswa (BEM, himpunan, komunitas literasi keuangan) dengan 100–200 pengguna beta.
- **Kanal:** media sosial kampus, kolaborasi dengan influencer/kreator literasi keuangan mahasiswa, program kampus (seminar, orientasi mahasiswa baru), dan kemitraan dengan lembaga edukasi keuangan.
- **Model bisnis (usulan):** gratis untuk fitur inti; opsi premium ringan di masa depan (ekspor lanjutan, tema, laporan mendalam) atau kemitraan edukasi (tanpa menjual data pengguna).
- **Loop umpan balik:** survei in-app, tombol feedback, dan wawancara pengguna berkala.

## 14. Rencana Rilis dan Timeline

Estimasi untuk tim kecil (1–2 developer, 1 desainer, 1 PM/konten).

| Fase | Durasi | Hasil |
| --- | --- | --- |
| 0. Discovery | 2 minggu | Riset pengguna (survei + 8–10 wawancara), analisis kompetitor, finalisasi PRD |
| 1. Desain | 3 minggu | Wireframe, prototipe Figma, design system, uji kegunaan awal |
| 2. Pengembangan MVP | 8 minggu | Autentikasi, dompet, transaksi, anggaran, tabungan, dashboard |
| 3. Konten edukasi | Paralel dengan fase 2 | 8–10 modul + kuis |
| 4. QA dan Beta | 3 minggu | Uji fungsional, keamanan, performa, beta tertutup |
| 5. Peluncuran publik | 1 minggu | Rilis v1.0, monitoring |
| 6. Iterasi | Berkelanjutan | Perbaikan berbasis data, fitur P1/P2 |

**Total estimasi menuju MVP: ± 16–17 minggu.**

## 15. Risiko dan Mitigasi

| Risiko | Dampak | Mitigasi |
| --- | --- | --- |
| Pengguna berhenti mencatat setelah beberapa hari | Retensi rendah | Input super cepat, pengingat, streak, insight bermakna |
| Kebocoran data keuangan | Kerugian reputasi dan hukum | Enkripsi, pentest sebelum rilis, kebijakan privasi, minimisasi data |
| Konten edukasi dianggap nasihat investasi | Risiko regulasi dan kepercayaan | Disclaimer, konten netral, review oleh praktisi/akademisi keuangan |
| Kompetitor sudah banyak | Sulit akuisisi | Diferensiasi: fokus mahasiswa, jatah harian, edukasi terintegrasi |
| Kurangnya sumber daya | Jadwal molor | Disiplin ruang lingkup MVP, gunakan layanan BaaS |
| Pengguna tidak percaya aplikasi baru | Adopsi lambat | Transparansi, tidak meminta akses rekening, komunitas kampus |

## 16. Asumsi dan Pertanyaan Terbuka

**Asumsi:** mayoritas pengguna mengakses lewat smartphone; mencatat manual dapat diterima di MVP; pengguna bersedia memberi data dasar untuk personalisasi.

**Pertanyaan terbuka:**

1. Apakah produk akan dikembangkan sebagai proyek komunitas/kampus, startup, atau tugas akhir? (memengaruhi model bisnis dan skala)
2. Apakah perlu kerja sama resmi dengan universitas atau lembaga seperti OJK/bank untuk konten edukasi?
3. Apakah dukungan offline penuh diperlukan sejak MVP?
4. Apakah fitur orang tua (laporan read-only) relevan untuk target pengguna?
5. Apa nama dan identitas merek final?

## 17. Lampiran: Daftar User Story Prioritas (MVP)

1. Sebagai mahasiswa, saya ingin mencatat pengeluaran dengan cepat agar saya tidak lupa ke mana uang saya pergi.
2. Sebagai mahasiswa, saya ingin tahu jatah harian saya agar uang saku cukup sampai akhir bulan.
3. Sebagai mahasiswa, saya ingin membuat anggaran per kategori agar pengeluaran tidak melebihi batas.
4. Sebagai mahasiswa, saya ingin menabung untuk target tertentu dan melihat progresnya agar tetap termotivasi.
5. Sebagai mahasiswa, saya ingin melihat grafik pengeluaran agar paham kategori terbesar.
6. Sebagai mahasiswa, saya ingin belajar konsep keuangan dasar dengan singkat agar tidak terjebak pinjol atau investasi bodong.
7. Sebagai mahasiswa, saya ingin data saya aman dan dapat dihapus kapan saja agar saya merasa tenang.

### Kriteria Penerimaan (Contoh)

- **Pencatatan transaksi:** transaksi tersimpan dan saldo dompet serta progres anggaran diperbarui dalam < 1 detik tampilan; validasi menolak nominal ≤ 0 atau kosong.
- **Jatah harian:** nilai = (total anggaran sisa bulan berjalan) ÷ (jumlah hari tersisa), diperbarui setiap ada transaksi baru.
- **Target tabungan:** setoran yang disarankan dihitung dari (target − terkumpul) ÷ periode tersisa, dan berubah otomatis saat tenggat atau nominal diubah.

---

*Dokumen ini adalah draft awal. Langkah berikutnya: validasi dengan riset pengguna, finalisasi prioritas fitur, lalu penyusunan wireframe dan backlog pengembangan.*
