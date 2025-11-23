# İleri Düzey Web Yapılandırması: HTML Form Mimarisi, Tablolar, Semantik Tasarım ve Evrensel Erişilebilirlik Standartları

## 1. Yönetici Özeti ve Giriş
Web teknolojilerinin evrimi, bilginin statik sunumundan kullanıcı ile karşılıklı etkileşimin esas olduğu dinamik ekosistemlere doğru radikal bir dönüşüm geçirmiştir. Bu dönüşümün merkezinde, webin yapısal iskeletini oluşturan HTML (HyperText Markup Language) yer almaktadır.

Günümüzde modern bir web arayüzü tasarımı, yalnızca görsel estetik kaygılardan ibaret olmayıp; verinin güvenli ve doğru biçimde toplanması (formlar), karmaşık veri setlerinin anlaşılabilir sunumu (tablolar), içeriğin hem makineler hem de insanlar tarafından anlamlandırılabilmesi (semantik yapı) ve her türlü fiziksel veya bilişsel yetiye sahip birey için kapsayıcılık (erişilebilirlik) gibi çok boyutlu disiplinleri barındırmaktadır.

Bu rapor, W3C (World Wide Web Consortium), MDN (Mozilla Developer Network) gibi uluslararası otoritelerin belirlediği güncel standartlar ışığında hazırlanmıştır. Raporun temel amacı, kullanıcı etkileşiminin temel yapı taşları olan formların teknik anatomisini ve güvenlik boyutlarını, veri gösterim aracı olan tabloların modern kullanım senaryolarını, HTML5 ile gelen semantik etiketlerin SEO ve erişilebilirlik üzerindeki stratejik etkisini derinlemesine analiz etmektir.

## 2. Web Ortamında Kullanıcı Verisi Toplama ve Form Mimarisi
Web sayfalarının tek yönlü bilgi aktarımından çift yönlü iletişime geçişi, "Form" yapıları sayesinde mümkün olmuştur. Formlar, istemci (kullanıcı tarayıcısı) ile sunucu (backend) arasındaki veri köprüsünü kuran, kullanıcı girdilerini işlenebilir veri paketlerine dönüştüren kritik arayüz elemanlarıdır.

### 2.1. Form Etiketinin Yapısal Anatomisi ve Veri İletim Protokolleri
HTML içerisinde bir veri toplama alanı oluşturmak `<form>` etiketi ile başlar. Bu etiket, görsel bir çerçeveden ziyade, verinin "nereye", "nasıl" ve "hangi formatta" taşınacağını belirleyen bir kontrol merkezidir.

#### 2.1.1. Action (Hedef ve Yönlendirme)
`action` özniteliği, kullanıcı tarafından girilen verilerin işlenmek üzere gönderileceği sunucu tarafı kaynağının URL adresini belirtir. Bu, bir PHP dosyası, bir ASP.NET sayfası veya modern web uygulamalarında bir API uç noktası (endpoint) olabilir.

Eğer `action` alanı boş bırakılırsa (`action=""`), form veriyi bulunduğu sayfanın kendisine (self-submission) gönderir. Bu durum, özellikle sunucu taraflı doğrulama hatalarının aynı sayfada kullanıcıya gösterilmesi gereken senaryolarda tercih edilir.

#### 2.1.2. Method (Veri Transfer Yöntemi)
Verilerin sunucuya transfer edilirken kullanılacak HTTP metodunu tanımlar. Bu seçim, uygulamanın güvenliği, performansı ve önbellekleme davranışlarını doğrudan etkiler:

**GET Yöntemi:**
- Verileri URL adres çubuğuna ekleyerek (`example.com/search?q=veri`) gönderir.
- Bu yöntem "idempotent" (tekrarlanabilir) işlemler için tasarlanmıştır.
- **Kullanım Alanları:** Arama motoru sorguları, filtreleme işlemleri.
- **Riskler:** Veriler URL'de açıkça görüldüğü için şifre, kredi kartı bilgisi veya kişisel verilerin (PII) taşınmasında asla kullanılmamalıdır. URL geçmişi ve sunucu loglarında bu veriler açık metin olarak saklanır.
- **Sınırlılıklar:** URL uzunluk sınırına (genellikle 2048 karakter) tabidir.

**POST Yöntemi:**
- Verileri HTTP isteğinin gövdesinde (request body) paketleyerek gönderir. URL üzerinde görünmezler.
- **Kullanım Alanları:** Kullanıcı kayıtları, giriş işlemleri, veritabanı güncellemeleri ve dosya yüklemeleri.
- **Avantajlar:** Veri boyutu sınırı yoktur ve ASCII dışı karakterleri veya ikili (binary) verileri sorunsuz taşır.

#### 2.1.3. Veri Kodlama Türleri (Enctype)
Form verilerinin sunucuya gönderilmeden önce nasıl kodlanacağını belirler. Varsayılan değer olan `application/x-www-form-urlencoded`, karakterleri URL uyumlu hale getirir.

Bir dosya (görsel, PDF vb.) sunucuya iletilecekse, form etiketine `enctype="multipart/form-data"` özelliği eklenmelidir. Bu, veriyi parçalara ayırarak hem metin hem de ikili dosya verisinin aynı anda iletilmesine olanak tanır.

### 2.2. Girdi Alanları (Input Types) ve Kullanıcı Deneyimi (UX) Optimizasyonu
Kullanıcıdan veri almak için kullanılan en temel element `<input>` etiketidir. HTML5 devrimi ile birlikte bu etiket, sadece basit bir metin kutusu olmaktan çıkmış, verinin türüne göre şekil alan, doğrulama yapabilen ve mobil cihazlarda sanal klavye düzenini değiştiren akıllı bir bileşene dönüşmüştür.

**Tablo 1: Temel ve İleri Düzey Giriş Türleri**

| Girdi Türü (Type) | Teknik İşlev ve Özellikler | Kullanıcı Deneyimi ve Erişilebilirlik Etkisi |
|-------------------|----------------------------|----------------------------------------------|
| `text` | Standart tek satırlık alfanümerik veri girişi. Varsayılan input türüdür. | İsim, soyisim, adres başlığı gibi genel veriler için kullanılır. |
| `password` | Girilen karakterleri maskeler (genellikle nokta veya yıldız sembolü ile). | Güvenlik sağlar. Modern tarayıcılarda entegre "şifreyi göster" butonu ile kullanılabilirliği artırılabilir. |
| `email` | E-posta formatı doğrulaması yapar (@ işareti ve alan adı kontrolü). | Mobil cihazlarda sanal klavyede @ ve .com tuşlarını öne çıkararak yazımı kolaylaştırır. |
| `number` | Sadece sayısal giriş kabul eder. `min`, `max`, `step` özellikleri ile sınırlandırılabilir. | Mobil cihazlarda sayısal tuş takımını (numpad) açar. `step` özelliği ile ondalık artışlar yönetilebilir. |
| `tel` | Telefon numaraları için semantik yapı sunar. Otomatik formatlama yapmaz ancak mobil klavyeyi tetikler. | Sayısal tuş takımını açar. Ekran okuyuculara verinin telefon numarası olduğunu bildirir. |
| `url` | Web adresi girişi için doğrulamalı alan sağlar. Protokol (http://) kontrolü yapar. | Mobil klavyede /, ., .com gibi URL spesifik karakterleri erişilebilir kılar. |
| `date` | Tarayıcının yerel tarih seçicisini (date picker) açar. | Kullanıcının format hatası yapmasını engeller. Takvim arayüzü sunar. |
| `radio` | Bir seçenek grubundan (name özelliği aynı olanlar) sadece birinin seçilmesine izin verir. | Karşılıklı dışlayıcı seçenekler (örn. Cinsiyet, Ödeme Tipi) için kullanılır. |
| `checkbox` | Birden fazla seçeneğin bağımsız olarak işaretlenmesine olanak tanır. | Kullanıcı sözleşmeleri, hobi seçimleri gibi çoklu onay gerektiren durumlar için idealdir. |
| `file` | Yerel depolama biriminden dosya seçilmesini sağlar. `accept` ile dosya türü kısıtlanabilir. | `multiple` özelliği ile çoklu dosya seçimine izin verilebilir. `enctype="multipart/form-data"` gerektirir. |
| `hidden` | Kullanıcıya görünmeyen ancak formla birlikte gönderilmesi gereken verileri (token, ID) tutar. | Oturum güvenliği (CSRF token) ve durum takibi için kritik öneme sahiptir. |

### 2.3. Form Doğrulama (Validation): Veri Bütünlüğü ve Kullanıcı Rehberliği
Veri kalitesinin sağlanması, veritabanı bütünlüğünün korunması ve hatalı girişlerin sunucu kaynaklarını tüketmeden engellenmesi için "Form Doğrulama" mekanizmaları kullanılır. Doğrulama işlemi modern web mimarisinde iki katmanda gerçekleşir: İstemci Taraflı (Client-Side) ve Sunucu Taraflı (Server-Side).

#### 2.3.1. HTML5 ile Yerleşik (Built-in) İstemci Taraflı Doğrulama
HTML5, karmaşık JavaScript kodlarına ihtiyaç duymadan, tarayıcının kendi motorunu kullanarak güçlü doğrulama özellikleri sunmaktadır.

**Required (Zorunlu Alan):** Bir alanın boş bırakılmasını engeller. Tarayıcı, "Lütfen bu alanı doldurun" şeklinde yerelleştirilmiş bir hata balonu gösterir.

**Pattern (Düzenli İfadeler - Regex):** Doğrulamanın en güçlü aracıdır. Girilen verinin belirli bir matematiksel desene uymasını zorunlu kılar.

- **Örnek:** Sadece harflerden oluşan 3-16 karakterlik bir kullanıcı adı için `pattern="\w{3,16}"` kullanılabilir.
- **Örnek:** 4 haneli bir PIN kodu için `pattern="\d{4,4}"` kullanılır.
- **İpucu:** Bir pattern kullanıldığında, kullanıcıya beklenen formatı açıklayan açıklayıcı bir `title` özelliği eklemek erişilebilirlik açısından en iyi uygulamadır.

**Uzunluk ve Değer Kısıtlamaları:**
- `minlength` ve `maxlength`: Metinsel veriler için karakter sınırlarını belirler (örn. şifre en az 6 karakter).
- `min` ve `max`: Sayısal girdiler ve tarihler için alt ve üst limitleri belirler.
- `step`: Sayısal artış miktarını belirler (örn. `step="0.5"` ondalık sayı girişine izin verir).

#### 2.3.2. Doğrulama için En İyi Uygulamalar (Best Practices)
2025 yılı web standartları ve kullanıcı deneyimi araştırmaları, form doğrulamasında aşağıdaki yaklaşımları önermektedir:

- **"On Blur" Doğrulama:** Kullanıcı yazarken (keypress) anlık hata göstermek yerine, kullanıcı alandan çıktığında (blur) veya formu gönderdiğinde doğrulama yapmak, kullanıcının dikkatini dağıtmamak adına daha doğrudur.

- **Anlamlı Hata Mesajları:** "Geçersiz Giriş" gibi jenerik mesajlar yerine, "Şifreniz en az bir büyük harf içermelidir" gibi aksiyona yönlendiren mesajlar kullanılmalıdır.

- **Görsel ve Metinsel Geri Bildirim:** Hata durumunu sadece kırmızı çerçeve (renk) ile belirtmek, renk körü kullanıcılar için erişilebilirlik sorunu yaratır. Renkle birlikte ikon ve metin tabanlı uyarılar da kullanılmalıdır.

**Kritik Güvenlik Uyarısı:** İstemci taraflı doğrulama (HTML5/JavaScript), yalnızca kullanıcı deneyimini iyileştirmek (hızlı geri bildirim) içindir. Kötü niyetli kullanıcılar, tarayıcı araçlarını kullanarak veya doğrudan API istekleri göndererek bu kontrolleri kolayca atlatabilir. Bu nedenle, tüm veri doğrulamaları, sanitizasyon (temizleme) ve güvenlik kontrolleri mutlaka sunucu tarafında (Backend) tekrarlanmalıdır.

### 2.4. İleri Düzey Form Yapıları ve Gruplama
Karmaşık formlarda, ilgili verileri mantıksal gruplara ayırmak hem görsel düzeni sağlar hem de ekran okuyucu kullanıcıları için bağlam oluşturur.

**Fieldset ve Legend:** Form elemanlarını gruplamak için `<fieldset>` etiketi kullanılır. Bu grubun başlığı ise `<legend>` etiketi ile tanımlanır.

**Örnek:** Bir e-ticaret ödeme sayfasında "Kişisel Bilgiler" ve "Kredi Kartı Bilgileri" iki ayrı fieldset içinde toplanabilir. Ekran okuyucular, kullanıcı bu alanlara girdiğinde grup başlığını (legend) okuyarak bağlamı hatırlatır.

## 3. HTML Tabloları ile Yapısal Veri Sunumu ve Modern Yaklaşımlar
Webin ilk yıllarında sayfa mizanpajı (layout) oluşturmak için kullanılan tablolar, CSS'in yükselişi ve kutu modelinin gelişimiyle birlikte bu işlevini tamamen yitirmiştir. Modern web tasarımında tablolar, yalnızca anlamsal olarak "tablo niteliği taşıyan" (satır ve sütun ilişkisi olan) çok boyutlu verilerin sunumu için kullanılmalıdır.

Fiyat listeleri, ders programları, finansal bilanço raporları, spor istatistikleri ve karşılaştırma matrisleri bu kapsama giren doğru kullanım örnekleridir.

### 3.1. Tablo Anatomisi ve Semantik Bölümlendirme
Bir HTML tablosu `<table>` etiketi ile başlar. Ancak tabloyu erişilebilir, taranabilir ve yönetilebilir kılan, içindeki hiyerarşik etiketlerin doğru kullanımıdır:

**Temel Hücreler:**
- `<tr>` (Table Row): Tablodaki her bir satırı tanımlar.
- `<th>` (Table Header): Başlık hücresini tanımlar. Görsel olarak genellikle kalın ve ortalanmış olsa da, asıl işlevi semantiktir. Ekran okuyucular bu etiketi algılayarak, altındaki veri hücrelerini okurken "Başlık: Veri" şeklinde ilişki kurar.
- `<td>` (Table Data): Standart veri hücresidir.

**Semantik Gruplama:**
Uzun ve karmaşık tablolarda, tarayıcıların yazdırma davranışlarını yönetmek ve arama motorlarına yapıyı anlatmak için tablo üç ana bölüme ayrılmalıdır:

- `<thead>`: Sütun başlıklarını içeren, tablonun "kafa" kısmıdır. CSS ile sabit başlık (sticky header) yaparken bu bölüm hedeflenir.
- `<tbody>`: Asıl verilerin bulunduğu, tablonun "gövde" kısmıdır. Bir tabloda birden fazla tbody kullanılabilir.
- `<tfoot>`: Toplamlar, özetler veya dipnotların yer aldığı "ayak" kısmıdır. Semantik olarak, veriler değişse bile bu bölümün bir sonuç bildirdiği ifade edilir.

### 3.2. Hücre Birleştirme ve Karmaşık Veri Yapıları
Gerçek dünyadaki veriler her zaman basit ızgara yapısına uymaz. Bazı durumlarda bir başlığın birden fazla sütunu kapsaması veya bir hücrenin dikeyde birleşmesi gerekir.

- **Colspan (Column Span):** Bir hücrenin yatayda kaç sütun genişliğinde olacağını belirler. `colspan="2"` ifadesi hücreyi iki birim genişletir.
- **Rowspan (Row Span):** Bir hücrenin dikeyde kaç satır boyunca uzanacağını belirler.

**Erişilebilirlik Uyarısı:** Hücre birleştirme işlemleri görsel düzeni sağlasa da, ekran okuyucular için tablonun karmaşıklığını artırabilir ve navigasyonu zorlaştırabilir. Bu tür karmaşık tablolarda `scope` özniteliği ("row", "col", "rowgroup", "colgroup") kullanılarak başlıkların etki yönü açıkça belirtilmelidir.

### 3.3. Kullanımdan Kaldırılan (Deprecated) Özellikler ve Modern Alternatifler
HTML5 standardı, sunum (görsellik) ile yapı (semantik) arasındaki ayrımı kesinleştirmiştir. Bu bağlamda, tablolara görsel şekil vermek için kullanılan eski özellikler kullanımdan kaldırılmıştır.

**Tablo 2: Kullanımdan Kaldırılan Özellikler ve Modern Alternatifler**

| Eski Özellik (Obsolete) | Durum | Modern Alternatif (Doğru Kullanım) |
|------------------------|-------|-----------------------------------|
| `border`, `cellpadding` | Kaldırıldı | CSS `border`, `padding` özellikleri kullanılmalıdır. |
| `align`, `bgcolor` | Kaldırıldı | CSS `text-align`, `background-color` özellikleri kullanılmalıdır. |
| `summary` | Kaldırıldı | Tablonun içeriğini özetlemek için eskiden kullanılan bu özellik artık desteklenmemektedir. Yerine `<caption>` etiketi veya tabloyu `<figure>` içine alıp `<figcaption>` ile açıklama ekleme yöntemi kullanılmalıdır. |

## 4. Semantik HTML5 ve Anlamsal Web Mimarisi
Web 2.0 döneminden sonra, arama motorlarının ve yapay zeka tabanlı sistemlerin içeriği "anlaması" kritik bir ihtiyaç haline gelmiştir. "Div çorbası" (div soup) olarak adlandırılan, tüm yapının anlamsız `<div>` ve `<span>` etiketleri ile kurulduğu eski yöntem, yerini Semantik (Anlamsal) HTML yaklaşımına bırakmıştır.

Semantik HTML, bir içeriğin sadece ekranda nasıl göründüğünü değil, o içeriğin ne "anlama" geldiğini, doküman içindeki rolünü ve önem derecesini tarayıcıya ve makinelere bildirir.

### 4.1. Sayfa İskeleti ve Semantik Etiketlerin Rolleri
HTML5 ile gelen yeni etiketler, bir web dokümanının mantıksal bölümlerini standartlaştırır.

#### 4.1.1. Yapısal Etiketler
- **<header>:** Sayfanın veya bir bölümün giriş kısmıdır. Genellikle logo, ana başlık, arama çubuğu ve yazar bilgisini içerir. Bir sayfada sadece en üstte değil, her `<article>` veya `<section>` içinde de o bölümün başlığını belirtmek için kullanılabilir.

- **<nav> (Navigation):** Sayfa içi veya site dışı ana gezinme bağlantılarını (menüleri) kapsar. Tüm link grupları için değil, yalnızca ana menü, içindekiler tablosu gibi birincil navigasyon blokları için kullanılmalıdır. Ekran okuyucular bu etiketi gördüğünde, kullanıcının menüyü atlayıp doğrudan içeriğe geçmesine ("skip to content") olanak tanır.

- **<main>:** Sayfanın, diğer sayfalarda tekrar etmeyen, o sayfaya özgü ana içeriğini kapsar. Her sayfada yalnızca bir tane `<main>` etiketi bulunmalıdır ve bu etiket header, nav, footer gibi elementlerin içinde olmamalıdır. Arama motorları için sayfanın en değerli ve indekslenmesi gereken kısmı burasıdır.

- **<footer>:** Sayfanın veya bölümün alt bilgisidir. Telif hakları, iletişim bilgileri, gizlilik politikası linkleri ve site haritası bağlantılarını içerir.

#### 4.1.2. İçerik Bölümleme Etiketleri
- **<section>:** Tematik olarak ilişkili içerik gruplarını belirtir. Genel bir kapsayıcıdır ancak `<div>`den farklı olarak içinde mutlaka bir başlık (h1-h6) bulunması beklenir. Örneğin, bir haber sayfasında "Spor Haberleri", "Ekonomi Haberleri" ayrı birer `<section>` olabilir.

- **<article>:** Kendi başına anlamlı, bağımsız olarak dağıtılabilir veya tekrar kullanılabilir içerikleri tanımlar. Blog yazısı, haber metni, kullanıcı yorumu veya bir forum gönderisi `<article>` ile işaretlenmelidir. Bir `<article>` etiketi, RSS beslemesi ile başka bir sayfaya taşındığında da anlam bütünlüğünü korumalıdır.

**Nesting (İç İçe Kullanım) Kuralı:** Bir `<article>` içinde başlık hiyerarşisi yeniden başlayabilir (H1 kullanılabilir), ancak modern tarayıcılar ve ekran okuyucular için doküman hiyerarşisini korumak (H2, H3 ile devam etmek) daha güvenli bir yaklaşımdır.

- **<aside>:** Ana içerikle dolaylı yoldan ilişkili olan yan içerikleri belirtir. Kenar çubuğu (sidebar), reklamlar, "bunu da okuyun" önerileri veya terim açıklamaları için kullanılır.

### 4.2. SEO ve Geleceğin Arama Deneyimi (SGE) Üzerindeki Etkisi
Semantik etiketlerin kullanımı, Arama Motoru Optimizasyonu (SEO) için doğrudan ve güçlü bir sıralama faktörüdür.

- **Daha İyi İndeksleme:** Arama motoru botları (crawlers), sayfayı tararken `<header>`, `<nav>` ve `<footer>` gibi alanları şablon (boilerplate) olarak işaretleyip, asıl odaklanmaları gereken anahtar kelimeleri `<main>` ve `<article>` blokları içinde ararlar.

- **Zengin Sonuçlar (Rich Snippets):** Semantik yapı, arama motorlarının içeriğin türünü (haber, tarif, etkinlik) anlamasına yardımcı olur.

- **Üretken Arama Deneyimi (SGE):** Geleceğin arama deneyimi olan yapay zeka destekli arama sonuçlarında (Google SGE gibi), yapay zeka modelleri içeriği özetlemek ve kullanıcı sorularına doğrudan cevap vermek için bu semantik ipuçlarına ihtiyaç duyar.

- **Mobil Performans:** Semantik kod, gereksiz div ve class tanımlarını azaltarak dosya boyutunu küçültür ve mobil cihazlarda daha hızlı yüklenen, daha kolay yönetilen (responsive) yapılar oluşturulmasını sağlar.

## 5. Web Erişilebilirliği (Accessibility - a11y) ve Kapsayıcı Tasarım
Erişilebilirlik, webin evrensellik ilkesinin teknik karşılığıdır. Tim Berners-Lee'nin de belirttiği gibi, "Webin gücü evrenselliğindedir. Engelli veya engelsiz herkesin erişimi temel bir unsurdur." Web erişilebilirliği, görme, işitme, motor veya bilişsel engelleri olan bireylerin web sitelerini herkesle eşit düzeyde kullanabilmesini sağlamayı hedefler.

### 5.1. WCAG Standartları ve POUR İlkeleri
Dünya genelinde web erişilebilirliği, W3C (World Wide Web Consortium) tarafından geliştirilen WCAG (Web Content Accessibility Guidelines) standartlarına dayanır. WCAG 2.1 ve 2.2, erişilebilirliğin dört temel sütununu (POUR) tanımlar:

- **Algılanabilir (Perceivable):** Bilgi ve kullanıcı arayüzü bileşenleri, kullanıcıların algılayabileceği şekilde sunulmalıdır. Görmeyenler için metin alternatifleri (ekran okuyucu desteği), işitmeyenler için altyazılar bu kapsama girer.

- **Kullanılabilir (Operable):** Kullanıcı arayüzü bileşenleri ve gezinme kullanılabilir olmalıdır. Fare kullanamayan bireyler için klavye ile gezinme (Tab tuşu ile dolaşım) zorunludur. Yanıp sönen içerikler nöbet tetikleyebileceği için kaçınılmalıdır.

- **Anlaşılabilir (Understandable):** Bilgi ve kullanıcı arayüzünün çalışması anlaşılır olmalıdır. Tutarlı menüler, net hata mesajları ve okunabilir dil kullanımı esastır.

- **Sağlam (Robust):** İçerik, ekran okuyucular gibi yardımcı teknolojiler de dahil olmak üzere çok çeşitli kullanıcı arayüzleri (tarayıcılar, cihazlar) tarafından güvenilir bir şekilde yorumlanabilecek kadar standartlara uygun kodlanmalıdır.

Bu standartlar, A (Minimum), AA (Güçlü Erişilebilirlik - Genellikle Yasal Zorunluluk Seviyesi) ve AAA (En Üst Düzey) olmak üzere üç uyumluluk seviyesine ayrılır.

### 5.2. HTML'de Yerleşik Erişilebilirlik Teknikleri
Erişilebilir bir web sayfası oluşturmak için çoğunlukla ek bir yazılıma gerek yoktur; doğru HTML kullanımı erişilebilirliğin %80'ini sağlar.

#### 5.2.1. Alternatif Metin (Alt Text)
Görseller için kullanılan `alt` özniteliği, görselin içeriğini metinsel olarak açıklar.

- **İşlevi:** Görsel yüklenmediğinde (düşük bant genişliği) veya görme engelli bir kullanıcı ekran okuyucu kullandığında görselin ne anlattığını iletir.
- **Kullanımı:** Eğer görsel bilgi taşıyorsa (örn. bir grafik veya ürün resmi), `alt="Öğrenci istatistiklerini gösteren grafik"` şeklinde açıklama yazılmalıdır. Eğer görsel sadece dekoratifse (süsleme amacı taşıyorsa), `alt=""` (boş) bırakılarak ekran okuyucunun bu görseli "gürültü" yapmadan atlaması sağlanır.

#### 5.2.2. Form Etiketleme (<label>)
Erişilebilirlikteki en yaygın hatalardan biri, form alanlarını etiketsiz bırakmaktır. Her `<input>` elementi mutlaka bir `<label>` ile ilişkilendirilmelidir.

- **Mekanizma:** `<label for="email">E-posta:</label>` etiketi ile `<input id="email">` alanı `for` ve `id` değerleri üzerinden bağlanır.
- **Faydası:** Ekran okuyucu, kullanıcı giriş kutusuna odaklandığında sadece "metin kutusu" demek yerine "E-posta, metin kutusu" diyerek bağlamı sunar. Ayrıca label metnine tıklamak (mouse ile), ilgili input alanını odaklar; bu da motor becerileri kısıtlı veya titreme sorunu yaşayan kullanıcılar için tıklama alanını (hit area) genişletir.

#### 5.2.3. Başlık Hiyerarşisi (Heading Structure)
Başlık etiketleri (h1-h6) sadece yazı boyutu (font-size) ayarlamak için değil, dokümanın mantıksal içindekiler tablosunu oluşturmak için kullanılmalıdır.

Ekran okuyucu kullanıcıları, sayfada hızlı gezinmek için başlıklar arasında atlama (Navigation by Headings) yöntemini sıkça kullanır. Hiyerarşinin bozulması (örn. h2'den sonra h4 kullanmak), kullanıcının zihinsel haritasını bozar ve içeriğin anlaşılmasını zorlaştırır.

### 5.3. WAI-ARIA (Erişilebilir Zengin İnternet Uygulamaları)
Standart HTML etiketlerinin yetersiz kaldığı, JavaScript ile oluşturulan son derece dinamik içeriklerde (özel açılır menüler, modallar, slider'lar, anlık bildirimler) erişilebilirliği sağlamak için WAI-ARIA standartları devreye girer.

ARIA, HTML elementlerine eklenen `role`, `state` ve `property` öznitelikleri ile çalışır ve ekran okuyuculara "bu element aslında şudur ve şu an şu durumdadır" bilgisini verir.

#### 5.3.1. ARIA Rolleri ve Özellikleri
**Roller (Roles):** Bir elementin ne olduğunu tanımlar. Örneğin, bir `<div>` elementi görsel olarak butona benzetildiyse, ona `role="button"` verilerek ekran okuyucunun onu bir buton olarak tanıması sağlanır (Ancak mümkünse her zaman yerel `<button>` etiketi tercih edilmelidir). Diğer örnekler: `role="alert"` (hata mesajı), `role="navigation"` (menü).

**Durumlar (States):** Bir elementin o anki dinamik durumunu belirtir.

- `aria-expanded="true/false"`: Bir akordeon menünün açık veya kapalı olduğunu bildirir.
- `aria-hidden="true"`: Bir elementi ekran okuyuculardan gizler.
- `aria-live="polite"`: Sayfanın bir bölümünde içerik dinamik olarak değiştiğinde (örn. sohbet mesajı geldiğinde), ekran okuyucunun kullanıcıyı rahatsız etmeden bu değişikliği ne zaman okuyacağını belirler.

**İleri Düzey Etiketleme:**
- `aria-labelledby`: Bir elementi, sayfadaki başka bir elementin metniyle etiketler.
- `aria-describedby`: Bir elemente (örn. şifre kutusu) ek açıklama (örn. "Şifre en az 8 karakter olmalı" uyarısı) bağlar.

**Altın Kural:** "Hiç ARIA kullanmamak, kötü ARIA kullanmaktan iyidir." ARIA, HTML'in varsayılan davranışını değiştirmez, sadece yardımcı teknolojilere bilgi verir. Eğer bir işlev standart HTML etiketiyle yapılabiliyorsa, ARIA yerine standart etiket tercih edilmelidir.

## 6. Sonuç ve Değerlendirme
Bu araştırma raporu, web tasarımının temellerini oluşturan HTML yapılandırmasının; formlar aracılığıyla güvenli veri akışını sağlamak, tablolarla veriyi anlamlı sunmak, semantik HTML ile makine/insan tarafından anlaşılabilir bir iskelet kurmak ve erişilebilirlik standartları ile teknolojiyi herkes için ulaşılabilir kılmak üzerine kurulu olduğunu ortaya koymuştur.

İncelenen teknikler ve standartlar (HTML5, WCAG, ARIA), sadece bir web sayfasının teknik olarak "çalışmasını" değil, aynı zamanda etik, yasal ve kullanıcı deneyimi açısından evrensel standartlara uygun, sürdürülebilir ve yüksek kaliteli bir dijital varlık olmasını garanti altına almaktadır.

**Tablo 3: Web Yapılandırmasının Temel Bileşenleri**

| Kategori | Temel Bileşen | Birincil Amaç | Kritik Standart / En İyi Uygulama |
|----------|---------------|--------------|----------------------------------|
| Veri Toplama | Formlar | Güvenli ve doğru veri transferi | POST metodu, Sunucu Taraflı Doğrulama, `<label>` kullanımı |
| Veri Sunumu | Tablolar | İlişkisel verinin yapısal gösterimi | `<thead>`, `<th>`, `<caption>` kullanımı; CSS ile stil verme |
| Yapısal Mimari | Semantik Etiketler | Makine okunabilirliği ve SEO | `<main>`, `<article>`, `<nav>` ile iskelet kurma |
| Kapsayıcılık | Erişilebilirlik (a11y) | Evrensel erişim ve eşitlik | WCAG uyumu, alt metinleri, Klavye navigasyonu, ARIA |

Geliştiricilerin bu prensipleri benimsemesi, webin kapsayıcı ve bilgi odaklı vizyonunun devamlılığı için bir tercih değil, profesyonel bir zorunluluktur.

