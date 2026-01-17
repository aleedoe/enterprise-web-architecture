# Sistem Manajemen Rumah Sakit Enterprise

> **⚠️ STATUS SAAT INI: KERANGKA ARSITEKTUR**
> Proyek ini saat ini merupakan cetak biru arsitektur yang terpisah. Ini berisi **struktur direktori lengkap** dan **layer arsitektur** untuk aplikasi tingkat produksi, namun **belum ada logika implementasi**. Ini berfungsi sebagai fondasi untuk pengembangan yang dapat disebarluaskan (scalable).

## 📋 Ikhtisar Sistem

Ini adalah Sistem Manajemen Rumah Sakit modern dan scalable yang dirancang dengan prinsip **Clean Architecture** dan **Domain-Driven Design (DDD)**. Tujuannya adalah menyediakan platform yang aman dan sesuai standar HIPAA untuk mengelola operasional rumah sakit, termasuk rekam medis pasien, janji temu, dan penagihan.

Sistem ini dibangun untuk menangani logika bisnis yang kompleks sambil menjaga loose coupling antar layer, memastikan maintainability dan testability jangka panjang.

## 🚀 Fitur Utama (Direncanakan)

### 🏥 Operasional Klinis
- **Manajemen Pasien**: Manajemen siklus hidup lengkap (Pendaftaran, Rawat Inap, Pemulangan).
- **Rekam Medis Elektronik (EMR)**: Akses aman dan tercatat audit ke riwayat pasien, diagnosis, dan perawatan.
- **Dashboard Dokter**: Manajemen jadwal, antrean pasien, dan resep digital.
- **Penjadwalan Janji Temu**: Sistem booking real-time dengan deteksi jadwal bentrok.

### 💼 Administratif & Keuangan
- **Penagihan & Faktur**: Pembuatan faktur otomatis, pemrosesan asuransi, dan pelacakan pembayaran.
- **Role-Based Access Control (RBAC)**: Izin granular untuk Admin, Dokter, Perawat, dan Staf.
- **Pencatatan Audit**: Pelacakan komprehensif atas semua akses data untuk kepatuhan HIPAA.

### 🛡️ Keamanan & Kepatuhan
- **Autentikasi**: Autentikasi multi-faktor (MFA) yang aman.
- **Perlindungan Data**: Enkripsi end-to-end untuk PHI (Protected Health Information) yang sensitif.

## 🛠️ Stack Teknologi

- **Framework**: [Next.js](https://nextjs.org/) (App Router, Server Components)
- **Bahasa**: [TypeScript](https://www.typescriptlang.org/) (Strict Mode)
- **Manajemen State**:
  - **Server State**: [TanStack Query](https://tanstack.com/query/latest) (Caching, Optimistic Updates)
  - **Client State**: [Zustand](https://github.com/pmndrs/zustand) (Global store ringan)
- **Styling**: [Tailwind CSS](https://tailwindcss.com/) + [shadcn/ui](https://ui.shadcn.com/)
- **Validasi**: [Zod](https://zod.dev/) (Validasi skema)
- **Formulir**: [React Hook Form](https://react-hook-form.com/)

## ⚖️ Kelebihan vs. Kekurangan

### ✅ Kelebihan

1.  **Arsitektur Scalable**:
    - Pemisahan **Clean Architecture** (4-layer) memastikan logika bisnis (`domain`) independen dari UI (`presentation`) dan layanan eksternal (`infrastructure`).
    - Fitur baru dapat ditambahkan sebagai "potongan" modular tanpa merusak kode yang sudah ada.

2.  **Maintainability & Testability**:
    - Tidak adanya dependensi di layer Domain membuat unit testing aturan bisnis menjadi sangat mudah.
    - Implementasi infrastruktur (seperti API) dapat dengan mudah diganti atau di-mock.

3.  **Performa Modern**:
    - **Next.js Server Actions** mengurangi JavaScript di sisi klien.
    - **TanStack Query** menangani caching agresif dan deduping request API secara otomatis.

4.  **Keamanan Tipe (Type Safety)**:
    - Cakupan TypeScript end-to-end melindungi dari error runtime.
    - Skema Zod memastikan integritas data di batas-batas sistem.

5.  **Struktur Siap Produksi**:
    - Folder khusus untuk **keamanan**, **logging**, dan **validator** sudah dibuat kerangkanya, mencegah "spaghetti code" di kemudian hari.

### ❌ Kekurangan

1.  **Kompleksitas Awal Tinggi**:
    - Boilerplate cukup signifikan. Membuat fitur "Hello World" sederhana memerlukan sentuhan di 3-4 layer (Entity -> Repository -> Use Case -> UI).
    - Arsitektur ini berlebihan (overkill) untuk aplikasi CRUD kecil dan sederhana.

2.  **Kurva Pembelajaran Terjal**:
    - Developer harus memahami konsep **Dependency Inversion**, **DDD**, dan **Clean Architecture**.
    - Salah menempatkan logika (misalnya, memanggil API di komponen) akan menggagalkan tujuan arsitektur ini.

3.  **Kecepatan Pengembangan**:
    - Pengembangan awal lebih lambat karena struktur yang ketat. Kecepatan akan meningkat seiring waktu saat kompleksitas bertambah, tetapi awalnya lebih lambat daripada aplikasi MVC sederhana.

4.  **Status Saat Ini (Kerangka)**:
    - Seperti dicatat, sistem saat ini belum memiliki implementasi. Pengkodean ekstensif diperlukan untuk menghidupkan fitur-fiturnya.

## 📂 Struktur Proyek

```text
src/
├── app/                  # Next.js App Router (Rute & Tata Letak)
├── modules/              # Organisasi berbasis fitur (Auth, Pasien, dll.)
├── presentation/         # Komponen UI Global & Provider
├── application/          # Use Cases & Manajemen State (Zustand)
├── domain/               # Aturan Bisnis Enterprise (Entities, Value Objects)
├── infrastructure/       # Antarmuka Eksternal (API, Query, Storage)
├── lib/                  # Konfigurasi Bersama
└── configs/              # Konfigurasi build tools
```
