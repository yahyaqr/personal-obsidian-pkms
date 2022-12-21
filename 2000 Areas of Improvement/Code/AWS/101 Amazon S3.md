---
created: Wednesday, December 21st 2022 - 07.55
updated: Wednesday, December 21st 2022 - 07.55
---
## Pengenalan Amazon S3

Amazon Simple Storage Service (S3) adalah layanan dari AWS untuk menyimpan file berbasis objek _(object storage)_. Artinya, file yang disimpan di S3 akan diperlakukan sebagai sebuah objek yang utuh.

Ketahuilah! Amazon S3 dapat menampung segala jenis file, baik itu video, gambar, data backup, bahkan konten web statis (HTML, CSS, dll). Nah, karena konten website itu dapat terdiri dari beberapa file, layanan Amazon S3 merupakan pilihan yang ideal sebagai langkah awal dalam perjalanan cloud kita di AWS.  
  
Amazon S3 memudahkan kita untuk meng-hosting website startup warung kopi tanpa perlu menjalankan, mengelola, dan me-_maintain_ server. Ingat, website statis memiliki beberapa limitasi. Namun, ini merupakan permulaan yang baik untuk mempelajari arsitektur di AWS, sesuai dengan nama modulnya yakni Arsitektur Tersederhana.

-   Amazon S3 adalah layanan penyimpanan tingkat objek (_object level storage_). Ini berarti, jika kita ingin mengubah sebagian kecil isi dalam sebuah file (misalnya dokumen _word_), kita harus mengunggah keseluruhan file itu kembali ke _S3 bucket_.

-   Tidak ada limitasi dalam ukuran bucket. Kita bisa menyimpan data sebanyak yang kita mau, akan tetapi ukuran maksimum untuk masing-masing objek adalah 5 TB.

-   Untuk mencapai daya tahan yang tinggi (_high durability_), data akan disimpan dan direplikasi ke lebih dari satu lokasi data center dalam satu AWS region. Hal ini membuat Amazon S3 sangat andal dan memiliki daya tahan (_durability_) 99.999999999 persen.

