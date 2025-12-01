Nama : Audi Makrufianto Afetama
NIM : H1D023037
Shift : C

--PENJELASAN KODE--

http: Digunakan untuk menangani permintaan HTTP (GET, POST, PUT, DELETE) agar aplikasi dapat berkomunikasi dengan REST API Server.
shared_preferences: Digunakan untuk menyimpan data sederhana secara lokal di perangkat, seperti Token Autentikasi dan User ID, agar sesi login pengguna tetap tersimpan meskipun aplikasi ditutup.
api.dart: Kelas ini berfungsi sebagai pembungkus (wrapper) untuk fungsi HTTP standar. Kelas ini menangani proses penyisipan Header (seperti Bearer Token) secara otomatis dan menangani Exception (error) jika terjadi kegagalan koneksi atau respon server yang tidak valid .
api_url.dart: Berfungsi sebagai pusat penyimpanan alamat endpoint API. Dengan memisahkan URL ke dalam satu file, proses perubahan alamat IP server menjadi lebih mudah karena hanya perlu diubah di satu tempat .
user_info.dart: Kelas ini mengelola sesi pengguna menggunakan shared_preferences. Terdapat fungsi setToken untuk menyimpan token saat login, getToken untuk mengambil token saat melakukan request, dan logout untuk menghapus data sesi .
Konversi Data: Setiap kelas model (seperti Produk, Login, Registrasi) memiliki metode fromJson. Metode ini bertugas memetakan data mentah dari respon server (JSON) menjadi atribut objek agar mudah diolah di dalam aplikasi.
Model Produk: Menyimpan atribut spesifik seperti kode_produk, nama_produk, dan harga yang digunakan di seluruh halaman manajemen produk .
registrasi_bloc.dart & login_bloc.dart: Mengirim data input pengguna (email/password) ke API melalui helper Api, lalu mengembalikan respon sukses atau gagal ke UI untuk ditindaklanjuti.
produk_bloc.dart: Menangani operasi CRUD (Create, Read, Update, Delete) produk.
Get: Mengambil daftar produk dan mengubahnya menjadi List of Objects.
Add/Update: Mengirim data produk baru atau perubahan data ke server.
Delete: Mengirim permintaan hapus berdasarkan ID produk .
login_page.dart & registrasi_page.dart: Menggunakan widget Form dan TextFormField untuk validasi input. Logika tombol submit memanggil fungsi pada Bloc terkait dan menampilkan Dialog (Pop-up) status sukses atau gagal.
produk_page.dart (List Produk): Menggunakan widget FutureBuilder. Widget ini sangat penting karena memungkinkan aplikasi untuk menampilkan indikator loading (CircularProgressIndicator) saat data sedang diambil dari server, dan otomatis menampilkan daftar data (ListView) setelah data berhasil diterima.
produk_form.dart (Tambah/Ubah): Halaman ini bersifat dinamis. Jika halaman menerima parameter data produk (tidak null), maka form akan berfungsi sebagai "Ubah Data" (Update). Sebaliknya, jika parameter kosong, form berfungsi sebagai "Tambah Data" (Create) .
produk_detail.dart: Menampilkan rincian produk dan menyediakan tombol navigasi ke halaman ubah atau konfirmasi penghapusan data.
success_dialog.dart & warning_dialog.dart: Merupakan widget dialog kustom untuk memberikan umpan balik visual yang konsisten kepada pengguna mengenai status operasi (berhasil atau gagal).

--SS HASIL--
<img width="1917" height="909" alt="Screenshot 2025-12-01 133440" src="https://github.com/user-attachments/assets/0583502a-0e09-4338-ba3c-7c4de850f47a" />
<img width="1919" height="392" alt="Screenshot 2025-12-01 133420" src="https://github.com/user-attachments/assets/5e0edc24-90a1-4ef1-a52a-998f95ceda8e" />
<img width="1919" height="413" alt="Screenshot 2025-12-01 133348" src="https://github.com/user-attachments/assets/f1c0925c-3f29-4bae-a3fe-5426d7f20fd3" />
