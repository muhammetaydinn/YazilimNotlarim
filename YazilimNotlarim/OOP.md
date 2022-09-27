PROGRAMLAMA PARADİGMALARI

Paradigma bir bilim dalında bir resmin, gerçekliğin algılanması kavramsallaştırılmasını sağlanayan modele denir.

Programlama Paradigmaları

1- EMİRLİ PROGRAMLAMA
- Prosedürel 
- Yapısal
- Nesne Yonelimli

2-BİLDİRİMLİ PROGRAMLAMA
- Fonksiyonel
- Mantıklsal

programlama modellemesi

UML
![](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/oop/uml-class-diagram/figures/uml-diagramlar.jpg)
UML diyagramları kullanılır.

![](https://miro.medium.com/max/700/1%2A-JJ1lEL5d5m__KkVCZnrHg.png)

nitelliği değişkenler davranışı metotlar

Sınıfa ait niteliklerin sözdizimi (syntax):

<Görünürlük> <İsim>: <Tür> <Multiplicity> = <Varsayılan Değer>
Görünürlük (Visibility): Niteliğin dışarıdan erişim ilkesinin ne olduğunu belirtir. Eğer bir sınıfın niteliği public ise buraya “+“, private ise buraya “–“, protected ise buraya “#” işareti konulur.
İsim (Name): Niteliğe ait isimlendirme yapılır.
Tür (Type): Bir niteliğin veri tipini belirtir.
Varsayılan Değer (Default Value): Niteliğin, ilk değerini belirtir.
Davranışlar (Metotlar)
Sınıfa ait davranışlara ait sözdizimi (syntax):

<Görünürlük> <İsim>(<Parametreler>): <Geri Dönüş Tipi>

Görünürlük (Visibility): Bu davranışın dışarıdan erişim ilkesinin ne olduğunu belirtir. Alabileceği değerler niteliklerde olduğu gibidir.
İsim (Name): Metoda ait isimlendirme yapılır.
Parametre Listesi (Parameter List): Programlamada metodun aldığı parametreler tür bilgileri ile birlikte buraya yazılır.
Geri Dönüş Türü (Return Type): Metodun geri dönüş tipini belirtir.

![](https://github.com/Kodluyoruz/taskforce/raw/main/oop/uml-class-diagram/figures/c2.png)

## Sınıflar Arası İlişkiler
Yazılımlar çoğu zaman tek sınıftan oluşmazlar. Küçük programlar bile çoğu zaman birden fazla sınıfa ihtiyaç duymaktadır. Bir yazılımda sınıf sayısı arttıkça programın tasarlanması da karmaşıklaşır. Bu yüzden UML diyagramlar kullanılarak, bu karmaşıklığı daha olayın en başında minimuma indirip maliyeti azaltmaktır. Sınıflar birbirleriyle ilişki içerisinde olan yapılardır. Bu ilişkileri UML diyagramlarında da göstermek gerekir. Elbette ilişkinin türüne göre gösterim de değişiklik gösterecektir.

- Bağlantı İlişkisi (Association)
- Genelleme/Kalıtım İlişkisi (Generalization/- Inheritance)
- Bağımlılık İlişkisi (Dependency) (Aggregation, - Composition)
- Gerçekleştirim İlişkisi (Realization)


# 4 Temel Ilke
OOP 4 temel ilkeye dayanır.Bunlar;
- Abstraction (Soyutlama)
- Encapsulation (Kapsülleme)
- Inheritance (Kalıtım)
- Polymorphism (Çok Biçimlilik)

### Encapsulation (Kapsülleme)
Access Modifiers(erişim belirleyiciler) ile kapsülleme yapılır. Bu erişim belirleyiciler ile sınıfın içindeki özelliklerin ve metotların dışarıdan erişimini kontrol edebiliriz. Bu erişim belirleyicileri şunlardır: public, private, protected.
Private kullanırsan getter setter ile erişim sağlanır.
```java
public class Kitap {
    public int sayfaSayisi;
    public String kitapAdi, yazar;
    Kitap(String kitapAdi, int sayfaSayisi, String yazar) {
        this.kitapAdi = kitapAdi;
        this.yazar = yazar;
        if (sayfaSayisi < 1) {
            this.sayfaSayisi = 10;
        } else {
            this.sayfaSayisi = sayfaSayisi;
        }
    }
}
/*
Constructor metodu görüldüğü gibi modifiye ettik ve nesne oluşturulurken anlamız verilerin olmasını engelledik. Ama sorunlarımız hala bitmedi , biz nesneye ait niteliklere hala dışarıdan erişebiliyoruz ve book.sayfaSayisi = -10 dersek , nesneye ait sayfa sayısını yine anlamsızlaştırmış oluruz. Bu sorunu çözmek için sınıfa ait değişkenlere dışarıdan erişimi kapatmamız gerekir ve oluşturduğumuz değişkenlerin erişim belirleyicilerini (Access Modifiers) değiştirmemiz gerekli. Tüm public'leri private olarak değiştiriyoruz.
*/
//Sınıfımızın son hali
public class Kitap {
    private int sayfaSayisi;//private olarak değiştirdik
    private String kitapAdi, yazar;//private olarak değiştirdik
    Kitap(String kitapAdi, int sayfaSayisi, String yazar) {
        this.kitapAdi = kitapAdi;
        this.yazar = yazar;
        if (sayfaSayisi < 1) {
            this.sayfaSayisi = 10;
        } else {
            this.sayfaSayisi = sayfaSayisi;
        }
    }
}

```
### Getter ve Setter Metotları
Private kullanırsan class içinde **public olan** getter setter ile erişim sağlanır.

```java
public class Kitap {
	private int sayfaSayisi;
	private String kitapAdi, yazar;


	Kitap(String kitapAdi, int sayfaSayisi, String yazar) {
		this.kitapAdi = kitapAdi;
		this.yazar = yazar;
		if (sayfaSayisi < 1) {
			this.sayfaSayisi = 10;
		} else {
			this.sayfaSayisi = sayfaSayisi;
		}
	}


	public int getSayfaSayisi() {
		return this.sayfaSayisi;
	}


	public void setSayfaSayisi(int sayfaSayisi) {
		if (sayfaSayisi < 1) {
			this.sayfaSayisi = 10;
		} else {
			this.sayfaSayisi = sayfaSayisi;
		}
	}
}
```
### Kalıtım (Inheritance)
Eğer bir A sınıfın B sınıfından kalıtım yapması isteniyorsa, aşağıda ki şekilde tanımlanır.
```java
public class A extends B {
     // 
}
``` 
### Çoklu Kalıtım (Multiple Inheritance)

Bir sınıfın birden fazla sınıfı miras almasını ifade eder; bu, bir alt sınıfın iki ata sınıfa sahip olduğu anlamına gelir.

Not : Java çoklu kalıtımı desteklemez. (Interface kullanılır)
![](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/java102/inheritance/figures/kl2.png)

### Çok Seviyeli Kalıtım (Multilevel Inheritance)

Bir sınıfa ait alt sınıfın başka sınıfları genişletmesine denir.

![](https://patika-prod.s3-eu-central-1.amazonaws.com/content/modules/oop/lessons/inheritance/zpxqtnLQrKGR5D2dh)

### Hiyerarşik Kalıtım (Hierarchical Inheritance)
Birden fazla sınıfın aynı sınıfı genişlettiği bir alt ve üst sınıf ilişkisini ifade eder.

![](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/java102/inheritance/figures/kl4.png)
Bu örnekte : B, C ve D sınıfları aynı A sınıfını genişletir.

### Hibrit Kalıtım (Hybrid Inheritance)
Programda birden fazla kalıtım türünün kombinasyonuna denir. Örneğin, A ve B sınıfı, C sınıfını genişletir ve başka bir D sınıfı, A sınıfını genişletir, bu bir hibrit kalıtım örneğidir, çünkü bu, tek yönlü ve hiyerarşik kalıtımın bir birleşimidir.
![](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/java102/inheritance/figures/kl5.jpeg)

### Kalıtım'da Constructor Zinciri ve Super Anahtar Sözcüğü
Bir sınıfa ait nesne oluşturulurken, o sınıfın bir kurucusunun işletildiğini, kurucunun çalışması tamamlandıktan sonra bellekte artık bir nesnenin oluştuğunu biliyoruz.

Bu durumda, eğer nesnesi oluşturulacak sınıf başka bir sınıfın alt sınıfıysa, önce ataya ait iç nesnesinin oluşturulması ve bu nesnenin niteliklerinin ilk değerlerinin verilmesi gerektiğini söyleyebiliriz.

Böylece iç içe nesneler sıra ile oluşturularak en son en dıştaki nesne oluşturulmuş olur ve kurucu zinciri tamamlanır.
### Super Kullanımı
Eğer ata sınıfta varsayılan kurucu yoksa ve programcı alt sınıftaki kurucunun içinde ata sınıfın hangi kurucusunun çağrılacağını belirtmezse derleme hatası alınacaktır. Çünkü derleyici aksi belirtilmedikçe ata sınıfın varsayılan kurucusunu çağıran super() kodunu üretecektir. 
Ata sınıfın hangi kurucusunun çağrılacağı, super anahtar sözcüğü ile birlikte verilen parametrelere göre belirlenir. Nasıl ki new işleci ile birlikte kullandığımız parametreler hangi kurucunun çağrılacağını belirliyorsa, super anahtar sözcüğü ile birlikte kullanılan parametreler de aynı şekilde ata sınıfın hangi kurucusunun işletileceğini belirler.

## PolyMorphism (Çok Biçimlilik)
Polymorphism(çok biçimlilik) NYP'de programlama dilinin farklı tip verileri ve sınıfları farklı şekilde işleme yeteneğini belirten özelliğidir. Daha belirgin olmak gerekirse, metotları ve türetilmiş sınıfları yeniden tanımlama yeteneğidir.

Polimorfizm, alt sınıfların ata sınıflardaki metotları geçersiz kılması(method overriding) sayesinde çok biçimli olarak davranmasına denir. Bu sayede alt sınıf ata sınıfından gelen davranışı kendine göre şekillendirebilir.
![](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/oop/polymorphism/figures/polimorfizm.jpg)

## Soyutlama (Abstraction)
**UML de abstract class isimler italik yazılr**

Bir sınıftan nesne üretimini istemiyorsak-mantıksız geliyorsa- bunu kullanabiliriz.

**"abstract" Anahtar Kelimesi ve Soyut Sınıf Kavramı (Abstract Class)**

Aynı şekilde Java'da sınıflarımızı tasarlarken bazı fonksiyonların ve işlevlerin sadece sınıf içinde kalması, dış dünyada bu sınıftan nesneleri kullanan kişilerin bu iç fonksiyonları bilemelerine gerek yoktur. Örneğin: KDV tutarını hesaplayan fonksiyonun sınıf içinde kullandığı birçok başka fonksiyon olabilir. Bu fonksiyonların sınıf dışına açılmasının bir anlamı yoktur. Sadece miktarı verip o miktara göre KDV tutarını hesaplayacak bir dış fonksiyon yeterlidir. Yazılım dünyasında bu nedenle soyutlama kavramı yazılım tasarımında önemli bir kavramdır. Soyutlama yapabilmek için "abstract" anahtar kelimesi, "interface" gibi yapılar bizlere yardımcı olmaktadır.

Soyutlama için Java'da iki yöntem mevcuttur:

"interface" tanımlamak
"abstract" sınıf tanımlamak
## Soyut Sınıf (Abstract Class)
"abstract" anahtar kelimesi ile tanımlanan sınıflardır. Sınıfın içinde soyut ("abstract") metotlar veya normal fonksiyonlar tanımlanabilir. **Soyut sınıflardan "new" anahtar kelimesi ile bir nesne oluşturulamaz.**

Soyut Sınıf Özellikleri:
- "abstract" anahtar kelimesi ile tanımlanmış olması gerekiyor.
- Soyut veya soyut olmayan fonksiyonlar tanımlanabilir.
- Soyut sınıflardan "new" anahtar kelimesi ile nesne oluşturulamaz.
- Kurucu metodu ve static fonksiyonlar tanımlanabilir.
- "final" kelimesi ile tanımlanmış fonksiyonları içerebilir. Bu final fonksiyonlar alt sınıflarda ezilemezler (override).

```java
// abstract sınıf örneği
public abstract class Doping {

	protected double price;
	protected double[] taxes;

	public double[] getTaxes() {
		return taxes;
	}

	public void setTaxes(double[] taxes) {
		this.taxes = taxes;
	}

	public double getPrice() {
		return price;
	}

	public void setPrice(double price) {
		this.price = price;
	}

	// soyut metot örneği
	public abstract double calculate();
}
```
Yukarıda soyut bir sınıf tanımladık. "abstract" kelimesi ile sınıf tanımladık, ayrıca sınıfın içinde "calculate" isimli "abstract" metot tanımladık. Aynı zamanda soyut olmayan metotlar da tanımladık. Senaryomuzda bir e-ticaret sisteminde "Doping" tipinde ek ürünler olduğunu düşünelim. İlan tarihini güncelleyen bir doping çeşidimiz olsun, bir de üst sırada çıkmanızı sağlayan bir doping olsun. Bu iki alt sınıfta "Doping" isimli sınıftan kalıtım alarak belli özellikleri kendilerine alsınlar. Fakat, her dopingin ücret hesaplama yöntemi birbirinden farklı olabilir. Ayrıca, her dopingin mutlaka fiyat hesaplama fonksiyonu olmalıdır.

Yukarıdaki durumda "abstract" sınıf tanımlayıp diğer doping çeşitleri bu ATA sınıftan kalıtım alacaklardır. "calculate" isimli "abstract" metodu, "metod ezme" (overriding) yöntemiyle ezip metodun içini kendilerine göre dolduracaklardır. Alt sınıflardaki diğer özellikler soyutlama tekniğiyle dış dünyadan gizlenecektir. Dış dünyadan dopingi kullanmak isteyen baka bir sınıf veya kod parçası doping nesnesi üzerindeki "calculate" fonksiyonunu çağırıp fiyatı hesaplayacaktır. Diğer iç hesaplama ve çalışma detaylarını bilmeyecektir.
```java
public class TopOfListDoping extends Doping {

	public TopOfListDoping(double price) 
	{
		super.setPrice(price);
	}

	// "Doping" soyut sınıfından kalıtımla gelen, "calculate" isimli soyut metodu metot ezmesi yöntemiyle alt sınıf kendi ihtiyacına göre dolduruyor.
	// "TopOfList" isimli doping tipinde vergiler olmadığı için komisyon oranı eklenip ücret hesaplanıyor. Fakat, başka doping çeşitlerinde hesaplama farklı olabilir.
	@Override
	public double calculate() {

		return super.getPrice() + super.getPrice() * 0.35;
	}
}

public class UptodateDoping extends Doping {

	public UptodateDoping(double price, double[] taxes) {
		super.setPrice(price);
		super.setTaxes(taxes);
	}

	// "Doping" soyut sınıfından kalıtımla gelen, "calculate" isimli soyut metodu metot ezmesi yöntemiyle alt sınıf kendi ihtiyacına göre dolduruyor.
	// "UptodateDoping" isimli doping tipinde vergiler fiyata dahil olduğu için komisyon oranı eklenip ve vergiler hesaplanıp ücret belirleniyor.
	// Görüldüğü gibi her doping çeşidinin fiyat hesaplama yöntemleri birbirinden farklıdır. Soyutlama ile sınıflara ait iç çalışma detayları gizlenmmiş oluyor.
	// Doping tiplerinde sadece "calculate" isimli fonksiyonu dış dünyaya açtık. Diğer tüm fonksiyonlar ve özellikler sınıf içinde kaldı.
	@Override
	public double calculate() {
		
		return calculateTaxes() + commisionRate();
	}

	private double calculateTaxes() {
		
		double totalTaxValue = 0;
		for(int i=0; i < super.getTaxes().length; i++) {
			totalTaxValue += super.getTaxes()[i];
		}
		return totalTaxValue;
	}

	private double commisionRate() {
		return super.getPrice() * 0.2;
	}
}
```
"Doping" soyut sınıfından kalıtımla gelen, "calculate" isimli soyut metodu metot ezmesi yöntemiyle alt sınıf kendi ihtiyacına göre dolduruyor. "UptodateDoping" isimli doping tipinde vergiler fiyata dahil olduğu için komisyon oranı eklenip ve vergiler hesaplanıp ücret belirleniyor. Görüldüğü gibi her doping çeşidinin fiyat hesaplama yöntemleri birbirinden farklıdır. Soyutlama ile sınıflara ait iç çalışma detayları gizlenmiş oluyor. Doping tiplerinde sadece "calculate" isimli fonksiyonu dış dünyaya açtık. Diğer tüm fonksiyonlar ve özellikler sınıf içinde kaldı.