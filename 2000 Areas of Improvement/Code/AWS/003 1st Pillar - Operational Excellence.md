---
created: Tuesday, December 20th 2022 - 20.09
updated: Tuesday, December 20th 2022 - 20.09
---
### Operational Excellence

Pilar ini membahas tentang kemampuan untuk mengoperasikan dan memonitor sistem demi memberikan nilai tambah bagi perusahaan serta menyempurnakan proses dan prosedur secara terus-menerus. 

Operational Excellence dilakukan sejak awal dan dilanjutkan secara terus-menerus sesuai perkembangan bisnis yang juga dinamis. Hal ini terutama ditunjukkan pada tiga hal di bawah ini, yaitu:

-   Menyelaraskan proses operasi dengan tujuan bisnis.
-   Membuat perubahan yang teratur, kecil, dan bertahap.
-   Belajar dari kejadian dan kegagalan operasional.

Berikut penjelasan detail dari prinsip pada pilar Operational Excellence:

-   **Gunakan kode untuk menjalankan operasi**  
    Di cloud, Anda bisa menerapkan disiplin teknik yang sama--yakni menggunakan code--dalam menjalankan operasinya. Anda dapat menentukan dan memperbaharui seluruh workload (beban kerja) infrastruktur maupun aplikasi melalui kode.  
      
    Dengan menggunakan kode dalam menjalankan operasi, Anda dapat mengautomasi operasi untuk dieksekusi berdasarkan sebuah _event_ (peristiwa). Hal ini tentu akan meminimalisir terjadinya _human error_ [[1]](https://docs.aws.amazon.com/wellarchitected/latest/framework/oe-design-principles.html).  
      
    
-   **Buatlah pembaruan yang sering, kecil, dan dapat diubah**  
    Rancanglah workload (beban kerja) yang dapat menerima pembaruan komponen secara teratur. Lakukan pembaruan sedikit demi sedikit dan pastikan pembaruannya dapat dibatalkan jika gagal (tanpa mengganggu jalannya operasional jika dimungkinkan).  
      
    
-   **Sering-seringlah memperbarui prosedur operasi**  
    Lakukan pembaruan pada prosedur operasi seiring dengan mengembangnya beban kerja Anda. Luangkan waktu untuk meninjau dan memvalidasi bahwa semua prosedur sudah efektif serta dipahami dan digunakan oleh tim terkait.  
      
    
-   **Mengantisipasi kegagalan**  
    Lakukan latihan “pra-mortem” untuk mengidentifikasi potensi sumber kegagalan sehingga dapat disingkirkan atau dikurangi.  
      
    Uji skenario kegagalan Anda dan validasikan dampaknya. Lalu, ujilah _response procedure_ (prosedur tanggapan) Anda untuk memastikan apakah sistem berjalan efektif? Apakah tim Anda terbiasa dengan pelaksanaannya? Selain itu, siapkan juga [Game Day](https://wa.aws.amazon.com/wat.concept.gameday.en.html) untuk menguji beban kerja dan respons tim terhadap simulasi _event_.  
      
    
-   **Belajar dari semua kegagalan operasional**  
    Tingkatkan sistem Anda melalui pembelajaran yang dipetik dari semua kejadian dan kegagalan operasional. Bagikan apa yang dipelajari di tim Anda ke seluruh organisasi.  
      
    

Jadi, pilar Operational Excellence ini memberikan prinsip desain, praktik terbaik, dan kumpulan pertanyaan terkait desain. Untuk petunjuk implementasi secara lebih mendetail, Anda bisa menemukannya di whitepaper untuk pilar Operational Excellence di tautan berikut ini [Operational Excellence Pillar - AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/operational-excellence-pillar/welcome.html).