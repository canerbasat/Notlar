# ADO(ActiveX Data Object)

"ADO" basit olarak veriye erişebilmek için seçilen yoldur.
Object Oriented Program(OOP) geliştirme araçlarında genellikle nesnelerin metodlarından faydalanır.

Bu çerçevede ADO'da veri tabanı işlemleri için geliştirilmiş bir nesnedir.
Metodları sayesinde veri tabanı üzerinde işler yapılır.

    Veri tabanına bağlanmak için bir provider seçmemiz gerekir.

ADO. NET veri sağlayıcısı, bir veri kaynağı ile etkileşime giren bir yazılım bileşenidir. ADO. NET veri sağlayıcıları, ODBC sürücüleri, JDBC sürücüleri ve OLE DB sağlayıcıları ile benzerdir.

ADO. NET sağlayıcıları, Oracle Veri Tabanı, Microsoft SQL Server, MySQL, PostgreSQL, SQLite, IBM DB2, Sybase ASE ve diğerleri gibi karmaşık veritabanlarına, bir metin dosyası ve elektronik tablo gibi basit veri depolarına erişmek için oluşturulabilir.

#### NESNELER(OBJECT)
- DAO(Data Acsess Object)
- RDO(Remote Data Object)
- ADO(Activex Data Object)

ADO gerek OLEDB gerekse ODBC ile ve gerek Windows tabanlı tüm uygulamalarda kullanılan en son geliştirilmiş veri işlemleri için ideal olan bir nesnedir.

DAO , veri nesnesi özellikle visual basic eski sürümlerde kullanılan bir nesnedir. Kısıtlı bağlantı sağladığından artık pek kullanılmamaktadır.

RDO , uzak veri nesnesi ODBC(Open Database Connectivity) veri kaynağı sağlayıcısı ile birlikte yine eski yazılımlarda kullanılan bir objedr. ADO'ya daha yakın ve ActiveX bir nesneydi. Ancak daha çok Windows Tabanlı yazılımlarda kullanılıp , web tabanlı yazılımlar için kullanılmamaktaydı.

**VERI SAGLAYICILARI(DATA PROVIDERS)**

**-ODBC-**
ODBC(Open Database Connectivity) Açık veri tabanına bağlanabilme bir sunucu arayüzü olup , Windows yönetimsel bir alt ürünüdür.
Özellikle server tabanlı Windows sürümlerde datalara erişim sağlamak için kullanılır.

Dataya erişim için DSN(Database System Name) kısmında tanım yapılmalıdır. ODBC ile daha çok Windows tabanlı uygulamalarda veri erişimi sağlamaktaydı. Özellikle de nesne olarak RDO' yu kullanmaktaydı. Ancak son zamanlarda ADO'yuda kullanmaktadır.

**-OLEDB-**
OLEDB(Object Linking Embedding Database) nesneler arası haberleşen veri tabanı yani , OLEDB bir veri kaynağı sağlayıcısıdır. Yalnız kullanılabileceği gibi , ADO ile'de kullanılabilir.

> ODBC = Mutlaka bir nesne kullanır.
> OLEDB= Nesnesizde kullanılabilir.

Bir uygulama geliştirirken en üst seviyede uygulamalarımız yer almaktadır.(Bir web veya Windows app farketmez.)

Bu katmanın hemen altında ADO ve/veya OLEDB veri kaynağından alınan verileri uygulamaya iletmek için yer alırlar.
Fakat OLEDB tüm programlama dilleri ile çalışabilecek şekilde değildir bundan dolayı ADO,OLEDB üzerinde bir geçiş katmanı görevi yapmaktadır.

ADO, OLEDB 'nin desteklemediği diller arasında arabirim görevi yapmaktadır. ADO , OLEDB 'ye göre daha kolay bir programlama arabirimine sahiptir.

Bu sebepten dolayı direkt OLEDB erişimi alabilen programlama dilleri(C++ , JAVA, .NET) veri kaynağına erişimi daha kolay hale getirebilmek için ADO kullanabilmektedirler.



ADO sadece Microsoft programlama dilleri ile değil bir com bileşeni(component) olduğu düşünüldüğünde  , diğer com destekli programlama dillerinde de (Delphi , Active Scripting Interface destekleyen script dilleri) kullanabilmektedir.

** 

*Data erişimi için OLEDB ve ADO' nun kullanabilceğini anladık . Peki ya neden eski metodları kullanmıyoruz bunun için iki büyük sebep var.*

1- OLEDB ve ADO bir veri kaynağına(database) erişmek için tasarlanmış.
Veri tabanları en çok kullanılan veri kaynağı olsada bir çok uygulama : (mesajlaşma sistemleri , Microsoft Exchange Server , Dizin hizmetleri ve Web sunucuları) veri tabanı dışında bir yapı kullanmaktadır.

2-) Internet uygulamaları hızla yaygınlaşmıştır. Eski data erişim metodları webden data için geliştirilmemiş.


***ADO OBJE MODELI***

ADO obje yapısıdır bir classtır(sınıftır).
Bu classın metodları vardır.

Connection = Connection objesi data kaynağına veya veritabanına direkt bağlanmak için kullanılmaktadır.

Command = Command objesi data kaynağı üzerinden komutlar çalıştırmak için tasarlanmıştır. Command objesi geriye kayıt döndürmeyen komutların kullanımı içinde uygundur.(SQL,INSERT,UPDATE)


Record Objesi = Record objesi ADO içerisinde en çok kullanılan objedir. Bu obje data kaynağından aldığı veriyi bir dizi şeklinde bize sunar. Bu obje sayesinde ADO bize veriler üzerinde değişiklik yapmamıza kayıtları taşımamıza ve kayıtları filtrelememize izin veir.
		Recordset objesi "Field" koleksiyonunu içerir.
		Bu koleksiyon sayesinde veri kaynağındaki tüm alanlara erişebiliriz.
