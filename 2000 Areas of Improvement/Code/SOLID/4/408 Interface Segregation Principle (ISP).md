---
created: Thursday, December 15th 2022 - 05.46
updated: Thursday, December 15th 2022 - 05.46
---

![[Pasted image 20221215054743.png]]

Setelah Liskov Substitution, prinsip selanjutnya yang akan kita pelajari adalah Interface segregation. Prinsip Interface Segregation adalah salah satu dari prinsip yang dikemukakan oleh Robert C.Martin dalam bukunya yang berjudul _Design Principle_. Meskipun prinsip-prinsip tersebut sudah beberapa tahun usianya, prinsip-prinsip ini tetap penting seperti saat pertama kali ia rilis. 

### Interface Segregation Principle (ISP)

> "_Clients should not be forced to depend upon interfaces that they do not use._"  

(Robert Cecil Martin)

Prinsip ini sendiri bertujuan untuk mengurangi jumlah ketergantungan sebuah class terhadap interface class yang tidak dibutuhkan. Faktanya, class memiliki ketergantungan terhadap class lainnya. Jumlah ketergantungan dari fungsi pada sebuah interface class yang dapat diakses oleh class tersebut harus dioptimalkan atau dikurangi. Mengapa penting? Terkadang ketika kita membuat sebuah class dengan jumlah fungsi dan properti yang banyak, class lain yang bergantung pada class tersebut hanya membutuhkan satu atau dua fungsi dari class tersebut. Ketergantungan antar class akan semakin bertambah seiring bertambahnya jumlah fungsi dan properti dari class yang dibutuhkan. Lalu bagaimana cara mengatasinya?

Pada saat kita membuat sebuah sistem, pasti kita pernah membuat sebuah class yang memiliki atau mengimplementasikan beberapa _public interface_ dan beberapa _interface_ tersebut juga digunakan dan diimplementasi oleh class lainnya dalam sistem kita. class-class yang kita buat ini terkadang hanya membutuhkan beberapa fungsi yang ada pada interface tersebut sehingga menurut aturan prinsip interface segregation hal ini kurang baik. Tapi tenang, ketika prinsip interface segregation diterapkan, setiap class-class akan mengimplementasi beberapa interface class yang lebih kecil sesuai dengan fungsi-fungsi yang dibutuhkan class-class tersebut. 

Hal ini berarti bahwa class-class yang saling bergantung dapat berkomunikasi dengan menggunakan interface yang lebih kecil, mengurangi ketergantungan pada fungsi-fungsi yang tidak digunakan dan mengurangi _coupling_. Dengan menggunakan _interface_ yang lebih kecil akan memudahkan dalam implementasi, meningkatkan fleksibilitas dan juga kemungkinan untuk digunakan kembali (_reuse)_.

Berikut adalah gambaran ilustrasi dari ISP:

[!![[Pasted image 20221215054755.png]]

ISP adalah tentang pemisahan tanggung jawab. Robot yang nggak punya alat untuk menyelesaikan tugas, jangan diberi tugas yang tidak semestinya. Misalnya robot yang tidak punya sayap, seharusnya tidak diberikan tugas untuk terbang. Namun sesuaikan tugas dengan kebutuhan masing-masing.

Menarik sekali bukan jika kita berhasil menerapkan prinsip interface segregation dalam sistem kita? Yuk kita lanjutkan belajarnya ke studi kasus pada modul selanjutnya.