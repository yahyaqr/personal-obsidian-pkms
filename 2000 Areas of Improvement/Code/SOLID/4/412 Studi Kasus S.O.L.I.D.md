---
created: Thursday, December 15th 2022 - 05.58
updated: Thursday, December 15th 2022 - 05.58
---
Pada studi kasus ini kita akan mencoba membuat pemodelan sebuah pabrik mobil skala besar atau _Car Gigafactory_. Sebuah perusahaan mobil berskala internasional bernama DiCars Corp ingin membuat sebuah mobil tipe sedan dengan bentuk dan model yang sama namun memiliki dua spesifikasi yang berbeda. Berikut ilustrasi bentuk mobil sedan tersebut:  
[![dos:fc6df47959c94f316e1fd495566cba7e20210830160706.jpeg](https://dicoding-web-img.sgp1.cdn.digitaloceanspaces.com/original/academy/dos:fc6df47959c94f316e1fd495566cba7e20210830160706.jpeg)](https://www.dicoding.com/academies/169/tutorials/19617?from=7831# "dos:fc6df47959c94f316e1fd495566cba7e20210830160706.jpeg")

Mobil Sedan tersebut nantinya akan memiliki dua tipe, yaitu tipe F dan tipe E. Di mana tipe F adalah tipe standar yang menggunakan bahan bakar bensin konvensional. Sedangkan tipe E adalah tipe baru yang lebih ramah lingkungan menggunakan daya listrik, atau disebut juga sebagai _EV_ (_Electric Vehicle_). Perbedaan antara kedua tipe tersebut adalah terletak pada spare part yang digunakan. Berikut adalah gambar diagram blok pada mobil sedan tipe F yang menggunakan bahan bakar bensin konvensional:

[![dos:a8dad8c0f2f01334bd3a4b24e717603a20210830160704.jpeg](https://dicoding-web-img.sgp1.cdn.digitaloceanspaces.com/original/academy/dos:a8dad8c0f2f01334bd3a4b24e717603a20210830160704.jpeg)](https://www.dicoding.com/academies/169/tutorials/19617?from=7831# "dos:a8dad8c0f2f01334bd3a4b24e717603a20210830160704.jpeg")

Sedangkan untuk mobil sedan tipe E yang menggunakan daya listrik, berikut ini adalah gambar diagram bloknya:

[![dos:11e3a021ca0a350c5816ebde4a7a927d20210830160704.jpeg](https://dicoding-web-img.sgp1.cdn.digitaloceanspaces.com/original/academy/dos:11e3a021ca0a350c5816ebde4a7a927d20210830160704.jpeg)](https://www.dicoding.com/academies/169/tutorials/19617?from=7831# "dos:11e3a021ca0a350c5816ebde4a7a927d20210830160704.jpeg")Gambar di diatas hanya merupakan ilustrasi secara singkat untuk dapat membedakan beberapa spare part atau komponen dasar antara mobil dengan bahan bakar bensin konvensional dengan mobil dengan daya listrik. Pada kenyataannya komponen di dalamnya lebih kompleks.

Berdasarkan dua diagram blok di atas, terlihat bahwa pada mobil bahan bakar bensin konvensional menggunakan fuel tank sebagai penyimpanan sumber bahan bakar (bensin) yang dihubungkan oleh oil pipe menuju mesin yang menggunakan piston sebagai penggerak. Sedangkan pada mobil dengan daya listrik menggunakan battery sebagai penyimpanan sumber tenaga, kemudian menggunakan komponen _BMS_ _(Battery Management System)_ untuk sistem pengisian daya atau pengaturan daya. Selanjutnya dihubungkan oleh _Speed Controller_ untuk pengaturan kecepatan pada motor listrik (_Electric Motor_).

Sebelum mobil tersebut diproduksi massal atau dibuat dalam bentuk prototype, perlu adanya simulasi terlebih dahulu. Di sini peran kita adalah sebagai _Vehicle Simulation Software Engineer_, bertugas untuk membuat pemodelan kendaraan dalam bentuk perangkat lunak. Agar dapat dilakukan uji coba terlebih dahulu sebelum diimplementasikan pada komponen yang sesungguhnya, menghitung efisiensi yang dihasilkan dan membuat algoritma untuk dapat meminimalisir kesalahan. 

Berikut ini adalah bentuk pemodelan dari mobil tersebut yang dibuat dalam bentuk diagram UML:[![dos:667be67cad5b9ae32c8b54adfc8c19fc20210831104726.png](https://dicoding-web-img.sgp1.cdn.digitaloceanspaces.com/original/academy/dos:667be67cad5b9ae32c8b54adfc8c19fc20210831104726.png)](https://www.dicoding.com/academies/169/tutorials/19617?from=7831# "dos:667be67cad5b9ae32c8b54adfc8c19fc20210831104726.png")Kita mulai dengan pemodelan kelas Car seperti berikut:

```JS
class Vehicle {
  accelerate() {
    throw new Error('method not implemented');
  }
 
  brake() {
    throw new Error('method not implemented');
  }
 
  refill(source) {
    throw new Error('method not implemented');
  }
}
 
class Car extends Vehicle {
  constructor(engine, storage) {
    super();
    this._engine = engine;
    this._storage = storage;
  }
 
  accelerate() {
    this._engine.move();
  }
 
  refill(source) {
    this._storage.fill(source);
  }
 
  brake() {}
}
```

Di dalamnya terdapat parameter EngineInterface, yaitu sebuah interface yang berfungsi agar dapat digunakan oleh dua mesin yang berbeda. Selain itu juga terdapat parameter StorageInterface sebagai interface yang berfungsi agar dapat digunakan oleh dua sumber daya yang berbeda. Penggunaannya adalah pada mesin bahan bakar bensin konvensional dan mesin dengan sumber daya listrik.

```JS
class EngineInterface {
  move() {
    throw new Error('method not implemented');
  }
}
 
class StorageInterface {
  fill(source) {
    throw new Error('method not implemented');
  }
 
  getSource() {
    throw new Error('method not implemented');
  }
}
```

Agar dapat memahami apa saja komponen di dalam mesin bahan bakar bensin, perhatikan contoh pemodelan ini yang dibuat dalam bentuk class **PetrolEngine**:

```JS
class PetrolEngine extends EngineInterface {
  constructor(oilPipe, piston) {
    super();
    this._oilPipe = oilPipe;
    this._piston = piston;
  }
 
  move() {
    const oil = this._oilPipe.suckOil();
    const energy = oil.burn();
    energy.push(this._piston);
  }
}
 
class Piston {
  move() {
 
  }
}
 
class OilPipe {
  suckOil() {
    return new Oil();
  }
}
 
class Oil {
  burn() {
    return new Energy();
  }
}
 
class Energy {
  push(piston) {
    piston.move();
  }
}
 
class Tank extends StorageInterface {
  constructor() {
    super();
    this._oil = null;
  }
 
  fill(source) {
    this._oil = source;
  }
 
  getSource() {
    return this._oil;
  }
}
```

Dalam class PetrolEngine untuk mesin mobil bahan bakar bensin konvensional, class PetrolEngine ini implements EngineInterface agar dapat digunakan pada parameter class Car. Terdapat pula class Tank yang implements StorageInterface, class ini berfungsi sebagai penyimpanan bensin, di mana dimodelkan sebagai class Oil. Kemudian terdapat class OilPipe yang memiliki method suckOil(), berfungsi sebagai pipa penghubung untuk menyedot bensin dari tank. 

Selanjutnya bensin tersebut melalui proses pembakaran (_combustion_) untuk menghasilkan energy yang dimodelkan pada class Energy. Langkah terakhir adalah energy tersebut digunakan untuk menggerakkan piston agar mobil dapat bergerak. Sehingga kira-kira penerapan class-nya menjadi seperti ini:

```JS
// Petrol car
const tank = new Tank();
const oilPipe = new OilPipe();
const piston = new Piston();
const petrolEngine = new PetrolEngine(oilPipe, piston);
const petrolCar = new Car(petrolEngine, tank);
const oil = new Oil();
petrolCar.refill(oil);
petrolCar.accelerate();
petrolCar.brake();
```

Sekarang mari perhatikan kembali bagaimana pemodelan dari mesin sumber daya listrik, yang dibuat dalam bentuk class ElectricEngine. Class ElectricEngine ini implement EngineInterface agar dapat digunakan sebagai parameter pada class Car. Di dalamnya terdapat komponen yang berbeda dari mesin bahan bakar bensin konvensional. Berikut adalah class **ElectricEngine** yang berisi komponen pendukung di dalamnya:

```JS
class ElectricEngine extends EngineInterface {
  constructor(speedController) {
    super();
    this._speedController = speedController;
  }
 
  move() {
    this._speedController.control();
  }
}
 
class SpeedController {
  constructor(bms, motor) {
    this._bms = bms;
    this._motor = motor;
  }
 
  control() {
    const battery = this._bms.getBattery();
    this._motor.rotate(battery);
  }
}
 
class BatteryManagementSystem {
  getBattery() {
    return new Battery(new Electrons());
  }
}
 
class ElectricMotor {
  rotate(batter) {
    // Rotate the rotor using electric power from battery
  }
}
 
class Electrons {}
 
class Battery extends StorageInterface {
  constructor(electrons) {
    super();
    this._electrons = electrons;
  }
 
  fill(source) {
    this._electrons = source;
  }
 
  getSource() {
    return this._electrons;
  }
}
```

Pada class ElectricEngine, terdapat class SpeedController yang digunakan sebagai pengatur kecepatan. Di dalamnya terdapat class BatteryManagementSystem yang digunakan untuk sistem pengisian daya atau pengaturan daya dan class ElectricMotor sebagai tenaga penggerak mobil, motor listrik ini membutuhkan daya listrik dari baterai. Sumber tenaga disimpan pada baterai yang dimodelkan pada class Battery implements StorageInterface. Di dalam Battery terdapat class Electrons, yang diibaratkan sebagai listrik yang tersimpan pada baterai. Sehingga, kira-kira penerapan class-nya menjadi seperti ini:

```JS
// Electric car
const electrons = new Electrons();
const battery = new Battery();
const speedController = new SpeedController(new BatteryManagementSystem(), new ElectricMotor());
const electricEngine = new ElectricEngine(speedController);
const electricCar = new Car(electricEngine, battery);
electricCar.refill(electrons);
electricCar.accelerate();
electricCar.brake();
```

Berdasarkan ilustrasi dari studi kasus di atas, pada penerapan mobil dengan dua mesin yang berbeda, yaitu pada mobil dengan bahan bakar bensin konvensional dan mobil dengan sumber daya listrik, dapat dibuat dengan satu class Car yang sama. Di mana di dalamnya terdapat dua interface sebagai parameter, jadi sebenarnya kita dapat membuat class Car tersebut dengan mesin/engine apa saja asalkan memenuhi syarat dengan implements interface EngineInterface dan StorageInterface. Di sinilah salah satu peran prinsip SOLID. 

Dengan menerapkan prinsip OCP dan DIP, kita tidak perlu membuat class baru untuk masing-masing tipe mesin yang berbeda, juga tidak perlu me-refactor class apabila terdapat perubahan tipe mesin baru. Selain itu, prinsip SRP juga digunakan untuk memisahkan masing-masing tanggung jawab pada class PetrolEngine, sehingga seluruhnya tidak ditumpuk pada class PetrolEngine. Pemisahan juga dilakukan pada interface yang berbeda dengan menerapkan prinsip ISP. Nah, kira-kira seperti itulah penerapan prinsip SOLID pada studi kasus mobil dengan tipe mesin yang berbeda, meskipun pada kenyataannya sistem pada mobil lebih kompleks, kita hanya menggunakan beberapa komponen saja untuk memudahkan kita membuat pemodelannya.

Untuk melihat contoh penerapan SOLID pada kasus yang lain, Anda dapat melihatnya pada tautan berikut.

-   [Explaining SOLID principles with examples of Android programming](https://blog.cezvedici.com/explaining-solid-principles-with-examples-of-android-programming-33d7736fbcf9)
-   [SOLID Design Principles In Kotlin](https://proandroiddev.com/solid-design-principles-in-kotlin-79100c670df1)