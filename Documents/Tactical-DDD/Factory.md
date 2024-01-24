# Factory

**Factory (Fabrika): Factory, nesnelerin yaratılması işlemini gerçekleştiren bir tasarım desenidir. Ancak, Eric Evans'ın vurguladığı önemli bir nokta, factory'leri sadece nesne yaratma işlemi için bir yer olarak değil, aynı zamanda bu yaratma sürecindeki karmaşıklığı gizleyen ve yöneten bir tasarım aracı olarak görmektir.**

Evans, factory kavramını "abstract factory" ve "concrete factory" gibi alt kategorilere böler. "Abstract factory", nesne yaratma sürecini tanımlayan bir arayüz sağlar ve "concrete factory" bu arayüzü uygular. Bu, kullanıcı kodunun somut sınıflardan bağımsız olmasını ve nesne yaratma sürecini daha esnek hale getirmeyi amaçlar.

Örneklerle açıklamak gerekirse, bir e-ticaret uygulamasında "Product" (Ürün) nesnelerini yaratmak için bir factory kullanılabilir. Bu factory, ürünlerin yaratılmasının yanı sıra, belirli kategorilere göre farklı ürün türlerini yaratma yeteneğine de sahip olabilir.

```java

// Abstract Factory arayüzü
public interface ProductFactory {
    Product createProduct(String name, double price);
}

// Concrete Factory implementasyonu
public class ElectronicProductFactory implements ProductFactory {
    @Override
    public Product createProduct(String name, double price) {
        return new ElectronicProduct(name, price);
    }
}

public class BookProductFactory implements ProductFactory {
    @Override
    public Product createProduct(String name, double price) {
        return new BookProduct(name, price);
    }
}

// Ürün arayüzü
public interface Product {
    // Product ile ilgili metotlar...
}

// Concrete Product implementasyonları
public class ElectronicProduct implements Product {
    // ElectronicProduct ile ilgili detaylar...
}

public class BookProduct implements Product {
    // BookProduct ile ilgili detaylar...
}


```

Bu örnekte, "ProductFactory" arayüzü, ürün yaratma sürecini tanımlar. "ElectronicProductFactory" ve "BookProductFactory" gibi concrete factory sınıfları, bu arayüzü uygular ve belirli ürün türlerini yaratır. Bu tasarım, yeni ürün türleri eklenmesini ve kullanıcı kodunun somut sınıflardan izole olmasını sağlar.

Factory kavramı, özellikle nesne yaratma süreçlerinin karmaşık olduğu durumlarda kullanışlıdır ve yazılımın esnekliğini artırmak, bağımlılıkları azaltmak için etkili bir araçtır.