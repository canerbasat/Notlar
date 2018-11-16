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

İlk önce veritabanı tabloları tasarlamak yerine,  ilk olarak, her bir öğrencinin ilişkili olduğu  `Oğrenci` ve `Sınıf` classlarını oluşturun.

```csharp
public class Ogrenci
{
    public int OgrenciID { get; set; }
    public string OgrenciName { get; set; }
    public DateTime? DogumYılı { get; set; }
    public byte[]  Resim { get; set; }
    public decimal Boy { get; set; }
    public float Kilo { get; set; }
        
    public Sınıf Sınıf { get; set; }
}
```
Aşağıda gösterildiği gibi Sınıf sınıfını oluşturun.

```csharp
public class Grade
{
    public int SınıfID { get; set; }
    public string SınıfAdı { get; set; }
    public string Section { get; set; }
    
    public ICollection<Ogrenci> Ogrenciler { get; set; }
}
```


[Code-First](http://www.ugurkizmaz.com/YazilimMakale-1858-Entity-Framework-Code-First-Nedir--Ornek-Proje-ile-Inceleyelim.aspx) yaklaşımı, DbContext sınıfından türetilmesi gereken bir bağlam sınıfını da gerektirir. Aşağıda gösterildiği gibi bir içerik sınıfı oluşturun.


DBContext sınıfından türetilir ve modelin parçası olmak istediğiniz türler için DbSet özelliklerini gösterir, ör. Bu durumda Öğrenci ve Sınıf sınıfları. DbSet, varlık sınıflarının bir koleksiyonudur

```csharp
 public class SchoolContext: DbContext 
    {
        public SchoolContext(): base()
        {
            
        }
            
        public DbSet<Ogrenci> Ogrenciler { get; set; }
        public DbSet<Sınıf> Sınıflar { get; set; }
    }
```


Şimdi, codefirst yaklaşım için gerekli sınıflar ile bitmiştir.
Aşağıda gösterildiği gibi içerik sınıfını kullanarak bir öğrenci ekleyeceğiz.


```csharp
class Program
    {
        static void Main(string[] args)
        {
     
            using (var ctx = new SchoolContext())
            {
                var stud = new Student() { StudentName = "Bill" };
        
                ctx.Students.Add(stud);
                ctx.SaveChanges();                
            }
        }
    }
```

Uygulamayı çalıştırırsanız, bir öğrencinin veritabanına başarıyla eklendiğini görürsünüz.

Pekiiii bu veritabanı nerede nasıl oluştu ???

Bu EF Code-First API'nin güzelliğidir. Bağlam sınıfınızın temel yapıcısında geçirilen parametrelere dayanarak veritabanını oluşturur.

İçerik sınıfımızın yapıcısında herhangi bir parametre geçmediğimiz için, yerel SQLEXPRESS veritabanında ***NameofYourProject.SchoolContext*** veritabanı oluşturdu.

Ayrıca bu veritabanında, yukarıda tanımlanan Öğrenci ve Sınıf alan sınıflarına dayalı `Öğrenci` ve `Sınıf` olmak üzere iki tablo oluşturdu.

![enter image description here](http://www.entityframeworktutorial.net/images/codefirst/codefirst-db.PNG)
Yukarıdaki ekran görüntüsünde gördüğünüz gibi, Öğrenciler ve Sınıflar tabloları oluşturdu ve her tablo , uygun veri tipi ve uzunluğa sahip sütunlar içeriyor.

Sütun adları ve veri türü, ilgili alan adı sınıflarının özellikleriyle eşleşir.(Classlarda tanımladığımız değişkenker)

Ayrıca, StudentId ve GradeId'i primarykey (birincil anahtarlar) haline getirdi ve foregin key (yabancı anahtar) olarak Grade_GradeId sütununu yarattı.
