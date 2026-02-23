# Laporan Proyek Website Portofolio - Pemrograman Berbasis Web

Proyek ini adalah aplikasi website portofolio statis yang dibangun menggunakan **HTML**, **CSS**, **Bootstrap 5**, dan **Vue JS 3**. Website ini dirancang untuk menampilkan identitas diri, keterampilan, pengalaman, dan sertifikat secara responsif dan interaktif.

## Identitas Mahasiswa

* **Nama:** Dharma Pala Candra
* **NIM:** 2409116065
* **Mata Kuliah:** Pemrograman Berbasis Web

## Teknologi yang Digunakan

1. **HTML5**: Sebagai struktur dasar halaman web.
2. **CSS3**: Untuk kustomisasi tampilan (styling) tambahan di luar framework.
3. **Bootstrap 5 (CDN)**: Digunakan untuk sistem tata letak (Grid System), komponen Navbar, Card, Progress Bar, dan utilitas responsif.
4. **Vue JS 3 (CDN)**: Digunakan untuk manajemen data secara reaktif, mempermudah pengisian konten melalui fitur *interpolation* (`{{ }}`) dan *list rendering* (`v-for`).

---

## Penjelasan Fitur dan Kode

### 1. Navbar

<img width="1920" height="1200" alt="Screenshot 2026-02-23 233551" src="https://github.com/user-attachments/assets/43c13840-5f3a-45fb-b0fe-192ef3c27600" />  

Menggunakan komponen `navbar` dari Bootstrap 5 dengan tema gelap (`bg-dark`). Navbar ini bersifat *sticky* (tetap berada di atas saat di-scroll) dan memiliki tautan navigasi yang mengarah ke bagian Home, About Me, dan Certificates. Nama pada brand navbar diambil secara dinamis dari data Vue menggunakan `{{ profile.name }}`.

### 2. Section Home (Hero Section)

Bagian ini adalah perkenalan singkat yang mencakup:

* **Gambar Profil**: Menampilkan foto profil dengan styling lingkaran (`profile-img`) dan bayangan.
* **Interpolasi Data**: Nama dan tagline (contoh: "Sabung Ayam Enthusiast") dipanggil langsung dari objek `profile` di dalam script Vue.
* **Visual**: Tampilan menggunakan *background gradient* melalui kustom CSS pada kelas `.hero-section`.

**Tampilan Home:**

### 3. Section About Me

<img width="1920" height="1200" alt="Screenshot 2026-02-23 233558" src="https://github.com/user-attachments/assets/acaff7cb-c6b7-4d35-97bf-d06f86ffbf6e" />  

Bagian ini terbagi menjadi dua kolom menggunakan Grid System Bootstrap (`col-md-6`):

* **Deskripsi & Pengalaman**: Menampilkan teks biografi dan daftar pengalaman yang di-render secara otomatis menggunakan direktif `v-for` dari array `experience`.
* **Skills (Progress Bar)**: Menampilkan keahlian dengan indikator visual. Lebar progress bar diatur secara dinamis berdasarkan data `level` (dalam persen) menggunakan binding style `:style="{ width: skill.level + '%' }"`.

**Tampilan About Me:**

### 4. Section Certificates

<img width="1920" height="1200" alt="Screenshot 2026-02-23 233603" src="https://github.com/user-attachments/assets/189152ad-deef-4b10-bd64-0e0fe65764d1" />  

Menampilkan daftar sertifikat dalam bentuk **Card Layout** dengan susunan grid.

* Setiap kartu berisi gambar sertifikat, judul, dan penerbit.
* Menggunakan `v-for="cert in certificates"` sehingga penambahan data sertifikat baru hanya perlu dilakukan pada bagian script Vue tanpa mengubah struktur HTML.
* Terdapat efek *hover* kustom pada CSS agar kartu sedikit terangkat saat disentuh kursor (`transform: translateY(-10px)`).

**Tampilan Certificates:**

---

## Struktur Kode Vue JS

Data utama dikelola di dalam fungsi `createApp` pada `index.html`. Berikut adalah cuplikan strukturnya:

```javascript
createApp({
    data() {
        return {
            profile: {
                name: "Dharma01",
                tagline: "...",
                image: "...",
                description: "..."
            },
            skills: [ /* Array objek skill */ ],
            experience: [ /* Array objek pengalaman */ ],
            certificates: [ /* Array objek sertifikat */ ]
        }
    }
}).mount('#app')

```

## Cara Menjalankan Proyek

1. Pastikan semua file (`index.html`, `style.css`, dan folder gambar) berada dalam satu direktori.
2. Buka file `index.html` menggunakan browser pilihan Anda (Chrome/Edge/Firefox).
3. Koneksi internet diperlukan karena proyek ini menggunakan CDN untuk Bootstrap dan Vue JS.
