---
created: Thursday, January 5th 2023 - 16.10
updated: Thursday, January 5th 2023 - 16.10
---
## Gateways

### Internet Gateway

Internet Gateway adalah komponen VPC yang dapat horizontal scaling, redundant, dan highly available. Ia memungkinkan kita untuk mengomunikasikan antara VPC dan internet. Internet Gateway adalah salah satu dari layanan Managed Services (layanan terkelola) dari AWS.

Internet Gateway memiliki dua tujuan: 

-   Menjadi target di route table VPC kita untuk lalu lintas yang akan dirutekan internet. 
-   Melakukan Network Address Translation (NAT) alias terjemahan alamat jaringan untuk instance yang telah di-assign alamat IPv4 publik. 

Internet Gateway mendukung lalu lintas IPv4 dan IPv6. Ilustrasi berikut menunjukkan konfigurasi Internet Gateway di route table:

![[Pasted image 20230105160930.png]]

Gambar di atas mendefinisikan sebuah subnet, yaitu subnet publik. Pada route table, kita memasukkan default route yaitu 0.0.0.0/0 dengan target igw-id yang merujuk ke Internet Gateway.  
  

### NAT Gateway

Kita dapat menggunakan _Network Address Translation_ (NAT) gateway untuk memungkinkan resource yang berada di private subnet terhubung ke internet atau layanan AWS lainnya secara satu arah (_outbound_), tetapi mencegah traffic internet dari luar untuk masuk dan memulai koneksi dengan resource tersebut (_inbound_).

![[Pasted image 20230105160944.png]]

Pada ilustrasi di atas, kita membuat subnet tambahan yaitu private subnet 10.0.20.0/24. Subnet ini tidak memiliki route di dalam route table-nya yang menunjuk ke internet gateway. Dari konfigurasi sebelumnya, kita telah memiliki public subnet yang memiliki route yang menuju ke Internet Gateway yaitu <igw-id>. 

Di dalam public subnet, kita melakukan provisioning NAT gateway <nat-id>. Karena berada di public subnet, maka <nat-id> juga mengerti mengenai adanya default route yang mengarah ke <igw-id>. Selanjutnya, kita mendefinisikan default route di private subnet yang menunjuk ke <nat-id>.

Dengan informasi di atas, maka saat kita membuat sebuah instance EC2 di private subnet, walaupun ia memiliki IP address private, instance ini akan tetap bisa mengakses internet melalui NAT Gateway. Ingat! Koneksi dari instance ini akan bersifat satu arah (arah keluar/outbound).

**PENTING!** Kita dikenai biaya untuk membuat dan menggunakan NAT gateway.  
  

### Rekomendasi tentang Subnet

Gunakanlah subnet yang lebih besar dibandingkan yang kecil (misal /24 ke atas), sebabnya:  

-   Penempatan workload (beban kerja) menjadi lebih sederhana.  
-   Kemungkinan kehabisan alamat IP akan lebih kecil.

Selain itu, kita juga dapat mempertimbangkan dua hal berikut dalam membuat arsitektur subnet, antara lain:

-   Jika kita tidak yakin mengenai konfigurasi subnet, mulailah dengan satu subnet public dan private di setiap Availability Zone.
-   Umumnya kita akan butuh lebih banyak IP di subnet private dibandingkan subnet public.