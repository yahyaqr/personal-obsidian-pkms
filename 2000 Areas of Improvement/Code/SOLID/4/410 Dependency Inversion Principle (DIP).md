---
created: Thursday, December 15th 2022 - 05.52
updated: Thursday, December 15th 2022 - 05.52
---
![[Pasted image 20221215055054.png]]

Setelah kita membahas mengenai empat prinsip sebelumnya, kini kita akan membahas mengenai prinsip terakhir dari S.O.L.I.D, yaitu Prinsip Dependency Inversion. Pada prinsip Dependency Inversion terdapat dua pernyataan atau aturan yang perlu kita ketahui, yang pertama adalah _high-level module_ tidak diperbolehkan untuk bergantung pada _low-level module_. Keduanya harus bergantung pada _abstraction_. Pernyataan yang kedua, abstraksi tidak diperbolehkan untuk bergantung pada detail. Detail harus bergantung pada abstraksi.

### Dependency Inversion Principle (DIP)

> _"High-level modules should not depend on low-level modules. Both should depend on abstractions."_   

(Robert Cecil Martin)

Prinsip Dependency Inversion hampir sama dengan konsep layering dalam aplikasi, di mana _low-level modules_ bertanggung jawab dengan fungsi yang sangat detail dan _high-level modules_ menggunakan _low-level classes_ untuk mencapai tugas yang lebih besar. Hal ini bisa dicapai dengan bergantung pada sebuah abstraksi, ketika ada ketergantungan antar kelas seperti interface, daripada referensi langsung ke kelas lainnya.

Apa yang dimaksud dengan _high-level modules_ dan _low-level modules_? Agar lebih mudah memahaminya, kita dapat mengkategorikan kelas-kelas menjadi sebuah hirarki. _High-level modules_ adalah kelas-kelas yang berurusan dengan kumpulan-kumpulan fungsionalitas. Pada hirarki tertinggi terdapat kelas-kelas yang mengimplementasikan aturan bisnis sesuai dengan desain yang telah ditentukan. _Low-level modules_ bertanggung jawab pada operasi yang lebih detail. Pada level terendah memungkinkan modul ini untuk bertanggung jawab dalam menulis informasi ke database atau menyampaikan pesan ke sistem operasi. 

![[Pasted image 20221215055150.png]]

Pada prinsip DIP, robot tidak boleh tergantung dengan satu alat saja, namun bisa diubah-ubah. Misalnya robot tidak boleh hanya tergantung pada spatula saja untuk memasak, tapi bisa juga menggunakan pisau, penjepit atau centong. Dapat dilihat sebelumnya spatula tertanam pada tangan robot, sehingga ia tidak bisa menggunakan alat lain. Nah, untuk mengatasinya kita perlu menambahkan sekrup yang bisa digunakan untuk bongkar pasang alat. Sekrup ini pada dunia programming bisa menggunakan interface atau abstract class.

Bagaimana? Sudah paham dengan konsep Dependency Inversion? Yuk kita simak modul selanjutnya agar paham penerapannya pada sebuah studi kasus.