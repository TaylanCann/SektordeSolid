# SektordeSolid

Turkcell Geleceği Yazanlar Ödevi

Taylan Can Hardal <br>
Ömer Gürbüz  <br>
Kübra Karagülle 


<h3> Single Responsibilty </h3>

Bu prensibe göre bir sınıfın yalnızca tek bir sorumluluğu olmalıdır. Başka bir deyişle, yazılımınız içinde birden fazla farkı görevi yapan kısım olmamalıdır.  Bu ilkede, yazılım kodunda her bir sınıfın, modülün veya metodun yalnızca bir iş yapması istenir. Örneğin, sınıf sadece konusu ile ilgili değişken ve yöntemleri içermelidir.

<h4> Single Responsibilty Sektörden Örneği</h4>

Buna örnek olarak alışveriş yapmak diyebiliriz. Bir ürünün fiyatlandırmasında, satışında ve alımında 3 kişi bulunur ve her birinin sadece bir sorumluluğu bulunmakta. Eğer fiyatlandırma konusunda bir sorun varsa kasiyer, satışında bir sorun olursa satış elemanı, ödeme sırasında bir sorun oluşursa müşteri sorumlu tutulur. Bu şekilde değil de satış elemanı hem fiyatlandırma hem satış ile uğraşacak olursa işlerde karmaşaya yol açacaktır. Bunu yazılım olarak ele alacak olursak da kod karmaşıklığı ve okunabilirlik bakımından yazılımcıları sıkıntıya sokabilir. Aynı zamanda hata ayıklama sırasında da koddaki hangi bölümün hata yaptığının anlaşılması zorlaşır.

<h3> Open/Closed </h3>

Bu ilke, bir sınıf veya yöntemin geliştirilmeye açık, ancak değiştirilmeye kapalı olması gerektiği anlamına gelir. Sonuçta değişmeyen tek şey değişimdir. Haliyle ürünler de zamanla değişecek. Ancak her seferinde kodu tekrar yazmak, içeriğinde oynama yapmak, o içeriğe erişen komutlarda sıkıntıya yol açabilir. Bu yüzden kodu değiştirmeden geliştirmeye çalışacağız. Prensip de tam olarak bizden bunu istiyor.

<h4> Open/Closed Sektörden Örneği</h4>

Örnek olarak sürekli elimizin altında olan telefonları göstermek prensibin anlaşılması açısından daha temiz olacaktır. Telefonların internet bağlantılarını class olarak düşünelim. Bu bağlantılar: 3G ve 4.5G, 5G. Bu teknolojiler gelişirken bağlantı hataları aldığınızı düşünün. 3G'den 4.5G'ye geçerken 1 hafta internete girememek mantıklı olmazdı değil mi? O yüzden yazılım geliştirirken de kaynak kodlara dokunmadan geliştirmek gerekir ki hata almayalım. O yüzden yazdığımız classları gelişime açık değişeme kapalı tasarlamalıyız. 

<h3> Liskov Substitution </h3>

LSP prensibi Open Closed prensibinin özel bir türüdür desek yanlış olmaz. OCP’de de olduğu gibi LSP de de genişlemeye açık yapılar söz konusudur. Her ne kadar anlaşılması biraz zor olsa da LSP ilk bakışta, altında yatan ana fikri: alt sınıflardan oluşan nesnelerin üst sınıfın nesneleri ile yer değiştirdikleri zaman, aynı davranışı sergilemesini beklemektir.

<h4> Liskov Substitution Sektörden Örneği</h4>

Müşteriden bir istek geldiğini düşünelim, bunu sağlamak için mevcut olan bir class’ten child class üretiyoruz, veyahut method’ları override ediyorsuz. Mevcut class yerine child class’i kullandığında bir hata oluşmamalı ya da worst case’de çıkan hata, bütün uygulamayı darmadağın etmemeli. Türetilmiş sınıflar (ihtiyaç üzerine method’ları override edilmiş ya da extend edilmiş), türetilikleri class’ler ile değiştirilebilir olmalıdır kısaca.

<h3> Interface Segregation </h3> 

Bu prensibi tek cümleyle açıklayacak olursak: Nesneler, ihtiyaç duymadıkları metotların bulunduğu Interface’lere bağlı olmaya zorlanmamalıdır. Projede kullanılan interface'leri olası tüm özelliklerle boğmak ve sonrasında kullanılmayan özellikler için throw ya da null atmak yerine interface'i parçalara ayırırsak hem daha efektif bir kullanım sağlar, hem okunabilirliği arttırır, hem de interface'lerin kullanımını kolaylaştırır.

<h4> Interface Segregation Sektörden Örneği</h4>

Örneğin, günümüz gelişmiş çok fonksiyonlu yazıcılarında hem tarama hem yazdırma hem fax hem wi-fi özellikleri mevcut. Eğer biz yazıcı sınıfının içerisine bu 4 niteliği belirtecek olursak, yalnızca yazdırma özelliğine sahip bir sınıf üretemeyecektik. Üretecektik belki de ama tarama özelliği null olacaktı, fax özelliği boşa yer kaplayacaktı. Bu yüzden biz nitelikleri farklı interface'ler altında işleyerek projeyi geliştirirsek, kullanıcının olası tüm isteklerine kolaylıkla cevap verebiliriz.

<h3> Dependency Inversion </h3>

Temelde yüksek seviye modüller, düşük seviye modüllere bağlı olmamalı, her ikisi de abstract kavramlara bağlı olmalı esasına dayalı bir prensiptir. Ayrıca soyut kavramlar da detaylara bağlı olmamalı, detaylar soyut kavramlara bağlı olmalıdır. Bu prensibin arkasında yatan asıl sebep herhangi bir küçük modülde oluşan bir hata yahut uyuşmazlık sonucu tüm projeyi değiştirmek yerine küçük modülü değiştirmek ve belki de yeni bir küçük modül yazarak projenin akışını bozmamaktır. Bu prensibi kullanarak daha kolay yeniliğe adapte olan programlar yazabileceğiz.

<h4> Dependency Inversion Sektörden Örneği</h4>

Hâli hazırda çalışan bir projede Microsoft SQL veritabanı kullanılıyor olsun. Veritabanının yaptığı işi de örneği sadeleştirmek açısından sınırlayalım: Projede veritabanı sadece veri çekmek için kullanılıyor olsun. İlerleyen zaman içinde NoSQL veritabanlarından Firebase'e geçiş yapılacak olursa proje modülleri değişmek zorunda kalacak. Bu da hem zaman hem karmaşıklık bakımından sıkıntıya sebep olacak. Ancak biz veritabanı işlemlerini yaptırmak için bir interface'den implemente edilmiş sınıf kullanmış olsaydık, aynı interface'den farklı bir sınıf üreterek yeni sınıfı direkt kullanabiliyor olacaktık.
