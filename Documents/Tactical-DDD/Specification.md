# Specification

Eric Evans'ın "Domain-Driven Design: Tackling Complexity in the Heart of Software" kitabında "Specification" (Belirleme) kavramı, özellikle bir nesnenin belirli bir durumu veya özelliği sağlayıp sağlamadığını belirlemek için kullanılan bir tasarım deseni olarak ele alınır.

Specification (Belirleme): Bir belirleme, bir nesnenin belirli bir kriter kümesini karşılayıp karşılamadığını kontrol eden bir nesnedir. Bu, genellikle bir boolean değer döndüren bir metodun bulunduğu bir arayüzü ifade eder. Belirleme, özellikle karmaşık iş kurallarını ifade etmek, nesnelerin durumlarını kontrol etmek veya filtreleme işlemleri gerçekleştirmek için kullanılır.

ProductAvailabilitySpecification (Ürün Durumu Belirleme): Bir e-ticaret uygulamasında, bir ürünün mevcut olup olmadığını belirleyen bir belirleme düşünelim.

```java
public interface ProductAvailabilitySpecification {
    boolean isSatisfiedBy(Product product);
}


```

Bu arayüz, isSatisfiedBy metodu ile bir ürünün mevcut olup olmadığını kontrol eder. Bu belirleme, daha sonra farklı ürünlerin durumunu kontrol etmek için farklı implementasyonlarla genişletilebilir.

OrderTotalAmountSpecification (Sipariş Toplam Tutar Belirleme): Bir siparişin toplam tutarının belirli bir kriteri karşılayıp karşılamadığını kontrol eden bir belirleme düşünelim.

```java
public interface OrderTotalAmountSpecification {
    boolean isSatisfiedBy(Order order);
}



```

Bu arayüz, isSatisfiedBy metodu ile bir siparişin toplam tutarının belirli bir kriteri karşılayıp karşılamadığını kontrol eder. Bu belirleme, örneğin minimum sipariş tutarı gibi iş kurallarını kontrol etmek için kullanılabilir.

Belirleme deseni, özellikle iş kurallarının karmaşık olduğu durumlarda kullanışlıdır. Bu desen, sistemin bakımını ve genişletilmesini kolaylaştırabilir ve iş kurallarını açıkça ifade etmeye yardımcı olabilir.

Specification, bir iş kuralını tanımlayan bir nesnedir. Bu nesne, bir şeyin bu kuralı karşılayıp karşılamadığını kontrol eder.

Specification Pattern'ın Tanımı ve Kullanımı

Specification Pattern, iş kurallarını bir nesne olarak modellemek için kullanılır. Bu pattern, iş kurallarını kodda belirgin ve yeniden kullanılabilir hale getirir.

Bir Specification, genellikle bir ya da birden çok nesnenin belirli bir kuralı karşılayıp karşılamadığını kontrol eden bir metoda sahip olur.