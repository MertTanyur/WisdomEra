## Wisdomera Core-1 whatsapp soruları
**mert tanyur**


## Soru 1 vue.js te created ve mounted'in farkı nedir , örneklerle açıkla

Created ve mounted vue.js deki life cyclesta kullanılan 2 zaman belirtecidir.

bu terimleri gerçek bir problem üzerinden açıklamak isterim

Diyelim bizim bir vue instancemiz var 

>  var app = new Vue({
> 
> 
> el: '#app'
> 
> 
> data: {
> 
> 
> 	hastalar : []
> 
> 	})

şimdi bu instace mizin içerisindeki hastalar kısmı boş fakat biz sağlık çalışanlarımıza sunacağımız ekranda hastalar kısmının boş olmasını istemeyiz

o yüzden onların ekranları daha yüklenmeden bizim bu hastalar kısmını doldurmamız gerekiyor

Created opsiyonu aynı el ve data opsiyonu gibi vue instance içerisinde bir opsiyondur ve onlarla eş zamanda yaratılıp render olur.

biz de created opsiyonu sayesinde hastalar listemizin içerisine databasemizden hastaları getirelim


>var app = new Vue({
	el: '#app'
	data: {
		hastalar : []
	},
	created(){
	//pseudo code (kodlar gerçeği yansıtmaz) eyy database bana hastalari getir 

> database.get().then((res) => {
  >      this.hastalar = res.data;
    >}).catch((hastaListesi) => {
        this.hastalar = hastaListesi ;
    });
>}  



artık hasta listemizin içerisi dolmuş oldu , şimdi bizim sağlık çalışanlarımız bu hastaları filtrelemek istiyor

kimse koskoca bir listeyle başa çıkamaz

bu hastaları filtrelemek için ekrandaki bazı butonları kullanıyorlar dolayısıyla ekrandaki html elementleri sayesinde ( DOM'u kullanarak)vue instance mizin içerisindeki data filtrelemek istiyorlar

böyle bir işlemi yapabilmek için mounted opsiyonunu kullanırız.

 sağlık çalışanlarımıza  browserlerlinde ilgili ekranı açıp önlerine görsel olarak ekran geldikten  sonra ekrandaki html elementleriyle yapacağı etkileşimlerin vue instancemizdeki datayı manipüle etmesini istiyorsak MOUNTED opsiyonunun içerisine bu değişiklikleri yazabiliriz.


 bu kadar detaya girmeden sadece sayfa yüklendikten  ve sağlık çalışanlarının önüne görsel olarak geldikten sonra bir uyarı vermesini istiyoruz


 

> var app = new Vue({
> 
> 
> el: '#app'
> 
> 
> data: {
> 
> 
> 	hastalar : []
> 
> 
> },
> 
> 
> created(){
> 
> 
> //pseudo code (kodlar gerçeği yansıtmaz) eyy database bana hastalari
> getir
> 
> 
> database.get().then((res) => {
> 	        this.hastalar = res.data;
> 	    }).catch((hastaListesi) => {
> 	        this.hastalar = hastaListesi ;
>     },
>     mounted(){
>     	alert("hastalari filtrelemek istediğiniz metodları seçin ");
>     }
> 
> 
> )}

## 2. soru port nedir minieradaki 8888 portu ne yapar:

backend ve front endi arasındaki 8888 portu
buradaki iki wisdomera uygulamasının internete bağlanarak birbirine bilgi aktarması için buluştukları ortak nokta. 

bu uygulamalar birbirine bilgi aktarmak için TCP denilen bir protokolü kullanıyorlar.


## 3. soru minieradaki uygulamalar hangi portları kullanıyor ?

8888: backend ile frontend arasındaki port
8080 : kullanıcı ile frontend arasındaki port
8091 : backend ile couchbase arasındaki port

## 4.soru python'dan couchbase bağlanmamızı sağlayan modül nedir

python couchbase sdk


## 5. soru git commit komutu ne işe yarar


kolabaratif calistigimiz yazılım ekibimizin veya kendimizin daha sonra baktığında anlam verebilmesi için bir kilometre taşı ya da snapshot oluşturuyoruz
Mesajı belirtmek icin de **-m "write your message here "** opsiyonunu kullanıyoruz

git commit komutu sayesinde ***.git*** dosyasının bulunduğu directory icerisinde  git add komutu tarafından tracked edilmiş tüm file lardaki degisimleri commit komiti ile snapshot alabiliriz


## 6. soru sys kütüphanesi ne yapar?

Python dosyasının içerisinde bir çok işi yapan fonksiyon bulunabilir,

Biz bu  fonksiyonlarlardan istediğimizi kolayca cmd'den  cagirabilmek için sys isimli kütüphaneyi  kullanırız.
 
Normalde bir Python dosyasını çalıştırmak için cmd den Python yazıp yanına *fileName.py*  yazarız.

Sys kütüphanesi bize cmd'den  istediğimiz fonksiyonu calistirabilme opsiyonu tanır ve  artık cmd ye 
Python *fileName.py -bizim belirledigimiz bir fonksiyonun ismi*

Yazdığımızda o .py dosyasını sys kutuphanesi sayesinde daha **custom** sekilde calistirabiliriz.




