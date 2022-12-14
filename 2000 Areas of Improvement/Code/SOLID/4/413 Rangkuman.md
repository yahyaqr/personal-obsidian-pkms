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