# Temel Bilgi Teknolojileri: Genel Bilinmesi Gerekenler

## 1. Giriş

Bu doküman, Temel Bilgi Teknolojileri dersi sınavlarına hazırlık için kritik bilgileri içermektedir. İçerik, veri işleme süreçlerinden bilgisayar mimarisine, işletim sistemlerinden kelime işlemci yazılımlarına kadar geniş bir yelpazeyi kapsamaktadır.

## 2. Bilişimin Temel Kavramları: Veriden Bilgeliğe Hiyerarşik Dönüşüm

Bilişim teknolojilerinin temelinde, ham verinin insanlık için faydalı bir forma dönüştürülmesi süreci yatar. Sınavların teorik sorularının önemli bir kısmı, literatürde DIKW (Data, Information, Knowledge, Wisdom) hiyerarşisi olarak bilinen bu dönüşüm sürecini sorgulamaktadır.

### 2.1. DIKW Hiyerarşisinin Katmanları ve Ontolojik Tanımları

Veri işleme sürecinin anlaşılması, sınavdaki kavramsal soruların çözümü için kritiktir. Sorular, bu hiyerarşinin basamaklarını net tanımlarla birbirinden ayırmaktadır.

#### 2.1.1. Veri (Data): Ham Gerçeklik

Veri, hiyerarşinin en alt basamağıdır. Henüz bir bağlama oturtulmamış, işlenmemiş, ham gerçeklikler bütünüdür. Sınav sorularında veri kavramı, "metinler, sözcükler, rakamlar, sayılar, olaylar, resimler vb. şekilde gösterilen ham gerçeklikler" olarak tanımlanmaktadır.1 Örneğin, bir sensörden gelen "24" değeri tek başına bir veridir. Bu değerin neyi ifade ettiği (sıcaklık mı, yaş mı, uzaklık mı?) bilinmediği sürece, karar verme mekanizmalarında kullanılamaz. Veri, objektif gerçeklerin sembolik temsili olup, kendi başına bir anlam taşımaz.

#### 2.1.2. Enformasyon (Information): İlişkilendirilmiş Anlam

Verinin işlenerek, kategorize edilerek veya hesaplanarak bir bağlama oturtulmuş halidir. Verilerin "ne olduğunu bilme" durumudur.5 Sınavlarda enformasyon, "verilerin belli bir işleme tabi tutularak anlamlı bir hale getirilmesi sonucu oluşan yapı" olarak sorulmaktadır.2 Önceki örnekteki "24" verisi, "Oda sıcaklığı 24 derecedir" cümlesine dönüştüğünde enformasyon haline gelir. Enformasyon, veriye "kim, ne, nerede, ne zaman" sorularının sorulmasıyla elde edilir ve karar vericiye bir durumu tasvir eder.

#### 2.1.3. Bilgi (Knowledge): İçselleştirilmiş Deneyim

Enformasyonun bireyin deneyimleri, değerleri ve içgörüleriyle birleşerek eyleme dönüştürülebilir hale gelmesidir. "Nasıl" sorusuna cevap verir.4 Bilgi, deterministik bir süreçten ziyade, enformasyonun özümsenmesiyle ortaya çıkar. Bir kişinin 24 derece sıcaklıkta klimayı nasıl ayarlayacağını bilmesi, bilgi seviyesidir. Sınav müfredatı genellikle Veri ve Enformasyon ayrımına odaklansa da, Bilgi kavramı, verinin işlenme sürecinin nihai hedeflerinden biri olarak arka planda yer alır.

#### 2.1.4. Bilgelik (Wisdom): Geleceği Öngörme ve Yargı

Hiyerarşinin zirvesi olan bilgelik, sınavların en ayırt edici sorularından birine konu olmaktadır. Bilgelik, "olası problemleri görebilme, değerlendirebilme, doğru-yanlış ayrımını yapabilme yeteneği" olarak tanımlanır.3 Bilgi, mevcut durumu yönetmeyi sağlarken; bilgelik, neden-sonuç ilişkilerini derinlemesine anlayarak geleceğe dair öngörüde bulunmayı ve etik yargılamayı içerir. "Neden" sorusunun cevabıdır.5

**Tablo 1: DIKW Hiyerarşisi Kavramları**

| Kavram | Sınav Tanımı ve Anahtar Kelimeler | İlişkili Soru Tipi |
|--------|----------------------------------|-------------------|
| Veri | Ham gerçeklik, işlenmemiş sayı/metin, olaylar | Tanım Sorusu 1 |
| Enformasyon | İşlenmiş veri, anlamlı hale gelmiş yapı, "Ne olduğunu bilme" | Dönüşüm Süreci Sorusu 2 |
| Bilgelik | Doğru/yanlış ayrımı, değerlendirme yeteneği, "Nedenini bilme" | Ayırt Edici Tanım Sorusu 3 |

### 2.2. Veri İşlemenin Tarihsel Evrimi ve Yöntemleri

İnsanlık tarihi boyunca verinin işlenmesi ihtiyacı, teknolojinin gelişimini tetikleyen ana unsurlardan biri olmuştur. Sınavlar, bu süreci dört ana evreye ayırarak sorgulamaktadır. Bu evrelerin kronolojik ve teknolojik özelliklerini bilmek, "Aşağıdakilerden hangisi veri işleme evresi değildir?" tarzındaki soruları çözmek için elzemdir.

- **El Yordamıyla Veri İşleme**: İnsanlık tarihinin en uzun dönemini kapsar. Abaküs, parmak hesabı veya kağıt-kalem kullanılarak yapılan, herhangi bir otomasyonun olmadığı süreçtir. İnsan beyni ve kas gücü temel işlem birimidir.3

- **Mekanik Veri İşleme**: Sanayi devrimiyle birlikte ortaya çıkan, dişliler ve çarklarla çalışan hesap makineleri (Pascaline, Leibniz çarkı) ve daktiloların kullanıldığı dönemdir. Elektrik enerjisinin işlem sürecine doğrudan dahil olmadığı, fiziksel kuvvetin mekanik avantajla işlendiği evredir.3

- **Elektromekanik Veri İşleme**: Bu evre, sınavlarda özellikle "delikli kartlar" (punch cards) teknolojisiyle özdeşleştirilmektedir. Herman Hollerith'in 1890 ABD nüfus sayımı için geliştirdiği tablolama makineleri bu dönemin en belirgin örneğidir. Veriler karton kartlar üzerine açılan deliklerle kodlanır ve elektrik devrelerini tamamlayıp tamamlamamasına göre makine tarafından okunur.3 Sınav sorusunda "delikli kartlar kullanılarak veri işleme yapılması" özelliği doğrudan Elektromekanik Veri İşleme evresine atıfta bulunur.

- **Elektronik Veri İşleme**: Vakum tüpleri, transistörler ve entegre devrelerin kullanıldığı, günümüz bilgisayarlarının temelini oluşturan evredir. Veri işleme hızı milisaniyelerden nanosaniyelere düşmüştür.3

**Sınav Uyarısı**: Sınavlarda çeldirici olarak "Mantıksal Veri İşleme" gibi bir seçenek sunulmaktadır. Literatürde veri işleme tarihçesinde böyle bir evre tanımlanmamıştır; mantıksal işlemler, elektronik veri işlemenin bir alt fonksiyonudur, tarihsel bir evre değildir.3

### 2.3. Verinin Enformasyona Dönüşüm Süreci

Verinin enformasyona dönüşümü, ham maddenin mamul maddeye dönüşümü gibi belirli alt süreçler gerektirir. Sınav soruları, bu sürecin aşamalarını da kapsamaktadır:

- **Kategorize Etme**: Verilerin belirli özelliklere göre gruplandırılması.
- **Hesaplama**: Veriler üzerinde matematiksel veya mantıksal işlemler yapılması.
- **Özetleme**: Büyük veri yığınlarının daha anlaşılır özetlere indirgenmesi.
- **Biçimlendirme (Formatting)**: Sınavlarda bu aşama, genellikle dönüşüm sürecinin dışında kalan veya farklı bir bağlamda (sunum katmanı) değerlendirilen bir seçenek olarak karşımıza çıkar.2 Biçimlendirme, verinin içeriğini veya anlamını değiştirmekten ziyade, görsel sunumunu (kalın, italik, renkli vb.) değiştirdiği için, verinin özünü enformasyona dönüştüren temel analitik süreçlerden biri olarak kabul edilmeyebilir.

## 3. Bilgisayar Mimarisi ve Donanım Teknolojileri

Bilgisayarın fiziksel yapısını anlamak, Temel Bilgi Teknolojileri dersinin omurgasını oluşturur. Sınavlar, bilgisayar tarihçesinden başlayarak modern donanım birimlerinin sınıflandırılmasına kadar geniş bir yelpazeyi kapsar.

### 3.1. Bilgisayar Tarihçesi: ENIAC ve Dijital Devrim

Bilgisayar tarihçesindeki en kritik dönemeç, genel amaçlı elektronik bilgisayarların ortaya çıkışıdır. Sınav soruları, 1946 yılında ABD ordusu tarafından balistik hesaplamalar için geliştirilen ENIAC (Electronic Numerical Integrator and Computer) üzerine yoğunlaşmaktadır.

**ENIAC'ın Özellikleri**: 1946 yılında tamamlanmıştır. İlk genel kullanım amaçlı elektronik bilgisayar olarak kabul edilir. Sınavlarda ayırt edici özellik olarak "onluk sayı tabanına (decimal) dayalı" olması sorulmaktadır.2 Modern bilgisayarlar ikili (binary) sistem kullanırken, ENIAC onluk sistemle çalışıyordu. Bu detay, bilgisayar bilimleri tarihindeki teknolojik geçişi anlamak adına önemlidir.

**Bilgisayar Türleri**: Çalışma prensiplerine göre bilgisayarlar üç ana kategoriye ayrılır:

- **Dijital (Sayısal) Bilgisayarlar**: Verileri 0 ve 1'lerden oluşan ikili (binary) kodlarla işleyen, ayrık (discrete) veri kullanan sistemlerdir. Günümüzdeki PC'ler, akıllı telefonlar ve tabletler bu sınıftadır. Sınavda "iki tabanlı sayı sisteminin kullanıldığı bilgisayar türü" olarak sorulmuştur.1

- **Analog Bilgisayarlar**: Fiziksel büyüklükleri (voltaj, akım, basınç) sürekli (continuous) sinyaller olarak işleyen cihazlardır. Termometreler veya eski tip hız göstergeleri basit analog bilgisayar mantığıyla çalışır. Doğruluk oranları dijital bilgisayarlara göre daha düşüktür ve programlanabilirlikleri sınırlıdır.8

- **Hibrid Bilgisayarlar**: Hem analog hem de dijital bileşenleri barındıran, analog sinyalleri dijitale çevirip işleyen karma sistemlerdir (Örn: EKG cihazları).

**Sayı Sistemleri ve Kaydediciler**: Modern dijital bilgisayarların işlemcileri (CPU) içindeki en hızlı bellek birimleri olan Kaydediciler (Registers), verileri depolarken ve işlerken İkili (Binary) sayı sistemini kullanır.3 Sınavlarda onluk (decimal), beşlik (quinary) veya sekizlik (octal) gibi seçenekler çeldirici olarak verilir. Elektronik devrelerin "açık" (1) ve "kapalı" (0) durumlarına dayanması nedeniyle, binary sistem dijital donanımın doğası gereği tek seçenektir.

### 3.2. Donanım Birimleri: Yapısal ve İşlevsel Sınıflandırma

Donanım birimleri, konumlarına (İçsel/Dışsal) ve işlevlerine (Giriş/Çıkış) göre sınıflandırılır. Sınav soruları bu sınıflandırmaları net bir şekilde yapabilme yeteneğini ölçmektedir.

#### 3.2.1. Anakart (Motherboard): Sistemin Omurgası

Tüm donanım birimlerinin doğrudan veya dolaylı olarak bağlandığı ana elektronik karttır. İşlemci, RAM ve ekran kartı gibi bileşenler doğrudan anakart üzerindeki yuvalara (slot/soket) takılırken; sabit disk, klavye ve fare gibi bileşenler kablolar veya portlar aracılığıyla anakarta bağlanır. Sınavlarda "bütün donanım birimlerinin üzerine bağlandığı kart" tanımı istisnasız Anakart'ı işaret eder.2

#### 3.2.2. İçsel (Dahili) ve Dışsal (Harici) Donanım

Donanımların bilgisayar kasasının (sistem ünitesi) içinde veya dışında bulunmasına göre yapılan ayrımdır:

**İçsel Donanım**: Sistemin çalışması için zorunlu olan ve kasa içinde korunan parçalardır.

- **İşlemci (CPU)**: Beyin. Verileri işler.
- **RAM Bellek**: Geçici hafıza.
- **Sabit Disk (HDD/SSD)**: Kalıcı depolama.
- **Ses Kartı**: Bilgisayardaki dijital ses verilerini analog sinyallere çevirerek hoparlöre gönderilmesini sağlayan donanım birimidir.1
- **Anakart**: Tüm parçaların taşıyıcısı.

**Dışsal Donanım**: Kasa dışından sisteme bağlanan çevre birimleridir.

- **Giriş Birimleri**: Klavye, Fare, Mikrofon, Kamera, Tarayıcı.
- **Çıkış Birimleri**: Monitör (Ekran), Yazıcı, Hoparlör.
- **İletişim**: Modem (Dışsal olabilir).

Bir sınav sorusunda, "Aşağıdakilerden hangisi içsel donanım birimlerinden biri değildir?" sorusuna cevap olarak Klavye verilmiştir.2 Bu, içsel/dışsal ayrımının sınavda belirleyici bir kriter olduğunu göstermektedir.

#### 3.2.3. Bellek Hiyerarşisi ve Depolama

Bilgisayarın veri saklama mantığı, hız ve kalıcılık ters orantısına dayanır.

- **RAM (Random Access Memory)**: Rastgele erişimli bellektir. İşlemcinin o an üzerinde çalıştığı programlar ve veriler burada tutulur. Elektrik kesildiğinde içindeki veriler silinir (uçucu bellek). RAM, bir çalışma masasına benzetilebilir; masa ne kadar genişse o kadar çok dosya ile aynı anda çalışılabilir.9

- **Sabit Disk (Hard Disk Drive / SSD)**: Kalıcı depolama birimidir. İşletim sistemi, programlar ve kullanıcı dosyaları burada saklanır. Elektrik kesilse bile veriler korunur. Sabit disk bir dosya dolabına benzetilebilir; kapasitesi yüksektir ancak verilere erişim hızı RAM'e göre çok daha düşüktür.9

- **MBR (Master Boot Record)**: Sabit diskin ilk sektörüdür. Bilgisayar açıldığında BIOS'un okuduğu ilk bölümdür ve işletim sisteminin yüklenmesini başlatır. Sınavlarda, bu bölüme yerleşen ve bilgisayarın açılışını engelleyen veya kontrolü ele alan zararlı yazılım türü "Ön yükleme virüsü" (Boot Sector Virus) olarak sorulmaktadır.3

## 4. İşletim Sistemleri: Masaüstü ve Mobil Mimari Analizi

İşletim sistemleri konusu, donanım ile kullanıcı arasındaki köprüyü kurması açısından kritik öneme sahiptir. Sınavlar, genel işletim sistemi tanımlarının ötesine geçerek, özellikle mobil işletim sistemlerinin (Android ve iOS) katmanlı mimarilerini detaylıca sorgulamaktadır.

### 4.1. İşletim Sistemi (OS) Kavramı ve Görevleri

İşletim sistemi; bilgisayar donanım kaynaklarını (işlemci, bellek, disk vb.) yöneten ve çeşitli uygulama yazılımları için yaygın servisleri sağlayan bir yazılımlar bütünüdür. Kullanıcı ile bilgisayar arasındaki iletişimi sağlar.2

**Yaygın İşletim Sistemleri**:

- **Windows**: Microsoft tarafından geliştirilen, en yaygın masaüstü OS.
- **Linux**: Açık kaynak kodlu, çekirdek (kernel) yazılımı.
- **Pardus**: TÜBİTAK tarafından geliştirilen, Linux tabanlı, Türkiye'nin ilk yerli ve milli işletim sistemi dağıtımıdır.1 Sınavlarda Pardus'un milliliği ve Linux tabanlı oluşu önemli bir bilgi maddesidir.
- **MacOS**: Apple bilgisayarların işletim sistemi.
- **Android & iOS**: Mobil işletim sistemleri.

**İşletim Sistemi Olmayanlar**:

- **ENIAC**: Bir bilgisayar donanımıdır, yazılım değildir.2
- **Microsoft Defender**: Bir antivirüs/güvenlik yazılımıdır.3
- **Safari / Edge**: Web tarayıcısıdır (Browser).

### 4.2. Android İşletim Sistemi Mimarisi

Android, Linux çekirdeği üzerine inşa edilmiş, açık kaynak kodlu ve katmanlı bir mimariye sahip mobil işletim sistemidir. Sınavlar, bu katmanların her birinin işlevini ve içeriğini spesifik olarak sormaktadır. Android mimarisi aşağıdan yukarıya doğru şu şekildedir:

- **Çekirdek (Linux Kernel)**: En alt katmandır. Donanım ile yazılım arasındaki soyutlamayı sağlar. Güvenlik, hafıza yönetimi, süreç yönetimi, ağ yığını ve sürücü modellerini içerir. Sınavlarda "Linux temel kodlarını barındıran bölüm" olarak sorulur ve doğru cevap Çekirdektir.1

- **Donanım Soyutlama Katmanı (HAL)**: Üst katmanların donanıma (kamera, bluetooth vb.) erişmesini sağlayan standart arabirimleri sunar.

- **Kütüphaneler (Libraries) ve Android Runtime (ART)**:
  - **Kütüphaneler**: C/C++ ile yazılmış, sistemin çalışması için gereken temel bileşenleri (SQLite veritabanı, WebKit tarayıcı motoru, OpenGL grafik kütüphanesi) içerir.
  - **Android Runtime (ART)**: Uygulamaların çalıştırıldığı sanal makine ortamıdır. Her uygulama kendi sürecinde ve kendi ART örneğinde çalışır.

- **Uygulama Çatısı (Application Framework)**: Uygulama geliştiricilerin kullandığı, Java/Kotlin tabanlı API'leri sunan katmandır. Geliştiriciler, sistemin sunduğu özellikleri (lokasyon, bildirimler vb.) bu katman üzerinden çağırır.

- **Uygulama Katmanı (Applications)**: Mimarinin en üst katmanıdır. Kullanıcının doğrudan etkileşime girdiği e-posta, SMS, takvim, harita, tarayıcı ve rehber gibi uygulamalar burada yer alır. Sınavlarda "Doğrudan Java programlama dili ile yazılmış uygulamaları içeren bölüm" olarak sorulur ve doğru cevap Uygulama Katmanıdır.1

### 4.3. Apple iOS İşletim Sistemi Mimarisi

iOS, Apple'ın mobil cihazları (iPhone, iPad) için geliştirdiği, Unix tabanlı (Darwin çekirdeği) kapalı kaynak kodlu bir işletim sistemidir. iOS mimarisi de katmanlıdır ancak isimlendirmeleri Android'den farklıdır. Sınavda bu katmanların isimlerini bilmek ve hangisinin iOS katmanı olmadığını ayırt etmek gerekmektedir.

**iOS Katmanları (Aşağıdan Yukarıya)**:

- **Core OS (Çekirdek İşletim Sistemi)**: En alt katmandır. Donanımla en yakın çalışan, güvenlik, yerel yetkilendirme ve temel sistem fonksiyonlarını barındıran katmandır.3

- **Core Services (Çekirdek Servisler)**: Dosya yönetimi, veri tabanı (SQLite), ağ hizmetleri, iCloud erişimi gibi temel hizmetleri sunar. Grafik arayüzü olmayan sistem servisleri buradadır.

- **Media (Medya)**: Ses, video ve grafik teknolojilerini içerir. OpenAL, Core Audio, OpenGL, PDF işleme gibi teknolojiler bu katmanda yer alır.

- **Cocoa Touch**: En üst katmandır. Dokunmatik ekran arayüzünü, çoklu dokunma (multi-touch) hareketlerini, ivmeölçer desteğini ve kullanıcı arayüzü elemanlarını (butonlar, listeler) barındırır. iOS uygulama geliştirme çatısıdır.

**Kritik Sınav Analizi**: Bir sınav sorusunda "Aşağıdakilerden hangisi Apple iOS İşletim Sistemi katmanı değildir?" sorusuna seçenek olarak "Uygulama Katmanı" konulmuş ve doğru cevap olarak işaretlenmiştir.3 Bu durum, iOS literatüründe en üst katmanın "Application Layer" yerine spesifik olarak "Cocoa Touch" olarak adlandırılmasından kaynaklanır. Android'de "Uygulama Katmanı" varken, iOS'ta bu işlevi "Cocoa Touch" üstlenir. Bu ince terminolojik fark, sınavda belirleyicidir.

**Tablo 2: Android ve iOS Katman Karşılaştırması**

| Katman Seviyesi | Android Karşılığı | iOS Karşılığı |
|----------------|-------------------|---------------|
| Arayüz / En Üst | Uygulama Katmanı (Applications) | Cocoa Touch |
| Medya / Çatı | Uygulama Çatısı (Framework) | Media Layer |
| Servisler | Kütüphaneler & Runtime | Core Services |
| Çekirdek / Taban | Linux Kernel | Core OS |

## 5. Kelime İşlemci Yazılımları: Microsoft Word Uzmanlığı

Dersin en uygulamalı kısmı Microsoft Word üzerinedir. Sorular, kullanıcının sadece metin yazmasını değil, programın arayüzüne (Ribbon/Şerit), kısayollarına ve dosya formatlarına profesyonel düzeyde hakim olmasını bekler.

### 5.1. Şerit (Ribbon) Yapısı ve Sekme İşlevleri

Word programında komutlar sekmeler (tabs) altında gruplandırılmıştır. Hangi komutun hangi sekmede olduğunu ezberlemek, sınav başarısı için en kritik faktördür.

- **Dosya (File) Menüsü**: Belgeyi açma, kaydetme, yazdırma ve paylaşma gibi "sahne arkası" işlemlerin yapıldığı yerdir. Sınavlarda "Paylaş" seçeneği üzerinden nelerin yapılıp yapılamayacağı sorulmuştur. Paylaş menüsü ile belge e-posta, PDF veya XPS olarak gönderilebilir, bir blog yazısı olarak yayınlanabilir. Ancak "Belgeye düzenleme kısıtı getirmek" (Belge Koruması) işlemi doğrudan Paylaş menüsünden değil, genellikle "Bilgi" sekmesi altındaki "Belgeyi Koru" veya "Gözden Geçir" sekmesindeki "Kısıtla" seçeneklerinden yapılır. Bu nedenle sınav sorusunda Paylaş menüsüyle yapılamayacak işlem olarak "düzenleme kısıtı getirmek" işaretlenmiştir.1

- **Giriş (Home) Sekmesi**: En sık kullanılan komutlar (Yazı tipi, Paragraf, Pano işlemleri).

- **Ekle (Insert) Sekmesi**: Belgeye metin olmayan öğelerin (Tablo, Resim, Şekil, Grafik, Sayfa Numarası, Simge) eklendiği yerdir.

  - **Tablo Ekleme**: Tablolar satır ve sütunlardan oluşur, verileri düzenli sunar. Metinler tabloya, tablolar metne dönüştürülebilir. Tablo ekleme düğmesi Ekle sekmesindedir. Sınavda çeldirici olarak "Tasarım sekmesindeki tablolar grubundan tablo eklenir" ifadesi verilmiştir; bu yanlıştır, Tasarım sekmesi var olan bir tablonun stilini değiştirmek için kullanılır, tabloyu oluşturmak için değil.1

- **Tasarım (Design) Sekmesi**: Belgenin genel görsel stilini yönetir. Sayfa Rengi, Sayfa Kenarlıkları ve Filigran (Watermark) komutları bu sekmededir.1 Filigranın Ekle veya Düzen sekmesinde değil, Tasarım sekmesinde olduğunu bilmek önemlidir.

- **Başvurular (References) Sekmesi**: Akademik ve uzun belgeler için hayati öneme sahiptir. İçindekiler Tablosu, Dipnot Ekle (Footnote), Alıntılar ve Kaynakça komutları buradadır.1 Dipnot eklemenin Ekle menüsünde değil, Başvurular menüsünde olduğu sıkça sorulan bir detaydır.

- **Gözden Geçir (Review) Sekmesi**: Belgeyi kontrol etme araçlarıdır. Yazım denetimi, Çeviri, Açıklamalar ve Değişiklikleri İzle (Track Changes) buradadır. Değişiklikleri izleme özelliği, belgede yapılan ekleme ve silme işlemlerinin farklı renklerle gösterilmesini sağlar.1

- **Görünüm (View) Sekmesi**: Belgenin ekranda nasıl görüneceğini ayarlar (Okuma Modu, Sayfa Düzeni, Web Düzeni). Düzenleme alanını yakınlaştırma (Zoom) veya birden çok sayfayı aynı anda görme işlemleri buradan yapılır.2

### 5.2. Kritik Klavye Kısayolları ve Tuş Fonksiyonları

Profesyonel kullanımın göstergesi olan kısayollar, sınavlarda "Hangi tuş kombinasyonu ne işe yarar?" formatında sorulmaktadır.

**Tablo 3: Microsoft Word Klavye Kısayolları**

| Kısayol | İşlev ve Açıklama | Sınav Referansı |
|---------|------------------|----------------|
| CTRL + S | Kaydet (Save): Belgeyi diske yazar. En temel kısayoldur. | 2 |
| CTRL + N | Yeni (New): Yeni boş bir belge açar. | 14 |
| CTRL + C | Kopyala (Copy): Seçili nesneyi panoya kopyalar. | 1 |
| CTRL + V | Yapıştır (Paste): Panodaki nesneyi imlecin olduğu yere yapıştırır. | 1 |
| CTRL + Z | Geri Al (Undo): Son yapılan işlemi geri alır. | 3 |
| Shift + F10 | Bağlam Menüsü: Seçili öğe üzerinde sağ tıklama (right-click) menüsünü açar. Mouse kullanmadan sağ tık menüsüne erişmek için kullanılır. | 171 |
| F10 + TAB | Şerit Gezintisi: F10 tuşu, şerit üzerindeki menülerin kısayol harflerini (KeyTips) aktif eder. Ardından TAB tuşuna basmak, aktif sekme üzerindeki komutlar arasında sırayla gezinmeyi sağlar. Sınavda "Etkin sekme üzerindeki komutlar arasında gezinmeyi sağlayan bileşen" olarak sorulmuştur. | 2 |

### 5.3. Dosya Biçimleri ve Standartlar

Kelime işlemcilerin ürettiği dosya formatları, belgenin taşınabilirliği ve uyumluluğu açısından önemlidir.

- **.docx**: Microsoft Word 2007 ve sonrası sürümlerin varsayılan, XML tabanlı dosya formatıdır.

- **.odt (Open Document Text)**: "Açık Belge Metni" olarak adlandırılır. LibreOffice, OpenOffice gibi açık kaynak kodlu yazılımların standart formatıdır. Ancak Word de bu formatı açabilir ve kaydedebilir. Sınavlarda "Kelime işlemcilere standart dosya biçimi sunan ve Açık Belge Metni olarak adlandırılan kavram" sorusunun cevabı odt'dir.2

- **.pdf (Portable Document Format)**: Belgenin her cihazda aynı görünmesini sağlayan, düzenlenmesi zor formattır. LibreOffice Writer gibi programlar sadece PDF değil, docx ve rtf gibi formatlarda da çıktı verebilir; bu nedenle "sadece pdf dışa aktarabilir" ifadesi yanlıştır.1

- **.xps (XML Paper Specification)**: Microsoft'un PDF formatına alternatif olarak geliştirdiği, belgenin görünümünü sabitleyen dosya biçimidir. Word belgeleri xps olarak kaydedilebilir veya gönderilebilir.1

## 6. İnternet Teknolojileri ve Siber Güvenlik

Dijital okuryazarlığın son halkası, ağ yapılarını anlamak ve siber tehditlere karşı bilinçli olmaktır.

### 6.1. Bilgisayar Ağları: Kapsama Alanına Göre Sınıflandırma

Ağlar, coğrafi büyüklüklerine göre sınıflandırılır. Sınav sorusu özellikle en küçük ağ birimine odaklanmıştır.

- **PAN (Personal Area Network - Kişisel Alan Ağı)**: Bir kişinin çalışma alanı içindeki (genellikle birkaç metrelik) cihazların (telefon, kulaklık, laptop, yazıcı) birbirine bağlanmasıdır. Bluetooth ve USB teknolojileri PAN oluşturur. Sınavda "kullanıcıların mobil cihazları ve bilgisayarları arasında birkaç metrelik mesafede iletişim kurabilmelerini sağlayan ağ" tanımı PAN'ı işaret eder.1

- **LAN (Local Area Network)**: Yerel alan ağı (Ev, ofis, okul laboratuvarı).

- **WAN (Wide Area Network)**: Geniş alan ağı (Şehirlerarası ağlar, İnternet).

### 6.2. İnternet Adresleri ve Tarayıcılar

**Alan Adı Uzantıları (Domain Extensions)**: Web sitelerinin türünü belirtir.

- **.gov**: Hükümet ve devlet kurumları (Government). Örn: turkiye.gov.tr. 2
- **.edu**: Eğitim kurumları / Üniversiteler (Education).
- **.k12**: İlk ve orta dereceli okullar (Kindergarten to 12th grade).

**Web Tarayıcıları (Browsers)**: İnternet sayfalarını görüntülemeye yarayan yazılımlardır. Chrome, Firefox, Safari, Edge, Opera, Yandex birer tarayıcıdır. Ancak Microsoft Defender bir tarayıcı değildir, Windows'un yerleşik güvenlik yazılımıdır.3

**Gizli Sekme (Incognito/Private Mode)**: Tarayıcının, kullanıcının gezinti geçmişini, çerezleri (cookies) ve site verilerini oturum kapandığında kaydetmediği moddur. "Kullanıcı hareketlerinin takip edilmemesi ve gizli kalması" istendiğinde kullanılır. Bu modda IP adresi gizlenmez, sadece yerel bilgisayarda iz bırakılmaz.3

**Adres Çubuğu**: Tarayıcının üst kısmında bulunan ve gidilmek istenen web sitesinin URL'sinin yazıldığı alandır.1

### 6.3. Zararlı Yazılımlar (Malware) ve Tehdit Türleri

Siber güvenlik soruları, tehdit türlerini tanımlamaya yöneliktir.

- **Spam (Çöp E-posta)**: Kullanıcının isteği ve onayı dışında gönderilen, genellikle reklam veya dolandırıcılık amaçlı toplu e-postalardır.1

- **Casus Yazılım (Spyware)**: Kullanıcının haberi olmadan sisteme sızan, klavye vuruşlarını kaydetmek, gezinti alışkanlıklarını izlemek veya kişisel verileri çalmak için tasarlanmış yazılımlardır.1

- **Solucan (Worm)**: Bir ağ üzerinde, insan müdahalesi olmadan kendi kendine çoğalabilen ve yayılan zararlı yazılımdır.

- **Truva Atı (Trojan)**: Kendisini faydalı bir program (oyun, araç vb.) gibi gösteren ancak arka planda sisteme zarar veren veya arka kapı açan yazılımdır. Kendi kendine çoğalmaz.

- **Ön Yükleme Virüsü (Boot Sector Virus)**: Sabit diskin veya disketin MBR (Master Boot Record) sektörüne yerleşen virüslerdir. Bilgisayar açılırken işletim sisteminden önce belleğe yüklenirler, bu da temizlenmelerini zorlaştırır.3

## 7. Sonuç ve Sınav Başarı Stratejisi

Yapılan derinlemesine analiz göstermektedir ki, "Temel Bilgi Teknolojileri I" dersi sınavları, bilgi teknolojilerinin terminolojisine ve mantığına hakimiyeti ölçmektedir. Yüksek puan almak isteyen bir öğrenci, aşağıdaki stratejik noktaları içselleştirmelidir:

- **Kavramsal Netlik**: Veri ile Enformasyon arasındaki farkı, Android'in Çekirdeği ile Uygulama Katmanı arasındaki işlevsel ayrımı, iOS'un Cocoa Touch katmanının Android'deki karşılığını net bir şekilde bilmek gereklidir.

- **Arayüz Görselleştirme**: MS Word soruları için programın arayüzünü zihinsel olarak haritalandırmak şarttır. Hangi sekmede hangi grubun (Örn: Tasarım sekmesinde Sayfa Arka Planı grubu) olduğunu bilmek, ezber yükünü azaltır.

- **Kategorik Düşünme**: Donanımları (İç/Dış), Yazılımları (İşletim Sistemi/Uygulama), Dosya Formatlarını (Açık/Kapalı) kategorize ederek çalışmak, "Aşağıdakilerden hangisi değildir?" şeklindeki olumsuz köklü soruları çözmeyi kolaylaştırır.

- **Anahtar Kelime Eşleştirmesi**:
  - Ham gerçeklik -> Veri
  - Nedenini bilme -> Bilgelik
  - Birkaç metre mesafe -> PAN
  - Açık belge metni -> odt
  - Onluk sayı tabanlı bilgisayar -> ENIAC
  - Linux kodlarını barındıran katman -> Çekirdek

Bu rapor, sağlanan sınav materyalleri ve ek araştırmalar ışığında, dersin tüm kazanımlarını kapsayacak şekilde hazırlanmıştır. Buradaki bilgilerin özümsenmesi, sadece sınav başarısı için değil, temel dijital okuryazarlık yetkinliklerinin kazanılması adına da yeterli olacaktır.

