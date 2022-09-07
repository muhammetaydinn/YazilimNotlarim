Java, doğrudan C++ ile bağlantılıdır. C++ ise C’nin devamıdır.

 C’nin sözdizimi (syntax), C++’ın ise nesne yönelimli programlama (object oriented programming- OOP) kavramları Java’ya miras kalmıştır. Bunun yanı sıra, Java, bu dillerdeki karmaşıklığı ortadan kaldırmış, eksik özelliklerini ise tamamlamıştır.

**Multi-Thread & Dinamik**

**Gömülü sistem** uygulamaları geliştirebilirsiniz. (Java2ME Embedded altyapısı ile) Java, gömülü sistem tasarımcıları için bir dizi avantaja sahiptir.

Java'da isimlendirilen tüm ögeler sadece A-Z veya a-z gibi harfler, $ karakteri veya _ karakteri ile başlayabilirler.

**Sınıflar** için upper camel case kullanılır. **HelloWorld**

**Metotlar** için lower camel case kullanılır. **helloWorld**

**Değişkenler** için lower camel case kullanılır. **helloWorld**

**Sabitler** için screaming snake case kullanılır. **HELLO_WORLD**



/ ** * /Bu tarzda yazılan açıklama satırlarına Javadoc adı verilmektedir. Javadoc için kullanılabilecek bazı örnekler ve ne için kullanılabilecekleri aşağıda listelenmiştir:

Değişkenlerin 4 özelliği bulunur ; Veri Tipi, İsim, Değer ve Adres.



## Java'daki İlkel Veri Tipleri
### Tam Sayılar

Byte

Short

Integer

Long

### Ondalıklı Sayılar

Float

Double

Karakterler

Char

Mantıksal Değerler

Boolean

## Byte, Short, Int ve Long Veri Tipleri

8 16 32 64 bit iki üzeri hesapla

Float32 1.4×10^-45 ile 3.4×10^38

Double64 4.9×10^-324 ile 1.8×10^308

Char Java’da 16 bittir.

```java
import java.util.Scanner;

Scanner input = new Scanner(System.in);
System.out.println("A sayısını giriniz : ");
        a = input.nextInt();
```
**Not : farklı tip sonrası nextLine alırsan bir atlat. Yoksa null doner.**


Java'da **Do-While** ve **While** döngüleri arasındaki **tek fark** , **Do-while** döngüsünde, döngü bloğu içindeki kod kesimi **en az bir kez mutlaka işletilecektir.** Çünkü önce döngü bloğu işletilip sonra koşul denetlenmektedir. While döngüsünde ise önce koşula bakılıp sonra döngü bloğu işletildiği için, döngüye hiç girilmemesi olasıdır.


```java
int i=1, j=1;
while(i<3)
{
  do
  {
    System.out.print(j + ",");
    j++;
  }while(j<4);
  i++;
}
Yukarıdaki programın çıktıs 1,2,3,4,
```


### Continue Deyimi
Java'da "continue" deyimi , döngü içinde bir koşul oluştuğunda o döngüyü tamamlamadan bir sonraki kademeye geçmeye yarar.

```java
int i = 0;
while (i < 10) {
  i++;
  if (i == 5) {
    continue;
  }
  System.out.println(i);
}
```
Örnekte görüldüğü gibi eğer i değişkeni 5 sayısına eşit olduysa, o kod bloğundan sonraki kodlar çalışmayıp döngü bir sonraki adıma geçiş yapacaktır.

 

### Break 
```java
for (int i = 0; i < 10; i++) {
  if (i == 5) {
    break;
  }
  System.out.println(i);
}
```

Bu tarz durumlarda break deyimini kullanırız. **Bu deyim**, içinde kullanıldığı **döngüyü anında sonlandırır.**

**static method içine çağrılacak methodlar da static olmalıdr**

static main içine girecek method da static olmalı yoksa bu hata gelir
```
Cannot make a static reference to the non-static method run() from the type MainJava(603979977)
```


Void içinde boş return olabilir. çalışır.
```java
return; //gibi ancak return 123; olmaz
```


### Overloading parametre farklı kullanma
aynı isimde aynı parametrede sadece 1 metod olabilir.

değişkenler tanımlandıkları kodbloklarına aittir farklı bloktaki atama diğer bloktakini etkilemez.

Bildiğimiz gibi her nesnenin kendine ait nitelikleri ve davranışları vardır.

NYP, "Don't Repeat Yourself" yani "Kendini Tekrar Etme" ilkesini uygular ve kodun bakımını, düzenlenmesini ve hata ayıklamasını kolaylaştırır.
Sözdizimi (Syntax)

```
class <class_name>{

	<variable>;
	<methods>;
    }
```

```java
// sınıfa ait davranışları baştabelirtirsek iyiolur.
class Car{

    // niteliklerString type;String model;String color;
    int speed;

    // davranışlarint increaseSpeed(int increment) {
        speed += increment;
        return speed;
    

    int decreaseSpeed(int decrease) {
        if (speed > 0) {
            speed -= decrease;
        }
        return speed;
    }
    
    void printSpeed() {
        System.out.println("Speed : " + speed);
    }
    // ...
}
```




Java'da nesne üretmek için kullanılan sözdizimi :
```java
ClassName object = new ClassName();  
```
**ClassName** : Nesne oluşturmak istediğimiz sınıfı belirtiyoruz. Bu sınıf daha öncesinde projemizde tanımlanmış olması gerekmektedir.
object : Nesnemize verdiğimiz isimdir ve aynı isimde birden fazla nesne oluşturulamaz.

**new** : Java'da nesne üretmek için "new" anahtar kelimesini kullanırız.

**ClassName();** : Sınıfa ait Kurucu (Constructor) Metodu temsil eder.
Varsayılan olarak parametresiz tanımlanır.
Sınıf Metotlarına Erişim
Sınıfa ait davranışlara yani metotlara erişmek için nokta (.) kullanılır. İlgili nesnenin ismini sonuna nokta koyularak erişilmek istenilen metodun ismi yazılır ve var ise parametreleri girilir.

**new** : Java'da **nesne üretmek için "new"** anahtar kelimesini kullanırız.

**Kurucu metotların isimleri Sınıf ismiyle aynı olmak zorundadır**



Not:
```
Bir Class içinde değişkenleri belirttikten sonra yine aynı class içinde methodlarda o değişkeni kullanacaksak this.degisken seklinde kullanmalıyız.
```

*Kurucu Methodlar nesneyi ilk kullanıma hazırlar*


```java
double[] myList;   // tercih edilen yol
```
Diziler veri tipi ve [] parantezler ile belirtilir. Yukarıda iki farklı tanımı görülmektedir. Hafızadan yer alıp diziye alan ayırabilmek için "new" anahtar kelimesi kullanılır.

```java
double[] myList = new double[10];


// Java'da diziye ilk değerler süslü parantezler arasında verilir.
double[] myList = { 1.9, 2.9, 3.4, 3.5 };

// tüm dizi elemanlarını arada boşuk bırakarak sırayla ekrana yazdırır.
for (int i = 0; i < myList.length; i++)
{
	System.out.println(myList[i] + " ");
}
dizilerde sadece aynı veri tipi bulunabilir.
```
Diziler new deyimiyle oluşturulur. Dizi oluştururken kapasite değeri vermek zorunludur. 
```java
int[] numbers = new int[5];
String[] weekDays = new String[] { "Pazartesi", "Salı", "Çarşamba", "Perşembe", "Cuma", "Cumartesi", "Pazar" };

//Yukarıdaki gibi dizi oluştururken new deyimini kullanmaya gerek yoktur. Yani, yukarıdaki kodu aşağıdaki gibi yazabiliriz:

String[] weekDays = { "Pazartesi", "Salı", "Çarşamba", "Perşembe", "Cuma", "Cumartesi", "Pazar" };
```


```java
 int cars[], count=3;

cars = new int[count];

//mumkun
```

```java
degiskenTipi[][] arrayIsmi;
int matrix[][];

int[][] array = {
{1, 2, 3}, 
{4, 5, 6}, 
{7, 8, 9}, 
{10, 11, 12} 
};
```

```java

int[][] matrix = new int[3][4];
int number = 1;

for (int x = 0; x < matrix.length; x++)
{
	int[] row = matrix[x];

    for (int y = 0; y < row.length; y++)
	{	
		row[y] = number;
		number++;
	}
}
```



```java
for (int row = 0; row < matrix.length; row++) {
   for (int column = 0; column < matrix[row].length; column++) {
       System.out.print(matrix[row][column] + " "); 
}
    System.out.println(); 
}
```


### Sütun Kapasiteleri Farklı Matris Oluşturmak - Düzensiz Diziler
```java
int[][] matrix = new int[3][];
matrix[0] = new int[1];
matrix[1] = new int[2];
matrix[2] = new int[3];
!!!!!
```


```java
!!!!!!!!!!!!!!!!!!!!!
int[][] numbers;
numbers = new int[3][];
numbers[0] = {1,2};
System.out.println(numbers[0][1]);
//BU OLMAZ 

//Array constants can only be used in initializersJava(1610612944)
//View Problem HATASI
//!!!!!!!
```



```java
ForEach Kullanımı
for (veritipi degisken: diziAdi) {
  // kod bloğu
}


String[] arabalar = {"BMW", "Mercedes", "Ford", "Ferrari"};
for (String i : arabalar) {
  System.out.println(i);
}

// Çıktısı
// BMW
// Mercedes
// Ford
// Ferrari 
 int[] list = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
        for(int a: list){
            System.out.println(a);
        }


public class Main {public static void main(String[] args) {
        int[][] matris = {
                {1, 2, 3},
                {4, 5, 6},
                {7, 8, 9},
                {10, 11, 12}
        };

        for (int[] u : matris) {
            for (int elem : u) {
                System.out.println(elem);
            }
        }
    }
}

```

## Arrays Sınıfı ve Metotları
```java
import java.util.Arrays;
Arrays.toString()

//Diziye ait elemanları direk ekrana basmak için kullanılan bir metottur.

import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        int[] dizi = {3, 5, 79, 12, 25, -3, 66, 82, -49, 152};
        System.out.println(Arrays.toString(dizi));
    }
}

// Çıktısı
// [3, 5, 79, 12, 25, -3, 66, 82,-49,152]

```

### Arrays.fill()
Arrays.fill metodu ile dizilerimizin belirli bir bölümlerine değerler atayabiliriz.

```java
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        int[] liste = {15, 1, 99, 7, 7, -22, 11, 2, -49, 52};

        Arrays.fill(liste, 2);
        System.out.println(Arrays.toString(liste));

        int[] liste2 = {15, 1, 99, 7, 7, -22, 11, 2, -49, 52};

        Arrays.fill(liste2, 3, 5, 7);
        System.out.println(Arrays.toString(liste2));
    }
}

// Çıktısı
// [2, 2, 2, 2, 2, 2, 2, 2, 2, 2]
// [15, 1, 99, 7, 7, -22, 11, 2, -49, 52]
```
### Arrays.sort()
Arrays.sort() metodu ile dizilerdeki elemanları sıralayabiliriz.
```java
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        int[] liste = {6, 1, 55, 21, 33, -321, -21, 2, -11, 27};
        Arrays.sort(liste);
        System.out.println(Arrays.toString(liste));
    }
}
// Çıktısı
// [-321, -21, -11, 1, 2, 6, 21, 27, 33, 55]
```

### Arrays.binarySearch()
Java'da dizideki bir elemanın indis değerini bulmak için binarySearch kullanılabilir. Ama bu metodu kullanabilmek için, **dizinin sıralı olması gerekmektedir.**
```java 
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        int[] liste = {6, 1, 55, 21, 33, -321, -21, 2, -11, 27};

        Arrays.sort(liste);
        System.out.println(Arrays.toString(liste));

        int index = Arrays.binarySearch(liste, 33);
        System.out.println("33'ün indeksi :" + index);
    }
}
// [-321, -21, -11, 1, 2, 6, 21, 27, 33, 55]
// 33'ün indeksi :8
```

### Arrays.copyOf() ve Arrays.copyOfRange() metotu
Mevcut diziden belli bir uzunlukta yeni bir dizi oluşturmak için Arrays.copyOf() metotu kullanılır

Mevcut diziden belli bir aralıkta yeni bir dizi oluşturmak için ise Array.copyOfRange() metodu kullanılır.
```java
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        int[] liste = {6, 1, 55, 21, 33, -321, -21, 2, -11, 27};

        int[] copyArray = Arrays.copyOf(liste, 3);
        System.out.println(Arrays.toString(copyArray));

        int[] copyOfRangeArray = Arrays.copyOfRange(liste, 0,5);
        System.out.println(Arrays.toString(copyOfRangeArray));
    }
}
// [6, 1, 55]
// [6, 1, 55, 21, 33]
```

### Arrays.equals() metotu
Java'da iki dizinin eşitliğini kontrol etmek için Arrays.equals() metotu kullanılır.
```java
import java.util.Arrays;

public class Main {public static void main(String[] args) {
        int[] list1 = {1, 2, 3};
        int[] list2 = {1, 2, 3};
        int[] list3 = {1, 2, 10};

        System.out.println(Arrays.equals(list1, list2)); // true
        System.out.println(Arrays.equals(list2, list3)); // false
    }
}
```
```
== kullanırken aynı pointera sahip olup olmadıgını kontrol et
```

## JAVA KUTUPHANESINDE GUZEL METODLAR
![](https://introcs.cs.princeton.edu/java/11cheatsheet/images/math-api.png)
![](https://introcs.cs.princeton.edu/java/11cheatsheet/images/stdin-api.png)
![](https://introcs.cs.princeton.edu/java/11cheatsheet/images/string-api.png)
![](https://introcs.cs.princeton.edu/java/11cheatsheet/images/string-ops.png)


comparetolgnoreCase

contentequals aynı karakterdizesi mi

substring baslangıctan indexe kadar harfyazar

tocharArray dizeyi string yapar

lowercase

tostring sting yapar

uppercase

valueof primitive tipini verir