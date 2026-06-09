# edu-tb-mvvm
EduTB is a Flutter-based application for tuberculosis (TB) education and early detection. This project implements the MVVM (Model-View-ViewModel) architecture pattern to improve code maintainability, scalability, and separation of concerns. Features include authentication, TB education, consultation, medical history, health facility location.
# EduTB — Aplikasi Edukasi & Deteksi Dini Tuberkulosis

> **COTD with Flutter — Pertemuan 12 | Tahap 3: Source Code Refactoring (MVVM)**
> Mata Kuliah: Teknologi Aplikasi | Semester Genap 2025/2026
> Universitas Pembangunan Nasional "Veteran" Jawa Timur

---

## Informasi

| Nama | NPM |
|------|-----|
| Richechab | ((23082010042)) |


---

## Deskripsi Aplikasi

**EduTB** adalah aplikasi mobile berbasis Flutter yang dirancang untuk membantu masyarakat dalam memperoleh edukasi mengenai penyakit **Tuberkulosis (TB)** serta melakukan **deteksi dini** gejala TB secara mandiri. Aplikasi ini ditujukan sebagai media informasi kesehatan yang mudah diakses, sehingga pengguna dapat memahami gejala, pencegahan, dan penanganan TB dengan lebih baik.

Pada tahap ini, proyek telah direfaktor menggunakan **pola arsitektur MVVM (Model-View-ViewModel)** untuk meningkatkan keterbacaan kode, skalabilitas, serta pemisahan logika bisnis dari tampilan antarmuka.

---

## Fitur Utama

| No | Fitur | Deskripsi |
|----|-------|-----------|
| 1 | **Autentikasi** | Registrasi dan login pengguna menggunakan Firebase Authentication |
| 2 | **Edukasi TB** | Konten informatif seputar penyakit TB: pengertian, gejala, pencegahan, dan pengobatan |
| 3 | **Konsultasi** | Fitur tanya jawab/konsultasi seputar kesehatan TB dengan tenaga medis atau chatbot |
| 4 | **Riwayat Kesehatan** | Pencatatan dan riwayat hasil pemeriksaan atau konsultasi pengguna |
| 5 | **Lokasi Fasilitas Kesehatan** | Peta lokasi puskesmas dan rumah sakit terdekat yang menangani TB |

---

## Arsitektur: MVVM (Model-View-ViewModel)

Proyek ini mengimplementasikan pola **MVVM** dengan struktur folder sebagai berikut:

```
lib/
├── model/           # Data layer: entitas, repository, API/service
│   ├── user_model.dart
│   ├── article_model.dart
│   ├── consultation_model.dart
│   └── health_record_model.dart
│
├── view/            # UI layer: widget & halaman Flutter
│   ├── auth/
│   │   ├── login_view.dart
│   │   └── register_view.dart
│   ├── home/
│   │   └── home_view.dart
│   ├── education/
│   │   └── education_view.dart
│   ├── consultation/
│   │   └── consultation_view.dart
│   ├── history/
│   │   └── history_view.dart
│   └── location/
│       └── location_view.dart
│
├── viewmodel/       # Business logic layer: state management & interaksi data
│   ├── auth_viewmodel.dart
│   ├── education_viewmodel.dart
│   ├── consultation_viewmodel.dart
│   ├── history_viewmodel.dart
│   └── location_viewmodel.dart
│
└── main.dart
```

### Penjelasan Layer MVVM

- **Model**: Bertanggung jawab atas definisi struktur data dan komunikasi dengan sumber data (Firebase Firestore, REST API).
- **View**: Menampilkan UI kepada pengguna dan meneruskan aksi pengguna ke ViewModel. View tidak mengandung logika bisnis.
- **ViewModel**: Menjadi jembatan antara Model dan View. Mengelola state menggunakan `Provider` dan memproses logika bisnis sebelum data ditampilkan ke View.

---

## Tech Stack

| Kategori | Teknologi |
|----------|-----------|
| **Framework** | Flutter 3.x (Dart) |
| **State Management** | Provider |
| **Backend / BaaS** | Firebase (Authentication, Firestore, Storage) |
| **Maps & Lokasi** | Google Maps Flutter Plugin |
| **HTTP Client** | `http` / `dio` package |
| **Arsitektur** | MVVM (Model-View-ViewModel) |
| **Version Control** | Git & GitHub |

---

## Cara Menjalankan Proyek

### Prasyarat
- Flutter SDK `>=3.0.0`
- Dart SDK `>=3.0.0`
- Android Studio / VS Code
- Akun Firebase (sudah dikonfigurasi)

### Langkah Instalasi

```bash
# 1. Clone repository
git clone https://github.com/richechab/edu-tb-mvvm.git

# 2. Masuk ke direktori proyek
cd edu-tb-mvvm

# 3. Install dependencies
flutter pub get

# 4. Jalankan aplikasi
flutter run
```

---

## Dependencies Utama

```yaml
dependencies:
  flutter:
    sdk: flutter
  provider: ^6.1.1
  firebase_core: ^2.27.0
  firebase_auth: ^4.17.9
  cloud_firestore: ^4.15.9
  firebase_storage: ^11.6.10
  google_maps_flutter: ^2.5.3
  http: ^1.2.0
  dio: ^5.4.1
  shared_preferences: ^2.2.2
```

---

## Riwayat Pengembangan

| Tahap | Deskripsi | Status |
|-------|-----------|--------|
| Tahap 1 | User Interface (UI) & Model Preparation | ✅ Selesai |
| Tahap 2 | UI Navigation | ✅ Selesai |
| Tahap 3 | Source Code Refactoring (MVVM) | ✅ Selesai |

---

## Lisensi

Proyek ini dibuat untuk keperluan akademik dalam rangka tugas mata kuliah **Teknologi Aplikasi**, Program Studi Informatika, Universitas Pembangunan Nasional "Veteran" Jawa Timur.