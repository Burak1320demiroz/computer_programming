# Grafik Tasarım: Genel Bilinmesi Gerekenler

## 1. Renk Teorisinin Fiziksel ve Psikolojik Temelleri

Grafik tasarımın en kritik bileşeni olan renk, sınavlarda hem teknik (fiziksel oluşum) hem de anlamsal (psikolojik etki) boyutlarıyla sorgulanmaktadır. Renk yönetimi, dijital tasarımdan baskı aşamasına kadar olan sürecin bel kemiğidir ve bu alandaki sorular genellikle adayların renk modelleri arasındaki farkları ayırt edip edemediğini ölçmeye odaklanır.

### 1.1. Işık ve Pigment: Renk Modellerinin Teknik Analizi

Dijital dünyada ve fiziksel baskıda renklerin oluşturulma prensipleri taban tabana zıttır. Sınav soruları, özellikle RGB ve CMYK modelleri arasındaki yapısal farklar, kullanım alanları ve dönüşüm zorunlulukları üzerinde yoğunlaşmaktadır. Bu iki modelin çalışma mantığını kavramak, ilgili tüm soruları doğru yanıtlamanın anahtarıdır.

#### RGB Renk Modu (Toplamsal Sentez)

RGB renk modeli, insan gözünün ışığı algılama prensibine dayanan ve ışık yayan cihazlar için geliştirilmiş bir standarttır. "Red" (Kırmızı), "Green" (Yeşil) ve "Blue" (Mavi) renklerinin baş harflerinden oluşur.1 Bu modelin temel özelliği toplamsal (additive) olmasıdır; yani renkler karanlık bir zemin üzerine ışık eklenerek oluşturulur. Hiçbir ışığın olmadığı durum siyahı (karanlığı), üç ana rengin tam yoğunlukta birleşimi ise beyaz ışığı oluşturur.

Sınavlarda RGB ile ilgili şu detaylar kritik önem taşır:

- **Bileşenler**: RGB modunun bileşenleri kesinlikle Kırmızı, Yeşil ve Mavi'dir. Sorularda "Sarı" veya "Gri" gibi seçenekler çeldirici olarak sunulur.2
- **Kullanım Alanları**: Monitörler, televizyonlar, dijital kameralar, tarayıcılar ve akıllı telefon ekranları bu modu kullanır. Web tasarımı, video prodüksiyonu ve dijital arayüz tasarımı RGB uzayında gerçekleştirilir.1
- **Doğal Renk (True Color)**: RGB modunda her bir kanalın (R, G, B) 8 bitlik veriye sahip olduğu durumlarda, toplam 24 bitlik renk derinliği elde edilir. Bu da yaklaşık 16.7 milyon renk tonuna tekabül eder. Sınavlarda, bir görüntünün doğal bir renk sunması veya buna çok yaklaşması durumu "True Color" (Gerçek Renk) olarak tanımlanır.3

#### CMYK Renk Modu (Çıkarımsal Sentez)

Baskı teknolojilerinin temelini oluşturan CMYK modeli, ışığı yansıtma prensibine dayanır. Kağıt gibi beyaz bir yüzey üzerine sürülen mürekkepler, yüzeye çarpan ışıktan belirli dalga boylarını emerek (çıkararak) rengin gözümüze ulaşmasını sağlar. Bu nedenle çıkarımsal (subtractive) renk modeli olarak adlandırılır.5

CMYK ile ilgili sınavlarda bilinmesi gereken en önemli hususlar şunlardır:

- **Bileşenler**: "Cyan" (Camgöbeği), "Magenta" (Galibarda/Pembe), "Yellow" (Sarı) ve "Key" (Siyah). Siyahın "Key" olarak adlandırılmasının nedeni, baskı kalıplarının hizalanmasında anahtar rol oynaması ve diğer üç rengin karışımının tam siyahı verememesidir.3
- **Siyahın Fonksiyonu**: Teorik olarak Camgöbeği, Galibarda ve Sarı'nın karışımı siyahı oluşturmalıdır, ancak pratikte bu karışım koyu kahverengi veya çamurlu bir gri oluşturur. Bu nedenle, metinlerin keskinliğini sağlamak, derinlik katmak ve renkli mürekkep maliyetini düşürmek amacıyla sisteme siyah (K) eklenmiştir.3
- **Kullanım Alanları**: Poster, broşür, kartvizit, dergi, kitap ve gazete gibi fiziksel olarak basılan tüm materyallerde kullanılır.1

#### Renk Modu Dönüşümünün Zorunluluğu

Grafik tasarımcılar genellikle tasarımlarını RGB moduna sahip monitörlerde yaparlar, ancak iş baskıya gideceği zaman dosyanın CMYK moduna dönüştürülmesi gerekir. Sınavlarda bu dönüşümün "neden" zorunlu olduğu sıkça sorulmaktadır.

- **Gamut Farkı**: RGB renk uzayı (gamut), CMYK renk uzayından çok daha geniştir. Ekranda görülebilen parlak neon renkler, elektrik mavileri veya canlı turuncular, standart baskı mürekkepleriyle elde edilemez.
- **Görünüm Tutarlılığı**: Basımdan önce tasarımın CMYK'ya dönüştürülmesi, ekrandaki görüntü ile baskı sonucu arasındaki farkı minimize etmek içindir. Sınav literatüründe bu durum, "RGB'den CMYK'ya dönüşüm sürecinde belirli renklerin görünümünün farklı görülebilir olması" gerekçesiyle açıklanır.2 Profesyonel yazıcılar, sürpriz sonuçları önlemek adına bu dönüşümü şart koşar.

### 1.2. Diğer Renk Modları ve Özel Kullanımlar

RGB ve CMYK dışında, grafik tasarım yazılımlarının desteklediği ve sınavlarda detay bilgisi olarak sorulan diğer renk modları da mevcuttur.

- **Lab Renk Modu**: İnsan gözünün algılayabildiği tüm renk spektrumunu kapsayan, cihazdan bağımsız (device-independent) bir modeldir. RGB ve CMYK arasında en kayıpsız dönüşüm sağlayan ara format olarak kullanılır. Sınavlarda, Photoshop'un desteklediği modlar arasında sayılır.3 Lab modundaki görseller; Photoshop EPS, PSB (Large Document Format), PDF, Raw ve TIFF formatlarında kaydedilebilirken, JPEG gibi bazı formatlarda doğrudan kaydedilmeyebilirler.2

- **Gri Tonlama (Grayscale)**: Renk bilgisinin atıldığı, sadece siyah, beyaz ve gri tonlarının (genellikle 256 ton) kaldığı moddur.3

- **Bitmap Modu**: Görüntünün sadece %100 siyah ve %100 beyaz piksellerden oluştuğu, gri tonların bulunmadığı 1-bitlik renk modudur. Bu moddaki resimlere filtre uygulanamaz.3

- **Çift Ton (Duotone)**: Tek renkli (gri tonlamalı) bir görüntünün üzerine ikinci, üçüncü veya dördüncü bir rengin (mürekkebin) eklenmesiyle oluşturulan moddur. Sınavlarda, "birden dörde kadar özelleştirilmiş mürekkep kullanarak görüntü oluşturan mod" tanımıyla sorulur.6 Bu mod genellikle sepya efektli fotoğraflar veya sanatsal baskılar için tercih edilir.

### 1.3. Renk Terminolojisi ve Kavramsal Altyapı

Renk teorisiyle ilgili soruları doğru yanıtlamak için temel kavramların tanımlarına tam hakimiyet gereklidir. Sınav dosyalarında yer alan tanımlar şöyledir:

**Tablo 1: Renk Terminolojisi**

| Kavram | Sınav Tanımı ve Açıklaması | Kaynak |
|--------|---------------------------|--------|
| Ton (Hue) | Bir nesneden yansıyan veya iletilen saf renktir. Kırmızı, mavi, sarı gibi rengin kimliğini ifade eder. | 2 |
| Doygunluk (Saturation) | Rengin yoğunluğu, saflığı veya canlılığıdır. Bir rengin ne kadar "parlak" veya "sönük" (griye yakın) göründüğünü belirler. Doygunluk azaldıkça renk grileşir. | 3 |
| Parlaklık (Brightness) | Rengin açıklığı veya koyuluğudur; renge ne kadar siyah veya beyaz eklendiğini ifade eder. | 3 |
| Renk Derinliği | Bir pikselin alabileceği toplam renk sayısını belirleyen bit değeridir. Örneğin 8-bit derinlik piksel başına 256 renk, 24-bit derinlik milyonlarca renk demektir. | 3 |
| Renk Modu | Görüntüdeki diğer tüm renkleri oluşturmak için çeşitli miktarlarda birleştirilen renkler kümesine verilen isimdir. | 3 |

### 1.4. Renk Uyumu ve Tasarım Psikolojisi

Tasarımda estetik dengeyi sağlamak için kullanılan renk şemaları (harmony rules) ve renklerin insan üzerindeki psikolojik etkileri, sınavın teorik kısmını oluşturur. Renk çemberi (color wheel), renkler arasındaki ilişkileri anlamada kullanılan temel grafiktir.3

#### Renk Şemaları (Harmoniler)

Sınavlarda, renk çemberi üzerindeki geometrik ilişkilere dayalı şemalar tanımlanarak sorulmaktadır:

- **Tamamlayıcı Renkler (Complementary)**: Renk çemberinde birbirinin tam karşısında yer alan zıt renklerdir (Örn: Kırmızı-Yeşil). Bu renkler yan yana kullanıldığında yüksek kontrast ve enerji yaratır.1

- **Benzer Renkler (Analogous)**: Renk çemberinde yan yana duran ve birbirine yakın olan renklerin seçilmesiyle oluşturulur. Gözü yormayan, sakin ve uyumlu tasarımlar sağlar.6

- **Tek Renkli (Monochromatic)**: Tek bir renk tonunun (hue) farklı doygunluk ve parlaklık değerlerinin kullanılmasıyla oluşturulur. Sınavlarda "renk uyumu için tek renk tonunu kullanan şema" olarak tanımlanır.2

- **Üçlü Renkler (Triadic)**: Renk çemberi üzerinde eşit aralıklarla yer alan üç rengin (bir eşkenar üçgen oluşturacak şekilde) kullanılmasıdır.2

- **Dörtlü Renkler (Tetradic)**: Çember üzerinde iki çift tamamlayıcı rengin kullanılarak bir dikdörtgen oluşturulmasıyla açığa çıkan şemadır. Çok zengin bir renk paleti sunar ancak dengelemek zordur.1

#### 60-30-10 Kuralı

Grafik tasarımında veya iç mimaride üç renk kullanıldığında dengeyi sağlamanın en kolay yolu olarak kabul edilen formüldür. Sınavda bu kuralın oranları sorulur:

- **%60**: Tasarımın ana rengi (baskın renk).
- **%30**: İkincil renk (yardımcı renk).
- **%10**: Vurgu rengi (üçüncü renk, dikkat çekici detaylar için).

Bu oranlar tasarımda hiyerarşi ve görsel konfor sağlar.4

#### Renk Psikolojisi

Renklerin izleyici üzerinde oluşturduğu zihinsel ve duygusal etkiler "Renk Psikolojisi" olarak adlandırılır.5 Sınavda spesifik renk anlamları sorulmaktadır:

- **Kırmızı**: Enerji, savaş, tehlike, güç, istek, sevgi ve aşk ile ilişkilendirilen renktir.6

- **Sıcak ve Soğuk Renkler**: Kırmızı, Sarı ve Turuncu sıcak renkler; Mavi, Yeşil ve Mor soğuk renklerdir. Sınav sorularında "Pembe" genellikle bu sınıflandırmanın dışında (nötr veya bağlama bağlı) veya sıcak/soğuk ayrımında bir çeldirici olarak kullanılmaktadır. "Aşağıdakilerden hangisi sıcak ve soğuk renkler arasında yer almaz?" sorusunun cevabı olarak Pembe verilmiştir.4

- **Birincil Renkler**: Geleneksel sanat teorisine (RYB) atıfta bulunulan sorularda birincil renkler Kırmızı, Sarı ve Mavi olarak kabul edilir.4

## 2. Dijital Görüntülemenin Matematiği: Vektör ve Bitmap

Bir grafik tasarım öğrencisinin, çalıştığı görselin matematiksel yapısını bilmesi hayati önem taşır. Sınavlarda en sık karşılaşılan konulardan biri, piksel tabanlı (bitmap) görseller ile vektör tabanlı görseller arasındaki farklardır.

### 2.1. Piksel ve Bitmap (Raster) Grafikler

Bitmap veya raster grafikler, piksel adı verilen küçük renkli karelerin ızgara (grid) yapısında yan yana gelmesiyle oluşur.

- **Temel Yapı**: Pikseller birleşerek Bitmap resmini oluşturur.5 Her piksel belirli bir renk ve parlaklık bilgisi taşır.
- **Avantaj**: Milyonlarca renk geçişini, gölge detaylarını ve karmaşık dokuları barındırabildiği için fotoğraflar ve dijital boyamalar için idealdir.4
- **Dezavantaj (Ölçekleme Sorunu)**: Bitmap grafiklerin boyutu değiştirildiğinde kalitesi bozulur. Görüntü büyütüldüğünde, yazılım aradaki boşlukları tahmin ederek doldurmaya çalışır (interpolasyon), bu da görüntünün bulanıklaşmasına veya "pikselleşmesine" (kare kare görünmesine) neden olur.4

### 2.2. Vektör Grafikler

Vektör grafikler, piksellerden değil; matematiksel formüllerle tanımlanan çizgi, eğri ve şekillerden (path) oluşur.

- **Çözünürlükten Bağımsızlık**: Sınavların vazgeçilmez sorusudur. Vektör grafikler, çözünürlükten bağımsızdır. Yani bir logo, kartvizit boyutundan bina cephesi boyutuna kadar ne kadar büyütülürse büyütülsün, kalitesi, netliği ve keskinliği asla bozulmaz.2
- **Dosya Boyutu**: Pikselleri tek tek kaydetmek yerine, şeklin matematiksel tanımını (örneğin: "A noktasından B noktasına kırmızı bir çizgi çek") kaydettiği için, dosya boyutları bitmaplere göre çok daha düşüktür.2
- **Kullanım Alanları**: Logo, amblem, tipografi, ikon tasarımı, teknik çizimler, tabela kesim işleri (plotter) için kullanılır.

### 2.3. Çözünürlük (Resolution) Standartları

Çözünürlük, birim alana düşen piksel yoğunluğunu ifade eder.

- **Tanım**: "Piksellerin (noktaların) birbirine ne kadar yakın olduğunu ifade eden kavramdır".1 Pikseller birbirine ne kadar yakınsa, görüntü o kadar keskin olur.
- **Birim Dönüşümü**: Sınavda sorulan teknik bir detay olarak; dijital ölçü birimi olan İnç (Inch), metrik sistemde 2.54 cm'ye karşılık gelir.3

### 2.4. Dosya Formatları ve Özellikleri

Hangi dosya formatının hangi özelliklere sahip olduğu ve hangi amaçla kullanıldığı sınavda belirleyici sorulardandır.

**Tablo 2: Dosya Formatları ve Özellikleri**

| Format | Özellikler ve Sınav Detayları | Kaynak |
|--------|-------------------------------|--------|
| PSD | Adobe Photoshop'un kendi yerel formatıdır. Katmanları, kanalları, yolları saklar. Çalışma dosyasıdır. En yaygın dijital resim çalışma biçimidir. Birden fazla katmanın saklanabildiği formattır. | 1 |
| PNG | Web için geliştirilmiştir. Kayıpsız sıkıştırma kullanır. GIF gibi saydamlığı (transparanlık) destekler ancak GIF'ten farklı olarak milyonlarca rengi barındırabilir (GIF 256 renkle sınırlıdır). JPG kalitesinde olup saydamlık sunması en büyük avantajıdır. | 1 |
| SVG | Vektör tabanlı resimlerin internet standardıdır (XML tabanlı). Corel Draw ve Illustrator gibi vektörel programlar tam destek verir. | 5 |
| CDR | Corel Draw programının yerel dosya uzantısıdır. | 5 |
| XCF | Açık kaynak kodlu GIMP programının yerel dosya formatıdır. | 3 |
| JPEG | Fotoğraflar için standarttır, sıkıştırma yapar ancak veri kaybına yol açar. Saydamlığı desteklemez. | 1 |
| PDF | Belge paylaşımı için standarttır. InDesign, Illustrator ve Photoshop'tan çıktı alınabilir. | 3 |

## 3. Adobe Photoshop CC 2018: Arayüz, Kurulum ve İşleyiş

Sınav sorularının büyük bir kısmı, endüstri standardı olan Adobe Photoshop yazılımının teknik detayları üzerine kuruludur.

### 3.1. Kurulum ve Lisanslama Modeli

Sınavda yazılımın dağıtım modeliyle ilgili güncel bilgiler sorulmaktadır.

- **Kiralama Modeli**: Adobe Photoshop CC (Creative Cloud) sürümüyle birlikte "satın alma" modeli bitmiş, yerine aylık veya yıllık kiralama (abonelik) sistemi gelmiştir.4
- **Deneme Sürümü**: Adobe, kullanıcılara yazılımı denemeleri için 30 günlük (sınav kaynağında bu süre 30 gün olarak belirtilmiştir, güncel Adobe politikaları değişse de sınavda 30 gün cevabı esas alınmalıdır) ücretsiz kullanım hakkı tanır.1 Kurulum öncesinde "Adobe Creative Cloud" masaüstü uygulaması yüklenmelidir.5

### 3.2. Arayüz Elemanları ve Paneller

Photoshop arayüzündeki bileşenlerin yerleşimi ve işlevleri önemlidir.

- **Çalışma Alanı (Workspace)**: Panellerin, pencerelerin ve araç çubuklarının düzenlendiği genel alana verilen isimdir.2
- **Katmanlar Paneli (Layers)**: Tasarımın yönetildiği merkezdir. Kısayolu F7 tuşudur.6
- **Geçmiş Paneli (History)**: Kullanıcının yaptığı işlemleri adım adım kaydeder. Hata yapıldığında önceki adımlara dönmeyi sağlayan, yapılan tüm eylemleri gösteren paneldir.1
- **Araçlar Paneli**: Sol tarafta bulunur. Özelleştirilebilir; az kullanılan araçlar "Ek Araçlar" bölümüne taşınabilir, hazırlanan araç düzeni kaydedilebilir ve başka bilgisayara taşınabilir. "Önceden oluşturulmuş bir araç çubuğu tekrar kullanılamaz" ifadesi sınavda yanlış seçenek olarak sorulur.4
- **Olmayan Paneller**: Sınavda çeldirici olarak sunulan "Düzen" (Layout) veya "Web" adında standart bir Photoshop paneli yoktur. Başlangıç ekranında "Web" diye bir buton yer almaz.3
- **Son Kullanılan Dosyalar**: Başlangıç ekranında görünecek son dosya sayısı, Düzen > Tercihler > Dosya İşleme menüsünden ayarlanabilir (0-100 arası).2

## 4. Operasyonel Araçlar ve Manipülasyon Teknikleri

Photoshop araçları, işlevlerine göre kategorize edilmiştir. Sınavlarda sıkça "Aşağıdakilerden hangisi seçim aracıdır/değildir?" formatında sınıflandırma soruları sorulur.

### 4.1. Araç Sınıflandırma Tablosu

Aşağıdaki tablo, sınav sorularında geçen araçların doğru kategorizasyonunu göstermektedir:

**Tablo 3: Araç Kategorileri**

| Araç Kategorisi | Kapsadığı Araçlar | Kapsamadığı / Yanlış Bilinen Araçlar | İşlev |
|----------------|------------------|-------------------------------------|-------|
| Seçim Araçları | Taşıma (Move), İşaretleme (Marquee), Kement (Lasso), Hızlı Seçim (Quick Selection) | Yavaş Seçim (Uydurma şık), Dilim Aracı | Görüntünün bir bölümünü izole etmek, seçmek ve taşımak. 3 |
| Kırpma ve Dilimleme | Kırpma (Crop), Dilim (Slice), Dilim Seçimi (Slice Select) | Hızlı Seçim, Kement | Görüntüyü boyutlandırmak veya web için parçalara bölmek. 3 |
| Rötuş Araçları | Nokta Düzeltme (Spot Healing), Düzeltme Fırçası (Healing), Yama (Patch), Kırmızı Göz (Red Eye) | Dilim Aracı | Görüntü üzerindeki lekeleri, bozuklukları kaldırmak, kusurları düzeltmek. 4 |
| Boyama ve Düzenleme | Sünger Aracı (Sponge), Boya Kovası | | Renk ve ton düzenlemeleri yapmak. |

### 4.2. Araçların Spesifik İşlevleri

- **Sünger Aracı (Sponge Tool)**: Bir bölgenin renk doygunluğunu (saturation) değiştirmek için kullanılır. Moduna göre rengi canlandırır (doyurur) veya soldurur (griye yaklaştırır).2

- **Hizalama Araçları**: Tasarımda grafiksel öğeleri hassas konumlandırmak için Cetveller (Rulers), Kılavuz Çizgileri (Guides), Izgaralar (Grids) ve Akıllı Kılavuzlar (Smart Guides) kullanılır. "Katmanlar"ın kendisi bir konumlandırma aracı değildir (katmanlar konumlandırılan nesnedir).1

## 5. Katman Yönetimi ve Kompozisyon Prensipleri

Katmanlar (Layers), dijital tasarımın en güçlü özelliğidir. Bir resim içinde birbirinden bağımsız çizimlerin saklanabildiği sanal düzlemler olarak tanımlanır.3

### 5.1. Katman İşlemleri

Katmanlar üzerinde şu işlemler yapılabilir:

- Yeniden boyutlandırma, konum değiştirme (taşıma).
- Birleştirme (Merge), bağlama (Link), çoğaltma (Duplicate).

**Sınav İpucu**: "Katmanların ters çevrilmesi" (Invert layers) standart bir katman yönetim işlemi (örneğin birleştirme veya gruplama gibi) olarak kabul edilmez; bu bir içerik düzenlemesidir.3

### 5.2. Metni Rasterleştirme (Rasterize Type)

Vektörel tabanlı olan yazı katmanının, piksellere dönüştürülerek normal bir resim katmanı haline getirilmesi işlemidir.

**Sonuçları**: Bu işlemden sonra yazı üzerindeki "T" (Text) simgesi kaybolur. Yazının içeriği (harfler, kelimeler) artık düzenlenemez, yazıya yeni harf eklenemez. Yazı artık bir resim gibi silinebilir, boyanabilir veya filtre uygulanabilir hale gelir.1

### 5.3. Hizalama ve Görünürlük

- **Otomatik Hizalama**: "Katmanları Otomatik Hizala" komutu, benzer içeriğe sahip katmanları (örneğin panorama yaparken) analiz ederek hizalar.5
- **Görünürlük**: Katmanlar panelinde, katmanın solundaki Göz ikonu katmanı gizler veya gösterir.2
- **Tam Şeffaflık**: Bir katmanın tamamen görünmez (şeffaf) olması için Opaklık (Opacity) değeri %0 yapılmalıdır.7

## 6. Görsel Efektler ve Filtre Algoritmaları

Photoshop'ta filtreler, görüntülerin piksellerini matematiksel algoritmalarla yeniden düzenleyerek efektler oluşturur.

### 6.1. Filtre Kullanım Kuralları

- **Erişim**: Menü çubuğunda Filtre > Filtre Galerisi yolundan ulaşılır.1
- **Kısıtlamalar**: Bitmap (siyah-beyaz) modundaki ve Dizinlenmiş (Indexed) renkteki resimlere filtre uygulanamaz. Bazı filtreler sadece RGB modunda çalışır.3
- **Geri Alma**: Filtre uygulandıktan sonra beğenilmezse Ctrl+Z veya Düzenle > Geri Al komutu ile işlem geri alınabilir. "Filtreler geri alınamaz" ifadesi yanlıştır.3
- **Akıllı Nesneler**: Filtrelerin kalıcı (destructive) olmaması ve sonradan ayarlarının değiştirilebilmesi için, katman filtre uygulanmadan önce "Akıllı Nesne" (Smart Object) ye dönüştürülmelidir.4

### 6.2. Önemli Filtreler ve İşlevleri

Sınavda her filtrenin ne işe yaradığı spesifik tanımlarla sorulmaktadır:

**Tablo 4: Önemli Filtreler**

| Filtre | İşlev ve Sınav Tanımı | Kaynak |
|--------|---------------------|--------|
| Doku (Texture) | Görüntüye derinlik veya organik bir görünüm kazandırır. | 1 |
| Çapraz Tarama | Görüntünün genel hatlarını koruyarak renkli alanlara kabartma/doku ekler. | 2 |
| Yamalı (Patchwork) | Görüntüdeki hakim renklerin küçük karelere ayrılmış gibi görünmesini sağlar. (Not: Sınavda "küçük çatlaklardan oluşan ağ" tanımı yanlıştır, o "Çatlaklar" filtresidir). | 1 |
| Vitray | Görüntüyü tek renkli bitişik hücrelerden oluşacak şekilde (cam mozaik) boyar. | 1 |
| Uyarlanabilir Geniş Açı | Geniş açılı (balık gözü) merceklerin neden olduğu bombeli bozulmaları düzeltir. | 1 |
| Sıvılaştırma (Liquify) | Görüntüyü itme, çekme, büzme, şişirme, döndürme yoluyla deforme eder. "İleri Çarpıtma" aracı pikselleri ileri iter. | 6 |
| Ufuk Noktası | Perspektif düzlemler tanımlayarak, perspektife uygun klonlama ve boyama sağlar. | 1 |

## 7. Kritik Klavye Kısayolları ve Komutlar

Profesyonel kullanımda hız sağlayan kısayollar, sınavın ezber gerektiren ancak puan getiren önemli bir kısmıdır.

**Tablo 5: Klavye Kısayolları**

| İşlem | Kısayol / Menü Yolu |
|-------|-------------------|
| Yeni Katman Oluştur | Shift + Ctrl + N 1 |
| Cetvelleri Aç/Kapa | Ctrl + R (Rulers) 1 |
| Geri Al (Undo) | Ctrl + Z 3 |
| Uyarlanabilir Geniş Açı | Alt + Shift + Ctrl + A 5 |
| Katmanlar Panelini Aç | F7 6 |
| Kılavuzları Temizle | Görünüm > Kılavuzları Temizle (Cetvel çizgilerini ekrandan siler) 2 |
| Yığın İşleme (Batch) | Dosya > Otomatikleştir > Yığın (Birden fazla resmi aynı anda boyutlandırmak için) 1 |
| CMYK Dönüşümü | Görüntü > Mod > CMYK (Image > Mode > CMYK) 5 |

## 8. Sektörel Yazılım Ekosistemi

Sınav, sadece Photoshop bilgisiyle sınırlı kalmayıp, diğer grafik yazılımlarının kullanım alanlarını ve özelliklerini de kapsamaktadır.

- **Adobe InDesign**: Çok sayfalı mizanpaj programıdır. Gazete, dergi, kitap ve broşür tasarımında kullanılır. Word ve Excel'den veri alabilir. Çıktı formatları PDF, EPUB ve SWF'dir. Açık kaynak kodlu değildir; Adobe'nin ticari yazılımıdır.3

- **GIMP**: Photoshop'un ücretsiz ve açık kaynak kodlu alternatifidir. Piksel tabanlıdır. XCF formatını kullanır. Windows, Mac ve Linux işletim sistemlerinin hepsinde çalışır (Sınavda "desteklemez" denilirse yanlıştır).3

- **Vektörel Çizim**: Corel Draw ve Adobe Illustrator, vektör tabanlı olmaları bakımından birbirinin rakibidir. Corel Draw CDR, Illustrator AI formatını kullanır ancak ikisi de web standardı olan SVG formatını destekler.5

