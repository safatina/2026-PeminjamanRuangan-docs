# API Specification – Peminjaman Ruangan

Base URL: [http://localhost:5112](http://localhost:5112)

1. Peminjaman
    1.1 Get Semua Peminjaman
        - Endpoint
            GET /api/peminjaman
        - Response 200
            [
            {
                "id": 1,
                "namaPeminjam": "Safa",
                "ruangan": "Lab Multimedia",
                "tanggalPinjam": "2026-02-10T08:00:00",
                "tanggalKembali": "2026-02-10T10:00:00",
                "status": "Menunggu persetujuan"
            }
            ]
    1.2 Get Peminjaman by ID
        - Endpoint
            GET /api/peminjaman/{id}
        - Response 200
            {
            "id": 1,
            "namaPeminjam": "Safa",
            "ruangan": "Lab Multimedia",
            "tanggalPinjam": "2026-02-10T08:00:00",
            "tanggalKembali": "2026-02-10T10:00:00",
            "status": "Disetujui"
            }
        - Response 404
        {
        "message": "Data peminjaman tidak ditemukan"
        }
    1.3 Tambah Peminjaman
        - Endpoint
            POST /api/peminjaman
        - Request Body
            {
            "namaPeminjam": "Safa",
            "ruangan": "Lab Jaringan",
            "tanggalPinjam": "2026-02-12T09:00:00",
            "tanggalKembali": "2026-02-12T11:00:00"
            }
        - Response 201
            {
            "message": "Peminjaman berhasil ditambahkan"
            }
    1.4 Update Peminjaman
        - Endpoint
            PUT /api/peminjaman/{id}
        - Request Body
            {
            "namaPeminjam": "Safa",
            "ruangan": "Lab Multimedia",
            "tanggalPinjam": "2026-02-12T10:00:00",
            "tanggalKembali": "2026-02-12T12:00:00",
            "status": "Disetujui"
            }
        - Response 200
            {
            "message": "Peminjaman berhasil diperbarui"
            }
    1.5 Hapus Peminjaman
        - Endpoint
            DELETE /api/peminjaman/{id}
        - Response 200
            {
            "message": "Peminjaman berhasil dihapus"
            }

2. Status Peminjaman
    Nilai yang digunakan pada field status:

    | Status               | Keterangan      |
    | -------------------- | --------------- |
    | Menunggu persetujuan | Pengajuan baru  |
    | Disetujui            | Disetujui admin |
    | Ditolak              | Ditolak admin   |

3. Catatan Teknis
- API menggunakan format JSON
- Backend dibuat menggunakan ASP.NET Core Web API
- Dokumentasi interaktif tersedia di Swagger: http://localhost:5112/swagger