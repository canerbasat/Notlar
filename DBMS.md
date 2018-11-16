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
public class Student
{
    public int StudentID { get; set; }
    public string StudentName { get; set; }
    public DateTime? DateOfBirth { get; set; }
    public byte[]  Photo { get; set; }
    public decimal Height { get; set; }
    public float Weight { get; set; }
        
    public Grade Grade { get; set; }
}
```
Aşağıda gösterildiği gibi Sınıf sınıfını oluşturun.

```csharp
public class Grade
{
    public int GradeId { get; set; }
    public string GradeName { get; set; }
    public string Section { get; set; }
    
    public ICollection<Student> Students { get; set; }
}
```


[Code-First](http://www.ugurkizmaz.com/YazilimMakale-1858-Entity-Framework-Code-First-Nedir--Ornek-Proje-ile-Inceleyelim.aspx) yaklaşımı, DbContext sınıfından türetilmesi gereken bir bağlam sınıfını da gerektirir. Aşağıda gösterildiği gibi bir içerik sınıfı oluşturun.



<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM2MjU5NjY2MywxNTIwODEwNzEwLC0xOT
U3MjA0MTgyLC0xMTQ0ODAwMDQ0LC00NTM0NTAyNzIsMTY1NjQ4
MTA1MSwxNTM0NjE0NzM2LDEyNzY2ODM1NTYsLTE4MDE1OTcxND
NdfQ==
-->