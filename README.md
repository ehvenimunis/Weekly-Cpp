# Weekly-C++


### Derleyici nedir?

Derleyici, yüksek seviye bir programlama dilinde (high-level programming language) yazılmış bir kaynak kodun, başka bir hedef dile veya bilgisayarın/işlemcinin anlayabileceği makine diline tercümesini yapan bir programdır.

### Linker nedir?

Bir derleyici tarafından üretilmiş olan kodları bağlayarak işletim sisteminin çalıştırabileceği tek bir kod üreten programdır.Object dosyasına çevrilen bir veya birden çok dosyanın birbirleri ile ilişkilendirmesi ve tek bir çalıştırılabilir dosyaya örneğin (explorer.exe) çevrilmesini sağlayan yazılımdır.

### Process ve thread arasındaki fark nedir?

Process yani diğer bi anlamıyla işlem bir işletim sistemi üzerinde herhangi bir dil ile kodlanmış ve bir compiler (derleyici) ile derlenmiş ve daha sonra hafızaya yüklenerek işlemcide çalıştırılan programlara verilen isimdir.
          Genel anlamda her program bir process olarak düşünülebilir, ancak bir programın birden fazla processi olabileceği gibi her process, yeni başka processlerde üretebilir. İşletim sisteminin tasarımına göre değişmekle birlikte işlemler (process) kendi adres alanında çalışırlar ve hafıza koruması uygulanır. Bu sayede bir işlemin, başka işlemlerin bilgisine erişmesi engellenmiştir.
         İşlemler arası iletişim aynı bilgisayarda çalışan farklı programların haberleşmesini hedef alır, bu durum ağ üzerinde birbiriyle haberleşen bilgisayarlara benzetilebilir.
Thread (iplik) kavramı, aynı process ortamında birden fazla iş yürütme imkanı sağlar. Bir process’in çalışmaya başlaması ile birlikte bir thread oluşturulur ve bu process içerisinde birden fazla iplik oluşturulabilir. Yaratılan iplikler aynı adres uzayında koşarlar. Her ipliğin kendine has program sayacı, saklayıcıları, yığını ve durumu(yok edilme, askıya alınma, önceliğinin değiştirilmesi) vardır. Bir iplikteki değişkeni aynı işlem tarafından üretilmiş bütün iplikler değiştirebilir veya okuyabilir.
          Threadler iş parçacıkları olup, çoklu görevlerde senkranizasyon sağlamak için kullanılır. Her threadin farklı bir görevi vardır. Eğer bu threadler aynı anda aynı bölgeye girerse hatalar meydana gelebilir.

### Constructor ve destructor nedir?

Constructor (Yapılandırıcı) fonksiyon, kendi sınıfı içerisindeki üyeleri veya oluşturduğu nesnenin ilk çıkış sahnesini oluşturan fonksiyonlardır.Nesneler, genelde yaratılırken ilk değer atamalarını kendi kurucu fonksiyonları sayesinde yaparlar.Böyle bir kural şart değildir, ancak nesne yönelimli programlama dilleri üzerinde kod yazan programcılar genelde bu yaklaşım ile sınıflarını tasarlarlar.Bakıldığı zaman programın optimizasyonu açısından da constructor fonksiyonları çok yararlıdır.
Destructor (Yıkıcı) olarak adlandırılan fonksiyonlar ise, Constructor fonksiyonunun yaptığı işin tersini yaparlar, yani görevi biten nesneyi yok ederler.Bir sınıfın (class) üyesi olan bir değişken (orn:string tipli) görevini noktaladığı durumda ~destructor() fonksiyonu otomatik cağrılarak, üzerinde caliştığı nesneyi devre dışı bırakır. C++ programlama dili içerisinde Destructorlar bulunurken, Java dilinde bu fonksiyonlar kaldırılmıştır.Nedeni ise, programlama zafiyeti açısından eğer iyi tasarlanmazsa, bu fonksiyonlar programa ciddi zararlar verebilirler.

### Statik Nedir?

Program işlediği sürece bellekte kendisine belirli bir yer ayrılan değişken türüdür. Program çalışma süresince sadece bir kere tanımlanır. Örneğin bir fonksiyon içerisindeki bir statik değişken fonksiyon ne kadar çaırılırsa çağırılsın bir kez tanımlanır.

```
#include <iostream>

void ArttirVeYazdir()
{
    static int s_degisken= 1;
    // Degisken statiktir.

    ++s_degisken;
    std::cout << s_degisken << std::endl;

} // s_degisken yok edilmedi.

int main()
{
    ArttirVeYazdir();
    ArttirVeYazdir();
    ArttirVeYazdir();

}
```

### Auto Nedir?

Auto deyimi eğer değişken tanımlanırken değer alıyorsa kullanılır. Örneğin bir double değişkene 5.5 değerini vereceksek derleyici tanımlayacağımız değişkenin zaten double olduğunu çözebilir.

```double x{ 5.6 };  //Derleyici 5.6'nin double literal oldugunu biliyor.```

```auto x { 5.6 }; //Yukaridakiyle ayni is yapilir. Derleyici x'in double oldugunu biliyor.```

C++14 ile birlikte auto deyimi fonksiyon dönüş tipi olarak kullanılabilir hale geldi.

Örneğin:

```
auto topla(int x, int y)

{

   return x + y;

}
```

### Bool neden 8 bit uzunluğunda?

Çünkü her C++ veri tipi adreslenebilir olmalıdır.

Tek bir bit için nasıl bir işaretçi yaratırsınız? Yapamazsın. Ancak bir bayt için bir işaretçi oluşturabilirsiniz. Bu nedenle, C++’daki bir boole, tipik olarak bayt boyutundadır. (Daha büyük de olabilir. Bu uygulamaya bağlı. Ana şey, adreslenebilir olması gerektiğidir, bu nedenle hiçbir C++ veri türü bir bayttan küçük olamaz)

### Kaç tür sabit vardır?

İki tür sabit vardır. Literaller ve sembolik sabitler.

Literaller kodda direkt olarak yazılan ifadelerdir. Sabitlerdir çünkü değerleri değiştirilemez.

Örneğin:

```
bool AmIAlive = true; // true bir literaldir ve değeri değiştirilemez.

int yas = 20; // 20 bir int literaldir ve degistirilemez.

char *isim = "Alperen"; // Alperen bir string sabitidir.

char A = 'A' // Char literal

double PI = 3.14159 // 3.14159 bir double literaldir.

double avogadro = 6.02e23;
```

Sayısal sabitler bazı eklere sahip olabilirler. Bu ekler o sabitin türünü belirler. İsteğe bağlıdırlar. Derleyici genellikle hangi sabiti kullanmak istediğinizi anlayabilir.

İkilik sayı sabitlerinin başına “0b”, sekizliklerin başına “0” ve on altılıkların başına “0x” koyulur.

```
int y = 0b01011001;

int x = 0765;

int f = 0xFF;
```

Sembolik sabit nedir?

Normal değişkenlerin değerleri değiştirilebilirdir. Const değişkenler ise değiştirilemezler. Örneğin pi sayısı, dünyanın çekim ivmesi gibi değerlerin değişmediğini biliriz. Yazdığımız kodda da değişmemesi gerekmektedir. Bunun için değişken tanımının başına “const” ifadesini koyarız.

Const değerlere ilk değer ataması yapmak zorunludur.

Örneğin:

```
const double gravity { 9.8 }; // Dogrudur ve tercih edilir.
double const PI { 3.14 }; // Calisir ama onerilmez.

const int X; //Derleyici hatasi.
```

### Constexpr nedir?

C ve C++ içinde makrolar, derlemeden önce ön işlemci tarafından işlenen belirteçlerdir. Bir makro belirtecinin her örneği, dosya derlenmeden önce tanımlı değeri veya ifadesiyle değiştirilir. Makrolar genellikle derleme zamanı sabit değerlerini tanımlamak için C stili programlamada kullanılır. Ancak makrolar hataya neden olur ve hata ayıklaması zordur. Modern C++ içinde, derleme zamanı constexpr sabitleri için değişkenleri tercih edersiniz:

```
#define SIZE 10 // C-style
constexpr int size = 10; // modern C++
```

Constexpr değişkenler const değişkenler gibi sabitlerdir ama constexpr değişkenler derleme zamanı çözülmelidirler.

örneğin:

```
constexpr pi(3.14); /* Derleyici derleme sirasinda pi'ye atanacak degeri cözebildi. Sikinti yok */

int x;

std::cin >> x;

constexpr int foo(x) /* Derleme hatasi. Derleme sirasinda atanacak deger bilinmiyor. */
```

C de çok kullanılan önişlemci sabitleri C++ da yazarken çok önerilmez. Çünkü dilin mekaniklerine aykırı bir kullanımı vardır ve yer yer ikiliklere sebep olabilir.

```
#define SABIT 100

int x = SABIT;
```

### Tür dönüşümü nedir?

Bir veri tipinin başka bir veri tipine çevrilmesidir. Bazı tip dönüşümleri veri kaybına sebep olurken bazılarını da yapmak mümkün değildir. C++ üstü kapalı (implicit) birçok dönüşümü otomatik olarak yapabilir. Örneğin, aşağıda int bir veri long bir veriye dönüştürülmüş.

```
int myInt{12};
long myLong;
myLong = myInt;
```

### static _cast nedir?

```
char c = 'a';
std::cout << static_cast<int>(c) << std::endl; // a değil 97 yazdırır.
```

Statik dönüşümün en iyi yanı, derleme zamanı kontrol yapmasıdır. Böylece mantıksız olabilecek işlemlerden kaçınılır.

Yapıcı ve Yıkıcı Fonksiyon nedir?

Yapıcı fonksiyon bir sınıftan yeni bir nesne oluşturulduğunda çalışan özel bir üye fonksiyondur.

Bir yapıcı fonksiyon tanımlanırken;

    Yapıcı fonksiyonun ismi sınıfla aynı isimde olmalıdır.
    Yapıcı fonksiyonlar değişkenlere ilk değer atamak için kullanılabilir.
    Yapıcı fonksiyonun, sınıf tanımı içinde veya sınıf adı ve kapsam çözümleme :: işleci kullanılarak dış sınıf tanımında tanımlanabilir.
    Yapıcı fonksiyonların dönüş türü yoktur.
    Yapıcı fonksiyonun başına bir anahtar kelime koyulamaz.

Derleyici yıkıcı fonksiyonu uygulama kapatıldığında veya nesnenin süresi dolduğunda çalıştırır. Yıkıcı fonksiyon içerisine kod yazılabilir, böylece her kaynağın temizlendiğinden emin olunmaktadır.

Bir Yıkıcı fonksiyon tanımlanırken;

    Yıkıcı fonksiyon tanımlarken sınıf adı ile aynı olmalıdır ve isimden önce ~(tilde) işareti koyulmalıdır.
    Yıkıcı fonksiyon parametre alamamaktadır.
    Yıkıcı fonksiyonunu geri dönüş tipi yoktur.

### pragma once nedir?

Microsoft visual studio’nun en kullanışlı pragma direktiflerinden. bir header file‘in sadece tek sefer include edilmesini saglar. boylece gcc ortamlarindaki #ifndef #define #endif gibi standart girizgahlara gerek kalmaz.

Microsoft compiler’ında gayet çalışırken, “#pragma once” içeren kodunuzu başka compiler ile derlemeye çalıştığınızda hata verebilir. Microsoft visual studio, yeni eklenen header dosyasına default olarak koyar bu direktifi.

### Constructor nedir?

Construct -> inşa etmek, kurmak
Constructor -> inşa eden, kurucu

Bilinmesi gerekenler:

    Constructor nesneyi hayata hazırlar.
    Her sınıfın constructorı mutlaka var.
    Ben constructor yazmassam benim yerime derleyici yazıyor.
    Constructor sınıf ismi ile aynı olmalıdır.
    Constructor geri dönüş kavramı yoktur. (void değil karıştırılmamalı)
    Constructor NON-STATIC üye fonksiyonudur.
    Constructor const OLAMAZ.
    Constructor OVERLOAD edilebilir.

### Constructor static üye fonksiyon mu yoksa non-static üye fonksiyon mu?

Constructor non-static üye fonksiyonudur. Çünkü nesnemize ilk değer vereceğine göre büyük olasıklıkla veri elemanlarına değerler yerleştirecek. Veri elemanlarına değer yerleştirmesi için nesnemizin adresini alması lazım. Nesnemizin adresini alması demek this göstericisinin olması demek.

### Constructor sınıfın public bölümünde olmak zorunda mı?

Hayır böyle bir zorunluluk yok. Eğer sınıfın private bölümüne koyarsak, derleyici tarafından çağırıldığı zaman yine sentaks hatası olur. Hatırlarsak clientlar sınıfın sadece public bölümüne erişebiliyorlardı. Hata olan constructor’ın private olması değil, private bir fonksiyonun çağırılması. Constructor’ı private bölümüne yazacağımız özel bazı senaryolar var. (Örnek: Singleton Pattern)

### Singleton Pattern Nedir?

Singleton(tek nesne) tasarım kalıbı, bir sınıfın tek bir örneğini almak için kullanılır.Amaç oluşturulan nesneye global erişim noktası sağlamaktır. Sistem çalıştığı sürece ikinci bir örnek oluşturulmaz, böylelikle istenen nesnenin tek bir defa oluşturulması garanti altına alınacaktır. Singleton nesneler ilk çağırıldıklarında bir kere oluşturulurlar ve sonraki istekler bu nesne üzerinden karşılanır.

Bir sakıncası nesne ömrü : Singleton, nesnenin nasıl silineceğini söylemez. Bellek yönetimi sağlayan dillerde sadece Singleton kalıbı nesneyi serbest bırakabilir (deallocate), çünkü sınıf nesneye private bir referans tutar. Diğer sınıflar nesneyi silebilir, fakat bu yöntem Singleton sınıfı içerisinde boşta kalan referansa neden olur.

### non-static ne demek?

    static keywordu olmayan, yani this göstericisine sahip olan demek
    Derleyicinin yazdığı constructor ın static olma imkanı yok, private olma imkanı yok

### Dinamik Bellek Yönetimi Nedir?

Dinamik bellek yönetimi temelde bir prosesin adres alanının (address space) çalışma zamanındaki ihtiyaçlarına göre genişletilebilmesi ve istenildiğinde sisteme geri verilebilmesidir.

### C++ dinamik dizi nedir?

Dizi boyutunun programın çalışması sırasında artması veya azalmasıdır. C ve C++ programlama dillerinde bellek yönetimi derleme ve çalışma zamanı olmak üzere iki farklı zamanda olur.

### Stack ve Heap farkı nedir?

Stack Memory, işlemcilerin register bilgilerinin tutulduğu yerdir. Burada programınızla ilgili bilgiler (örneğin; lokal değişkenler, referans değişkenler vs) yer almaktadır. Bu memory, geliştirici tarafından değil, compiler tarafından yönetilir. Stack’teki bilgiler kodunuzun derleme aşamasında, direk bellek içine yerleştirildiği için erişimi oldukça hızlıdır.

Heap Memory, bellek üzerinde yer tahsisi yapılan belli bir bölümdür. Bu yer, bellek üzerinde “malloc” fonksiyonu aracılığıyla tahsis edilir ve heap üzerinde allocate edilen(yer tahsisi yapılan) bellek “free” lenerek tekrar kullanım için serbest bırakılır. Heap’teki bellek kullanımı compiler tarafından değil, geliştiriciler tarafından kontrol edilir. Karmaşık programlar oluştururken, genellikle büyük bir bellek alanına ihtiyaç duyarız. Bu durumda Heap Memory kullanırız. Heap üzerinde allocate ettiğimiz bellek operasyonuna “dynamic memory allocation” adı verilir.

Eğer program esnasında boyutları bildirilmiş değişmez bir değer kullanıyorsak stack, değişebilir bir değer kullanıyorsak heap bizim için uygun olacaktır. Stack ve heap kullanımları farklı ve dikkat edilmesi gereken bir konudur. Stack kullanılır ve işi bittikten sonra kendini otomatik olarak bellekten yok eder. Fakat heap‘te bu işi siz yapmalısınız. (Çünkü C’de Garbage Collector yok, ne olduğuna konunun özünü kaçırmamak için girmiyorum.)

Örnek kod parçacığımıza gelecek olursak:

```
void fonksiyon()
{
  //Henuz kullanmadigimiz pointer(Su an stack'de duruyor).  
  char *araba_ismi; 
    // Stack'te yer ayirilan bool deger.
  boolean b = true; 
  
  if(b)
  {
    //Stack uzerinde 20 byte yer ayrildi.
    char araba_markasi[20];    //Heap uzerinde yer ayrildi.
    araba_ismi = new char[];}   //<- araba_markasi burada bellekten silindi ama araba_ismi hala
      duruyor.
}  //<- Burada bir bellek problemi oluşacak, araba_ismi değişkenini
        free(araba_ismi) yazılması gerekiyordu
```
Kullanacağınız yerin boyutunu tam olarak biliyorsanız Stack‘i kullanmak sizin için uygun olacaktır.

Heap, Stack ile karşılaştırıldığında oldukça yavaştır. Çalışma zamanında oluşturulur. Doğru kullanılmaması durumunda bellek sorunları yaratır. Bilgisayarda RAM’de tutulur. Tıpkı Stack gibi.

Öncelikle stack bir LIFO (Last In First Out) data structures’dır. Somutlaştırmak adına LIFO’yu şöyle düşünebiliriz:

### reference nedir?

Bir değişkene erişilmesini sağlayan Pointer benzeri veri tipleridir. Pointer değeri değişkenin adresine işaret eden bir sayı değeriyken, referans, derleyici için sadece bir değişkene ait takma addır. Yani bir değişkene ait referans tanımladığınızda onu başka bir değişken için kullanamazsınız. Standart C++, referansların gerçeklenmesi için özel bir yöntem dayatmaz ama modern derleyiciler bu yetkinliği gerçeklemek için temelde Pointer kullanırlar.

### lvalue nedir?

Locator value. Bir adrese sahip değişkenlere denir. Bu tip değişkenlerin/değerlerin içeriği değiştirilebilir. Bellekte bir yer tutan ve adresi temin edilen değer/ifade (“expression”).

lvalue reference: lvalue değerine ait reference tipidir.

### rvalue nedir?

Reusable/Disposable value. Programın akışı içinde çıkan ara değerlerdir. Ara değer olarak oluşturulduklarından içerikleri direkt olarak programcı kontrolünde değildir. Programcı kontrolüne geçmeleri için bir lvalue’ya atanmaları gerekmektedir.

rvalue reference: rvalue reference tipleri lvalue reference ile aynı özelliklere sahiptir. Farkları, rvalue değerlerine de işaret edebilmeleridir. Programcının özel senaryolarda rvalue içeriğini değiştirmesini sağlarlar.

C++ da metotlara parametre geçirme yöntemlerine baktığımız zaman elimizde bir kaç seçeneğimiz var nedir bunlar:

    “Pass by value”: Bu durumda ise ilgili değerin kendisi metoda kopyalanarak geçirilir ve metot içerisinde bu parametreye yapılan değişiklikler ilgili değere yansıtılmaz. Fazladan bir kopyalama yapıldığı için büyük veri yapılarında performans kaybına yol açar.

    “Pass by reference” : Yani parametrelerin referans (&) operatörü kullanılarak metotlara geçirilmesi. Bu durumda ilgili parametrelerin sadece adresinin (kendisi değil) kopyası tutulur. Bu bir nebze işaretçi kullanılarak parametrelerin geçirilmesine benzer ve metot içerisinde yapılan değişiklikler ilgili parametreleri değiştirir. Parametrenin kendisi kopyalanmaz.

### decltype nedir?

Türden bağımsız (generic) olarak yazılan kodlarda, bazı durumlarda bir ifadenin türünün derleme zamanında derleyici tarafından yapılacak bir çıkarımla anlaşılması gerekiyor. decltype c++11 ile gelen bir özellik. Temel olarak değişkenin tipini belirlemeye yarıyor fakat auto gibi değil. auto kelimesi oldukça sınırlıdır. python “type(değişken)” ifadesi gibi çalışıyor.

### typeid nedir?

typeid ile decltype anahtar kelimeleri birbirlerine benzer olsalar da, çok temel farklılıkları var. typeid, ilgili tipin çalışma zamanında (RTTI mekanizması) tipini öğrenmeye yönelik olsa da, declype ile derleme zamanında bu tipe ilişkin işlemleri gerçekleştirebiliyorsunuz. typeid’ye biraz mesafeli yaklaşılmakta, özellikle aviyonik ya da emniyet kritik yazılımlar geliştiriyorsanız, uzak da durmalısınız (keza çoğu zaman bu özellik kapatılmakta).

### Code Review nedir? Neden Önemlidir?

Kod kalitesini artırmak için bir çok yol izlenebilir; unit test, continuous integration, continuous deployment, agile methodology etc. ancak en önemli yollardan biri code review dır. Bazen kaliteli diyebileceğimiz kodlar yazmaya çalışsak bile öyle anlar geliyor ki proje müdürünüz bir anda gelip bu feature’u bugün yetiştirmemiz gerekiyor deyip spaghetti code yazma süreciniz başlıyor. Bu gibi durumlar hep olacak ancak daha sonrasında geriye dönüp yazmış olduğunuz kodu review-refactoring etmemiz gerekmekte. Yada normal akışında geliştirme yapıyor olsak bile teknik olarak bilgili birisi (genelde takım liderleri) yapmış olduğumuz geliştirmelere bir göz atıp ondan sonra master branch’ine commit/checkin yapıyor olmamız gerekir.

Hem review edecek olan kişi hemde developer için checklist‘inizin olması önemli daha sistematik bir review süreci için oldukça önemlidir.

    Bugs,
    Duplicate Code,
    Login Pages,
    Code Style and Formatting
    etc..

Bu gibi checklist’ler yaparak süreci daha kolay hale getirebiliriz. 

### CI/CD Nedir?

CI/CD, istediğiniz zaman sürdürülebilir bir şekilde yayınlayabileceğiniz yazılım geliştirme yoludur.

“CI/CD”, Sürekli Entegrasyon (CI) ve Sürekli Teslimat (CD) uygulamalarının birleşik uygulamalarını ifade eder.

Sürekli Entegrasyon, CI/CD için bir ön koşuldur ve şunları gerektirir:

Geliştiriciler, değişikliklerini günde birçok kez ana kod dalında birleştirir.
Her kod, otomatik bir kod oluşturma ve test sırasını tetiklemek için birleştirilir. Geliştiriciler ideal olarak sonuçları 10 dakikadan daha kısa sürede alır, böylece çalışmalarına odaklanmaya devam edebilirler.

Sürekli Teslimat uygulamasında ise çoğu durum manuel olarak gerçekleşse de kod değişiklikleri sürekli olarak devreye alınır.

Sisteminizi tekrar eden sürümleri destekleyecek şekilde tasarlayın: Sorunları gerçek zamanlı olarak tespit etmeye yardımcı olan ölçümleri uygulayın. Kodu her zaman test odaklı geliştirmeye çalışın. Küçük yinelemelerle çalışın.

Agile: Çeviklik olarak anılanAgile, süreç engellerini ortadan kaldırmaya ve daha yakın işbirliğine odaklanıyor. Agile, değişimin sürekliliğini vurgular ve yazılım üreticileri olarak yüksek kaliteli yazılımı başarılı bir şekilde tasarlamak, geliştirmek ve sunmak için ihtiyaç duyduğumuz şeyleri genellikle eksik olarak bildiğinizi düşünür. Sürekli entegrasyon/Sürekli teslimat (CI / CD): Sürekli entegrasyon (CI), bir ekibin üyelerinin çalışmalarını entegre ettikleri bir yazılım mühendisliği uygulamasıdır.

### C++ override nedir?

Overriding bir sınıfa ait bir metodun, o sınıftan türetilmiş bir sınıf içerisinde aynı isimli bir metod tanımlanarak, bu metodun temel sınıftaki metodun yerine geçirmeye denir. Bu işlem,bir metodun aynı sınıftan türetilmiş farklı sınıflarda farklı işlere yaramasını sağlar.

Fonksiyon Yüklemesi (Function Overloading) nedir?

//function overloading (fonksiyon yüklenmesi)
int func(int);
int func(int, int);

Aynı isimde biden fazla fonksiyon tanımlamak isteyebiliriz. Çünkü aynı isimli fonsiyonların farklı imzaları (bu fonksiyonların parametrik yapıları birbirinden farklı olur, fonksiyonların parametre değişkenlerinin sayısı ile her bir parametre değişkeninin türü) vardır.

```
// const and function overloading  example
void func(int *ptr);		//1
void func(const int *ptr);	//2
```

İşlevlerin parametreleri gösterici ya da referans değilse bildirimde kullanılan const anahtar sözcüğü bir anlam farklılığı yaratmaz:

```
void func(int x);	//1
void func(const int x);	//2  yeniden bildirim (function redeclaration)
```

Yukarıdaki bildirimler bir fonksiyon yüklemesi oluşturmuyor. Derleyici ikinci deyimi bir “yeniden bildirim” (function redeclaration) kabul eder. Eğer her iki fonksiyon da tanımlansaydı sentaks hatası oluşurdu.

Fonksiyon yüklemesi yapayım derken çift anlamlılık hatası (ambiguity) durumuna düşmememeye dikkat ediniz!

Hangi fonksiyonun çağrılmış olduğunu saptamak derleme zamanında yapılan bir işlemdir. Yani kaynak kod derlenip hedef kod (object code) haline getirildiğinde artık hangi fonksiyonun çağrılmış olduğu bilinmektedir. Çünkü çağrılan fonksiyonun kimliği bir şekilde hedef koda yazılmış olur. Başka bir deyişle “fonksiyon yüklemesi” için programın çalışma zamanı açısından bir ek maliyet söz konusu değildir. Ancak böyle bir araç derleyici üzerindeki yükü de artırır. Derleyici programın boyutunun büyümesine neden olur.

Aynı isimli fonksiyonlar gereksiz yere tanımlanmamalıdır. Fonksiyon yüklemesinin ana amacı özünde aynı işi yapan ancak kodları farklı fonksiyonları aynı isim altında soyutlamaktır. Birden fazla fonksiyonun aynı ismi taşıması kullanıcı kodların işini kolaylaştırmaya yöneliktir. Farklı işler gören fonksiyonların, aynı ismi taşıması kodun okunmasını zorlaştırır. (Necati Ergin)

### (. . .) argumanı (ellipsis) nedir?

Argüman sayısının değişken olmasını istediğimiz fonksiyonlarda kullanırız.

```
void func(int, ...); 
```

Fonksiyonun son parametresinin üç nokta atomu (ellipsis) ile belirtildiğini görüyorsunuz. Bu fonksiyonun birinci parametresine bir argüman gönderilmek zorundadır. variadic parametre (ellipsis) için istenilen sayıda argüman gönderilebilir. Yani func fonksiyonu bir ya da birden fazla argüman ile çağrılabilir. Ayrıca Değişken Şablonlar (“Variadic Templates”) da mevcuttur.

### Function pointer nedir?

Bir fonksiyon adresi başka bir fonksiyona argüman olarak gönderilebilir. Bir fonksiyonun geri dönüş değeri bir fonksiyon adresi olabilir. Elemanları fonksiyon adresleri olan diziler oluşturulabilir. Fonksiyon adresleri C ve C++ dillerinde en sık kullanılan araçlar arasındadır.
Bir fonsiyonun adresini asterix (&) kullanarak gösterebiliriz. 

```
int func(int, int);
int (*fptr)(int, int);
```
          
```fptr``` değişkenine ```func``` fonksiyonunun adresi ilk değer olarak verilebilir ya da atanabilir

```fptr = &func;```

Fonksiyon isimlerinin derleyici tarafından fonksiyonların adreslerine dönüştürülmesinden faydalanarak bu atama deyimi aşağıdaki gibi de yazılabilirdi:

```fptr = func;```

          
```func(10, 20)```

Burada fonksiyon çağrı operatörünün terimi func adresidir. Operatör, func adresinde bulunan kodu, yani func fonksiyonunun kodunu çalıştırır. Fonksiyon çağrı operatörünün ürettiği değer çağrılan fonksiyonun geri dönüş değeridir. Örneğin:

```int result = strcmp(s1, s2);```

Burada strcmp ifadesinin türü, geri dönüş değeri int parametreleri (const char *, const char *) olan bir fonksiyon adresidir. Yani strcmp ifadesi

``` int (*)(const char *, const char *)```  

türüne dönüştürülür.  

``` strcmp(s1, s2) ```

gibi bir fonksiyon çağrısının oluşturduğu ifade ise int türdendir.

Fonksiyonu çağırma iki farklı şekilde yapılabilir:

```
pf()

biçiminde, ya da

(*pf)()

```


```

#include <stdio.h>void func(void(*fp)(void))
{
    printf("func cagrildi\n");
    fp();
    //
}void f()
{
    printf("f cagrildi\n");
    //
}int main()
{
    func(f);
}

```

Yukarıdaki kodda func fonksiyonunun parametre değişkeni bir fonksiyon göstericisi. main fonksiyon içinde func fonksiyonu f fonksiyonunun adresi ile çağrılıyor. func fonksiyonu da adresini aldığı fonksiyonu çağırıyor. Buna popüler olarak ```callback``` deniyor.
          
### Kaynaklar
GeekForGeeks
NecatiErgin
