## JVM (JAVA VİRTUAL MACHİNE)
.class uzantılı bytecode'u satır satır işleyerek makine koduna dönüştürür ve çalıştırır.Özetle, Javada yazılan kod önce bytecode'a çevrilir, daha sonrasında üzerinde çalıştığı makinenin içerisindeki yalın dile (makine koduna) yorumlanarak çalıştırılır.

**Bytecode** -> Java derleyicisinin Java ile yazılmış kodların makine dili yerine kendine has oluşturduğu Binary (0 ve 1) dosyasıdır.

**JVM** -> Java Bytecode formatına derlenmiş programların çalışmasını sağlayan bir sistemdir.





Dynamic Arrays (Dinamik diziler) ise yeni bir eleman için boşta yer tutmasından ötürü esnektir.

Dynamic Array (Dinamik dizinin) dezavantajlarından biri ise hafızada fazladan yer kaplaması, 

linked ile array farkı array yanyana ancak linked farklı yerlerde ama bir sonrakinin yerini biliyor


Stack, LIFO (Last in First out) (En son giren en önce çıkar) 

Queue (Kuyruk), FIFO (First in First out) (İlk giren ilk çıkar)

Queue (Kuyruk)'da eleman eklemesi yaparken enqueue methodunu kullanıyoruz. Eleman silerken ise dequeue methodunu kullanıyoruz.
### Hash Function/ Hash Table
Hash Table, key value prensibine dayanan bir array kümesidir. Key olarak çağırdığınız elemanın değerini (value) yansıtır.

Hash Table yerine dizileri kullanabilirdik. Fakat her ürünü ve fiyatını tek tek aramak istemediğimiz için hash table kullanıyoruz.

### Hash Function
Hash Function (Karma Fonksiyonu), karma fonksiyonu olabilmesi için bazı temel şartlar vardır.Bunlar;

Gönderdiğimiz anahtarlar (keys) farklı olmasına rağmen bize aynı sonuçları veriyorsa bu bir hash function değildir.
Fonksiyona gönderilen anahtarlar aynı fakat sonuç farklı ise hash function değildir.
Hash Table için kullanılan dizinin boyutu verilen sonuçların sayısı kadar olmalı.
Collision
aynı sonuc alan keyler için geçerli

Hash Function farklı iki değerden aynı sayı üretilirse bu duruma Collison (çarpışma) denir. Bu olay istediğimiz bir durum değildir.

Hash Function'lar bazen farklı durumlar için farklı sonuçlar üretemeyebilir. Örnek olarak araçları bir hash function dan geçirelim. Bu fonksiyonumuz son harflerine göre bir değer atıyor. Örneğin, motor ve tır için aynı değerleri ataması collision'a neden oluyor.
Collision sorunuyla az karşılaşabilmek için kaliteli bir hash function olmalı. Bu sayede verimli bir Hash Table elde etmiş oluyoruz.
Çarpışma sayısı arttıkça aradığımız şeyi bulma hızı azalır.


## Ram 


Bu hayalî cihaza RAM (Random Access Machine) diyoruz. Ram, algoritmalar arasındaki farkları belirlemek için kullanacağımız bir araç olacak.

Her işlemin birim zamanı var. Döngüler, kaç defa işlem yapıyorsa, (işlem sayısı * kaç kere tekrar edeceği) kadar birim zaman alır. Toplama, Çıkarma, and, or gibi aritmetik işlemler, 1 birim zaman alır.

## Time Complexity
worst-best- average = beklenen ayrıca average bulmak daha zor

## Sorting
Searching yöntemini kullanarak elemanlarımızı **sıraladık**. Bunun sebebi, eleman ararken işimizin kolaylaşmasını istiyoruz.

**Selection sort:** dizide en kucugı bulup sıraya göre o sıradaki elemanla yer değiştirme küçükten buyuge

**insertion:** ise kucukten buyuge bir eleman tum elamanlarla kıyaslanıp yerlestırılır

## Merge Sort
Insertion Sort'da, Big-O gösteriminden dolayı input'um arttığında n2 olduğunda dolayı çalışma zamanı artıyor.

Insertion sort'da, time complexity n2 olduğundan ötürü çalışma zamanımız artıyordu. Merge sort'da ise **nlogn** olduğu için açık ara performans olarak daha iyi diyebiliriz.



## Quick Sort
Hızlı sıralama günümüzde çok yaygın olarak kullanılan bir sıralama algoritmasıdır. N tane sayıyı **average case e göre big-o nlogn**, **worst case e göre big-o n^2** karmaşıklığı ile sıralanır.

QuickSort

![](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/veri-yapilari-algoritmalar/quick-sort/figures/Quicksort.png)



## Linear Search
big-o notasyonumuz otomatik olarak n oluyor.


## Binary Search
İkili arama algoritması, elimizde bulunan veri dizisini sıralı olduğunu varsayıyor, bu durumu değiştirerek sonuca varmak istiyor.

İkili arama algoritması, diziyi her seferinde ikiye bölerek ikili arama yapar. Sıralı bir listem var ise benim Big-o logn olarak karşımıza çıkıyor.
en kucuk solda
## Binary Search Tree
Bir düğüm her iki tarafa da referans verebiliyor. Sağ ve sol olarak. Sağ tarafından kendinden büyük elemanlar, sol tarafında ise kendinden küçük elemanlar bulunacak.

tree'ye eleman eklemek istediğimde root'dan başlıyorum
![](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/veri-yapilari-algoritmalar/binary-search-tree/figures/binary-search-tree.png)