# Infrastructure Layer

Amaç: Teknik yetenekleri sağlar (dış servisler ile entegrasyon).
İçerik: Harici servislerle etkileşim.
Özellik: Genellikle uygulamanın diğer katmanlarında kullanılan araç ve kütüphaneleri içerir.

Bu katman veri tabanı, mesajlaşma sistemleri, email servisleri gibi dış servislere erişilen katman olacaktır.

**uygulamanın dış dünya ile etkileşimini yöneten ve teknik detayları barındıran bir katmandır. Bu katman, veritabanı erişimi, dış servis çağrıları, dosya işlemleri gibi altyapısal görevleri üstlenir ve domain katmanı ve uygulama katmanı ile iletişim kurar.**

Altyapı katmanı genellikle şu görevleri yerine getirir:

Veritabanı Erişimi: Veritabanı ile etkileşim kurar, veri okuma, yazma, güncelleme ve silme işlemlerini gerçekleştirir.

Harici Servis Entegrasyonu: Harici API'ler veya web servisleriyle iletişim kurar, veri alışverişi yapar ve sonuçları işler.

Dosya ve Depolama İşlemleri: Dosya okuma, yazma, silme gibi işlemleri gerçekleştirir, depolama alanı yönetir.

E-posta Gönderme: E-posta gönderimi gibi iletişim işlemlerini gerçekleştirir.

Günlükleme (Logging): Uygulamanın çalışmasıyla ilgili olayları günlüğe kaydeder, hata ve uyarı mesajlarını işler.

Görüntü İşleme ve CDN Entegrasyonu: Görüntü işleme hizmetleriyle veya içerik dağıtım ağı (CDN) ile etkileşim kurar.

---

Örnek bir senaryoda, bir e-ticaret uygulamasını ele alalım ve altyapı katmanının bazı görevlerini görelim:

Veritabanı Erişimi: Müşteri bilgilerini depolamak ve sipariş verilerini yönetmek için bir veritabanı sunucusuna erişim sağlar.

Harici Servis Entegrasyonu: Ödeme işlemleri için bir ödeme geçidi ile iletişim kurar veya stok takibi için bir dış envanter servisi ile entegrasyon sağlar.

Dosya ve Depolama İşlemleri: Ürün resimlerini depolamak ve kullanıcıların yüklediği dosyaları saklamak için bir dosya depolama sistemi kullanır.

E-posta Gönderme: Kullanıcılara sipariş onayı veya şifre sıfırlama gibi e-posta bildirimleri gönderir.

Günlükleme (Logging): Uygulamanın çalışmasıyla ilgili bilgileri bir günlük dosyasına kaydeder, hata durumlarını takip eder ve izler.

Görüntü İşleme ve CDN Entegrasyonu: Ürün resimlerini optimize etmek ve kullanıcıya sunmak için bir görüntü işleme servisiyle veya CDN ile etkileşim kurar.

Altyapı katmanı, uygulamanın teknik detaylarını ve dış kaynaklarla iletişimini yönetirken, domain katmanı ve uygulama katmanı ile bağlantı kurar. Bu katman, uygulamanın dış dünyayla etkileşimini soyutlar ve uygulamanın daha esnek ve ölçeklenebilir olmasını sağlar.