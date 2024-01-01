# Ubiquitous Language

Ubiquitous Language is the term Eric Evans uses in Domain Driven Design for the practice of building up a common, rigorous language between developers and users. This language should be based on the Domain Model used in the software - hence the need for it to be rigorous, since software doesn't cope well with ambiguity.

**"Ubiquitous Language," Eric Evans'ın Domain Driven Design (DDD) içinde geliştiriciler ve kullanıcılar arasında ortak, katı bir dil oluşturma uygulaması için kullandığı bir terimdir. Bu dil, yazılımda kullanılan Domain Model'e dayanmalıdır - bu nedenle katı olması gerekmektedir, çünkü yazılım belirsizlikle iyi başa çıkamaz.**

Evans makes clear that using the ubiquitous language in conversations with domain experts is an important part of testing it, and hence the domain model. He also stresses that the language (and model) should evolve as the team's understanding of the domain grows.

Evans, yaygın dilin ve dolayısıyla alan modelinin test edilmesinin önemli bir parçasının, alan uzmanlarıyla yapılan görüşmelerde yaygın dilin kullanılması olduğunu açıkça belirtir. Ayrıca dilin (ve modelin) takımın alan anlayışı büyüdükçe evrim geçirmesi gerektiğini vurgular.

## Eric Evans:

    By using the model-based language pervasively and not being satisfied until it flows, we approach a model that is complete and comprehensible, made up of simple elements that combine to express complex ideas.

    Model tabanlı dilin yaygın olarak kullanılması ve akıcı hale gelene kadar tatmin olunmamasıyla, kompleks fikirleri ifade etmek için bir araya gelen basit öğelerden oluşan anlaşılır ve tam bir model yaklaşırız.

    ...

    **Domain experts** should object to terms or structures that are awkward or inadequate to convey domain understanding; developers should watch for ambiguity or inconsistency that will trip up design.

**Alan uzmanları, alan anlayışını iletmekte zorlayan veya yetersiz terimlere veya yapısal unsurlara itiraz etmelidir; geliştiriciler, tasarımı engelleyebilecek belirsizlik veya tutarsızlıkları gözlemlemelidir.**


Bir alan adı için yazılım oluşturabilmek için, alanı tanımlamanın bir yoluna ihtiyacınız vardır. İlişkisel bir veri modeline veya benzer bir şeye sahip olmak yeterli değildir. Sadece şeyleri ve onların ilişkilerini değil, aynı zamanda olaylar, süreçler, iş değişmezleri, şeylerin zaman içinde nasıl değiştiği gibi dinamikleri de tanımlayabilmelisiniz. Domain hakkında hem geliştiricilerinizle hem de domain uzmanlarıyla tartışabilmeniz ve mantık yürütebilmeniz gerekir. İhtiyacınız olan şey, ortak bir dildir.

Ortak dil, hem alan uzmanları hem de geliştiriciler tarafından alanı açıklamak ve tartışmak için sürekli olarak kullanılan bir dildir. Kodun kendisinden ayrı olarak, bu dil, Domaine Dayalı Tasarım (DDD)  sürecinin en önemli çıktısıdır. Dilin büyük bir kısmı, alan uzmanları tarafından halihazırda kullanılmakta olan alan terminolojisidir, ancak alan uzmanlarıyla işbirliği içinde yeni kavramlar ve süreçler icat etmeniz de gerekebilir. Bu nedenle, alan uzmanlarının aktif katılımı, Domaine Dayalı Tasarım (DDD)'ın  başarılı olması için kesinlikle gereklidir. Müşteri alanınızı öğretmek ve ortak  bir dil oluşturmanıza yardımcı olmak için zaman ve çaba harcamakla ilgilenmiyorsa, müşteriyi fikrini değiştirmeye ikna etmeye çalışmalı veya başka bir tasarım yöntemi seçmelisiniz.

Ortak dili çeşitli şekillerde belgeleyebilirsiniz. İyi bir başlangıç noktası, bir terimler sözlüğü oluşturmaktır. İş süreçleri, örn. swimline diyagramları ve akış şemaları. UML, farklı şeyler farklı süreçler boyunca ilerlerken durumun nasıl değiştiğini açıklamak için nesneler ve durum diyagramları arasındaki ilişkiyi tanımlamak için kullanılabilir. Alt alan adları da ortak dilin bir parçasıdır ve hatta farklı alt alanlar için dilin farklı "lehçelerini" tanımlamanız gerekebilir. Ortak dilin bu düzenlemesi alan modelidir ve sonunda çalışma koduna dönüştürülecektir. Başka bir deyişle, alan modeli bir veri modeli veya bir UML sınıf diyagramı ile aynı değildir.

Ortak dilin güzel bir özelliği vardır ve bu size doğru yolda olup olmadığınızı söylemesi. Bir iş kavramını veya sürecini dili kullanarak kolayca açıklayabiliyorsanız, doğru yoldasınız demektir. Öte yandan, kendinizi bir şeyi açıklamakta zorlanırken bulursanız, büyük olasılıkla dilden ve dolayısıyla alan modelinizden bir şeyler kaçırıyorsunuzdur. Bu olduğunda, bir alan uzmanı tutmalı ve eksik parçaları aramalısınız. Hatta mevcut modelinizi tamamen tersine çeviren ve daha önce sahip olduğunuzdan çok daha üstün bir domain modeliyle sonuçlanan bir geliştirmeyle karşılaşabilirsiniz.

## Sources

https://martinfowler.com/bliki/UbiquitousLanguage.html

https://www.turkninja.com/2020/08/strategic-domain-driven-design.html

