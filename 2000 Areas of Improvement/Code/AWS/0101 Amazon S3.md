---
created: Wednesday, December 21st 2022 - 07.55
updated: Wednesday, December 21st 2022 - 07.55
---
## Pengenalan Amazon S3

Amazon Simple Storage Service (S3) adalah layanan dari AWS untuk menyimpan file berbasis objek _(object storage)_. Artinya, file yang disimpan di S3 akan diperlakukan sebagai sebuah objek yang utuh.

Ketahuilah! Amazon S3 dapat menampung segala jenis file, baik itu video, gambar, data backup, bahkan konten web statis (HTML, CSS, dll). Nah, karena konten website itu dapat terdiri dari beberapa file, layanan Amazon S3 merupakan pilihan yang ideal sebagai langkah awal dalam perjalanan cloud kita di AWS.  
  
Amazon S3 memudahkan kita untuk meng-hosting website startup warung kopi tanpa perlu menjalankan, mengelola, dan me-_maintain_ server. Ingat, website statis memiliki beberapa limitasi. Namun, ini merupakan permulaan yang baik untuk mempelajari arsitektur di AWS, sesuai dengan nama modulnya yakni Arsitektur Tersederhana.

![[Pasted image 20221221080241.png]]

-   Amazon S3 adalah layanan penyimpanan tingkat objek (_object level storage_). Ini berarti, jika kita ingin mengubah sebagian kecil isi dalam sebuah file (misalnya dokumen _word_), kita harus mengunggah keseluruhan file itu kembali ke _S3 bucket_.

-   Tidak ada limitasi dalam ukuran bucket. Kita bisa menyimpan data sebanyak yang kita mau, akan tetapi ukuran maksimum untuk masing-masing objek adalah 5 TB.

-   Untuk mencapai daya tahan yang tinggi (_high durability_), data akan disimpan dan direplikasi ke lebih dari satu lokasi data center dalam satu AWS region. Hal ini membuat Amazon S3 sangat andal dan memiliki daya tahan (_durability_) 99.999999999 persen.

Amazon S3 juga memiliki fitur _event notifications_ yang memungkinkan kita untuk mendapatkan pemberitahuan saat ada sebuah kejadian misalnya ketika object diunggah atau dihapus dari sebuah bucket tertentu. Event notifications ini bisa dikirimkan ke kita atau digunakan untuk menjadi pemicu (_trigger_) sebuah proses lanjutan, misalnya eksekusi AWS Lambda function.

Kita bisa mengakses Amazon S3 dari berbagai metode: AWS Management Console atau melalui akses terprogram dengan cara CLI (_Command Line Interface_), SDK (_Software Development Kit_), dan solusi pihak ketiga yang memanfaatkan API/SDK.

Amazon S3 juga memiliki fitur _storage class analysis_ yang akan sangat membantu kita dalam menganalisis pola akses objek di S3 bucket. Fitur ini secara otomatis mengidentifikasi apakah objek di dalam _bucket_ sering diakses atau tidak. Lalu dengan _lifecycle policy_, objek-objek di dalam bucket dapat dipindahkan ke storage class yang lebih sesuai.

Salah satu contohnya adalah memindahkan suatu objek ke storage class yang jarang diakses alias Amazon S3 Standard-Infrequent Access (Amazon S3 Standard-IA). Kita bisa mengonfigurasi kebijakan storage class analysis untuk memonitor objek di dalam bucket berdasarkan prefiks ataupun _object tag_.

Setelah pola _infrequent access_ (akses yang jarang) didapatkan, Anda dapat dengan mudah membuat _lifecycle age policy_ yang baru berdasarkan hasil analisisnya. Storage class analysis juga menyajikan visualisasi harian dari penggunaan penyimpanan Anda di AWS Management Console. Bahkan, Anda dapat mengekspornya ke S3 bucket untuk kemudian dianalisis menggunakan alat _business intelligence_ (kecerdasan bisnis) pilihan Anda, seperti Amazon QuickSight.

Seperti yang sudah kita bahas sebelumnya, hosting website statis hanyalah salah satu contoh penggunaan dari Amazon S3. Ada beberapa kasus penggunaan S3 yang layak Anda lihat. Mari kita bahas satu per satu dalam bentuk pembahasan kasus.