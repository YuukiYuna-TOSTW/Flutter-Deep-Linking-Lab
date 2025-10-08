# Concept Check

Route Flutter merupakan sebuah proses perpindahan bagian halaman aplikasi yang sedang berjalan dengan menggunakan Navigator dan Route. Navigator merupakan bagian yang bertugas untuk mengatur tumpukan Route yang menjadi halaman dari aplikasi serta Route merupakan objek yang menjadi halaman dari aplikasi. Cara kerja dari Route sendiri sama dengan Stack yang menjadi salah satu cara untuk menyimpan data di dalam sebuah aplikasi. 

Deep Linking merupakan sebuah proses perpindahan bagian aplikasi yang sedang berjalan dengan menggunakan link untuk langsung membuka bagian tertentu yang ada pada aplikasi. Dalam konteks ini kita akan berfokus pada perangkat yang berjalan dengan menggunakan sistem operasi Android. URI memungkinkan untuk mengakses aplikasi dengan menggunakan 
berbagai macam Aplikasi atau Browser yang mendukung link yang diberikan.

Intent Filter merupakan komponen yang ada didalam Android yang memiliki peran yang sangat penting dalam mengelola sebuah tautan (link). Kegunaan dari komponen ini yaitu untuk memberitahukan sistem operasi mengenai Intent yang dapat diterima dan dijalankan oleh Android.

# Techical Understanding

App Links merupakan komponen yang bertugas untuk mengarahkan pengguna pada bagian dari aplikasi berdasarkan aplikasi atau browser yang dimiliki. Komponen ini juga membantu dalam menjaga keamanan pengguna ketika menjalankan tautan (link) yang dituju sehingga tidak dibutuhkan izin untuk mengakses dikarenakan link telah diverifikasi oleh App Links.

Ketika pengguna membuka link lain ketika aplikasi sedang berjalan maka respon dari Android akan langsung mengarahkan aplikasi untuk membuka bagian sesuai dengan link yang sedang dibuka tanpa perlu menjalankan aplikasi dari awal.

# Debugging Insight

Intent Filter di file AndroidManifest.xml. Bagian ini menentukan tautan (deep link) yang dikenali aplikasi. Jika elemen seperti scheme, host, atau pathPrefix tidak sesuai dengan URL yang dikirim, maka aplikasi memang terbuka, tetapi data tautan tidak diteruskan. Setelah itu, periksa kode Flutter yang menangani deep link, seperti fungsi getInitialLink() atau linkStream.listen(), untuk memastikan tautan diproses dan diarahkan ke halaman yang benar. Terakhir, pastikan URL yang digunakan di perintah ADB cocok dengan konfigurasi di manifest. Dengan memeriksa tiga hal tersebut, kamu bisa menemukan penyebab aplikasi tidak berpindah ke halaman detail meskipun berhasil terbuka.

# Summary

Deep Linking berfungsi sebagai jembatan antara sistem Android dan sistem navigasi internal Flutter. Pada sisi Android, intent filter di dalam file AndroidManifest.xml digunakan untuk menentukan tautan (URL atau URI) seperti apa yang dapat dikenali dan dibuka oleh aplikasi, termasuk pengaturan scheme, host, dan path. Ketika pengguna menekan tautan yang cocok, sistem Android akan menjalankan aplikasi dan mengirimkan data tautan tersebut melalui sebuah Intent ke aktivitas utama aplikasi.Dengan cara ini, intent filter Android menentukan kapan dan bagaimana aplikasi dibuka, sedangkan navigasi Flutter menentukan ke mana pengguna diarahkan di dalam aplikasi. Keduanya bekerja bersama untuk menciptakan pengalaman transisi yang mulus dari tautan eksternal menuju halaman tertentu dalam aplikasi.

Salah satu skenario praktis di mana deep linking sangat berguna adalah pada tautan yang dikirim melalui notifikasi. Misalnya, ketika aplikasi e-commerce mengirimkan notifikasi tentang diskon produk tertentu, tautan di dalam notifikasi tersebut dapat berupa deep link seperti https://tokoku.com/produk/123. Saat pengguna mengetuk notifikasi itu, sistem Android akan membuka aplikasi langsung ke halaman detail produk tersebut, bukan hanya ke beranda aplikasi. Dengan cara ini, pengguna dapat langsung melihat informasi yang relevan tanpa harus menavigasi secara manual di dalam aplikasi. Skenario seperti ini meningkatkan kenyamanan pengguna dan efisiensi interaksi, karena deep linking memungkinkan transisi yang cepat dan terarah dari sumber eksternal ke konten spesifik dalam aplikasi.

Ada beberapa masalah dan halangan yang terdapat pada saat membuat dan menjalankan program ini antara lain:
- Adb yang tidak ingin berjalan dikarenakan tidak terbaca oleh sistem komputer.
- Uni_links yang tidak dapat berjalan ketika sedang mencoba menjalankan Flutter.
- Tampilan pada emulator yang tidak sesuai dengan contoh yang diberikan.
- Flutter yang tidak dapat berjalan dengan baik dikarenakan versi yang tidak sesuai.

Jika terdapat masalah tentunya terdapat beberapa tindakan yang dilakukan untuk menyelesaikan permasalahan dan hambatan yang dialami:
- Meminta bantuan kepada orang yang lebih ahli pada bagian yang sedang dipelajari (Ce Inno, Ko Reinaldo, Dewa, Laury).
- Mencari akar permasalah dengan membaca kode error yang ada pada terminal lalu mengecek bagian yang bermasalah.
- Meminta bantuan kepada AI (Chat GPT, Github Copilot) untuk menyelesaikan permasalahan atau error yang didapatkan.
- Menjalankan ulang Android Studio dari awal untuk menjalankan bagian program yang telah diperbaiki.
- Mengganti versi dari Flutter maupun komponen lainnya yang sesuai dengan sistem komputer yang sedang digunakan.
- Memeriksa kembali komponen yang digunakan pada komputer telah berjalan dengan baik seperti adb yang sangat penting di dalam program ini.
- Mengganti Uni_links dengan App_links yang merupakan versi yang lebih baik ketika dijalankan.

