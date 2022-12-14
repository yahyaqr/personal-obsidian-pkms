Untuk memahami Interface Segregation Principle, mari kita gunakan studi kasus  antara kendaraan sepeda motor dan mobil. Keduanya termasuk dalam jenis kendaraan, tetapi apakah keduanya memiliki fitur atau kelengkapan yang sama? Perhatikan contoh penerapan fitur pada sepeda motor dan mobil berikut. 

Pada sepeda motor dimodelkan sebagai class Motorcycle, sedangkan mobil dimodelkan sebagai class Car. Keduanya merupakan bagian dari interface VehicleInterface sebagai berikut:

![[Pasted image 20221215054900.png]]

```JS
class VehicleInterface {
  drive() {
    throw new Error('Method not implemented!');
  }
 
  stop() {
    throw new Error('Method not implemented!');
  }
 
  refuel() {
    throw new Error('Method not implemented!');
  }
 
  openDoors() {
    throw new Error('Method not Implemented!');
  }
}
 
class Motorcycle extends VehicleInterface {
  drive() {
    // implementation
  }
 
  stop() {
    // implementation
  }
 
  refuel() {
    // implementation
  }
 
  // pain point
  // Can not be implemented
  openDoors() {
 
  }
}
```

Di dalam interface Vehicle, terdapat beberapa function, di antaranya drive(), stop(), refuel(), dan openDoors(). Ketika class Motorcycle mengimplementasikan interface tersebut, maka seluruh function dari interface Vehicle akan ter-override di dalam classs Motorcycle. Namun, ada hal yang kurang tepat, yaitu terdapat function openDoors(), sementara kenyataannya motorcycle tersebut seharusnya tidak memiliki pintu (doors). Bagaimana kita dapat mengatasinya?

Caranya adalah dengan menerapkan Interface Segregation Principle. Kita perlu memisahkan function openDoors() ke dalam interface lain, kodenya akan menjadi seperti ini:

```JS
class VehicleInterface {
  drive() {
    throw new Error('Method not implemented!');
  }
 
  stop() {
    throw new Error('Method not implemented!');
  }
 
  refuel() {
    throw new Error('Method not implemented!');
  }
}
 
const doorMixins = (BaseClass) => class extends BaseClass {
  openDoors() {
    throw new Error('Method not Implemented!');
  }
};
```

Selanjutnya, pada class MotorCycle yang hanya mengimplementasikan interface Vehicle menjadi seperti ini:

```JS
class Motorcycle extends VehicleInterface {
  drive() {
    // implementation
  }
 
  stop() {
    // implementation
  }
 
  refuel() {
    // implementation
  }
}
```

Maka, interface DoorInterface dapat diterapkan pada class lain, misalnya pada class Car, di mana kenyataannya mobil memiliki pintu. Sehingga kita dapat menerapkannya menjadi seperti ini:

![[Pasted image 20221215054955.png]]

```JS
class Car extends doorMixins(VehicleInterface) {
  openDoors() {
    // implementation
  }
 
  drive() {
    // implementation
  }
 
  stop() {
    // implementation
  }
 
  refuel() {
    // implementation
  }
}
```

Dengan memisahkan interface menjadi bagian-bagian kecil, kegunaan dan tanggung jawab dari interface tersebut akan mudah dipahami oleh developer. Tujuannya adalah untuk menghasilkan desain yang fleksibel, dengan cukup mengimplementasikan interface tertentu daripada mengimplementasikan satu interface yang di dalamnya terdiri dari banyak function yang lebih kompleks.

Berikut adalah perbandingan studi kasus antara tanpa ISP dengan yang menerapkan ISP.

![[Pasted image 20221215055032.png]]