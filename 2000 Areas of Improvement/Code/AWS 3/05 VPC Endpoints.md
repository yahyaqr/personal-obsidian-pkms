---
created: Thursday, January 5th 2023 - 16.29
updated: Thursday, January 5th 2023 - 16.29
---
## VPC Endpoints

Amazon VPC Endpoints memungkinkan koneksi pribadi antara VPC dan layanan lainnya tanpa meninggalkan jaringan AWS. Dengan VPC Endpoints, Amazon EC2 instance dapat berkomunikasi dengan layanan AWS di region yang sama dengan alamat IP private. Ia tidak perlu melewati internet, NAT instance, koneksi VPN, atau DX. 

VPC Endpoints juga menyediakan fitur keamanan tambahan seperti kemampuan untuk menambahkan kebijakan untuk mengontrol S3 bucket mana yang dapat diakses atau mengunci S3 bucket ke VPC tertentu.

VPC Endpoint adalah perangkat virtual. Ia merupakan komponen VPC yang _horizontally scaled_, _redundant_, _highly available_, serta memungkinkan komunikasi antara instance dalam VPC dan layanan lainnya tanpa perlu memikirkan availability atau keterbatasan bandwidth pada lalu lintas jaringan.

VPC Endpoints memiliki fitur-fitur berikut:

-   Lalu lintas data tetap berada di dalam AWS.
-   Layanan AWS tujuan harus berada di region yang sama.
-   Horizontally scaled, redundant, dan highly available.

Ada dua jenis VPC EndPoints, yaitu Interface Endpoint dan Gateway Endpoint. Interface Endpoint merupakan ENI (Elastic Network Interface) dengan alamat IP private yang berfungsi sebagai _entry point_ (titik masuk) untuk lalu lintas yang ditujukan ke layanan tertentu.

Sementara itu, Gateway Endpoint adalah target untuk route tertentu di dalam Route Table. Ia digunakan sebagai penghubung pada layanan AWS.

Berikut adalah beberapa layanan yang didukung untuk Interface Endpoint dan Gateway Endpoint:

![[Pasted image 20230105162906.png]]