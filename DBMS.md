# Object Relational Mapping

İlişkisel veritabanı ile nesne yönelimli(Object Oriented Programming) arasında bir tür köprü özelliği gören ve ilişkisel veritabanındaki bilgilerimizi yönetmek için nesne modelimizi kullandığımız bir tekniktir.


ORM, veritabanında oluşturulan her bir nesneye (tabloya) karşılık uygulama tarafında bir nesne oluşturma işidir. Bu işlem bazı Frameworklerde ara yazılımlar sayesinde (ORM Tools), bazı frameworklerde ise elle gerçekleştirilmektedir.

ORM tekniği belli bir programlama diline bağlı değildir ve her OOP dilinde yazılabilir.

Avantaj
- 
- OOP metodu sunar.
- Yazılan kodun veritabanı çeşidiyle bağlılığı yoktur.
- SQL/JDBC bilmenize yazmanıza gerek kalmadan kısa bir zamanda ve daha az kod ile veritabanına bağlı bir uygulama yapabiliriz.
- Daha test edilebilir bir kod yazmamızı sağlar.

Dezavantaj
-
- Performans sorunu
- Veri transferi sırasında kontrolün yüzde yüz elde olmaması(Üretilen SQL bazen farklı olabilir)
- Kullanılan ORM aracını öğrenmek için harcanan zaman

ORM bize veritabanı üzerinde kayıt ekleme (INSERT), çekme (SELECT), düzenleme (UPDATE) işlemlerini daha kolaya indirgememizi sağlar. Bu işlemler direk ORM üzerinden gerçekleşmektedir. Bu yöntemin dışında katı SQL kodu yazarak da yapılabileceği gibi,






							    
							 **ORM Araçları**
    
						*1. Java için ORM frameworkleri:*
    
    - Hibernate
    
    - JPA
    
    - OpenJPA
    
    - Toplink
    
    - EclipseLink
    
    - Apache Cayenne
    
    - MyBattis
    
    
					    *2. .Net için ORM frameworkleri*
    
    - Entity Framework
    
    - Nhibernate
    
    - .Net Persistence
    
    - BBADataObjects-
    
    - DataObjects(.net)
    - DotNorm
    
    - FastObjects(.net)
    
    - Norm
    
    - OJB(.net)
    
					    **3. PHP için ORM frameworkleri:**
    
    - Propel
    
    - Doctrine
    
    - PHP-Activerecord
    
    - PdoMap
    
    - RedBean


ORM sayesinde SQL sorgularıyla yapılan birçok işlem SQL sorgusu kullanılmadan gerçekleştirilmektedir. 

Ornek
-
**Entity Framework**  kullanarak SQL Server üzerinde bulunan  **veritabanımıza**  bağlanarak veri çekme,veri  **ekleme**,veri  **silme**ve veri  **güncelleme**  işlemlerini anlatan bir örnek yapalım

Sql Server’ da “**dbOkul”**  isimli bir  **database**  oluşturarak içine “**ogrenci”**  ekleyelim.

![Sql Server'da dbOkul isimli bir database oluşturarak içine ogrenci ekleyelim](https://picasaweb.google.com/115368328299963382215/6624366539265349473#6624366543358441634)




<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExNDQ4MDAwNDQsLTQ1MzQ1MDI3MiwxNj
U2NDgxMDUxLDE1MzQ2MTQ3MzYsMTI3NjY4MzU1NiwtMTgwMTU5
NzE0M119
-->