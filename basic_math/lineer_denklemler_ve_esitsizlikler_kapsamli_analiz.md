# Matematik I Dersi Ünite 5: Lineer Denklemler ve Eşitsizlikler Kapsamlı Analiz ve Öğrenim Raporu

## 1. Giriş ve Kuramsal Çerçeve

Matematiksel düşüncenin evrimi, somut aritmetikten soyut cebire geçişle birlikte insanlık tarihinde devrim niteliğinde bir sıçrama yaşamıştır. Atatürk Üniversitesi Açıköğretim Fakültesi Matematik I dersinin 5. Ünitesi olan "Lineer Denklemler ve Eşitsizlikler" modülü, bu geçişin en temel ve hayati yapı taşlarını oluşturmaktadır. Bu rapor, söz konusu ders materyalini derinlemesine inceleyerek, sunulan kavramların teorik altyapısını, tarihsel gelişimini, uygulama yöntemlerini ve çözüm stratejilerini akademik bir titizlikle ele almaktadır. Raporun amacı, sadece mevcut bilgiyi özetlemek değil, aynı zamanda bu matematiksel araçların mantıksal kurgusunu çözümleyerek öğrenci ve araştırmacılar için kapsamlı bir başvuru kaynağı oluşturmaktır.

Lineer (doğrusal) ilişkiler, evrendeki neden-sonuç bağıntılarının en saf ve anlaşılır halidir. Bir değişkenin diğerine bağlı olarak sabit bir oranda değiştiği durumlar—ister bir taksimetrenin yazdığı ücret olsun, ister serbest düşen bir cismin hızı—lineer modellerle ifade edilir. Bu ünite, $ax+b=0$ formundaki en basit cebirsel yapıdan başlayarak, düzlem geometrisini inşa eden $ax+by+c=0$ yapılarına ve ardından büyüklük-küçüklük ilişkilerini analiz eden eşitsizlik sistemlerine kadar uzanan geniş bir spektrumu kapsamaktadır.

### 1.1. Tarihsel Perspektif ve Cebirin Doğuşu
Ders materyalinde de vurgulandığı üzere, lineer denklemlerin kökeni modern zamanların çok ötesine, medeniyetin şafağına kadar uzanmaktadır. Antik Mısır ve Babil medeniyetleri (M.Ö. 2000-1800), tarım arazilerinin ölçümü, miras paylaşımı ve vergi hesaplamaları gibi pratik sorunları çözmek amacıyla aritmetik yöntemler geliştirmişlerdir. M.Ö. 1650 yıllarına tarihlenen Rhind Papirüsü, lineer denklemlerin bilinen en eski yazılı örneklerini barındırması bakımından matematik tarihinde eşsiz bir yere sahiptir. Bu dönemde henüz sembolik cebir (x, y gibi harflerin kullanımı) mevcut olmasa da, "aha" hesabı olarak bilinen yöntemlerle bilinmeyen niceliklerin bulunması sağlanmıştır.

Ancak, bu hesaplamaların sistematik bir disiplin haline gelmesi, 9. yüzyılda İslam Dünyası'nın altın çağında gerçekleşmiştir. Büyük matematikçi El-Harezmi, cebir üzerine yaptığı çalışmalarla denklemlerin çözüm yöntemlerini bir algoritma disiplinine dönüştürmüştür. El-Harezmi'nin geliştirdiği "el-cebr" (tamamlama) ve "el-mukabele" (dengeleme) yöntemleri, bugün eşitliğin her iki tarafına aynı işlemin uygulanması prensibinin atasıdır. Bu tarihsel bağlam, lineer denklemlerin sadece soyut semboller yığını olmadığını, aksine binlerce yıllık bir entelektüel birikimin ürünü olduğunu göstermesi açısından kritiktir.

### 1.2. Ünitenin Pedagojik Hedefleri
İncelenen doküman, öğrencilerin ulaşması beklenen bilişsel hedefleri net bir şekilde tanımlamıştır. Bu hedefler, Bloom taksonomisinin bilgi, kavrama ve uygulama basamaklarını kapsamaktadır:
*   **Kavramsal Anlama:** Lineer denklem kavramının tanımını ve yapısını içselleştirme.
*   **İlişkisel Düşünme:** Aralarında doğrusal ilişki bulunan iki değişkenden birinin (bağımsız değişken) diğerine (bağımlı değişken) etkisini analiz edebilme.
*   **Temsil Yeteneği:** Bu ilişkileri tablo, grafik ve cebirsel denklem formlarında çoklu temsillerle ifade edebilme.
*   **Modelleme:** Günlük hayattaki problemleri (maliyet, yol, zaman vb.) matematiksel dile çevirerek lineer denklem formunda yazabilme.
*   **Analitik Çözüm:** Bir ve iki bilinmeyenli eşitsizliklerin çözüm kümelerini belirleyebilme ve grafik üzerinde gösterebilme.
Bu hedefler, öğrencinin sadece "x'i bulma" mekaniğini değil, aynı zamanda değişkenler arasındaki dinamik ilişkileri görselleştirme ve yorumlama becerisini de kazanmasını amaçlamaktadır.

## 2. Bir Bilinmeyenli Lineer Denklemler: Cebirin Temeli

Cebirsel düşüncenin giriş kapısı, bilinmeyeni temsil eden bir sembolün değerinin bulunması sürecidir. Bu süreç, eşitlik kavramının korunması ilkesine dayanır.

### 2.1. Tanım ve Yapısal Analiz
Matematiksel kesinlik açısından, bir bilinmeyenli lineer denklem şu şekilde tanımlanır: $a, b \in \mathbb{R}$ (reel sayılar) ve $a \neq 0$ olmak üzere;
$$ax + b = 0$$
biçimindeki açık önermelerdir. Bu tanımda dikkat edilmesi gereken en kritik nokta $a \neq 0$ koşuludur. Eğer $a$ katsayısı sıfır olursa, değişken ortadan kalkar ve geriye $b=0$ ifadesi kalır. Bu durumda iki olasılık doğar:
*   Eğer $b$ gerçekten 0 ise ($0=0$), denklem bir "özdeşlik" olur ve tüm reel sayılar için doğrudur.
*   Eğer $b$ sıfırdan farklı ise ($5=0$ gibi), bu bir "çelişki" olur ve çözüm kümesi boştur ($\emptyset$).
Lineer denklem tanımı, bu belirsizlik durumlarını dışlayarak, tek ve kesin bir çözümü garanti altına alan yapıyı ($a \neq 0$) şart koşar.

Denklemdeki $x$ sembolü "bilinmeyen" veya "değişken" olarak adlandırılırken, $a$ ve $b$ "katsayı" ve "sabit" olarak nitelendirilir. "Lineer" (doğrusal) terimi ise, değişkenin derecesinin 1 olmasından kaynaklanır ($x^1$). Eğer $x^2$ veya $x^3$ gibi terimler işin içine girerse, denklem lineerliğini kaybeder ve çözüm yöntemleri tamamen değişir.

### 2.2. Çözüm Metodolojisi ve Aksiyomatik Yaklaşım
Bir denklemi çözmek, bilinmeyeni yalnız bırakmak demektir. Bu süreç, reel sayıların cisim aksiyomlarına (toplama ve çarpmanın tersi özellikleri) dayanır. $ax + b = c$ tipindeki bir denklemin çözümü iki temel adımda gerçekleştirilir:
1.  **Toplamsal Ters Eleman Özelliği:** Eşitliğin her iki tarafına, sabit terimin ters işaretlisi eklenir. Amaç, bilinmeyeni içeren terimi izole etmektir.
    $$ax + b - b = c - b \implies ax = c - b$$
2.  **Çarpımsal Ters Eleman Özelliği:** Eşitliğin her iki tarafı, bilinmeyenin katsayısına bölünür (veya katsayının tersi ile çarpılır).
    $$\frac{ax}{a} = \frac{c - b}{a} \implies x = \frac{c - b}{a}$$

Bu algoritma, denklem ne kadar karmaşık görünürse görünsün değişmez. Dokümanda yer alan örnekleri bu teorik çerçevede inceleyelim:

*   **Vaka Analizi 1:** $4x - 12 = 0$
    Bu denklemde $a=4$ ve $b=-12$'dir.
    Eşitliğin her iki tarafına $+12$ eklenir: $4x = 12$.
    Her iki taraf $4$'e bölünür: $x = 3$.
    **Sağlama:** Bulunan kök, denklemde yerine yazıldığında önermeyi doğrulamalıdır: $4(3) - 12 = 0$. Doğru.

*   **Vaka Analizi 2:** $3x - 2 = 5$
    Sabit terim (-2) karşı tarafa +2 olarak geçer: $3x = 7$.
    Bilinmeyenin katsayısı (3) bölen olarak geçer: $x = 7/3$.
    **Önemli Not:** Çözüm kümesi her zaman tam sayı olmak zorunda değildir. Rasyonel sayılar ($\mathbb{Q}$) da çözüm kümesinin doğal bir parçasıdır. Öğrencilerin sıklıkla düştüğü "sonuç tam çıkmadı, yanlış yaptım" yanılgısı, bu örnekle giderilmektedir.

### 2.3. İleri Düzey Manipülasyonlar
Lineer denklemler her zaman standart formda verilmez. Değişkenin eşitliğin her iki tarafında bulunduğu veya parantezli ifadelerin yer aldığı durumlar, cebirsel manipülasyon becerisi gerektirir.

#### 2.3.1. Çift Taraflı Değişkenler
Denklem $4y - 12 = 3y + 5$ örneğindeki gibi her iki tarafta bilinmeyen içeriyorsa, çözüm stratejisi "Gruplandırma"dır. Bilinmeyenler eşitliğin bir tarafına, bilinenler diğer tarafına toplanır. Matematiksel estetik ve işlem kolaylığı açısından genellikle katsayısı küçük olan terim, büyük olanın yanına taşınır.
$3y$, sol tarafa $-3y$ olarak geçer.
$-12$, sağ tarafa $+12$ olarak geçer.
$$4y - 3y = 5 + 12 \implies y = 17$$.

#### 2.3.2. Parantezli Yapılar ve Dağılma Özelliği
Cebirde çarpmanın toplama üzerine dağılma özelliği ($a(b+c) = ab + ac$), parantezli denklemlerin çözüm anahtarıdır.
**Örnek:** $3(4y - 3) = 2(3y + 5)$
Bu denklemde doğrudan toplama veya çıkarma yapılamaz; öncelikle parantezlerin açılması gerekir.
*   **Dağıtma:** Sol taraf $12y - 9$, sağ taraf $6y + 10$ olur.
    $$12y - 9 = 6y + 10$$
*   **Gruplandırma:** Bilinmeyenler sola, sabitler sağa.
    $$12y - 6y = 10 + 9$$
*   **Çözüm:** $6y = 19 \implies y = 19/6$.
Bu tür örnekler, işlem sırasının (parantez $\to$ çarpma $\to$ toplama) önemini vurgular.

## 3. İki Bilinmeyenli Lineer Denklemler ve Analitik Geometri

Matematiksel modelleme, tek bir değişkenin izole dünyasından çıkıp iki değişken arasındaki ilişkinin incelendiği düzleme geçtiğinde boyut değiştirir. Bu bölüm, cebir ile geometrinin kesişim noktası olan analitik geometriye girişi temsil eder.

### 3.1. İki Değişkenli Yapının Doğası
$a, b, c \in \mathbb{R}$ ve $a, b \neq 0$ olmak üzere;
$$ax + by + c = 0$$
biçimindeki denklemler "İki Bilinmeyenli Lineer Denklem" olarak adlandırılır. Bir bilinmeyenli denklemin çözümü sayı doğrusu üzerinde bir nokta iken, iki bilinmeyenli denklemin çözümü düzlemde bir doğru belirtir. Bu ontolojik fark, çözüm kümesinin yapısını tamamen değiştirir.
*   **Sıralı İkili Kavramı:** Bu denklemin tek bir "x" değeri yoktur. Çözüm, denklemi sağlayan $(x, y)$ çiftlerinden oluşur. Bu çiftlere "sıralı ikili" denir çünkü x ve y'nin sırası konumu belirler.
*   **Sonsuz Çözüm Kümesi:** $2x - 3y + 3 = 0$ denklemi ele alındığında;
    *   $x=0$ seçilirse $y=1$ bulunur. $(0, 1)$ bir çözümdür.
    *   $y=0$ seçilirse $x=-3/2$ bulunur. $(-3/2, 0)$ bir çözümdür.
    *   $x=3$ seçilirse $2(3) - 3y + 3 = 0 \implies 9 = 3y \implies y=3$. $(3, 3)$ bir çözümdür.
    Bu şekilde sonsuz sayıda nokta bulunabilir. Bu noktaların koordinat düzleminde işaretlenip birleştirilmesiyle denklemin grafiği (bir doğru) elde edilir.

### 3.2. Doğru Grafikleri ve Çizim Teknikleri
Bir doğrunun karakteristiğini belirleyen iki temel unsur vardır: Eğim (doğrunun ne kadar dik olduğu) ve eksenleri kestiği noktalar (konumu). Ders materyali, grafik çizimi için pratik yöntemler sunmaktadır.

#### 3.2.1. Eksenleri Kesme Yöntemi (Intercept Method)
Öklid geometrisinin temel bir aksiyomu şudur: "İki noktadan yalnız ve yalnız bir doğru geçer." Bu nedenle, bir doğruyu çizmek için onun üzerindeki herhangi iki noktayı bulmak yeterlidir. En kolay bulunan noktalar, eksenlerin kesildiği yerlerdir.
*   **x-eksenini kestiği nokta:** Denklemde $y=0$ yazılır ve $x$ bulunur.
*   **y-eksenini kestiği nokta:** Denklemde $x=0$ yazılır ve $y$ bulunur.
**Örnek Uygulama:** $3x - 4y - 1 = 0$.
*   $y=0$ için: $3x - 1 = 0 \implies x = 1/3$. Nokta: $A(1/3, 0)$.
*   $x=0$ için: $-4y - 1 = 0 \implies y = -1/4$. Nokta: $B(0, -1/4)$.
Bu iki nokta koordinat sisteminde işaretlenir ve cetvel yardımıyla birleştirilerek doğru çizilir.
Matematiksel olarak bu denklem şu formata da dönüştürülebilir:
$$\frac{x}{A} + \frac{y}{B} = 1$$
Burada $A$ ve $B$, sırasıyla x ve y eksenlerini kesen değerlerdir. Bu form, doğrunun eksenlerle ilişkisini en net gösteren formdur.

#### 3.2.2. Eğim-Kesişim Formu ve Doğrunun Eğimi
Denklem $y$ yalnız bırakılarak düzenlendiğinde $y = mx + n$ formu elde edilir.
*   **m (Eğim):** Doğrunun x-ekseniyle yaptığı pozitif yönlü açının tanjantıdır ($m = \tan \alpha$). Aynı zamanda "değişim oranı"dır; $x$'teki 1 birimlik artışın $y$'de yarattığı değişimi gösterir. Dokümanda eğim formülü iki nokta için $m = \frac{y_2 - y_1}{x_2 - x_1}$ olarak verilmiştir.
*   **n (y-kesişim):** Doğrunun y-eksenini kestiği ordinat değeridir.
Genel denklemden ($ax+by+c=0$) eğime geçiş şöyledir:
$$by = -ax - c \implies y = -\frac{a}{b}x - \frac{c}{b}$$
Burada eğim $m = -a/b$ olur. Örneğin, $2y - 3x + 1 = 0$ denkleminin eğimi, $y$'yi yalnız bıraktığımızda $y = \frac{3}{2}x - \frac{1}{2}$ olacağından $m = 3/2$'dir. Bu, doğrunun her 2 birim sağa gidişte 3 birim yukarı çıktığı anlamına gelir.

### 3.3. Özel Doğrular: Eksenlere Paralellik
Lineer denklemlerin her zaman iki değişken içermesi gerekmez. Bazı durumlarda değişkenlerden birinin katsayısı sıfır olabilir.
*   **Yatay Doğrular ($y = k$):** Denklemde $x$ terimi yoksa ($a=0$), $y$ değeri $x$'ten bağımsız olarak sabittir. Bu, x-eksenine paralel bir doğru belirtir. Eğim sıfırdır.
*   **Düşey Doğrular ($x = k$):** Denklemde $y$ terimi yoksa ($b=0$), $x$ değeri sabittir. Bu, y-eksenine paralel bir doğru belirtir. Eğim tanımsızdır (sonsuzdur).

### 3.4. Doğruların Birbirine Göre Konumları
Analitik düzlemde iki doğrunun etkileşimi, lineer denklem sistemlerinin çözüm mantığını oluşturur. İki doğru ($d_1$ ve $d_2$) için üç temel senaryo mevcuttur.

| Doğrusal Konum | Cebirsel Koşul (Katsayı Oranları) | Çözüm Kümesi Anlamı | Grafiksel Görünüm |
| :--- | :--- | :--- | :--- |
| **Kesişen Doğrular** | $\frac{a_1}{a_2} \neq \frac{b_1}{b_2}$ | **Tek Çözüm:** Doğrular tek bir $(x, y)$ noktasında buluşur. Sistem tutarlıdır ve bağımsızdır. | "X" şeklinde kesişim. |
| **Paralel Doğrular** | $\frac{a_1}{a_2} = \frac{b_1}{b_2} \neq \frac{c_1}{c_2}$ | **Çözüm Yok ($\emptyset$):** Eğimler eşittir ancak doğrular farklı yerlerdedir. Asla kesişmezler. | Tren rayları gibi. |
| **Çakışık Doğrular** | $\frac{a_1}{a_2} = \frac{b_1}{b_2} = \frac{c_1}{c_2}$ | **Sonsuz Çözüm:** İki denklem aslında aynı doğruyu ifade eder (birbirinin katıdır). | Üst üste binen tek çizgi. |

**Kritik Örnek Analizi:**
$x - y + 2 = 0$ ve $-2x + 2y + 3 = 0$ doğrularını inceleyelim.
Katsayı oranlarına bakıldığında:
x katsayıları oranı: $1 / -2 = -0.5$
y katsayıları oranı: $-1 / 2 = -0.5$
Sabitler oranı: $2 / 3 \approx 0.66$
Eğim oranları eşit ($\frac{a_1}{a_2} = \frac{b_1}{b_2}$) olduğu için bu doğrular aynı doğrultudadır. Ancak sabit oranları farklı olduğundan ($\neq \frac{c_1}{c_2}$), bu doğrular paraleldir ve hiçbir ortak noktaları yoktur. Dolayısıyla bu denklem sisteminin çözüm kümesi boş kümedir.

## 4. Eşitsizlikler: Büyüklük ve Küçüklük Analizi

Matematik sadece eşitlikleri ($=$) değil, aynı zamanda niceliklerin birbirine göre durumlarını da inceler. Eşitsizlikler, bir değerin diğerinden büyük ($>$), küçük ($<$), büyük veya eşit ($\ge$), küçük veya eşit ($\le$) olduğu durumları modeller.

### 4.1. Bir Bilinmeyenli Lineer Eşitsizlikler
$ax + b > 0$ (veya $\ge, <, \le$) biçimindeki ifadelere birinci dereceden eşitsizlik denir. Eşitsizliklerin en belirgin özelliği, çözüm kümelerinin genellikle sonlu sayıda eleman değil, sonsuz elemanlı bir aralık olmasıdır.

#### 4.1.1. Eşitsizlik Özellikleri ve "Ters Dönme" Kuralı
Eşitsizliklerin cebirsel manipülasyonu denklemlerle büyük oranda benzerlik gösterir, ancak hayati bir fark vardır. Bu fark, negatif sayılarla işlem yapıldığında ortaya çıkar.
*   **Ekleme/Çıkarma:** Eşitsizliğin yönünü değiştirmez. $2 < 5 \implies 2+3 < 5+3$.
*   **Pozitif Sayıyla Çarpma/Bölme:** Yön değişmez. $4 < 8 \implies 4/2 < 8/2$.
*   **Negatif Sayıyla Çarpma/Bölme:** Eşitsizlik yön değiştirir.
    *   *Mantıksal İspat:* $2 < 5$ doğrudur. Her iki tarafı $-1$ ile çarparsak $-2$ ve $-5$ elde ederiz. Sayı doğrusunda $-5$, $-2$'nin solunda yer alır, yani daha küçüktür. Bu nedenle ifade $-2 > -5$ olmalıdır.

**Uygulama Örneği:** $-8(2x+1) < 5$
Bu sorunun çözümünde dağılma özelliğinden sonra gelen bölme işlemi kritiktir.
$-16x - 8 < 5$
$-16x < 13$
Her iki taraf $-16$'ya bölünür. Bölen sayı negatif olduğu için $<$ işareti $>$ olur.
$$x > \frac{13}{-16}$$
Çözüm kümesi: $(-13/16, \infty)$.

### 4.2. İşaret İnceleme Tablosu Metodolojisi
Özellikle çarpım veya bölüm durumundaki ifadelerin ($P(x) \cdot Q(x) > 0$ veya $P(x)/Q(x) \le 0$) çözümünde "deneme-yanılma" yöntemi yetersiz ve risklidir. Bunun yerine sistematik "İşaret İnceleme Tablosu" yöntemi kullanılır.

**Metodoloji:**
1.  **Köklerin Bulunması:** İfadeyi sıfır yapan tüm $x$ değerleri (pay ve payda için ayrı ayrı) bulunur.
2.  **Sıralama:** Bulunan kökler sayı doğrusu tablosunda küçükten büyüğe sıralanır.
3.  **İşaret Tayini:** Tablonun en sağ bölmesine, terimlerin en büyük dereceli katsayılarının işaretlerinin çarpımı yazılır. Sola doğru gidildikçe her kökte (tek katlı köklerde) işaret değiştirilir.

**Kompleks Örnek Analizi:** $\frac{2x-1}{x+2} \ge 0$
Bu rasyonel eşitsizlikte, ifadenin pozitif olduğu veya sıfıra eşit olduğu aralıklar aranmaktadır.
*   **Kökler:** Payı sıfır yapan değer $2x-1=0 \implies x=1/2$. Paydayı sıfır yapan değer $x+2=0 \implies x=-2$.
*   **Tablo Yapısı:** Tablo sayı doğrusunu üç bölgeye ayırır: $(-\infty, -2)$, $(-2, 1/2)$ ve $(1/2, \infty)$.
*   **İşaret Kontrolü:** $x$'in katsayıları payda $+2$, paydada $+1$'dir. $(+) \cdot (+) = +$.
    *   Tablonun en sağına ($1/2$'den büyük bölgeye) + yazılır.
    *   $1/2$ kökünde işaret değişir: -.
    *   $-2$ kökünde işaret tekrar değişir: +.
*   **Çözüm Kümesi:** Bizden $\ge 0$ (pozitif) olan bölgeler isteniyor. Yani $(-\infty, -2)$ ve $(1/2, \infty)$ bölgeleri.
*   **Sınır Değer Analizi:** Eşitlik ($\ge$) olduğu için payın kökü ($1/2$) kümeye dahildir (köşeli parantez). Ancak paydanın kökü ($-2$) ifadeyi tanımsız yaptığı için asla kümeye dahil edilemez (açık parantez).
*   **Sonuç:** $(-\infty, -2) \cup [1/2, \infty)$.

### 4.3. Bileşik Eşitsizlikler
Birden fazla eşitsizlik durumunun aynı anda sağlandığı sistemlerdir. $c \le ax+b < d$ yapısındaki ifadeler, aslında "VE" bağlacı ile bağlanmış iki ayrı eşitsizliktir: $c \le ax+b$ VE $ax+b < d$.
Çözüm için en pratik yol, işlemleri her üç tarafa aynı anda uygulamaktır.
**Örnek:** $-3 < 2x + 5 \le 10$
Amaç ortadaki $x$'i yalnız bırakmaktır.
*   Her taraftan 5 çıkarılır: $-3 - 5 < 2x \le 10 - 5 \implies -8 < 2x \le 5$.
*   Her taraf 2'ye bölünür (Pozitif olduğu için yön değişmez): $-4 < x \le 5/2$.
*   Aralık gösterimi: $(-4, 2.5]$.

## 5. İki Bilinmeyenli Eşitsizlikler ve Grafiksel Çözüm

Cebirsel eşitsizliklerin grafiksel yorumu, modern optimizasyon teorisinin (Lineer Programlama) temelini oluşturur. Bir doğru düzlemi ikiye böler, eşitsizlik ise bu bölgelerden birini seçer.

### 5.1. Yarı Düzlem Kavramı
Herhangi bir $ax + by + c = 0$ doğrusu, koordinat düzlemini üç ayrık kümeye ayırır:
1.  **Doğru Üzeri:** $ax + by + c = 0$ olan noktalar.
2.  **Pozitif Yarı Düzlem:** $ax + by + c > 0$ olan bölge.
3.  **Negatif Yarı Düzlem:** $ax + by + c < 0$ olan bölge.
Çözüm kümesini bulmak, hangi yarı düzlemin eşitsizliği sağladığını tespit etme işlemidir.

### 5.2. Test Noktası (Orijin Testi) Yöntemi
Hangi bölgenin taranacağını belirlemenin en güvenilir ve hızlı yolu "Test Noktası" kullanmaktır. İşlem kolaylığı nedeniyle genellikle $(0,0)$ noktası seçilir (eğer doğru orijinden geçmiyorsa).

**Uygulama Adımları:** $2x + 3y - 10 < 0$ eşitsizliği için:
1.  **Sınır Doğrusu Çizimi:** Öncelikle $2x + 3y - 10 = 0$ doğrusu çizilir. Eşitsizlikte "eşitlik" durumu ($\le$ veya $\ge$) olmadığı için, sınır doğrusu kesikli çizgi (dashed line) olarak çizilir. Bu, sınırın çözüm kümesine dahil olmadığını gösterir.
2.  **Test:** $(0,0)$ noktası eşitsizlikte yerine yazılır.
    $2(0) + 3(0) - 10 < 0 \implies -10 < 0$.
3.  **Karar:** $-10 < 0$ ifadesi matematiksel olarak doğru bir önermedir. Bu demektir ki, orijin $(0,0)$ çözüm bölgesinin içindedir. O halde doğrunun orijin tarafında kalan kısmı taranır.

**Aksi Durum Örneği:** $2x + 3y - 4 \ge 0$
*   Sınır doğrusu düz çizgi (solid line) olarak çizilir (eşitlik var).
*   Test $(0,0)$: $-4 \ge 0$ (Yanlış).
*   **Karar:** Orijin çözüm bölgesinde değildir. Doğrunun orijine bakmayan diğer tarafı taranır.

## 6. Mutlak Değerli Eşitsizlikler

Mutlak değer ($|x|$), bir sayının sayı doğrusunda başlangıç noktasına (sıfıra) olan uzaklığını ifade eder. Uzaklık negatif olamayacağı için mutlak değer sonucu daima non-negatiftir. Eşitsizliklerde mutlak değer, çözüm kümesini kısıtlayan veya parçalayan bir operatör görevi görür.

### 6.1. Teorik Altyapı ve Dönüşümler
Dokümanda mutlak değerin eşitsizlik çözümlerinde kullanılan üç temel teoremi sunulmuştur:
*   **İçe Kapalı Aralık Teoremi ($|x| \le k$):** Bir sayının orijine uzaklığı $k$'dan küçükse, bu sayı $-k$ ile $k$ arasındadır.
    $$|x| \le k \iff -k \le x \le k$$
    Bu özellik, mutlak değerli ifadeyi "sandviç" şeklinde tek bir bileşik eşitsizliğe dönüştürür.
*   **Dışa Açık Aralık Teoremi ($|x| \ge k$):** Uzaklığın $k$'dan büyük olması için, sayının ya $k$'dan büyük olması ya da $-k$'dan küçük olması gerekir.
    $$|x| \ge k \iff x \ge k \lor x \le -k$$
    Bu durumda çözüm kümesi iki ayrık aralığın birleşimidir ($\cup$).

### 6.2. İleri Düzey Vaka Analizi: Rasyonel Mutlak Değer
Ders materyalinde yer alan zorlu bir örnek olan $|\frac{-1}{x-1}| > 4$ sorusunu adım adım analiz edelim.
1.  **Mutlak Değer Özellikleri:** Bölümün mutlak değeri, mutlak değerlerin bölümüne eşittir: $\frac{|-1|}{|x-1|} > 4$.
2.  **Sadeleştirme:** $|-1| = 1$ olduğu için ifade $\frac{1}{|x-1|} > 4$ haline gelir.
3.  **Ters Çevirme:** Eşitsizliğin her iki tarafı pozitif olduğu için, ifadeyi ters çevirebiliriz (takla attırma). Bu işlem eşitsizliğin yönünü değiştirir: $|x-1| < \frac{1}{4}$.
    *   *Alternatif Yol:* İçler dışlar çarpımı (payda pozitif olduğu için): $1 > 4|x-1| \implies \frac{1}{4} > |x-1|$.
4.  **Sandviç Teoremi:** $-\frac{1}{4} < x-1 < \frac{1}{4}$.
5.  **Çözüm:** Her tarafa $+1$ eklenir: $\frac{3}{4} < x < \frac{5}{4}$.
6.  **Kritik Kontrol:** Orijinal ifadede payda $x-1$ olduğu için, $x=1$ değeri ifadeyi tanımsız yapar. Bulunan $(0.75, 1.25)$ aralığı $1$'i kapsamaktadır. Bu nedenle çözüm kümesinden $1$ çıkarılmalıdır.
    **Doğru Çözüm:** $(\frac{3}{4}, 1) \cup (1, \frac{5}{4})$ veya $\{x \in \mathbb{R} \mid \frac{3}{4} < x < \frac{5}{4}, x \neq 1\}$.

## 7. Öğrenim Notu ve Çalışma Kılavuzu

Bu bölüm, yukarıda detaylandırılan akademik analizin özünü teşkil eden, öğrencilerin sınavlara ve gerçek hayat uygulamalarına yönelik hızlı tekrar yapmalarını sağlayacak "Öğrenim Notu"nu içermektedir.

### 7.1. Kritik Kavramlar Özeti

| Kavram | Tanım ve Formül | Önemli İpucu |
| :--- | :--- | :--- |
| **Lineer Denklem** | $ax+b=0$. Çözüm $x=-b/a$. | $a=0$ durumunda denklem bozulur. |
| **İki Bilinmeyenli** | $ax+by+c=0$. Grafik bir Doğru belirtir. | Grafiği çizmek için $x=0 \to y$ ve $y=0 \to x$ bul. |
| **Eğim (m)** | Doğrunun dikliği. $y=mx+n$. | $m > 0$ ise doğru sağa yatık (artan), $m < 0$ ise sola yatık (azalan). |
| **Paralel Doğrular** | Eğimleri eşittir ($m_1=m_2$). | Ortak noktaları yoktur, çözüm kümesi $\emptyset$. |
| **Eşitsizlik Yönü** | Negatifle çarp/böl $\to$ Yön değişir. | En çok yapılan hata budur! $-2x < 6 \implies x > -3$. |
| **İşaret Tablosu** | Kökleri sırala, sağdan işaretle başla. | Paydayı 0 yapan kök asla dahil edilmez (içi boş). |
| **Mutlak Değer** | Uzaklık ölçer. $x<a \to -a<x<a$. | Bölüm durumunda paydayı 0 yapanı ÇIKAR. |

### 7.2. Stratejik Çözüm Adımları

*   **Senaryo 1: Karışık bir denklemle karşılaştınız.**
    1.  Sakin Olun ve Dağıtın: Önce parantezleri açın.
    2.  Gruplayın: $x$'leri bir tarafa, sayıları diğer tarafa toplayın.
    3.  İzole Edin: $x$'in katsayısına bölün.
*   **Senaryo 2: Eşitsizlik çözüm kümesi isteniyor.**
    1.  Eğer ifade rasyonelse ($P(x)/Q(x)$), asla içler dışlar çarpımı yapmayın (paydanın işaretini bilmiyorsunuz).
    2.  Bunun yerine her şeyi bir tarafa toplayıp (sıfıra eşitleyip) Tablo yapın.
    3.  Tabloda "tanımsız" yapan değerlere çift çizgi veya boş daire koyarak kendinizi uyarın.
*   **Senaryo 3: Grafik Çizimi.**
    1.  Denklemde $x=0$ verin, y-eksenini kestiği yeri bulun.
    2.  Denklemde $y=0$ verin, x-eksenini kestiği yeri bulun.
    3.  Bu iki noktayı cetvelle birleştirin.

### 7.3. Neden Öğreniyoruz? (Gelecek Vizyonu)
Bu ünitede (Ünite 5) kazanılan beceriler, bir sonraki ünite olan "Lineer Denklem Uygulamaları" için mutlak ön koşuldur. Ekonomideki Arz-Talep Dengesi, işletmedeki Başabaş Noktası Analizi (Break-even Analysis) ve mühendislikteki optimizasyon problemleri, tamamen bu ünitede öğrenilen $ax+by+c=0$ sistemlerinin kesişim noktalarının bulunmasına dayanır. Bir doğrunun eğimini anlamak, marjinal maliyeti veya hızı anlamak demektir.

## 8. Değerlendirme Soruları Analizi

Dokümanın sonunda yer alan değerlendirme soruları, konunun anlaşılma düzeyini ölçmek için kritik öneme sahiptir.
*   **Soru 2: $3x - 9 < 0$ eşitsizliğinin çözümü nedir?**
    *   **Çözüm:** $3x < 9 \implies x < 3$.
    *   **Aralık Gösterimi:** 3'ten küçük tüm sayılar $(-\infty, 3)$.
    *   **Çeldirici Analizi:** Şıklarda $(3, \infty)$ verilmiş olabilir, dikkat.
    *   **Öğrenim:** Basit eşitsizliklerde yön takibi hayati önem taşır.
*   **Soru 18: $|\frac{-2}{x-3}| > 1$ çözüm kümesi?**
    *   **Analiz:** $|-2| / |x-3| > 1 \implies 2 / |x-3| > 1$.
    *   **Düzenleme:** $2 > |x-3| \implies |x-3| < 2$.
    *   **Sandviç:** $-2 < x-3 < 2$.
    *   **Çözüm:** $+3$ ekle $\to 1 < x < 5$.
    *   **Dikkat:** $x \neq 3$ olmalı (payda).
    *   **Sonuç:** $(1, 3) \cup (3, 5)$.
    *   **Öğrenim:** Negatife bölme kuralının ve mutlak değerin birleştiği, öğrencilerin en çok zorlandığı soru tipidir.

## 9. Sonuç
Lineer denklemler ve eşitsizlikler, matematiğin alfabesidir. Bu ünite boyunca incelenen kavramlar, soyut sembollerin ötesinde, dünyayı modelleme yeteneğimizi artıran güçlü araçlardır. İşaret inceleme tablolarından analitik geometriye uzanan bu yolculuk, öğrenciyi daha karmaşık matematiksel analizlere (türev, integral, lineer cebir) hazırlamaktadır. Bu rapor, söz konusu ders materyalinin sadece bir özeti değil, aynı zamanda onun pedagojik ve teorik bir genişlemesidir.
