---
created: Thursday, December 15th 2022 - 06.05
updated: Thursday, December 15th 2022 - 06.05
---
![[Pasted image 20221215060359.png]]

Setelah selesai dengan Single Responsibility Principle, mari kita lanjut ke aturan berikutnya yaitu sebuah entitas perangkat lunak seperti class, property, dan function. Mereka adalah entitas untuk ditambahkan tetapi tidak untuk dimodifikasi yaitu **Open/Close Principle**. Seperti apa detail aturannya?

### Open/Close Principle (OCP)

> _"A software artifact should be open for extension but closed for modification."_ [2](https://learning.oreilly.com/library/view/clean-architecture-a/9780134494272/)

(Bertrand Meyer, 1988)

Pada Tahun 1988, seorang profesor asal Perancis, Bertrand Meyer menulis sebuah buku yang berjudul _Object Oriented Software Construction_. Di dalamnya terdapat sebuah aturan yang mengatur di mana sebuah artefak perangkat lunak harus terbuka untuk ditambahkan tetapi tertutup untuk dimodifikasi. Aturan tersebut kemudian ditulis lagi pada sebuah artikel yang berjudul _The Open-Closed Principle_ oleh Robert C. Martin pada tahun 1996.

Lantas apa yang dimaksud dengan terbuka untuk ditambahkan dan tertutup untuk dimodifikasi? Jangan bingung. Terbuka untuk ditambahkan adalah keadaan ketika sebuah sistem dapat ditambahkan dengan spesifikasi baru yang dibutuhkan. Sedangkan tertutup untuk dimodifikasi adalah agar ketika ingin menambahkan spesifikasi baru, kita tidak perlu mengubah atau memodifikasi sistem yang telah ada.

Aturan ini sekilas terlihat bertentangan satu sama lain, yah? Namun tak usah khawatir, karena saat kita bisa mengatur dependensi sistem dengan baik dan benar, dengan mudahnya aturan tersebut dapat kita capai. Secara umum, penggunaan aturan open/close diterapkan dengan memanfaatkan _interface_ dan abstraksi kelas daripada menggunakan sebuah kelas konkret. Penggunaan _interface_ dan abstraksi kelas bertujuan agar dapat mudah diperbaiki setelah pengembangan tanpa harus mengganggu kelas yang mewarisi dan ketika ingin membuat fungsionalitas baru, cukup dengan membuat kelas baru dan mewarisi _interface_ atau abstraksi tersebut.

Berikut adalah gambaran ilustrasi dari OCP:

![[Pasted image 20221215060433.png]]

Seperti yang Anda lihat, ketika ingin menambahkan fungsi baru pada robot, kita tidak boleh mengubah fitur dasarnya. Misalnya pada dasarnya dia adalah robot yang bisa memasak, maka kemampuan memasak tersebut tidak boleh hilang ketika ada perubahan.

Penasaran seperti apa penerapannya? Mari melangkah ke modul berikutnya.