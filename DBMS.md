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

İlk önce veritabanı tabloları tasarlamak yerine,  ilk olarak, her bir öğrencinin ilişkili olduğu  `Oğrenci` ve `Not` classlarını oluşturun.


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3NzMwNjY4MjcsMTUyMDgxMDcxMCwtMT
k1NzIwNDE4MiwtMTE0NDgwMDA0NCwtNDUzNDUwMjcyLDE2NTY0
ODEwNTEsMTUzNDYxNDczNiwxMjc2NjgzNTU2LC0xODAxNTk3MT
QzXX0=
-->