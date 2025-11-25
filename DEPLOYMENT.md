# Panduan Deployment ke Cloudflare Pages

Halo! Berikut adalah panduan langkah demi langkah untuk mengupload game "Petualangan Anak" ke internet menggunakan **Cloudflare Pages**.

Cloudflare Pages adalah layanan gratis yang sangat cepat dan mudah digunakan untuk menaruh website statis (HTML) seperti game ini.

## Persiapan

Pastikan kamu memiliki akun Cloudflare. Jika belum, daftar gratis di [dash.cloudflare.com/sign-up](https://dash.cloudflare.com/sign-up).

## Metode 1: Upload Langsung (Paling Mudah)

Metode ini cocok jika kamu ingin cara tercepat tanpa menggunakan Git/GitHub.

1.  **Login ke Cloudflare Dashboard**: Buka [dash.cloudflare.com](https://dash.cloudflare.com).
2.  **Pilih Menu Workers & Pages**: Di sidebar sebelah kiri, klik menu **Workers & Pages**.
3.  **Buat Aplikasi Baru**: Klik tombol biru **Create application**.
4.  **Pilih Tab Pages**: Pastikan kamu memilih tab **Pages**, lalu klik **Upload assets**.
5.  **Beri Nama Proyek**: Masukkan nama proyek, misalnya `petualangan-anak`, lalu klik **Create project**.
6.  **Upload File**:
    *   Buka folder proyek kamu di komputer: `/Users/krisna-123/Sites/kids`
    *   Drag & drop (tarik dan lepas) **semua file dan folder** dari folder `kids` tersebut ke area upload di browser.
    *   Pastikan file `index.html`, `tebak_bendera.html`, dan `tebak_peta.html` ikut terupload.
7.  **Deploy**: Setelah semua file terupload, klik tombol **Deploy site**.
8.  **Selesai!**: Cloudflare akan memberikan link website kamu (contoh: `https://petualangan-anak.pages.dev`). Klik link tersebut untuk mencoba game-nya!

## Metode 2: Menggunakan Git (Disarankan untuk Jangka Panjang)

Metode ini lebih baik jika kamu ingin sering mengupdate game-nya di masa depan.

1.  **Push ke GitHub/GitLab**: Pastikan kode kamu sudah ada di repository GitHub atau GitLab.
2.  **Login ke Cloudflare Dashboard**: Buka [dash.cloudflare.com](https://dash.cloudflare.com).
3.  **Pilih Menu Workers & Pages**: Di sidebar sebelah kiri, klik menu **Workers & Pages**.
4.  **Buat Aplikasi Baru**: Klik tombol biru **Create application**.
5.  **Connect to Git**: Klik tombol **Connect to Git**.
6.  **Pilih Repository**: Pilih repository `kids` kamu.
7.  **Konfigurasi Build**:
    *   **Project name**: `petualangan-anak` (atau sesukamu)
    *   **Production branch**: `main` (atau branch utama kamu)
    *   **Framework preset**: `None` (karena ini HTML biasa)
    *   **Build command**: (Kosongkan)
    *   **Build output directory**: (Kosongkan, atau isi `.` jika diminta)
8.  **Save and Deploy**: Klik tombol **Save and Deploy**.

## Metode 3: Menggunakan Wrangler CLI (Untuk Developer)

Jika kamu lebih suka menggunakan terminal (command line), kamu bisa menggunakan `wrangler`. Ini cara yang paling cepat untuk update selanjutnya.

1.  **Install/Update Wrangler**:
    ```bash
    npm install -g wrangler
    ```

2.  **Login ke Cloudflare**:
    ```bash
    wrangler login
    ```
    (Ikuti instruksi di browser untuk login).

3.  **Deploy**:
    Jalankan perintah ini di dalam folder proyek (`/Users/krisna-123/Sites/kids`):
    ```bash
    wrangler pages deploy . --project-name petualangan-anak
    ```

4.  **Selesai**: Wrangler akan mengupload file dan memberikan link website terbaru.

## Tips Tambahan

*   **Caching**: Cloudflare sangat cepat karena menyimpan copy website kamu di seluruh dunia. Jika kamu update file tapi tidak berubah di browser, coba tunggu sebentar atau buka di "Incognito Mode".
*   **Custom Domain**: Jika kamu punya domain sendiri (misal: `gamesanak.com`), kamu bisa menghubungkannya di menu **Custom domains** di dashboard proyek Cloudflare Pages kamu.

Selamat mencoba! 🚀
