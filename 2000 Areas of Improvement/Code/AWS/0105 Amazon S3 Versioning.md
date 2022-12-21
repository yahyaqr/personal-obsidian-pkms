---
created: Wednesday, December 21st 2022 - 08.22
updated: Wednesday, December 21st 2022 - 08.22
---
## Versioning di Amazon S3

Sebelum masuk ke pembahasan, tahukah Anda apa itu versioning? Versioning adalah pembuatan dan pengelolaan beberapa rilis dari suatu produk, yang mana memiliki fungsi umum yang sama namun telah dilakukan perbaikan, peningkatan, atau penyesuaian.

Di Amazon S3, versioning adalah cara untuk menyimpan beberapa versi objek dalam bucket yang sama. Sehingga ketika ada objek yang tertimpa (_override_) baik sengaja atau tidak, Anda dapat memulihkan setiap versi dari setiap objek yang disimpan di bucket Anda.

Misalnya, Anda memiliki website statis untuk startup warung kopi yang dihosting di Amazon S3. Karena suatu kebutuhan, Anda ingin memperbarui website tersebut untuk menambahkan logo. Tapi sayangnya, proses update tersebut malah menimbulkan eror.

Nah, jika Anda mengaktifkan versioning di Amazon S3, maka tak perlu khawatir. Anda masih bisa mengembalikan (_restore_) versi sebelumnya dari website tersebut. Dengan begitu, Anda bisa memperbaiki eror dan meng-hosting kembali website tersebut dengan aman. Mari kita pelajari tentang versioning di S3 lebih lanjut!

Bucket yang mendukung versioning memungkinkan Anda untuk memulihkan objek dari penghapusan atau overwrite (penimpaan) yang terjadi secara tidak disengaja. Sebagai contoh:

-   Jika Anda menghapus objek, aksi penghapusan ini tidak akan permanen, melainkan Amazon S3 akan menyisipkan penanda hapus (delete marker) yang menjadi versi objek saat ini. Anda selalu dapat memulihkan versi sebelumnya.

-   Jika Anda menimpa objek, Amazon S3 akan menghasilkan versi objek baru di S3 bucket dan menjaga versi objek sebelumnya. Anda selalu dapat memulihkan versi sebelumnya.

![[Pasted image 20221221082128.png]]

Amazon S3 Bucket dapat berada di salah satu dari tiga status: _unversioned_ (default), versioning-enabled, atau versioning-suspended.

Penting! Setelah Anda mengaktifkan fitur versioning, bucket tidak akan pernah bisa kembali ke status unversioned. Namun, Anda dapat menangguhkan (suspend) pembuatan versi pada bucket tersebut.

Status pembuatan versi berlaku untuk semua objek dalam S3 bucket dan tidak bisa diberlakukan untuk beberapa objek saja. Saat pertama kali Anda mengaktifkan bucket untuk pembuatan versi, objek di dalamnya akan selalu dibuat versinya dan diberi version ID yang unik. Perhatikan hal-hal berikut:

Objek yang disimpan di bucket sebelum Anda menyetel status pembuatan versi, memiliki version ID “null”. Jika Anda mengaktifkan pembuatan versi, objek yang ada di bucket Anda tidak berubah. Melainkan, yang berubah adalah bagaimana Amazon S3 menangani objek untuk permintaan di masa mendatang. Jika tertarik untuk belajar lebih mendalam mengenai ini, Anda dapat membaca detail lengkapnya di tautan ini [Working with objects in a versioning-enabled bucket](https://docs.aws.amazon.com/AmazonS3/latest/userguide/manage-objects-versioned-bucket.html).

Pemilik bucket (atau pengguna dengan izin yang sesuai) dapat menangguhkan (suspend) pembuatan versi untuk memberhentikan fitur object versioning. Jika Anda menangguhkan pembuatan versi, objek yang ada di bucket Anda tidak berubah. Melainkan, yang berubah adalah bagaimana Amazon S3 menangani objek untuk permintaan setelah _suspension_ terhadap _bucket_ diaktifkan.