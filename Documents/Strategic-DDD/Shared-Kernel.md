# Shared Kernel (Paylaşılan Çekirdek)

The shared kernel is a more formal way of defining a contract between multiple bounded contexts. Here, instead of ad hoc integrations, the contract is defined explicitly in a compiled library—the shared kernel. The library defines the integration methods and language used by both bounded contexts, as shown in Figure 4-2.

//"Shared kernel," birden fazla sınırlı bağlam arasında bir sözleşmeyi daha resmi bir şekilde tanımlamanın bir yoludur. Burada, rastgele entegrasyonlar yerine sözleşme, derlenmiş bir kütüphanede - yani paylaşılan çekirdek - açıkça tanımlanır. Kütüphane, her iki sınırlı bağlam tarafından kullanılan entegrasyon yöntemlerini ve dilini tanımlar, Şekil 4-2'de gösterildiği gibi.

![image](https://github.com/ibrahimdoss/Domain-Driven-Design/blob/main/Images/widd_0402.png)

The shared kernel is both referenced and owned by multiple bounded contexts. Each team is free to modify the compiled library that defines the integration contract. A change to the contract can break the other team’s build, though; hence, as in the partnership case, this pattern requires high levels of commitment and synchronization between teams.

Paylaşılan çekirdek, birden çok sınırlı bağlam tarafından hem referans alınan hem de sahip olunan bir bileşendir. Her ekip, entegrasyon sözleşmesini tanımlayan derlenmiş kütüphaneyi değiştirme özgürlüğüne sahiptir. Ancak, sözleşmede yapılan bir değişiklik, diğer ekip tarafından yapılan derlemeyi bozabilir; **bu nedenle, ortaklık durumunda olduğu gibi, bu desen, ekipler arasında yüksek düzeyde bağlılık ve senkronizasyon gerektirir.**

A peculiar detail about the shared kernel pattern is that in a way, it contradicts a core principle of bounded contexts: that only one team can own a bounded context. Here we extract a shared part of multiple bounded contexts into its own bounded context. As a result, the shared bounded context is jointly owned by multiple teams.

Paylaşılan çekirdek deseniyle ilgili dikkat çekici bir detay, sınırlı bağlamın temel prensibini bir bakıma çiğniyor olmasıdır: yalnızca bir ekip bir sınırlı bağlama sahip olabilir. Burada, birden çok sınırlı bağlamın paylaşılan bir bölümünü kendi sınırlı bağlamına çıkarıyoruz. Sonuç olarak, paylaşılan sınırlı bağlam, birden fazla ekibin ortak sahip olduğu bir bağlam haline gelir.

The key to implementing the shared kernel pattern is to keep the scope of the shared kernel small, and limited to the integration contract only.

Paylaşılan çekirdek desenini uygulamanın anahtarı, paylaşılan çekirdeğin kapsamını küçük tutmak ve sadece entegrasyon sözleşmesine odaklanmakta yatar.

#### One team owning multiple bounded contexts (Tek bir ekip, birden çok sınırlı bağlama sahip olma durumu)

It’s worth mentioning that a shared kernel is a natural fit for integrating bounded contexts that are owned and implemented by the same team. In such a case, an ad hoc integration of the bounded contexts can “wash out” the contexts’ boundaries over time. A shared kernel can be used for explicitly defining the integration contract.


Değerlendirilmesi gereken bir nokta, aynı ekibin sahip olduğu ve uyguladığı sınırlı bağlamları entegre etmek için paylaşılan bir çekirdeğin doğal bir çözüm olduğudur. Bu durumda, sınırlı bağlamların rastgele entegrasyonu zamanla bağlam sınırlarını belirsizleştirebilir. Paylaşılan bir çekirdek, entegrasyon sözleşmesini açıkça tanımlamak için kullanılabilir.

Moreover, in this scenario, the one team ownership principle is not broken—both bounded contexts are implemented by the same team.

Ayrıca, bu senaryoda, tek ekip sahiplik ilkesi çiğnenmez — her iki sınırlı bağlam da aynı ekip tarafından uygulanmaktadır.


## Summary

Her iki bağlam da çekirdek olan ortak bir kod tabanını paylaşır. Çekirdek, herhangi bir ekip tarafından değiştirilebilir, ancak önce diğer ekibe danışılmadan yapılamaz. İstenmeyen yan etkilerin ortaya çıkmadığından emin olmak için, sürekli entegrasyon (otomatik test ile) gereklidir. İşleri olabildiğince basit tutmak için, paylaşılan çekirdek mümkün olduğu kadar küçük tutulmalıdır. Paylaşılan çekirdekte çok sayıda model kodu varsa, bu bağlamların aslında tek bir büyük bağlamda birleştirilmesi gerektiğinin bir işareti olabilir.

## Sources

https://www.oreilly.com/library/view/what-is-domain-driven/9781492057802/ch04.html

https://www.turkninja.com/2020/08/strategic-domain-driven-design.html














