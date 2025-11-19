# 📱 Mobile Programming – Modul 13
**Operasi CRUD (Create, Read, Update, Delete) di Flutter dengan REST API**

## 👤 Identitas
- **Nama**: Ahmad Nashir Ulwan
- **NIM**: 230605110122
- **Kelas**: B

---

## 🎯 Tujuan
- Memahami implementasi operasi CRUD (Create, Read, Update, Delete) pada aplikasi Flutter.
- Menerapkan paket `http` untuk komunikasi antara aplikasi (client) dan server (REST API).
- Menangani respons REST API, termasuk *parsing* data JSON menjadi objek Dart dan penanganan error.
- Membuat antarmuka pengguna (UI) yang interaktif untuk manajemen data menggunakan widget seperti `AlertDialog`, `Card`, dan `SnackBar`.

---

## 📝 Ringkasan Tugas
Langkah-langkah pengerjaan tugas implementasi CRUD Client-Server:

1.  **Setup Proyek & Dependensi**: Membuat proyek baru dan menambahkan paket `http` (untuk request API), `intl` (format tanggal), dan `google_fonts` pada `pubspec.yaml`.
2.  **Model Data**: Membuat Model Class `Post` yang memiliki metode factory `fromJson` untuk mempermudah parsing data dari format JSON ke objek Dart.
3.  **Implementasi Logika CRUD (Asynchronous)**:
    -   **Create (`createPost`)**: Mengirim request `POST` ke API JSONPlaceholder. Jika berhasil (status 201), state aplikasi diperbarui dengan data baru.
    -   **Read**: Menampilkan data yang berhasil diambil atau dibuat ke dalam widget `Card`.
    -   **Update (`updatePost`)**: Mengirim request `PUT` berdasarkan ID. Memperbarui state lokal dengan data yang diedit.
    -   **Delete (`deletePost`)**: Mengirim request `DELETE`. Jika berhasil (status 200), data dihapus dari tampilan (state dikembalikan ke null).
4.  **Membangun UI Interaktif**:
    -   **Dialog Input**: Menggunakan `AlertDialog` yang berisi `TextField` untuk menambah dan mengedit data (Nama & Pekerjaan).
    -   **Tampilan Data**: Menggunakan `Card` untuk menampilkan detail data.
    -   **Menu Aksi**: Menambahkan `PopupMenuButton` pada Card untuk opsi "Update" dan "Delete".
    -   **Feedback**: Menggunakan `SnackBar` untuk memberikan notifikasi sukses atau gagal kepada pengguna.

---

## 📸 Screenshot Hasil
Berikut adalah tampilan aplikasi saat menjalankan operasi CRUD:

**Tampilan Awal Aplikasi**
![Tampilan Awal](screenshot_awal.png)

**Dialog Tambah Post (Create)**
![Dialog Create](screenshot_dialog_create.png)

**Hasil Create Data (Tampilan Card)**
![Hasil Create](screenshot_hasil_create.png)

**Dialog Update Post**
![Dialog Update](screenshot_dialog_update.png)

**Konfirmasi & Notifikasi Delete**
![Konfirmasi Delete](screenshot_delete.png)

*(Catatan: Ganti nama file gambar di atas dengan nama file screenshot yang kamu miliki)*

---

## ✅ Kesimpulan
- **Komunikasi HTTP**: Flutter dapat dengan mudah berinteraksi dengan REST API menggunakan paket `http`. Metode standar seperti `POST`, `PUT`, dan `DELETE` dipetakan langsung ke operasi CRUD.
- **Manajemen State Sederhana**: Penggunaan `setState()` cukup efektif untuk skenario ini. Saat data diterima dari server, `setState()` memicu *rebuild* UI sehingga data baru langsung tampil.
- **Asynchronous Programming**: Penggunaan `async` dan `await` sangat krusial untuk mencegah aplikasi macet (*freeze*) saat menunggu respons server.
- **JSON Parsing**: Data dari API yang berupa JSON perlu dikonversi (*parsing*) menjadi objek Dart agar lebih mudah diakses dan ditampilkan di UI secara terstruktur.
