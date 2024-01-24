# Repository

Veri erişim katmanlarını soyutlamak için Repository tasarım desenini kullanır.

Services iş kurallarının ve doğrulama işlemleri için kullanılır. Repository bazı kurallar ile birlikte Aggregate-veritabanı iletişimi için kullanılır.

Örnek: “Müşteri Deposu” ve “Ürün Deposu” oluşturulur. Bu depolar, veritabanına erişimi yönetir ve müşteri ve ürün bilgilerini iş alanı kodundan soyutlar.

Repository Pattern, domain model ile veri erişim mantığı arasında bir soyutlama sağlar. Bu, domain modelin veri erişim teknolojilerinden bağımsız kalmasını sağlar.

Bir Repository genellikle aşağıdaki işlemleri destekler: ekleme (add), kaldırma (remove), alım (get) ve listeleme (list).

```java
public interface CustomerRepository {

    void add(Customer customer);

    Customer get(String id);

    List<Customer> list();

    void remove(Customer customer);

}


```

## Repository Tasarımı

Repository, genellikle bir ya da birkaç Aggregate için tasarlanır. Her Aggregate için bir Repository olmalıdır. Bunun nedeni, Aggregate'lerin transactional sınırlar olması ve her birinin kendi yaşam döngüsünün olmasıdır.

```java
public class CustomerRepositoryImpl implements CustomerRepository {

    // veri erişim mantığı burada gerçekleşir



    @Override

    public void add(Customer customer) {

        // veritabanına Customer ekleme kodu...

    }



    @Override

    public Customer get(String id) {

        // id'ye göre Customer getirme kodu...

        return null;

    }



    @Override

    public List<Customer> list() {

        // tüm Customer'ları listeleme kodu...

        return null;

    }



    @Override

    public void remove(Customer customer) {

        // Customer'ı silme kodu...

    }

}


```

## Data Mapper ve Repository

Data Mapper, bir objenin veri tabanı tablosuna (ve tersi) nasıl map edileceğini tanımlar. Bu, genellikle bir ORM aracılığıyla gerçekleştirilir.

Repository, genellikle bir ya da daha fazla Data Mapper kullanır. Repository, Aggregate'lerle çalışmayı soyutlarken, Data Mapper veri tabanı tablolarıyla çalışmayı soyutlar.

```java
public class CustomerMapper {

    public Customer toDomain(CustomerEntity entity) {

        // entity'yi domain modeline dönüştürme kodu...

        return null;

    }



    public CustomerEntity fromDomain(Customer customer) {

        // domain modelini entity'ye dönüştürme kodu...

        return null;

    }

}


```

# Sources

https://www.turkninja.com/2023/08/ddd-konsusunda-dansmanlk-vermek-isteyen.html