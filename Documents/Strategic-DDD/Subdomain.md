# Subdomain(ALtalan)

## Problem

How to decompose an application into services?

## Solution

Define services corresponding to Domain-Driven Design (DDD) subdomains. DDD refers to the application’s problem space - the business - as the domain. A domain is consists of multiple subdomains. Each subdomain corresponds to a different part of the business.

Domain-Driven Design (DDD) ile ilişkilendirilmiş hizmetleri tanımlamak, alt alanlara karşılık gelir şekilde önemlidir. DDD, uygulamanın problem alanını - işi - "domain" olarak adlandırır. **Bir domain, birden çok subdomain'i içerir. Her bir subdomain, işin farklı bir bölümüne karşılık gelir.**

Subdomains can be classified as follows:

Core - key differentiator for the business and the most valuable part of the application
Supporting - related to what the business does but not a differentiator. These can be implemented in-house or outsourced.
Generic - not specific to the business and are ideally implemented using off the shelf software

Subdomain'lar şu şekilde sınıflandırılabilir:

**Çekirdek (Core):** İşletme için temel farklılaştırıcı ve uygulamanın en değerli kısmıdır.

**Destekleyici (Supporting):** İşletmenin ne yaptığı ile ilgili olup, ancak bir farklılaştırıcı değildir. Bunlar genellikle içeride veya dış kaynak kullanılarak uygulanabilir.

**Jenerik (Generic):** İşle ilgili olmayan ve ideal olarak hazır yazılımlar kullanılarak uygulanabilen özellikleri içerir.

## Examples:


The subdomains of an online store include: //Bir çevrimiçi mağazanın alt alan adları şunları içerir:

- Product catalog
- Inventory management
- Order management
- Delivery management

The corresponding microservice architecture would have services corresponding to each of these subdomains.

//İlgili mikro hizmet mimarisi, bu alt alanların her birine karşılık gelen hizmetlere sahip olacaktır.

![image](https://github.com/ibrahimdoss/Domain-Driven-Design/blob/main/Images/decompose-by-subdomain.png)

## Resulting Context

Resulting Context
This pattern has the following benefits:

- Stable architecture since the subdomains are relatively stable
- Development teams are cross-functional, autonomous, and organized around delivering business value rather than technical features
- Services are cohesive and loosely coupled

-  Alt alanlar (subdomain'ler) nispeten kararlı olduğu için, genel mimari de kararlıdır.

- Geliştirme ekipleri çapraz fonksiyonlu, otonom ve iş değeri sunma üzerine odaklıdır.

- Hizmetler birbirine uyumlu ve gevşek bağlıdır.

## Issues

- **How to identify the subdomains?** Identifying subdomains and hence services requires an understanding of the business. Like business capabilities, subdomains are identified by analyzing the business and its organizational structure and identifying the different areas of expertise. Subdomains are best identified using an iterative process. Good starting points for identifying subdomains are:

- organization structure - different groups within an organization might correspond to subdomains

- high-level domain model - subdomains often have a key domain object


- Subdomain'leri nasıl belirleyeceğiniz ve bu nedenle hizmetleri tanımlamak, işin anlaşılmasını gerektirir. İş kapasiteleri gibi, subdomain'ler belirlenirken işin ve organizasyon yapısının anlaşılması, farklı uzmanlık alanlarını belirlemek için bir analiz yapmayı içerir. Subdomain'leri tanımlamak için en iyi yaklaşım, yinelemeli bir süreç kullanmaktır. Subdomain'leri belirlemenin iyi başlangıç noktaları şunlar olabilir:

- Organizasyon yapısı - bir organizasyon içindeki farklı gruplar genellikle subdomain'lere karşılık gelebilir.

- Yüksek düzeydeki domain modeli - subdomain'ler genellikle önemli bir domain nesnesine sahiptir.

## Summary

Alan kavramı çok geniş ve soyuttur. Daha somut ve elle tutulur hale getirmek için, onu alt alan adı verilen daha küçük parçalara ayırmak mantıklıdır. Tüm alt alan adlarının, hangi kategoriye girdiklerine bakılmaksızın genel çözüm için önemli olduğuna dikkat çekmek önemlidir. Bununla birlikte, farklı miktarlarda çaba gerektirirler ve aynı zamanda farklı kalite ve eksiksizlik gereksinimlerine sahip olabilirler.

## Sources

https://microservices.io/patterns/decomposition/decompose-by-subdomain.html#:~:text=DDD%20refers%20to%20the%20application's,valuable%20part%20of%20the%20application

https://www.turkninja.com/2020/08/strategic-domain-driven-design.html