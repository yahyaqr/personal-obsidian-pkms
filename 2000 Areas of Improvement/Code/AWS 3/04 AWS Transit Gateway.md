## AWS Transit Gateway

AWS Transit Gateway dapat mengoneksikan VPC dengan on-premise melalui hub terpusat sebagai layanan yang terkelola sepenuhnya yang tanpa mewajibkan kita untuk menyediakan peralatan khusus di on-premise. AWS-lah yang akan mengelola ketersediaan dan skalabilitas jaringan tersebut untuk Anda.

![[Pasted image 20230105162658.png]]

AWS Transit Gateway memungkinkan Anda untuk menghubungkan ribuan VPC. Kita dapat memasang semua konektivitas hybrid (VPN dan juga koneksi Direct Connect) ke satu Transit Gateway, di mana ia akan mengonsolidasi dan mengontrol seluruh konfigurasi perutean kita secara terpusat. 

Transit Gateway juga mengontrol bagaimana lalu lintas diarahkan di antara semua jaringan yang terhubung menggunakan route table. Transit Gateway menggunakan topologi hub-and-spoke, yakni model jaringan yang memiliki komponen terpusat dan menghubungkan beberapa jaringan di sekitarnya. Model _hub dan spoke_ ini menyederhanakan manajemen dan mengurangi biaya operasional karena VPC hanya terhubung ke Transit Gateway untuk mendapatkan akses ke jaringan yang terhubung.

  

### Contoh Implementasi Transit Gateway

1.  **Komunikasi antar-VPC**  
    ![[Pasted image 20230105162751.png]]
    Gambar di atas menunjukkan bahwa dengan menggunakan Transit Gateway, kita dapat menyederhanakan konfigurasi Route Table pada setiap VPC. Dengan menggunakan Transit Gateway, kita hanya mendefinisikan rute ke Transit Gateway pada masing-masing VPC. Selanjutnya, kita mendefinisikan route ke masing-masing VPC di dalam Route Table Transit Gateway.
    
2.  **Komunikasi terpisah antar masing-masing VPC dan akses VPN**  
    Skenario yang umum adalah memiliki akses penuh ke lingkungan kita dari sumber VPN. Namun dalam skenario kedua, kita tidak ingin VPC dapat berbicara satu sama lain.  
    ![[Pasted image 20230105162741.png]]
    Untuk mencapai skenario ini, kita memerlukan dua Route Table di dalam Transit Gateway dengan fungsi sebagai berikut:
    
    1.  Route Table warna hijau memberitahukan jalur default ke seluruh VPC yang mengarah ke VPN gateway.
    2.  Route Table warna merah selanjutnya memberitahukan jalur ke CIDR block masing-masing VPC.