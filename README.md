# 🌐 Website Pemerintah Kabupaten Madiun 🌐

---

# 📁 Daftar Isi
1. [Persyaratan Sistem](#-persyaratan-sistem)
2. [Instalasi](#-instalasi)
3. [Cara Menjalankan](#-cara-menjalankan)
4. [Import Database](#-import-database)
5. [Kredit](#-kredit)

---

## 💻 Persyaratan Sistem

### Sistem Operasi
- **OS**: Windows 10/11, macOS, atau Linux (Ubuntu/Debian/CentOS)  
- **Docker**: Docker Desktop 4.38.0

### Versi Software
- **PHP**: 8.2
- **Laravel**: 11.31
- **Node.js**: 18.x
- **Nginx**: Alpine latest
- **MySQL**: 8.0
- **PHPMyAdmin**: latest
- **Composer**: latest

### Patch/Extension
- **PHP**: `pdo_mysql`, `mbstring`, `exif`, `pcntl`, `bcmath`, `gd`  
- **Node.js**: `npm` sudah terinstal secara default

### Port
- **Laravel App**: 8000  
- **MySQL**: 3307  
- **PHPMyAdmin**: 8080  

### RAM & CPU
- **RAM**: Minimal 4GB  
- **CPU**: Minimal 2 core  

---

## 📦 Instalasi

1. **Buat File `.env`**  
   Salin file `.env.example` ke `.env` dan sesuaikan konfigurasi database:  
   ```env
   DB_CONNECTION=mysql
   DB_HOST=mysql
   DB_PORT=3306
   DB_DATABASE=pemkab
   DB_USERNAME=kominfoadmin
   DB_PASSWORD=kominfoadmin
   ```

2. **Jalankan Docker Compose**  
   ```bash
   docker-compose up --build
   ```
   **Catatan**: Semua perintah seperti `composer install`, `npm install`, `php artisan key:generate`, dan `php artisan migrate` sudah otomatis dijalankan melalui `docker-entrypoint.sh`.

---

## 🚀 Cara Menjalankan

1. **Start Container**  
   ```bash
   docker-compose up
   ```

2. **Stop Container**  
   ```bash
   docker-compose down
   ```

3. **Restart Container**  
   ```bash
   docker-compose restart
   ```

---

## 📥 Import Database

Untuk mengimpor database, Anda dapat menggunakan salah satu dari dua cara berikut:

### Cara 1: Menggunakan Command Line
1. Masuk ke container MySQL:  
   ```bash
   docker exec -it mysql_db bash
   ```

2. Salin file `database.sql` ke dalam container:  
   ```bash
   docker cp /path/to/database.sql mysql_db:/tmp/database.sql
   ```

3. Import database ke MySQL:  
   ```bash
   mysql -u root -p
   use pemkab;
   source /tmp/database.sql;
   exit
   ```

### Cara 2: Menggunakan PHPMyAdmin
1. Buka PHPMyAdmin di browser:  
   `http://localhost:8080`

2. Login dengan username `kominfoadmin` dan password `kominfoadmin`.

3. Pilih database `pemkab`.

4. Import file `database.sql` secara manual.
   
---

## 🏅 Kredit

Proyek ini dikembangkan oleh:

| Nama                        | Departemen                 | Institusi |
|-----------------------------|---------------------------|-----------|
| Mutiara Nurhaliza           | Teknologi Informasi       | ITS       |
| Etha Felisya Br Purba       | Teknologi Informasi       | ITS       |
| Rehana Putri Salsabilla     | Teknologi Informasi       | ITS       |
| Salsabila Amalia Harjanto   | Teknologi Informasi       | ITS       |

---






<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

You may also try the [Laravel Bootcamp](https://bootcamp.laravel.com), where you will be guided through building a modern Laravel application from scratch.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains thousands of video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

## Laravel Sponsors

We would like to extend our thanks to the following sponsors for funding Laravel development. If you are interested in becoming a sponsor, please visit the [Laravel Partners program](https://partners.laravel.com).

### Premium Partners

- **[Vehikl](https://vehikl.com/)**
- **[Tighten Co.](https://tighten.co)**
- **[WebReinvent](https://webreinvent.com/)**
- **[Kirschbaum Development Group](https://kirschbaumdevelopment.com)**
- **[64 Robots](https://64robots.com)**
- **[Curotec](https://www.curotec.com/services/technologies/laravel/)**
- **[Cyber-Duck](https://cyber-duck.co.uk)**
- **[DevSquad](https://devsquad.com/hire-laravel-developers)**
- **[Jump24](https://jump24.co.uk)**
- **[Redberry](https://redberry.international/laravel/)**
- **[Active Logic](https://activelogic.com)**
- **[byte5](https://byte5.de)**
- **[OP.GG](https://op.gg)**

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
