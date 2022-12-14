---
created: Thursday, December 15th 2022 - 06.07
updated: Thursday, December 15th 2022 - 06.07
---
Sebelum kita memahami tentang Open Close Principle, perhatikan contoh kasus perhitungan biaya admin (admin fee) dari berbagai jenis Bioskop ini. Terdapat berbagai jenis bioskop dengan fasilitas dan biaya admin yang berbeda-beda. Bioskop tersebut dimodelkan menjadi class Cinema, sedangkan perhitungan biaya admin dilakukan pada class CinemaCalculations.

![[Pasted image 20221215060508.png]]

```JS
class CinemaCalculations {
  calculateAdminFee(cinema) {
    if (cinema instanceof StandardCinema) {
      return (cinema.price * 10) / 100;
    }
 
    if (cinema instanceof DeluxeCinema) {
      return (cinema.price * 12) / 100;
    }
 
    if (cinema instanceof PremiumCinema) {
      return (cinema.price * 20) / 100;
    }
 
    return 0;
  }
```

Class Cinema adalah sebuah class yang dapat di-extend oleh berbagai jenis cinema:

```JS
class Cinema {
  constructor(price) {
    this.price = price;
  }
}
 
class StandardCinema extends Cinema {}
 
class DeluxeCinema extends Cinema {}
 
class PremiumCinema extends Cinema {}
```

Berdasarkan kode pada class CinemaCalculations, untuk mendapatkan perhitungan admin fee dilakukan operasi percabangan if else yang mengecek masing-masing jenis cinema. Pada kasus ini, nilai admin fee dari masing-masing cinema berbeda yang diurutkan dari standard hingga premium. Semakin mewah fasilitas cinema tersebut (termewah adalah premium), maka biaya admin fee semakin besar. 

Lalu, bagaimana jika ada jenis cinema baru? Untuk menambahkan cinema baru, kita perlu menambahkan else if lagi di percabangan calculateAdminFee. Semakin banyak jenis cinema-nya, maka percabangan if else-nya akan semakin bertambah, tentu ini menjadi problem karena kelas CinemaCalculation akan terus perlu diubah.

Sekarang, mari kita terapkan prinsip dari Open Close Principle untuk menyederhanakan kasus ini:

![[Pasted image 20221215060547.png]]

```JS
class Cinema {
  constructor(price) {
    if (this.constructor.name === 'Cinema') {
      throw new Error(`${this.constructor.name} is abstract class!`);
    }
 
    this.price = price;
  }
 
  calculateAdminFee() {
    throw new Error('Method not implemented!');
  }
}
 
class StandardCinema extends Cinema {
  calculateAdminFee() {
    return (this.price * 10) / 100;
  }
}
 
class DeluxeCinema extends Cinema {
  calculateAdminFee() {
    return (this.price * 12) / 100;
  }
}
 
class PremiumCinema extends Cinema {
  calculateAdminFee() {
    return (this.price * 20) / 100;
  }
}
```

Dengan menerapkan OCP (Open Close Principle), kita dapat mengubah class cinema menjadi abstract class. Di dalamnya terdapat abstract function calculateAdminFee() yang akan mengembalikan nilai admin fee. Jadi, perhitungan admin fee diletakkan pada masing-masing jenis cinema, dalam hal ini dimodelkan dalam bentuk class Cinema yang berbeda seperti StandardCinema, DeluxeCinema, dan PremiumCinema. Sehingga, seluruh class akan lebih mudah untuk ekstensi dengan class Cinema. Tentu akan lebih mudah jika kita ingin menambahkan cinema baru. Contohnya, ada jenis cinema baru yang bernama CoupleCinema, maka kita tinggal membuat class baru seperti ini:

```JS
class CoupleCinema extends Cinema {
  calculateAdminFee() {
    return (this.price * 15) / 100;
  }
}
```

Lebih mudah dan rapi kan, daripada menggunakan if else.

Jika kita ingin membuat class cinema maka contoh kode programnya adalah seperti berikut:

```JS
const main = () => {
  const standardCinema = new StandardCinema(100);
  const adminFee = standardCinema.calculateAdminFee();
  console.log(adminFee); // output: 10
};
 
main();
```

Dari kode di atas kita melihat bahwa jika ada perubahan perhitungan admin fee atau perhitungan lainnya, tidak perlu lagi mengubah/modifikasi class CinemaCalculations. Sesuai dengan prinsipnya yaitu “open for extensions close for modifications”, cukup dengan extend method dari abstract class tanpa modifikasi isi class tersebut. 

Berikut ini adalah perbandingan studi kasus cinema sebelum menerapkan OCP dan juga setelah menerapkannya:

![[Pasted image 20221215060652.png]]

