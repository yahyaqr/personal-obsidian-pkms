---
created: Thursday, December 15th 2022 - 06.17
updated: Thursday, December 15th 2022 - 06.17
---
### Modul Object Oriented Programming

Pada modul pendahuluan ini, kita telah mengenal dasar-dasar sebelum melangkah ke modul selanjutnya, yaitu tentang _Object Oriented Programming_. Mari kita ulas sejenak apa saja yang telah dipelajari pada rangkuman ini :

-   Paradigma pemrograman adalah gaya atau cara dalam menulis suatu program menggunakan bahasa pemrograman tertentu.
    
-   OOP (Object Oriented Programming) adalah salah satu paradigma atau teknik pemrograman yang populer dalam pengembangan aplikasi. Dengan paradigma tersebut, kita dapat dengan mudah memvisualisasikan kode karena OOP sendiri mirip dengan skenario kehidupan nyata.
    
-   Dalam penerapannya, OOP menggabungkan kumpulan fungsi atau atribut yang memiliki kesamaan dalam sebuah unit yang kita sebut sebagai objek. 
    
-   _Class_, merupakan sebuah blueprint yang dapat dikembangkan untuk membuat sebuah objek. Di dalam class bisa terdapat beberapa attribut ataupun behaviour.
    
-   _Property_, adalah data yang ada dalam sebuah class yang merepresentasikan karakteristik dari sebuah class. Setiap _property_ memiliki struktur dasar, diantaranya adalah modifier, tipe data, nama konstanta dan nilai.
    
-   _Function_, sebuah prosedur yang memiliki keterkaitan dengan pesan dan objek. 
    
-   Ada 4 pilar dalam OOP, yaitu _Inheritance, Encapsulation, Abstraction_, dan _Polymorphism_
    
-   _Inheritance_, mekanisme pewarisan sifat yang dilakukan dari sebuah kelas (induk) ke class baru (anak), di mana beberapa fungsi maupun property yang ada pada induk kelas akan bisa diakses oleh kelas baru tersebut. 
    
-   Ada beberapa istilah dalam inheritance, yaitu superclass dan subclass. _Superclass_ adalah class yang fitur-fiturnya akan diwariskan. Sedangkan _subclass_ adalah class baru yang akan mewarisi _member_ milik _superclass_.
    
-   Inheritance di kenal ada beberapa jenis, yaitu :
    
    -   _Single Inheritance_, class yang dibuat hanya mewarisi satu class saja.
        
    -   _Multiple Inheritance_, class yang mewarisi lebih dari satu superclass
        
    -   _Hierarchical Inheritance,_ sebuah superclass yang diwarisi oleh beberapa subclass.
        
    -   _Hybrid Inheritance_, kombinasi dari beberapa inheritance.
        
-   _Encapsulation_, adalah proses di mana penanganan data diisolasi dan ditempatkan di dalam sebuah class. Data yang terisolasi tidak dapat diakses langsung dari luar. 
    
-   _Abstraction_, adalah mekanisme saat proses dalam sebuah objek disembunyikan dan hanya akan menyediakan apa yang benar-benar perlu digunakan.
    
-   _Polymorphism_,  merupakan kemampuan objek, variabel, atau fungsi yang dapat memiliki berbagai bentuk. _Polymorphism_ terbagi menjadi 2 yaitu:
    
    -   _Compile Time Polymorphism_,  adalah sebuah proses di mana sebuah method atau fungsi dipanggil saat kompilasi. Contoh dari ini adalah konsep overloading.
        
    -   _Runtime Polymorphism_, adalah proses di mana sebuah fungsi dipanggil pada saat runtime. Contohnya adalah konsep _overriding_.
        

### Modul Relasi pada OOP

Pada modul ini, Anda sudah mempelajari beberapa hubungan dalam OOP. Sebelum menuju ke modul selanjutnya, mari kita mengingat-ingat point apa saja yang sudah dipelajari;

-   Relations in OOP atau bisa disebut hubungan antar object adalah hal yang mendasar dalam pemrograman berorientasi objek. Hubungan tersebut mendefinisikan bagaimana objek-objek tersebut akan berinteraksi atau berkolaborasi satu sama lain.  
    
-   Ada 3 kategori dalam hubungan antar objek, yaitu _association, dependency_, dan _generalization_.
    
-   _Association_, didefinisikan sebagai hubungan yang terstruktur, yang secara konsep memiliki arti bahwa dua komponen saling terhubung satu sama lain. 
    
-   Hubungan dalam asosiasi disebut sebagai kardinalitas, yang merupakan hubungan maksimum yang terjadi dari himpunan entitas yang satu ke himpunan entitas yang lain, atau sebaliknya. Ada beberapa tipe dalam kardinalitas, yaitu:
    
    -   _One-to-one relationship_, hubungan yang terjadi ketika satu objek A memiliki referensi dari satu objek B, atau sebaliknya.
        
    -   _One-to-many relationship_, hubungan antara dua objek A dan B di mana objek A terhubung dengan lebih dari satu objek B, tetapi anggota dari objek B hanya terhubung dengan satu anggota A.
        
    -   _Many-to-many relationship_, hubungan antara dua buah objek A dan B, di mana setiap anggota dari objek A maupun B memiliki hubungan lebih dari satu objek A dan B.
        
-   Dalam hubungan asosiasi antara 2 objek, terdapat 2 relasi yaitu:
    
    -   _Aggregation_, hubungan yang tidak terikat, hanya sekedar memiliki. Setiap class yang berhubungan dapat berdiri sendiri jika salah satunya dihancurkan atau tidak ada.
        
    -   _Composition_, hubungan yang saling terikat, yang saling memiliki satu sama lain. Apabila salah satunya dihancurkan, maka class yang terikat lainnya akan hancur juga, atau tidak bisa digunakan lagi.
        
-   _Dependency_, adalah hubungan antara dua buah class, di mana satu class memiliki ketergantungan dengan class lainnya tetapi class lainnya tidak atau mungkin memiliki ketergantungan terhadap class pertama.
    
-   _Generalization_, adalah konsep pemisahan karakteristik dari dua atau lebih class dan menggabungkannya menjadi satu class yang lebih umum atau biasa disebut Superclass. Berbanding terbalik dari generalisasi, _specialization_ adalah konsep membuat subclass dari class yang sudah ada.
    
-   _Realization_, adalah hubungan abstraksi khusus antara dua kelas, satu mewakili kelas yang direalisasikan (supplier) dan yang lainnya mewakili kelas implementasinya (client)
    

### Modul Software Design Principle

Akhirnya, kita telah selesai mempelajari tentang Software Design. Berikut adalah beberapa materi yang telah dibahas: 

-   Dalam mengembangkan perangkat lunak, dibutuhkan _architecture_ dan _design_ yang baik. _Architecture_ menentukan struktur dari perangkat lunak. Sedangkan _design_, lebih mengarah pada hubungan antar komponen yang berada di dalamnya.
    
-   Software Design Principle merupakan pedoman yang dapat digunakan untuk menghindari design yang buruk saat mengembangkan sebuah perangkat lunak. 
    
-   Menurut Robert C. Martin, terdapat 3 design yang buruk, yaitu :
    
    -   _Rigidity_, adalah kondisi suatu sistem yang sulit diubah, bahkan untuk perubahan yang paling sederhana. 
        
    -   _Fragility_, adalah kecenderungan perangkat lunak yang salah di beberapa bagian setiap kali melakukan perubahan. 
        
    -   _Immobility_, adalah sebuah ketidakmampuan untuk menggunakan kembali perangkat lunak dari proyek lain atau bagian-bagian dari proyek yang sama.
        

### Modul S.O.L.I.D

Berikut adalah rangkuman dari beberapa materi yang telah dibahas pada module ini:

-   SOLID adalah kumpulan dari beberapa principle yang diwujudkan oleh para _engineer_ yang ahli di bidangnya dan membantu mengembangkan sebuah perangkat lunak dengan tingkat kekukuhan yang tinggi. 
    
-   Ada beberapa tujuan dari prinsip SOLID, yaitu toleran terhadap perubahan, mudah dipahami dan komponen dasar dapat digunakan kembali dalam bentuk _software system_ lainnya.
    
-   SOLID adalah sebuah singkatan. Yang setiap hurufnya dapat dipecah lagi agar bisa memahami isinya. Masing-masing pecahannya adalah
    
    -   _Single Responsibility Principle_ (SRP), merupakan sebuah principle yang digunakan untuk mengatur tanggung jawab dari sebuah entitas yang berada di dalam sebuah proyek. Entitas dalam hal ini adalah sebuah module/class untuk memenuhi kebutuhan actor. Sedangkan _Actor_ sendiri merupakan kumpulan "user" atau "stakeholder" yang menginginkan perubahan pada perangkat lunak.
        
    -   _Open / Close Principle_, sebuah principle yang mengatur di mana artefak perangkat lunak harus terbuka untuk ditambahkan tetapi tertutup untuk dimodifikasi. 
        
    -   _Liskov Subtitution Principle_, sebuah principle yang mengatur desain hirarki pewarisan. Aturan - aturan tersebut antara lain 
        
        -   Contravariant & Covariant,  
            _Contravariant_ adalah kondisi di mana parameter dari sebuah fungsi yang berada pada SubClass harus memiliki tipe dan jumlah yang sama dengan fungsi yang berada pada SuperClass-nya. Sedangkan _Covariant_, adalah kondisi pengembalian nilai dari fungsi yang berada pada SubClass dan SuperClass.
            
        -   Precondition & PostCondition,  
            _Precondition_ adalah tindakan yang harus ada sebelum sebuah proses dijalankan. Sedangkan _postcondition_ sebaliknya, yaitu tindakan yang harus ada ketika sebuah proses selesai dijalankan.
            
        -   _Invariant_, adalah penjelasan dari kondisi suatu proses yang benar sebelum proses tersebut dimulai dan tetap benar setelahnya.
            
        -   _Constraint_, adalah pembatasan yang ditentukan oleh SuperClass terhadap perubahan keadaan sebuah obyek.
            
    -   _Interface Segregation Principle_, sebuah principle yang bertujuan untuk mengurangi jumlah ketergantungan sebuah class terhadap interface class yang tidak dibutuhkan.
        
    -   _Dependency Inversion Principle_, sebuah principle yang mengatur ketergantungan antar module. Terdapat 2 aturan dalam dependency inversion principle, yaitu 
        
        -   _High-level module_ tidak diperbolehkan untuk bergantung pada _low-level module_. Keduanya harus bergantung pada abstraction.
            
        -   Abstraksi tidak diperbolehkan untuk bergantung pada detail. Detail harus bergantung pada abstraksi.