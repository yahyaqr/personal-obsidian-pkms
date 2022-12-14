---
created: Thursday, December 15th 2022 - 05.41
updated: Thursday, December 15th 2022 - 05.41
---
Sama seperti contoh kasus sebelum-sebelumnya, kita akan memulai dengan skenario yang menyalahi aturan dalam penerapan. Lebih lanjut, kita akan coba membahas bagaimana mengubah penerapannya agar sesuai dengan prinsip Liskov’s substitution. Untuk itu, berikut adalah contoh diagram dan kode dari skenario yang akan kita gunakan:

```JS
class Product {
  constructor() {
    if (this.constructor.name === 'Product') {
      throw new Error(`${this.constructor.name} is abstract class!`);
    }
  }
 
  getName() {
    throw new Error('Method not implemented!');
  }
 
  getExpiredDate() {
    throw new Error('Method not implemented!');
  }
 
  /**
   * Function to get all of information about product
   */
  getProductInfo() {
    // some magic code
  }
}
 
class Vegetable extends Product {
  getName() {
    return 'Broccoli';
  }
 
  getExpiredDate() {
    return new Date();
  }
}
```

Pada contoh kode di atas kita memiliki sebuah kelas _abstract_ bernama Product yang di dalamnya terdapat pula beberapa member _abstract_ . Kelas tersebut diwariskan oleh kelas lain yaitu kelas Vegetable. Untuk saat ini, kelas tersebut dapat berjalan dengan baik sesuai dengan fungsinya.

Selanjutnya kita membutuhkan sebuah kelas produk baru. Katakanlah produk smartphone. Untuk itu, kita tinggal membuat kelas baru yang mewarisi kelas Product karena kelas tersebut merupakan abstraksi dari sebuah kelas produk. Kurang lebih diagram dan kodenya akan seperti berikut:  
[![dos:42bcedd77a904cf691bf21865f93d90c20210921112507.png](https://dicoding-web-img.sgp1.cdn.digitaloceanspaces.com/original/academy/dos:42bcedd77a904cf691bf21865f93d90c20210921112507.png)](https://www.dicoding.com/academies/169/tutorials/7825?from=7824# "dos:42bcedd77a904cf691bf21865f93d90c20210921112507.png")

```JS
class Product {
    constructor() {
        if (this.constructor.name === 'Product') {
            throw new Error(`${this.constructor.name} is abstract class!`);
        }
    }
 
    getName() {
        throw new Error('Method not implemented!');
    }
 
    /**
     * Function to get all of information about product
     */
    getProductInfo() {
        // some magic code
    }
 
    getExpiredDate() {
        throw new Error('Method not implemented!');
    }
}
 
class Vegetable extends Product {
    getName() {
        return 'Broccoli';
    }
 
    getExpiredDate() {
        return new Date();
    }
}
 
class Smartphone extends Product {
    getName() {
        return 'Samsung S10+ Special Edition';
    }
 
    getExpiredDate() {
        return new Date(); // ?????
    }
}
```

Pada kode di atas hubungan antara kelas Product dan kelas Vegetable sudah benar dan dapat berjalan dengan baik. Tapi jika kita perhatikan pada kelas Smartphone, di dalamnya terdapat member yang nilainya adalah masa kedaluwarsa produk yang harus kita tentukan. Namun seperti yang kita ketahui, sebuah smartphone tidaklah mempunyai masa kedaluwarsa. Dalam kasus ini kelas Product menjadi tidak relevan untuk diwariskan ke kelas Smartphone dan ini tentunya melanggar aturan SubClass yang sudah kita pelajari di modul sebelumnya.

Untuk mengatasi kasus di atas, kita perlu melakukan substitusi fungsi yang tidak relevan tersebut ke dalam kelas abstraksi sendiri dan diwariskan pada kelas yang relevan. Namun, Perubahan ini tetap menjadikan kelas Product sebagai SuperClass dari hirarki yang ada saat ini. Kurang lebih perubahannya akan seperti berikut:  
  
[![dos:0c90969d88471ecdc4e83fbb771f493220210921112534.png](https://dicoding-web-img.sgp1.cdn.digitaloceanspaces.com/original/academy/dos:0c90969d88471ecdc4e83fbb771f493220210921112534.png)](https://www.dicoding.com/academies/169/tutorials/7825?from=7824# "dos:0c90969d88471ecdc4e83fbb771f493220210921112534.png")

```JS
class Product {
    constructor() {
        if (this.constructor.name === 'Product') {
            throw new Error(`${this.constructor.name} is abstract class!`);
        }
    }
 
    getName() {
        throw new Error('Method not implemented!');
    }
 
    /**
     * Function to get all of information about product
     */
    getProductInfo() {
        // some magic code
    }
}
 
class FoodProduct extends Product {
    constructor() {
        super();
 
        if (this.constructor.name === 'FoodProduct') {
            throw new Error(`${this.constructor.name} is abstract class!`);
        }
    }
 
    getExpiredDate() {
        throw new Error('Method not implemented!');
    }
}
 
class Vegetable extends FoodProduct {
    getExpiredDate() {
        return new Date();
    }
 
    getName() {
        return 'Broccoli';
    }
}
 
class Smartphone extends Product{
    getName() {
        return 'Samsung S10+ Limited Edition';
    }
}
```

Dengan perubahan kode seperti di atas, kita sudah memenuhi aturan yang ada. Mudah bukan? Liskov’s Substitution principle merupakan prinsip yang dapat meningkatkan design dari sistem yang kita kembangkan. Sehingga ketergantungan antar klien dapat disubstitusikan tanpa klien tahu perubahan yang ada.

Berikut ini adalah perbandingan studi kasus Product sebelum menerapkan LSP dan juga setelah menerapkannya:

[![dos:77f743e4b1fe43f96c74066057e9000820210921112704.png](https://dicoding-web-img.sgp1.cdn.digitaloceanspaces.com/original/academy/dos:77f743e4b1fe43f96c74066057e9000820210921112704.png)](https://www.dicoding.com/academies/169/tutorials/7825?from=7824# "dos:77f743e4b1fe43f96c74066057e9000820210921112704.png")

Sudah paham belum tentang penggunaannya? Jika belum, silakan tanya di forum diskusi kelas ya. Ayok kita lanjut  ke modul berikutnya.