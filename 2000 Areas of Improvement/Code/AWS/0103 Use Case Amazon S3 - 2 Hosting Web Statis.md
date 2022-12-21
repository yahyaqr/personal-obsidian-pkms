---
created: Wednesday, December 21st 2022 - 08.16
updated: Wednesday, December 21st 2022 - 08.16
---
### Kasus Penggunaan 2: Hosting Seluruh Konten Web Statis

Amazon S3 juga bisa digunakan untuk hosting seluruh konten web statis termasuk file html, gambar, video, dan juga skrip sisi klien (_client-side scripts_).

![[Pasted image 20221221081536.png]]

Untuk mengonfigurasi bucket agar dapat meng-hosting situs web statis, Anda bisa menggunakan AWS Management Console tanpa perlu menulis kode apa pun. Anda juga dapat membuat, memperbarui, dan menghapus konfigurasi situs web secara terprogram dengan menggunakan AWS SDK.

SDK menyediakan utility agar dapat mengunggah objek ke Amazon S3 dengan mudah.. Jika aplikasi Anda membutuhkan akses langsung ke Amazon S3, Anda dapat mengirim permintaan melalui REST API.

Untuk meng-hosting situs web statis di Amazon S3, aktifkan fitur “_static website hosting_” pada Amazon S3 bucket Anda, kemudian unggah konten situs web yang diinginkan.

Saat Anda mengonfigurasi bucket sebagai situs statis, selain harus mengaktifkan fitur “_static website hosting_”, Anda juga perlu mengatur permission dan membuat serta menambahkan dokumen indeks. Bergantung pada kebutuhan situs web Anda, Anda juga dapat mengonfigurasi _redirect_, _web traffic logging_, dan _custom error document_.

Setelah mengonfigurasi bucket sebagai situs web statis, Anda dapat mengakses bucket melalui website endpoint untuk AWS Regions tertentu dari bucket Anda.

Website endpoint ini berbeda dengan endpoint tempat Anda mengirim permintaan REST API. Untuk informasi lebih lanjut, lihat [Amazon S3 Website Endpoints](https://docs.aws.amazon.com/general/latest/gr/s3.html#s3_website_region_endpoints).

Ketahuilah! Amazon S3 tidak mendukung akses HTTPS untuk website endpoint. Jika Anda ingin menggunakan HTTPS, Anda dapat menggunakan Amazon CloudFront untuk melayani situs web statis yang di-hosting di Amazon S3.