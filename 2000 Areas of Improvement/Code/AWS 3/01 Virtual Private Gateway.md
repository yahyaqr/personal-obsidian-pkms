---
created: Thursday, January 5th 2023 - 16.23
updated: Thursday, January 5th 2023 - 16.23
---
## Virtual Private Gateway

![[Pasted image 20230105162255.png]]

Secara default, instance yang diluncurkan ke Amazon VPC tidak dapat berkomunikasi dengan jaringan kita, misalnya yang berada di on-premise. 

Kita dapat mengaktifkan akses ke jaringan jarak jauh dari VPC dengan menempatkan virtual private gateway (VGW), membuat route table khusus, memperbarui aturan security group, dan membuat koneksi VPN yang dikelola AWS.

Meskipun kata koneksi VPN adalah istilah umum, dalam dokumentasi Amazon VPC, istilah ini merujuk pada koneksi antara VPC dan jaringan kita yang berada pada lokasi on-premise. AWS juga mendukung IPsec (IP security) VPN connection alias koneksi VPN dengan protokol keamanan internet.

VGW adalah konsentrator VPN di sisi Amazon dari koneksi VPN. Kita dapat membuat VGW dan menempatkannya pada VPC yang diinginkan untuk membuat koneksi VPN. 

Amati gambar di bawah ini yang mengilustrasikan koneksi VPN antara gateway virtual VPC dan data center kita. 

![[Pasted image 20230105162317.png]]

Di AWS, VGW juga mendukung beberapa koneksi gateway sehingga pelanggan dapat menerapkan _redundancy_ dan _failover_ di sisi koneksi VPN. Tersedia juga opsi perutean dinamis dan statis yang dapat memberikan fleksibilitas dalam konfigurasi perutean.

Selain solusi di atas, tentu saja kita juga dapat membangun koneksi VPN ke jaringan remote (bisa on-premise atau cloud lain) dengan menggunakan Amazon EC2 instance di VPC yang menjalankan software VPN. Selain itu, keuntungan menggunakan VGW adalah segala masalah (seperti high availability) ditangani oleh AWS.