---
created: Thursday, January 5th 2023 - 16.24
updated: Thursday, January 5th 2023 - 16.24
---
## AWS Direct Connect (DX)

Untuk Anda yang membutuhkan koneksi yang lebih cepat dan lebih aman dibandingkan koneksi VPN, AWS menyediakan solusi Direct Connect (DX). AWS DX menyediakan koneksi langsung antara data center on-premise Anda, terhubung dengan Direct Connect partner, dan kemudian langsung terhubung dengan data center AWS sehingga jalur data yang disediakan jauh lebih besar mulai dari 1 sampai 10 Gbps.

AWS Direct Connect (DX) adalah solusi yang dapat melampaui kecepatan dari konektivitas internet. Anda bisa mendapatkan skala akses, kecepatan, dan konsistensi ke jaringan AWS untuk aplikasi penting ini. 

DX tidak melibatkan internet; sebaliknya, ia menggunakan koneksi jaringan pribadi terdedikasi antara solusi on-premise, DX partner, dan AWS. Oke, sekarang mari kita lihat beberapa kasus penggunaan untuk layanan AWS Direct Connect. 

  

### Skenario Penggunaan Direct Connect

Agar memudahkan pembahasan kita, silakan amati gambar berikut yang menunjukkan dua skenario penggunaan Direct Connect.

1.  Menggunakan Direct Connect untuk menghubungkan On-Premise network dengan AWS VPC.  
    ![[Pasted image 20230105162406.png]]
    

2.  Menggunakan Direct Connect dengan tambahan dukungan VPN.  
    ![[Pasted image 20230105162415.png]]
    

Untuk menggunakan AWS Direct Connect, jaringan kita harus memenuhi salah satu dari ketentuan berikut:

-   Jaringan kita terletak di Region yang memiliki layanan AWS Direct Connect. 
-   Anda bekerja sama dengan mitra AWS Direct Connect yang merupakan anggota AWS Partner Network (APN). 
-   Anda bekerja sama dengan penyedia layanan independen untuk terhubung ke AWS Direct Connect.