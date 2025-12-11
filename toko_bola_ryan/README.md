Muhammad Indi Ryan Pratama
2406432160
PBP F

Tugas 7

1. Jelaskan apa itu widget tree pada Flutter dan bagaimana hubungan parent-child (induk-anak) bekerja antar widget.

Widget tree adalah struktur hierarki yang menggambarkan bagaimana semua widget tersusun dalam aplikasi Flutter. Setiap widget berada dalam posisi tertentu di dalam pohon, dan widget yang membungkus widget lain disebut parent, sedangkan widget yang dibungkus disebut child. Hubungan parent-child ini menentukan bagaimana tampilan dan perilaku UI terbentuk. Misalnya, Scaffold menjadi parent dari AppBar dan Body, dan perubahan pada parent dapat memengaruhi tata letak child di dalamnya.

2. Sebutkan semua widget yang kamu gunakan dalam proyek ini dan jelaskan fungsinya.

Dalam proyek ini digunakan beberapa widget utama seperti MaterialApp (pembungkus utama aplikasi yang menyediakan tema dan navigasi), Scaffold (struktur dasar halaman seperti AppBar dan body), AppBar (menampilkan judul di bagian atas), Column dan Row (mengatur tata letak vertikal dan horizontal), Padding dan SizedBox (mengatur jarak antar elemen), Card (menampilkan informasi dalam kotak dengan bayangan), GridView.count (membuat grid item dalam jumlah kolom tertentu), Icon dan Text (menampilkan ikon dan teks), serta InkWell (memberi efek klik). Masing-masing bekerja sama membentuk tampilan halaman utama secara terstruktur.

3. Apa fungsi dari widget MaterialApp? Jelaskan mengapa widget ini sering digunakan sebagai widget root.

MaterialApp berfungsi sebagai titik awal aplikasi berbasis Material Design di Flutter. Widget ini menyediakan konfigurasi global seperti tema warna, rute navigasi, dan judul aplikasi. Biasanya digunakan sebagai root widget karena semua komponen Material seperti Scaffold, AppBar, atau SnackBar membutuhkan konteks MaterialApp agar dapat berfungsi dengan benar. Tanpa widget ini, aplikasi tidak dapat menggunakan gaya dan perilaku khas Material Design.

4. Jelaskan perbedaan antara StatelessWidget dan StatefulWidget. Kapan kamu memilih salah satunya?

StatelessWidget adalah widget yang tidak memiliki state atau kondisi yang bisa berubah, sehingga tampilannya selalu sama selama aplikasi berjalan — cocok untuk elemen statis seperti teks atau ikon. Sedangkan StatefulWidget memiliki state yang dapat berubah seiring waktu, misalnya ketika pengguna menekan tombol atau ada data baru. Kita memilih StatelessWidget ketika tampilan tidak perlu diperbarui, dan StatefulWidget ketika interaksi atau perubahan data memengaruhi tampilan.

5. Apa itu BuildContext dan mengapa penting di Flutter? Bagaimana penggunaannya di metode build?

BuildContext adalah objek yang merepresentasikan posisi suatu widget di dalam widget tree. Ia penting karena memungkinkan widget mengakses informasi konteks seperti tema, ukuran layar, atau parent widget. Dalam metode build, BuildContext digunakan untuk memanggil fungsi seperti Theme.of(context) atau ScaffoldMessenger.of(context) agar widget dapat menyesuaikan diri dengan lingkungan tempatnya berada. Tanpa BuildContext, widget tidak bisa mengetahui di mana atau bagaimana ia ditampilkan dalam pohon.

6. Jelaskan konsep "hot reload" di Flutter dan bagaimana bedanya dengan "hot restart".

Hot reload adalah fitur Flutter yang memperbarui kode aplikasi secara langsung tanpa kehilangan state, sehingga perubahan UI atau logika kecil bisa langsung terlihat tanpa memulai ulang aplikasi. Sebaliknya, hot restart memuat ulang seluruh aplikasi dari awal dan menghapus state yang sedang berjalan. Hot reload digunakan untuk mempercepat proses pengembangan antarmuka, sedangkan hot restart digunakan jika terjadi perubahan besar pada struktur widget atau variabel global.

Tugas 8

 1. Jelaskan perbedaan antara Navigator.push() dan Navigator.pushReplacement() pada Flutter. Dalam kasus apa sebaiknya masing-masing digunakan pada aplikasi Football Shop kamu?

Navigator.push() menambah halaman baru sehingga pengguna dapat kembali ke halaman sebelumnya, sedangkan Navigator.pushReplacement() mengganti halaman saat ini sehingga tidak dapat kembali; pada Football Shop, push() digunakan saat membuka halaman Create Product, sedangkan pushReplacement() cocok setelah berhasil login atau menyimpan produk agar tidak kembali ke form.

 2. Bagaimana kamu memanfaatkan hierarchy widget seperti Scaffold, AppBar, dan Drawer untuk membangun struktur halaman yang konsisten di seluruh aplikasi?

 Struktur aplikasi dibuat konsisten dengan menjadikan Scaffold sebagai kerangka halaman, AppBar untuk judul dan identitas tiap halaman, serta Drawer sebagai navigasi utama, sehingga seluruh halaman memiliki tata letak dan pengalaman pengguna yang seragam.

 3. Dalam konteks desain antarmuka, apa kelebihan menggunakan layout widget seperti Padding, SingleChildScrollView, dan ListView saat menampilkan elemen-elemen form? Berikan contoh penggunaannya dari aplikasi kamu.

 Penggunaan Padding, SingleChildScrollView, dan ListView membuat tampilan form lebih rapi, tidak menumpuk, serta dapat di-scroll pada layar kecil sehingga pengguna dapat mengisi data dengan nyaman tanpa elemen terpotong.

 4. Bagaimana kamu menyesuaikan warna tema agar aplikasi Football Shop memiliki identitas visual yang konsisten dengan brand toko?

 Warna tema disesuaikan melalui ColorScheme dan warna utama seperti indigo untuk memastikan tombol, AppBar, dan elemen antarmuka lain memiliki identitas visual yang konsisten dan mencerminkan brand Football Shop.

 Tugas 9
 1. Jelaskan mengapa kita perlu membuat model Dart saat mengambil/mengirim data JSON? Apa konsekuensinya jika langsung memetakan Map<String, dynamic> tanpa model (terkait validasi tipe, null-safety, maintainability)? 
 
 Kita perlu membuat model Dart karena model memberikan struktur data yang jelas, tipe yang terjamin, dan dukungan null-safety. Dengan model, kita dapat memvalidasi tipe data sejak compile-time sehingga lebih aman dan mudah dirawat. Jika kita langsung memakai Map<String, dynamic>, maka seluruh data menjadi dynamic, rawan error runtime, sulit melakukan pengecekan null, dan kode menjadi kurang rapi serta tidak scalable saat aplikasi berkembang.

 2. Apa fungsi package http dan CookieRequest dalam tugas ini? Jelaskan perbedaan peran http vs CookieRequest. 
 
 Package http digunakan sebagai alat dasar untuk melakukan request HTTP tanpa state, cocok untuk API stateless seperti REST. Sementara CookieRequest digunakan khusus untuk autentikasi berbasis session Django karena ia menyimpan cookie, menyertakan session secara otomatis pada tiap request, serta menangani CSRF token. Jadi, http bersifat low-level dan stateless, sedangkan CookieRequest adalah wrapper high-level yang menjaga session login pengguna.
 
 3. Jelaskan mengapa instance CookieRequest perlu untuk dibagikan ke semua komponen di aplikasi Flutter. 
 
 Instance CookieRequest harus dibagikan ke seluruh komponen aplikasi Flutter karena session pengguna hanya valid jika cookie tersimpan dalam satu objek yang konsisten. Jika tiap widget memiliki instance berbeda, cookie tidak terbagi dan server tidak mengenali pengguna sebagai login. Dengan menaruhnya di Provider, semua halaman dapat mengakses session yang sama dan state login tetap terjaga.
 
 4. Jelaskan konfigurasi konektivitas yang diperlukan agar Flutter dapat berkomunikasi dengan Django. Mengapa kita perlu menambahkan 10.0.2.2 pada ALLOWED_HOSTS, mengaktifkan CORS dan pengaturan SameSite/cookie, dan menambahkan izin akses internet di Android? Apa yang akan terjadi jika konfigurasi tersebut tidak dilakukan dengan benar? 

 Flutter dapat berkomunikasi dengan Django jika konfigurasi jaringan diatur dengan benar. 10.0.2.2 perlu ditambahkan pada ALLOWED_HOSTS agar Django menerima request dari emulator Android. CORS perlu diaktifkan untuk memperbolehkan permintaan lintas origin, sementara pengaturan SameSite/cookie memungkinkan Django mengirimkan cookie session ke Flutter. Android juga memerlukan izin internet agar aplikasi dapat melakukan HTTP request. Jika konfigurasi tersebut tidak dilakukan, request akan ditolak, cookie tidak terkirim, atau Flutter tidak bisa mengakses server sama sekali.
 
 5. Jelaskan mekanisme pengiriman data mulai dari input hingga dapat ditampilkan pada Flutter. 
 
 
 
 6. Jelaskan mekanisme autentikasi dari login, register, hingga logout. Mulai dari input data akun pada Flutter ke Django hingga selesainya proses autentikasi oleh Django dan tampilnya menu pada Flutter. 
 
 
 7. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step!