# Aggregate

**Domain Driven Design’da konsepti ve ihtiyaçlarını implemente ederken, birbiri ile alakalı birden fazla Entity’nin bir iş akışını, kuralını gerçekleştirmek için beraber kullanılması “Aggregate” olarak tanımlanır . Bu aggreagete’in ana nesnesi de Aggreagete root olarak adlandırılır.** Bir örnek vermek gerekirse, Product, ProductVariant, ProductDetailInfo gibi entityler çoğunlukla bir akışını gerçekleştirmek için beraber kullanılır ve bu sebeple aggreagate’tir diyebiliriz. Product entitysi de bunların aggreagate rootudur diyebiliriz. 

Aggreate rooutin ana amacı aggreagetin tutarlılığını sağlamaktır. Bu sebeple diğer tüm aggregate üyelerini aggregate root üzerinden manipule ederiz. Eğerki aggreagetteki bir nesneyi Aggregate Root’dan bağımsız değiştirirseniz Aggregate Root konseptin valid state olduğunu bilemez. Yine bir örnek üzerinden gitmek gerekirse Araba, motor, lastik, direksiyon gibi entitylerimiz olsun. Bunlar bir logici gerçekleştirmek için çoğunlukla beraber kullanılacakladır. Dolayısıyla bu gruba Aggregate diyebiliriz. Bu grubun Aggregate Rootu da Araba nesnesi olacaktır.

 Nedenini ise bir örnek üzerinden düşünelim, Lastikteki bir sorunun arabadan bağımsız çözülmesi pek mümkün değildir. Lastik arabaya entegreyken bir anlam ifade eder. Arabanın lastikteki değişiklikten haberdar olması ve hatta bir sürüş ile validliğini teyit etmesi gerekir. Dolayısıyla lastiğe yapılacak her değişiklik araba üzerinden uygunluk durumuna göre yapılır mesela bir otomobile traktör lastiği takamayız gibi. Diğer tüm entitiyleri de aynı konseptte düşünürsek Araba entitysi Aggreagate Roottur çünkü aggreagetin tutarlılığından sorumludur diyebiliriz.

Buradaki en önemli nokta bu grup transactional olarak bir bütün halide düşünülür ve böylelikle entity’lerin bütünlüğü sağlanmış olur

Projede direkt Aggregate Root’u belirlemek yerine aggreageti bildiğimizden emin olmalı ve Aggregate Root’un Aggregate Consistency’sinden sorumlu olduğundan emin olmalıyız. Çünkü container olarak diğer objeleri içinde barındırması bir nesneyi Aggregate yapmaz.

**A DDD aggregate is a cluster of domain objects that can be treated as a single unit. An aggregate will have one of its component objects be the aggregate root. Any references from outside the aggregate should only go to the aggregate root. The root can thus ensure the integrity of the aggregate as a whole.**

Bir Aggregate, bir veya daha fazla Entity ve Value Object'i bir araya getiren ve iş kurallarını ve tutarlılığı koruyan bir nesnedir. Aggregate, tüm işlemlerin tek bir atomik birim olarak gerçekleşmesini sağlar.


## Eric Evans'ın "Domain-Driven Design: Tackling Complexity in the Heart of Software" 

Aggregate (Toplu): Bir aggregate, birlikte tutulan ve birbirine bağlı olan bir grup ilişkili nesnenin oluşturduğu bir bütündür. Aggregate, bir kök (root) ve onun altındaki bir veya daha fazla iç nesneden oluşur. Bu ilişkili nesneler bir araya getirilerek, birbirleriyle bütün olarak yönetilir ve dış dünyaya bir tek kök nesne üzerinden görünürler.

Aggregate, içindeki nesneler arasında bir tutarlılık sınırlarına sahiptir ve bu sınırlar, yalnızca aggregate'nin kökü üzerinden değiştirilebilir. Bu, aggregate içindeki nesnelerin birbirleriyle doğrudan etkileşimde bulunamayacakları anlamına gelir.

## Example

Örneklerle açıklamak gerekirse, bir e-ticaret uygulamasında "Order" (Sipariş) ve "OrderLine" (Sipariş Satırı) kavramları bir aggregate oluşturabilir. Sipariş, kök nesne olarak düşünülür ve bu siparişin içinde bir veya daha fazla sipariş satırı bulunabilir. Ancak, bir sipariş satırı doğrudan dış dünya tarafından değiştirilemez; sadece bağlı olduğu siparişin kökü üzerinden değiştirilebilir.

```java
public class Order {
    private List<OrderLine> orderLines = new ArrayList<>();

    public void addOrderLine(Product product, int quantity) {
        // Sipariş satırı eklemek için özel bir metot
        OrderLine orderLine = new OrderLine(product, quantity);
        orderLines.add(orderLine);
    }

    // Diğer gerekli metotlar...
}

public class OrderLine {
    private Product product;
    private int quantity;

    public OrderLine(Product product, int quantity) {
        this.product = product;
        this.quantity = quantity;
    }

    // Diğer gerekli metotlar...
}

}


```

Bu örnekte, "Order" aggregate'nin köküdür ve "OrderLine" nesneleri ile birleşir. Sipariş satırları sadece siparişin metotları aracılığıyla eklenir veya silinir, bu da aggregate sınırları içinde tutarlılığı sağlar.

Aggregate'lar, yazılım modelleme sürecinde karmaşıklığı azaltmaya yardımcı olan önemli bir tasarım kavramıdır. Bu tasarım, bir iş domain'indeki bağlantılı nesneleri bir araya getirerek, daha düzenli ve anlaşılır bir model oluşturulmasına olanak tanır.