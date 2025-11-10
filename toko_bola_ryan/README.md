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