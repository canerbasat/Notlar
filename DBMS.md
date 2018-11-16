# ENTITY FRAMEWORK

Microsoft tarafından geliştirilen .NET tabanlı bir ORM aracıdır.
EF geliştirilen bir uygulama ile veri tabanı arasında köprü olan bir araçtır.


Veritabanındaki :

 - Tabloları sınıflara,
 - Kolonları propertylere,
 - Kayıtları nesnelere
 Dönüştürerek uygulamanın direkt olarak veritabanına erişmesine gerek kalmadan tüm veritabanı işlemlerini gerçekleştirir.

Böylece veritabanı işlemlerinin SQL kodları yazmadan nesneler üzerinden kolayca yapılmasını sağlar.

Veritabanına yapılacak CRUD(create,read,update,delete) işlemlerini EF(entity framework) aracı tarafından algılanır ve dönüştürülür.

Bu işleme "*Code Generating*" denir.  EF kullanan geliştirici LINQ kullanarak sorgu yazabilir.

#### ENTITY DATA MODEL
Entity(varlık) 3 bölümden oluşur.

 1.  Conceptual Model 
	   - Model sınıflarımız ve bu sınıfların ilişkileri yer alacaktır 
	   - Bu sınıflar veritabanından bağımsızdır.
2.  Storage Model
	  - Tasarım modelimiz yer alır.
	  - Bu model içerisinde veritabanımıza ait view'laar , stored procedureler 


<!--stackedit_data:
eyJoaXN0b3J5IjpbNjE0NjU4ODc3LC0xOTU3MjA0MTgyLC0xMT
Q0ODAwMDQ0LC00NTM0NTAyNzIsMTY1NjQ4MTA1MSwxNTM0NjE0
NzM2LDEyNzY2ODM1NTYsLTE4MDE1OTcxNDNdfQ==
-->