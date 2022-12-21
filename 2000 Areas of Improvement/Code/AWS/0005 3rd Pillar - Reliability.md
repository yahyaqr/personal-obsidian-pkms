---
created: Tuesday, December 20th 2022 - 20.11
updated: Tuesday, December 20th 2022 - 20.11
---
### Reliability

Pilar reliability membicarakan tentang kemampuan sebuah sistem untuk pulih dari gangguan, secara dinamis memperoleh dan mengalokasi sumber daya komputasi demi memenuhi permintaan, dan memitigasi gangguan seperti kesalahan konfigurasi atau gangguan lain yang sifatnya temporer.

Tahukah Anda? Tidaklah mudah untuk memastikan keandalan sebuah sistem di lingkungan data center tradisional. Masalah bisa saja terjadi dari mana saja, seperti tidak adanya _redundancy_ di sistem kita, tak hadirnya automasi, dan tiadanya elastisitas. 

Dengan mengaplikasikan prinsip-prinsip dari pilar Reliability, kita bisa mencegah munculnya masalah-masalah di atas. Maka dari itu, desainlah arsitektur sistem Anda dengan memperhatikan hal-hal seperti _High-Availability, Fault Tolerance_, dan _Redundancy_.

Ada 5 prinsip desain untuk mencapai reliability/keandalan di cloud:

-   **Pemulihan otomatis ketika terjadi kegagalan**  
    Pantaulah beban kerja (workload) Anda agar sesuai dengan KPI (Key Performance Indicator). Anda dapat men-trigger automasi saat ambang batas terlewati. KPI ini harus menjadi ukuran nilai bisnis, bukan aspek teknis pengoperasian layanan.  
      
    Ini memungkinkan Anda mendapatkan pemberitahuan secara otomatis dan melacak kegagalan untuk proses pemulihan otomatis serta perbaikan kegagalan.  
      
    Bahkan dengan automasi yang lebih canggih, Anda dapat mengantisipasi dan memulihkan kegagalan sebelum terjadi.  
      
-   **Uji prosedur pemulihan**  
    Di lingkungan on-premise, pengujian sering dilakukan untuk membuktikan beban kerja berfungsi dalam skenario tertentu. Dan biasanya, pengujian tidak digunakan untuk memvalidasi strategi pemulihan.  
      
    Sedangkan di cloud, Anda dapat menguji bagaimana kegagalan bisa terjadi pada beban kerja serta memvalidasi prosedur pemulihan yang Anda buat. Anda juga dapat menggunakan automasi untuk mensimulasikan berbagai kegagalan atau membuat ulang skenario yang menyebabkan kegagalan sebelumnya.  
      
    Pendekatan ini memperlihatkan alur kegagalan yang dapat Anda uji dan perbaiki sebelum skenario kegagalan sesungguhnya terjadi sehingga dapat mengurangi risiko.  
      
-   **Lakukan horizontal scaling untuk meningkatkan ketersediaan beban kerja**  
    Gantilah satu sumber daya besar dengan beberapa sumber daya kecil guna mengurangi dampak kegagalan tunggal pada keseluruhan beban kerja. Distribusikan permintaan di beberapa sumber daya yang lebih kecil untuk memastikan permintaan tersebut tidak memiliki titik kegagalan yang sama.  
      
-   **Berhenti memperkirakan kebutuhan kapasitas**  
    Penyebab umum terjadinya kegagalan dalam beban kerja di on-premise adalah resource saturation (kejenuhan sumber daya), yakni saat permintaan yang ditempatkan pada beban kerja melebihi kapasitas beban kerja tersebut (ini sering kali menjadi tujuan serangan denial of service alias DoS).  
      
    Di cloud, Anda dapat memantau permintaan dan pemanfaatan beban kerja, serta mengotomatiskan penambahan atau penghapusan resource. Dengan begitu, Anda dapat mempertahankan tingkat optimal guna memenuhi permintaan tanpa kelebihan atau kekurangan penyediaan. Meski masih ada batasan, tetapi beberapa kuota dapat dikontrol dan dikelola.  
      
-   **Kelola perubahan menggunakan automasi**  
    Perubahan pada infrastruktur Anda harus dilakukan menggunakan automasi. Perubahan yang perlu dikelola termasuk perubahan otomatisasi yang nantinya dapat dilacak dan ditinjau.
    
Untuk petunjuk implementasi secara lebih mendetail, Anda bisa menemukannya di whitepaper untuk pilar Reliability di tautan berikut ini [Reliability Pillar - AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html).