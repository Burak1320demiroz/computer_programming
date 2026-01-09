# Adobe Photoshop Mimarisinde Veri Kalıcılığı, Dışa Aktarma Protokolleri ve Format Standardizasyonu: Kapsamlı Sınav Hazırlık ve Araştırma Raporu

## 1. Grafik Tasarımda Veri Yönetiminin Teorik Temelleri ve Sınav Kapsamı

Grafik tasarım eğitimi sürecinde, bir görselin estetik kurgusu kadar, o görselin dijital dünyada varlığını sürdürebilmesi için gerekli teknik altyapının anlaşılması da kritik bir önem taşır. Atatürk Üniversitesi Açıköğretim Fakültesi Grafik Tasarımı Bölümü müfredatında yer alan "Dosyaları Kaydetme, Dışa Aktarma ve Farklı Formatlarda Kaydetme" başlıklı ünite, tasarımcının dijital veriyi nasıl yönettiğini, sakladığını ve dağıttığını belirleyen temel prensipleri kapsamaktadır. Bu rapor, söz konusu ünitenin sınav hazırlığı bağlamında derinlemesine analizini sunmakta, akademik ders notlarını genişletilmiş teknik literatür ve endüstri standartları ile harmanlayarak kapsamlı bir başvuru kaynağı oluşturmayı hedeflemektedir.

Dijital görüntü işleme süreçlerinde, bir dosyanın kaydedilmesi eylemi basit bir arşivleme işleminden çok daha fazlasını ifade eder. Bu süreç, verinin ham halden (RAW) işlenmiş sonuca (Output) dönüşürken geçirdiği matematiksel sıkıştırma, renk uzayı dönüşümü ve piksel yeniden örnekleme aşamalarını içerir. Sınav perspektifinden bakıldığında, öğrencilerin sadece hangi menünün nerede olduğunu değil, aynı zamanda "Neden JPG yerine PNG tercih edilmelidir?", "Bikübik örnekleme ile Bilineer örnekleme arasındaki algoritma farkı görüntüye nasıl yansır?" veya "Bulut tabanlı kayıt sistemlerinin (PSDC) yerel diske göre avantajları nelerdir?" gibi neden-sonuç ilişkilerini kavramaları beklenmektedir. Bu rapor, Photoshop ekosistemindeki veri akışını, çalışma dosyasının (Work File) oluşturulmasından nihai ürünün (Delivery Asset) dışa aktarılmasına kadar olan tüm yaşam döngüsünü ele almaktadır.

Sınav hazırlığı sürecinde öğrencilerin karşılaşacağı en büyük zorluklardan biri, teknik terimlerin ve format özelliklerinin birbirine karışmasıdır. Örneğin, PDF'in hem vektör hem de piksel verisini barındırabilen hibrit yapısı veya GIF formatının sadece 256 renk ile sınırlı olması gibi teknik kısıtlar, çoktan seçmeli sorularda ayırt edici faktörler olarak karşımıza çıkmaktadır. Bu bağlamda rapor, ders materyalindeki bilgileri temel alarak, bu bilgileri endüstriyel pratiklerle zenginleştirmekte ve öğrencinin konuyu ezberlemek yerine mantığını kavramasını sağlamayı amaçlamaktadır. Dosya formatlarının (JPG, PNG, GIF, PDF, PSD, TIFF vb.) her birinin kendine has sıkıştırma algoritmaları ve kullanım senaryoları, sınavın omurgasını oluşturan temel bilgi kümeleridir.

## 2. Çalışma Dosyası Mimarisi: Kaydetme Stratejileri ve Veri Güvenliği

Adobe Photoshop'ta yürütülen bir projenin sürdürülebilirliği, doğru kayıt stratejilerine bağlıdır. Kayıt işlemi, bilgisayarın geçici belleğinde (RAM) işlenen verilerin, kalıcı depolama birimlerine (Sabit Disk, SSD veya Bulut) aktarılmasını sağlar. Bu süreç, tasarımın veri bütünlüğünü korumak ve ileride yapılabilecek düzenlemelere olanak tanımak adına hayati öneme sahiptir.

### 2.1. Temel Kayıt Mekanizması ve Kısayol Mantığı

Photoshop arayüzünde en temel işlem, çalışma alanındaki verilerin disk üzerine yazılmasıdır. Ders notlarında vurgulandığı üzere, dosya menüsü altında yer alan "Kaydet" (Save) komutu veya evrensel klavye kısayolu olan **Ctrl+S** (Macintosh sistemlerde **Cmd+S**), projenin o anki durumunu günceller. "S" harfi İngilizce "Save" kelimesinin baş harfinden gelmektedir ve bu kısayol, tasarımcının kas hafızasında yer etmesi gereken en temel reflekstir. Bir çalışma dosyası ilk kez oluşturulduğunda (örneğin "Adsız-1" olarak), henüz disk üzerinde fiziksel bir adresi yoktur. Bu aşamada kullanıcı Ctrl+S komutunu verdiğinde, Photoshop otomatik olarak "Farklı Kaydet" (Save As) iletişim penceresini tetikler. Bu durum, işletim sisteminin dosyaya bir kimlik (isim) ve konum (adres) atama zorunluluğundan kaynaklanan teknik bir gerekliliktir. Dosya bir kez kaydedildikten sonra yapılan müteakip Ctrl+S işlemleri, diskteki mevcut verinin üzerine yazar.

Sınav sorularında sıklıkla karşılaşılan bir senaryo, ilk kayıt işlemi ile sonraki kayıt işlemleri arasındaki davranış farkıdır. İlk kayıtta diyalog penceresinin açılması zorunluluğu, dosyanın henüz bir "yol" (path) bilgisinin olmamasından kaynaklanır. Öğrencilerin bu nüansı kavraması, pratik sınavlarda veya uygulama adımlarının sorulduğu teorik sorularda hata yapmalarını engeller. Ayrıca, kayıt işlemi sırasında dosya formatının seçimi de bu aşamada gerçekleşir. Varsayılan olarak Photoshop, katman bilgisini, maskeleri, yolları ve efektleri koruyan kendi yerel formatı olan **PSD**'yi (Photoshop Document) önerir. Ancak kullanıcı bu aşamada formatı değiştirerek çalışmasını farklı bir yapıda da saklayabilir.

### 2.2. "Farklı Kaydet" (Save As) ile Versiyonlama ve Format Dönüşümü

"Farklı Kaydet" komutu (**Shift+Ctrl+S**), mevcut çalışmanın bir kopyasını farklı bir isimle veya farklı bir formatta kaydetmek için kullanılır. Bu komut, tasarım süreçlerinde "Versiyonlama" (Versioning) stratejisinin temel taşıdır. Profesyonel bir iş akışında, bir proje üzerinde radikal değişiklikler yapılmadan önce dosyanın "Proje_v1.psd", "Proje_v2.psd" şeklinde farklı kaydedilmesi, olası hatalarda geri dönülebilecek güvenli limanlar yaratır.

Adobe'nin son yıllarda yaptığı güncellemelerle birlikte, "Farklı Kaydet" menüsünün işlevi biraz daha özelleşmiştir. Geleneksel olarak tüm formatları (JPG, PNG vb.) bu menüden kaydetmek mümkündü; ancak modern Photoshop sürümlerinde, katman yapısını desteklemeyen "düzleştirilmiş" formatlar (JPG gibi) için bazen "Bir Kopyayı Kaydet" (Save a Copy) komutunun kullanılması gerekmektedir. Bu ayrım, kullanıcının orijinal çalışma dosyasını yanlışlıkla düzleştirilmiş bir formatta kaydedip katmanlarını kaybetmesini önlemek için geliştirilmiş bir güvenlik önlemidir. Sınavda, "Farklı Kaydet" menüsünün ne zaman açıldığı (ilk kayıtta otomatik olarak veya kullanıcı manuel seçtiğinde) ve hangi kısayol tuşuyla (**Shift+Ctrl+S**) tetiklendiği potansiyel soru adaylarıdır.

### 2.3. Bulut Tabanlı Kayıt (Creative Cloud) ve PSDC Formatı

Dijital dönüşümün bir parçası olarak Adobe, yerel disk kaydının ötesine geçerek "Bulut Belgeleri" (Cloud Documents) sistemini entegre etmiştir. Ders materyalinde belirtildiği üzere, Adobe Creative Cloud aboneliği kapsamında kullanıcılara 100 GB'a kadar bulut depolama alanı sunulmaktadır. Bu sistem, dosyaların **.psdc** uzantısı ile Adobe sunucularında saklanmasını sağlar. PSDC formatı, yerel PSD dosyalarıyla aynı veri yapısına sahip olmakla birlikte, bulut mimarisine özgü ek avantajlar sunar.

Bulut kaydının en belirgin avantajı, cihazlar arası sürekliliktir (continuity). Bir kullanıcı iPad üzerindeki Photoshop uygulamasında başladığı bir çizimi buluta kaydettiğinde, ofisteki masaüstü bilgisayarını açtığı anda çalışmaya kaldığı yerden devam edebilir. Ayrıca, bulut belgeleri "Otomatik Yedekleme" özelliği sayesinde, kullanıcı Ctrl+S yapmayı unutsa bile belirli aralıklarla çalışmayı sunucuya gönderir. Bu, elektrik kesintisi veya yazılım çökmesi gibi durumlarda veri kaybını minimize eder. Sınav bağlamında, .psdc uzantısının ne anlama geldiği (Photoshop Cloud Document) ve bulut kaydının sağladığı depolama kapasitesi (100 GB) gibi sayısal veriler önem taşır.

## 3. Dışa Aktarma (Export) Ekosistemi: Teknik Altyapı ve Yöntemler

Grafik tasarımda "Kaydetme" (Save) ile "Dışa Aktarma" (Export) kavramları sıklıkla karıştırılır, ancak teknik olarak farklı amaçlara hizmet ederler. Kaydetme işlemi genellikle çalışmanın düzenlenebilirliğini (Layers, Smart Objects, Text) korumayı hedeflerken; Dışa Aktarma işlemi, çalışmanın nihai kullanım amacına (Web, Baskı, Mobil Uygulama) uygun olarak optimize edilmesini, sıkıştırılmasını ve genellikle tek bir katmana indirgenmesini (flattening) içerir. Photoshop, bu işlem için kullanıcıya çok katmanlı ve detaylı bir araç seti sunar.

### 3.1. Piksel ve Vektör Veri İşleme Prensipleri

Photoshop, doğası gereği piksel tabanlı (raster) bir görüntü işleme yazılımıdır. Yani görüntüler, ızgara yapısı üzerinde dizilmiş renkli karelerden (piksellerden) oluşur. Ancak modern tasarım ihtiyaçları doğrultusunda Photoshop, metinler, şekiller ve yollar gibi vektörel verileri de barındırabilir. Dışa aktarma sürecinde bu iki veri türünün nasıl işlendiği kritik bir teknik detaydır. Ders notlarında vurgulandığı üzere, Photoshop'taki vektörel öğeler (yazı, şekil vb.) dışa aktarılırken genellikle piksele çevrilerek (rasterize edilerek) kaydedilir. Ancak SVG veya PDF gibi formatlar seçildiğinde, bu vektörel yapı korunabilir.

Bu ayrım, sınavda *"Vektör tabanlı bir çizim Photoshop'tan JPG olarak dışa aktarıldığında ne olur?"* gibi bir soruyla test edilebilir. Cevap, vektörel verinin piksele dönüşerek çözünürlük bağımlı hale gelmesidir. SVG (Scalable Vector Graphics) formatı ise, vektör tabanlı grafiklerin tarayıcı uyumlu ve çözünürlükten bağımsız biçimde dışa aktarılmasını sağlayan istisnai bir formattır.

### 3.2. Hızlı Dışa Aktarma (Quick Export) ve Tercihlerin Yönetimi

İş akışını hızlandırmak adına Photoshop, "Dosya > Dışa Aktar" menüsü altında "PNG Olarak Hızlı Dışa Aktar" (Quick Export as PNG) seçeneğini sunar. Bu komut, karmaşık ayar pencerelerini atlayarak, önceden belirlenmiş standart ayarlarla görüntüyü anında diske yazar. Bu özellik, özellikle sosyal medya içerikleri veya taslak sunumlar hazırlarken büyük zaman tasarrufu sağlar. Ancak "Hızlı" ifadesi, ayarların değiştirilemeyeceği anlamına gelmez. Kullanıcılar, "Dışa Aktarma Tercihleri" (Export Preferences) menüsünden bu varsayılan formatı JPG, GIF veya SVG olarak değiştirebilirler.

Dışa Aktarma Tercihleri menüsü, sınav için potansiyel bir detay bilgi kaynağıdır. Bu menüde kullanıcı, hızlı dışa aktarma formatını seçerken "Şeffaflık" (Transparency) özelliğini açıp kapatabilir veya dosya boyutunu küçültmek için 8-bit (daha az renk derinliği) seçeneğini işaretleyebilir.

### 3.3. "Farklı Dışa Aktar" (Export As) İletişim Penceresi ve Modern Web Standartları

"Farklı Dışa Aktar" (Export As), Photoshop'un modern web ve mobil tasarım ihtiyaçlarına cevap veren en kapsamlı dışa aktarma arayüzüdür. Bu pencere, eski "Web İçin Kaydet" (Save for Web Legacy) aracının yerini almak üzere tasarlanmıştır ve daha yüksek performansla çalışır. **Alt+Shift+Ctrl+W** kısayolu ile erişilen bu menü, tek bir görselden birden fazla varyasyon üretme yeteneğine sahiptir. Özellikle mobil uygulama geliştirmede, farklı ekran yoğunlukları (Retina ekranlar vb.) için aynı görselin 1x, 2x, 3x gibi farklı boyutlarda çıktılarının alınması gerekliliği, bu menüdeki "Tümünü Ölçekle" (Scale All) özelliği ile karşılanır.

Bu penceredeki ayarlar, sınavda detaylı teknik soruların gelebileceği bir alandır:
*   **Format Seçimi:** PNG, JPG, GIF ve SVG formatları desteklenir.
*   **Ölçekleme:** Görselin %10 ile %500 arasında yeniden boyutlandırılmasını sağlar. 0.1x seçimi görseli %10 boyutuna küçültürken, 3x seçimi orijinalin 3 katına büyütür.
*   **Tuval Boyutu (Canvas Size):** Görüntüyü bozmadan çalışma alanını genişletmek veya kırpmak için kullanılır. Görsele çerçeve payı (padding) eklemek için idealdir.
*   **Meta Veriler:** Dosya boyutunu minimize etmek için "Yok" seçilebilir veya telif haklarını korumak için "Telif Hakkı ve Kişi Bilgileri" gömülebilir.
*   **Renk Uzayı:** Dijital ekranlar için standart olan sRGB'ye dönüştürme seçeneği, renklerin farklı monitörlerde tutarlı görünmesini sağlar.

### 3.4. Geleneksel Yöntem: Web İçin Kaydet (Legacy)

Photoshop menülerinde "Eski" (Legacy) etiketiyle yer alan "Web İçin Kaydet" (**Alt+Shift+Ctrl+S**), hala birçok profesyonel tarafından tercih edilen köklü bir araçtır. Özellikle GIF optimizasyonu konusunda "Farklı Dışa Aktar" menüsünden daha detaylı kontroller sunar (örneğin renk paletini 128 renge düşürme, dither ayarları vb.). Bu menüde, diğer dışa aktarma seçeneklerinde bulunmayan **WBMP** (Wireless Bitmap) formatı da yer alır. WBMP, 1-bit renk derinliğine sahip, sadece siyah ve beyaz piksellerden oluşan ve çok eski mobil cihazlar için geliştirilmiş bir formattır. Günümüzde kullanım alanı kalmamış olsa da, sınav müfredatında tarihsel bir bilgi veya çeldirici şık olarak yer alabilir.

## 4. Yeniden Örnekleme (Resampling) Algoritmaları ve Görüntü Kalitesi Analizi

Bir dijital görüntünün boyutlarını değiştirmek (Image Size), piksellerin yeniden düzenlenmesini gerektirir. Eğer görüntü küçültülüyorsa bazı pikseller atılmalı, büyütülüyorsa da yeni pikseller yaratılmalıdır. Photoshop, bu işlemi yaparken "Yeniden Örnekleme" (Resampling) algoritmalarını kullanır. Hangi algoritmanın seçildiği, elde edilecek görüntünün keskinliğini, yumuşaklığını ve genel kalitesini doğrudan etkiler.

**Tablo 1: Yeniden Örnekleme Yöntemleri Karşılaştırması**

| Yeniden Örnekleme Yöntemi | Algoritma Mantığı ve Teknik Detay | En İyi Kullanım Alanı | Sonuç Karakteristiği ve Sınav İpuçları |
| :--- | :--- | :--- | :--- |
| **Bikübik (Bicubic)** | Çevredeki piksellerin değerlerini karmaşık matematiksel hesaplamalarla analiz eder. Bilineer yöntemden daha yavaş ama daha hassas (precise) sonuç üretir. | Standart fotoğraf büyütme ve küçültme işlemleri. | Yumuşak ton geçişleri (tonal gradations) sağlar. Bilineer'e göre daha pürüzsüzdür. |
| **Bikübik Daha Keskin (Bicubic Sharper)** | Görüntü küçültülürken (Downsampling) detay kaybını önlemek için algoritma sonrasında ekstra keskinleştirme uygular. | Görseli web için küçültürken, thumbnail oluştururken. | Keskin hatlar sağlar. Ancak bazen aşırı keskinleşme (halo etkisi) yaratabilir. Sınav İpucu: Küçültme işlemi için idealdir. |
| **Bikübik Daha Yumuşak (Bicubic Smoother)** | Görüntü büyütülürken (Upsampling) oluşan pikselleşmeyi ve bozulmaları yumuşatmak için tasarlanmıştır. | Görseli orijinal boyutundan daha büyük hale getirirken. | Daha az tırtıklı, yumuşak bir görünüm. Sınav İpucu: Büyütme işlemi için idealdir. |
| **Bikübik Otomatik (Bicubic Automatic)** | Photoshop, yapılan işlemin türüne (büyütme mi küçültme mi) bakarak yukarıdaki yöntemlerden en uygununu otomatik seçer. | Genel kullanıcılar ve hızlı işlemler için varsayılan ayar. | Dengeli sonuçlar verir. |
| **Bilineer (Bilinear)** | Çevreleyen piksellerin ortalamasını alarak yeni pikseller üretir (2x2 piksel analizi). | Orta kalite gerektiren, işlemci gücünden tasarruf edilecek durumlar. | Bikübik'ten daha hızlıdır ancak daha az hassastır. Sonuçlar biraz daha bulanık olabilir. |
| **En Yakın Komşu (Nearest Neighbor)** | Mevcut pikselleri kopyalayarak çoğaltır. Ara tonlar (anti-aliasing) oluşturmaz. | Piksel sanatı (Pixel Art), barkodlar, QR kodlar, keskin kenarlı çizimler. | Keskin, bloklu ve "tırtıklı" (jagged) kenarlar oluşur. Dosya boyutu küçüktür. Pürüzlü efektler yaratabilir. |
| **Ayrıntıları Koru (Preserve Details)** | Yapay zeka destekli modern bir algoritmadır (Upscale). Gürültüyü (noise) azaltarak büyütme yapar. | Çok büyük ölçekli büyütmeler (Poster baskısı vb.). | Yüksek netlik ve doku koruma sağlar. Eski yöntemlere göre çok daha başarılıdır. |

## 5. Gelişmiş Dışa Aktarma Senaryoları: Katmanlar ve Yüzeyler

Profesyonel tasarım süreçlerinde, tek bir görselin dışa aktarılması her zaman yeterli değildir. Web tasarımı, mobil uygulama arayüzü (UI) veya karmaşık reklam kampanyalarında, tasarımın parçalara ayrılarak (slicing/assets) kaydedilmesi gerekir. Photoshop, bu ihtiyaçlar için özelleşmiş araçlar sunar.

### 5.1. Çalışma Yüzeylerinden (Artboards) Dışa Aktarma

Mobil uygulama tasarımında sıkça kullanılan Çalışma Yüzeyleri, tek bir PSD dosyası içinde birden fazla ekranın (örneğin Giriş Sayfası, Profil Sayfası, Ayarlar Sayfası) yan yana tasarlanmasına olanak tanır.

*   **Dosyalara Dışa Aktarma:** "Dosya > Dışa Aktar > Çalışma Yüzeylerinden Dosyalara" yolu izlenerek, her bir yüzey ayrı bir dosya (JPG, PNG vb.) olarak kaydedilebilir.
*   **PDF Çıktısı:** "Çalışma Yüzeylerinden PDF'e" seçeneği ile tüm yüzeyler, sunum için tek bir çok sayfalı PDF dosyasında birleştirilebilir.

### 5.2. Katman Kompozisyonları (Layer Comps)

Katman Kompozisyonları, bir tasarımın farklı varyasyonlarını tek bir dosyada saklamayı sağlayan güçlü bir özelliktir. Örneğin, bir web sitesi butonunun "Normal", "Üzerine Gelindiğinde (Hover)" ve "Tıklandığında (Active)" halleri aynı PSD içinde farklı katman kombinasyonları olarak saklanabilir. "Dosyalara Katman Kompozisyonları" komutu, tüm bu varyasyonları tek seferde ayrı dosyalar olarak dışa aktarır.

### 5.3. Katmanlardan Dosyalara (Layers to Files)

"Katmanlardan Dosyalara" komutu, belgedeki her bir katmanı (veya seçili katmanları) ayrı bir dosya olarak dışa aktarır. Bu işlem, özellikle web geliştiricilere (developer) asset teslim ederken çok kullanışlıdır.

## 6. Dosya Formatları Ansiklopedisi: Özellikler, Kullanım Alanları ve Sınav Odaklı Analiz

Tasarımcının en kritik kararlarından biri doğru dosya formatını seçmektir. Aşağıdaki bölüm, ders notlarında geçen formatları detaylı bir şekilde incelemekte ve sınavda çıkabilecek özellikleri vurgulamaktadır.

### 6.1. Çalışma Dosyası Formatları (Kaynak Dosyalar)

*   **PSD (Photoshop Document):** Photoshop'un ana formatıdır. Katmanlar, maskeler, akıllı nesneler, metinler ve efektler korunur. Maksimum 2 GB boyutunu destekler. Sınavda "Temel kayıt formatı hangisidir?" sorusunun cevabıdır.
*   **PSB (Photoshop Big):** Büyük belge formatıdır. Dosya boyutu 2 GB'ı aştığında veya piksel boyutları 30.000'i geçtiğinde kullanılır. 300.000 piksele kadar destek verir.
*   **PSDC:** Bulut tabanlı PSD dosyasıdır. Cihazlar arası senkronizasyon sağlar.

### 6.2. Sıkıştırılmış Görüntü Formatları (Web ve Ekran)

*   **JPG / JPEG:** Kayıplı sıkıştırma (lossy). Şeffaflığı desteklemez. Fotoğraflar için idealdir.
*   **PNG:** Kayıpsız sıkıştırma (lossless). Alfa kanalı ile şeffaflığı destekler. Logolar ve web grafikleri için standarttır.
*   **GIF:** Maksimum 256 renk (8-bit). Fotoğraflar için uygun değildir. Animasyon ve 1-bit şeffaflık destekler.
*   **WebP:** Google tarafından geliştirilen modern format. JPG'den daha küçük boyutta yüksek kalite sunar, şeffaflığı ve animasyonu destekler.

### 6.3. Baskı ve Profesyonel Formatlar

*   **TIFF:** Kayıpsızdır (LZW sıkıştırma). RGB, CMYK, LAB destekler. Profesyonel baskı ve arşivleme içindir.
*   **PDF:** Hibrit yapılıdır (Vektör + Piksel). Platform bağımsızdır. Baskıya hazır belgeler için kullanılır.
*   **EPS:** Vektör ve piksel verilerini bir arada tutabilen eski bir formattır.

### 6.4. Özel ve Niş Formatlar

*   **Targa (TGA):** Video işleme ve 3D render yazılımlarında alfa kanallarını saklamada kullanılır.
*   **BMP:** Sıkıştırmasız Windows formatıdır. Çok yer kaplar.
*   **RAW:** Fotoğraf makinesinden gelen ham, işlenmemiş veridir. Dijital negatiftir.
*   **Pixar:** 3D animasyon tasarımında kullanılan özel bir formattır.

## 7. Format Karşılaştırma Tablosu

| Format | Veri Türü | Sıkıştırma | Şeffaflık | Animasyon | Katman Desteği | Temel Kullanım Alanı |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **PSD** | Raster+Vektör | Kayıpsız | Var | Yok | Var | Düzenleme (Kaynak Dosya) |
| **JPG** | Raster | Kayıplı | Yok | Yok | Yok | Web Fotoğraf, Paylaşım |
| **PNG** | Raster | Kayıpsız | Var (Alfa) | Yok | Yok | Logo, İkon, Web Grafik |
| **GIF** | Raster | Kayıpsız (Renk Kayıplı) | Var (1-bit) | Var | Yok | Basit Animasyon, Banner |
| **TIFF** | Raster | Kayıpsız | Var | Yok | Var | Baskı, Arşivleme |
| **PDF** | Hibrit | Karışık | Var | Yok | Var | Belge Paylaşımı, Baskı |
| **SVG** | Vektör | Kayıpsız | Var | Var (Kodla) | Yok | Web İkon, UI (Vektörel) |
| **Targa** | Raster | Kayıpsız | Var | Yok | Yok | Video, Oyun Dokuları |
| **WebP** | Raster | Hibrit | Var | Var | Yok | Modern Web Siteleri |

## 8. Sınav Hazırlık ve Kritik Değerlendirme Soruları Analizi

### 8.1. Sıkça Sorulan Kavramlar ve Çeldiriciler

*   **WBMP'nin Yeri:** Sınavda "Mobil cihazlar için geliştirilmiş eski format hangisidir?" sorusu gelirse cevap kesinlikle **WBMP**'dir.
*   **Kayıt Kısayolları:** **Ctrl+S** (Kaydet) ve **Shift+Ctrl+S** (Farklı Kaydet) arasındaki fark temel bir sınav sorusudur.
*   **Yeniden Örnekleme:** "Pürüzlü efektler (aliasing) hangi yöntemde ortaya çıkar?" sorusunun cevabı **En Yakın Komşu** (Nearest Neighbor) yöntemidir.
*   **Meta Veriler:** Dışa aktarma sırasında telif hakkı bilgisinin eklendiği bölümün adı **"Meta Veriler"**dir.
*   **SVG'nin Doğası:** SVG'nin vektörel olduğu, bu sayede çözünürlükten bağımsız olduğu bilgisi kritiktir.
*   **Renk Sayısı:** GIF'in 256 renk (8-bit) ile sınırlı olduğu unutulmamalıdır.

### 8.2. Ders Notlarındaki Değerlendirme Sorularının Çözümlemesi

Sınav pratiği için örnek soru analizleri:

1.  **Soru:** Çalışma dosyasını kaydetmek için hangi menü kullanılır?
    *   **Cevap:** Dosya > Kaydet.
2.  **Soru:** Hangisi yaygın dijital görüntü formatı değildir?
    *   **Cevap:** **TGA** (Genel kullanıcı için yaygın değildir, profesyonel/video odaklıdır).
3.  **Soru:** SVG'nin yaygın kullanılma sebepleri arasında hangisi yoktur?
    *   **Cevap:** Piksel tabanlı bir yapısı olması (SVG vektöreldir).
4.  **Soru:** Hangi örnekleme yöntemi pürüzlü efektler yaratır?
    *   **Cevap:** **En Yakın Komşu** (Nearest Neighbor).
5.  **Soru:** Telif hakkı bilgisi nereden eklenir?
    *   **Cevap:** Meta Veriler.
6.  **Soru:** Photoshop'un temel kayıt formatı nedir?
    *   **Cevap:** PSD.
7.  **Soru:** Mobil aygıtlarda (eski) iyileştirilmiş görüntü için hangi format kullanılır?
    *   **Cevap:** WBMP.
8.  **Soru:** Web ortamı için modern ve esnek çıktı alma yöntemi hangisidir?
    *   **Cevap:** Farklı Dışa Aktar (Export As).
9.  **Soru:** Animasyon ve 3D görüntülerin tasarımında kullanılan format?
    *   **Cevap:** Pixar.
10. **Soru:** Aynı projeye ait farklı sürümleri tek dosyada organize eden özellik?
    *   **Cevap:** Katman Kompozisyonları (Layer Comps).

### 8.3. Sınavda Başarı İçin Çalışma Stratejisi

Öğrencilerin sınavda başarılı olabilmeleri için ezberden ziyade mantıksal eşleştirmeler yapmaları önerilir:
*   Baskı -> **TIFF / CMYK**
*   Web/Logo -> **PNG / SVG**
*   Animasyon -> **GIF**
*   Fotoğraf -> **JPG**
*   Ham Veri -> **RAW**
*   Varyasyon Yönetimi -> **Katman Kompozisyonları**

Bu rapor, Photoshop'un veri yönetim mimarisini kapsamlı bir şekilde ele almış ve sınavda çıkabilecek tüm kritik noktaları teknik derinliğiyle birlikte sunmuştur.
