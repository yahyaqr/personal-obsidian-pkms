---
created: Thursday, December 15th 2022 - 06.01
updated: Thursday, December 15th 2022 - 06.01
---
![[Pasted image 20221215060035.png]]

Kita sudah belajar memahami Object Orientation Programming dan Software Design Principle. Akhirnya kita sampai juga di modul yang membahas masing-masing prinsip bagian dari SOLID, lebih dalam.

### Single Responsibility Principle (SRP)

> "_A module should be responsible to one, and only one, actor._" [2](https://learning.oreilly.com/library/view/clean-architecture-a/9780134494272/)  

(Robert Cecil Martin, 2017)

Kita mulai dari **Single Responsibility Principle (SRP).** SRP merupakan sebuah principle yang relatif mudah diterapkan dalam pengembangan perangkat lunak. Sederhananya, principle ini digunakan untuk mengatur tanggung jawab dari sebuah entitas yang berada di dalam sebuah proyek dalam hal ini adalah sebuah _module__/class_ untuk memenuhi kebutuhan dari _actor. A__ctor_ merupakan kumpulan "user" atau "stakeholder" yang menginginkan perubahan pada perangkat lunak kita [2](https://learning.oreilly.com/library/view/clean-architecture-a/9780134494272/).

Tanggung jawab (responsibility) berarti bahwa jika suatu _class_ punya 2 (dua) fungsionalitas yang tak miliki keterkaitan untuk melakukan suatu perubahan, maka kita harus membagi fungsionalitas yang berbeda tersebut dengan cara memisahkannya menjadi dua _class_ yang berbeda. 

Maka dari itu, setiap class yang sudah dipisahkan berdasarkan fungsionalitasnya hanya akan menangani satu tanggung jawab. Lebih lanjut, jika kita melakukan perubahan tanggung jawab, kita tinggal fokus pada masing-masing _class_ yang sudah dipisahkan tersebut. 

Berikut adalah gambaran ilustrasi dari SRP:

![[Pasted image 20221215060127.png]]

Sudah jelas kan? Pada SRP sebuah class tidak boleh memiliki lebih dari dari satu tanggung jawab, seperti sebagai koki, kasir, satpam, dan sopir sekaligus. Namun ia harus dipisah sesuai dengan tanggung jawab masing-masing.

Apa tujuan menerapkan Single Responsibility? Ketika kita ingin melakukan perubahan pada sebuah class yang memiliki tanggung jawab yang banyak, perubahan yang akan dilakukan berpotensi untuk mempengaruhi fungsionalitas dan tanggung jawab lain yang saling berkaitan di dalam _class_ tersebut.

Single Responsibility Principle adalah prinsip yang sederhana dan intuitif, tetapi dalam praktiknya terkadang sulit untuk memperbaikinya. Untuk itu, mari kita lanjut ke modul selanjutnya untuk mengetahui seperti apa penerapannya pada sebuah contoh kasus. Ayo!