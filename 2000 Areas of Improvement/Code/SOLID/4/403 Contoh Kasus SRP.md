---
created: Thursday, December 15th 2022 - 06.03
updated: Thursday, December 15th 2022 - 06.03
---
Sebelum kita membahas penerapan Single Responsibility Principle (SRP), perhatikan studi kasus pada order (pesanan) sebuah mesin kasir atau POS (Point Of Sales) yang dimodelkan menjadi code class Order berikut:

![[Pasted image 20221215060150.png]]

```JS
class Item {}
 
class Order {
  calculateTotalSum() { /* ... */
  }
 
  getItems() { /* ... */
  }
 
  getItemCount() { /* ... */
  }
 
  addItem(item) { /* ... */
  }
 
  deleteItem(item) { /* ... */
  }
 
  printOrder() { /* ... */
  }
 
  showOrder() { /* ... */
  }
 
  getDailyHistory() { /* ... */
 
  }
 
  getMonthlyHistory() { /* ... */
 
  }
}
 
const main = () => {
  const order = new Order();
  order.calculateTotalSum();
};
 
main();
```

Berdasarkan kode di atas, class Order memiliki banyak tanggung jawab (responsibility). Contohnya untuk menambah item, menghapus item, kalkulasi jumlah total, bahkan untuk print dan show. 

Dengan menerapkan prinsip dari SRP, kita dapat memisahkan tanggung jawab dari masing-masing function ke dalam class baru. Sehingga, hasilnya akan menjadi seperti ini:

![[Pasted image 20221215060216.png]]

```JS
class Item {}
 
class Order {
  calculateTotalSum() {}
  getItems() {}
  getItemCount() {}
  addItem(item) {}
  deleteItem(item) {}
}
 
class OrderHistory {
  getDailyHistory() {}
  getMonthlyHistory() {}
}
 
class OrderPreview {
  printOrder(order) {}
  showOrder(order) {}
}
 
const main = () => {
  const item = new Item();
  const order = new Order();
  order.addItem(item);
  const history = new OrderHistory();
  history.getDailyHistory();
  const viewer = new OrderPreview();
  viewer.printOrder(order);
};
```

Contohnya jika ingin mendapatkan history dari order, kita hanya perlu memanggil class OrderHistory. Sehingga, kita bisa mendapatkan daily atau monthly history. Sedangkan jika kita hanya membutuhkan viewer dari class Order, cukup panggil class OrderViewer yang di dalamnya terdapat function printOrder() dan showOrder(). 

Sehingga, class Order itu sendiri hanya memiliki tanggung jawab untuk modifikasi item, yang diwakilkan pada:

-   function addItem() untuk menambahkan item;
-   function deleteItem() untuk menghapus item;
-   function getItems() untuk mendapatkan seluruh items yang telah ditambahkan;
-   function getItemCount() untuk mendapatkan jumlah item; dan 
-   function calculateTotalSum() untuk perhitungan penjumlahan total item.

Jika kita ingin membuat class order dan memanggil fungsi yang sudah dipisahkan, maka contoh kode programnya terlihat seperti di bawah ini:

```JS
const main = () => {
  const order = new Order();
  order.calculateTotalSum();
};
 
main();
```

Berikut adalah perbandingan studi kasus order antara tanpa SRP dengan setelah menerapkan SRP:

![[Pasted image 20221215060312.png]]

Keunggulan dari SRP adalah kode yang dibuat akan lebih mudah dikelola dan diidentifikasi. Bayangkan jika seluruh operasi untuk business rules Order ditumpuk pada class Order, developer akan terus menambahkan fungsi pada class Order seiring bertambahnya requirement atau business rules. Hal ini tentu akan menimbulkan karakteristik buruk dari sebuah software design principle, yaitu rigidity dan fragility. Ketika suatu class sudah memiliki function yang terlalu besar dan ingin melakukan perubahan, perubahan tersebut dapat menyebabkan ketergantungan untuk mengubah function lain di dalamnya. Sehingga ketika ada perubahan, kadang malah muncul kesalahan lain yang tidak terduga, biasanya disebut dengan defect. Kemungkinan kesalahan juga akan meningkat seiring banyaknya perubahan yang dilakukan.

Single Responsibility Principle (SRP) merupakan cara yang baik untuk mengidentifikasi class selama fase desain aplikasi, dan mengingatkan Anda untuk mencari cara terbaik agar class dapat dikembangkan tanpa adanya masalah berarti.

Pemisahan tanggung jawab yang baik hanya bisa dilakukan ketika sebuah gambaran lengkap aplikasi secara keseluruhan telah dipahami dengan baik. Hal ini berisi tentang bagaimana aplikasi tersebut dapat bekerja, sehingga kita dapat memisahkannya dengan rinci.