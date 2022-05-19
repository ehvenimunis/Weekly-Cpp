# Weekly-C++-4

<!-- wp:paragraph -->
<p><strong>OOP nedir?</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Nesne yönelimli programlama (OOP) paradigması, gerçek hayatta olan varlıkları yazılım dünyasında modellemekte kullandığımız, her işlevin nesneler olarak soyutlandığı bir programalama yaklaşımıdır. Tıpkı gerçek hayatta olduğu gibi yazılımda da bu sayede nesnelerimizin öznitelikleri, davranışları olacaktır.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>Sınıf Hiyerajileri nasıl olur?</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Hiyerarşi düzeninde; genel, kapsayıcı sınıfa <code>superclass</code> (üst sınıf). Bunlardan türeyen sınıflara da <code>subclasses</code> (alt sınıflar) denir. Bu hiyerarşi ile birlikte alt sınıflar, üst sınıfların özelliklerini ve davranışlarını almaktadır.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Nesne yönelimi programlama ilkeleri nelerdir?</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Nesne yönelimli programalama 4 temel ilke üzerine kuruludur ve bir dilin, nesne yönelimli programlamayı uyguluyor denmesi için 4 koşulu da sağlıyor olması gerekiyor. Bunlar; <code>Encapsulation</code>, <code>Abstraction</code>, <code>Inheritance</code>, <code>Polymorphism</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1801,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="https://salihspacehome.files.wordpress.com/2022/05/resim-5.png?w=900" alt="" class="wp-image-1801"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":4} -->
<h4>Encapsulation (Kapsülleme)</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Herhangi bir nesnenin metotlarını, verilerini veya değişkenlerini diğer nesnelerden saklayarak ve bunlara erişimini sınırlandırarak yanlış kullanımlardan koruyan bir konsepttir. Bir nesne üzerinde hem veri soyutlama hem de kontrol soyutlaması yapılıyor ise buna sarma adı verilir. Çoğu programlama dilleri kapsüllemeyi aşağıda sıraladığımız erişim belirteçleri ile desteklerler.</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><li><strong>public:</strong> Erişimin her yerden yapılabileceği anlamı taşıyor.</li><li><strong>private:</strong> Erişimin tanımlandığı sınıf içerisinden yapılabileceği anlamı taşıyor.</li><li><strong>protected:</strong> Sadece tanımlandığı sınıfın içinden veya o sınıftan türetilmiş diğer sınıfların içinden erişilebilir.</li></ol>
<!-- /wp:list -->

<!-- wp:heading {"level":4} -->
<h4><a href="https://github.com/yusufyilmazfr/tasarim-desenleri-turkce-kaynak#abstraction-soyutlama"></a>Abstraction (Soyutlama)</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Farklı kod parçalarının kompleks kısımlarını, sahip oldukları ortak davranışlar, amaçlar, karakteristik özellikler arkasında saklamak sayesinde daha anlaşılır ve kolay kullanılabilir kod yazmaktır abstraction.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4>Inheritance (Kalıtım)</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Kalıtım, mevcut sınıfların üzerine yeni sınıflar oluşturma yeteneğidir. Bu sayede türetilen sınıf, türediği sınıfın özelliklerini devralır. Kalıtımın en büyük yararı kodun yeniden kullanılmasıdır. Mevcut sınıftan biraz farklı bir sınıf oluşturmak istiyorsak, kodu kopyalamamıza gerek yoktur. Bunun yerine, varolan sınıfı genişletir ve ekstra işlevselliği alt sınıfa koyarız.&nbsp;&nbsp;&nbsp;&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4>Polymorphism (Çok Biçimlilik)</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Bir nesnenin başka bir nesne gibi davranabilmesi, kullanılabilmesi. Biraz daha açık bir ifade ile: alt sınıfların, üst sınıflara ait olan davranışlarını başka bir biçimde gerçekleştiriyor olması olayıdır.</p>
<!-- /wp:paragraph -->

     
### Kaynaklar
GeekForGeeks
NecatiErgin
https://en.cppreference.com/w/
https://github.com/yusufyilmazfr

