---
created: Thursday, January 5th 2023 - 15.53
updated: Thursday, January 5th 2023 - 15.53
---
## Jenis-Jenis Amazon VPC

Berdasarkan arsitekturnya, Amazon VPC bisa dibagi ke dalam tiga kategori, yaitu:

-   Satu VPC, dengan satu akun AWS.
-   Banyak VPC, dengan satu akun AWS.
-   Banyak VPC, dengan beberapa akun AWS.

Supaya dapat dipahami lebih jelas, mari kita uraikan satu per satu. _Let’s go!_

  

### Satu VPC, Satu Akun

Di dunia nyata, jarang ada pengguna AWS yang hanya menggunakan satu VPC dalam satu akun. Terdapat beberapa kasus penggunaan untuk kategori ini, antara lain:

-   **Aplikasi kecil atau tunggal (single application) yang dikelola oleh satu orang atau tim yang sangat kecil**  
    Kasus penggunaan ini mungkin akan sesuai untuk aplikasi yang baru berkembang atau tim yang masih kecil.
    
-   **Komputasi berkinerja tinggi (High Performance Computing)**  
    HPC membutuhkan latensi sekecil mungkin di mana menempatkan resources di satu lingkungan VPC akan mendapatkan latensi yang lebih baik dibandingkan menyebarkannya di beberapa VPC.
    
-   **Manajemen identitas**  
    Untuk memenuhi unsur keamanan, satu VPC bisa memberikan solusi terbaik.
    

Selanjutnya, mari kita bahas konfigurasi yang lebih umum digunakan oleh pengguna AWS, yakni banyak VPC dalam satu akun.

  

### Banyak VPC, Satu Akun

Arsitektur kedua ini umum digunakan oleh pengguna AWS. Kategori ini mendefinisikan beberapa VPC sesuai kebutuhan. Sebagai contoh, gambar di bawah ini menjelaskan empat buah VPC untuk beberapa _environment_ (lingkungan) dalam satu akun AWS, yaitu **Prod** (Production), **Staging**, **Test**, dan terakhir **Dev** (Development).

![[Pasted image 20230105155326.png]]

Arsitektur ini ideal untuk:

-   Tim atau organisasi tunggal, seperti penyedia layanan terkelola (_managed service providers_).
-   Tim terbatas, ini membuatnya lebih mudah untuk mempertahankan standar dan mengelola akses.

**Pengecualian**: Harus diperhatikan apakah ada kebutuhan untuk memenuhi standar tata kelola dan kepatuhan (_Governance and Compliance Standards_) di mana mungkin memerlukan isolasi beban kerja yang lebih dalam lagi terlepas dari kompleksitas organisasi.

  

### Banyak VPC, Beberapa Akun

Arsitektur ini mungkin akan lebih cocok untuk organisasi atau perusahaan yang besar dan/atau memiliki banyak tim IT. Selain itu, arsitektur ini juga sesuai untuk perusahaan yang sedang mengantisipasi pertumbuhan yang besar. Simak ilustrasi di bawah berikut:

![[Pasted image 20230105155432.png]]

Contoh di atas menggambarkan sebuah perusahaan multinasional yang memiliki banyak akun, di mana setiap akun juga punya VPC masing-masing. Arsitektur ini juga bisa digunakan untuk organisasi yang memiliki beberapa tim khusus di mana developers hanya akan memiliki akses penuh terhadap Dev environment dan punya restriksi akses terhadap Production environment.

Untuk pemahaman lebih lanjut mengenai arsitektur VPC, AWS telah menerbitkan _whitepaper_ (buku putih) khusus mengenai ini yaitu [Building a Scalable and Secure Multi-VPC AWS Network Infrastructure](https://docs.aws.amazon.com/whitepapers/latest/building-scalable-secure-multi-vpc-network-infrastructure/welcome.html).