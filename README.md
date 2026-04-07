
# Database Java - Nindia Nur Artika - I.2510256

### 1. Persiapan Database (MySQL)
Pastikan MySQL sudah menyala, lalu jalankan perintah berikut di terminal/query editor:
```sql
CREATE DATABASE karyawan_db;
USE karyawan_db;

CREATE TABLE karyawan (
    nip VARCHAR(20) PRIMARY KEY,
    nm_kar VARCHAR(100) NOT NULL,
    tem_lhr VARCHAR(50),
    tgl_lhr DATE,
    jabatan VARCHAR(50)
);

-- Buat user akses
CREATE USER 'karyawan_user'@'localhost' IDENTIFIED BY 'password123';
GRANT ALL PRIVILEGES ON karyawan_db.* TO 'karyawan_user'@'localhost';
FLUSH PRIVILEGES;
```

### 2. Konfigurasi Aplikasi
Buka file `src/main/java/javatutorial/CConnection.java` dan pastikan pengaturannya sesuai:
* **URL**: `jdbc:mysql://localhost:3306/karyawan_db`
* **User**: `karyawan_user`
* **Password**: `password123`

### 3. Cara Menjalankan
Gunakan terminal di folder proyek (`crud-swing-karyawan`) dan ketik:
```bash
mvn clean compile exec:java
```

---

## Troubleshooting Singkat
* **Database Error**: Pastikan MySQL di XAMPP/Service sudah **Running** sebelum menjalankan aplikasi.
* **Null Connection**: Cek kembali *username* dan *password* di file `CConnection.java`.
* **Build Gagal**: Jalankan `mvn clean` untuk menghapus *cache* lama.


