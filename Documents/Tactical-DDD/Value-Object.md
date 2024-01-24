# Value Object


Value Object (Değer Nesnesi): Bir değer nesnesi, sadece değerine ve içsel durumuna bağlı olarak tanımlanan bir nesnedir. Değer nesneleri, eşdeğerlik kurallarına dayanır; yani, iki değer nesnesi aynı değere sahipse, birbirleriyle eşdeğer kabul edilirler. Değer nesneleri genellikle immutable (değişmez) olup, iç durumları değiştirilemez.

Örneklerle açıklamak gerekirse, bir telefon numarası, tarih aralığı, coğrafi konum gibi kavramlar değer nesneleri olabilir. Bu nesneler, içerdikleri değere göre tanımlanır ve eşdeğerlik kurallarına uyarlar.

Para Miktarı (Money): Bir para miktarı, değer nesnesi olarak düşünülebilir. Örneğin, 100 dolarlık bir para miktarı, içsel değeri olan 100'e sahiptir ve başka bir 100 dolarlık para miktarı ile eşdeğer kabul edilir.

```java
public class Money {
    private final int amount;

    public Money(int amount) {
        this.amount = amount;
    }

    public int getAmount() {
        return amount;
    }

    // Diğer gerekli metotlar...
}


```

Coğrafi Konum (Location): Bir coğrafi konum, enlem ve boylam gibi değerlere sahip olabilir. İki coğrafi konum, aynı enlem ve boylama sahipse, birbirleriyle eşdeğer kabul edilir.

```java
public class Location {
    private final double latitude;
    private final double longitude;

    public Location(double latitude, double longitude) {
        this.latitude = latitude;
        this.longitude = longitude;
    }

    public double getLatitude() {
        return latitude;
    }

    public double getLongitude() {
        return longitude;
    }

    // Diğer gerekli metotlar...
}


```

Value object'ler, immutable olmaları ve sadece değerlerine bağlı olarak tanımlanmaları nedeniyle genellikle sistemde güvenli bir şekilde paylaşılabilir ve kullanılabilir. Bu nedenle, DDD'de value object'ler, iş domain'inde önemli kavramları temsil etmek için sıkça kullanılır.

## Summary

Bir Value Object, değeri tarafından tanımlanan, kimliği olmayan bir nesneyi temsil eder. Value Objects genellikle Entities'nin özellikleri olarak kullanılır. Örneğin, bir müşterinin adresi bir Value Object olabilir.






