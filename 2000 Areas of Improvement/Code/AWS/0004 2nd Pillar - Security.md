---
created: Tuesday, December 20th 2022 - 20.10
updated: Tuesday, December 20th 2022 - 20.10
---
### Security

Pilar Security (Keamanan) mencakup mengenai bagaimana melindungi informasi dan memitigasi kerusakan atau kerugian. Arsitektur Anda akan memiliki perlindungan yang jauh lebih baik dengan mengimplementasikan langkah-langkah keamanan dasar, misalnya mengaktifkan _traceability_ (keterlacakan), mengaplikasikan keamanan di seluruh lapisan, mengotomatiskan praktik terbaik keamanan, dan melindungi data baik _in-transit_ maupun _at rest_.

Berikut penjelasan detail prinsip desain pada pilar Security:

-   **Terapkan fondasi identitas yang kuat**  
    Terapkan prinsip _least privilege_ (hak akses secukupnya/sesuai kebutuhan) dan pemisahan tugas dengan otorisasi yang sesuai untuk setiap interaksi dengan sumber daya AWS Anda. Selain itu, Anda juga perlu memusatkan manajemen identitas yang bertujuan untuk menghilangkan ketergantungan pada kredensial statis jangka panjang.  
      
-   **Aktifkan keterlacakan (_Enabling traceability_)**  
    Pantau, beri peringatan, serta audit tindakan dan perubahan pada lingkungan Anda secara real time. Integrasikan pengumpulan log dan metrik dengan sistem untuk menyelidiki sekaligus mengambil tindakan secara otomatis.  
      
-   **Terapkan keamanan pada semua lapisan**  
    Terapkan pendekatan pertahanan yang mendalam dengan beberapa kontrol keamanan untuk semua lapisan, seperti edge network, VPC, load balancing, semua instance dan layanan komputasi, sistem operasi, aplikasi, dan kode.  
      
-   **Otomatiskan praktik terbaik untuk keamanan**  
    Mekanisme keamanan berbasis perangkat lunak dapat secara otomatis meningkatkan kemampuan Anda untuk meningkatkan skala secara aman, lebih cepat, dan hemat biaya.  
      
    Buatlah arsitektur yang aman, termasuk penerapan kontrol yang ditentukan dan dikelola sebagai kode dalam template yang menggunakan version control.  
      
-   **Lindungi data in-transit dan at rest**  
    Klasifikasikan data Anda ke dalam tingkat sensitivitas dan mekanisme penggunaan, seperti enkripsi, tokenisasi, dan kontrol akses jika sesuai.  
      
-   **Jauhkan orang dari data**  
    Gunakan mekanisme dan alat untuk mengurangi atau meniadakan kebutuhan akan akses langsung atau pemrosesan data secara manual. Dengan begitu, Anda dapat mengurangi risiko kesalahan penanganan, modifikasi, dan _human error_ saat berurusan dengan data sensitif.  
      
-   **Persiapkan diri Anda untuk insiden keamanan**  
    Anda perlu bersiap untuk suatu insiden keamanan dengan memiliki manajemen insiden dan kebijakan serta proses investigasi yang sejalan dengan kebutuhan organisasi Anda.  
      
    Jalankan simulasi respons insiden dan gunakan alat dengan automasi untuk meningkatkan kecepatan deteksi, investigasi, dan pemulihan Anda.  
      

Untuk petunjuk implementasi secara lebih mendetail, Anda bisa menemukannya di whitepaper untuk pilar Security di tautan berikut ini [Security Pillar - AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/welcome.html).