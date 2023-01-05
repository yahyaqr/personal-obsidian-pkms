---
created: Thursday, January 5th 2023 - 16.26
updated: Thursday, January 5th 2023 - 16.26
---
## Menghubungkan VPC

Mengisolasikan workloads (beban kerja) adalah pendekatan yang baik dan hal ini umum diterapkan dengan penggunaan VPC. Tetapi, adakalanya kita tetap memerlukan komunikasi antara workload-workload yang terdapat di VPC yang berbeda. Hal ini bisa kita dapatkan dengan melakukan VPC Peering.

Berikut adalah hal-hal yang perlu diperhatikan saat kita mendesain VPC Peering:

-   VPC Peering hanya bisa digunakan untuk IP private.
-   Kita bisa melakukan Peering intra dan antar-Region.
-   Block IP antara VPC tidak boleh tumpang tindih.
-   Hanya satu resource peering di antara dua VPC mana pun.
-   Tidak mendukung hubungan peering transitif.
-   Dapat dibuat di antara akun AWS yang berbeda.

Untuk membuat koneksi VPC Peering, VPC pemohon/_requester_ (VPC lokal) mengirimkan permintaan ke VPC peer untuk membuat koneksi VPC Peering. VPC peer dapat dimiliki oleh kita sendiri atau akun AWS lain, tidak boleh terjadi blok CIDR yang tumpang tindih dengan blok CIDR VPC pemohon. VPC peer tujuan harus menerima (_accept_) permintaan untuk mengaktifkan koneksi VPC Peering. 

Nah, untuk mengizinkan aliran lalu lintas antara VPC peer yang sudah terkoneksi dengan menggunakan alamat IP private, tambahkan route ke satu atau beberapa route table VPC kita yang mengarah ke alamat IP dari VPC peer tujuan. Demikian sebaliknya, VPC peer tujuan juga perlu menambahkan route pada salah satu route table VPC mereka yang mengarah ke rentang alamat IP VPC kita. Diagram di bawah menggambarkan hal ini.

![[Pasted image 20230105162515.png]]

### Contoh Pengaplikasian VPC Peering

Sekarang, mari kita lihat contoh pengaplikasian VPC Peering untuk layanan berbagi (_shared services_). Dalam contoh ini, untuk melaksanakan tanggung jawabnya, tim IT dan Information Security perusahaan menyediakan "Services VPC" yang mana setiap departemen dapat melakukan peer satu sama lain. 

VPC ini memiliki koneksi ke Active Directory, alat pemindaian keamanan, alat pemantauan/pencatatan, dan beberapa fungsi lainnya. VPC ini juga menyediakan proxy yang dapat mengakses resource on-premise.

![[Pasted image 20230105162531.png]]

Perhatikan bahwa ada koneksi VPC Peering dengan VPC yang berada di region yang berbeda, yakni antara Region A dan Region B. Amazon EC2 memungkinkan hubungan peering antara VPC di berbagai AWS Regions. 

VPC Peering antar region memungkinkan sumber daya VPC (seperti EC2 instance, Amazon RDS, dan Lambda function) yang berjalan di AWS Region yang berbeda untuk berkomunikasi satu sama lain menggunakan alamat IP private tanpa memerlukan gateway, koneksi VPN, atau perangkat keras fisik terpisah.