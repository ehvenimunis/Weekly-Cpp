# Weekly-C++


Desing Pattern Nedir?

Bu terimi “Tasarım Kalıpları”, “Tasarım Şablonları”, “Tasarım Örüntüleri” gibi farklı isimlerle görebilirsiniz. Tasarım kalıpları, yazılım geliştiricilerin yazılım geliştirme sırasında karşılaştıkları genel sorunların çözümüdür. Bu çözümler, uzun bir süre boyunca sayısız yazılım geliştirici tarafından deneme yanılma yoluyla elde edilmiştir.

Yaratılış kalıpları, nesneleri doğrudan oluşturmanıza değil, sizin için nesneler yaratan kalıplardır. Bu, belirli bir durum için hangi nesnelerin yaratılması gerektiğine karar vermede programınıza daha fazla esneklik sağlar. Tasarım kalıpları bir algoritma ya da kod değildir. Ayrıca belli dile özgü değildir, dilden bağımsızdır. Genellikle nesneler arası ilişkileri UML diyagramları ile gösteririz, bu sayede yazılımcılar arasında ortak bir iletişim dili oluşmuş olur. Belli bir tasarımı istediğiniz dille yazdığınız bir projeye kolaylıyla uygulayabilirsiniz. Tabi burada bir yanlış anlaşılmayı gidermekte fayda var. Neredeyse tüm Türkçe kaynaklarda tasarım kalıplarını OOP(Nesne Tabanlı Programlama) ile sınırlandırmışlar. Ancak Tasarım Kalıpları, dilden ve programlama paradigmalarından bağımsızdır.

Tasarım Kalıpları Çeşitleri Nelerdir?

    Creational Patterns (Yaratımsal Kalıplar)
    Structural Patterns (Yapısal Kalıplar)
    Behavioral Patterns (Davranışsal Kalıplar)

Creational (Yaratılış) Kalıbı Nedir?

Yaratılış kalıpları, nesneleri doğrudan oluşturmanıza değil, sizin için nesneler yaratan kalıplardır. Bu, belirli bir durum için hangi nesnelerin yaratılması gerektiğine karar vermede programınıza daha fazla esneklik sağlar.

    Singleton pattern, bir sınıf için sadece bir nesne oluşturmayı sağlar.
    Factory method pattern, oluşturulacak tam sınıfı belirtmeden nesneleri oluşturur.
    Abstract factory pattern, ortak gruplar, ortak bir temaya sahip olan sınıfların yaratılış biçimini hedefler.
    Builder pattern, karmaşık nesneler inşa eder.
    Prototype pattern, mevcut bir nesneyi klonlayarak nesneler oluşturur.

enum class?

Numaralandırma sınıfı türlerinin kendi kapsamları var ve tanıtılan numaralandırma sabitleri numaralandırma sınıfının kendi kapsamında yer alır.

// class kelimesine dikkat enum ile birlikte kullanılacaktır
enum class Color {NONE, RED, GREEN, BLUE}; 
enum class Alert {NONE, GREEN, YELLOW, RED};

// Karşılaştırmalarda kullanım
Color currentColor = Color::GREEN;

if (Color::RED == currentColor)
{
    // gelen renk kırmızı
}

// Aynı zamanda fonksiyonlara parametre olarak verilebilir ve bunlara dair 
// forward declaration yapilabilir
enum class Color; // Forward declaration
void DrawText(Color currentColor);

// Daha sonra ilgili enumun kullanılacağı yerde enum tipi tanımlanır

Tür dönüştürme operatörleri nelerdir?

    static_cast<> operatörü
    const_cast<> operatörü
    reinterpret_cast<> operatörü
    dynamic_cast<> operatörü

dynamic_cast (dinamik tür dönüştürme operatörü)

Referanslar ve göstericiler için kullanılır. Geri dönüş değeri istenilen türe dönüştürme işlemi başarısız ise NULL’dır. Genel kullanım alanlarından biri çalışma zamanında tür belirlenmesi (Run Time Type Identification) içindir.

dynamic_cast<> operatörü

static_cast te dynamic_cast te olduğu gibi dinamiklik söz konusu değildir. Yani çalışma zamanında türün dönüşüp dönüşemediğini belirleyemezsiniz. Dolayısıyla static_cast’te tüm sorumluluk programcıya aittir.

const_cast<> operatörü

Bir türün değişmezliğini manipüle etmemizi sağlar. Örneğin const olan bir nesnenin normalde const olmayan bir nesneye atanması mümkün değil. Bu tür dönüştürme operatörü ile mümkün hale geliyor.

reinterpret_cast<> operatörü

Her türlü gösterici türünü her türlü gösterici türüne çevirebilir. Bilinçsiz kullanımı kesinlikle tavsiye edilmez. Aslında basit olarak göstericinin diğer göstericiye binary olarak kopyalanmasıdır. Hash fonksiyonlarında pratiklik açısından adres olarak kullanılan alanı hash değerine çevirmek için kullanılır. Kullanım alanları oldukça kısıtlıdır.

Storage Class nedir?

Storage class yapıları: bir fonksiyonun veya değişkenin tanımlanması esnasında, onun amacını, görünürlüğünü ve bellekten ne zaman silineceğini belirten anahtar kelimelerdir. C++ programlama dilinde 5 tane storage class anahtar kelimesi bulunmaktadır: auto, register, extern, static, mutable.

auto ile tanımlanan değişkene benzer tiplerdeki değişkenler atanabilir. Örnek olarak int olarak kullanılan bir değişkene double veya float değerler atanabilir. auto kullanılarak yapılan tanımlama biz geliştiricilere zaman kazandırmış olur. auto storage sınıfı kullanıldığında derleyici uygun değişken tipini bulmak için ek zaman harcayacaktır. Dolayısıyla derleme süresi bir miktar uzayacaktır fakat sonuç olarak program uygun değişken tipi ile derlenmiş olacağından çalışmasında herhangi bir hız problemi olmayacaktır.

register ile tanımlanan bir değişkenin erişim hızını arttırmak amacıyla yer varsa CPU üzerindegi registerlarda tutulması istenir. Yer yoksa normal bellekte tutulur. auto sınıfı benzer şekilde çalışmaktadır. Farkları ise register olarak belirtilen bir değişkeni, derleyici CPU üzerindeki registerlar üzerinde tutmaya çalışır. Eğer uygunluk yoksa yine bellekte tutulurlar. Bu sayede ilgili değişkene daha hızlı erişim sağlanır. Çok fazla kullanılan değişkenlerin register ile tanımlanmaları önerilmektedir. Bu sayede programın çalışması esnasında RAM bellekten daha hızlı bir erişim sağlanacağı için performans artacaktır. Sadece gerekli olanların register olarak tutulmaları gerekmektedir.

extern ile programın herhangi bir yerinde tanımlanan bir değişken başka biryerde başlatılır ve diğer yerlerden bu değişkene erişilerek veri okuma yazma yapılabilir. Static yapısına benzer global olarak kullanım sağlanır. Bu sayede bir değişkenin sınıf yapısının kullanılmadığı yerlerde, global olarak kullanılmasına olanak tanımaktadır. Çok geniş bir programda farklı header dosyaları ile çalışılırken extern ile değişkenlerin global olarak kullanılmalarına olanak tanınmaktadır.

static ile tanımlanan bir değişkene programın her yerinden erişilebilir ve global olarak kullanılabilir hale gelir. Yani static ifadeler, tanımlandığında başlatılır ve program kapanana kadar herhangi bir şekilde bellekten kaldırılmazlar ve sürekli bellekte tutulur. Herhangi bir şekilde yeniden tanımlanmalarına gerek yoktur. Başlatıldıkları bellek bilgisini program kapanana kadar saklarlar. Tanımlandıklarında herhangi bir değer atanmazlarsa derleyici tarafından değeri 0 olarak belirlenir.

mutable ile cons olarak tanımlanan bir sınıfın içerisinde barındırılan bir değişkenin değiştirilmesine izin verilir. İlgili değişken mutable olarak tanımlanır. Bu sayede herhangi bir değerinin değiştirilmemesi gereken bir sınıfı const olarak tanımlarız ama içerisinde değişmesini istediğimiz bir değişken olursa mutable olarak tanımlarız ve değiştirilmesine olanak tanımış oluruz.

#include <iostream>
using std::cout;

class Test {
public:
	int x;

	// defining mutable variable y
	// now this can be modified
	mutable int y;

	Test()
	{
		x = 4;
		y = 10;
	}
};

int main()
{
	// t1 is set to constant
	const Test t1;

	// trying to change the value
	t1.y = 20;
	cout << t1.y;

	// Uncommenting below lines
	// will throw error
	// t1.x = 8;
	// cout << t1.x;
	return 0;
}

/*
Output: 
20
*/


          
### Kaynaklar
GeekForGeeks
NecatiErgin
