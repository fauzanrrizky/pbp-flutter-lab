# Tugas 7 Readme

## *Stateless widget* dan *stateful widget*

 - *Stateless widget* : Widget yang tidak punya *state*. Artinya, widgets tidak menyimpan keadaan dari dirinya sendiri. Maka, jika ingin diubah, *stateless widgets* diubah oleh events external dari *parent widget* mereka, dan tidak akan berubah sendiri.
 
 - *Stateful widget* : Widget yang state sendiri dapat berubah-ubah sepanjang waktu. *State* yang disimpan tersebut akan mendeskripsikan bagaimana *widget* tersebut dirender. Karena memiliki *state*, *widgets* ini dapat menerima *event* yang mengubah *state* mereka secara langsung.
 - Perbedaan dari keduanya adalah, *stateful widgets* memiliki *state*, sehingga dapat menerima *events* untuk mengubah *state* dan tampilan di layar, sedangkan *stateless widgets* tidak merubah dirinya sendiri dan dikontrol oleh *parent widgets* jika ingin diubah

## *Widgets* yang dipakai untuk tugas 7

 - text : Menampilkan text GENAP, GANJIL, counter
 - FloatingActionButton : Tombol lingkaran yang mengambang (digunakan untuk tombol increment & decrement)
 - Padding : Layouting
 - Row : Layouting
 - Scaffold : Implementasi basic Material Design visual layout structure
 
## Fungsi dari setState(), variable apa saja yang terdampak fungsi tersebut
setState() digunakan untuk melakukan build ulang dari stateful widgets dan childs nya. Variabel yang terdampak adalah variabel yang terletak didalam fungsi yang sama dengan fungsi yang memanggil setState()


## Perbedaan const dengan final

 - Const : Variabel yang konstan di compile time nya saja, const membuat suatu object frozen dan immutable, const tidak dapat digunakan ke object yang valuenya tidak dapat ditentukan ketika code di compile.
 
 - Final : Nilai yang tidak akan diubah dan tidak dapat diubah, final digunakan untuk menyimpan object yang valuenya tidak dapat ditentukan ketika compile, contohnya menyimpan HTTP Response yang tidak akan diubah.

## Cara mengimplementasikan checklist

 1. ketik `fullter create counter_7` di cmd
 2. Buat variabel `_parity` dan `parityColor` untuk ubah text GANJIL GENAP.
 3.  Ganti parameter  `floatingActionButton`  pada widget  `Scaffold`  dengan  `bottomSheet`. Parameter  `bottomSheet`  digunakan supaya widget button dapat ditaro ke bawah layar.  `bottomSheet`  kita isi dengan widget  `Row`  yang berisi 2  `FloatingActionButton`, button yang menambahkan dan mengurangi counter.
 4. Buat fungsi  `_decrementCounter` untuk implementasi decrement.
 5. Gunakan padding untuk styling
 6. Untuk modifikasi visibility tombol decrement saat counter 0, buat variabel boolean `_minusVisible`


# Tugas 8 Readme

## Perbedaan Navigator.push dan Navigator.pushReplacement

Perbedaan terletak ketika melakukan perpindahan layer

 - Navigator.push : Menambahkan rute lain keatas tumpukan screen (stack)
 - Navigator.pushReplacement : Mengganti layer sebelumnya dengan layer itu sendiri yang ditunjuk oleh page dari Navigator.pushReplacement (tidak menimpa layer sebelumnya)

## Widget yang dipakai di proyek kali ini

 - Drawer : panel sebagai navigator untuk berpindah halaman
 - Form : sebagai container untuk input2
 - Column & row : Styling widgets untuk membentuk kolom dan baris
 - Padding : styling agar lebih rapih
 - TextButton : untuk submit form
 - Card : Menampilkan data budget

## Jenis event yang ada pada flutter

 - onPressed : Trigger ketika pencet sesuatu
 - onTap  : Ketika tap sesuatu
 - onSaved : Trigger ketika form disave
 - onCHanged : Trigger ketika field text form, atau apapun berubah isinya

## Cara kerja navigator mengganti halaman pada aplikasi flutter
Ketika navigator push, maka akan menimpa layer sebelumnya, layer sebelumnya tetap ada di bawah layer yang baru. Kalau pake navigator.pushReplacement, pindah layer yang dituju tanpa menimpa layer sebelumnya.

## Bagaimana cara implementasi checklist

 1. Membuat file drawer yang berisi AppDrawer sebagai navigator untuk berpindah halaman.
 2. Menambahkan children di AppDrawer yang berfungsi untuk berpindah halaman sesuai dengan tombol masing-masing
 3. Membuat file form yntuk menambahkan budget, file form menggunakan TextFormField dan DropdownButton
 4. Membuat file data tambah_budget untuk melakukan menambahkan dan menyimpan data budget
 5. Membuat file data_budget untuk menampilkan data budget yang sudah disimpan lewat tambah_budget.

# Tugas 9 Readme
## Apakah bisa kita melakukan pengambilan data JSON tanpa membuat model terlebih dahulu? Jika iya, apakah hal tersebut lebih baik daripada membuat model sebelum melakukan pengambilan data JSON?
Pengambilan data tanpa menggunakan model tetap bisa dilakukan, karena pengambilan data (melakukan HTTP Request) tidak berhubungan dengan model. Namun, menyimpan data JSON dengan bantuan model dapat lebih mudah diproses.

## Sebutkan widget apa saja yang kamu pakai di proyek kali ini dan jelaskan fungsinya.
-   Text : menampilkan text
-   Column, Row : menata widgets dalam bentuk kolom dan baris
- TextSpan : dapat menggunakan beberapa text pada 1 baris dengan style yang berbeda-beda
-   FutureBuilder : melakukan build dengan data future (harus menunggu http request)
- Container : mengatur lokasi widgets
-   ListView : membuat banyak widget sekaligus dan memastikan jika berlebihan children maka bisa discroll
-   Card : membantu menampilkan data watchlist
-   InkWell : card dapat ditekan dan memberikan ripple animation
-   ElevatedButton : button biasa yang terlihat "diangkat" agar meningkatkan penampilan

## Jelaskan mekanisme pengambilan data dari json hingga dapat ditampilkan pada Flutter.
Flutter memanggil fungsi fetchWatchList() yang ada di file fetch_mywatchlist.dart. fungsi tersebut melakukan HTTP GET Request ke https://pbp-tugas-2-insta-x.herokuapp.com/mywatchlist/json/ untuk mendapatkan data watchlist yang berbentuk JSON.

Setelah itu, fetchWatchList() menggunakan model Watch dan menggunakan data JSON yang diterima untuk meng-construct Watch. Data seluruh Watch yang telah di construct kemudian diterima oleh FutureBuilder. Seluruh Card akan di build dengan format yang tepat oleh FutureBuilder. Seluruh data Watch juga disimpan sehingga digunakan sebagai context saat membuka halaman detail


## Bagaimana Cara Mengimplementasi Checklist

1. Menambahkan tombol navigasi pada drawer untuk ke halaman MyWatchList   

2. Membuat file `mywatchlist.dart` sebagai model untuk watchlist, dengan parameter sesuai.
3. `Membuat fetch_mywatchlist.dart`yang akan menjalankan fungsi fetchWatchList() yang berfungsi melakukan pengambilan data dari endpoint JSON.
4. FutureBuilder akan membuat card sesuai dengan data yang didapat dari fungsi fetchWatchList()
5. Menambahkan tombol untuk kembali ke daftar myWatchList
