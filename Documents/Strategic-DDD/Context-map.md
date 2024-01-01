# Context Maps and Integration Patterns(Bağlam Haritaları ve Entegrasyon Modelleri)

Bağlamlarımızın ne olduğunu ve nasıl ilişkili olduklarını öğrendikten sonra, bunları nasıl bütünleştireceğimize karar vermeliyiz. Bu birkaç önemli soruyu içerir:

- Bağlam sınırları nerede?
- Bağlamlar teknik olarak nasıl iletişim kuracak?
- Bağlamların domain modelleri arasında nasıl harita oluşturacağız (yani yeknesak bir dilden diğerine nasıl çeviri yapıyoruz)?
- Yukarı yönde meydana gelen istenmeyen veya sorunlu değişikliklere karşı nasıl korunacağız?
- Aşağı akış bağlamlarında sorun yaratmaktan nasıl kaçınacağız?

Yukarıdaki sorulara context map ile cevap veriyoruz.

Context map, bir projedeki farklı "bounded context"leri (sınırlı bağlam) ve bu bağlamlar arasındaki ilişkileri gösteren bir araçtır. Context map'in ana amaçları şunlardır:

- Karmaşıklığı Yönetme:

Farklı ekiplerin ve bileşenlerin bir arada çalıştığı büyük ve karmaşık sistemlerde, context map karmaşıklığı yönetmek için bir harita sunar. Bu, her bir bounded context'in sınırlarını belirlemek ve bu bağlamlar arasındaki ilişkileri anlamak açısından değerlidir.

- Dilin ve Modelin Birleştirilmesi:

Proje içindeki her bounded context, kendi içinde tutarlı bir dil ve model kullanır. Context map, bu dilleri birbirine bağlamak ve farklı bağlamlar arasında anlam kaybını önlemek için kullanılır.

- Ekipler Arası İletişimi Kolaylaştırma:

Farklı ekipler genellikle farklı bounded context'ler üzerinde çalışır. Context map, ekipler arasında nasıl iletişim kurulacağını ve işbirliği yapılacağını gösterir.

- Proje Stratejisinin Belirlenmesi:

Projenin stratejik hedeflerini anlamak ve bu hedeflere nasıl ulaşılacağını belirlemek için context map kullanılır. Bu, proje ekibinin ve paydaşlarının projenin genel yönünü anlamasına yardımcı olur.

- Birleşik Bir Görünüm Sağlama:

Tüm projeyi tek bir görselde birleştirerek, projenin bütünlüğünü ve tüm bileşenlerin nasıl bir araya geldiğini gösterir. Bu, proje paydaşlarına ve ekiplere genel bir bakış sunar.

Context map, projenin genel tasarımını ve organizasyonunu anlamak, farklı bağlamlar arasında uyumu sağlamak ve proje ekibini yönlendirmek için kullanılır. Ayrıca, projenin evrimleşen gereksinimlerine ve değişikliklerine esnek bir şekilde uyum sağlamak için kullanılan bir araçtır.


## Example

### Bağlam Haritası

**Bağlam haritası, proje içindeki farklı sınırlı bağlamları (bounded context) ve bu bağlamlar arasındaki ilişkileri gösterir.**


1. Müşteri Yönetimi Bounded Context'i

- Tanım: Müşteri bilgilerini yöneten, kullanıcı hesaplarını takip eden ve müşteri iletişimini sağlayan bir bağlamdır.

- Sınırlar:
    Müşteri Bilgileri Servisi
    Kullanıcı Hesapları Servisi
- İlişkiler:
    Sipariş Yönetimi ile Etkileşim
    Pazarlama Kampanyaları ile Etkileşim

2. Sipariş Yönetimi Bounded Context'i

-Tanım: Müşteri siparişlerini işleyen, stok durumunu takip eden ve sipariş durumlarını yöneten bir bağlamdır.

- Sınırlar:
    Sipariş İşleme Servisi
    Stok Takibi Servisi

- İlişkiler:
    Müşteri Yönetimi ile Etkileşim
    Fatura Servisi ile Etkileşim

3. Fatura Bounded Context'i

- Tanım: Siparişler için fatura oluşturan, ödeme durumunu yöneten bir bağlamdır.

- Sınırlar:
    Fatura Oluşturma Servisi
    Ödeme İşlemleri Servisi

- İlişkiler:
    Sipariş Yönetimi ile Etkileşim
    Müşteri Yönetimi ile Etkileşim

4. Pazarlama Bounded Context'i

- Tanım: Pazarlama kampanyalarını yöneten, indirimleri işleyen ve müşterilere özel teklifler sunan bir bağlamdır.

- Sınırlar:
    Kampanya Yönetimi Servisi
    İndirim İşlemleri Servisi

- İlişkiler:
    Müşteri Yönetimi ile Etkileşim
    Sipariş Yönetimi ile Etkileşim

5. Raporlama Bounded Context'i

- Tanım: İş zekası ve raporlama için veri analizi sağlayan bir bağlamdır.

- Sınırlar:
    Veri Analizi Servisi
    Raporlama Servisi

- İlişkiler:
    Tüm Bağlamlar ile Bilgi Alışverişi

6. Altyapı Bounded Context'i

- Tanım: Sistem altyapısını yöneten ve genel sistem bileşenlerini içeren bir bağlamdır.

- Sınırlar:
    Kimlik Doğrulama Servisi
    İletişim Servisi

- İlişkiler:
    Tüm Bağlamlar ile Teknolojik Bağlamda İlişki

Bu bağlam haritası, projenin farklı işlevselliğini temsil eden ve birbirinden bağımsız çalışan bounded context'leri gösterir. İlişkiler, her bir bağlamın diğerleriyle nasıl etkileşimde bulunduğunu açıklar. Bu bağlam haritası, proje ekipleri arasında bir anlayış oluşturmak ve paydaşlara projenin bütünlüğünü göstermek için kullanılabilir.


## Sources

https://www.infoq.com/articles/ddd-contextmapping/

https://www.turkninja.com/2020/08/strategic-domain-driven-design.html