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
	  - Bu model içerisinde veritabanımıza ait view'laar , stored procedureler ve bunlara ait ilişkiler ve keyler yer alır.
3. Mapping
	  - Mapping alanı ise model sınıflarımız ve tasarım modelimiz arasındaki haritalama işlemlerinin bilgilerinin tutulduğu alandır.

Ornek
-
XYZ Okulu için basit bir uygulama oluşturmak istediğimizi varsayalım. Bu Okul uygulamasının kullanıcıları, öğrencileri, notları, öğretmenleri ve kurs bilgilerini ekleyebilmeli ve güncelleyebilmelidir.

İlk önce veritabanı tabloları tasarlamak yerine, gerektiğinde ilk olarak, her bir öğrencinin o ile ilişkili olduğu `Oğrenci` ve `Sınıf` classlarını oluşturun.

İlk olarak, oluşturma `Ogrenci`ve `Sınıf`her sınıfları `Sınıf`biri ile ilişkili olan `Grade`, aşağıda gösterildiği gibi. Buna bire çok ilişki denir. EF varlıkları (domain sınıflar) arasındaki ilişkiyi yöneten nasıl öğrenin
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjA0OTY3MDU5NCwxNTIwODEwNzEwLC0xOT
U3MjA0MTgyLC0xMTQ0ODAwMDQ0LC00NTM0NTAyNzIsMTY1NjQ4
MTA1MSwxNTM0NjE0NzM2LDEyNzY2ODM1NTYsLTE4MDE1OTcxND
NdfQ==
-->