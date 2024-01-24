# Domain Event

Domain Event (Domain Olayı): Domain Event, iş domain'indeki önemli değişiklikleri veya olayları temsil eden bir kavramdır. Bir domain event, genellikle bir durumu veya olayı ifade eden nesnelerin bir araya getirilmesidir. Bu olaylar, sistemin farklı bileşenleri arasında bilgi paylaşımını sağlar ve asenkron sistemlerde kullanılabilir.

Domain event'ler genellikle bir şeyin olduğunu veya bir şeyin gerçekleştiğini ifade eder ve bu olaylar, sistemin çeşitli bileşenleri arasında bağlantılar kurarak, birbiriyle etkileşimde bulunmalarını sağlar.

OrderPlaced (Sipariş Verildi): Bir e-ticaret uygulamasında, müşteri bir sipariş verdiğinde tetiklenen bir domain event düşünelim. Bu olay, yeni bir siparişin oluşturulduğunu ve işleme alındığını temsil eder.

```java

public class OrderPlacedEvent {
    private final Order order;

    public OrderPlacedEvent(Order order) {
        this.order = order;
    }

    public Order getOrder() {
        return order;
    }
}


```

InventoryUpdated (Stok Güncellendi): Bir stok güncelleme işlemi sonucunda stokta bir değişiklik olduğunda tetiklenen bir domain event düşünelim. Bu olay, stok güncelleme işleminin gerçekleştiğini diğer bileşenlere bildirir.

```java

public class InventoryUpdatedEvent {
    private final Product product;
    private final int newStockLevel;

    public InventoryUpdatedEvent(Product product, int newStockLevel) {
        this.product = product;
        this.newStockLevel = newStockLevel;
    }

    public Product getProduct() {
        return product;
    }

    public int getNewStockLevel() {
        return newStockLevel;
    }
}


```

**Domain event'ler, sistemdeki çeşitli bileşenler arasında birbirleriyle etkileşim kurmayı sağlar ve bu etkileşimler, iş domain'indeki değişiklikleri diğer bileşenlere bildirerek daha esnek bir sistem oluşturulmasına olanak tanır. Asenkron yapılarla birleştirildiğinde, domain event'ler sistemdeki olayları daha etkin bir şekilde yönetmeye yardımcı olabilir.**

Domain Event'lar, bir durumun değiştiğini belirten olayları temsil eder. Bu olaylar genellikle iş süreçlerini harekete geçirir veya diğer durumları etkiler. Domain event'larının kullanılması, bir uygulamanın farklı bölümlerini decouple etmeye yardımcı olabilir, çünkü bir bölüm sadece olayları yayınlar ve diğer bölümler bu olaylara yanıt verir.





