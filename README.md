# Reflection 1
Beberapa prinsip clean code dan secure code yang telah saya terapkan adalah sebagai berikut.
1. Nama variable, class, dan methods yang jelas, konsisten, dan tidak ambigu sehingga mudah untuk dipahami.
2. Setiap method atau function hanya memiliki 1 tugas tanpa ada beberapa tugas dikerjakan dalam 1 function atau method.
3. Tidak comment untuk code code yang terlihat membingungkan tetapi ditulis ulang hingga mudah dipahami.
4. Layout dan formatting yang konsisten antara semua file.
5. Penggunaan interface dan abstract method membantu menyembunyikan detail implementasi, mengurangi ketergantungan pada implementasi konkret.
6. Menerapkan arsitektur yang jelas dan konkret, setiap tanggung jawab terpisah (controller, service, repository), masing-masing memiliki tugas tersendiri dan readability serta maintainability.
7. Controller yang tidak mengandung logika kompleks, controller hanya sebagai perantara view dan service untuk menghandle http request.

Beberapa kesalahan yang masih ditemukan dan cara improve.
1. Tidak ada error handling yang jika terjadi error akan menyebabkan aplikasinya tidak berfungsi dengan baik, caranya adalah dengan menambahkan error handling dan juga membuat exception handler sendiri.
2. Masih ada return null pada beberapa method, caranya adalah dengan menambahkan beberapa exception untuk menghandle dan merespons jika returnnya adalah null.
3. Tidak ada input validation yang dapat menyebabkan data tidak valid, caranya adalah menambahkan validation setiap ada input form.


# Reflection 2
1. Setelah menulis unit test, saya merasa untuk project kecil unit test masih belum kerasa relevannya atau kebergunaannya, tetapi untuk project besar saya yakin unit test dapat berguna karena testing 1 1 akan memakan waktu dan tenaga kerja yang besar. Unit test dapat kita buat sebanyaknya hingga code coverage mencapai suatu standar yang kita tentukan misalnya di atas 90%, itu juga bisa memastikan bahwa unit test dapat mencover code kita yang memastikan verifikasi program kita. Code coverage 100% belum tentu berarti program tidak ada error atau bugs, karena unit test dan code dibuat dengan logika dan sepengetahuan kita, sehingga semisal ada bug logika tetapi unit test dan program berjalan lancar, kita tidak akan mengetahuinya.
2. Potensi masalah clean code yang dapat muncul adalah adanya duplikasi kode karena setup seperti inisialisasi baseUrl dan konfigurasi Selenium ditulis berulang di banyak class, yang menyebabkan kode sulit dirawat karena setiap perubahan konfigurasi harus dilakukan di banyak file sekaligus, serta rendahnya reusability karena logic umum seperti navigasi halaman dan pengambilan data dari tabel ditulis berulang. Untuk memperbaiki hal tersebut, dapat dibuat sebuah abstract base class (misalnya BaseFunctionalTest) yang menampung konfigurasi bersama, inisialisasi baseUrl, dan method setup umum, serta menggunakan helper method untuk operasi yang sering digunakan.