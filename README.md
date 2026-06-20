# EduTB - Aplikasi Edukasi & Deteksi Dini Tuberkulosis

EduTB merupakan aplikasi mobile berbasis Flutter yang dirancang untuk membantu masyarakat memperoleh edukasi mengenai Tuberkulosis (TB) serta melakukan deteksi dini gejala TB secara mandiri. Aplikasi ini menyediakan informasi kesehatan yang mudah diakses, fitur konsultasi, pencatatan riwayat kesehatan, dan pencarian fasilitas kesehatan terdekat.

Proyek ini telah direfaktor menggunakan pola arsitektur MVVM (Model-View-ViewModel) untuk meningkatkan maintainability, scalability, serta pemisahan tanggung jawab antara tampilan dan logika bisnis.

---

## Informasi Mahasiswa

| Nama | NPM |
|------|------|
| Riche Chalimul Habibah | 23082010042 |

---

## Deskripsi Aplikasi

Tuberkulosis (TB) merupakan salah satu penyakit menular yang masih menjadi masalah kesehatan di Indonesia. Kurangnya informasi dan keterlambatan deteksi sering menyebabkan penanganan yang tidak optimal.

EduTB hadir sebagai solusi digital yang membantu pengguna untuk:

- Memahami informasi mengenai Tuberkulosis.
- Mengenali gejala awal TB melalui fitur deteksi dini.
- Menyimpan riwayat kesehatan pengguna.
- Melakukan konsultasi terkait kesehatan TB.
- Menemukan fasilitas kesehatan terdekat yang menangani TB.

---

## Fitur Utama

| No | Fitur | Deskripsi |
|----|--------|------------|
| 1 | Autentikasi | Registrasi dan login pengguna menggunakan Firebase Authentication |
| 2 | Edukasi TB | Informasi mengenai pengertian, gejala, pencegahan, dan pengobatan TB |
| 3 | Deteksi Dini TB | Screening awal berdasarkan gejala yang diinput pengguna |
| 4 | Konsultasi | Fitur konsultasi terkait informasi dan gejala Tuberkulosis |
| 5 | Riwayat Kesehatan | Penyimpanan data hasil konsultasi dan pemeriksaan pengguna |
| 6 | Lokasi Fasilitas Kesehatan | Menampilkan lokasi rumah sakit dan puskesmas terdekat menggunakan Google Maps |

---

## Implementasi Arsitektur MVVM

Proyek ini menggunakan pola arsitektur MVVM (Model-View-ViewModel) untuk memisahkan tampilan, logika bisnis, dan pengelolaan data.

### Struktur Folder

```text
lib/
├── models/
│   ├── user_model.dart
│   ├── article_model.dart
│   ├── consultation_model.dart
│   └── health_record_model.dart
│
├── services/
│   ├── auth_service.dart
│   ├── firestore_service.dart
│   └── location_service.dart
│
├── viewmodels/
│   ├── auth_viewmodel.dart
│   ├── education_viewmodel.dart
│   ├── consultation_viewmodel.dart
│   ├── history_viewmodel.dart
│   └── location_viewmodel.dart
│
├── views/
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
└── main.dart
```

### Diagram MVVM

```text
        View
          │
          ▼
     ViewModel
          │
          ▼
       Model
          │
          ▼
 Firebase / API / Database
```

### Penjelasan Layer

#### Model
Berisi representasi data aplikasi dan komunikasi dengan sumber data seperti Firebase Firestore, REST API, maupun database lokal.

#### View
Berisi seluruh tampilan antarmuka pengguna (UI). View hanya bertugas menampilkan data dan menerima interaksi pengguna.

#### ViewModel
Menghubungkan View dengan Model. ViewModel bertanggung jawab mengelola state aplikasi menggunakan Provider serta memproses logika bisnis.

---

## Hasil Refactoring MVVM

Setelah implementasi MVVM, diperoleh beberapa keuntungan:

- Pemisahan yang jelas antara UI dan business logic.
- Struktur proyek lebih rapi dan mudah dipelihara.
- State management lebih terorganisir menggunakan Provider.
- Memudahkan pengembangan fitur baru.
- Mengurangi duplikasi kode.
- Meningkatkan scalability aplikasi.

### Perbandingan Sebelum dan Sesudah MVVM

| Sebelum MVVM | Sesudah MVVM |
|--------------|--------------|
| UI dan business logic bercampur | UI dan business logic terpisah |
| Sulit melakukan maintenance | Lebih mudah dikembangkan |
| Struktur kode kurang terorganisir | Struktur lebih modular |
| Sulit melakukan testing | Lebih mudah diuji dan dipelihara |

---

## Tech Stack

| Kategori | Teknologi |
|-----------|------------|
| Framework | Flutter 3.x |
| Bahasa Pemrograman | Dart |
| State Management | Provider |
| Backend as a Service | Firebase |
| Authentication | Firebase Authentication |
| Database | Cloud Firestore |
| Storage | Firebase Storage |
| Maps | Google Maps Flutter |
| HTTP Client | Dio / HTTP |
| Arsitektur | MVVM |
| Version Control | Git & GitHub |

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

## Cara Menjalankan Proyek

### Prasyarat

- Flutter SDK >= 3.0.0
- Dart SDK >= 3.0.0
- Android Studio atau VS Code
- Firebase Project yang telah dikonfigurasi

### Instalasi

```bash
# Clone repository
git clone https://github.com/richechab/edu-tb-mvvm.git

# Masuk ke folder project
cd edu-tb-mvvm

# Install dependency
flutter pub get

# Jalankan aplikasi
flutter run
```

---

## Konfigurasi Firebase

1. Buat project baru pada Firebase Console.
2. Tambahkan aplikasi Android atau iOS.
3. Unduh file konfigurasi Firebase:
   - `google-services.json` (Android)
   - `GoogleService-Info.plist` (iOS)
4. Tempatkan file pada direktori yang sesuai.
5. Jalankan konfigurasi FlutterFire:

```bash
flutterfire configure
```

6. Jalankan aplikasi:

```bash
flutter run
```

---

## Tampilan Aplikasi

Simpan screenshot aplikasi pada folder:

```text
screenshots/
├── login.png
├── register.png
├── home.png
├── education.png
├── consultation.png
├── history.png
└── maps.png
```
