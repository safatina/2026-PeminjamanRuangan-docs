## cara run docker
1. Prasyarat
    Pastikan sudah terinstall:
    - Docker Desktop
    - Docker Compose (sudah termasuk di Docker Desktop)
    - WSL 2 (untuk Windows)

Cek instalasi:
    docker --version
    docker compose version

2. Struktur Folder

Pastikan struktur project sebagai berikut:
PDBL-PeminjamanRuangan/
├── 2026-PeminjamanRuangan-backend
├── 2026-PeminjamanRuangan-frontend
└── 2026-PeminjamanRuangan-infrastructure
    └── docker
        ├── docker-compose.yml
        ├── backend.Dockerfile
        └── frontend.Dockerfile

3. Menjalankan Aplikasi
    Masuk ke folder docker: cd 2026-PeminjamanRuangan-infrastructure/docker
    Jalankan perintah: docker compose up --build
    Tunggu hingga semua container berjalan.

4. Akses Aplikasi
    Jika berhasil, aplikasi dapat diakses melalui:
    - Frontend ->  [http://localhost:5174](http://localhost:5174)
    - Backend (Swagger API) -> [http://localhost:5112/swagger](http://localhost:5112/swagger)
    - Database (SQL Server)
    Host: localhost
    Port: 1433

5. Menghentikan Aplikasi
    Untuk menghentikan container: docker compose down

6. Catatan
- Backend berjalan di dalam container pada port `8080` dan dipetakan ke `5112`
- Frontend disajikan menggunakan Nginx
- Database menggunakan SQL Server 2022
