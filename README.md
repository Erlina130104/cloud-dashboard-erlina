Cloud Dashboard – Pemantauan IoT Simulasi dengan Docker
Proyek ini merupakan simulasi data IoT (suhu dan kelembaban) yang sepenuhnya dijalankan secara lokal, menggunakan layanan Python berbasis Docker, API Flask, dan dashboard web real-time. Proyek ini berfokus pada pembelajaran cloud dan DevOps.

Fitur Utama
- Simulasi real-time data sensor IoT (suhu & kelembaban)
- Backend REST API menggunakan Flask
- Dashboard frontend menggunakan HTML + Chart.js
- Orkestrasi layanan dengan Docker Compose
- Bisa dijalankan sepenuhnya di laptop (tanpa perangkat keras tambahan)

Struktur Folder Proyek
cloud-dashboard/
- docker-compose.yml
- backend/
  -> app.py
  -> requirements.txt
  -> Dockerfile
- publisher/
  -> publisher.py
  ->  Dockerfile
- frontend/
  -> index.html

Cara Menjalankan Proyek

 1. Clone repositori
bash
git clone <alamat-repo-anda>
cd cloud-dashboard

 2. Build dan jalankan dengan Docker Compose
bash
docker-compose up –build

 3. Akses sistem melalui browser
Komponen	URL
Dashboard Frontend	http://localhost:8080
Endpoint API (JSON)	http://localhost:5000/data

 Cara Kerja Sistem
- publisher.py: Menghasilkan data suhu dan kelembaban acak setiap 3 detik, lalu dikirim ke server Flask.
- app.py: Menerima data, menyimpannya di memori, dan menyajikan melalui endpoint /data.
- index.html: Mengambil data dari API setiap 3 detik dan menampilkannya dalam grafik menggunakan Chart.js.
- docker-compose.yml: Menjalankan ketiga layanan (backend, publisher, frontend) secara bersamaan.
 Kebutuhan Sistem
- Docker Desktop (Windows/Mac/Linux)
- Tidak memerlukan perangkat keras tambahan
 Ide Pengembangan Lanjutan
- Tambahkan database (InfluxDB/PostgreSQL) untuk menyimpan data historis
- Deploy ke cloud (contoh: Railway, Render, DigitalOcean)
- Tambahkan fitur login/autentikasi untuk dashboard
 Lisensi
MIT – bebas digunakan, dimodifikasi, dan dibagikan!

