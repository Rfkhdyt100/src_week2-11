# books_2d

Nama: RIFKI HIDAYAT
Nim: 2097
Kelas: 2D TRPL

## Praktikum

## soal 3: 
a. Substring
value.body adalah respons dari API yang berisi data dalam format JSON. toString() mengonversi data JSON tersebut menjadi string 
substring(0, 450) mengambil 450 karakter pertama dari string tersebut. 
Ini dilakukan untuk membatasi jumlah data yang ditampilkan di layar, sehingga tidak terlalu panjang dan lebih mudah dibaca.

b. catchError!
catchError adalah metode yang digunakan untuk menangani kesalahan yang mungkin terjadi selama pemanggilan Future.
Jika terjadi kesalahan saat mengambil data dari API, blok catchError akan dieksekusi.
setState(() { result = 'An error occurred'; }) memperbarui state dengan pesan kesalahan, sehingga pengguna tahu bahwa ada masalah saat mengambil data.

## soal 4:
langkah 1: 
Asynchronous Method: Ketiga method ini menggunakan Future untuk menjalankan operasi asynchronous.
Future.delayed: Setiap method menggunakan Future.delayed untuk menunda eksekusi selama 3 detik. Ini mensimulasikan operasi yang memerlukan waktu untuk menyelesaikan, seperti mengambil data dari server.
Return Value: Setelah penundaan, setiap method mengembalikan nilai integer (1, 2, dan 3).

langkah 2:
Inisialisasi Total: Method ini menginisialisasi variabel total dengan nilai 0.

Memanggil Method Asynchronous: Method ini memanggil ketiga method asynchronous (returnOneAsync(), returnTwoAsync(), dan returnThreeAsync()) secara berurutan menggunakan await.

Update State: Setelah semua operasi selesai, method ini memperbarui state dengan nilai total yang telah dikonversi menjadi string menggunakan setState(). Ini akan menyebabkan UI diperbarui untuk menampilkan hasilnya.


## Soal 5:
Completer: Digunakan untuk menyelesaikan Future secara manual, memungkinkan kontrol penuh atas kapan dan bagaimana Future diselesaikan.

getNumber(): Menginisialisasi Completer dan memulai proses asynchronous dengan memanggil calculate().

calculate(): Menunda eksekusi selama 5 detik dan kemudian menyelesaikan Completer dengan nilai 42.


## Soal 6:
Penggunaan Completer:

Pada langkah 2, Completer digunakan untuk menyelesaikan Future secara manual setelah penundaan 5 detik.

Pada langkah 5-6, Completer tetap digunakan, tetapi fokusnya adalah pada bagaimana hasil dari Completer ditangani di dalam onPressed.

Penanganan Kesalahan:

Pada langkah 2, tidak ada penanganan kesalahan eksplisit di dalam method calculate().

Pada langkah 5-6, catchError digunakan untuk menangani kesalahan yang mungkin terjadi selama eksekusi Future dan memberikan umpan balik kepada pengguna.

Pembaruan State:

Pada langkah 2, state diperbarui di dalam method calculate() dengan nilai yang diselesaikan oleh Completer.

Pada langkah 5-6, state diperbarui di dalam then dan catchError di dalam onPressed untuk menampilkan hasil atau pesan kesalahan.

## Soal 7:
capture

## Soal 8:
Objek yang Digunakan:
Langkah 1: Menggunakan FutureGroup untuk mengelola beberapa operasi asynchronous.

Langkah 4: Menggunakan Future.wait untuk mengelola beberapa operasi asynchronous.

Cara Menambahkan Futures:
Langkah 1: Menggunakan method add untuk menambahkan Future ke dalam FutureGroup.

Langkah 4: Menggunakan daftar Future yang diberikan sebagai argumen ke Future.wait.

Penutupan:
Langkah 1: FutureGroup harus ditutup secara eksplisit dengan futureGroup.close().

Langkah 4: Tidak ada langkah eksplisit untuk menutup Future.wait.

Penggunaan:
Langkah 1: FutureGroup lebih fleksibel dan dapat digunakan untuk menambahkan Future secara dinamis sebelum menutup grup.

Langkah 4: Future.wait lebih sederhana dan langsung, cocok untuk kasus di mana semua Future sudah diketahui sebelumnya.