---
created: Thursday, December 15th 2022 - 06.00
updated: Thursday, December 15th 2022 - 06.00
---
![[Pasted image 20221215055907.png]]

Pada  beberapa modul sebelumnya kita telah belajar memahami Object Oriented Programming, dari definisi hingga pilar-pilarnya. Kini kita akan masuk ke pembahasan tentang SOLID ya.

### Apa itu SOLID

SOLID merupakan kumpulan dari beberapa principle yang diwujudkan oleh engineer-engineer yang ahli dibidangnya. SOLID membantu kita  mengembangkan sebuah perangkat lunak dengan tingkat kekukuhan yang tinggi. Itu _goal_ kita!

Lantas apakah seseorang yang sudah menguasai dan menggunakan OOP perlu mempelajari SOLID? Tentu saja YA, karena pada dasarnya OOP dan SOLID merupakan 2 (dua) hal yang berbeda. OOP adalah sebuah paradigma untuk menuliskan program yang sudah diadaptasi oleh beberapa bahasa pemrograman, sedangkan SOLID merupakan sebuah principle yang sudah disebutkan sebelumnya. Sampai di sini kita pasti sudah bisa membedakannya ya. 

Berbicara soal paradigma lebih dalam, paradigma sendiri bukanlah sebuah principle yang mengajarkan tentang bagaimana sebuah tanggung jawab suatu entitas yang berada di dalam sebuah perangkat lunak. Saat kita sudah berhasil menulis kode dengan mengikuti paradigma OOP, bukan berarti kita sudah mengikuti _design principle_ yang sudah kita pelajari bersama di modul-modul sebelumnya.

Jika kita mengilustrasikan prinsip SOLID, seperti inilah gambarnya:  

![[Pasted image 20221215055916.png]]

Ilustrasi di atas menggambarkan bagaimana sekumpulan bola yang disusun sedemikian rupa dapat menciptakan bentuk yang kukuh. Padahal seperti yang kita ketahui, bola memiliki bentuk yang sangat mudah untuk bergerak. Analogi serupa dapat kita terapkan saat mengetik kode. Dalam mengembangkan sebuah perangkat lunak, jika kita bisa menuliskan kode dengan bentuk dan ukuran yang sama seperti halnya kumpulan bola di atas, kita pun dapat menciptakan sebuah sistem yang kukuh. Denga terciptanya sistem yang kukuh, kita dapat lebih mudah dan leluasa mengganti komponen dan memperluas sistem tanpa adanya gangguan.

### Tujuan SOLID

Sudah paham kan penjelasan dari ilustrasi di atas? Kita jadi paham bahwa dengan mengikuti prinsip SOLID, kode yang kita buat dapat dengan mudah diekstensi _(extended)_ dan dipertahankan _(maintained)_.

Prinsip SOLID bukanlah suatu hukum atau aturan tertentu yang wajib kita patuhi, melainkan sebuah prinsip yang dimaksudkan untuk membantu kita dalam menuliskan kode yang rapi. Bagaimana hal itu dapat diwujudkan? Berikut adalah tujuan dari prinsip SOLID dalam pembuatan struktur _mid-level_ perangkat lunak:

-   Toleran terhadap perubahan [2](https://learning.oreilly.com/library/view/clean-architecture-a/9780134494272/).
-   Mudah dipahami [2](https://learning.oreilly.com/library/view/clean-architecture-a/9780134494272/).
-   Komponen dasar dapat digunakan kembali dalam bentuk _software system_ lainnya [2](https://learning.oreilly.com/library/view/clean-architecture-a/9780134494272/).

Istilah _mid-level_ yang merujuk pada prinsip SOLID ini diterapkan oleh engineer yang bekerja pada level module [2](https://learning.oreilly.com/library/view/clean-architecture-a/9780134494272/). Prinsip ini diterapkan tepat di atas level kode. Manfaatnya, ia dapat membantu menentukan jenis struktur perangkat lunak yang digunakan dalam modul dan komponen. Setelah komponen tersebut dapat kita desain dengan baik menggunakan prinsip SOLID, maka selanjutnya kita dapat melanjutkan ke dalam prinsip-prinsip arsitektur tingkat tinggi _(high-level architecture)_ [2](https://learning.oreilly.com/library/view/clean-architecture-a/9780134494272/). 

Di modul berikutnya kita akan sama-sama belajar lebih dalam lagi tentang masing-masing _principle_ yang menjadi bagian dari SOLID itu sendiri.