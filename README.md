# SektordeSolid

Turkcell Geleceği yazanlar ödevi

<h3> Single Responsibilty </h3>

Bu prensibe göre bir sınıfın yalnızca tek bir sorumluluğu olmalıdır. Başka bir deyişle, yazılımınız içinde birden fazla farkı görevi yapan kısım olmamalıdır.  Bu ilkede, yazılım kodunda her bir sınıfın, modülün veya metodun yalnızca bir iş yapması istenir. Örneğin, sınıf sadece konusu ile ilgili değişken ve yöntemleri içermelidir.

<h4> Single Responsibilty Sektörden Örneği</h4>

Buna örnek olarak alışveriş yapmak diyebiliriz. Bir ürünün fiyatlandırmasında, satışında ve alımında 3 kişi bulunur ve her birinin sadece bir sorumluluğu bulunmakta. Eğer fiyatlandırma konusunda bir sorun varsa kasiyer, satışında bir sorun olursa satış elemanı, ödeme sırasında bir sorun oluşursa müşteri sorumlu tutulur. Bu şekilde değil de satış elemanı hem fiyatlandırma hem satış ile uğraşacak olursa işlerde karmaşaya yol açacaktır. Bunu yazılım olarak ele alacak olursak da kod karmaşıklığı ve okunabilirlik bakımından yazılımcıları sıkıntıya sokabilir. Aynı zamanda hata ayıklama sırasında da koddaki hangi bölümün hata yaptığının anlaşılması zorlaşır.
