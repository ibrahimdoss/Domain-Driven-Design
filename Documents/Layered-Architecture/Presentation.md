# Presentation Layer

Amaç: Kullanıcı arayüzünü (UI) yönetir ve kullanıcı etkileşimlerini işler.
İçerik: Web sayfaları, mobil uygulama arayüzleri, REST API’ler.
Özellik: Kullanıcıların uygulama ile etkileşime girdiği arayüzleri ve API’leri içerir.

Bu katman dış sistemlerle etkileşimin sağlanacağı kısımdır. Bu katman bir insan, bir uygulama veya bir mesajın domainin üzerinde oluşturacağı etkilerin giriş kapısı olarak yer almaktadır. Talepler bu katmandan kabul edecek ve cevaplar bu katmanda şekillenerek kullanıcıya gösterilecektir.


Sunum katmanı, kullanıcıya bilgi sunan ve kullanıcı girişini alan arayüzleri yönetir. Bu katman, genellikle kullanıcı arayüzüne odaklanır ve kullanıcıların etkileşimde bulunduğu bileşenleri içerir.

Sunum katmanı genellikle aşağıdaki görevleri yerine getirir:

Kullanıcı Arayüzü Yönetimi: Kullanıcıların etkileşime girdiği web sayfaları, mobil uygulama ekranları veya diğer arayüz bileşenlerini yönetir.

Kullanıcı Girişi ve Doğrulama: Kullanıcıların hesaplarına giriş yapmalarını sağlar, kimlik doğrulaması gerçekleştirir ve yetkilendirme işlemlerini yönetir.

Sunum Mantığı: Kullanıcı arayüzünden gelen istekleri alır, gerekirse işler ve uygun şekilde domain katmanına iletilmek üzere hazırlar.

Görüntüleme ve Formatlama: Domain katmanından gelen verileri kullanıcıya uygun şekilde görsel olarak düzenler ve sunar.

Kullanıcı Etkileşimi Yönetimi: Kullanıcıdan gelen girişleri alır, doğrular, gerektiğinde işler ve domain katmanına iletilmek üzere hazırlar.

Örnek bir senaryoda, bir e-ticaret uygulamasını ele alalım ve sunum katmanının bazı görevlerini görelim:

Kullanıcı Arayüzü Yönetimi: Web sitesindeki ürün listesi sayfası, ürün detay sayfası, sepet sayfası vb. ekranları yönetir.

Kullanıcı Girişi ve Doğrulama: Kullanıcıların hesaplarına giriş yapmalarını sağlar, kayıt olmalarını yönetir ve kimlik doğrulaması gerçekleştirir.

Sunum Mantığı: Kullanıcı bir ürün satın almak istediğinde, bu isteği alır, gerekirse sepete ekler, ödeme ekranına yönlendirir ve işlemleri yönetir.

Görüntüleme ve Formatlama: Domain katmanından gelen ürün bilgilerini kullanıcı dostu bir şekilde düzenler, fiyatları formatlar ve kullanıcıya sunar.

Kullanıcı Etkileşimi Yönetimi: Kullanıcıdan gelen tıklamaları, form doldurmaları ve diğer etkileşimleri yönetir, doğrular ve ilgili işlemleri başlatır.

Sunum katmanı, kullanıcı arayüzünü yöneterek, kullanıcıların uygulama ile etkileşimde bulunmasını sağlar. Bu katman, genellikle domain katmanı ve uygulama katmanı arasında bir arayüz sağlar ve kullanıcı taleplerini iş mantığına çevirir.