# Adobe Photoshop 2025 Görüntü İşleme ve Manipülasyon Stratejileri: Akademik Müfredat Analizi ve Kapsamlı Sınav Hazırlık Raporu

## Yönetici Özeti ve Müfredat Bağlamı

Dijital görüntü işleme teknolojilerinin evrimi, Adobe Photoshop 2025 sürümünün piyasaya sürülmesiyle, geleneksel raster tabanlı manipülasyon tekniklerinin gelişmiş üretken yapay zeka (Generative AI) ile bütünleştiği kritik bir dönemece ulaşmıştır. Bu rapor, Atatürk Üniversitesi Grafik Tasarımı Bölümü müfredatında yer alan "Ünite 9: Resim Üzerinde İşlemler" modülünün eksiksiz bir teknik analizini sunmakta, aynı zamanda bu temel kaynak materyali, akademik sınavlar ve Adobe Sertifikalı Profesyonel (ACP) sınav standartlarıyla uyumlu, endüstriyel düzeydeki teknik bilgilerle sentezlemektedir.

Bu analizin temel amacı, müfredatta sunulan operasyonel çerçeveleri—temel çözünürlük yönetiminden karmaşık perspektif düzeltmelerine ve yapay zeka destekli genişletmelere kadar—parçalarına ayırarak derinlemesine incelemektir. Sağlanan ders materyali ve genişletilmiş araştırma verileri ışığında, öğrencilerin ve profesyonellerin ustalaşması gereken beş temel yetkinlik alanı belirlenmiştir: görüntü çözünürlüğü ve boyutlandırma algoritmaları, kırpma ve perspektif restorasyonu, geometrik dönüşümler, histogram tabanlı renk/ton yönetimi ve Bağlamsal Görev Çubuğu (Contextual Task Bar) üzerinden yürütülen yapay zeka iş akışları.

Bu rapor, basit bir özetin ötesine geçerek, işlemlerin arkasındaki matematiksel ve algoritmik mekanizmaları incelemektedir. Örneğin, yeniden örnekleme (resampling) yöntemleri arasındaki enterpolasyon farkları veya histogram eşitlemenin sinyal işleme prensipleri gibi konular, sınav başarısı için kritik olan neden-sonuç ilişkileriyle birlikte ele alınmıştır. Aşağıdaki bölümler, PDF içeriğindeki teorik bilgileri, araştırma verilerinden elde edilen pratik endüstri standartlarıyla birleştirerek, hem akademik sınavlara hem de profesyonel sertifikasyonlara yönelik nihai bir başvuru kaynağı oluşturmaktadır.

## 1. Dijital Görüntülemenin Temelleri: Renk Bilimi ve Yapılandırma

Herhangi bir dijital grafik projesinin başlatılması, hedef medyanın fiziksel ve dijital kısıtlamalarının derinlemesine anlaşılmasını gerektirir. Müfredat, dijital ekran gösterimi ile fiziksel baskı arasındaki kritik ayrımı vurgulamakta ve bu ikiliğin, "Yeni Belge" oluşturma aşamasında renk modları ve çözünürlük ayarlarının seçimini nasıl dikte ettiğini açıklamaktadır.

### 1.1 Renk Modlarının Fiziği ve Yönetimi: RGB ve CMYK Paradoksu

Hem ders notlarında hem de harici sertifikasyon sınavlarında sürekli karşılaşılan en temel kavram, toplamsal (additive) ve çıkarımsal (subtractive) renk modelleri arasındaki ayrımdır. RGB ve CMYK arasındaki seçim, yalnızca bir menü tercihi değil, ışık fiziği ve pigment kimyası arasındaki temel bir çatışmanın yönetimidir.

#### 1.1.1 Toplamsal Model (RGB) ve Dijital Işık

RGB modeli, monitörler, mobil ekranlar ve projektörler gibi ışık yayan cihazlara özgüdür. Bu modelde renk, siyah bir boşluğa (vakum) ışık eklenerek oluşturulur. Kırmızı, Yeşil ve Mavi ışık tam yoğunlukta (8-bitlik bir kanalda 255, 255, 255 değerlerinde) birleştirildiğinde, sonuç saf beyazdır.

*   **Müfredat Uygulaması:** PDF belgesi, dijital ortamlar (Web, Mobil, Film ve Video) için tasarlanan görsellerin, ekranların sunabileceği tam görünür spektrumun (gamut) kullanılabilmesi için mutlaka RGB renk modunda çalışılması gerektiğini açıkça belirtmektedir.
*   **Teknik Derinlik ve Sınav Bilgisi:** Sınavlarda sıklıkla sorulan bir detay, RGB çalışma uzayları arasındaki farktır. sRGB, web ve mobil cihazlarda tutarlılık için endüstri standardı iken, Adobe RGB (1998) daha geniş bir gamut sunarak baskıya dönüştürülecek fotoğraflar için daha fazla renk verisi saklar. Ancak, geniş gamutlu bir görselin (örneğin ProPhoto RGB) sRGB bir ekranda yönetilmeden görüntülenmesi, renklerin soluk görünmesine neden olabilir; bu, renk yönetimi zincirinin anlaşılmasını gerektiren bir sınav konusudur.

#### 1.1.2 Çıkarımsal Model (CMYK) ve Pigment Sınırlamaları

Buna karşılık, CMYK, ofset baskı ve fiziksel çoğaltma standardıdır. Işık emilimi prensibine dayanır. Kağıt ışığı yansıtır; mürekkep ise bu yansımadan belirli dalga boylarını çıkarır (emer). Camgöbeği (Cyan) kırmızı ışığı, Macenta (Magenta) yeşil ışığı ve Sarı (Yellow) mavi ışığı emer. Teorik olarak C, M ve Y'nin karışımı siyahı oluşturmalıdır, ancak mürekkep safsızlıkları nedeniyle bu karışım genellikle çamurlu bir kahverengi verir. Bu nedenle, kontrastı artırmak, metin keskinliğini sağlamak ve mürekkep yükünü azaltmak için "Key" (Anahtar/Siyah) plakası eklenir.

*   **Müfredat Uygulaması:** Baskı projeleri için PDF, belgenin CMYK moduna dönüştürülmesini tavsiye eder. Bu, ekranda görülen parlak neon renklerin (özellikle saf maviler ve parlak yeşiller), CMYK mürekkeplerinin kimyasal sınırlamaları nedeniyle basılamayacağı gerçeğiyle yüzleşmeyi sağlar. Photoshop, bu renkleri "gamut dışı" olarak işaretler ve en yakın basılabilir karşılığa indirger.
*   **Kritik Sınav Uyarısı:** Önemli bir sınav tuzağı, dönüştürme zamanlamasıyla ilgilidir. RGB'den CMYK'ya dönüşüm yıkıcı (destructive) bir işlemdir; gamut dışı renk verileri kalıcı olarak kaybolur. Profesyonel iş akışı ve doğru sınav cevabı, görselin mümkün olduğunca uzun süre RGB'de tutulmasını, düzenlemelerin bu geniş alanda yapılmasını ve yalnızca nihai çıktı aşamasında CMYK'ya çevrilmesini veya "Soft Proofing" (Görünüm > Prova Ayarları) kullanılarak baskı simülasyonu yapılmasını öngörür.

**Tablo 1: RGB ve CMYK Arasındaki Temel Farklar**

| Özellik | RGB (Kırmızı, Yeşil, Mavi) | CMYK (Cyan, Magenta, Yellow, Key) |
| :--- | :--- | :--- |
| **Model Türü** | Toplamsal (Işık Kaynaklı) | Çıkarımsal (Pigment/Yansıma Kaynaklı) |
| **Beyaz Nokta** | Tüm renklerin maksimum birleşimi (255, 255, 255) | Kağıdın rengi (0% mürekkep örtücülüğü) |
| **Siyah Nokta** | Işığın yokluğu (0, 0, 0) | Mürekkeplerin karışımı (Rich Black) veya %100 K |
| **Gamut Genişliği** | Geniş (Milyonlarca renk, parlak neonlar dahil) | Dar (Mürekkep kimyası ile sınırlı, mat renkler) |
| **Kullanım Alanı** | Web, Video, UI/UX, Mobil Uygulamalar | Ofset Baskı, Dergi, Ambalaj, Gazete |
| **Dosya Boyutu** | Genellikle daha küçük (3 kanal) | Genellikle daha büyük (4 kanal) |

### 1.2 Çözünürlük Matematiği ve Bit Derinliği

Müfredat, görüntü çözünürlüğünün kullanım amacına göre optimize edilmesini şart koşar. Çözünürlük, doğrusal inç başına düşen piksel sayısı (PPI - Pixels Per Inch) ile tanımlanır.

*   **Ekran Çözünürlüğü:** Tarihsel standartlar web grafikleri için 72 ppi veya 96 ppi'yi referans alsa da, PDF'de belirtildiği gibi modern "Retina" veya yüksek yoğunluklu ekranlar (HiDPI), keskinlik için daha yüksek piksel yoğunlukları gerektirir. Ancak, web için temel mantık, piksel boyutlarıdır (örneğin 1920x1080). Bir görselin 72 ppi veya 300 ppi olarak etiketlenmesi, web tarayıcısındaki görüntülenme boyutunu değiştirmez; tarayıcılar sadece piksel ızgarasını (grid) okur.
*   **Baskı Çözünürlüğü:** Profesyonel baskı standardı 300 ppi'dir. Bu değer, standart okuma mesafesinde piksellerin insan gözüyle ayırt edilemeyecek kadar küçük olmasını sağlar. 72 ppi'lik bir görseli basmak, genellikle "pikselleşme" veya merdiven etkisi (aliasing) adı verilen görsel bozulmalara yol açar. Sınav sorularında, *"Web için hazırlanan 600x400 piksellik bir görsel baskıya gönderildiğinde neden bulanık çıkar?"* sorusunun cevabı, fiziksel boyutun inç başına düşen yetersiz piksel sayısı nedeniyle genişlemesidir.

**Bit Derinliği (Bit Depth):** PDF'de 8-bit, 16-bit ve 32-bit kanallardan bahsedilmektedir.
*   **8-bit/kanal:** Kanal başına 256 ton seviyesi ($2^8$) sağlar. RGB modunda bu, yaklaşık 16.7 milyon renk demektir. JPEG formatı ve çoğu nihai çıktı için standarttır.
*   **16-bit/kanal:** Kanal başına 65.536 ton seviyesi sunar. İnsan gözü bu kadar fazla rengi ayırt edemese de, 16-bit modunda çalışmak, histogramı genişletme veya ağır eğri (Curve) manipülasyonları gibi düzenlemeler sırasında "banding" (renk şeritlenmesi veya posterizasyon) oluşumunu engeller. Sınav bağlamında, *"Neden 16-bit modunda çalışmalıyız?"* sorusunun cevabı, veri kaybını ve şeritlenmeyi önleyerek düzenleme esnekliği sağlamaktır.

## 2. Algoritmik Görüntü Boyutlandırma ve Örnekleme (Resampling)

Müfredatın ve sınav kapsamının önemli bir bölümü "Görüntü Boyutu" (Image Size) penceresindeki işlemlere odaklanmaktadır. Bir Photoshop uzmanı için Yeniden Boyutlandırma (Resizing) ve Yeniden Örnekleme (Resampling) arasındaki farkı anlamak hayati önem taşır. Bu ayrım, PDF'deki teknik detaylarla araştırma verilerindeki algoritmik açıklamaların sentezlenmesini gerektirir.

### 2.1 Yeniden Boyutlandırma vs. Yeniden Örnekleme

*   **Yeniden Boyutlandırma (Örnekleme Olmadan Ölçekleme):** Bu işlem, dosyadaki toplam piksel sayısını değiştirmeden, görselin fiziksel baskı boyutlarını (inç veya cm) ve çözünürlük değerini (PPI) değiştirir. Veri yaratılmaz veya yok edilmez; sadece mevcut piksellerin ne kadar sıkışık veya seyrek basılacağı belirlenir. Örneğin, 3000 piksel genişliğindeki bir görsel 300 ppi'de 10 inç baskı verir. Eğer "Yeniden Örnekle" (Resample) seçeneği kapalıyken genişlik 20 inç yapılırsa, çözünürlük otomatik olarak 150 ppi'ye düşer. Pikseller büyür, ancak sayıları artmaz.
*   **Yeniden Örnekleme (Resampling):** Bu işlem, görselin piksel boyutlarını değiştirir (ve dolayısıyla dosya boyutunu etkiler). Yazılımın, yeni piksellerin rengini tahmin etmesi (interpolation - büyütme/upsampling) veya hangi piksellerin atılacağına karar vermesi (küçültme/downsampling) gerekir. Bu işlem, görsel kalitesini doğrudan etkileyen algoritmik tahminlere dayanır.

### 2.2 Enterpolasyon Algoritmaları ve Kullanım Senaryoları

PDF belgesi, "Görüntü Boyutu" penceresindeki "Yeniden Örnekle" seçeneklerinin (Otomatik, Ayrıntıları Koru, bikübik vb.) önemini vurgulamaktadır. Araştırma verileri, bu algoritmaların teknik işleyişini ve hangi senaryoda hangisinin seçilmesi gerektiğini detaylandırır.

#### 2.2.1 Otomatik (Automatic)
Bu ayar, Photoshop'un yapılan işlemin büyütme mi yoksa küçültme mi olduğunu algılayarak en uygun yöntemi kendisinin seçmesini sağlar. Photoshop 2025'te bu, genellikle büyütme için "Ayrıntıları Koru 2.0" ve küçültme için "Bikübik Daha Keskin" yöntemine varsayılan olarak ayarlanır.

#### 2.2.2 Ayrıntıları Koru 2.0 (Preserve Details 2.0)
Müfredatta "Ayrıntıları Koru (genişletme)" olarak geçen ve Photoshop 2025 ile gelen bu özellik, yapay zeka destekli derin öğrenme modellerini kullanır. Geleneksel yöntemlerin aksine, pikselleri sadece matematiksel ortalamayla çoğaltmaz; görseldeki dokuları (örneğin saç, deri gözenekleri) tanıyarak yeniden oluşturur. Bu seçenek aktifken kullanılabilir hale gelen "Parazit Azaltma" sürgüsü, büyütme sırasında oluşabilecek dijital gürültüyü temizler. Bu, %200 veya %300 gibi büyük ölçekli büyütmeler için tartışmasız en iyi seçenektir.

#### 2.2.3 Bikübik Varyasyonları (Bicubic Variants)
*   **Bikübik Daha Yumuşak (genişletme):** Büyütme işlemleri için tasarlanmıştır. Çevreleyen piksellerin ağırlıklı ortalamasını alarak yeni pikseller oluşturur. Kenarları yumuşatarak pikselleşmeyi önler ancak "Ayrıntıları Koru 2.0" kadar keskin detay sunamaz. Yumuşak geçişli degradeler veya bulanık arka planlar için tercih edilebilir.
*   **Bikübik Daha Keskin (azaltma):** Küçültme işlemleri için idealdir. Bir görsel küçültüldüğünde detaylar birbirine karışarak bulanıklaşabilir. Bu algoritma, küçültme işlemi sırasında otomatik bir keskinleştirme (sharpening) filtresi uygulayarak kenar kontrastını korur. Web için thumbnail (küçük resim) hazırlarken en doğru seçimdir.

#### 2.2.4 En Yakın Komşu (Nearest Neighbor)
Bu, en basit ve en hızlı algoritmadır. Çevreleyen piksellerin ortalamasını almak yerine, mevcut pikselleri kopyalar. Fotoğraflar için kullanıldığında testere dişi (aliasing) görünümüne neden olduğu için genellikle kaçınılır. Ancak, piksel sanatı (pixel art), ekran görüntüleri (screenshot), QR kodları veya keskin kenarlı vektör benzeri grafiklerin boyutlandırılmasında tek doğru seçenektir. Bulanıklık yaratmadan keskin, bloklu yapıyı korur.

**Tablo 2: Sınav Senaryoları için Önerilen Algoritmalar**

| Senaryo | Önerilen Algoritma | Neden? |
| :--- | :--- | :--- |
| **Büyük Ölçekli Fotoğraf Büyütme** | Ayrıntıları Koru 2.0 | Yapay zeka ile doku üretimi ve gürültü azaltma sağlar. |
| **Web İçin Küçültme (Thumbnail)** | Bikübik Daha Keskin | Küçültme kaynaklı bulanıklığı telafi eder. |
| **Piksel Sanatı / QR Kod Büyütme** | En Yakın Komşu | Kenarları bulanıklaştırmadan sert hatları korur. |
| **Yumuşak Geçişli Degrade Büyütme** | Bikübik Daha Yumuşak | Renk geçişlerinde bantlaşmayı (banding) önler. |

## 3. Photoshop 2025'te Üretken Yapay Zeka Paradigması

Sağlanan PDF, Photoshop müfredatında devrim niteliğinde bir değişikliğe işaret etmektedir: Manuel rötuşlamadan yapay zeka destekli kompozisyona geçiş. Bu yeni paradigma, Bağlamsal Görev Çubuğu (Contextual Task Bar) ve Adobe Firefly motoru etrafında şekillenmektedir.

### 3.1 Bağlamsal Görev Çubuğu ve İş Akışı Optimizasyonu

Kullanıcı deneyimini hızlandırmak için tasarlanan bu kayan menü, tuval üzerinde aktif olan araca veya seçime göre dinamik olarak değişir.

*   **Dinamik Davranış:** Eğer bir özne seçiliyse, çubuk "Üretken Dolgu" (Generative Fill) veya "Seçimi Ters Çevir" seçeneklerini sunar. Hiçbir seçim yoksa, "Özneyi Seç" veya "Arka Planı Kaldır" gibi genel komutları önerir.
*   **Sınav Bilgisi:** Çubuğun konumu varsayılan olarak seçimin altına yapışır ancak kullanıcı tarafından ekranın sabit bir noktasına "iğnelenebilir" (Pin bar position). Sınavlarda, bu çubuğun kaybolması durumunda "Pencere > Bağlamsal Görev Çubuğu" menüsünden tekrar açılabileceği sorulabilir.

### 3.2 Üretken Genişletme (Generative Expand)

PDF'de özellikle vurgulanan bu özellik, Kırpma Aracı (Crop Tool) ile entegre çalışır.

*   **Mekanizma:** Kırpma Aracı seçiliyken, üstteki seçenekler çubuğunda (veya Bağlamsal Görev Çubuğu'nda) "Doldur" (Fill) seçeneği "Üretken Genişletme" olarak ayarlanır. Kullanıcı tuval tutamaçlarını görsel sınırlarının dışına sürüklediğinde, oluşan boşluk şeffaf veya beyaz kalmaz; Firefly yapay zekası, görselin mevcut piksellerini analiz ederek sahneyi tutarlı bir şekilde devam ettirir. Örneğin, yarım kalmış bir dağ manzarasını tamamlayabilir veya kesik bir portreyi tüm vücuda tamamlayabilir.
*   **İstem (Prompt) Kullanımı:** Kullanıcı, genişletilen alan için özel bir istem (örneğin "gün batımı gökyüzü ekle") girebilir veya kutuyu boş bırakarak yapay zekanın bağlamsal olarak en uygun içeriği üretmesini sağlayabilir.
*   **Teknik Kısıtlamalar:** Üretken Genişletme ve Dolgu işlemleri, Adobe'nin bulut sunucularıyla iletişim gerektirdiği için aktif bir internet bağlantısına ihtiyaç duyar. Ayrıca, bu işlemler kullanıcının abonelik planına bağlı olarak "Üretken Krediler" (Generative Credits) tüketir.

### 3.3 Üretken Dolgu ve Arka Plan Manipülasyonu

*   **Arka Planı Kaldır (Remove Background):** PDF'de gösterilen "Hızlı İşlem" (Quick Action), yapay zeka kullanarak görseldeki ana özneyi (insan, araba, ürün vb.) algılar ve arka planı maskeler. Bu işlem yıkıcı değildir; bir katman maskesi oluşturur. Sınav soruları, maskenin kenarlarının (özellikle saç gibi ince detaylarda) nasıl iyileştirilebileceğini (Seç ve Maskele çalışma alanı) sorabilir.
*   **Üretken Dolgu (Generative Fill):** Seçim araçlarıyla (Kement, Dikdörtgen İşaretleme vb.) belirlenen bir alana nesne eklemek veya çıkarmak için kullanılır.
    *   **Nesne Çıkarma:** İstenmeyen bir nesneyi seçip istem kutusunu boş bırakarak "Oluştur"a basmak, Photoshop'un o alanı çevreleyen doku ve ışıkla doldurmasını sağlar (gelişmiş İçeriğe Uygun Dolgu).
    *   **Nesne Ekleme:** "Eski model araba" veya "kırmızı şemsiye" gibi metin komutları girilerek, sahnenin perspektifine ve ışıklandırmasına uygun fotorealistik nesneler eklenebilir.

## 4. Kompozisyonel Geometri: Kırpma, Düzleştirme ve Dönüştürme

Görüntü çerçeveleme ve perspektif düzeltme, grafik tasarımın temel taşlarıdır. PDF, bu işlemlerin yalnızca estetik değil, teknik doğruluğu sağlama araçları olduğunu belirtir.

### 4.1 Kırpma Aracı (Crop Tool) ve Düzeltme İşlevleri

Kırpma aracı, basitçe görselin kenarlarını atmaktan daha fazlasını yapar.

*   **Düzleştir (Straighten):** Eğri çekilmiş ufuk çizgilerini düzeltmek için kullanılır. Seçenekler çubuğundaki su terazisi simgesi (Düzleştir) seçilerek, görsel üzerindeki referans bir hat (örneğin deniz yüzeyi veya bina kenarı) boyunca çizgi çekilir. Photoshop, görseli bu çizgiye göre otomatik olarak döndürür ve tuvali yeniden boyutlandırır.
*   **İçeriğe Uygun Kırpma (Content-Aware Crop):** Bir görsel düzleştirildiğinde veya döndürüldüğünde, köşelerde şeffaf boşluklar oluşur. Eskiden bu boşlukları yok etmek için görselin içine doğru kırpma yapılırdı (veri kaybı). "İçeriğe Uygun" seçeneği işaretlendiğinde, Photoshop bu boş köşeleri otomatik olarak sentezlediği dokularla doldurur, böylece orijinal kompozisyon boyutu korunur.
*   **Perspektif Kırpma (Perspective Crop):** Bu araç, açılı çekilmiş bir nesneyi (örneğin duvardaki bir tablo veya bina cephesi) tam karşıdan çekilmiş gibi düzeltmek için kullanılır. Kullanıcı, nesnenin dört köşesine uyan bir ızgara çizer; işlem onaylandığında, yazılım köşeleri "çekerek" görüntüyü düzlemsel bir dikdörtgene dönüştürür.

### 4.2 Serbest Dönüştürme ve Deformasyon

Katmanların geometrisini değiştirmek için "Düzenle > Serbest Dönüştürme" (Ctrl+T) komutu kullanılır.

*   **En-Boy Oranı:** PDF'de Shift tuşunun önemi vurgulanmıştır. Ancak, Photoshop 2019 ve sonrası sürümlerde varsayılan davranış değişmiştir: Artık orantılı ölçekleme varsayılandır; Shift tuşuna basmak orantıyı bozar. Sınavda hangi sürümün sorulduğuna dikkat edilmelidir, ancak PDF 2025 sürümünü referans aldığı için güncel davranışı (Shift basılı tutulursa oran bozulur, tutulmazsa korunur) veya PDF'in eski alışkanlıkları referans verip vermediğini (Shift orantıyı korur ifadesi varsa eski davranış) kontrol etmek gerekir. *PDF metninde "Shift tuşuna basılı tutulursa resmin en boy oranı sabit kalır" ifadesi yer almaktadır.* Bu, Photoshop'un "eski" davranışını (Legacy Transform) referans alan bir anlatımdır ve sınavda bu bilgiye sadık kalınmalıdır.
*   **Perspektif ve Deforme Et (Distort):** Bir görseli, eğik duran bir laptop ekranına yerleştirmek gibi işlemler için "Deforme Et" veya "Perspektif" modları kullanılır. Bu modlar, köşe tutamaçlarının birbirinden bağımsız hareket etmesine izin vererek görselin 3 boyutlu uzayda bükülmesini simüle eder.

## 5. Renk ve Ton Bilimi: Histogramlar ve Ayarlamalar

Ünite 9, fotoğrafik iyileştirmenin kalbi olan renk ve ışık düzenlemelerine geniş yer ayırmaktadır. Müfredat, pikselleri doğrudan değiştiren statik ayarlamalar ile maskelenebilen ve geri alınabilen Ayarlama Katmanları (Adjustment Layers) arasındaki farkı öğretmektedir.

### 5.1 Histogram Analizi: Görselin İstatistiksel DNA'sı

Sınav hazırlığının en teknik kısımlarından biri Histogram grafiğini okumaktır. Bu grafik, piksellerin (Dikey Eksen) parlaklık seviyelerine (Yatay Eksen, 0-255) göre dağılımını gösterir.

*   **Grafik Yorumlama:** Grafiğin sol tarafı gölgeleri (siyahlar), sağ tarafı vurguları (beyazlar), orta kısım ise orta tonları temsil eder.
*   **Sola Dayalı Grafik:** "Low Key" veya karanlık bir görüntüyü ifade eder. Eğer grafik sol duvara tırmanıyorsa (clipping), gölgelerde detay kaybı var demektir (saf siyah).
*   **Sağa Dayalı Grafik:** "High Key" veya çok parlak bir görüntü. Sağ duvara tırmanma, "patlamış" (detaysız) beyaz alanları gösterir.
*   **Taraklı Yapı (Combing):** Histogramda dikey boşlukların oluşması, görselin aşırı düzenlendiğini ve bazı ton seviyelerinde veri kaybı yaşandığını gösterir.

### 5.2 Düzeyler (Levels) ve Eğriler (Curves)

Ton kontrolü için kullanılan bu iki araç arasındaki farklar sınavda belirleyicidir.

*   **Düzeyler:** Üç kontrol noktası sunar: Siyah Nokta, Beyaz Nokta ve Gama (Orta Ton). Siyah sürgüsünü sağa çekmek, koyu grileri siyaha dönüştürerek kontrastı artırır. Orta ton sürgüsü, uç noktaları kırpmadan parlaklığı ayarlar.
*   **Eğriler:** Sonsuz kontrol noktası sunar ve en hassas araçtır.
    *   **S-Eğrisi:** Eğrinin gölgeler bölgesini aşağı çekip, vurgular bölgesini yukarı itmek "S" şekli oluşturur; bu, kontrastı artırmanın en profesyonel yoludur.
    *   **Sınav Detayı:** "Hangi araç ton aralığının belirli bir bölgesini (örneğin çeyrek tonları) diğerlerini etkilemeden değiştirme imkanı verir?" sorusunun cevabı Eğriler'dir.

### 5.3 Psikoradyometrik Renk Ayarları: Canlılık ve Doygunluk

Renk yoğunluğunu artırmak için kullanılan iki terim arasındaki nüans, profesyonel bir sınav konusudur.

*   **Doygunluk (Saturation):** Tüm renklerin yoğunluğunu doğrusal olarak artırır. Bu, zaten doygun olan renklerin "patlamasına" ve cilt tonlarının (turuncu/kırmızı) doğal olmayan bir görünüme bürünmesine neden olabilir.
*   **Canlılık (Vibrance):** "Akıllı doygunluk" olarak bilinir. Sadece soluk (doygunluğu düşük) renkleri artırır, zaten doygun olan renkleri korur. En önemlisi, cilt tonlarını (skin tones) koruyacak şekilde programlanmıştır. Portre fotoğraflarında Doygunluk yerine Canlılık kullanılması önerilir.

### 5.4 Siyah-Beyaz ve Diğer Ayarlamalar

*   **Siyah-Beyaz (Black & White):** Görüntüyü gri tonlamaya çevirmek için "Doygunluğu Azalt" (Desaturate) yerine bu özellik tercih edilmelidir. Çünkü bu araç, renk kanallarının (Kırmızı, Yeşil, Mavi) griye dönüşürken ne kadar koyu veya açık olacağını kontrol etme imkanı verir (örneğin, mavi gökyüzünü karartıp kırmızı çiçeği parlatmak).
*   **Gölgeler/Açık Tonlar (Shadows/Highlights):** Ters ışıkta kalmış (silüet olmuş) nesneleri kurtarmak veya aşırı parlak gökyüzünü dengelemek için kullanılan, yerel kontrast algoritmasına sahip bir kurtarma aracıdır.

## 6. Sınav Simülasyonu ve Kritik Değerlendirme Soruları

Aşağıdaki bölüm, müfredat içeriği ve araştırma verilerinden derlenen, sınavda çıkması muhtemel senaryo tabanlı soruları ve teknik analizlerini içermektedir.

### 6.1 Senaryo Tabanlı Soru Analizleri

> [!NOTE]
> Bu sorular, neden-sonuç ilişkisini test etmek için tasarlanmıştır.

1.  **Konu: Bağlamsal Görev Çubuğu ve Yapay Zeka**
    *   **Soru:** Bir kullanıcı, Kırpma Aracı ile tuvalin sağ tarafını genişletmiştir. Boş kalan alanı, görselin devamı niteliğinde bir manzarayla doldurmak için hangi özellik kullanılmalıdır?
    *   **Cevap:** Üretken Genişletme (Generative Expand).
    *   **Analiz:** Öğrenci, "İçeriğe Uygun Dolgu"nun sadece doku tekrarı yaptığını, ancak "Üretken Genişletme"nin (Contextual Task Bar üzerinden) yeni ve anlamlı içerik (dağlar, bulutlar vb.) ürettiğini bilmelidir.

2.  **Konu: Çözünürlük ve Örnekleme**
    *   **Soru:** Web için hazırlanmış 72 ppi'lik bir görselin, baskı için 300 ppi kalitesinde, boyutları 4 kat artırılacak şekilde büyütülmesi gerekmektedir. En az bozulma ve en yüksek doku kalitesi için hangi enterpolasyon yöntemi seçilmelidir?
    *   **Cevap:** Ayrıntıları Koru 2.0 (Preserve Details 2.0).
    *   **Analiz:** Eski standart "Bikübik Daha Yumuşak" idi, ancak 2025 müfredatı yapay zeka destekli Ayrıntıları Koru 2.0'ı en iyi büyütme algoritması olarak işaretlemektedir.

3.  **Konu: Renk Modları**
    *   **Soru:** RGB modundaki bir fotoğrafta görülen parlak elektrik mavisi, CMYK moduna çevrildiğinde neden matlaşır ve grileşir?
    *   **Cevap:** Renk, CMYK renk uzayının gamut (kapsama alanı) dışındadır.
    *   **Analiz:** CMYK mürekkepleri, RGB ışığının üretebildiği parlaklık seviyelerine fiziksel olarak ulaşamaz. Bu bir hata değil, fiziksel bir kısıtlamadır.

4.  **Konu: Histogram Okuma**
    *   **Soru:** Düzeyler (Levels) panelinde, Girdi Beyaz Sürgüsünü (sağdaki üçgen) sola doğru kaydırmak görselde nasıl bir etki yaratır?
    *   **Cevap:** Açık gri tonlarını saf beyaza (255) dönüştürerek görselin parlaklığını ve açık tonlardaki kontrastı artırır.
    *   **Analiz:** Beyaz noktasını içeri çekmek, tonal aralığı daraltır ve dinamik aralığı genişletir.

5.  **Konu: Dönüştürme Araçları**
    *   **Soru:** Bir binanın aşağıdan yukarıya doğru çekilen fotoğrafında oluşan "Keystone" etkisini (binanın yukarı doğru daralması) düzeltmek için hangi yöntem en uygundur?
    *   **Cevap:** Perspektif Kırpma (Perspective Crop) veya Dönüştür > Perspektif (Perspective) komutu.
    *   **Analiz:** Bu işlem, paralel olması gereken dikey çizgileri düzelterek mimari doğruluğu sağlar.

### 6.2 Pratik Çalışma Önerileri

*   **"Görünmez Adam" Egzersizi:** Bir fotoğraftaki kişiyi "Özneyi Seç" ile seçin. Seçimi ters çevirin. Arka planı "Üretken Dolgu" ile değiştirin (örneğin "Mars yüzeyi"). Ardından tekrar kişiyi seçip kıyafetlerini değiştirmek için bir istem girin. Bu, seçim, ters çevirme ve istem mühendisliği becerilerini test eder.
*   **Perspektif ve Genişletme:** Eğik ufuk çizgisine sahip bir bina fotoğrafı bulun. Önce Kırpma aracındaki "Düzleştir" ile ufku düzeltin. Ardından "Perspektif Kırpma" ile binayı dik hale getirin. Düzeltme sonucu kenarlarda oluşan boşlukları "Üretken Genişletme" ile doldurun.
*   **Baskı Hazırlığı Simülasyonu:** Dijital bir fotoğrafı (RGB) açın. Görüntü Boyutu'na gidin. "Yeniden Örnekle"yi kapatın ve çözünürlüğü 300 ppi yapın; baskı boyutunun (cm) nasıl küçüldüğünü gözlemleyin. Ardından "Görünüm > Prova Ayarları" ile CMYK baskı simülasyonunu açın ve renklerdeki solmayı (gamut uyarısı) inceleyin.

## 7. Sonuç

Grafik Tasarımı müfredatının 9. Ünitesi, dijital sanatlar endüstrisindeki geniş çaplı dönüşümün bir mikrokozmosudur. Bu ünite, öğrencilerden iki zıt yeteneği aynı anda sergilemelerini talep etmektedir: Bir yanda pikselleri, çözünürlüğü ve renk uzaylarını manuel olarak yönetebilen teknik hassasiyet; diğer yanda yapay zeka destekli üretken araçları (Firefly, Generative Fill) kullanarak yaratıcı iş akışlarını hızlandırabilen adaptasyon yeteneği.

Sınav başarısı, bir aracın sadece "nerede" olduğunu bilmeye değil, "neden" kullanıldığını anlamaya bağlıdır. Kırpma Aracının sadece görseli kesmek için değil, aynı zamanda tuvali yapay zeka ile genişletmek veya perspektifi düzeltmek için kullanıldığını bilmek gereklidir. Benzer şekilde, "Canlılık" ayarının "Doygunluk"tan farkının cilt tonlarını koruması olduğunu kavramak, profesyonel bir operatörü amatörden ayıran temel bir bilgidir.

Enterpolasyon algoritmalarına (Sert kenarlar için En Yakın Komşu, Büyütme için Ayrıntıları Koru), renk fiziğine (RGB ışık vs. CMYK mürekkep) ve ışığın istatistiksel analizine (Histogramlar) hakim olan bir öğrenci, sadece akademik sınavda değil, 2025'in zorlu profesyonel grafik tasarım dünyasında da yetkinliğini kanıtlayacaktır.

### Ek: Anahtar Terim Eşleştirmesi (Türkçe/İngilizce)

Bu tablo, PDF'deki Türkçe terimlerin uluslararası yazılım arayüzündeki İngilizce karşılıklarını ve temel işlevlerini özetlemektedir.

| Türkçe Terim (PDF) | İngilizce Arayüz Karşılığı | Temel İşlev ve Sınav Notu |
| :--- | :--- | :--- |
| **Görüntü Boyutu** | Image Size | Piksel boyutlarını ve baskı boyutunu ayarlar. |
| **Tuval Boyutu** | Canvas Size | Görseli büyütmeden çalışma alanını genişletir/daraltır. |
| **Yeniden Örnekle** | Resample | Piksel ekleyerek (enterpolasyon) veya silerek boyutu değiştirir. |
| **Bağlamsal Görev Çubuğu** | Contextual Task Bar | Seçime göre değişen, yapay zeka araçlarını içeren yüzer menü. |
| **Üretken Dolgu / Genişletme** | Generative Fill / Expand | Metin istemleriyle (prompt) yeni görüntü içeriği üretir. |
| **Kırpma Aracı** | Crop Tool | Görseli keser, düzleştirir (Straighten) veya genişletir. |
| **Düzeyler** | Levels | Histogram üzerindeki 3 nokta ile ton aralığını ayarlar. |
| **Eğriler** | Curves | Tonları grafik çizgisiyle hassas ayarlar (S-Eğrisi ile kontrast). |
| **Canlılık** | Vibrance | Doygunluğu düşük renkleri artırır, cilt tonlarını korur. |
| **Ton / Doygunluk** | Hue / Saturation | Renk tonunu, yoğunluğunu ve ışıklılığını değiştirir. |
| **Arka Planı Kaldır** | Remove Background | Yapay zeka ile özneyi maskeler. |
| **Deforme Et** | Distort | Perspektifi uydurmak için köşeleri bağımsız hareket ettirir. |
| **Ayrıntıları Koru 2.0** | Preserve Details 2.0 | Yapay zeka destekli büyütme (upscaling) algoritması. |
