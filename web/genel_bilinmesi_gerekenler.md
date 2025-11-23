# Web Teknolojileri: Genel Bilinmesi Gerekenler

## 1. Giriş

Bu doküman, web teknolojileri sınavlarına hazırlık için kritik bilgileri içermektedir. İçerik, internet altyapısından HTML5'e, CSS'ten JavaScript'e kadar geniş bir yelpazeyi kapsamaktadır.

## 2. İnternet Altyapısı, Protokoller ve Tarihsel Gelişim

Web teknolojilerini anlamak, öncelikle bu teknolojilerin üzerinde koştuğu altyapıyı, yani interneti ve onun temel bileşenlerini kavramakla mümkündür. Sınav materyalleri, internetin fiziksel varlığı ile onun üzerinde çalışan servisler arasındaki ayrımı net bir şekilde çizmeyi hedeflemektedir.

### 2.1. İnternet ve World Wide Web (WWW) Dikotomisi

Akademik ve teknik literatürde "İnternet" ve "World Wide Web" (WWW) kavramları sıklıkla birbirinin yerine kullanılsa da, sınav müfredatı bu iki kavramın kesin çizgilerle ayrılmasını talep etmektedir. İnternet, 1960'larda ARPANET projesiyle temelleri atılan, küresel çapta bilgisayar sistemlerini birbirine bağlayan, TCP/IP protokol yığını üzerinde çalışan devasa bir fiziksel ve mantıksal ağdır. Bu ağ, bilgisayarların birbirleriyle haberleşmesini, veri paketlerinin yönlendirilmesini ve fiziksel bağlantıyı ifade eder. İnternetin tanımı sınavlarda genellikle "kişisel bilgisayarları birbirine bağlayarak bilgi alışverişini artırmak ve dünya çapında haberleşmeyi sağlamak" şeklinde karşımıza çıkmaktadır.

Buna karşın, World Wide Web (WWW) veya kısaca Web, internet altyapısı üzerinde çalışan, hiper metin (hypertext) transfer protokolü (HTTP) aracılığıyla bilgi paylaşımını sağlayan bir servistir. Dolayısıyla, internet bir otoban ise, WWW bu otobanda hareket eden araçlardan sadece biridir. Sınav sorularında "İnternet ile www kavramları farklı anlama gelir" ifadesi, bu hiyerarşik ilişkiyi doğrulayan temel bir önerme olarak kabul edilmektedir. Ayrıca, internetin tarihsel sürecinde 1993 yılı, bu teknolojinin kamusal kullanıma tam anlamıyla açıldığı ve ticarileşmeye başladığı kritik bir dönemeç olarak işaretlenmektedir.

### 2.2. Protokoller: IP ve DNS Mimarisi

Ağ üzerindeki iletişimin sağlanabilmesi için cihazların birbirini tanıması ve belirli kurallar (protokoller) çerçevesinde konuşması gerekmektedir. Sınav kapsamında bu protokollerden özellikle IP (Internet Protocol) ve DNS (Domain Name System) üzerinde durulmaktadır.

**Internet Protocol (IP)**: IP, ağa bağlı her cihazın kimliğini belirleyen sayısal adresleme şemasıdır. Sınav analizleri, IP'nin görevlerini ve görev sınırlarını netleştirmektedir. IP'nin temel işlevi, bilgisayarların birbirleriyle haberleşmesini sağlamak ve sunucu-istemci mimarisinde bağlantı kurmaktır. Ancak, öğrencilerin sıklıkla karıştırdığı bir nokta olarak, IP protokolü kendi başına "virüsleri engelleme" veya ağ güvenliği sağlama gibi bir misyona sahip değildir; bu görev güvenlik duvarlarına ve antivirüs yazılımlarına aittir. Benzer şekilde, kişisel bir bilgisayara IP adresi atama işlemi IP protokolünün kendisi tarafından değil, genellikle DHCP (Dynamic Host Configuration Protocol) servisi veya manuel konfigürasyon ile gerçekleştirilir.

**Domain Name System (DNS)**: Kullanıcıların karmaşık sayısal IP adreslerini (örn. 192.168.1.1) ezberlemesi pratik olmadığından, insan dostu alan adlarını (örn. www.atauni.edu.tr) makine diline çeviren bir sisteme ihtiyaç duyulmuştur. DNS, bu ihtiyacı karşılayan, bilgisayarları, internet hizmetlerini ve kaynakları hiyerarşik bir yapıda isimlendiren ve dağıtan sistemdir. DNS'in bu "hiyerarşik" yapısı, alan adlarının sondan başa doğru (.tr ->.edu ->.atauni) çözümlenmesini ifade eder ve sınav sorularında tanımlayıcı bir özellik olarak vurgulanır.

### 2.3. Alan Adı Uzantıları (TLD) ve Kullanım Alanları

Web sitelerinin kurumsal kimliğini ve amacını yansıtan Üst Düzey Alan Adları (Top-Level Domains - TLD), sınavda eşleştirme sorularının temelini oluşturur. Bu uzantıların doğru bilinmesi, sadece sınav başarısı için değil, dijital okuryazarlık açısından da kritiktir.

**Tablo 1: Alan Adı Uzantıları (TLD)**

| Uzantı | Resmi Kullanım Alanı | Sınav Bağlamındaki Detaylar ve Yanılgılar |
|--------|---------------------|------------------------------------------|
| .com | Ticari (Commercial) | Genel ve ticari konularda kullanılır. "Ordu kuruluşları" veya sadece "seyahat acenteleri" gibi kısıtlı tanımlar yanlıştır. |
| .edu | Eğitim (Education) | Üniversiteler ve akademik kurumlar tarafından kullanılır. |
| .gov | Hükümet (Government) | Devlet daireleri ve hükümet kurumlarına aittir. |
| .org | Organizasyon (Organization) | Genellikle kar amacı gütmeyen kuruluşlar, dernekler ve vakıflar kullanır. |
| .info | Bilgi (Information) | Bilgi içerikli siteler için tahsis edilmiştir. |
| .net | Ağ (Network) | Ağ altyapı servisleri için çıkmış olsa da genel kullanıma açıktır. |
| .aero | Havacılık (Aeronautics) | Hava endüstrisi ve havacılık firmaları tarafından kullanılır. |
| .mil | Askeri (Military) | Ordu kuruluşları tarafından kullanılır (.com ile karıştırılmamalıdır). |

Sınavlarda özellikle ".com" uzantısının "Ordu kuruluşları tarafından kullanılır" şeklinde yanlış bir önermeyle sunulduğu görülmektedir. Ayrıca, ".gov" uzantısının uluslararası organizasyonlar için değil (onlar.int kullanır), spesifik olarak hükümet kurumları için olduğu bilgisi test edilmektedir.

## 3. Web Tarayıcıları ve Arama Motoru Teknolojileri

Kullanıcıların web üzerindeki deneyimini şekillendiren iki temel yazılım aracı tarayıcılar ve arama motorlarıdır. Bu iki kavramın işlevleri, çalışma mantıkları ve örnekleri, sınavın teknik bilgi gerektiren bölümlerindendir.

### 3.1. Web Tarayıcılarının (Browsers) Anatomisi

Web tarayıcıları, sunuculardan gelen HTML, CSS, JavaScript ve medya dosyalarını işleyerek (rendering) kullanıcının anlayabileceği görsel bir forma dönüştüren istemci tarafı yazılımlarıdır. Sınav analizleri, tarayıcıların görevlerini şu şekilde detaylandırmaktadır:

- **Protokol Desteği**: HTTP/HTTPS protokollerini kullanarak sunucularla iletişim kurarlar.

- **İçerik Görüntüleme**: Metinsel ve görsel ögeleri ekrana basarlar.

- **Veri Yönetimi**: Dosya indirme (download) ve sunucuya dosya yükleme (upload) işlemlerini yönetirler. Ayrıca kullanıcı deneyimini iyileştirmek için sık kullanılanlar listesi ve gezinme geçmişi tutarlar.

- **Platform Bağımsızlığı**: Tarayıcılar sadece masaüstü bilgisayarlarda değil, mobil cihazlar, tabletler ve akıllı televizyonlarda da çalışır. "Sadece bilgisayarlar üzerinde kullanılır" ifadesi, sınavlarda çeldirici yanlış seçenek olarak sunulmaktadır.

**Tarayıcı Örnekleri ve Yanılgılar**: Google Chrome, Mozilla Firefox, Safari, Opera ve Yandex, sınavlarda geçerli tarayıcı örnekleri olarak kabul edilir. Ancak, Microsoft Access bir veritabanı yönetim sistemidir ve tarayıcılar listesine dahil edilemez; bu ayrım sınavlarda net bir şekilde sorgulanmaktadır. Ayrıca, tarayıcıların yerel ağdaki bir bilgisayara IP adresi atamak gibi bir ağ yönetimi görevi bulunmamaktadır.

### 3.2. Arama Motorları: Algoritmalar ve Operatörler

Arama motorları, internetin kaotik bilgi yığınını düzenleyen, "Spider" veya "Bot" adı verilen yazılımlarla web sayfalarını tarayan (crawling), içerikleri indeksleyen ve belirli algoritmalara göre sıralayan sistemlerdir.

**Arama Operatörleri**: Kullanıcıların arama motorlarını daha verimli kullanmasını sağlayan operatörler, sınavın mantık sorularını oluşturur.

- **Kesin Arama**: Birden fazla kelimenin (örneğin "Erzincan ve Erzurum") her ikisinin de sonuçlarda geçmesinin istendiği durumlarda, arama motorlarında genellikle AND mantığı veya + işareti kullanılır. Sınav bağlamında, belirli bir kökten türeyen kelimeleri aramak için * (joker karakter) kullanımı (Örn: Erz* -> Erzincan, Erzurum) sorgulanmıştır. Çift tırnak (" ") kullanımı ise kelime öbeğini tam olarak (exact match) aramak için tercih edilir.

**Altyapı ve Türler**: Bazı arama motorları kendi indekslerini oluştururken, bazıları (Meta-search engines) diğer motorların sonuçlarını derler. Sınav materyalleri, Startpage ve Ixquick arama motorlarının aynı altyapıyı ve tasarımı kullandığını belirtmektedir. Ayrıca, "Arama dizini" (Directory) kavramı, modern algoritmik arama motorlarından farklı olarak, insanların manuel kategorizasyonuna dayanan bir arama motoru türü olarak sınıflandırılır.

## 4. HTML: Yapısal İşaretleme Dili ve Standartlar

Web sayfalarının iskeletini oluşturan HTML (Hyper Text Markup Language), W3C (World Wide Web Consortium) tarafından standartları belirlenen bir işaretleme dilidir; bir programlama dili değildir. Sınavlar, HTML'in sürüm farklılıklarını, belge yapısını ve etiketlerin (tags) doğru söz dizimini mercek altına almaktadır.

### 4.1. HTML Belge Hiyerarşisi ve Söz Dizimi

Standart bir HTML belgesi, tarayıcının sayfayı doğru yorumlaması için belirli bir hiyerarşiyi takip etmek zorundadır. Bu yapı, sınav sorularında kod bloklarının doğruluğunu test eden sorularla ölçülmektedir.

- **<!DOCTYPE html>**: HTML5 standardını belirten bu bildirim, belgenin ilk satırında yer almalıdır. Görevi, tarayıcıya dokümanın tipini ve hangi HTML sürümüyle yazıldığını bildirmektir.

- **<html>**: Kök elementtir. Sayfanın başlangıcını ve bitişini tanımlar. lang özniteliği (örneğin lang="tr") ile sayfanın doğal dili belirtilir.

- **<head>**: Belgenin "beyni" olarak nitelendirilebilir. Meta veriler, başlık (<title>), stil dosyası bağlantıları (<link>) ve karakter seti tanımları burada bulunur. <head> içindeki veriler (title hariç) sayfanın içerik alanında kullanıcıya gösterilmez.

- **<body>**: Kullanıcının tarayıcı penceresinde gördüğü metin, resim, video ve tabloların tamamı bu etiketin sınırları içindedir.

**Söz Dizimi Kuralları**:

- HTML etiketleri küçüktür (<) işaretiyle başlar ve büyüktür (>) işaretiyle biter (Örn: <body>).

- İç içe geçen etiketlerde LIFO (Last In First Out - Son Giren İlk Çıkar) prensibi geçerlidir. Doğru sıralama <html><head>...</head><body>...</body></html> şeklindedir. Yanlış kapatılan veya sırası karışan etiketler (örneğin head kapanmadan body açılması) sınavlarda hata olarak sorulmaktadır.

- HTML5 ile birlikte etiketlerin büyük/küçük harf duyarlılığı kalmasa da, küçük harf kullanımı standartlaşmıştır.

- Bazı etiketler kapatma etiketi gerektirmez (Void Elements): <img>, <br>, <meta>, <hr>, <input>. Ancak <table>, <div>, <a> gibi içerik barındıran etiketler mutlaka kapatılmalıdır.

### 4.2. Meta Veriler ve SEO Stratejileri

Web sayfalarının arama motorları ve tarayıcılar tarafından nasıl algılandığını belirleyen <meta> etiketleri, sınavın en teknik konularından biridir. Bu etiketler <head> bölümünde yer alır ve sayfa içeriğinde görüntülenmezler.

**Tablo 2: Önemli Meta Etiketleri**

| Meta Özelliği | İşlev ve Sınav Detayı |
|---------------|----------------------|
| Charset | Karakter kodlamasını belirler. Türkçe karakter sorunlarını (ş, ğ, ü) önlemek için HTML5'te <meta charset="utf-8"> formatı kullanılır. |
| Description | Sayfa içeriğinin kısa bir özetidir. Arama motoru sonuç sayfalarında (SERP) başlığın altında görünür. SEO için kritiktir ve önerilen maksimum uzunluk 160 karakterdir. |
| Robots | Arama motoru botlarına talimat verir. follow değeri, botun sayfadaki linkleri takip etmesini sağlar; index değeri sayfanın dizine eklenmesini sağlar. |
| Refresh | Sayfanın belirli bir süre sonra otomatik olarak yenilenmesini veya başka bir URL'e yönlendirilmesini sağlar. Kullanıcı deneyimi açısından dikkatli kullanılmalıdır. |
| Viewport | Mobil uyumluluk için sayfanın görüntüleme alanını cihaz genişliğine göre ayarlar. Sınavlarda "Görüş alanı" olarak da geçer. |

Sınav soruları, özellikle Türkçe karakter problemleri yaşandığında <head> arasına hangi kodun ekleneceğini sormaktadır; cevap meta charset tanımlamasıdır. Ayrıca, meta etiketinin "küresel alanda Meta Tag olarak isimlendirildiği" ve "basit HTML kodlarından biri olduğu" bilgisi doğru kabul edilirken, "web sayfası ekranında görülür" ifadesi yanlıştır.

### 4.3. Metin Biçimlendirme: Semantik ve Sunumsal Yaklaşımlar

HTML'in evrimi sürecinde, metin biçimlendirme etiketleri "sunumsal" (görünümü değiştiren) ve "semantik" (anlam katan) olarak ikiye ayrılmıştır. Sınav, bu geçiş dönemindeki hem eski (deprecated) hem de yeni etiketleri kapsamaktadır.

**Vurgu ve Stil Etiketleri**:

- **Kalınlık**: <b> etiketi metni görsel olarak kalınlaştırır. Sınavda "ATA-AÖF yazısının koyu (bold) yazılmasını sağlayan etiket" sorusuna cevap olarak <b> verilmiştir. Modern standartlarda <strong> etiketi anlamsal önem belirtir, ancak sınav bağlamında <b> halen geçerlidir.

- **Eğiklik**: <i> etiketi metni italik yapar. <em> (emphasis) ise vurgu belirtir. Sınav soruları <i> etiketini doğrudan italik yazı için işaret etmektedir.

- **Altı Çizili**: <u> etiketi metnin altını çizer.

- **Vurgulama**: <mark> etiketi, metni fosforlu kalemle çizilmiş gibi (genellikle sarı arka plan) vurgulamak için kullanılır. "Önemli yerleri daha dikkat çekici hale getirmek" tanımı bu etikete aittir.

**Boyutlandırma**:

- **<small>**: Metni normal akıştan daha küçük yazar.
- **<big>**: Metni normalden daha büyük yazar (HTML5'te desteklenmese de sınav müfredatında yer almaktadır).
- **<sup> (Üst simge) ve <sub> (Alt simge)**: Matematiksel veya kimyasal formüller için kullanılır.

**Eski Tip (Deprecated) <font> Etiketi**: Modern web tasarımında CSS'e bırakılan görevler, eski HTML sürümlerinde <font> etiketi ile yapılırdı. Sınav, bu etiketin parametrelerini detaylıca sormaktadır:

- **face**: Yazı tipini belirler (Örn: <font face="Verdana">).
- **size**: Yazı boyutunu belirler (1-7 arası değer alır).
- **color**: Yazı rengini belirler. Renkler İngilizce isimlerle (blue, red) veya 6 haneli Hexadecimal kodlarla (#FF0000) verilebilir. Hexadecimal sistemde 16'lık sayı tabanı kullanılır.

**Önemli Uyarı**: <font> etiketi weight veya bold gibi bir parametre almaz; kalınlık için <b> etiketi ile sarmalanmalıdır.

### 4.4. Listeler ve Tabloların Yapısal Analizi

Verilerin düzenli gösterimi için kullanılan listeler ve tablolar, parametreleri ile birlikte sınavın vazgeçilmez konularındandır.

**Listeler**:

- **Sıralı Listeler (<ol>)**: Maddelerin başına otomatik olarak numara (1, 2, 3) veya harf (A, B, C) ekler.
- **Sırasız Listeler (<ul>)**: Maddelerin başına madde imi (bullet points - yuvarlak, kare) ekler.
- **Liste Elemanı (<li>)**: Her iki liste türünde de her bir maddeyi tanımlamak için kullanılır. Sınavda <ul> ve <ol> etiketlerinin ortak özelliği olarak sorulmaktadır.

**Tablolar (<table>)**: Tablo oluşturma süreci, satır (<tr>) ve sütun/hücre (<td>) mantığına dayanır.

- **Hücre Birleştirme**:
  - **rowspan**: Aynı sütundaki hücreleri dikey olarak birleştirir. Birleştirilen hücre sayısı kadar alttaki satırlardan hücre silinmesi gerekir.
  - **colspan**: Aynı satırdaki hücreleri yatay olarak birleştirir.

- **Tablo Parametreleri (Eski HTML)**:
  - **width**: Tablo veya hücre genişliğini piksel ya da yüzde (%) cinsinden belirler.
  - **border**: Çerçeve kalınlığını ayarlar.
  - **cellpadding**: Hücre içindeki metin ile hücre kenarı arasındaki boşluğu (iç marj) belirler.
  - **cellspacing**: Hücrelerin birbirleri arasındaki boşluğu (dış marj) belirler.
  - **rules**: Tablo ızgara çizgilerini yönetir. cols değeri sadece dikey çizgileri gösterirken, none değeri iç çizgileri tamamen kaldırır.
  - **valign**: Hücre içi dikey hizalamayı (top, middle, bottom) sağlar. ColTop gibi uydurma değerler sınavda yanlış seçenek olarak sunulur.

- **Semantik Gruplama**: Tablolar <thead> (başlık), <tbody> (gövde) ve <tfoot> (alt bilgi) etiketleri ile bölümlere ayrılarak daha anlamlı ve yönetilebilir hale getirilir.

### 4.5. Hiperlinkler ve Özel Karakterler

Web'in birbirine bağlı yapısını sağlayan bağlantılar (<a> - Anchor) ve klavyede bulunmayan karakterlerin yazımı (Entities) teknik detaylar içerir.

**Bağlantı (<a>) Özellikleri**:

- **href**: Hedef adresi (URL) belirtir.
- **target**: Bağlantının açılma davranışını kontrol eder.
  - **_blank**: Bağlantıyı yeni bir pencerede veya sekmede açar.
  - **_self**: Bağlantıyı aynı pencerede açar (varsayılan davranıştır).
  - **_top ve _parent**: Çerçeve (frame) yapılarında üst katmanlara çıkışı sağlar.

Sınavda _include diye bir target değerinin olmadığı sorulmuştur.

- **E-posta Linki**: mailto: protokolü ile tanımlanır (Örn: <a href="mailto:aof@atauni.edu.tr">).
- **Çapa (Anchor)**: Sayfa içinde belirli bir noktaya gitmek için href="#bolumAdi" şeklinde kullanılır.

**HTML Özel Karakterleri (Entities)**: HTML kodlamasında rezerve edilmiş karakterleri ekranda göstermek için ampersand (&) ile başlayan kodlar kullanılır.

- **&nbsp;**: Boşluk (Non-breaking space) ekler.
- **&quot;**: Çift tırnak (") işareti.
- **&lt; ve &gt;**: Küçüktür (<) ve Büyüktür (>) işaretleri.
- **&amp;**: Ve (&) işareti.

## 5. HTML5 Devrimi: Semantik Web ve API Entegrasyonu

HTML5, web tasarımında bir paradigma değişimi yaratarak, web sayfalarını basit dokümanlardan zengin uygulamalara dönüştürmüştür. Bu sürüm, yapısal anlamı güçlendiren etiketler ve tarayıcı tabanlı API'ler ile sınavın modern yüzünü temsil eder.

### 5.1. Semantik Etiketler ve Sayfa Düzeni

HTML5, <div> karmaşasına son vererek, içeriğin ne olduğunu isminden belli eden etiketler sunmuştur. Sınavda bu etiketlerin tanımları eşleştirme soruları olarak karşımıza çıkar.

**Tablo 3: HTML5 Semantik Etiketleri**

| Etiket | Görev ve Tanım | Önemli Notlar ve Yanılgılar |
|--------|---------------|---------------------------|
| <header> | Sayfanın veya bir bölümün üst kısmını (logo, başlık, menü) tanımlar. | <head> ile karıştırılmamalıdır; <header> görünür kısımdır. |
| <footer> | Sayfanın en alt bölümünü (telif, iletişim, hızlı linkler) belirtir. | |
| <nav> | Navigasyon (menü) linklerini kapsar. | |
| <article> | Kendi başına anlamlı, bağımsız içeriği (blog yazısı, haber, makale) belirtir. | <section>dan farkı, başka bir sayfaya taşındığında da anlamını korumasıdır. |
| <aside> | Ana içerikle ilişkili yan içeriği (kenar çubuğu, yazar bilgisi) belirtir. | Blog yazısının sağ kısmına anahtar kelime veya yazar eklemek için idealdir. |
| <section> | Belge içindeki tematik bölümleri ayırır. | Genel bir kapsayıcıdır. |
| <progress> | Bir işlemin ilerleme durumunu gösteren grafiksel çubuktur. | |

### 5.2. HTML5 Medya ve Grafik Yetenekleri

Harici eklentilere (Adobe Flash, Silverlight) olan ihtiyacı bitiren HTML5, medya oynatımını standartlaştırmıştır.

- **<audio> ve <video>**: Ses ve video dosyalarını doğrudan tarayıcıda oynatır. Sınavda <video> etiketi için yanlış bir tanım olarak "Sayfalar içinde içerik kısmını ayırmayı sağlar" ifadesi verilmiştir; bu <div> veya <section>ın görevidir.

- **<canvas>**: JavaScript kullanılarak "anlık" (on the fly) grafik çizimi, animasyon ve oyun geliştirmek için kullanılan bir tuvaldir. Sınavlarda "Sayfaya basit çizimler eklemek" veya "Grafik çizmek" tanımlarıyla sorulur.

- **Canvas API arc() Metodu**: Tuval üzerinde çember veya yay çizmek için arc(x, y, r, baslangicAcisi, bitisAcisi) metodu kullanılır.

### 5.3. HTML5 API'leri ve Gelişmiş Özellikler

HTML5 ile gelen JavaScript tabanlı API'ler, web sayfalarına masaüstü uygulaması yetenekleri kazandırmıştır.

- **Geolocation API**: Kullanıcının coğrafi konumunu (enlem-boylam) tespit eder. Sınavda "API performansını ölçmek için bir araç" olduğu iddia edilerek yanlış seçenek olarak sunulmuştur; Geolocation bir test aracı değil, bir web servisidir. Google Maps gibi uygulamalarla entegre çalışır.

- **Drag and Drop (Sürükle-Bırak) API**: Sayfa içi öğelerin taşınmasını sağlar. Bir nesnenin sürüklenebilmesi için HTML etiketine draggable="true" özelliği eklenmeli, JavaScript tarafında ise ondragover (sürükleme esnası) ve ondrop (bırakma anı) olayları yönetilmelidir.

- **Web Storage**: Çerezlere (cookies) alternatif olarak, verilerin istemci tarayıcısında daha güvenli ve yüksek kapasiteli saklanmasını sağlayan localStorage ve sessionStorage yapılarıdır.

## 6. CSS (Cascading Style Sheets): Görsel Tasarımın Dili

HTML'in oluşturduğu iskelete "deri ve kıyafet" giydiren teknoloji CSS'tir. Sınav materyalleri, CSS'in bir programlama dili olmadığını, bir stil şablonu teknolojisi olduğunu vurgular.

### 6.1. Seçiciler ve Özellikler

CSS kuralları, HTML elementlerini hedefleyen "seçiciler" (selectors) ve onlara uygulanan "özellikler" (properties) üzerine kuruludur.

**Seçici Türleri**:

- **ID Seçicisi**: Sayfada sadece bir kez kullanılan benzersiz öğeleri seçer. # işareti ile başlar (Örn: #logo).

- **Sınıf (Class) Seçicisi**: Birden fazla öğeye uygulanabilen stilleri tanımlar. . işareti ile başlar (Örn: .kutu).

- **Sözde Sınıflar (Pseudo-classes)**: Bir elementin özel durumunu (tıklanma, üzerine gelme) belirtir. : işareti ile başlar. Sınavda "Sınıf olmayan fakat sınıf gibi davranış gösteren seçiciler" olarak tanımlanır (Örn: :hover, :active).

**Metin ve Dekorasyon Özellikleri**:

- **text-decoration**: Metin üzerindeki çizgileri yönetir. underline (altı çizili), overline (üstü çizili), line-through (üzeri çizili) değerlerini alır. Sınavlarda "İçeriğin (metnin) altına, üstüne veya üzerine çizgi çekmeyi belirten özellik" olarak tanımlanır.

- **text-align**: Metni hizalar (sağ, sol, orta, iki yana yasla).

**Boyutlandırma ve Düzen (Layout)**:

- **min-height**: İçerik az olsa bile bir elementin kaplayacağı minimum yüksekliği belirler.

- **column-gap**: Çok sütunlu metin düzenlerinde (Multi-column layout) veya Grid/Flex yapılarında sütunlar arasındaki boşluğu (gutter) ayarlar.

### 6.2. CSS Animasyonları

Statik web sayfalarını hareketlendiren CSS3 animasyonları, sınavın modern CSS konularındandır.

- **@keyframes**: Animasyonun senaryosunu yazar. Animasyon süresince (0% ile 100% arasında) hangi CSS özelliklerinin değişeceğini belirten kural setidir.

- **Performans Avantajı**: Sınavda CSS animasyonlarının "fazladan komut dosyaları gerektirdiği için sayfayı yavaşlattığı" iddiası yanlış seçenek olarak sunulmuştur. Aksine, CSS animasyonları JavaScript veya GIF kullanımına göre daha performanslıdır ve tarayıcı tarafından optimize edilir.

### 6.3. CSS Entegrasyonu

CSS kodları HTML'e üç yolla eklenebilir: Satır içi (inline), Sayfa içi (internal) ve Harici (external). Sınav soruları, harici bir .css dosyasını sayfaya bağlamak için <head> bölümünde <link> etiketinin kullanılması gerektiğini belirtir.

```html
<link rel="stylesheet" type="text/css" href="stil.css">
```

## 7. Web Programlama ve JavaScript Ekosisteminin Tarihçesi

Web'in etkileşim katmanını oluşturan JavaScript (JS), sınavda sadece kod olarak değil, tarihsel gelişimi ve kütüphaneleriyle de ele alınmaktadır.

### 7.1. JavaScript'in Rolü ve Sınırları

JavaScript, web sayfalarında hesaplamalar yapabilen, verileri düzenleyebilen, animasyonları tetikleyen ve sunucu ile asenkron iletişim kurabilen bir betik dilidir. Ancak sınav analizlerinde dikkat çeken bir ayrım şudur: "Görsel tasarımı belirlemek" doğrudan JavaScript'in birincil görevi değildir; bu CSS'in sorumluluğundadır. JS, stilleri manipüle edebilir ancak görsel tasarımın tanımlandığı yer CSS'tir.

### 7.2. Kütüphaneler ve Frameworkler: Tarihsel Bir Bakış

Modern web geliştirmede kullanılan popüler kütüphanelerin kökenleri ve geliştiricileri, sınavın bilgi sorularını oluşturur.

- **Angular**: Google tarafından desteklenen ve modern Tek Sayfa Uygulamaları (SPA) geliştirmeyi sağlayan popüler bir framework'tür. Tarihsel olarak, Misko Hevery tarafından 2008-2009 yıllarında kişisel bir proje olarak başlatılmış, daha sonra Google bünyesine katılmıştır. Sınavda bu isim ve tarih eşleştirmesi kritik önem taşır.

- **jQuery**: 2006 yılında John Resig tarafından geliştirilen, "Write Less, Do More" (Az Yaz, Çok İş Yap) felsefesiyle DOM manipülasyonunu ve tarayıcı uyumluluğunu basitleştiren efsanevi kütüphanedir. Günümüzde popülaritesi azalmış olsa da web tarihinin en önemli dönüm noktalarından biridir.

**Geliştirme Ortamları (IDE)**: Kod yazımını kolaylaştıran Entegre Geliştirme Ortamları (IDE) da sorulmaktadır.

- **NetBeans**: Oracle tarafından geliştirilmiş (başlangıçta Sun Microsystems) bir IDE'dir.
- **Visual Studio Code (VS Code)**: Microsoft tarafından geliştirilen, günümüzün en popüler kod editörüdür.

## 8. Web API'leri (Application Programming Interfaces): Tarihçe ve Araçlar

Yazılımların birbirleriyle konuşmasını sağlayan arayüzler olan API'ler, modern web'in belkemiğidir. Sınav müfredatı, API kavramını teknik tanımların ötesinde, tarihsel ilkleri ve test araçlarıyla irdelemektedir.

### 8.1. API Tarihçesi: Ticari İlkler

Web API'lerinin ticarileşme süreci 2000'li yılların başına dayanır. Sınavlarda "API kullanımına ilk izin veren site" sorusu, web tarihinin önemli bir kilometre taşını işaret eder.

- **Salesforce.com**: 7 Şubat 2000 tarihinde, XML tabanlı web API'sini tanıtarak, kurumsal verilerin web üzerinden paylaşımını başlatan ilk firma olmuştur. Bu hamle, "Internet as a Service" (Hizmet Olarak İnternet) kavramının doğuşudur.

- **eBay**: Salesforce'tan kısa bir süre sonra, Kasım 2000'de API programını başlatmıştır.

- **Amazon**: E-ticaret devrimini API ile taçlandırarak Temmuz 2002'de Amazon Web Services (AWS) API'lerini sunmuştur.

### 8.2. API Test Araçları ve Performans

Geliştirilen API'lerin beklenen yanıtları verip vermediğini kontrol etmek için kullanılan araçlar sınavda sorulmaktadır.

- **Postman**: Sektör standardı haline gelmiş, grafik arayüzlü ve kullanıcı dostu en popüler API test aracıdır.

- **Diğer Araçlar**: SoapUI, JMeter, Katalon Studio gibi araçlar da listede yer alır.

**Kavram Yanılgısı**: Sınavda şıklar arasına yerleştirilen Geolocation, bir test aracı değil, bir API türüdür. Benzer şekilde "Canvas" da bir HTML5 elementidir.

API kullanımının avantajları arasında entegrasyon kolaylığı, projeye değer katma ve yazılımcının işini hızlandırma sayılırken; "projelerin başarılı olma olasılığını düşürür" ifadesi kesinlikle yanlıştır.

## 9. Web Tasarım Süreçleri ve Roller

Bir web projesinin hayata geçirilmesi, farklı disiplinlerin ve rollerin işbirliğini gerektirir. Sınav, bu rolleri ve tasarımın proje üzerindeki etkilerini sorgular.

### 9.1. Front-end vs Back-end Ayrımı

- **Front-end (Ön Yüz) Geliştirici**: Kullanıcının tarayıcıda gördüğü arayüzü kodlar. HTML, CSS, JavaScript kullanır. Kullanıcı memnuniyeti ve arayüz tasarımı ile ilgilenir. Ancak, sınavda vurgulandığı üzere "Veri Tabanı İşlemleri" front-end geliştiricinin değil, back-end geliştiricinin sorumluluk alanındadır.

- **UX (User Experience - Kullanıcı Deneyimi)**: Kullanıcının siteyi kullanırken hissettiği kolaylık ve akıcılıkla ilgilenir. Görsel tasarımdan ziyade "etkileşime ve fonksiyonelliğe" odaklanır.

### 9.2. Tasarımın Proje Üzerindeki Etkileri

İyi bir web tasarımı sadece estetik değildir; projenin başarısını doğrudan etkileyen teknik bir süreçtir. Sınav sorularına göre tasarım süreci:

- Kullanıcı deneyimini (UX) ve memnuniyetini etkiler.
- Front-end tarafında kullanılacak bileşenlerin seçimini belirler.
- Projenin kapsamını ve amacını şekillendirir.
- **Sistem Performansını Etkiler**: Gereksiz büyük görseller veya kötü kodlanmış CSS animasyonları sistemi yavaşlatabilir. Bu nedenle sınavda "Tasarım süreci sistem performansını etkilemez" ifadesi yanlış kabul edilmiştir.

## 10. Sonuç ve Sınav Başarı Stratejisi

Web teknolojileri sınavları, hem teorik bilgi hem de pratik uygulama yeteneğini ölçmektedir. Yüksek puan almak isteyen bir öğrenci, aşağıdaki stratejik noktaları içselleştirmelidir:

- **Kavramsal Netlik**: İnternet ile WWW arasındaki farkı, HTML ile programlama dili arasındaki ayrımı, Front-end ile Back-end sorumluluklarını net bir şekilde bilmek gereklidir.

- **Söz Dizimi Hakimiyeti**: HTML etiketlerinin doğru kapatılması, CSS seçicilerinin doğru yazılması ve JavaScript söz dizimi kuralları kritik öneme sahiptir.

- **Tarihsel Bilgi**: API'lerin ticarileşme tarihleri, framework geliştiricileri ve teknolojik dönüm noktaları sınavda belirleyicidir.

- **Kategorik Düşünme**: Etiketleri (Semantik/Sunumsal), API'leri (Test Aracı/API Türü), Rolleri (Front-end/Back-end) kategorize ederek çalışmak, olumsuz köklü soruları çözmeyi kolaylaştırır.

Bu rapor, web teknolojileri sınavlarına hazırlık için gerekli tüm temel bilgileri kapsamaktadır. Buradaki bilgilerin özümsenmesi, sadece sınav başarısı için değil, modern web geliştirme yetkinliklerinin kazanılması adına da yeterli olacaktır.

