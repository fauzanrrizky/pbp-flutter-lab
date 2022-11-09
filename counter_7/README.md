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
