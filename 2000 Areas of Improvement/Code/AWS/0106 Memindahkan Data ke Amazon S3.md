---
created: Wednesday, December 21st 2022 - 08.26
updated: Wednesday, December 21st 2022 - 08.26
---
## Memindahkan Data ke Amazon S3

Masihkah Anda menyimpan data secara lokal di komputer atau laptop? Jika jawabannya “masih”, lalu bagaimana jika Anda membutuhkan data itu sesegera mungkin namun Anda tak membawa laptop atau tak sedang berada di depan komputer? Tentu, itu akan menyulitkan.

Tak hanya itu, masih banyak alasan lain mengapa Anda harus memindahkan data ke cloud, terutama Amazon S3, seperti biaya yang murah, aman, dan awet.

Saat Anda mengunggah file ke Amazon S3, file tersebut akan disimpan sebagai objek S3. Objek terdiri dari file data dan metadata yang memberikan gambaran mengenai objek tersebut. Sebuah bucket dapat menampung objek dalam jumlah yang tak terbatas.

Anda dapat memindahkan data ke Amazon S3 dengan beberapa cara yang berbeda:

-   **Transfer menggunakan AWS Management Console, AWS Command Line Interface (AWS CLI), atau API**   
    Jika Anda memiliki sejumlah kecil data atau data yang sudah ada di dalam jaringan AWS, Anda dapat mentransfernya ke Amazon S3 dengan mudah menggunakan console, CLI, atau API.  
      
-   **Unggah ke S3 bucket**  
    Anda dapat mengunggah semua jenis file—gambar, backup, data, film, dll—ke dalam S3 bucket. Ukuran maksimum file yang dapat Anda unggah dengan menggunakan Amazon S3 console adalah 160 GB. Jika menggunakan CLI atau API, Anda dapat memindahkan file dengan ukuran yang lebih besar.

-   **AWS DataSync**  
    AWS DataSync adalah layanan transfer data yang memudahkan Anda mengotomatiskan pemindahan data antara penyimpanan di on-premise dan layanan penyimpanan di AWS, seperti Amazon S3, Amazon Elastic File System (Amazon EFS), dan Amazon FSx (untuk Windows File Server file systems).  
      
-   **AWS Transfer for SFTP**  
    AWS Transfer for SFTP adalah layanan Secure File Transfer Protocol atau SFTP yang terkelola sepenuhnya dan sangat tersedia. Layanan ini memungkinkan aplikasi mentransfer file melalui protocol SFTP langsung ke Amazon S3.  

Selain itu, Anda juga dapat menggunakan metode _multipart upload_ yang memungkinkan Anda mengunggah objek berukuran besar secara konsisten di bagian yang dapat dikelola.

![[Pasted image 20221221082514.png]]

Proses ini melibatkan 3 langkah:

-   Mulai pengunggahan (_initiate_).
-   Unggah bagian objek (_upl__oad object parts_).
-   Selesaikan proses multipart upload (_complete_).

Setelah permintaan multipart upload selesai, Amazon S3 akan menyusun objek secara keseluruhan dari masing-masing bagian. Berikut adalah manfaat _multipart upload_ bagi Anda:

-   **Throughput yang lebih baik**  
    Anda dapat mengunggah bagian-bagian objek secara paralel untuk meningkatkan throughput.  
      
-   **Pemulihan yang cepat dari masalah jaringan**  
    Ukuran bagian objek yang lebih kecil meminimalkan dampak untuk mengulang proses unggahan yang gagal karena kesalahan jaringan.  
      
-   **Jeda dan lanjutkan unggahan objek**  
    Anda dapat mengunggah bagian objek dari waktu ke waktu. Setelah Anda memulai proses multipart upload, tidak akan ada nilai _expiry time_; Anda harus secara eksplisit menyelesaikan atau menghentikan proses tersebut.  
      
-   **Mulailah mengunggah sebelum Anda mengetahui ukuran objek akhir**  
    Dengan multipart upload, Anda dapat mengunggah objek saat membuatnya.  
      
-   **Unggah objek besar**  
    Dengan API multipart upload, Anda dapat mengunggah objek besar, bahkan hingga 5 TB.