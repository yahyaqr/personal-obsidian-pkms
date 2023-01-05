---
created: Thursday, January 5th 2023 - 16.06
updated: Thursday, January 5th 2023 - 16.06
---
## Subnets

Seperti yang sudah dijelaskan sebelumnya, VPC adalah jaringan virtual yang didedikasikan untuk akun AWS kita. Saat membuat VPC, kita harus menentukan rentang alamat IPv4 dalam bentuk blok Classless Inter-Domain Routing (CIDR), misalnya 10.0.0.0/16. Ini adalah blok CIDR utama untuk VPC kita. 

Selanjutnya, kita membagi-bagi blok CIDR tadi ke beberapa sub block atau kelompok alamat IP yang lebih kecil. Sub block ini disebut sebagai subnet. 

![[Pasted image 20230105160604.png]]

Setiap subnet harus berada seluruhnya dalam satu Availability Zone. Itu artinya, kita bisa membuat Subnet 1 di Availability Zone A, Subnet 2 di Availability Zone B, dan Subnet 3 di Availability Zone C.

Berikut adalah beberapa atribut kunci dari subnet:

-   Subnet adalah subset dari blok CIDR VPC.
-   Subnet yang berada di dalam setiap blok CIDR tidak boleh bertumpang tindih (_overlap_).
-   Setiap subnet berada sepenuhnya dalam satu Availability Zone.
-   Availability Zone dapat terdiri dari beberapa subnet.

**PENTING:** AWS akan me-reserve 5 alamat IP dari setiap subnet yang didefinisikan.

Saat membicarakan sebuah subnet, kita juga perlu belajar bagaimana cara menentukan rute lalu lintas jaringannya. Maka dari itu, yuk kita belajar tentang route table di materi selanjutnya!

### Route Table

Route table berisi sekumpulan aturan (disebut _route_) yang digunakan untuk menentukan ke mana lalu lintas jaringan dari subnet akan diarahkan. Agar lebih memperjelas pembahasan, berikut adalah hal-hal penting mengenai route table:

-   Route table diperlukan untuk mengarahkan lalu lintas antar sumber daya VPC.
-   Setiap VPC memiliki route table utama (default).
-   Anda dapat membuat route table sendiri (custom).
-   Semua subnet harus diasosiasikan ke route table.

_Route table_ utama berada di tingkat VPC. Jika diperlukan, kita dapat menambah, mengubah, dan menghapus route yang ada di route table utama. Namun, kita tidak bisa menghapus **route table** utama.

Sementara itu, _route table custom_ berada di tingkat subnet. Sebuah subnet hanya bisa diasosiasikan ke satu route table custom. Jika diperlukan, kita bisa menambah, mengubah, dan menghapus route yang ada di route table custom. Route table custom hanya bisa dihapus jika tidak ada lagi asosiasi subnet di dalamnya.

Ada dua jenis subnet yaitu Private dan Public Subnet. Silakan cek gambar berikut yang akan menunjukkan rekomendasi pembagian jenis subnet berdasarkan resources-nya:

![[Pasted image 20230105160716.png]]

Seperti yang ditampilkan pada gambar di atas, kita menggunakan subnet untuk mendefinisikan akses ke internet. Berikut adalah perbedaan antara public subnet dan private subnet:

![[Pasted image 20230105160728.png]]

Kita dapat melihat perbedaan public dan private subnet dari gambar di atas. Oke, setelah belajar mengenai subnet, mari kita bahas mengenai komponen lain yang digunakan terkait jaringan di AWS, yakni Elastic Network Interface dan juga Elastic IP address.

  

### Elastic Network Interface

![[Pasted image 20230105160737.png]]

Elastic Network Interface (ENI) adalah network adapter atau network card virtual yang dapat dipasangkan ke instance AWS. ENI bisa dipindahkan antar-_instance_ EC2 yang berada di Availability Zones yang sama.

Saat dipindahkan, ENI akan tetap menyimpan beberapa konfigurasi, seperti:

-   Alamat IP Private
-   Alamat IP Elastic (Elastic IP Address)
-   MAC address

![[Pasted image 20230105160750.png]]

Ketahuilah! Satu instance EC2 bisa memiliki satu atau lebih ENI dan masing-masing ENI tersebut bisa saja berada di subnet yang berbeda, tetapi sekali lagi ingat, harus tetap berada di Availability Zone yang sama. Konfigurasi ini disebut _dual-homed_ atau _multi-homed_.

  

### Elastic IP Address

Elastic IP Address adalah alamat IPv4 publik yang dipesan (reserve) khusus untuk kita. Elastic IP address ini adalah resource yang ada di tingkat Region. Berikut adalah hal-hal penting mengenai Elastic IP Address:

-   Dapat diasosiasikan dengan sebuah instance atau ENI.
-   Bisa diasosiasikan kembali (_re-associate_) dan mengarahkan lalu lintas dengan segera.
-   Secara default, setiap akun AWS dapat memiliki 5 IP Publik per AWS Region.
-   EIP bisa didapatkan dari alamat yang dibawa sendiri alias Bring Your Own IP (BYOIP).