---
created: Wednesday, December 21st 2022 - 08.09
updated: Wednesday, December 21st 2022 - 08.09
---

### Kasus Penggunaan 1: Menyimpan dan Mendistribusikan Konten Web Statis dan Media

![[Pasted image 20221221080234.png]]

Anda dapat menggunakan Amazon S3 untuk menyimpan dan mendistribusikan konten web statis atau media. File ini dapat dikirim langsung dari Amazon S3 karena setiap objek dikaitkan dengan URL HTTP unik yang harus sesuai dengan nama domainnya (contoh startupwarungkopi.com).

Misalnya, Anda dapat menyimpan konten web (gambar atau video) di Amazon S3 dan menjalankan web server di Amazon EC2. Dengan strategi ini, beban kerja server menjadi lebih ringan karena ia bisa fokus terhadap kalkulasi proses bisnis.

Tak hanya itu, Amazon S3 juga dapat digunakan sebagai _origin_ (asal) untuk layanan _content delivery_ _network_ seperti Amazon CloudFront.

Amazon S3 berfungsi dengan baik untuk situs web yang berkembang pesat dan membutuhkan elastisitas kuat. Termasuk juga beban kerja dengan konten yang dibuat pengguna dalam jumlah besar, seperti _photo_ atau _video sharing_.

Secara default, semua sumber daya Amazon S3—bucket, objek, dan sub-sumber daya terkait (konfigurasi lifecycle dan situs web) bersifat **private**. Artinya, hanya pemilik sumber daya (owner dari bucket) yang dapat mengaksesnya. Pemilik sumber daya dapat memberikan izin akses kepada orang lain dengan menulis _access policy_.

![[Pasted image 20221221081224.png]]

Amazon S3 bucket terlindungi secara default. Hanya akun administrator dan root user-lah yang memiliki akses ke bucket yang baru dibuat dan belum dimodifikasi.

Lalu, bagaimana jika ingin mengaktifkan akses tambahan untuk pengguna lain? Nah, tenang! Caranya, Anda dapat memodifikasi bucket policy.

Selain itu, AWS menyediakan sejumlah alat (_tool_) berbeda yang memungkinkan developer mengonfigurasi bucket untuk berbagai macam beban kerja.

Amazon S3 juga menyertakan fitur "_block public access_" yang bertindak sebagai lapisan perlindungan tambahan untuk mencegah pembukaan akses data pelanggan tanpa sengaja.

Di setelan akses publik untuk sebuah bucket, pelanggan dapat menentukan 4 opsi yang mana semuanya telah diaktifkan secara default. Di antaranya:

-   Memblokir akses publik terhadap bucket dan objek yang diberikan melalui ACL (Access Control List) yang baru.
-   Memblokir akses publik terhadap bucket dan objek yang diberikan melalui ACL (Access Control List) yang sudah ada (existing) maupun yang baru.
-   Memblokir akses publik terhadap bucket dan objek yang diberikan melalui _bucket policy_ yang baru.
-   Memblokir akses untuk publik dan akses antar akun terhadap bucket dan objek melalui bucket policy yang sudah ada (existing) maupun yang baru.

Karena semua opsi pengaturan di atas diaktifkan secara default, maka jika Anda memerlukan akses publik, Anda perlu menonaktifkan setelan-setelan tersebut secara manual.

> **PENTING!** Meskipun kasus penggunaan situs web atau konten statis dengan S3 adalah contoh yang bagus untuk menyiapkan arsitektur AWS dengan cepat, namun akses publik ke Amazon S3 bukanlah termasuk ke dalam mayoritas kasus penggunaan. Tahukah Anda bahwa sebagian besar kasus penggunaan Amazon S3 TIDAK memerlukan akses publik. Lebih sering, Amazon S3 menyimpan data yang merupakan bagian dari aplikasi lain. Akses publik tidak boleh digunakan untuk jenis bucket pribadi.