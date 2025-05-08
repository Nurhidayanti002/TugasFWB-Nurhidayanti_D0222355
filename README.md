
<p align="center"><strong>KursusQ - Sistem Informasi Kursus</strong></p>

<div align="center">

![logo_unsulbar](public/image.png)

<b>Nurhidayanti</b><br>
<b>D0222355</b><br>
<b>Framework Web Based</b><br>
<b>2025</b>

</div>

---

## 🎯 Role dan Fitur

### 1. Admin 

-   Manajemen data pengguna (tambah/edit/hapus Pengelola & Pengguna )
-   Manajemen jenis kursus
-   Manajemen konten kursus (judul, deskripsi, harga, reting)
-   Verifikasi kursus yang diajukan oleh instruktur


### 2. Pengelola Kursus 

-   Membuat dan mengelola kursus
-   Melihat pendaftaran peserta pada kursus mereka
-   Melihat statistik kursus (jumlah siswa, rating)

### 3. Peserta Kursus

-   Mendaftar dan login ke sistem
-   Menelusuri & mencari kursus
-   Mengelola kategori pekerjaan
-   Mengelola lokasi (kota)
-   Memberi rating dan ulasan terhadap kursus
-   Melihat detail kursus
-   Mengelola profil pribadi

---

##  Struktur Tabel Database

### 1. `pengguna`

| Field          | Tipe Data | Keterangan                             |
| -------------- | --------- | -------------------------------------- |
| id             | INT,PK    | ID pengguna                            |
| nama           | VARCHAR   | Nama pengguna                          |
| email          | VARCHAR   | Email unik pengguna                    |
| password       | VARCHAR   | Password (hashed)                      |
| role           | ENUM      | `peserta_kursus`, `pengelola`, `admin` |
| created_at     | TIMESTAMP | Timestamp pembuatan                    |
| updated_at     | TIMESTAMP | Timestamp pembaruan                    |

### 2. `Kategori`

| Field         | Tipe Data | Keterangan                      |
| ------------- | --------- | ------------------------------- |
| id            | INT,PK    | ID kategori                     |
| Nama_Kategori | VARCHAR   | Nama Kategori                   |
| created_at    | TIMESTAMP | Timestamp pembuatan             |
| updated_at    | TIMESTAMP | Timestamp pembaruan             |

### 3. `kursus`

| Field           | Tipe Data | Keterangan                      |
| --------------- | --------- | ------------------------------- |
| id              | INT,PK    | ID kursus                       |
| Nama_kursus     | Text      | Nama_kursus                     |
| Deskripsi       | VARCHAR   | deskripsi Kursu                 |
| thumbnail       | VARCHAR   | Gambar thumbnail                |
| kategori_id     | INT, FK   | ID kategori                     |
| created_at      | TIMESTAMP | Timestamp pembuatan             |
| updated_at      | TIMESTAMP | Timestamp pembaruan             |

### 4. `review`

| Field      | Tipe Data | Keterangan                |
| ---------- | --------- | ------------------------- |
| id         | INT, PK   | ID Review                 |
| pengguna_id| INT, FK   | ID pengguna               |
| kursus_id  | INT, FK   | ID kursus                 |
| reting     | Int       | Penilaian (1-5)           |
| created_at | TIMESTAMP | Timestamp pembuatan       |
| updated_at | TIMESTAMP | Timestamp pembaruan       |

---

## 🔗 Relasi Antar Tabel

-   `pengguna` ↔ `Kursus` : One-to-Many
-   `Kategori` ↔ `kursus` : One-to-Many
-   `Review` ↔ `Kursus` : One-to-Many
-   `Pengguna` ↔ `Review` : One-to-Many
---
