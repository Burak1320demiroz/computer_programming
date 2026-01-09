# Matematiksel Modelleme, Lineer Cebir Uygulamaları ve Eşitsizlik Analizleri Üzerine Kapsamlı Öğrenim ve Araştırma Raporu

## 1. Giriş ve Metodolojik Çerçeve

Matematik, evrenin karmaşık yapısını anlamlandırmak, fiziksel ve sosyal olaylar arasındaki görünmez bağları görünür kılmak ve belirsizlikler içeren dünyada rasyonel kararlar alabilmek için geliştirilmiş evrensel bir dildir. Atatürk Üniversitesi Açıköğretim Fakültesi Matematik I dersinin "Lineer Denklem ve Eşitsizlik Uygulamaları" başlıklı 6. ünitesi, bu evrensel dilin gramer yapısını oluşturan teorik cebir bilgisinin, pratik yaşamın sorunlarına nasıl uyarlandığını inceleyen kritik bir dönemeçtir. [1]

Bu rapor, söz konusu ders materyali ve ilgili akademik literatür ışığında, matematiksel modellemenin epistemolojik temellerini, tek ve çok değişkenli lineer yapıların deterministik doğasını, piyasa ekonomisindeki arz-talep mekanizmalarını ve mühendislik toleranslarını belirleyen mutlak değerli eşitsizlikleri "tüketici" düzeyinden "analist" düzeyine taşıyacak derinlikte ele almaktadır.

Raporun temel amacı, 9124-6.pdf kodlu belgede sunulan ham bilgiyi, öğrenim sürecini destekleyecek, formüllerin arkasındaki mantıksal kurguyu açıklayacak ve değişkenler arasındaki nedensellik ilişkilerini irdeleyecek bir "öğrenim notu" formatında yeniden inşa etmektir. Analiz süreci, basit aritmetik hesaplamaların ötesine geçerek, olayların matematiksel düzlemde temsili (modelleme), bu temsillerin çözümü (analiz) ve elde edilen sonuçların gerçek hayatla uyumu (validasyon) döngüsü üzerine kurulmuştur.

## 2. Matematiksel Modellemenin Teorik ve Felsefi Temelleri

Matematiksel modelleme, gerçek dünyada gözlemlenen bir fenomenin veya karşılaşılan bir problemin, matematiksel semboller, denklemler ve eşitsizlikler kullanılarak soyut bir dile tercüme edilmesi sürecidir. Bu süreç, "sözel" olanın "sayısal" olana dönüşümüdür ve problemin çözümünde insan zihninin bilişsel yükünü hafifleten bir araçtır.

### 2.1. Modelleme Sürecinin Bileşenleri ve Yapısal Adımları

Bir problemin matematiksel modele dönüştürülmesi lineer bir süreç olmayıp, yinelemeli (iteratif) bir yapı arz eder. Literatür ve ders materyalleri incelendiğinde, bu sürecin dört ana fazda gerçekleştiği ve her bir fazın modelin başarısı için kritik olduğu görülmektedir [1]:

1.  **Problemin Tanımlanması ve Değişken Seçimi (Identification):** Modellemenin ilk ve en önemli adımı, problemin doğasını anlamak ve bilinmeyen parametreleri temsil edecek sembolleri belirlemektir. Genellikle keyfi değişen elemanlar için $x, y, z$ gibi semboller; sistemin sabit parametreleri (katsayılar) için ise $a, b, c$ gibi harfler kullanılır. Karar değişkenlerinin doğru belirlenmesi, modelin geçerliliği için hayati öneme sahiptir. Örneğin, bir üretim probleminde "üretilecek miktar" bir karar değişkeni ($x$) iken, hammadde birim maliyeti bir parametredir ($c$).
2.  **İlişkilerin Kurgulanması (Formulation):** Problemde verilen diğer niceliklerin, seçilen değişken cinsinden ifade edilmesidir. Bu aşama, sözel mantığın cebirsel mantığa dönüştürüldüğü kısımdır. "Bir sayının 3 fazlasının yarısı" ifadesi, dilbilimsel bir yapıdan $\frac{x+3}{2}$ cebirsel yapısına evrilir. Bu aşamada kurulan ilişkilerin doğruluğu, problemin çözümünün doğruluğunu garanti eder.
3.  **Modelin İnşası (Equation/Inequality Building):** Veriler arasındaki kısıtlar ve eşitlikler kullanılarak nihai model oluşturulur. Sistemde kesin bir denge aranıyorsa "denklem" ($=$), bir sınır değer veya tercih söz konusuysa "eşitsizlik" ($\le, \ge, <, >$) kullanılır. Bu adımda, fiziksel dünyanın kuralları (örneğin zamanın negatif olamaması, fiyatın sıfırdan küçük olamaması) matematiksel kısıtlar olarak modele eklenir.
4.  **Çözüm ve Doğrulama (Solution & Validation):** Kurulan modelin matematiksel yöntemlerle çözülmesi ve elde edilen sonucun gerçek hayatın dinamikleriyle uyumlu olup olmadığının kontrol edilmesidir.

### 2.2. Sembolik Temsil ve Değişkenler

Ekonomi, mühendislik ve sosyal bilimlerde kullanılan semboller alanın doğasına göre değişebilir. Ancak temel prensip, bağımlı değişken ve bağımsız değişken ayrımıdır. Lineer denklem uygulamalarında genellikle [1]:

*   **Bağımsız Değişken ($x$):** Doğrudan kontrol edilebilen veya zaman gibi kendiliğinden değişen nicelik (Örn: Gidilen yol, satılan ürün miktarı, geçen süre).
*   **Bağımlı Değişken ($y$):** Bağımsız değişkene göre şekillenen sonuç (Örn: Toplam maliyet, toplam hasılat, depodaki kalan yakıt).

Bu ilişki, en genel haliyle fonksiyonel bir yapı ($y = f(x)$) altında incelenir ve lineer modellerde $y = ax + b$ formunda ifade edilir. Burada $a$ katsayısı, bağımsız değişkendeki bir birimlik değişimin bağımlı değişkende yarattığı etkiyi (marjinal değişim/eğim) temsil ederken, $b$ katsayısı başlangıç koşulunu (sabit terim/y-kesen) ifade eder.

## 3. Tek Bilinmeyenli Lineer Denklem Uygulamaları ve Çözüm Analizleri

Tek bilinmeyenli lineer denklemler, bir sistemin çıktısının tek bir girdiye doğrusal olarak bağlı olduğu durumları modeller. Bu modellerde değişim oranı sabittir; yani ölçek ekonomisi veya azalan verimler yasası gibi lineer olmayan etkiler ihmal edilir. Bu basitleştirme, karmaşık sistemlerin birinci dereceden yaklaşımlarla anlaşılmasını sağlar.

### 3.1. Hizmet Sektöründe Fiyatlandırma: Taksi Ücreti Modellemesi

Günlük hayatta en sık karşılaşılan lineer modeller, hizmet sektöründeki "sabit ücret + değişken ücret" şeklindeki fiyatlandırma politikalaridir. Bu yapı, analitik geometrideki doğru denkleminin ($y = mx + n$) en somut örneğidir. [1]

**Vaka Analizi:**

Bir taksi hizmetinde tarife şu şekilde belirlenmiştir:
*   **Sabit Parametre (Açılış Ücreti):** $40,5$ TL. Bu değer, hizmet hiç kullanılmasa dahi (veya hizmet başladığı anda) oluşan taban maliyettir. Matematiksel olarak $x=0$ anındaki $y$ değeri, yani y-eksenini kesen noktadır (intercept).
*   **Değişim Oranı (Eğim):** Kilometre başına $27$ TL. Bu değer, bağımsız değişkendeki ($x$) bir birimlik artışın bağımlı değişkende ($y$) yarattığı marjinal maliyeti gösterir.

**Matematiksel Modelin Kurulması:**

Bilinmeyen değişken olarak gidilen mesafe ($x$) ve hesaplanan toplam ücret ($y$) belirlenir.
$$\text{Toplam Ücret} = \text{Açılış Ücreti} + (\text{Kilometre başı ücret} \times \text{Gidilen yol})$$
$$y = 40,5 + 27x$$

**Uygulama Örneği:**

Taksiye binen bir kişinin 10 km yol gittiği varsayıldığında ödenecek ücretin hesaplanması:
Modelde $x$ yerine $10$ değeri konulur:
$$y = 40,5 + (27 \times 10)$$
$$y = 40,5 + 270$$
$$y = 310,5 \text{ TL}$$

Bu modelin lineer olmasının temel göstergesi, her kilometrede ücretin sabit miktarda artmasıdır. Eğer tarife, "ilk 5 km'den sonra indirimli" veya "trafik yoğunluğuna göre değişken" olsaydı, model parçalı fonksiyon veya dinamik bir yapıya dönüşürdü. [1]

### 3.2. Ticari Kar-Zarar, Maliyet ve Vergi Analizleri

Ticari işlemlerde maliyet, satış fiyatı, Katma Değer Vergisi (KDV) ve operasyonel giderlerin hesaplanması, lineer denklemlerin en yaygın ve kritik uygulama alanıdır. Bir ürünün "toplam satın alma maliyeti"; ürünün net fiyatı, üzerine eklenen oransal vergiler ve sabit giderlerin toplamıdır. [1]

**Vaka Analizi (Bilgisayar Satın Alma):**

Bir tüketici, kargo ücreti ve KDV dahil olmak üzere bir bilgisayar için toplam $34.420$ TL ödemiştir. Parametreler şöyledir:
*   Sabit Kargo Gideri: $200$ TL.
*   KDV Oranı: $\%18$.
*   Bilinmeyen: Bilgisayarın KDV'siz ve kargosuz ham fiyatı ($x$).

**Modelin Kurulması:**

Toplam maliyet fonksiyonu, değişken ve sabit bileşenlerin toplamıdır. KDV, ham fiyatın bir fonksiyonu ($0,18x$) iken, kargo fiyattan bağımsız sabit bir değerdir.
$$\text{Toplam Maliyet} = \text{Ham Fiyat} + \text{KDV Tutarı} + \text{Kargo Ücreti}$$
$$34.420 = x + 0,18x + 200$$

**Çözüm Adımları:**

1.  Değişken terimler bir araya getirilir: $x + 0,18x = 1,18x$. Bu katsayı ($1,18$), ürünün vergisiz fiyatının vergili fiyata dönüşüm çarpanıdır.
2.  Sabit terim ($200$) eşitliğin diğer tarafına atılarak net ürün bedeli (vergili) bulunur:
    $$1,18x = 34.420 - 200$$
    $$1,18x = 34.220$$
3.  Bilinmeyen $x$ yalnız bırakılarak ham fiyat hesaplanır:
    $$x = \frac{34.220}{1,18}$$
    $$x = 29.000 \text{ TL}$$

Bu örnek, lineer denklemlerin "tersine mühendislik" (reverse engineering) mantığıyla kullanılarak, sonuçtan (toplam fiyattan) girdiye (ham fiyata) ulaşılmasını sağlar.

### 3.3. Kar Marjı ve Maliyet Hesaplamaları

Kar, bir işletmenin sürdürülebilirliği için temel metriktir ve genellikle maliyet üzerine eklenen lineer bir oranla modellenir.

Satış Fiyatı ($S$), Maliyet ($M$) ve Kar Oranı ($k$) arasındaki ilişki:
$$S = M + (M \times k) = M(1+k)$$

**Uygulama Örneği:**

%40 karla 378 TL'ye satılan bir ürünün maliyeti nedir? [1]

**Model:**
$$x + 0,40x = 378 \Rightarrow 1,40x = 378$$
$$x = \frac{378}{1,40} = 270 \text{ TL}$$

Bu basit model, perakende sektöründe "markup" (kar marjı) belirlemede kullanılan temel algoritmadır.

### 3.4. Başabaş (Break-Even) Analizi ve Üretim Planlaması

İşletme matematiğinde stratejik bir öneme sahip olan başabaş analizi, toplam gelirin toplam maliyete eşit olduğu, yani karın sıfır olduğu üretim miktarını belirler. Bu analiz, bir yatırımın riskini ve geri dönüş potansiyelini ölçmek için kullanılır.

**Temel Tanımlar:**

*   **Toplam Gelir (Total Revenue - TR):** Birim satış fiyatı ($p$) ile satılan miktar ($x$) çarpımıdır: $TR = p \cdot x$
*   **Toplam Maliyet (Total Cost - TC):** Üretimden bağımsız sabit maliyetler ($FC$) ve üretim miktarına bağlı birim değişken maliyetlerin ($v \cdot x$) toplamıdır: $TC = FC + v \cdot x$.
*   **Kar Fonksiyonu ($\pi$):** $\pi(x) = TR - TC$. [3]

**Vaka Analizi:**

Bir firma için veriler şu şekildedir [1]:
*   Birim değişken maliyet: 5 TL.
*   Sabit maliyet: 50.000 TL.
*   Birim satış fiyatı: 15 TL.
*   Hedeflenen Kar: 70.000 TL.

**Modelin Kurulması:**

Firmanın 70.000 TL kar elde etmesi için satması gereken ürün miktarı ($x$) hesaplanacaktır.
$$\text{Kar} = \text{Toplam Gelir} - \text{Toplam Maliyet}$$
$$70.000 = 15x - (5x + 50.000)$$

**Çözüm Adımları:**

1.  Parantez açılarak denklem düzenlenir:
    $$70.000 = 15x - 5x - 50.000$$
    $$70.000 = 10x - 50.000$$
2.  Sabitler bir tarafa toplanır:
    $$120.000 = 10x$$
3.  Bilinmeyen bulunur:
    $$x = 12.000 \text{ adet}$$

**Analiz:**

Bu denklemdeki $15x - 5x = 10x$ terimindeki "10 TL", Marjinal Katkı (Contribution Margin) olarak adlandırılır. Her bir ürün, sabit maliyetleri ve karı karşılamak için kasaya 10 TL bırakmaktadır. Sabit maliyet (50.000) ve hedef kar (70.000) toplamı olan 120.000 TL'lik fonun oluşması için 12.000 adet ürün (120.000 / 10) satılması gerektiği mantıksal olarak da doğrulanır.

## 4. İki Bilinmeyenli Lineer Denklem Sistemleri

Gerçek hayat problemleri nadiren tek bir değişkene bağlıdır. Birden fazla bilinmeyen faktörün etkileşimi söz konusu olduğunda, $ax + by + c = 0$ veya $y = mx + n$ formatındaki iki değişkenli denklemlerle modelleme yapılır. Bu sistemler, bir değişkenin diğerine bağlı olarak nasıl değiştiğini veya iki farklı kısıtın aynı anda nasıl sağlandığını gösterir.

### 4.1. Finansal Portföy Yönetimi ve Karışım Problemleri

Bir yatırımcının toplam sermayesini farklı risk ve getiri oranlarına sahip araçlara dağıtması, iki bilinmeyenli denklemlerin tek değişkene indirgenerek çözüldüğü klasik bir optimizasyon problemidir.

**Vaka Analizi:**

Bir yatırımcı 50.000 TL'lik sermayesini iki farklı hisse senedine yatırmıştır. [1]
*   Toplam Sermaye: $50.000$ TL.
*   Yıllık Toplam Getiri: $6.120$ TL.
*   Hisse A Getiri Oranı: $\%14$.
*   Hisse B Getiri Oranı: $\%12$.

**Modelin Kurulması:**

Burada iki bilinmeyen ($x$: Hisse A miktarı, $y$: Hisse B miktarı) vardır ancak $x+y=50.000$ olduğu için $y = 50.000 - x$ dönüşümü yapılarak denklem tek bilinmeyene indirgenir. Bu, lineer cebirde "yerine koyma" (substitution) metodudur.
$$\text{Toplam Getiri} = (\text{A Getirisi}) + (\text{B Getirisi})$$
$$6.120 = 0,14x + 0,12(50.000 - x)$$

**Çözüm Adımları:**

1.  Parantez dağıtılır:
    $$6.120 = 0,14x + 6.000 - 0,12x$$
2.  Benzer terimler işleme alınır ($0,14x - 0,12x = 0,02x$):
    $$6.120 = 0,02x + 6.000$$
3.  Sabitler düzenlenir:
    $$120 = 0,02x$$
4.  Sonuç:
    $$x = \frac{120}{0,02} = 6.000 \text{ TL}$$

Bu durumda yatırımcı, yüksek getirili (%14) araca 6.000 TL, düşük getirili (%12) araca ise 44.000 TL yatırmıştır. Bu model, finansal piyasalarda risk dağılımının matematiksel ispatıdır.

### 4.2. Fiziksel Dönüşüm Modelleri: Sıcaklık Skalaları

Farklı ölçüm birimleri arasındaki dönüşümler, doğadaki fiziksel yasaların lineerliğine dayanır. Celsius ($C$) ve Fahrenheit ($F$) skalaları arasındaki ilişki, analitik geometride "iki noktası bilinen doğrunun denklemi" yöntemiyle modellenir. [1]

**Referans Noktaları:**

*   Suyun Donma Noktası: $(0^\circ C, 32^\circ F)$ $\rightarrow$ Nokta 1 $(x_1, y_1)$
*   Suyun Kaynama Noktası: $(100^\circ C, 212^\circ F)$ $\rightarrow$ Nokta 2 $(x_2, y_2)$

**Modelin Türetilmesi:**

Analitik geometride eğim ($m$) formülü:
$$m = \frac{y_2 - y_1}{x_2 - x_1} = \frac{212 - 32}{100 - 0} = \frac{180}{100} = 1,8$$

Eğim-Nokta formülü ($y - y_1 = m(x - x_1)$) kullanılarak genel denklem yazılır:
$$F - 32 = 1,8(C - 0)$$
$$F = 1,8C + 32$$

Alternatif olarak kesirli gösterimle:
$$F = \frac{9}{5}C + 32$$

**Yorum:**
Bu modelde $1,8$ katsayısı, Celsius ölçeğindeki her 1 derecelik artışın, Fahrenheit ölçeğinde 1,8 derecelik bir artışa denk geldiğini gösterir. Sabit terim $32$ ise, skalaların başlangıç noktaları (offset) arasındaki farktır.

**Pratik Tolerans Hesabı:**
Günlük hayatta $1,8$ ile çarpmak zor olduğundan, yaklaşık bir değer olarak $2$ kullanılır ve formül $(F-32)/2 \approx C$ haline gelir. Bu, matematiksel modellemenin "yaklaşıklık" (approximation) gücünü gösterir ve hata payı içerse de hızlı karar vermeyi sağlar.

## 5. Ekonomik Modelleme: Arz, Talep ve Piyasa Dengesi

Ekonomi bilimi, kaynakların dağılımını incelerken matematiksel modellerden yoğun bir şekilde yararlanır. Lineer arz-talep modeli, serbest piyasa mekanizmasının nasıl çalıştığını, fiyatların nasıl oluştuğunu anlamak için en temel ve güçlü araçtır.

### 5.1. Arz ve Talep Yasalarının Matematiksel İfadesi

Piyasa davranışları, fiyat ($P$) ve miktar ($Q$) arasındaki ilişki üzerinden tanımlanır. Alfred Marshall geleneğine uygun olarak, genellikle dikey eksende Fiyat ($P$), yatay eksende Miktar ($Q$) gösterilir. [1]

#### 5.1.1. Talep Fonksiyonu (Demand)

Tüketici davranışını yansıtır. "Ceteris paribus" (diğer tüm şartlar sabitken) varsayımı altında, fiyat arttıkça talep edilen miktar azalır. Buna Talep Kanunu denir. Bu ters orantı, negatif eğimli bir doğru ile modellenir:
$$P = -cQ + d \quad \text{veya} \quad Q_d = a - bP$$

Burada:
*   **Negatif Eğim ($-c$ veya $-b$):** Tüketicinin fiyat artışına verdiği tepkiyi (fiyat duyarlılığını) gösterir.
*   **Y-Kesen ($d$):** Fiyatın teorik olarak talebi sıfırladığı maksimum "rezervasyon fiyatı"nı temsil eder.

#### 5.1.2. Arz Fonksiyonu (Supply)

Üretici davranışını yansıtır. Fiyat arttıkça, üreticinin kar motivasyonuyla piyasaya sunduğu miktar artar. Buna Arz Kanunu denir. Bu doğru orantı, pozitif eğimli bir doğru ile modellenir:
$$P = aQ + b \quad \text{veya} \quad Q_s = c + dP$$

Burada:
*   **Pozitif Eğim ($a$ veya $d$):** Üreticinin fiyat artışına üretim artışıyla verdiği tepkiyi gösterir.

### 5.2. Piyasa Dengesi (Equilibrium)

Piyasa dengesi, arz edilen miktarın talep edilen miktara eşit olduğu ($Q_s = Q_d$), dolayısıyla piyasada arz fazlası (stok) veya talep açığının (kıtlık) bulunmadığı noktadır. Bu nokta, arz ve talep doğrularının kesişim noktasıdır ($D$ noktası). [1]

**Vaka Analizi (Denge Noktası Hesabı):**

Verilen Denklemler [1]:
*   **Arz Doğrusu:** $y = -2x + 3$ (Not: Dokümandaki bu örnekte arzın eğimi negatif verilmiştir, ancak ekonomik teoride genellikle pozitiftir. Metin içi tutarlılık adına dokümandaki veri esas alınmıştır, ancak standart teoride arz $y=2x+...$ formundadır. Öğrenim notu olarak bu durumun istisnai veya veri hatası olabileceği, normalde arzın artan fonksiyon olduğu not düşülmelidir. Çözüm dokümandaki verilere göre yapılacaktır).
*   **Talep Doğrusu:** $y = 5x - 6$.

**Denge Durumu ($y_{arz} = y_{talep}$):**
$$-2x + 3 = 5x - 6$$
$$3 + 6 = 5x + 2x$$
$$9 = 7x \Rightarrow x = \frac{9}{7} \text{ (Denge Fiyatı)}$$

Bulunan $x$ değeri denklemlerden birinde yerine yazılarak denge miktarı ($y$) bulunur:
$$y = 5\left(\frac{9}{7}\right) - 6 = \frac{45}{7} - \frac{42}{7} = \frac{3}{7} \text{ (Denge Miktarı)}$$

Denge Noktası: $D(\frac{9}{7}, \frac{3}{7})$

**Teorik Genelleştirme:**

Lineer fonksiyonlar için genel denge formülü [3]:
*   Talep: $Q_d = a - bP$
*   Arz: $Q_s = c + dP$

Denge ($Q_d = Q_s$):
$$a - bP = c + dP \Rightarrow a - c = P(b + d)$$
$$\text{Denge Fiyatı } (P_e) = \frac{a - c}{b + d}$$
Bu formül, piyasa dengesinin dışsal şoklardan (örneğin vergiler, sübvansiyonlar veya gelir artışı) nasıl etkilendiğini analiz etmek için kullanılır.

## 6. Eşitsizlik Uygulamaları ve Karar Verme Analizi

Eşitlikler ($=$) kesin ve statik durumları modellerken, gerçek hayat dinamiktir ve genellikle sınırlar, limitler, toleranslarla doludur. "En az", "en fazla", "daha karlı", "daha ekonomik" gibi kavramlar matematiksel olarak eşitsizliklerle ($\le, \ge, <, >$) ifade edilir.

### 6.1. Karşılaştırmalı Karar Modelleri: Alternatiflerin Analizi

İki farklı seçenek arasındaki tercih noktası, genellikle eşitsizliklerin çözüm kümesi ile belirlenir. Bu analiz, "Hangi noktadan sonra A seçeneği B seçeneğinden daha avantajlıdır?" sorusuna yanıt verir.

**Vaka Analizi (Araç Kiralama):**

İki firmanın fiyatlandırma politikaları karşılaştırılmaktadır [1]:
*   **Firma 1:** Günlük 1.500 TL + Km başı 35 TL.
*   **Firma 2:** Günlük 1.750 TL + Km başı 30 TL.

**Problem:** 1 haftalık (7 gün) kiralama için, Firma 1'in Firma 2'den daha ekonomik olması için araç en fazla kaç km kullanılmalıdır?

**Modelin Kurulması:**
Maliyet$_1$ < Maliyet$_2$ eşitsizliği kurulur.
$$7 \times 1.500 + 35x < 7 \times 1.750 + 30x$$
$$10.500 + 35x < 12.250 + 30x$$

**Çözüm:**
Bilinenler ve bilinmeyenler gruplanır:
$$35x - 30x < 12.250 - 10.500$$
$$5x < 1.750$$
Her iki taraf 5'e bölünür:
$$x < 350$$

**Yorum:**
Bu matematiksel sonuç, stratejik bir karar destek verisidir: Eğer yapılacak yolculuk 350 km'den az olacaksa, kilometre başı ücreti yüksek olmasına rağmen sabit ücreti düşük olan Firma 1 tercih edilmelidir. 350 km, iki firmanın maliyetinin eşitlendiği "kayıtsızlık noktası"dır.

### 6.2. Aralık Belirleme ve Dönüşümler

Bir değişkenin belirli bir aralıkta tanımlandığı durumlarda, bu aralığın başka bir birime dönüştürülmesi eşitsizlik özellikleri korunarak yapılır.

**Vaka Analizi (Sıcaklık Aralığı):**

Bir bölgedeki sıcaklık değişimi $-49^\circ F \le x \le 14^\circ F$ aralığındadır. Bu aralığın Celsius cinsinden karşılığı nedir? [1]

**Model:**
$C = \frac{5}{9}(F - 32)$ formülü kullanılarak eşitsizliğin sınır değerleri dönüştürülür.

*   Alt Sınır ($-49^\circ F$): $C = \frac{5}{9}(-49 - 32) = \frac{5}{9}(-81) = -45^\circ C$
*   Üst Sınır ($14^\circ F$): $C = \frac{5}{9}(14 - 32) = \frac{5}{9}(-18) = -10^\circ C$

**Sonuç:** $-45^\circ C \le C \le -10^\circ C$. Eşitsizliğin yönü korunmuştur çünkü dönüşüm katsayısı ($5/9$) pozitiftir.

## 7. Mutlak Değerli Eşitsizlikler ve Tolerans Analizi

Mutlak değer, bir sayının sayı doğrusu üzerindeki başlangıç noktasına (sıfıra) olan uzaklığıdır ($|x| = \text{uzaklık}$). Bu tanım, mühendislikte kalite kontrol, tıpta sağlık parametreleri ve istatistikte standart sapma analizleri için temel oluşturur. Mutlak değerli eşitsizlikler, bir değerin ideal noktadan ne kadar sapabileceğini (tolerans) modeller.

### 7.1. Tolerans İçi Durumlar ($|x| \le k$)

Bu ifade, $x$ değişkeninin merkez noktaya olan uzaklığının $k$ birimden fazla olmamasını, yani güvenli/kabul edilebilir bölgede kalmasını anlatır. [1]

**Genel Çözüm Kuralı:**
$$|x| \le k \Rightarrow -k \le x \le k$$

**Uygulama (Sanayi Fırını Kalite Kontrolü):**
Bir tuğla fabrikasında fırının ideal çalışma sıcaklığı $80^\circ C$ olarak belirlenmiştir. Ancak sistem, $5^\circ C$'lik sapmalara izin vermektedir.

**Model:** Gerçek sıcaklığın ($x$), hedef sıcaklıktan ($80$) farkının mutlak değeri $5$'ten küçük veya eşit olmalıdır.
$$|x - 80| \le 5$$

**Çözüm:**
$$-5 \le x - 80 \le 5$$
Eşitsizliğin her tarafına $+80$ eklenir:
$$75 \le x \le 85$$

Bu sonuç, fırının $75$ ile $85$ derece arasında çalışmasının "standartlara uygun" olduğunu matematiksel olarak tanımlar.

### 7.2. Tolerans Dışı/Ayrık Durumlar ($|x| \ge k$)

Bu ifade, değişkenin merkezden en az $k$ birim uzakta olması gerektiğini belirtir. Genellikle "tehlike bölgesi", "alarm seviyesi" veya "dışlanan aralık" modellemesinde kullanılır.

**Genel Çözüm Kuralı:**
$$|x| \ge k \Rightarrow x \le -k \quad \text{veya} \quad x \ge k$$

Örneğin, $|x - 4| \ge 6$ eşitsizliğinin çözümü [1]:
*   $x - 4 \le -6 \Rightarrow x \le -2$
*   $x - 4 \ge 6 \Rightarrow x \ge 10$

Çözüm Kümesi: $(-\infty, -2] \cup [10, \infty)$

**Vaka Analizi (Sağlık - Tansiyon):**
Bir hastanın sistolik tansiyonunun 120 (ideal) değerinden sapmasının 20 birimden fazla olmaması isteniyorsa (Tolerans içi), model:
$$|x - 120| \le 20$$
$$100 \le x \le 140$$
Doktorlar, hastanın tansiyonu $100$ ile $140$ arasında ise "normal", bu aralığın dışında ise "hipertansiyon" veya "hipotansiyon" teşhisi koyar.

## 8. Özet Tablolar ve Formül Envanteri

Aşağıdaki tablolar, rapor boyunca irdelenen kavramların ve formüllerin sistematik bir özetini sunmaktadır. Bu tablolar, pratik kullanım ve hızlı başvuru için tasarlanmıştır.

### Tablo 1: Temel Lineer Modelleme Formülleri

| Uygulama Alanı | Genel Formül | Değişkenlerin Anlamı |
| :--- | :--- | :--- |
| **Genel Lineer Denklem** | $y = mx + n$ | $m$: Eğim (Değişim Oranı), $n$: Y-kesen (Başlangıç Değeri) |
| **Toplam Maliyet (TC)** | $TC = FC + (v \cdot x)$ | $FC$: Sabit Maliyet, $v$: Birim Değişken Maliyet, $x$: Miktar |
| **Toplam Hasılat (TR)** | $TR = p \cdot x$ | $p$: Birim Satış Fiyatı, $x$: Satılan Miktar |
| **Kar Fonksiyonu ($\pi$)** | $\pi = TR - TC$ | $\pi$: Kar, Başabaş noktasında $\pi=0$ olur. |
| **Satış Fiyatı (Markup)** | $S = M(1+k)$ | $M$: Maliyet, $k$: Kar Oranı (Örn: %20 için 0.20) |
| **Sıcaklık Dönüşümü** | $F = 1,8C + 32$ | $F$: Fahrenheit, $C$: Celsius |
| **Hizmet Ücretlendirme** | $T = A + (k \cdot x)$ | $A$: Açılış Ücreti, $k$: Km Başı Ücret, $x$: Mesafe |

### Tablo 2: Ekonomik Arz-Talep Parametreleri

| Kavram | Formül / Gösterim | Ekonomik Anlamı |
| :--- | :--- | :--- |
| **Talep Fonksiyonu** | $Q_d = a - bP$ | Fiyat ($P$) arttıkça talep ($Q_d$) azalır (Negatif eğim). |
| **Arz Fonksiyonu** | $Q_s = c + dP$ | Fiyat ($P$) arttıkça arz ($Q_s$) artar (Pozitif eğim). |
| **Piyasa Dengesi** | $Q_d = Q_s$ | Arz ve talebin eşitlendiği, piyasanın temizlendiği nokta. |
| **Denge Fiyatı ($P_e$)** | $P_e = \frac{a-c}{b+d}$ | Denge durumundaki tekil fiyat seviyesi. |

### Tablo 3: Eşitsizlik ve Mutlak Değer Kuralları

| Eşitsizlik Tipi | Çözüm Kümesi (Aralık) | Gerçek Hayat Karşılığı |
| :--- | :--- | :--- |
| $x \le a$ | $(-\infty, a]$ | Maksimum kapasite, Bütçe kısıtı. |
| $x \ge a$ | $[a, \infty)$ | Minimum kota, Hedef satış miktarı. |
| $|x - \mu| \le \epsilon$ | $[\mu-\epsilon, \mu+\epsilon]$ | Tolerans içi, Kalite kontrol "Geçer". |
| $|x - \mu| \ge \epsilon$ | $(-\infty, \mu-\epsilon] \cup [\mu+\epsilon, \infty)$ | Tolerans dışı, "Hatalı" ürün veya Alarm durumu. |
| $ax + b < cx + d$ | $x < \frac{d-b}{a-c}$ | Karşılaştırma, Maliyet avantajı analizi (Break-even comparison). |

## 9. İleri Uygulama: Değerlendirme Sorularının Analizi

Dokümanın sonunda yer alan değerlendirme soruları, teorik bilginin sentezlenmesi için mükemmel vaka çalışmaları sunmaktadır. Bu soruların detaylı çözümleri, modelleme yeteneğini pekiştirmektedir. [1]

#### Vaka 1: Net Puan Hesabı (Sınav Sistemi)

**Problem:** 4 yanlışın 1 doğruyu götürdüğü 52 soruluk sınavda, tüm soruları yanıtlayan öğrenci 148 puan almıştır (Her soru 4 puan). Kaç doğru yapmıştır?

**Model:**
*   Doğru sayısı: $D$, Yanlış sayısı: $Y$.
*   Toplam Soru: $D + Y = 52 \Rightarrow Y = 52 - D$.
*   Net Puan Formülü: $\text{Net} = D - \frac{Y}{4}$.
*   Toplam Puan: $4 \times (D - \frac{Y}{4}) = 148$.

**Çözüm:**
1.  Denklem: $4D - Y = 148$.
2.  $Y$ yerine $52-D$ yazılır:
    $$4D - (52 - D) = 148$$
    $$5D - 52 = 148$$
    $$5D = 200 \Rightarrow D = 40$$

**Sonuç:** Öğrenci 40 doğru, 12 yanlış yapmıştır.

#### Vaka 2: Geometrik Kısıtlar

**Problem:** Çevresi 35 cm olan üçgenin iki kenarı, üçüncü kenardan 7 ve 10 cm uzundur. En kısa kenar nedir?

**Model:**
*   En kısa kenar: $x$.
*   Diğer kenarlar: $x+7$ ve $x+10$.
*   Çevre: $x + (x+7) + (x+10) = 35$.

**Çözüm:**
$$3x + 17 = 35 \Rightarrow 3x = 18 \Rightarrow x = 6$$

Bu örnekler, farklı bağlamlardaki (sınav, geometri) problemlerin aynı lineer düşünce yapısıyla ($ax+b=c$) nasıl çözüldüğünü göstermektedir.

## 10. Sonuç

İncelenen 9124-6 kodlu ders materyali ve destekleyici literatür, lineer denklemlerin ve eşitsizliklerin yalnızca soyut matematiksel ifadeler olmadığını ortaya koymaktadır. Bu yapılar:

*   **Deterministik Sistemlerde:** Taksometreler, vergi hesapları ve fiziksel dönüşümlerde kesin sonuçlar üretir.
*   **Ekonomik Sistemlerde:** Piyasa dengesi ve yatırım planlamasında, denge noktalarını ve optimum dağılımı belirler.
*   **Karar Alma Süreçlerinde:** Eşitsizlikler sayesinde alternatifler arasında en uygun seçimi yapmayı (araç kiralama örneği) ve kalite standartlarını (tolerans aralıkları) tanımlamayı sağlar.

Matematiksel modelleme, gerçek hayatın karmaşasını basitleştirerek yönetilebilir parçalara ayırma sanatıdır. Bu raporda detaylandırılan formüller, yöntemler ve analizler, bu sanatı icra etmek isteyenler için kapsamlı bir rehber niteliğindedir. Öğrenim notunun bu derinlikte ele alınması, sadece ders başarısını değil, analitik düşünme ve problem çözme yetkinliğini de kalıcı olarak artıracaktır.
