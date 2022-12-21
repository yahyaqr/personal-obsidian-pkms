---
created: Wednesday, December 21st 2022 - 08.20
updated: Wednesday, December 21st 2022 - 08.20
---
### Kasus Penggunaan 4: Media Penyimpanan Data Backup

Karena sifatnya yang sangat _durable_ dan scalable, Amazon S3 juga berfungsi dengan baik sebagai alat pencadangan (_backup_) dan pengarsipan. Selain itu, Anda dapat memindahkan data yang sifatnya untuk jangka panjang ke Amazon Glacier melalui penggunaan lifecycle policies. Untuk menjaga kehilangan/korupsi data, Anda dapat menggunakan _cross-region replication_ untuk menyalin objek secara otomatis ke Amazon S3 bucket lainnya di region berbeda.

![[Pasted image 20221221081859.png]]

Tahukah Anda? Jumlah data yang dihasilkan di on-premise kian bertambah, begitu pula permintaan untuk penyimpanan arsip cadangan. 

Jika Anda mengikuti metodologi pencadangan secara umum dan memiliki beberapa cadangan di lokasi yang berbeda, maka kemungkinan besar Anda memiliki banyak data yang tersimpan di disk storage atau physical tape archives (arsip pita fisik). Melacak beberapa salinan data lokal dapat menjadi tantangan dan sering kali menimbulkan biaya yang signifikan, baik dalam hal waktu maupun biaya.

AWS Cloud memberikan alternatif menarik untuk penyimpanan backup di on-premise atau physical tape archives. Misalnya, Amazon S3 Glacier Deep Archive memberikan daya tahan sebelas 9 (99.999999999%) dengan harga sekitar $1 per TB / bulan. 

Dengan AWS Cloud, tidak ada perangkat keras penyimpanan yang harus Anda kelola, tidak ada tape yang harus Anda kirim ke luar lokasi, dan tidak perlu mengeluarkan biaya ketika ada hardware yang perlu diperbaharui dalam sebuah siklus. Bahkan, Anda akan mendapatkan semua keuntungan di sisi skalabilitas dan daya tahan cloud, dengan hanya membayar sesuai yang Anda gunakan.