# Troubleshooting Docker Peminjaman Ruangan
1. Docker tidak dikenali di PowerShell
    - Error:
    docker : The term 'docker' is not recognized
    - Solusi:
    Pastikan Docker Desktop sudah terinstall
    Restart laptop
    Pastikan Docker Desktop statusnya "Running"

2. Error: no configuration file provided
    - Penyebab:
    Menjalankan docker compose up bukan di folder yang berisi docker-compose.yml
    - Solusi:
    cd 2026-PeminjamanRuangan-infrastructure/docker
    docker compose up

3. Backend tidak bisa diakses
    - Gejala:
    Frontend muncul
    Backend http://localhost:5112/swagger tidak bisa dibuka
    - Penyebab: Backend berjalan di port internal 8080
    - Solusi:
    Pastikan di docker-compose.yml terdapat mapping:
    ports:
    - "5112:8080"

4. Error path / context Dockerfile
    - Error: failed to read dockerfile
    - Penyebab:
    Path context atau dockerfile salah
    - Solusi:
    Pastikan path sesuai struktur folder dan file ada.

6. Database tidak bisa connect
    - Solusi umum:
    pada file yang terdapat docker ketik docker compose up -d
    Tunggu SQL Server container siap (±30 detik)
    Gunakan hostname database sesuai service name (db)
    Gunakan port internal 1433

7. Cara cek container berjalan  : docker ps
