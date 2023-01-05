---
created: Thursday, January 5th 2023 - 16.10
updated: Thursday, January 5th 2023 - 16.10
---
## Keamanan Jaringan

Saat menggunakan VPC, keamanan jaringan ditangani oleh dua layanan AWS, yaitu Security Group dan Network ACL. Sebelum kita membahas keduanya lebih lanjut, silakan pelajari tabel di bawah ini: 

![[Pasted image 20230105161202.png]]
  

### Security Group

Security Group bertindak sebagai firewall virtual untuk instance yang dapat mengontrol lalu lintas masuk dan keluar. Saat meluncurkan sebuah instance di VPC, kita dapat menetapkan hingga 5 Security Group untuk instance tersebut.

Security Group bekerja di tingkat instance, bukan di tingkat subnet. Oleh karena itu, setiap instance dalam subnet di VPC kita dapat ditetapkan ke kumpulan Security Group yang berbeda.

Kita dapat mendefinisikan rules untuk Security Group yang melakukan pemeriksaan berdasarkan arah (inbound/outbound), protokol dan port, serta sumbernya. Gambar berikut menunjukkan contoh konfigurasi dari Security Group:

![[Pasted image 20230105161215.png]]

Meski kita bisa mendefinisikan Inbound/Outbound rules, praktik yang umum dilakukan oleh pengguna AWS adalah dengan mendefinisikan hanya Inbound rules saja untuk setiap Tier dari aplikasi atau sistem yang ada di AWS VPC.

**PENTING!** Koneksi dan data yang berjalan dari/ke instance EC2 akan diperiksa terhadap seluruh rules yang didefinisikan dalam Security Group yang diaplikasikan ke instance tersebut.  
  

### Network Access Control List (Network ACL)

Network ACL adalah lapisan keamanan opsional yang bertindak sebagai firewall untuk mengontrol lalu lintas masuk dan keluar dari subnet. Kita dapat mengaitkan/mengasosiasikan beberapa subnet dengan satu Network ACL. Namun, subnet hanya dapat dikaitkan/diasosiasikan dengan satu Network ACL pada satu waktu.

Network ACL bekerja di tingkat subnet dan didefinisikan di tingkat VPC. Di tingkat VPC, terdapat Network ACL default yang akan diaplikasikan ke seluruh subnet yang tidak memiliki Network ACL custom. Berikut adalah contoh konfigurasi dari Network ACL:

![[Pasted image 20230105161254.png]]

Coba kita pikirkan, rules mana yang memperbolehkan seluruh akses terbuka? Apa yang akan terjadi jika rules tersebut dihapus?