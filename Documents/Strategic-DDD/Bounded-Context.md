# Strategic Domain-Driven Design
 - Bounded Context (Sınırlı Bağlam)
 - Subdomain (Alt Alan)
 - 	Context Map (Bağlam Haritası)
 - 	Shared Kernel (Paylaşılan Çekirdek)
 - 	Anti-Corruption Layer (Bozulma Karşıtı Katman)
 - 	Ubiquitous Language
 - 	Big Ball of Mud (Büyük Çamur Topu)

## Bounded Context (Sınırlı Bağlam)

Bounded Context is a central pattern in Domain-Driven Design. It is the focus of DDD's strategic design section which is all about dealing with large models and teams. DDD deals with large models by dividing them into different Bounded Contexts and being explicit about their interrelationships.

// Sınırlanmış Bağlam, Etki Alanı Odaklı Tasarım'da merkezi bir desendir. DDD'nin büyük modeller ve ekiplerle ilgilenmekle ilgili stratejik tasarım bölümünün odak noktasıdır.DDD, büyük modelleri farklı Sınırlı Bağlamlara bölerek ve aralarındaki ilişkiler konusunda açık olarak ele alır.

![image](https://github.com/ibrahimdoss/Domain-Driven-Design/blob/main/Images/sketch.png)

DDD is about designing software based on models of the underlying domain. A model acts as a UbiquitousLanguage to help communication between software developers and domain experts. It also acts as the conceptual foundation for the design of the software itself - how it's broken down into objects or functions. To be effective, a model needs to be unified - that is to be internally consistent so that there are no contradictions within it.

// "DDD, temel alanın modellerine dayalı olarak yazılım tasarlamakla ilgilidir. Bir model, yazılım geliştiricileri ile alan uzmanları arasındaki iletişime yardımcı olacak olan Evrensel Dil (Ubiquitous Language) olarak işlev görür. Aynı zamanda yazılımın tasarımı için kavramsal temel olarak da işlev görür - nasıl nesnelere veya işlevlere bölündüğü. Etkili olabilmesi için bir modelin birleşik olması gerekir - yani içsel olarak tutarlı olmalıdır, böylece içinde çelişkiler bulunmaz."

As you try to model a larger domain, it gets progressively harder to build a single unified model. Different groups of people will use subtly different vocabularies in different parts of a large organization. The precision of modeling rapidly runs into this, often leading to a lot of confusion. Typically this confusion focuses on the central concepts of the domain. Early in my career I worked with a electricity utility - here the word "meter" meant subtly different things to different parts of the organization: was it the connection between the grid and a location, the grid and a customer, the physical meter itself (which could be replaced if faulty). These subtle polysemes could be smoothed over in conversation but not in the precise world of computers. Time and time again I see this confusion recur with polysemes like "Customer" and "Product".

Geniş bir alanı modellemeye çalıştıkça, tek bir birleşik model oluşturmak giderek zorlaşır. Büyük bir organizasyonun farklı grupları farklı kısımlarda hafif farklı terimleri kullanacaktır. Modellemenin kesinliği, genellikle birçok kafa karışıklığına yol açan bu durumla hızla karşılaşır. Genellikle bu karışıklık, temel alanın merkezi kavramlarına odaklanır. **Kariyerimin erken dönemlerinde bir elektrik hizmetleri şirketiyle çalıştım - burada "sayacı" kelimesi, organizasyonun farklı kısımlarında hafif farklı şeyleri ifade ediyordu: bu, şebeke ile bir konum arasındaki bağlantı mıydı, şebeke ile bir müşteri arasındaki bağlantı mıydı, fiziksel sayaç kendisi miydi (arızalıysa değiştirilebilirdi).** Bu hafif çokanlamlılıklar konuşmada düzeltilebilirdi, ancak bilgisayarların kesin dünyasında düzeltilemezdi. Kez ve kez bu tür çokanlamlılıkların, "Müşteri" ve "Ürün" gibi, tekrar ettiğini görüyorum.

In those younger days we were advised to build a unified model of the entire business, but DDD recognizes that we've learned that "total unification of the domain model for a large system will not be feasible or cost-effective" [1]. So instead DDD divides up a large system into Bounded Contexts, each of which can have a unified model - essentially a way of structuring MultipleCanonicalModels.

O genç günlerimizde bize, bütün işin birleşik bir modelini oluşturmamız öneriliyordu, ancak DDD, "büyük bir sistem için alan modelinin tam birleşik olmanın uygun veya maliyet etkili olmayacağını öğrendik" [1] şeklinde bir tanıma sahiptir. Bu nedenle, DDD, büyük bir sistemi Bounded Context'leri olan birimlere böler; her biri birleşik bir modelle sahip olabilir - temelde Birden Çok Kanonik Modeli yapılandırma yolu.

Bounded Contexts have both unrelated concepts (such as a support ticket only existing in a customer support context) but also share concepts (such as products and customers). Different contexts may have completely different models of common concepts with mechanisms to map between these polysemic concepts for integration. Several DDD patterns explore alternative relationships between contexts.


Bounded Context'ler, ilişkisiz kavramları (örneğin, bir destek talebinin sadece müşteri destek bağlamında var olması gibi) ve aynı zamanda kavramları paylaşır (örneğin, ürünler ve müşteriler gibi). Farklı bağlamlar, entegrasyon için bu çokanlamlı kavramlar arasında eşleme mekanizmalarıyla birlikte ortak kavramların tamamen farklı modellerine sahip olabilir. Birkaç DDD deseni, bağlamlar arasındaki alternatif ilişkileri keşfeder.

Various factors draw boundaries between contexts. Usually the dominant one is human culture, since models act as Ubiquitous Language, you need a different model when the language changes. You also find multiple contexts within the same domain context, such as the separation between in-memory and relational database models in a single application. This boundary is set by the different way we represent models.

Çeşitli faktörler, bağlamlar arasında sınırlar çizer. Genellikle baskın olan faktör insan kültürüdür, çünkü modeller Evrensel Dil olarak işlev gördüğünden dil değiştiğinde farklı bir modela ihtiyaç duyarsınız. Aynı alan bağlamı içinde de birden çok bağlam bulabilirsiniz, örneğin tek bir uygulamada bellek içi ve ilişkisel veritabanı modelleri arasındaki ayrım. Bu sınır, modelleri temsil etme şeklimizin farklı olması nedeniyle belirlenir.

DDD's strategic design goes on to describe a variety of ways that you have relationships between Bounded Contexts. It's usually worthwhile to depict these using a context map.

DDD'nin stratejik tasarımı, Bounded Context'ler arasındaki ilişkileri açıklamanın çeşitli yollarını tanımlar. Genellikle bu ilişkileri göstermek için bir bağlam haritası kullanmak faydalıdır.

## Summary

- İş süreçleri birbiri içine geçebilir ve hatta çakışabilir. Buradan aynı kelime farklı anlamlara gelebilir veya farklı kelimeler farklı bağlamlarda aynı anlama gelebilir.

- Büyük bir alanı modellemek, tek bir birleşik model oluşturmayı zorlaştırır. Modelin keskinliği kafa karısıklığına yol açar. Buna örnek olarak yukarıda martin fowler'ın elektrik şirketin de çalışırken sayac kavramı örnek verilebilir.

- Her bir Bounded Context, kendi içinde birleşik bir modele sahiptir, bu da Birden Çok Kanonik Modelin bir yapılandırmasıdır.

- Bounded Context'ler, birbirinden bağımsız ve/veya ortak kavramları içerebilir. Farklı bağlamlar, aynı kavramlar için farklı modellere sahip olabilir ve entegrasyon için mekanizmalar sağlar.

## Real World Example

e-ticaret platformun da müşteri ilişkileri, envanter yönetimi, ödeme islemleri, kampanya yönetimi gibi farklı alanlar mevcut. Her biri kendi içinde benzersiz kurallara, süreçlere sahip. Bu durumda her bir alanı ayrı bir Bounded Context olarak düşünebiliriz.

#### Müşteri Siparişleri Bounded Context'i:

Amaç: Sipariş oluşturma, sipariş takibi ve teslimat yönetimi gibi sipariş süreçleriyle ilgili konuları içerir.

Model: Sipariş, sepet, teslimat gibi terimler bu bağlamda tanımlanır.

#### Envanter Yönetimi Bounded Context'i:

Amaç: Ürün katalogu, stok takibi ve tedarikçi ilişkileri gibi envanter odaklı konuları içerir.

Model: Ürün, stok, kategori gibi terimler bu bağlamda anlam bulur.


Müşteri siparişleri context'i, Envanter Bounded Context'i ile etkileşim içindedir. Ancak her iki bağlam da kendi içinde tutarlı bir modele sahiptir. Bu sayede her bir Bounded Context, kendi sorumluluk alanındaki karmaşıklığı ele alabilir ve daha iyi ölçeklenebilir


## Sources:

https://martinfowler.com/bliki/BoundedContext.html










