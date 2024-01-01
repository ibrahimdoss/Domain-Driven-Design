# Open Host Service

This pattern addresses the case where the power is skewed toward the consumers. The supplier is interested in protecting its consumers and providing the best service possible.

Bu desen, gücün tüketicilere eğilimli olduğu durumu ele alır. Tedarikçi, tüketicilerini koruma ve en iyi hizmeti sunma konusunda ilgili olabilir.

To protect the consumers from changes in its implementation, the upstream supplier decouples its implementation model from the public interface. This decoupling allows the supplier to evolve its implementation and public models at different rates, as shown in Figure 4-6.

Tedarikçi, tüketicilerini uygulamasındaki değişikliklerden korumak için, yukarı akış tedarikçi uygulama modelini genel arayüzden ayırır. Bu ayrıştırma, tedarikçinin uygulama ve genel modellerini farklı oranlarda evrimleştirmesine izin verir, Şekil 4-6'da gösterildiği gibi.

![image](https://github.com/ibrahimdoss/Domain-Driven-Design/blob/main/Images/widd_0406.png)

The supplier’s public interface is not intended to conform to its ubiquitous language. Instead, it is intended to expose a protocol convenient for the consumers, expressed in an integration-oriented language. Hence, the public protocol is called the “published language.”

Tedarikçinin genel arayüzü, yaygın dil ile uyumlu olmaktan ziyade, tüketiciler için uygun bir protokolü ifade eden bir entegrasyon odaklı dilde ifade edilmek üzere tasarlanmıştır. Bu nedenle, genel protokol "yayınlanmış dil" olarak adlandırılır.

In a sense, the open-host service pattern is a reversal of the anticorruption layer pattern: instead of the consumer, the supplier implements the translation of its internal model.

**Bir bakıma, açık ana servis deseni, anticorruption layer deseninin bir tersidir: tüketici yerine, tedarikçi iç modelin çevirisini uygular.**


## Summary

Bir sisteme erişim, açıkça tanımlanmış bir protokol kullanılarak, açıkça tanımlanmış hizmetler tarafından sağlanır. Protokol, ihtiyaç duyan herkesin sisteme entegre olabilmesi için açıktır. Web hizmetleri ve mikroservisler, bu entegrasyon modelinin güzel bir örneğidir. Bu örüntü, bağlamlar ve onları geliştiren takımlar arasındaki ilişkiyi önemsemediği için diğerlerinden farklıdır. open host service modelini diğer modellerden herhangi biriyle birleştirebilirsiniz.


Bu kalıbı kullanırken dikkat edilmesi gereken nokta, protokolü basit ve kararlı tutmaktır. Sistem istemcilerinin çoğu bu protokolden ihtiyaç duyduklarını alabilmelidir. Kalan özel durumlar için özel entegrasyon noktaları oluşturun.

## Sources

https://www.oreilly.com/library/view/what-is-domain-driven/9781492057802/ch04.html

https://www.turkninja.com/2020/08/strategic-domain-driven-design.html













