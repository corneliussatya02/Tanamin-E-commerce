# Tanam.in — E-Commerce

**Tanam.in** adalah aplikasi e-commerce berbasis web yang dikembangkan menggunakan **Laravel** dan **PHP**. Aplikasi ini dirancang untuk menyediakan platform penjualan produk secara online dengan struktur aplikasi yang mendukung pengelolaan data, autentikasi pengguna, serta proses transaksi.

Project ini dikembangkan sebagai salah satu project pengembangan sistem untuk menerapkan konsep **web development, database, authentication, payment integration, dan software engineering**.

---

## Project Overview

Tanam.in merupakan sistem e-commerce yang memungkinkan pengguna untuk berinteraksi dengan produk melalui aplikasi web. Sistem dibangun menggunakan framework Laravel sehingga proses pengembangan dapat menggunakan konsep MVC (*Model-View-Controller*), routing, migration, ORM, authentication, serta integrasi layanan eksternal.

Repository menggunakan struktur standar Laravel, antara lain:

* `app/` — logika utama aplikasi
* `bootstrap/` — proses bootstrap framework
* `config/` — konfigurasi aplikasi
* `database/` — migration, factory, dan seeder database
* `public/` — file publik dan entry point aplikasi
* `resources/` — view dan asset frontend
* `routes/` — konfigurasi routing
* `storage/` — file hasil proses aplikasi dan log
* `tests/` — pengujian aplikasi

Struktur tersebut terlihat langsung pada repository Tanam.in.

---

## Tujuan Project

Project ini dikembangkan dengan beberapa tujuan:

1. Membangun aplikasi e-commerce berbasis web.
2. Menerapkan framework Laravel dalam pengembangan aplikasi.
3. Mengimplementasikan pengelolaan data menggunakan database.
4. Menerapkan sistem autentikasi pengguna.
5. Mengintegrasikan layanan pembayaran melalui payment gateway.
6. Menerapkan struktur pengembangan aplikasi berbasis MVC.
7. Meningkatkan pemahaman mengenai pengembangan aplikasi web full-stack.

---

## Teknologi yang Digunakan

| Teknologi             | Penggunaan                   |
| --------------------- | ---------------------------- |
| **PHP**               | Bahasa pemrograman backend   |
| **Laravel 11**        | Framework utama aplikasi     |
| **MySQL**             | Database aplikasi            |
| **Blade**             | Template/view Laravel        |
| **Bootstrap**         | Antarmuka dan styling        |
| **JavaScript**        | Interaksi pada sisi frontend |
| **Laravel Breeze**    | Authentication               |
| **Laravel Socialite** | Integrasi autentikasi sosial |
| **Midtrans**          | Integrasi pembayaran         |
| **Composer**          | Dependency management PHP    |
| **Vite**              | Pengelolaan asset frontend   |

Berdasarkan `composer.json`, project secara resmi mendeklarasikan PHP `^8.2`, Laravel `^11.9`, Laravel Socialite `^5.16`, Laravel Tinker, dan Midtrans PHP SDK `^2.6`.

---

# Fitur Sistem

## 1. User Authentication

Sistem menyediakan mekanisme autentikasi untuk mengelola pengguna.

Pengguna dapat melakukan:

* Registrasi akun
* Login
* Logout
* Pengelolaan sesi pengguna
* Validasi akses pengguna

Project menggunakan **Laravel Breeze** sebagai salah satu dependency untuk mendukung authentication.

---

## 2. Product Management

Sistem e-commerce menyediakan pengelolaan data produk sehingga produk dapat ditampilkan kepada pengguna melalui aplikasi.

Data produk dapat digunakan untuk:

* Menampilkan daftar produk
* Menampilkan informasi produk
* Mengelola data produk
* Menyimpan informasi produk pada database

---

## 3. Shopping Cart

Pengguna dapat memilih produk yang ingin dibeli dan memasukkannya ke dalam keranjang.

Alur umum:

```text
Product
   ↓
Product Detail
   ↓
Add to Cart
   ↓
Shopping Cart
   ↓
Checkout
```

---

## 4. Checkout

Setelah memilih produk, pengguna dapat melanjutkan proses pembelian melalui halaman checkout.

Tahapan checkout secara umum:

```text
Keranjang
    ↓
Checkout
    ↓
Data Pembelian
    ↓
Konfirmasi
    ↓
Pembayaran
```

---

## 5. Payment Integration

Tanam.in menggunakan **Midtrans PHP SDK** untuk mendukung integrasi payment gateway.

Dependency Midtrans tercantum pada `composer.json` sebagai:

```text
midtrans/midtrans-php
```

sehingga aplikasi dapat dikembangkan untuk menangani proses pembayaran melalui layanan Midtrans.

---

## 6. Social Authentication

Project juga memiliki dependency **Laravel Socialite** yang dapat digunakan untuk integrasi autentikasi menggunakan layanan pihak ketiga/social login.

Dependency yang digunakan:

```text
laravel/socialite
```

---

# Arsitektur Aplikasi

Project menggunakan pendekatan **MVC (Model-View-Controller)** yang merupakan pola arsitektur utama Laravel.

```text
                USER
                 │
                 ▼
          ┌─────────────┐
          │    ROUTES   │
          └──────┬──────┘
                 │
                 ▼
          ┌─────────────┐
          │ CONTROLLER  │
          └──────┬──────┘
                 │
        ┌────────┴────────┐
        ▼                 ▼
   ┌─────────┐       ┌─────────┐
   │  MODEL  │       │  VIEW   │
   └────┬────┘       └────┬────┘
        │                 │
        ▼                 ▼
   ┌──────────┐       USER INTERFACE
   │ DATABASE │
   └──────────┘
```

### Model

Digunakan untuk merepresentasikan dan mengelola data aplikasi serta berinteraksi dengan database menggunakan ORM Laravel.

### View

Digunakan untuk menampilkan antarmuka aplikasi kepada pengguna.

### Controller

Berfungsi sebagai penghubung antara request pengguna, proses bisnis, model, dan view.

---

# Struktur Project

Struktur utama repository:

```text
Tanamin-E-commerce/
│
├── app/
│   ├── Http/
│   ├── Models/
│   └── ...
│
├── bootstrap/
│
├── config/
│
├── database/
│   ├── factories/
│   ├── migrations/
│   └── seeders/
│
├── public/
│
├── resources/
│
├── routes/
│
├── storage/
│
├── tests/
│
├── .env.example
├── artisan
├── composer.json
├── composer.lock
├── package.json
├── phpunit.xml
└── vite.config.js
```

Struktur tersebut sesuai dengan file dan direktori yang tersedia pada repository GitHub.

---

# Database

Laravel menyediakan mekanisme **Migration** untuk mendefinisikan struktur database secara terkontrol.

File migration disimpan pada:

```text
database/migrations/
```

Seeder dan factory juga tersedia pada:

```text
database/seeders/
database/factories/
```

Pendekatan ini membantu proses pembuatan dan pengelolaan struktur database selama proses development.

---

# Environment Configuration

Project menggunakan file:

```text
.env
```

untuk menyimpan konfigurasi environment.

Contohnya:

```env
APP_NAME=Tanamin
APP_ENV=local
APP_KEY=
APP_DEBUG=true
APP_URL=http://localhost

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=
DB_USERNAME=root
DB_PASSWORD=
```

Untuk keamanan, file `.env` **tidak seharusnya di-upload ke repository** karena dapat berisi credential dan API key.

Repository menyediakan:

```text
.env.example
```

sebagai template konfigurasi environment.

---

# Installation & Setup

## 1. Clone Repository

```bash
git clone https://github.com/corneliussatya02/Tanamin-E-commerce.git
```

Masuk ke directory project:

```bash
cd Tanamin-E-commerce
```

---

## 2. Install PHP Dependencies

Pastikan **PHP** dan **Composer** sudah terinstall.

Jalankan:

```bash
composer install
```

---

## 3. Install Frontend Dependencies

Pastikan **Node.js dan npm** sudah terinstall.

```bash
npm install
```

---

## 4. Setup Environment

Copy file `.env.example` menjadi `.env`.

Windows:

```bash
copy .env.example .env
```

atau:

```bash
cp .env.example .env
```

Kemudian konfigurasi database pada `.env`.

---

## 5. Generate Application Key

```bash
php artisan key:generate
```

---

## 6. Setup Database

Buat database MySQL, kemudian masukkan konfigurasi pada `.env`.

Contoh:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=tanamin
DB_USERNAME=root
DB_PASSWORD=
```

Kemudian jalankan migration:

```bash
php artisan migrate
```

Jika project menyediakan seeder:

```bash
php artisan db:seed
```

atau:

```bash
php artisan migrate --seed
```

---

## 7. Build Frontend

Untuk menjalankan Vite pada development:

```bash
npm run dev
```

Untuk production build:

```bash
npm run build
```

---

## 8. Menjalankan Laravel

Jalankan:

```bash
php artisan serve
```

Kemudian buka:

```text
http://127.0.0.1:8000
```

---

# Konfigurasi Midtrans

Karena project menggunakan Midtrans PHP SDK, konfigurasi credential pembayaran perlu disiapkan pada `.env`.

Contoh konfigurasi:

```env
MIDTRANS_SERVER_KEY=
MIDTRANS_CLIENT_KEY=
MIDTRANS_IS_PRODUCTION=false
```

**Jangan memasukkan Server Key asli ke GitHub.**

Gunakan environment variable untuk menyimpan credential.

---

# Alur Sistem

Secara umum, alur pengguna pada aplikasi dapat digambarkan sebagai:

```text
                 START
                   │
                   ▼
              Landing Page
                   │
                   ▼
          Browse Product Catalog
                   │
                   ▼
            Product Detail
                   │
                   ▼
              Add to Cart
                   │
                   ▼
             Shopping Cart
                   │
                   ▼
                Checkout
                   │
                   ▼
              Payment
                   │
          ┌────────┴────────┐
          │                 │
       Success            Failed
          │                 │
          ▼                 ▼
   Order Confirmation    Payment Retry
          │
          ▼
         END
```

---

# Testing

Laravel menyediakan struktur testing pada:

```text
tests/
```

Testing dapat dijalankan menggunakan:

```bash
php artisan test
```

atau:

```bash
./vendor/bin/pest
```

Project juga mendeklarasikan Pest dan plugin Laravel untuk kebutuhan development/testing.

---

# Development Tools

Project menggunakan beberapa tools pendukung:

### Composer

Digunakan untuk mengelola dependency PHP dan Laravel.

```bash
composer install
composer update
```

### NPM

Digunakan untuk mengelola dependency frontend.

```bash
npm install
npm run dev
npm run build
```

### Artisan

Laravel Artisan digunakan untuk menjalankan berbagai perintah development.

Contoh:

```bash
php artisan serve
php artisan migrate
php artisan make:model
php artisan make:controller
php artisan route:list
```

---

# Project Role

**Role:** Web Developer / Contributor

Kontribusi pada project mencakup proses pengembangan aplikasi e-commerce berbasis Laravel, termasuk:

* Pengembangan aplikasi web menggunakan Laravel
* Implementasi struktur MVC
* Pengelolaan database
* Pengembangan fitur e-commerce
* Implementasi authentication
* Integrasi payment gateway
* Pengembangan dan pengelolaan UI
* Debugging dan testing aplikasi
* Version control menggunakan Git dan GitHub

> Detail kontribusi individual dapat disesuaikan dengan bagian yang benar-benar kamu kerjakan dalam project bersama.

---

# Skills yang Diterapkan

Project ini menerapkan beberapa kompetensi:

**Programming**

* PHP
* JavaScript
* HTML
* CSS

**Framework**

* Laravel 11
* Bootstrap

**Database**

* MySQL
* Laravel Eloquent ORM
* Database Migration

**Web Development**

* MVC Architecture
* Routing
* Authentication
* CRUD
* Session Management

**Integration**

* Midtrans Payment Gateway
* Laravel Socialite

**Tools**

* Git
* GitHub
* Composer
* NPM
* Vite
* XAMPP / Local Development Environment

---

# Project Outcome

Melalui pengembangan Tanam.in, project ini memberikan pengalaman dalam membangun aplikasi web dari sisi backend hingga frontend dengan menggunakan framework Laravel.

Project juga memberikan pengalaman dalam mengintegrasikan sistem dengan layanan eksternal, mengelola database, menerapkan authentication, serta menggunakan Git dan GitHub sebagai version control.

---

# Repository

**GitHub Repository:**

https://github.com/corneliussatya02/Tanamin-E-commerce

---

## License

Project menggunakan framework Laravel yang memiliki lisensi MIT.

---

## Author

**Cornelius Adyatma Satya Gunawan**

GitHub: `@corneliussatya02`

Project: **Tanam.in — E-Commerce**
