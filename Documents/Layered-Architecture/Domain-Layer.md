# Domain Layer

Uygulamanın merkezi burası olacaktır. Çözülmek istenen soruna ait tüm iş kurallarının yer aldığı katmandır. Bu katman içerisinde varlıklar (entities), değer objeleri (value objects), domain varlıklarımız (aggregates), yaratıcı sınıflarımız (factories) ve arayüzler (interfaces) yer alacaktır. Bu katman olabildiğince bağımlılıklardan uzak tutulmalıdır. Diğer katmanları referans olarak almaması gerektiği gibi olabildiğince 3rd party kütüphaneler de eklenmemelidir.

Bu katman, uygulamanın iş mantığına odaklanır ve sistemdeki verilerin nasıl işleneceğini belirler.

**Domain katmanı, yazılımın çekirdek iş mantığını ve iş süreçlerini temsil eder. Bu katman, iş alanınızın gerçek dünyasındaki kavramları, kuralları ve ilişkileri ifade eder.**

Domain katmanı genellikle aşağıdaki bileşenlerden oluşur:

Entity (Varlık): Gerçek dünyadaki nesnelerin yazılım modellemesidir. Bir örneği takip ederken değişebilirler ve birbirleriyle ilişkilendirilebilirler. Örneğin, bir e-ticaret uygulamasında "Ürün" veya "Müşteri" gibi varlıklar olabilir.

Value Object (Değer Nesnesi): Sadece değerlerini temsil eden, ancak bir kimlikleri olmayan nesnelerdir. Değer nesneleri genellikle değişmez ve eşsiz değerlere sahiptir. Örneğin, bir tarih aralığı veya coğrafi konum bir değer nesnesi olabilir.

Aggregate (Toplu): İlişkilendirilmiş varlık ve değer nesnelerinin bir koleksiyonudur. Bir toplu, birbirine bağlı nesneler arasında bir inceleme noktası sağlar. Örneğin, bir e-ticaret uygulamasında bir "Sipariş" toplu olarak düşünülebilir, içinde "Sipariş Satırı" gibi alt öğeler bulunabilir.

Repository (Depo): Domain katmanı, veri erişim işlemlerinin arayüzlerini sağlamak için bir depoya sahip olabilir. Bu, veritabanı işlemlerini gizler ve domain nesneleriyle iletişim kurar. Örneğin, bir "ÜrünDeposu" veritabanı işlemlerini yönetebilir ve iş mantığına uygun ürün nesneleri döndürebilir.

Service (Hizmet): Belirli iş mantığı işlemlerini gerçekleştirmek için kullanılır. Eğer bir işlem birden çok varlık veya değer nesnesini kapsıyorsa, genellikle bir servis kullanılır. Örneğin, bir ödeme işlemini gerçekleştirmek için bir "ÖdemeServisi" olabilir.

Domain Events (Domain Olayları): Domain katmanı, domaindeki önemli olayları temsil eden olaylar yayabilir. Bu, diğer katmanlara belirli bir durumun veya eylemin gerçekleştiğine dair bilgi sağlar. Örneğin, bir siparişin tamamlandığını belirten bir "SiparişTamamlandı" olayı olabilir.


Örnek bir senaryoda, bir e-ticaret uygulamasını ele alalım:

Varlık (Entity): "Ürün", "Müşteri"
Değer Nesnesi (Value Object): "Tarih Aralığı", "Coğrafi Konum"
Toplu (Aggregate): "Sipariş" (Sipariş içinde Sipariş Satırları gibi)
Depo (Repository): "ÜrünDeposu"
Hizmet (Service): "ÖdemeServisi"
Domain Olayları (Domain Events): "SiparişTamamlandı"

Domain katmanı, iş mantığını temsil ederken, diğer katmanlarla (örneğin, altyapı katmanıyla) doğrudan iletişim kurmaz. Bunun yerine, diğer katmanlar aracılığıyla iletişim kurar ve katmanlar arasındaki bağımlılığı en aza indirir. Bu, yazılımın daha esnek, bakımı daha kolay ve değişikliklere daha uygun olmasını sağlar.