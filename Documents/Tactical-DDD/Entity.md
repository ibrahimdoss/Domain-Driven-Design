# Entity (Varlık)

Entity, bir iş domain'inde belirli bir kimliğe sahip ve sürekli olarak izlenebilen, değişebilen nesneleri temsil eder. Entity'ler genellikle bir yaşam döngüsüne sahiptir ve bu yaşam döngüsü içinde durumları değişebilir. Entity'lerin özellikleri, onların kimliklerini belirleyen özelliklerle birlikte diğer özellikleridir.

Bir entity'nin kimliği genellikle benzersiz bir şekilde belirlenir ve bu kimlik, entity'nin yaşam döngüsü boyunca değişmez. Örneğin, bir müşteri entity'si bir müşteri ID ile benzersiz bir şekilde tanımlanabilir.

Entity'ler, iş mantığına doğrudan odaklanan, bağımsız ve kendi başına anlamlı nesneleri temsil ederler. Bu, yazılım modelini daha anlaşılır ve esnek kılar, çünkü iş domain'ine daha yakın bir şekilde modellenmiş olur.

Örneğin, bir e-ticaret uygulamasında "Product" (Ürün) bir entity olabilir. Her ürün, kendine özgü bir ürün ID'si ile tanımlanır ve fiyat, stok durumu gibi özelliklere sahiptir. Bu entity, müşteri siparişleri, stok takibi gibi iş süreçlerinde kullanılabilir.

## Eric Evans "Domain Driven Design: Tackling Complexity in the Heart of Software"

**Kimlik (Identity):** Entity'lerin belirgin bir özelliği, benzersiz bir kimliğe sahip olmalarıdır. Evans, bir entity'nin kimliğinin, onun yaşam *döngüsü boyunca değişmeyen ve onu diğer entity'lerden ayıran bir özellik olduğunu vurgular. Bu, entity'nin benzersiz bir şekilde tanımlanabilmesini sağlar.

**Zaman Bağımlılığı (Time-Variant):** Entity'lerin zaman içinde değişebilen durumları vardır. Yani, bir entity'nin özellikleri zamanla güncellenebilir. Bu durum, iş domain'indeki gerçek dünya nesnelerinin zaman içinde evrim geçirebileceği gerçeğini yansıtarak, yazılım modellemesini daha gerçekçi kılar.

**Ömür Döngüsü (Lifecycle):** Entity'lerin bir ömür döngüsü vardır. Bu ömür döngüsü, bir entity'nin yaratılması, güncellenmesi ve silinmesi gibi aşamalardan oluşur. Bu konsept, entity'nin nasıl kullanılacağı ve nasıl yönetileceği konusunda rehberlik sağlar.

**İş Süreçlerinde Rolü:** Entity'ler, iş domain'indeki temel nesneleri temsil ettikleri için, iş süreçlerinde önemli bir rol oynarlar. Örneğin, bir siparişin ürünlerini temsil eden entity'ler, siparişin işlenmesi, stok kontrolü gibi iş süreçlerinde merkezi bir rol oynar.

## Summary

**Bir Entity, iş domaininde benzersiz bir kimliği olan bir nesneyi temsil eder. Bu kimlik, nesnenin özelliklerinin değişmesine rağmen tutarlı kalır. Örneğin, bir e-ticaret uygulamasında, her müşteri bir Entity'dir. Müşterinin adı, adresi veya sipariş geçmişi değişse bile, müşterinin benzersiz kimliği aynı kalır.**
