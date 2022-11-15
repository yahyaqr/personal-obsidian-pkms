---
created: Monday, November 14th 2022 - 06.48
updated: Monday, November 14th 2022 - 06.48
---
## Pengenalan
Kita telah membahas beberapa hal di modul ini, antara lain:
-   JavaScript dibuat dengan tujuan awal agar website menjadi lebih interaktif.
-   JavaScript termasuk ke dalam kategori scripting language, sehingga kode tidak perlu dikompilasi untuk bisa dijalankan. Terdapat interpreter untuk menerjemahkan kode kita agar bisa dimengerti oleh mesin.
-   Terdapat dua lingkungan umum untuk menjalankan JavaScript, yaitu browser dan Node.js
-   JavaScript dikembangkan dengan standar ECMAScript. Update besar terakhir tersaji dalam versi ES6 pada tahun 2015. Sejak saat itu, tiap tahun JavaScript melakukan update bersifat minor.
- https://www.youtube.com/watch?v=Uwvl-X8wiYc

## Pengenalan Fundamentals JavaScript
Pada akhir modul ini, Anda diharapkan dapat:
-   Menuliskan kode JavaScript dan menampilkannya ke konsol
-   Memahami penggunaan komentar pada kode
-   Memahami konsep variabel pada JavaScript
-   Memahami beberapa jenis tipe data pada JavaScript
-   Mengenal operator pada JavaScript dan bagaimana menggunakannya
-   Memahami konsep percabangan pada pemrograman
-   Memahami konsep perulangan pada pemrograman
- https://www.youtube.com/watch?v=X8SbmPNxVL0

## Struktur Data
Pada modul ini kita akan membahas tentang tipe data JavaScript yang dapat menyimpan struktur data yang lebih kompleks. Beberapa jenis struktur data yang akan kita pelajari, antara lain:
-   Object
-   Array
-   Map
-   Set
- https://www.youtube.com/watch?v=etDR8rc_vvs

## Function
Di sini kita akan mempelajari beberapa hal terkait function, seperti:
-   Apa itu function?
-   Tujuan dan alasan kenapa kita menggunakan function.
-   Bagaimana membuat function pada JavaScript.
- https://www.youtube.com/watch?v=AL9ipPNzSOE

## Pengenalan OOP
Pada modul ini kita akan membahas beberapa hal terkait OOP, seperti:
-   Apa itu class?
-   Empat pilar OOP.
-   Penggunaan property & method.
-   Object Composition.
-   Contoh object/class bawaan dari JavaScript.
- https://www.youtube.com/watch?v=Z5I46E3-QMU

## Pengenalan Functional Programming
Di modul kali ini, kita akan belajar banyak mengenai paradigma functional programming. Hingga di akhir modul ini Anda diharapkan dapat:
-   Mengetahui Paradigma Functional Programming.
-   Mengetahui konsep Pure Function, Immutability, dan Higher-Order Function.
-   Menggunakan Reusable Function yang ada pada JavaScript.

Di sini kita akan membahas 4 konsep besar yang ada di FP. Yakni Pure Function, Immutability, Recursive, dan High-Order Function.
1. Pure Function
	- Pure Function merupakan konsep dari pembuatan fungsi yang mengharuskan fungsi untuk **tidak bergantung terhadap nilai yang berada di luar fungsi atau parameternya**. Sehingga mau seperti apa keadaanya, fungsi yang dibuat selalu menghasilkan sesuatu yang sama, terkecuali bila fungsi tersebut diberikan nilai parameter yang berbeda. 
	- Selain dilarang untuk bergantung terhadap nilai luar, pure function juga **dilarang keras untuk mengubah nilai yang berada di luar baik secara sengaja atau tidak sengaja**. Pure function tidak boleh menimbulkan efek samping (_no side effect_) ketika digunakan.
2. Immutability
	- Konsep yang kedua adalah immutability. Immutable berarti sebuah objek tidak boleh diubah setelah objek tersebut dibuat. Kontras dengan mutable yang artinya objek boleh diubah setelah objek tersebut dibuat.
	- Alih-alih mengubah nilai objek secara langsung, terapkan perubahan tersebut pada nilai return dalam objek baru.
3. Rekursif
	- Rekursif merupakan teknik pada sebuah function yang memanggil dirinya sendiri.
4. Higher-Order Function
	- JavaScript memiliki kemampuan First Class Functions, karena itu fungsi pada JavaScript dapat diperlakukan layaknya sebuah data. Kita bisa menyimpan function dalam variabel, memberikan function sebagai parameter pada fungsi lainnya, hingga mengembalikan function di dalam function.
	- Higher-Order Function merupakan fungsi yang dapat menerima fungsi lainnya pada argumen; mengembalikan sebuah fungsi; atau bahkan keduanya.

## NPM
Pada modul ini kita akan belajar mengenai beberapa hal berikut:
-   Menambahkan package ke dalam project JavaScript.
-   Menggunakan package untuk membantu pengembangan aplikasi.
-   Menghapus package yang sudah tidak digunakan.

```js
function findMax(a, b, c) {
    if (a > b && b > c) {
        return a;
    } else if (b > a && a > c) {
        return b;
    } else {
        return c;
    }
}

findMax(1, 2, 3);
findMax(5, 1, 2);
findMax(102, 404, 48);
findMax(-1, 0, -1);
findMax(2, 2, 2);
```

```js
const name = 'Dicoding';
const language = 'JavaScript';

console.log(`Hello $name. Welcome to $language!`);
```