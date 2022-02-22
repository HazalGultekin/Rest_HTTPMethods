# ``` REST VE RESTFUL ```


## WEB Servis Nedir?
- Verilerinizi web sayfanız dışında tüm cihazlarda göndermek istediğinizde devreye “web servis” kavramı girer.
- Web Service ile platform bağımsız tüm cihazlara veri aktarımı gerçekleştirilir.
- Facebook’da mesajlaşırken karşılıklı olarak mesajların hem web sayfasına hem de Facebook Messenger uygulamasına gelmesini Web Service sağlar. Messenger uygulaması, Android, IOS, Wİndows Phone işletim sistemli cihazlarda çalışması Web Service kavramının gücünü kanıtlamaktadır.


## REST Nedir?
- Client-server arasındaki haberleşmeyi sağlayan HTTP protokolü üzerinden çalışan bir mimaridir.
- Rest, servis yönelimli mimari üzerinde oluşturulan yazılımlarda kullanılan bir transfer yöntemidir. 
- İstemci ve sunucu arasında XML ve JSON verilerini taşıyarak uygulamanın haberleşmesini sağlar.
- REST mimarisinde tüm bilgiler URL’ler üzerinden oluşturulur.

## RESTFUL Nedir?
- REST mimarisini kullanan servislere RESTFUL servis denir.
- Restful servislerinin amacı client-servis arasındaki veri akışını platform bağımsız olarak gerçekleştirebilmek ve veri akışını en az yükle sağlayabilmektedir.
- Restful servisleri response tipi olarak JSON, HTML, XML gibi bir çok formatta çalışabilirler. 
- Yapısının az yer kaplaması ve bir çok mobil platformda kullanışlı olmasından dolayı response tipi olarak JSON kullanılmaktadır.
- Restful servisleri esnek ve kolay geliştirilebilir bunun yanında dil ve platform bağımsızdırlar.

## Client-Server yapısı : 
Client, server tarafındaki veri kaynağı ile ilgili hiçbir şey bilmediği gibi, server da client hakkında birşey bilmemelidir. Server sadece kendisine gelen istekler doğrultusunda değer döner. Böylece server daha basit ve scalable olur.

![alt text](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRKk5bbEuFHSxe0o5sY2mkR0s5hBdjmIvbECQ&usqp=CAU)







 # ``` HTTP METOTLARI ```
- HTTP, web browser ile web server arasındsa iletişim kurmamızı sağlayan bir protokoldür.
- Sunucu ve istemci arasında bir köprü vazifesi görür.

HTTP 1.1 versiyonu(RFC 2616) ile tanımlanan ve diğer eklentilerle gelen başlıca HTTP metotları şunlardır:

## GET:
- Bu metodu sunucudan veri almak için kullanırız. 
- Hızlıdır fakat güvenli değildir. 
- Get metodu ile bir istekte bulunduğumuzda bu isteği tarayıcı üzerinde açık bir şekilde görüntüleyebiliriz, bu durum büyük güvenlik sorunlarına yol açmaktadır.

### Örn:
http:example.com/test/demo_form.php?name1=value1&name2=value2

URL’yi bir web sunucusundan HTML belgelerini almak için kullanırız.
Kullanıcı tarafından bir sorgunun arama motoruna gönderilmesinden sonra(URL ile gönderilir), motor sorguyu yürütür ve sonuçtaki sayfayı verir.  Sorgu sonuçları bir link (yer imi) olarak ayarlanabilir.

### Örn: GET ile sipariş detaylarını getirebiliriz.
		GET : /orders/{id}

### Örn: 
Kullanıcı bir tarayıcının konum çubuğuna herhangi bir URL girdiğinde, http // www.example.com / xyz / file1.htm gibi . Adres daha sonra geçerli bir HTTP GET isteğine dönüştürülür, örneğin, GET / xyz / file1.htm HTTP / 1.0 .
Bu istek daha sonra www.example.com sunucusuna aktarılır. İstek, xyz dizinindeki file1.htm dosyasını ve HTTP'nin 1.0 lehçesine bağlanıp bağlanmadığını sorar. Burada kullanıcı dosyayı gönderdikten sonra dosyayı kendisi almaz, gerçekte form verilerini işlemek için bir program arka planda çalışıyor.
Kullanıcı, yürütülmesi için programın adıyla form verilerini iletmelidir. Bu yürütmeyi başarmak için form bilgileri istenen URL'ye eklenir. Gerçek verilerle birlikte yüz karakterli bir URL oluşturur; örneğin, //www.example.com/cgi-x/comments.exe?Name=AI+Alena&Age=23&Gender=female .


## POST:
- Sunucudan veri almak için kullnaılır ancak mevcut olan bir veriyi güncellemek için de kullanılır.
- Doğrudan sayfaya veri gönderilir ve veriler adres çubuğunda görünmez. Bu yğzden daha güvenilir bir yöntemdir.
- Bu metodla istek parametreleri hem URL içinde hem de mesaj gövdesinde gönderebiliriz.

Get metodunda bilgiler açık bir şekilde iletildiği için kullanıcı işlemleri ya da gizli olması gereken işlemlerde Post metodu kullanılır.
Post metodunu kullandığımızda yaptığımız istekler tarayıcı üzerinden gizli bir şekilde gönderilir.

### Örn:
POST /test/demo_form.php HTTP/1.1
Host: example.com
name1=value1&name2=value2
Post metoduyla gönderilmek istenen bilgiler mesaj gövdesinde yer alır bu şekilde url adresi üzerinde bir bilgi görüntülenmez. Bir sitede form doldurduktan sonra bir önceki sayfaya gitmek istediğinizde bir uyarı ile karşılaşırız bunun sebebi Post metodu ile giden bilgileri tekrar tekrar sunucuya yüklemek istenmemesinden kaynaklanmaktadır.

### Örn: POST ile yeni bir sipari oluştururuz.
		POST:/orders
    
### Örn:
Bir form tarafından gönderilen veriler İsim = AI + Alena ve Yaş = 23 ve Cinsiyet = kadın gibi görünebilir. Program verileri bölümlere ayırarak işler. Form verileri, POST yönteminde ENCTYPE özniteliği kullanılarak farklı şekilde kodlanabilir.
Form içeriği genellikle URL’de görülmez ve ana avantajı, POST yöntemi kullanılarak önemli miktarda veri gönderilebilmesidir.


## SONUÇ: GET - POST 
Verileri sunucuya göndermek için GET ve POST yöntemi kullanılır ve aralarındaki temel fark, GET yönteminin verileri formun işlem özelliğinde tanımlanan URI'ye eklemesidir. Tersine, POST yöntemi verileri istenen kuruluşa ekler. GET yönteminin kullanılması, hassas bilgilerin formda doldurulması gerektiğinde uygun değildir. POST yöntemi, kullanıcının şifreleri veya diğer gizli bilgileri doldurması gerektiğinde yararlıdır.

### Aşağıdaki şekilde GET ve POST farklılıkları daha rahat bir şekilde görülmektedir.

![alt text](https://ugurgelisken.com/wp-content/uploads/2017/07/bb.png)


## İLİŞKİLİ APİ UÇLARI
![alt text](https://miro.medium.com/max/1400/1*GIiYwvBEFReWH4QAdU0Mzw.png)



## PUT :
- PUT metodu ile sunuculara veri (genellikle de dosya) atılmak için kullanılır. 
- POST gibi metodlardan farklı olarak gönderilen bu veri (katar veya dosya) ile hedef sunucuya dosya gönderilir. Gönderilen dosya ile aynı isimde bir dosya varsa da üzerine yazar, yoksa belirtilen isimde ve içerikteki dosya oluşturulur.
- Veri güncellemek için kullanılır. PUT ‘un POST’dan farkı idempotent olmasıdır.Yani bir request birden fazla kez tekrarlansa da sonucunun aynı olmasıdır.
### Örn: PUT ile belirli sipariş güncelleriz.
PUT : /orders/{id}
### Örn: PUT /orders de update edilecek bir sipariş yok.Tüm siparişleri de güncelleyemeyeceğimize göre PUT metodunu kullanamayız.

## PATCH :
Verinin sadece bir parçasını güncellemek için kullanılır.
### Örn: PATCH /addresses/1

## HEAD :
GET metoduyla benzer işleve sahiptir ancak geri dönen yanıtta mesaj gövdesi bulunmaz(yani başlıklar ve içerikleri GET metoduyla aynıdır.) 
Bu nedenle GET mesajı gönderilmeden önce bir kaynağın var olup olmadığını kontrol etmek için kullanılabilir.


## DELETE :
Bu metod ile sunucu üzerinde bir veriyi silebilirsiniz. Bu metod ile yaptığınız bir istekte, tanımlanmış olan veri id değerini gönderip, o id değerine karşlık gelen veriyi sunucu üzerinden silebilirsiniz.

### Örn: Id’si verilen adresi sileriz.
DELETE /addresses/id



# HTTP STATUS KODLARI
- Başarılı KOdlar: 2xx
- Yönlendirme: 3xx
- Client(istemci) Hataları: 4xx
- Server Hataları: 5xx


