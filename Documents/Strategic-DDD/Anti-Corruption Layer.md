# 	Anti-Corruption Layer (Bozulma Karşıtı Katman)

As in the case of the conformist pattern, the balance of power in this relationship is still skewed toward the upstream service. However, in this case the downstream bounded context is not willing to conform. What it can do instead is translate the upstream bounded context’s model into a model tailored to its own needs via an anticorruption layer, as shown in Figure 4-5.

Conformist deseni durumunda olduğu gibi, bu ilişkideki güç dengesi hala yukarı akış servisine doğru eğilmiştir. Ancak, bu durumda aşağı akış sınırlı bağlam uyum sağlamaya istekli değildir. Bunun yerine, yukarı akış sınırlı bağlamın modelini kendi ihtiyaçlarına uygun bir modele çevirebilir, bunu da bir anti-corruption layer (karşılaştırma katmanı) aracılığıyla yapabilir, Şekil 4-5'te gösterildiği gibi.

![image](https://github.com/ibrahimdoss/Domain-Driven-Design/blob/main/Images/widd_0405.png)

The anticorruption layer pattern addresses scenarios in which it is not desirable or worth the effort to conform to the supplier’s model, such as:

**Anticorruption layer deseni, tedarikçinin modeline uyum sağlamanın istenmediği veya çabanın karşılığını vermediği senaryolarla başa çıkar, örneğin:**

- When the downstream bounded context contains a core subdomain. A core subdomain’s model requires extra attention, and adhering to the supplier’s model might impede the modeling of the problem domain.

- Aşağı akış sınırlı bağlam, temel bir alt alan (core subdomain) içerdiğinde. Bir temel alt alanın modeli ekstra dikkat gerektirir ve tedarikçinin modeline uymak, problem alanının modellemesini engelleyebilir.

- When the upstream model is bad or inconvenient. If a bounded context conforms to a mess, it risks becoming a mess itself. This is often the case with integration with legacy systems.

- Yukarı akış model kötü veya kullanışsız olduğunda. Bir sınırlı bağlam bir karışıklığa uyum sağlarsa, kendisi de bir karışıklığa dönüşme riski taşır. Bu durum genellikle eski sistemlerle entegrasyonlarda görülür.

- When the supplier’s contract changes often, and the consumer wants to protect its model from such frequent changes. With an anticorruption layer, the changes in the supplier’s model only affect the translation mechanism.

- Tedarikçinin sözleşmesi sık sık değiştiğinde ve tüketici, kendi modelini bu sık değişikliklerden korumak istediğinde. Bir anticorruption layer ile, tedarikçinin modelindeki değişiklikler sadece çeviri mekanizmasını etkiler.

From the modeling perspective, the translation of the supplier’s model isolates the downstream consumer from foreign concepts that are not relevant to its bounded context. Hence, it simplifies the consumer’s ubiquitous language and model.

Modelleme perspektifinden bakıldığında, tedarikçinin modelinin çevirisi, aşağı akış tüketicisini, sınırlı bağlamıyla ilgisi olmayan yabancı kavramlardan izole eder. Bu nedenle, tüketici'nin evrensel dilini ve modelini basitleştirir.

## Summary

Bağlamlar yukarı akış-aşağı akış ilişkisi içindedir ve yukarı akış ekibi, aşağı akış ekibinin ihtiyaçlarını umursamaz. Ancak, yukarı akış modeline uymak yerine, aşağı akış ekibi, aşağı akış bağlamını yukarı akış bağlamındaki değişikliklerden koruyan bir soyutlama katmanı oluşturmaya karar verir. Bu adaptasyon katmanı, aşağı akış ekibinin ihtiyaçlarına en çok uyan bir domain modeliyle çalışmasına olanak tanır ve yine de yukarı akış bağlamıyla bütünleşir. Yukarı akış bağlamı değiştiğinde, adaptasyon katmanının da değişmesi gerekir, ancak aşağı akış bağlamının geri kalanı değişmeden kalabilir. Bu stratejiyi, yukarı akış arayüzündeki değişiklikleri tespit etmek için otomatik testlerin kullanıldığı sürekli entegrasyonla birleştirmek iyi bir fikir olabilir.

# Sources

https://www.turkninja.com/2020/08/strategic-domain-driven-design.html

https://www.oreilly.com/library/view/what-is-domain-driven/9781492057802/ch04.html

















