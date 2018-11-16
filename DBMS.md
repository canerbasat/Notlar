Object Relational Mapping

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

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4NzIyNTUwNTYsMTI3NjY4MzU1NiwtMT
gwMTU5NzE0M119
-->