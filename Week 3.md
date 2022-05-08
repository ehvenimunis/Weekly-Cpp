# Weekly-C++-3

<!-- wp:paragraph -->
<p><strong>CLASSES vs STRUCTS</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph {"align":"justify"} -->
<p class="has-text-align-justify">Struct birçok özellik bakımından sınıflara benzemektedirler. Fakat <strong>verilerin tutuldukları alanlar birbirinden ayrılır</strong> ve en önemli farkları da budur. <strong>Yapılar stack (yığın) alanında tutulur</strong>ken sınıflar heap (öbek) alanında tutulur. Bu sebep ile yapılar belli büyüklükteki verileri tutabilir. Çünkü <strong>stack alanı çok sınırlı bir veri alanıdır.</strong> Büyük veriler stack alanına yüklenmeye çalışıldığında <strong>stack overflow</strong> olarak adlandırılan <strong>yığın taşması</strong> meydana gelir.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph {"align":"justify"} -->
<p class="has-text-align-justify">Özellikle metodlara veriler aktarırken bu verileri sınıf içerisinde tanımladığımızda, tüm veriler metoda aktarılacağını sadece bu verilerin öbekteki başlangıç adresi aktarılır ve ilgili parametrenin de bu adresteki verilere işaret etmesi sağlanmış olur. Böylece büyük boyutlu verileri stack’ta kopyalayarak gereksiz miktarda bellek harcanmasının önüne geçilmiş olunur. Ancak küçük boyutlarda veriler ile çalışırken bu verileri sınıflar içerisinde kullandığımızda bu kezde gereksiz yere bellek kullanıldığı öbek şişer ve performans düşer. Bu konudaki uzman görüş 16 byte’tan küçük veriler için yapıların kullanılması, 16 byte’tan büyük veriler için ise sınıfların kullanılmasıdır.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Diğer taraftan yapılar ile sınıflar arasında başka farklılıklarda vardır. Örneğin bir yapı için varsayılan yapıcı metod (default constructor) yazamayız. Derleyici hatası alırız. Ancak bu değişik sayıda parametreler alan yapıcılar yazmamızı engellemez. Oysaki sınıflarda istersek sınıfın varsayılan yapıcı metodunu kendimiz yazabilmekteyiz. l &nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Bir yapı içersinde yer alan constructor metod(lar) içinde tanımlamış olduğumuz alanlara başlangıç değerlerini atamak zorundayız. Oysaki bir sınıftaki constructor(lar) içinde kullanılan alanlara başlangıç değerlerini atamaz isek, derleyici bizim yerimize sayısal değerlere 0, boolean değerlere false vb... gibi başlangıç değerlerini kendisi otomatik olarak yapar. Ancak derleyici aynı işi yapılarda yapmaz. Bu nedenle bir yapı içinde kullandığımız constructor(lar)daki tanımlamış olduğumuz alanlara mutlaka ilk değerlerini vermemiz gerekir.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Yapı kullanımı sınıf kullanımına göre <strong>erişim hızı bakımından yüksek ve daha az maliyetli</strong>dir.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Birden fazla struct'ı iç içe kullanabiliriz. Bu duruma Nested Structures denir.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><li><strong>Struct:</strong> Kendiliğinden değiştirilmeden halinde (default) <strong>public</strong>&nbsp;öğelere sahiptir. Çok nesneye dayalı işlem içermeyen, düz yapılarınız için bunu kullanabilirsiniz.</li><li><strong>Class:</strong>&nbsp;Kendiliğinden değiştirilmeden halinde (default) <strong>private</strong>&nbsp;öğelere sahiptir. Yapılar arasında işlem yapıldığında, öğeler arasında fonksiyonel aksiyonlara ihtiyaç duyduğunuzda bunu kullanabilirsiniz.&nbsp;</li></ul>
<!-- /wp:list -->

<!-- wp:image {"id":1748,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://salihspacehome.files.wordpress.com/2022/04/resim-3.png?w=876" alt="" class="wp-image-1748"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong>ENUM vs STRUCTS</strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1760,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://salihspacehome.files.wordpress.com/2022/05/resim.png?w=960" alt="" class="wp-image-1760"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"fontSize":"medium"} -->
<h2 class="has-medium-font-size" id="d005"><strong>Sanal Fonksiyona neden ihtiyaç duyulur ?</strong></h2>
<!-- /wp:heading -->

<!-- wp:paragraph {"align":"justify"} -->
<p class="has-text-align-justify" id="f036">Sanal fonksiyonları çok biçimli programlama tekniği (polymorphism) ile kullanılır. Bir sınıfın fonksiyonunun miras alan diğer sınıflar tarafından kullanılmasını sağlamak için virtual anahtar kelimesiyle tanımlarız. Bunun nedenini bir örnek ile açıklayayım. Diyelim ki bir kare sınıfımız var. Bu sınıf için alan hesaplayabiliriz, çizim yaptırabiliriz , çevre hesaplayabiliriz. Diğer bir sınıf olan üçgen ise kare’den miras alsın. Üçgen içinde aynı fonksiyonları kullanabiliriz değil mi ? Bunu yapabilmemiz için kare sınıfımızdaki fonksiyonlarımızı virtual anahtar kelimesiyle deklare etmemiz gerekir yani prototiplerini virtual ön eki ile yazarız.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>İlk bakışta, ana sınıf içinde bildirimi yapılan sanal bir fonksiyonunun ana sınıftan türetilen bir sınıf içinde yeniden tanımlanması, fonksiyon için çoklu işlem tanımlama (overloading) işlemi ile benzerlik gösterir. Ancak, türetilen sınıf içindeki sanal fonksiyonun yeniden tanımlanmasında kullanılan bildirim yapısı ana sınıf içindeki sanal fonksiyon ile aynı olmalıdır. Fonksiyon çoklu işlem tanımlama işleminde fonksiyon parametre sayısı ve veri türlerinden birisi mutlaka farklı olmalıdır. Ayrıca, fonksiyonun geri döndürdüğü değer de farklı olabilir. Eğer türetilen sınıf içindeki sanal fonksiyon bildirim yapısı ana sınıf içindekinden farklı olursa, fonksiyonun sanal özelliği kaybolur ve fonksiyon çoklu işlem tanımlama işlemi uygulanır.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>Linked List Nedir?</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>Linked list</strong>, pointerlar kullanılarak oluşturulmuş bir listedir. Bir linked list, sabit bir boyuta sahip değildir. Program çalışıyorken boyut( <strong>size</strong>) büyüyebilir ya da küçülebilir. <strong>Tree</strong>, pointerlar kullanılarak oluşturulmuş bir başka veri yapısıdır.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1770,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://salihspacehome.files.wordpress.com/2022/05/resim-2.png?w=759" alt="" class="wp-image-1770"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Bir linked list, dinamik veri yapısının basit bir örneğidir. Dinamik veri yapısı olarak adlandırılmasının sebebi, sahip olduğu her değişkenin new operatörüyle dinamik olarak oluşturulmasıdır. Linked listler head ve node’lardan oluşur.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1767,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://salihspacehome.files.wordpress.com/2022/05/resim-1.png?w=619" alt="" class="wp-image-1767"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Her bir node, kendinden önceki ve sonraki node’a bağlıdır. Bu da, linked list’te ileri ve geri ilerleyebilmemizi sağlar. Bütün node’lar aynı tipte olmalıdır. Örneğin yukarıdaki örnekte her node’un bir string tipinde ve integer tipinde elemanı vardır. Ve kendisiyle aynı tipteki diğer node’lara işaret eder.(pointerlar yardımı ile)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>C++’ta node’lar struct ya da sınıf olarak implement edilirler.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Yukarıdaki örnek için, şu şekilde bir struct tanımlanabilir.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>struct ListNode
 
{
 
string item;
 
int count;
 
ListNode *link;
 
}
 
Typedef ListNode* ListNodePtr;</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>simple example:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>// A simple C++ program for traversal of a linked list
#include &lt;bits/stdc++.h&gt;
using namespace std;

class Node {
public:
	int data;
	Node* next;
};

// This function prints contents of linked list
// starting from the given node
void printList(Node* n)
{
	while (n != NULL) {
		cout &lt;&lt; n-&gt;data &lt;&lt; " ";
		n = n-&gt;next;
	}
}

// Driver code
int main()
{
	Node* head = NULL;
	Node* second = NULL;
	Node* third = NULL;

	// allocate 3 nodes in the heap
	head = new Node();
	second = new Node();
	third = new Node();

	head-&gt;data = 1; // assign data in first node
	head-&gt;next = second; // Link first node with second

	second-&gt;data = 2; // assign data to second node
	second-&gt;next = third;

	third-&gt;data = 3; // assign data to third node
	third-&gt;next = NULL;

	printList(head);

	return 0;
}

/*
<strong>Output: 

 1  2  3</strong>
*/
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>Temel mantık olarak, linked list’te her bir eleman(node)&nbsp;tutması gereken dataya ilaveten kendinden bir sonra gelecek olan node’un adresini tutar. Dolayısıyla her linked list node’u kendisinden bir sonraki node’un yerini bilir. Bu da linked listlerin bellekte sıralanış şekli açısından bize esneklik sağlar. Örneğin, bir array tanımladığınızda arrayın boyutunu başlangıçta<em><strong> int[] myArray = new int[10];</strong></em>&nbsp; şeklinde statik olarak vermeniz gerekir. Bu da size bellekte sıralı olarak arka arkaya ayrılmış 10 intlik bir alan rezerve etmek etmektir. Kullansanız da kullanmasanız da bu alan sizin için ayrılır. Hatta bellek alanları ardışık rezerve edildiği için pointer ile ilk index adresini alıp diğer elemanlara, ilk adrese bellekte 4er bytelık değerler ekleyerek ulaşabilirsiniz de. Ancak linked list’te böyle bir zorunluluk yok. Linked listin her node’u bir diğerinin adresini bildiğinden, node’lar bellekte bambaşka boş buldukları alanlara yerleşebilirler. Dolayısıyla linked listin eleman sayısı da dinamik olarak artabilir. Madem öyle linked list’in ortalarındaki elemanlarına nasıl ulaşıyoruz gibi bir soru kafanıza takılabilir. 1. elemandan başlayıp traverse ederek.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1775,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://salihspacehome.files.wordpress.com/2022/05/resim-3.png?w=756" alt="" class="wp-image-1775"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Yazının başında da bahsettiğim gibi, linked listin her bir elemanına node denir. Linked list isminden de anlaşılacağı üzere birbirine bağlı node’lardan oluşur. Node’lar temelde (simple one way node için) iki bilgiyi tutar. Bunlar;</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1777,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://salihspacehome.files.wordpress.com/2022/05/resim-4.png?w=680" alt="" class="wp-image-1777"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><strong>&nbsp; 1.</strong> Tutulacak olan veri -&gt; Data<br><strong>&nbsp; 2.</strong> Kendinden bir sonraki node’ın adresi -&gt; Next</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Genelde bizim linked liste dair tek bildiğimiz şey ilk elemanın yani head’in adresi ve uygulamaya göre tailin yani son node’un adresidir. Bazı uygulamalarda son nodeun adresinin tail olarak bir değişkende tutulmadığını görebilirsiniz. Böyle durumlarda son node’a ulaşmanın maliyeti O(n) olacaktır. Tutulduğu durumlarda ise O(1). Diğer elemanların yerlerini ise hiç bir şekilde bilemeyiz. E o zaman diğer elemanlara nasıl ulaşacağız. Tabiki head üzerinden… Aynı kervan saraylarda dolaşırcasına, adresini bildiğimiz ilk node’u alır, onun nexti üzerinden diğer node’a oradan diğer node ilerleyerek aradığımız elemanı buluruz. Şanslı isek aradığımız eleman ilk node’da çıkar ve linked list için search işlemi best case’de O(1) olurken, en kötü ihtimalle aradığımız eleman listede olmaz ve worst case’imiz O(n) olur.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>ilk eleman : head<br>ikinci eleman : head.next<br>üçüncü eleman : head.next.next </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>……<br>son eleman (tail) : head.next.next.next… = tail –&gt; tail.next =&gt; null</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Peki linkedin list kullanmanın avantajlarını nerede görürüz.</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><li>Dinamic memory yerleşme yapısı sayesinde daha az memory israfı.</li><li>Dinamik boyutlu olarak kullanılabilmesi.</li><li>Başa ve sona ekleme/çıkarma işlemlerinin O(1) komplexitysi ile yapılabilmesi.</li></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>Peki linked list kullanmanın dezavantajları nelerdir.</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><li>Random access’e izin vermemesi.</li><li>Her bir node’un datanın dışında, kendinden bir sonra gelecek node’un adresini de tutmasının getirdiği extra memory yükü.</li></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><strong>Dönüştüren kurucu fonksiyon <em>“(conversion constructor)</em> nedir?</strong></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>convert constructor C++ da bildiğimiz içerisine parametre alan constructor a denmektedir. Peki sizce neden böyle bir ad konulma gereği duyulmuş bu parametre alan constructor tipine?</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>#include &lt;iostream&gt;
using namespace std;

class Test {
    int var;

public:
    Test(int v = 0) : var(v) {}
    int getVar() const { return this-&gt;var; }
};

void function(Test t1) {
    cout &lt;&lt; t1.getVar() &lt;&lt; endl;
}

int main() {
    function(50);
    return 0;
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>Gördüğünüz üzere function fonksyonunun giriş parametresi class Test tipinden tanımlanmıştır. Ozaman demek ki bizim function fonksiyonuna Test nesnesi vermemiz gerekir. Oysa biz napıyoruz açıkça bir int parametre veriyoruz </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>İşte burada convert constructor dediğimiz olay devreye giriyor! 50 sayısı Test için yazdığımız constructora yada birden fazla varsa sırayla, verilerek Test nesnesine cast edilmeye yani 50 sayısı ile bir giriş parametresi oluşturulmaya çalışılıyor…</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Burada argümanlar bire bir uyuştuğu için, Test sınıfının constructor ı bir tane int parametre alır, bu casting işi başarılı oluyor ve Yığında bir adet Test nesnesi oluşturuluyor. Bu yüzden bu constructorlar convert constructor olarak adlandırılmıştır.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:spacer {"height":"350px"} -->
<div style="height:350px" aria-hidden="true" class="wp-block-spacer"></div>
<!-- /wp:spacer -->











     
### Kaynaklar
GeekForGeeks
NecatiErgin
