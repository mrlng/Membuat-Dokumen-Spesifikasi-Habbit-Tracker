# **Dokumentasi Proyek: Simple Habit Tracker App**

Dokumen ini berisi kumpulan spesifikasi dan rencana proyek untuk aplikasi "Simple Habit Tracker" dalam satu file yang terorganisir. Dokumen-dokumen ini mencakup persyaratan produk (PRD), spesifikasi teknis (SRS), desain arsitektur perangkat lunak (SDD), diagram hubungan entitas (ERD), dan jadwal sprint (Timeline).

## **1\. Product Requirements Document (PRD)**

### **1\. Pendahuluan**

#### **1.1. Tujuan Dokumen**

Dokumen ini menguraikan tujuan, fitur, dan persyaratan fungsional/non-fungsional dari aplikasi "Simple Habit Tracker". Tujuannya adalah untuk menjadi panduan utama bagi tim pengembangan, desainer, dan pemangku kepentingan lainnya untuk memastikan pemahaman yang konsisten tentang produk yang akan dibangun.

#### **1.2. Gambaran Umum Produk**

"Simple Habit Tracker" adalah aplikasi mobile berbasis Flutter yang dirancang untuk membantu pengguna membangun dan mempertahankan kebiasaan positif dalam hidup mereka. Aplikasi ini mengutamakan kesederhanaan, kemudahan penggunaan, dan kinerja yang ringan, menyediakan pelacakan kebiasaan yang intuitif dan pengingat yang efektif tanpa fitur yang berlebihan.

#### **1.3. Visi Produk**

Menjadi alat yang paling mudah diakses dan tidak membebani untuk pelacakan kebiasaan, memberdayakan pengguna untuk mencapai tujuan pribadi mereka melalui langkah-langkah kecil dan konsisten setiap hari.

#### **1.4. Target Pengguna**

Individu yang mencari cara sederhana dan efektif untuk:

* Memulai kebiasaan baru (misalnya, minum air, membaca, olahraga ringan).  
* Mempertahankan kebiasaan baik yang sudah ada.  
* Mengurangi kebiasaan buruk.  
* Tidak ingin aplikasi yang kompleks atau fitur yang membanjiri.

### **2\. Fitur Utama (Fungsionalitas)**

#### **2.1. Manajemen Kebiasaan**

**2.1.1. Menambah Kebiasaan Baru:**

* Pengguna dapat menambahkan kebiasaan baru melalui formulir input yang intuitif.  
* **Input:** Nama Kebiasaan (teks), Deskripsi (opsional, teks), Frekuensi (Harian, Hari Tertentu dalam Seminggu \- dengan pilihan hari), Pengingat (Aktif/Nonaktif, Waktu Spesifik, Hari), Ikon (pilihan dari daftar ikon yang disediakan), Warna (pilihan dari palet warna terbatas).  
* **Validasi:** Nama kebiasaan tidak boleh kosong.

**2.1.2. Daftar Kebiasaan:**

* Menampilkan semua kebiasaan yang telah ditambahkan.  
* Setiap item kebiasaan harus menampilkan: Nama Kebiasaan, status penyelesaian untuk hari ini (belum selesai/sudah selesai), dan visualisasi progres singkat (misalnya, *streak count*).  
* **Interaksi:** Ketuk item kebiasaan untuk melihat detail/mengedit.

**2.1.3. Menandai Kebiasaan Selesai:**

* Pengguna dapat menandai kebiasaan sebagai selesai untuk hari ini langsung dari daftar utama (misalnya, tombol centang, *toggle switch*).  
* Status kebiasaan harus diperbarui secara *real-time* di UI.  
* Penandaan ulang kebiasaan yang sudah selesai akan membatalkan penyelesaiannya.

**2.1.4. Mengedit Kebiasaan:**

* Pengguna dapat mengedit semua detail kebiasaan (nama, deskripsi, frekuensi, pengingat, ikon, warna) yang sebelumnya ditambahkan.

**2.1.5. Menghapus Kebiasaan:**

* Pengguna dapat menghapus kebiasaan individual.  
* Konfirmasi penghapusan diperlukan untuk mencegah penghapusan yang tidak disengaja.

#### **2.2. Pengingat (Reminders)**

**2.2.1. Pengaturan Pengingat Spesifik Kebiasaan:**

* Pengguna dapat mengatur waktu spesifik untuk pengingat setiap kebiasaan.  
* Pilihan untuk mengaktifkan/menonaktifkan pengingat untuk kebiasaan individual.

**2.2.2. Notifikasi**

* Aplikasi akan mengirimkan notifikasi *push* lokal pada waktu pengingat yang telah ditentukan.  
* Notifikasi akan mencantumkan nama kebiasaan.

#### **2.3. Pelacakan Progres (Simple Progress Tracking)**

**2.3.1. Hitungan *Streak*:**

* Setiap kebiasaan akan menampilkan hitungan *streak* (berapa hari berturut-turut kebiasaan dilakukan).  
* *Streak* akan direset jika kebiasaan tidak diselesaikan pada hari yang diharapkan.

**2.3.2. Kalender Progres (Sederhana):**

* Tampilan kalender kecil di detail kebiasaan yang menunjukkan hari-hari kebiasaan diselesaikan (ditandai dengan warna/ikon).

### **3\. Desain UI/UX**

* **Kesederhanaan & Minimalis:** Antarmuka pengguna harus bersih, tidak berantakan, dan mudah dinavigasi. Minimalkan jumlah klik atau langkah untuk menyelesaikan tugas inti.  
* **Estetika:** Menggunakan palet warna yang menenangkan dan visual yang menyenangkan.  
* **Navigasi:** Navigasi yang intuitif, kemungkinan menggunakan *bottom navigation bar* atau desain satu layar utama yang dominan.

### **4\. Persyaratan Non-Fungsional**

* **Kinerja:** Aplikasi harus responsif dan cepat, dengan konsumsi baterai dan ukuran aplikasi yang minimal.  
* **Keamanan:** Data pengguna (kebiasaan) harus disimpan dengan aman secara lokal di perangkat.  
* **Skalabilitas:** Arsitektur *clean code* harus diimplementasikan untuk memudahkan penambahan fitur di masa depan.  
* **Pemeliharaan:** Kode harus bersih, terdokumentasi dengan baik, dan mudah dipelihara.  
* **Kompatibilitas:** Mendukung perangkat Android (minimal Android 7.0) dan iOS (minimal iOS 12.0).  
* **NFR-013:** Mendukung *portrait orientation* saja.  
* **NFR-014:** UI harus bersih, minimalis, dan intuitif.  
* **NFR-015:** Pengguna harus menerima *feedback* visual langsung.

## **2\. Software Requirements Specification (SRS)**

### **1\. Pendahuluan**

#### **1.1 Tujuan Dokumen**

Dokumen ini menguraikan persyaratan fungsional dan non-fungsional yang mendetail untuk aplikasi "Simple Habit Tracker".

#### **1.2 Gambaran Umum Produk**

"Simple Habit Tracker" adalah aplikasi mobile Flutter yang dirancang untuk pelacakan kebiasaan yang mudah dan efektif.

#### **1.3 Ruang Lingkup**

Dokumen ini mencakup persyaratan untuk **Minimum Viable Product (MVP)** aplikasi.

#### **1.4 Definisi, Akronim, dan Singkatan**

* **MVP:** Minimum Viable Product  
* **UI:** User Interface  
* **UX:** User Experience  
* **PRD:** Product Requirements Document  
* **SRS:** Software Requirements Specification  
* **API:** Application Programming Interface  
* **DB:** Database

### **2\. Persyaratan Fungsional (Functional Requirements)**

#### **2.1 Manajemen Kebiasaan (Habit Management)**

**FR-001: Menambahkan Kebiasaan Baru**

* **Deskripsi:** Pengguna harus dapat menambahkan kebiasaan baru melalui layar "Tambah Kebiasaan".  
* **Input:** Nama Kebiasaan (teks, maks 50 karakter), Deskripsi (opsional, maks 200 karakter), Frekuensi, Pengingat, Pilihan Ikon, Pilihan Warna.  
* **Validasi:** Nama kebiasaan harus diisi.

**FR-002: Menampilkan Daftar Kebiasaan**

* **Deskripsi:** Aplikasi harus menampilkan semua kebiasaan aktif pengguna di layar utama.  
* **UI:** Setiap kebiasaan ditampilkan sebagai item terpisah dengan: Nama, Ikon, Warna, status penyelesaian hari ini, dan *streak count*.

**FR-003: Menandai Kebiasaan Selesai/Belum Selesai**

* **Deskripsi:** Pengguna dapat menandai kebiasaan sebagai selesai atau membatalkan penyelesaian untuk tanggal saat ini.

**FR-004: Mengedit Detail Kebiasaan**

* **Deskripsi:** Pengguna dapat mengubah detail kebiasaan yang ada.

**FR-005: Menghapus Kebiasaan**

* **Deskripsi:** Pengguna harus dapat menghapus kebiasaan secara permanen.

#### **2.2 Sistem Pengingat (Reminder System)**

**FR-006: Mengatur Pengingat Individual**

* **Deskripsi:** Pengguna harus dapat mengatur waktu pengingat dan mengaktifkan/menonaktifkan pengingat untuk setiap kebiasaan.

**FR-007: Mengirimkan Notifikasi Pengingat**

* **Deskripsi:** Aplikasi harus mengirimkan notifikasi *push* lokal pada waktu pengingat yang telah ditentukan.

#### **2.3 Pelacakan Progres (Progress Tracking)**

**FR-008: Menghitung & Menampilkan *Streak***

* **Deskripsi:** Aplikasi harus menghitung dan menampilkan *streak* (jumlah hari berturut-turut kebiasaan diselesaikan).

**FR-009: Menampilkan Kalender Progres Sederhana**

* **Deskripsi:** Di layar detail kebiasaan, aplikasi harus menampilkan kalender kecil yang mengindikasikan hari-hari kebiasaan diselesaikan.

### **3\. Persyaratan Non-Fungsional (Non-Functional Requirements)**

* **NFR-001:** Waktu muat layar utama tidak lebih dari 1 detik.  
* **NFR-002:** Operasi penambahan/pengeditan/penghapusan harus selesai dalam waktu kurang dari 500ms.  
* **NFR-003:** Pengiriman notifikasi pengingat harus tepat waktu.  
* **NFR-004:** Konsumsi memori minimal.  
* **NFR-005:** Data pengguna disimpan secara lokal.  
* **NFR-006:** Tidak ada data sensitif yang disimpan.  
* **NFR-007:** Aplikasi tersedia di Google Play Store dan Apple App Store.  
* **NFR-008:** Arsitektur aplikasi harus skalabel.  
* **NFR-009:** Kode sumber harus mengikuti pedoman *clean code*.  
* **NFR-010:** Unit dan *widget tests* harus diimplementasikan.  
* **NFR-011:** Kompatibel dengan Android OS versi 7.0+.  
* **NFR-012:** Kompatibel dengan iOS versi 12.0+.  
* **NFR-013:** Mendukung *portrait orientation* saja.  
* **NFR-014:** UI harus bersih, minimalis, dan intuitif.  
* **NFR-015:** Pengguna harus menerima *feedback* visual langsung.

## **3\. Software Design Document (SDD)**

### **1\. Pendahuluan**

#### **1.1 Tujuan Dokumen**

Dokumen ini menjelaskan desain arsitektur dan komponen-komponen utama dari aplikasi "Simple Habit Tracker".

#### **1.2 Gambaran Umum Produk**

"Simple Habit Tracker" adalah aplikasi mobile Flutter yang ringan dan intuitif untuk melacak dan membangun kebiasaan.

#### **1.3 Lingkup**

Dokumen ini mencakup desain sistem untuk **Minimum Viable Product (MVP)** aplikasi.

### **2\. Desain Arsitektur**

Mengimplementasikan **Clean Architecture** untuk memisahkan masalah (*separation of concerns*).

#### **2.1 Lapisan Arsitektur**

graph TD  
    A\[Presentation Layer\] \--\> B\[Domain Layer\]  
    B \--\> C\[Data Layer\]

* **Presentation Layer:** Bertanggung jawab untuk UI & State Management. Menggunakan Flutter Widgets dan GetX.  
* **Domain Layer:** Berisi aturan bisnis inti, entitas, *use cases*, dan *repository interfaces*. Menggunakan Pure Dart.  
* **Data Layer:** Mengimplementasikan *repository interfaces* dan berinteraksi dengan sumber data eksternal. Menggunakan sqflite.

#### **2.2 Struktur Direktori Proyek**

lib/  
├── main.dart  
├── app/  
├── presentation/  
├── domain/  
├── data/  
└── core/

### **3\. Desain Komponen**

#### **3.1 Database Lokal (sqflite)**

* **Initialization:** Kelas DatabaseHelper bertanggung jawab untuk membuka dan membuat database.  
* **Schema:** Menggunakan tabel Habits dan HabitCompletions.  
* **Constraints:** HabitCompletions.habit\_id sebagai FOREIGN KEY. HabitCompletions memiliki UNIQUE *constraint* pada (habit\_id, completion\_date).

#### **3.2 Data Layer**

* **Models:** HabitModel & HabitCompletionModel untuk mengonversi data ke dan dari database.  
* **Data Source:** HabitLocalDataSource bertanggung jawab untuk semua operasi CRUD langsung ke database.  
* **Repository:** HabitRepositoryImpl mengimplementasikan *repository interface* dari Domain Layer.

#### **3.3 Domain Layer**

* **Entities:** Kelas Dart murni yang merepresentasikan data inti aplikasi.  
* **Repository Interface:** HabitRepository mendefinisikan kontrak untuk operasi data.  
* **Use Cases:** Setiap *use case* merepresentasikan satu interaksi pengguna atau logika bisnis.

#### **3.4 Presentation Layer**

* **Screens:** Setiap layar memiliki file \_screen.dart dan \_controller.dart.  
* **Controllers:** GetX *controller* yang mengelola *state* UI dan memanggil *use cases*.  
* **Widgets:** Komponen UI yang dapat digunakan kembali.  
* **Routing & Bindings:** Menggunakan GetX untuk mengelola navigasi dan *dependency injection*.

### **4\. Penanganan Kesalahan (Error Handling)**

* ***Failure*** **Classes:** Digunakan untuk merepresentasikan jenis kesalahan.  
* **Presentation Layer:** *Controllers* akan menampilkan kesalahan kepada pengguna.

### **5\. Sistem Pengingat (Reminder System)**

* Menggunakan flutter\_local\_notifications dan kelas ReminderHelper.

### **6\. Integrasi Pihak Ketiga**

* **sqflite:** Database lokal.  
* **GetX:** *State Management*, *Dependency Injection*, *Routing*.  
* **flutter\_local\_notifications:** Notifikasi *push* lokal.  
* **intl:** *Formatting* tanggal/waktu.  
* **path\_provider:** Jalur penyimpanan database.

### **7\. Desain UI (Garis Besar)**

* **Home Screen:** Daftar kebiasaan dengan tombol tambah.  
* **Add/Edit Habit Screen:** Formulir untuk menambahkan/mengubah kebiasaan.  
* **Habit Detail Screen:** Menampilkan detail kebiasaan dan riwayat progres.

## **4\. Entity-Relationship Diagram (ERD)**

Berikut adalah diagram hubungan entitas (ERD) untuk skema database aplikasi Simple Habit Tracker.

#### **Entitas Utama**

* **Habits**  
* **HabitCompletions**

#### **Tabel 1: Habits**

* **Kolom:** id (INTEGER, PRIMARY KEY), name (TEXT), description (TEXT), created\_at (INTEGER), is\_active (INTEGER), icon\_name (TEXT), color\_hex (TEXT), reminder\_enabled (INTEGER), reminder\_time\_hour (INTEGER), reminder\_time\_minute (INTEGER), frequency\_type (TEXT), frequency\_days (TEXT).

#### **Tabel 2: HabitCompletions**

* **Kolom:** id (INTEGER, PRIMARY KEY), habit\_id (INTEGER, FOREIGN KEY), completion\_date (INTEGER), completed\_at (INTEGER).  
* **Indeks:** (habit\_id, completion\_date) sebagai gabungan unik untuk mencegah entri ganda per hari.

#### **Hubungan Antar Tabel**

Habits (One) \<-----\> HabitCompletions (Many)  
Setiap kebiasaan di tabel Habits dapat memiliki nol atau banyak entri penyelesaian di tabel HabitCompletions. Kolom habit\_id di HabitCompletions adalah Foreign Key yang merujuk ke id di Habits.

## **5\. Checklist Timeline Sprint MVP**

### **Sprint Durasi: 2 Minggu (10 Hari Kerja)**

### **Fokus Sprint: Implementasi Fitur Inti MVP**

### **FASE 1: Setup & Data Layer (Hari 1-3)**

* **Hari 1:** Project Setup & Arsitektur Dasar.  
* **Hari 2:** Database Initialization & HabitCompletion (Schema dan Data Source).  
* **Hari 3:** Habit Entity & Data Source.

### **FASE 2: Domain & Repository Layer (Hari 4-6)**

* **Hari 4:** Habit Repository & Use Cases (Create & Read).  
* **Hari 5:** Use Cases (Update, Delete, Mark Complete).  
* **Hari 6:** Reminder System Integration (Domain).

### **FASE 3: Presentation Layer & Integrasi (Hari 7-10)**

* **Hari 7:** HomeScreen & AddEditHabitScreen (Basic UI & GetX Controller).  
* **Hari 8:** Fitur Utama UI & Reminder Implementation.  
* **Hari 9:** HabitDetailScreen & Progres Sederhana.  
* **Hari 10:** Bug Fixing, Testing, & Persiapan Demo.

### **Catatan Tambahan**

* ***Pair Programming***  
* ***Version Control***  
* ***Daily Stand-up***  
* ***Buffer Time***  
* ***Minimum Viable***