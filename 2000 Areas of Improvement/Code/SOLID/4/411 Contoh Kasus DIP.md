Agar dapat memahami prinsip Dependency Inversion Principle, mari perhatikan dahulu penerapan studi kasus antara mobil dan mesin, yang dimodelkan menjadi kode class Car dan Engine sebagai berikut:

![[Pasted image 20221215055219.png]]

```JS
class Car {
  constructor(engine) {
    this._engine = engine;
  }
}
 
class Engine {
  start() {
 
  }
}
```

Berdasarkan kode di atas, terdapat class Car yang di dalamnya terdapat constructor untuk menambahkan engine, dalam hal ini dimodelkan sebagai class Engine. Namun, bagaimana jika kasusnya pada model Car yang sama, ingin mengubah engine atau mesinnya. Dalam hal ini ingin menggantinya dengan diesel engine (mesin diesel), seperti ini:

```JS
class DieselEngine {
  start() {
 
  }
}
```

Kita tidak dapat menerapkannya, karena parameter dari constructor class Car adalah class Engine. Jika kita memasukkan class DieselEngine maka hasilnya akan seperti ini:

![[Pasted image 20221215055307.png]]

Gambar di atas adalah salah satu penerapan kode pada Kotlin, di mana terdapat pesan error berupa _Type Mismatch_ dari Code editor.  Eror tersebut menjelaskan parameter yang required atau diperlukan adalah class Engine, tetapi yang diinputkan adalah class DieselEngine. Karena kedua class tersebut berbeda, maka muncullah pesan error _type mismatch_.

Salah satu cara mengatasi problem ini adalah dengan menerapkan Dependency Inversion Principle. 

Pertama, kita buat dahulu interface EngineInterface seperti berikut:

```JS
class EngineInterface {
  start() {
    throw new Error('Method not implemented!');
  }
}
```

Selanjutnya kita ubah parameter constructor dari class Car menjadi seperti ini:

```JS
class Car {
  constructor(engine) {
    if (!(engine instanceof EngineInterface)) {
      throw new Error('Engine is not EngineInterface');
    }
 
    this._engine = engine;
  }
 
  start() {
    this._engine.start();
  }
}
```

Sehingga kita dapat membuat class engine baru dengan masing-masing tipe mesin seperti di bawah ini. Di mana masing-masing class tersebut mengimplementasikan interface EngineInterface.

![[Pasted image 20221215055405.png]]

```JS
class PetrolEngine extends EngineInterface {
  start() {
    // implementation
  }
}
 
class HybridEngine extends EngineInterface {
  start() {
    // implementation
  }
}
 
class DieselEngine extends EngineInterface {
  start() {
    // implementation
  }
}
```

Sehingga, kita dengan mudah dapat membuat jenis Car yang berbeda, cukup dari satu model class Car saja. Berikut penerapan untuk pemanggilan kodenya:

```JS
const main = () => {
  const petrolEngine = new PetrolEngine();
  const petrolCar = new Car(petrolEngine);
 
  const dieselEngine = new DieselEngine();
  const dieselCar = new Car(dieselEngine);
 
  const hybridEngine = new HybridEngine();
  const hybridCar = new Car(hybridEngine);
 
  // Booom boom
  petrolCar.start();
  dieselCar.start();
  hybridCar.start();
};
 
main();
```

Dengan menerapkan Dependency Inversion Principle, kita dapat membuat sistem yang fleksibel. Di mana ketergantungan atau dependencies pada source code hanya mengacu pada abstractions bukan pada concretions (sebuah class). Pada contoh di atas digambarkan dalam bentuk interface EngineInterface yang berisi method start(). Sehingga, setelah prinsip ini diterapkan, high level class tidak bekerja secara langsung dengan dengan low level class, tetapi menggunakan interface sebagai lapisan abstraksi.

Berikut adalah perbandingan studi kasus antara tanpa DIP dengan menerapkan DIP:

![[Pasted image 20221215055502.png]]