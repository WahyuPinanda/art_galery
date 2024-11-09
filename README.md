# Art Gallery API

API ini memungkinkan pengguna untuk mengunggah, melihat, memperbarui, dan menghapus gambar karya seni dalam galeri seni. API ini dibangun dengan Express.js, Prisma sebagai ORM untuk PostgreSQL, Multer untuk menangani file gambar, dan ImageKit untuk penyimpanan gambar.

- Node.js
- PostgreSQL
- ImageKit API Key
- Prisma ORM

Jalankan Prisma Migrate untuk membuat skema database:
bash
npx prisma migrate dev --name init

Jalankan server:
bash
npm start

Endpoint API

1. Tambah Gambar
Endpoint: /api/images
Method: POST
Deskripsi: Menambahkan gambar baru ke galeri.
Headers:
Content-Type: multipart/form-data
Body:
title (string) - Judul gambar.
description (string) - Deskripsi gambar.
file (file) - File gambar yang akan diunggah.
Response:
201 Created jika berhasil.
400 Bad Request jika file gambar tidak ada atau ukurannya terlalu besar.
500 Internal Server Error jika ada kesalahan pada server.
2. Dapatkan Semua Gambar
Endpoint: /api/images
Method: GET
Deskripsi: Mendapatkan daftar semua gambar yang aktif.
Response:
200 OK dengan daftar gambar.
3. Dapatkan Gambar Berdasarkan ID
Endpoint: /api/images/:id
Method: GET
Deskripsi: Mendapatkan informasi gambar berdasarkan ID.
Params:
id (integer) - ID dari gambar yang ingin dilihat.
Response:
200 OK dengan data gambar jika ditemukan.
404 Not Found jika gambar tidak ditemukan.
4. Perbarui Gambar
Endpoint: /api/images/:id
Method: PUT
Deskripsi: Memperbarui judul dan deskripsi gambar berdasarkan ID.
Params:
id (integer) - ID dari gambar yang ingin diperbarui.
Body:
title (string) - Judul gambar baru.
description (string) - Deskripsi gambar baru.
Response:
200 OK dengan data gambar yang diperbarui.
500 Internal Server Error jika ada kesalahan pada server.
5. Hapus Gambar
Endpoint: /api/images/:id
Method: DELETE
Deskripsi: Menghapus gambar dari galeri berdasarkan ID.
Params:
id (integer) - ID dari gambar yang ingin dihapus.
Response:
200 OK jika gambar berhasil dihapus.
404 Not Found jika gambar tidak ditemukan.
500 Internal Server Error jika ada kesalahan pada server.
