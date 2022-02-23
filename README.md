Rangkuman OOP
-------------
OOP adalah singkatan dari Pemrograman Berorientasi Objek.

Pemrograman prosedural adalah tentang menulis prosedur atau fungsi yang melakukan operasi pada data, sedangkan pemrograman berorientasi objek adalah tentang membuat objek yang berisi data dan fungsi.

Pemrograman berorientasi objek memiliki beberapa keunggulan dibandingkan pemrograman prosedural:

1. OOP lebih cepat dan lebih mudah untuk dieksekusi
2. OOP menyediakan struktur yang jelas untuk program
3. OOP membantu menjaga kode C++ KERING "Jangan Ulangi Sendiri", dan membuat kode lebih mudah untuk dipelihara, dimodifikasi, dan di-debug
4. OOP memungkinkan untuk membuat aplikasi penuh yang dapat digunakan kembali dengan lebih sedikit kode dan waktu pengembangan yang lebih singkat

Kelas dan Objek? adalah dua aspek utama dari pemrograman berorientasi objek.
Jadi, kelas adalah templat untuk objek, dan objek adalah turunan dari kelas.
Ketika objek individu dibuat, mereka mewarisi semua variabel dan fungsi dari kelas.

Kelas C++
Segala sesuatu di C++ dikaitkan dengan kelas dan objek, bersama dengan atribut dan metodenya. Misalnya: dalam kehidupan nyata, mobil adalah objek . Mobil memiliki atribut , seperti berat dan warna, dan metode , seperti drive dan rem.
Atribut dan metode pada dasarnya adalah variabel dan fungsi yang dimiliki oleh kelas. Ini sering disebut sebagai "anggota kelas".
Kelas adalah tipe data yang ditentukan pengguna yang dapat kita gunakan dalam program kita, dan berfungsi sebagai konstruktor objek, atau "cetak biru" untuk membuat objek.

Membuat Class : Untuk membuat kelas, gunakan class sebagai kata kunci
Contoh
Buat kelas yang disebut " MyClass":

class MyClass {       // class
  public:             // Access specifier
    int myNum;        // Attribute (int variable)
    string myString;  // Attribute (string variable)
};

Objek
Dalam C++, sebuah objek dibuat dari sebuah kelas. Kami telah membuat kelas bernama MyClass, jadi sekarang kami dapat menggunakan ini untuk membuat objek.
Contoh
Buat objek bernama " myObj" dan akses atributnya:

class MyClass {       // The class
  public:             // Access specifier
    int myNum;        // Attribute (int variable)
    string myString;  // Attribute (string variable)
};

int main() {
  MyClass myObj;  // Create an object of MyClass

  // Access attributes and set values
  myObj.myNum = 15; 
  myObj.myString = "Some text";

  // Print attribute values
  cout << myObj.myNum << "\n";
  cout << myObj.myString;
  return 0;
}

Methods adalah fungsi yang dimiliki oleh class. Ada dua cara untuk mendefinisikan fungsi yang termasuk dalam class:
1. Definisi di dalam class
2. Definisi luar class
Contoh dalam class
class MyClass {        // The class
  public:              // Access specifier
    void myMethod() {  // Method/function defined inside the class
      cout << "Hello World!";
    }
};

int main() {
  MyClass myObj;     // Create an object of MyClass
  myObj.myMethod();  // Call the method
  return 0;
}

Contoh Luar Class
class MyClass {        // The class
  public:              // Access specifier
    void myMethod();   // Method/function declaration
};

// Method/function definition outside the class
void MyClass::myMethod() {
  cout << "Hello World!";
}

int main() {
  MyClass myObj;     // Create an object of MyClass
  myObj.myMethod();  // Call the method
  return 0;
}

Parameter Konstruktor
Contoh
class Car {        // The class
  public:          // Access specifier
    string brand;  // Attribute
    string model;  // Attribute
    int year;      // Attribute
    Car(string x, string y, int z) { // Constructor with parameters
      brand = x;
      model = y;
      year = z;
    }
};

int main() {
  // Create Car objects and call the constructor with different values
  Car carObj1("BMW", "X5", 1999);
  Car carObj2("Ford", "Mustang", 1969);

  // Print values
  cout << carObj1.brand << " " << carObj1.model << " " << carObj1.year << "\n";
  cout << carObj2.brand << " " << carObj2.model << " " << carObj2.year << "\n";
  return 0;
}

Sama seperti fungsi, konstruktor juga dapat didefinisikan di luar class.
Contoh
class Car {        // The class
  public:          // Access specifier
    string brand;  // Attribute
    string model;  // Attribute
    int year;      // Attribute
    Car(string x, string y, int z); // Constructor declaration
};

// Constructor definition outside the class
Car::Car(string x, string y, int z) {
  brand = x;
  model = y;
  year = z;
}

int main() {
  // Create Car objects and call the constructor with different values
  Car carObj1("BMW", "X5", 1999);
  Car carObj2("Ford", "Mustang", 1969);

  // Print values
  cout << carObj1.brand << " " << carObj1.model << " " << carObj1.year << "\n";
  cout << carObj2.brand << " " << carObj2.model << " " << carObj2.year << "\n";
  return 0;
}

Enkapsulasi
Arti Encapsulation , adalah untuk memastikan bahwa data "sensitif" disembunyikan dari pengguna. Untuk mencapai ini, Anda harus mendeklarasikan variabel/atribut kelas sebagai private(tidak dapat diakses dari luar kelas). Jika Anda ingin orang lain membaca atau mengubah nilai anggota pribadi, Anda dapat menyediakan metode get dan set publik.

Akses private
Untuk mengakses atribut private, gunakan metode "get" dan "set" publik:

Contoh
#include <iostream>
using namespace std;

class Employee {
  private:
    // Private attribute
    int salary;

  public:
    // Setter
    void setSalary(int s) {
      salary = s;
    }
    // Getter
    int getSalary() {
      return salary;
    }
};

int main() {
  Employee myObj;
  myObj.setSalary(50000);
  cout << myObj.getSalary();
  return 0;
}
  
Inheritance
Dalam C++, dimungkinkan untuk mewarisi atribut dan metode dari satu kelas ke kelas lainnya. Kami mengelompokkan "konsep pewarisan" ke dalam dua kategori:

kelas turunan (anak) - kelas yang mewarisi dari kelas lain
kelas dasar (induk) - kelas yang diwarisi dari
Untuk mewarisi dari kelas, gunakan :simbol.

Pada contoh di bawah, Carkelas (anak) mewarisi atribut dan metode dari Vehiclekelas (induk):
Contoh
// Base class
class Vehicle {
  public:
    string brand = "Ford";
    void honk() {
      cout << "Tuut, tuut! \n" ;
    }
};

// Derived class
class Car: public Vehicle {
  public:
    string model = "Mustang";
};

int main() {
  Car myCar;
  myCar.honk();
  cout << myCar.brand + " " + myCar.model;
  return 0;
}

Polimorfisme
Polimorfisme berarti "banyak bentuk", dan itu terjadi ketika kita memiliki banyak kelas yang terkait satu sama lain melalui pewarisan.
Contoh
// Base class
class Animal {
  public:
    void animalSound() {
    cout << "The animal makes a sound \n" ;
  }
};

// Derived class
class Pig : public Animal {
  public:
    void animalSound() {
    cout << "The pig says: wee wee \n" ;
  }
};

// Derived class
class Dog : public Animal {
  public:
    void animalSound() {
    cout << "The dog says: bow wow \n" ;
  }
};


