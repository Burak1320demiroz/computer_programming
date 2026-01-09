# Atatürk Üniversitesi Temel Bilgi Teknolojileri I: Hesap Tablolarında İleri Düzey İşlemler, Fonksiyon Mimarisi ve Modern Veri Analitiği Raporu

## 1. Giriş: Hesap Tablolarında İşlemsel Paradigma ve Veri Yönetimi

Modern iş dünyasının ve akademik çalışmaların omurgasını oluşturan hesap tabloları, basit veri depolama araçları olmanın çok ötesinde, karmaşık algoritmaların işletildiği, dinamik veri modellerinin kurulduğu ve karar destek sistemlerinin temellendirildiği analitik platformlardır. Atatürk Üniversitesi Açıköğretim Fakültesi "Temel Bilgi Teknolojileri I" dersinin 9. Ünitesi kapsamında ele alınan "Hesap Tablolarında İşlemler" modülü, bu analitik yetkinliğin temel taşlarını oluşturmaktadır. Bu rapor, söz konusu ders materyalini merkeze alarak, hesap tablosu mantığının (spreadsheet logic) derinlemesine bir analizini sunmakta, temel aritmetik operasyonlardan modern Excel 2024 fonksiyonlarına kadar uzanan geniş bir spektrumu kapsamlı bir şekilde incelemektedir.

Hesap tablolarının evrimi, statik veri girişinden dinamik veri işlemeye doğru radikal bir dönüşüm geçirmiştir. Bu dönüşümün merkezinde "formül" kavramı yer alır. Bir hesap tablosunda formül, verinin kendisi değil, verinin "nasıl işleneceğine" dair bir komut setidir. Kullanıcı, hücrelere girdiği verileri (input) belirli mantıksal ve matematiksel operatörler aracılığıyla işleyerek anlamlı enformasyona (output) dönüştürür. Bu süreçte, yazılımın sunduğu fonksiyon kütüphaneleri, kullanıcıyı karmaşık matematiksel hesaplamaları manuel olarak yapma yükünden kurtarır ve standardizasyon sağlar. Raporumuz, bu temel prensipleri akademik bir derinlikle ele alırken, aynı zamanda öğrenim sürecini destekleyecek pedagojik notları ve kritik uyarıları da içermektedir.

Analizimiz, klasik fonksiyonların (TOPLA, ORTALAMA, EĞER vb.) yanı sıra, ders materyalinin sonunda işaret edilen ve Excel ekosisteminde devrim yaratan "Dinamik Dizi" (Dynamic Array) fonksiyonlarını da (METİNAYIR, ÖNCEKİMETİN, RESİM vb.) kapsamaktadır. Bu yeni nesil fonksiyonlar, hesap tablosu yönetiminde "tek hücreye formül yazıp sonucun birden fazla hücreye taşması" (spilling) prensibini getirerek, geleneksel yöntemleri kökten değiştirmiştir. Rapor, bu değişimi teknik detayları, kullanım senaryoları ve karşılaştırmalı analizlerle sunarak, hem temel düzeydeki öğreniciler hem de ileri düzey kullanıcılar için kapsamlı bir başvuru kaynağı olmayı hedeflemektedir.

## 2. Hesap Tablolarında İşlem Mimarisi ve Formül Sentaksı

Hesap tablolarında (Spreadsheets) gerçekleştirilen her türlü analitik işlem, belirli bir sözdizimi (syntax) kuralına dayanır. Bu kurallar, yazılımın kullanıcı niyetini doğru yorumlaması ve beklenen hesaplamayı hatasız gerçekleştirmesi için hayati öneme sahiptir. Atatürk Üniversitesi ders materyalinde vurgulandığı üzere, Excel'in hesaplama motoru, hücre içeriğinin bir veri mi yoksa bir komut mu olduğunu ayırt etmek için katı kurallar uygular.

### 2.1. Formül Başlatma Protokolü: Eşittir (=) İşareti

Excel ve benzeri tüm hesap tablosu yazılımlarında evrensel kural, her formülün **eşittir (=)** işareti ile başlaması zorunluluğudur. Bu işaret, yazılımın derleyicisine (compiler) şu mesajı verir: *"Bu hücreye girilen karakterler statik bir metin değil, işlenmesi gereken bir matematiksel veya mantıksal ifadedir."*

Eğer bir kullanıcı hücreye `33+22` yazarsa, Excel bunu bir metin dizisi (string) olarak kabul eder ve hücrede `33+22` ifadesini olduğu gibi gösterir. Ancak `=33+22` yazıldığında, hesaplama motoru devreye girer, aritmetik işlemi gerçekleştirir ve hücrede sonuç olan `55` değerini gösterir. Bu ayrım, hesap tablolarının "Veri Katmanı" ve "İşlem Katmanı" arasındaki sınırı belirler. İleri düzey kullanımlarda, formüllerin başına artı (+) veya eksi (-) işareti koymak da hesaplamayı tetikleyebilir (Lotus 1-2-3 uyumluluğundan gelen bir miras), ancak endüstri standardı ve akademik olarak doğru kabul edilen yöntem eşittir işaretidir.

### 2.2. Hücre Referanslama Mantığı ve Dinamik Veri Yapısı

Hesap tablolarının kağıt-kalem hesaplamalarına veya hesap makinelerine göre en büyük üstünlüğü "dinamik güncellenebilirlik" yeteneğidir. Bu yetenek, formüllerde sabit sayılar (sabitler/constants) yerine **Hücre Adresleri (Referanslar)** kullanılmasıyla sağlanır.

#### 2.2.1. Sabit Değerler vs. Hücre Referansları
Bir formülde sabit değerler kullanmak (Örn: `=20+4`), o formülü statik hale getirir. Veri değiştiğinde (örneğin 20 sayısı 50 olduğunda), kullanıcının formülün içine girip manuel olarak düzeltme yapması gerekir. Bu durum, binlerce satırlık veri setlerinde sürdürülemez bir iş yükü ve hata riski oluşturur. Bunun yerine, ders materyalinde belirtildiği gibi, verilerin bulunduğu hücrelerin adresleri (Örn: A1, B1) kullanılarak dinamik bir yapı kurulur.

**Örnek Senaryo Analizi:**
*   **Senaryo:** A1 hücresinde 33, A2 hücresinde 22 değeri bulunmaktadır.
*   **Statik Yaklaşım:** A3 hücresine `=33+22` yazılır. Sonuç 55'tir. A1 hücresi 40 olarak değiştirilse bile A3 hücresi 55 olarak kalır.
*   **Dinamik Yaklaşım:** A3 hücresine `=A1+A2` yazılır. Sonuç 55'tir. A1 hücresi 40 olarak değiştirildiğinde, Excel'in "Hesaplama Zinciri" (Calculation Chain) otomatik olarak tetiklenir ve A3 hücresi anında 62 olarak güncellenir.

Bu dinamik yapı, finansal modellemelerden akademik not hesaplamalarına kadar tüm Excel uygulamalarının temelini oluşturur. Kullanıcı, veriyi ve işlem mantığını birbirinden soyutlayarak, veri değiştikçe sonucun otomatik olarak aktığı bir "akış" (flow) tasarlar.

#### 2.2.2. Referans Türleri: Göreceli, Mutlak ve Karma
Her ne kadar temel ders materyalinde detaylı olarak mutlak referans ($ işareti) vurgulanmasa da, formül kopyalama işlemlerinde hayati olan bu ayrım, öğrenim notlarının bütünlüğü açısından kritik bir bağlamdır.
*   **Göreceli Referans (A1):** Formül başka bir hücreye kopyalandığında, referans alınan hücre adresleri de kopyalanan yöne göre ötelenir.
*   **Mutlak Referans ($A$1):** Formül nereye kopyalanırsa kopyalansın, referans alınan hücre sabit kalır.
*   **Karma Referans ($A1 veya A$1):** Sadece satırın veya sadece sütunun sabitlendiği durumlardır.

### 2.3. Matematiksel Operatörler ve İşlem Hiyerarşisi

Excel, matematiksel işlemleri gerçekleştirmek için standart aritmetik operatörleri kullanır. Bu operatörlerin kullanımı, matematiksel aksiyomlara tam uyum gösterir. Ders notlarında belirtilen dört temel işlem operatörü şunlardır:

| İşlem | Operatör | Klavye Karşılığı | Örnek Formül | Açıklama |
| :--- | :---: | :--- | :--- | :--- |
| **Toplama** | `+` | Artı | `=A1+B1` | İki veya daha fazla hücrenin değerini toplar. |
| **Çıkarma** | `-` | Eksi/Tire | `=A1-B1` | Bir hücre değerinden diğerini çıkarır. |
| **Çarpma** | `*` | Yıldız (Asterisk) | `=A1*B1` | "x" harfi yerine yıldız kullanılır. |
| **Bölme** | `/` | Eğik Çizgi (Slash) | `=A1/B1` | Bölme işlemi için kullanılır. |

**İşlem Önceliği (Precedence Rules):**
Excel'de karmaşık formüller yazılırken, matematiksel işlem sırası kuralları (Parantez > Üs Alma > Çarpma/Bölme > Toplama/Çıkarma) geçerlidir. Örneğin, `=5+2*3` formülü yazıldığında, Excel önce çarpmayı yapar (2*3=6), sonra toplar (5+6=11). Eğer kullanıcının niyeti önce toplama yapmaksa, parantez kullanmak zorundadır: `=(5+2)*3` sonucu 21 verir. Ders materyalindeki ortalama hesaplama örneğinde `=(B1+B2+B3)/3` formülünde parantez kullanımı bu kuralın bir gereğidir; aksi takdirde sadece B3 hücresi 3'e bölünürdü.

## 3. Temel Fonksiyonlar ve İstatistiksel Analiz

Fonksiyonlar, Excel'in önceden tanımlanmış, karmaşık matematiksel, mantıksal veya metinsel işlemleri gerçekleştiren paket kod bloklarıdır. Yüzlerce satırlık bir sütunu toplamak için `A1+A2+A3...+A100` yazmak pratik olmadığından, fonksiyonlar bu tür işlemleri tek bir komutla (`=TOPLA(A1:A100)`) gerçekleştirmek için tasarlanmıştır.

### 3.1. Fonksiyon Ekleme Yöntemleri ve Arayüz

Ders notlarına göre, fonksiyonlar üç farklı yöntemle hücreye eklenebilir:
1.  **Doğrudan Yazım:** Kullanıcı, fonksiyonun adını ve parametrelerini ezbere biliyorsa, doğrudan hücreye `=` yazıp fonksiyonu girebilir. Bu yöntem en hızlısıdır ancak hata yapma riski içerir.
2.  **Formül Çubuğu (fx):** Formül çubuğunun solundaki **fx** butonuna tıklandığında açılan "İşlev Ekle" penceresi, kullanıcıya rehberlik eder. Fonksiyonun ne işe yaradığını açıklar ve gerekli parametreleri kutucuklar halinde sunar.
3.  **Formüller Sekmesi:** Excel şeridindeki (Ribbon) "Formüller" sekmesinde fonksiyonlar kategorize edilmiştir (Finansal, Mantıksal, Metin vb.). Kullanıcı buradan uygun kategoriyi seçerek fonksiyonu ekleyebilir.

### 3.2. Aralık Belirteçleri: İki Nokta (:) ve Noktalı Virgül (;)

Fonksiyonlarda birden fazla hücreyi işleme dahil ederken kullanılan noktalama işaretleri, işlemin kapsamını belirler. Bu, Excel okuryazarlığının en kritik detaylarından biridir:
*   **İki Nokta Üst Üste (:):** Bir aralığı (range) ifade eder. Belirtilen başlangıç ve bitiş hücreleri arasındaki **tüm hücreleri** kapsar.
    *   *Örnek:* `=TOPLA(A1:A5)` $\rightarrow$ A1, A2, A3, A4 ve A5 hücrelerinin tamamını toplar.
*   **Noktalı Virgül (;):** Bağımsız hücreleri ifade eder. Sadece belirtilen hücreleri işleme alır, aradakileri atlar.
    *   *Örnek:* `=TOPLA(A1;A5)` $\rightarrow$ Sadece A1 ve A5 hücrelerini toplar; A2, A3, A4 işleme dahil edilmez.

### 3.3. Kritik İstatistiksel Fonksiyonlar

Atatürk Üniversitesi ders materyali, özellikle akademik not hesaplamaları ve basit veri analizleri için gerekli olan temel fonksiyonlara odaklanmıştır. Bu fonksiyonların her biri, veri setlerinden anlamlı özetler çıkarmak için kullanılır.

#### 3.3.1. TOPLA (SUM) Fonksiyonu
Verilen bir hücre aralığındaki tüm sayısal değerlerin kümülatif toplamını hesaplar.
*   **Sözdizimi:** `=TOPLA(Sayı1;;...)` veya `=TOPLA(Aralık)`
*   **Uygulama:** Öğrenci notlarının toplamını bulmak veya bir aylık harcamaları toplamak için kullanılır.
*   **Özellik:** Metin içeren hücreleri veya boş hücreleri otomatik olarak görmezden gelir (hataya düşmez, 0 kabul eder).
*   **Ders Örneği:** F2 hücresine `=TOPLA(B2:E2)` yazılarak öğrencinin Derse Katılım, Ödev, Vize ve Final notları toplanmıştır.

#### 3.3.2. ORTALAMA (AVERAGE) Fonksiyonu
Veri setinin aritmetik ortalamasını (merkezi eğilim ölçüsü) hesaplar. Toplam değerin eleman sayısına bölünmesi prensibini otomatikleştirir.
*   **Sözdizimi:** `=ORTALAMA(Aralık)`
*   **Uygulama:** Sınıfın sınav ortalamasını veya yıllık sıcaklık ortalamasını bulmak.
*   **Kritik Detay:** Hücrede 0 yazması ile hücrenin boş olması ORTALAMA fonksiyonu için farklıdır. **0** yazan hücre ortalamaya katılır (değeri düşürür), **boş** hücre ise işleme hiç dahil edilmez (yok sayılır).
*   **Manuel Hesaplama Riski:** `=(A1+A2)/2` formülü ile aynı sonucu verir ancak veri sayısı değiştiğinde manuel formülde bölen sayısını (2) değiştirmek gerekirken, ORTALAMA fonksiyonu bunu otomatik ayarlar.

#### 3.3.3. MAK (MAX) ve MİN (MIN) Fonksiyonları
Veri setindeki uç değerleri (ekstremum noktaları) tespit etmek için kullanılır.
*   **MAK (Maksimum):** Seçili aralıktaki en büyük sayıyı döndürür.
    *   *Ders Örneği:* `=MAK(B2:B11)` formülü ile sınıfın en yüksek "Derse Katılım Puanı" (98) tespit edilmiştir.
*   **MİN (Minimum):** Seçili aralıktaki en küçük sayıyı döndürür.
    *   *Ders Örneği:* `=MİN(B2:B11)` formülü ile en düşük not (18) bulunmuştur.
*   **Kullanım Alanı:** Bu fonksiyonlar, veri setinin dağılım aralığını (Range) görmek, en başarılı/başarısız performansı belirlemek veya stok takibinde kritik seviyeleri görmek için idealdir.

## 4. Mantıksal Fonksiyonlar ve Karar Destek Mekanizmaları

Excel'i basit bir hesap makinesinden ayıran en önemli özellik, verilere dayalı "karar verme" (decision making) yeteneğidir. Bu yetenek, mantıksal fonksiyonlar aracılığıyla sağlanır. Ders materyali, bu kapsamda EĞERSAY ve EĞER fonksiyonlarını detaylandırmıştır.

### 4.1. EĞERSAY (COUNTIF): Koşullu Veri Madenciliği

Bir veri setinde, sadece belirli bir kriteri sağlayan hücrelerin sayısını bulmak için kullanılır. Bu fonksiyon, "Sınıfta kaç kişi geçti?", "Kaç ürün stokta 100'den az?" gibi soruların cevabını verir.
*   **Sözdizimi:** `=EĞERSAY(Aralık; Ölçüt)`
*   **Parametreler:**
    *   *Aralık:* Sayılacak hücrelerin bulunduğu alan (Örn: B2:B11).
    *   *Ölçüt:* Hangi koşulu sağlayanların sayılacağı (Örn: ">=85").
*   **Önemli Kural:** Ölçüt kısmında karşılaştırma operatörleri (>, <, =, >=) kullanıldığında, ifadenin mutlaka **çift tırnak (" ")** içine alınması gerekir.
    *   *Yanlış Kullanım:* `=EĞERSAY(A1:A10; >50)`
    *   *Doğru Kullanım:* `=EĞERSAY(A1:A10; ">50")`
*   **Ders Örneği:** Sınıfta 85 puan ve üzeri not alan öğrenci sayısını bulmak için `=EĞERSAY(B2:B11; ">=85")` formülü kullanılmıştır.

### 4.2. EĞER (IF): Algoritmik Karar Ağaçları

Excel'in en popüler ve güçlü mantıksal fonksiyonudur. Bir koşulun doğruluğunu test eder; koşul doğruysa bir değer, yanlışsa başka bir değer döndürür.
*   **Temel Sözdizimi:** `=EĞER(Mantıksal_Sınama; Doğruysa_Değer; Yanlışsa_Değer)`
*   **Basit Senaryo:** Öğrenci notu 50'den büyükse "Geçti", değilse "Kaldı" yazsın.
    *   `=EĞER(A1>50; "Geçti"; "Kaldı")`

#### 4.2.1. İç İçe EĞER (Nested IF) Yapıları
Gerçek hayatta kararlar genellikle ikili (Binary) değildir; çok seçenekli durumlar mevcuttur. Örneğin harf notu hesaplamada (AA, BA, BB...) tek bir EĞER fonksiyonu yetersiz kalır. Bu durumda, EĞER fonksiyonları birbirinin içine yerleştirilerek bir karar ağacı oluşturulur.

**Ders Materyali Harf Notu Algoritması:**
Ders notlarında sunulan harf notu sistemi, öğrencinin ortalamasına (H2 hücresi) göre şu mantıkla çalışır:
*   Not < 25 ise FF
*   Not < 45 ise DD
*   Not < 55 ise DC
*   ...şeklinde devam eder.

**Formül Yapısı:**
`=EĞER(H2<25; "FF"; EĞER(H2<45; "DD"; EĞER(H2<55; "DC";...)))`

**Çalışma Mantığı:** Excel formülü soldan sağa doğru okur.
1.  İlk koşula bakar (H2<25 mi?). Eğer not 20 ise, bu koşul DOĞRU olur, Excel "FF" yazar ve formülün geri kalanına bakmayı bırakır.
2.  Eğer not 60 ise, ilk koşul YANLIŞ olur. Excel "Yanlışsa_Değer" kısmına geçer. Burada yeni bir EĞER fonksiyonu ile karşılaşır.
3.  İkinci koşula bakar (H2<45 mi?). 60 sayısı 45'ten küçük olmadığı için yine YANLIŞ olur ve bir sonraki EĞER'e geçer.
4.  Bu süreç, doğru koşul bulunana veya tüm koşullar tükenene kadar devam eder.

**Kritik Uyarı:** İç içe EĞER fonksiyonlarında açılan her parantez, formülün en sonunda mutlaka kapatılmalıdır. 8 tane EĞER iç içe kullanıldıysa, sonda 8 adet kapatma parantezi `))))))))` bulunmalıdır.

## 5. Modern Excel Devrimi: Dinamik Diziler ve Yeni Fonksiyonlar (2024 ve Sonrası)

Ders materyalinin son bölümü, Excel'in evrimindeki en büyük kırılma noktalarından biri olan "Yeni Nesil Fonksiyonlar"a (Excel 2024 / Microsoft 365) ayrılmıştır. Bu fonksiyonlar, geleneksel Excel kullanım alışkanlıklarını (örneğin Ctrl+Shift+Enter ile dizi formülü yazma zorunluluğunu) ortadan kaldırmış ve **Dinamik Dizi (Dynamic Array)** dönemini başlatmıştır. Dinamik diziler, tek bir hücreye yazılan formülün sonucunun, birden fazla hücreye otomatik olarak "taşması" (Spill) prensibine dayanır.

### 5.1. Metin Manipülasyonunda Devrim

Geleneksel Excel'de metinleri parçalamak veya birleştirmek için SOLDAN, SAĞDAN, BUL, UZUNLUK gibi fonksiyonların karmaşık kombinasyonları kullanılırdı. Yeni fonksiyonlar bu işlemleri tek komuta indirgemiştir.

#### 5.1.1. METİNAYIR (TEXTSPLIT)
Bir metni belirli bir ayırıcıya (delimiter) göre parçalayarak ayrı hücrelere dağıtır.
*   **Eski Yöntem:** "Metni Sütunlara Dönüştür" sihirbazı veya karmaşık PARÇAAL formülleri.
*   **Yeni Yöntem:** `=METİNAYIR(Metin; Sütun_Ayırıcısı;)`
*   **Senaryo:** A1 hücresinde "Ahmet,Yılmaz,Mühendis,Ankara" verisi olsun. Virgüllerden ayırmak için:
    *   `=METİNAYIR(A1; ",")`
*   **Sonuç:** B1'de "Ahmet", C1'de "Yılmaz", D1'de "Mühendis" ve E1'de "Ankara" otomatik olarak oluşur.

#### 5.1.2. ÖNCEKİMETİN (TEXTBEFORE) ve SONRAKİMETİN (TEXTAFTER)
Metin içerisindeki belirli bir karakterden önceki veya sonraki kısmı çekip alır.
*   **ÖNCEKİMETİN:** Belirteçten önceki kısmı alır.
    *   *Örnek:* `=ÖNCEKİMETİN("info@sirket.com"; "@")` $\rightarrow$ Sonuç: "info"
    *   *Kullanım:* E-posta adreslerinden kullanıcı adlarını ayıklamak için idealdir.
*   **SONRAKİMETİN:** Belirteçten sonraki kısmı alır.
    *   *Örnek:* `=SONRAKİMETİN("info@sirket.com"; "@")` $\rightarrow$ Sonuç: "sirket.com"
    *   *Kullanım:* Alan adlarını (domain) ayıklamak için kullanılır.

**İleri Düzey Özellik:** Bu fonksiyonlar "instance_num" (örnek numarası) parametresi ile çalışabilir. Örneğin metinde birden fazla tire (-) varsa, ikincisinden sonrasını al (`=SONRAKİMETİN(A1; "-"; 2)`) gibi spesifik komutlar verilebilir.

### 5.2. Veri Yapılandırma ve Görselleştirme Fonksiyonları

#### 5.2.1. DİKEYBİRLEŞTİR (VSTACK) ve YATAYBİRLEŞTİR (HSTACK)
Farklı sayfalarda veya tablolarda bulunan veri kümelerini tek bir dizide birleştirir.
*   **DİKEYBİRLEŞTİR (VSTACK):** Dizileri alt alta ekler.
    *   *Örnek:* `=DİKEYBİRLEŞTİR(Tablo1; Tablo2)` $\rightarrow$ Tablo 2'yi Tablo 1'in altına ekleyerek tek bir uzun liste oluşturur.
*   **YATAYBİRLEŞTİR (HSTACK):** Dizileri yan yana ekler.
*   **Avantajı:** Kaynak tablolara yeni veri eklendiğinde, birleştirilmiş dizi de otomatik olarak güncellenir. Bu özellik, konsolide raporlar hazırlamak için devrim niteliğindedir.

#### 5.2.2. RESİM (IMAGE) Fonksiyonu
Excel hücrelerinin içine internet üzerindeki bir görseli doğrudan gömer.
*   **Sözdizimi:** `=RESİM(Kaynak; [Alternatif_Metin];)`
*   **Özellik:** Eklenen resim hücrenin "üstünde" yüzen bir obje değil, hücrenin "içinde" bir veri gibi davranır. Hücre boyutu değiştiğinde resim de yeniden boyutlanır. Sıralama ve filtreleme işlemlerinde resim verisi satırla birlikte hareket eder.
*   **Kısıtlama:** Resim kaynağının `https://` protokolü ile başlayan bir web adresi olması gerekir. Yerel diskten resim çekmek için kullanılmaz.

### 5.3. Çeviri ve Dil Algılama Fonksiyonları

Global iş dünyası için Excel'e eklenen dil yetenekleridir.
*   **ÇEVİR (TRANSLATE):** Bir hücredeki metni bir dilden diğerine çevirir.
    *   *Not:* Excel'de geçmişte "ÇEVİR" ismi CONVERT (birim dönüştürme) fonksiyonu için kullanılıyordu. Yeni sürümde Microsoft Translator altyapısını kullanan bu fonksiyon, metin çevirisi yapar. CONVERT fonksiyonu ise halen fiziksel birimler (inç -> cm) için kullanılmaktadır.
*   **DİLTESPİT (DETECTLANGUAGE):** Metnin hangi dilde yazıldığını algılar ve dil kodunu (Örn: "tr", "en") döndürür.

## 6. Verimlilik Araçları: Otomatik Doldurma

Excel'in en çok zaman kazandıran özelliği, **Doldurma Tutamacı (Fill Handle)** aracıdır. Bu araç, veri girişinde desenleri (pattern) tanıyarak devamını getirir veya formülleri hızla kopyalar.

### 6.1. Çalışma Prensibi
Aktif hücrenin sağ alt köşesinde bulunan küçük kareye "Doldurma Tutamacı" denir. Fare imleci bu karenin üzerine getirildiğinde, imleç kalın beyaz artı işaretinden ince siyah artı (+) işaretine dönüşür. Bu durumdayken fare ile tıklayıp sürüklemek işlemi başlatır.

### 6.2. Kullanım Senaryoları
*   **Formül Kopyalama:** Bir hücreye yazılan formül (Örn: C1 hücresine `=A1+B1`) aşağı doğru sürüklendiğinde, Excel "Göreceli Referans" mantığıyla sonraki satırlar için formülü otomatik günceller (C2 hücresine `=A2+B2`, C3 hücresine `=A3+B3` yazar).
*   **Sıralı Liste Oluşturma:**
    *   *Metin Serileri:* "Pazartesi" yazıp sürüklerseniz, Excel haftanın diğer günlerini sırayla yazar. Aynı mantık Ay isimleri (Ocak, Şubat...) için de geçerlidir.
    *   *Sayısal Seriler:* Sadece "1" yazıp sürüklerseniz hepsine "1" kopyalar. Ancak "1" ve "2" yazıp ikisini birden seçip sürüklerseniz, Excel aradaki artış miktarını (1) algılar ve "3, 4, 5..." şeklinde devam ettirir. Eğer "5" ve "10" yazıp sürüklerseniz "15, 20, 25..." şeklinde beşer beşer artırır.
*   **Hızlı Doldurma (Flash Fill):** Excel, kullanıcının veri düzenleme mantığını öğrenir. Örneğin A sütununda "Ad Soyad" varken, B sütununa sadece "Ad"ı yazarsanız, Excel diğer satırlar için de sadece adları ayırmak istediğinizi anlar ve öneride bulunur.

## 7. Kapsamlı Öğrenim Notları ve Sınav Hazırlık Özeti

Bu bölüm, "Öğrenim Notu Çıkartalım" talebine istinaden, ünitenin en kritik bilgilerini pedagojik bir yapıda özetlemektedir. Bilgiler, sınav hazırlığı ve hızlı tekrar için optimize edilmiştir.

### 7.1. Temel Kavramlar ve Kurallar (Mutlaka Bilinmesi Gerekenler)
*   **Formül Başlangıcı:** Her formül istisnasız **eşittir (=)** ile başlar. Başlamazsa Excel onu metin sanır.
*   **Dinamiklik İlkesi:** Formüllerde sayı (50+20) değil, **hücre adresi** (A1+B1) kullanılmalıdır. Bu sayede veriler değişince sonuç otomatik güncellenir.
*   **İşlem Önceliği:** Matematikteki sıra geçerlidir: Parantez $\rightarrow$ Üs $\rightarrow$ Çarpma/Bölme $\rightarrow$ Toplama/Çıkarma.
*   **Hücre Seçimi:**
    *   **:** (İki Nokta) = **ARALIK** (Başlangıçtan bitişe kadar hepsi).
    *   **;** (Noktalı Virgül) = **AYRIK** (Sadece seçilenler).

### 7.2. Fonksiyon Sözlüğü (Ne İşe Yarar?)

| Fonksiyon | Görevi | Örnek Formül | Kritik Not |
| :--- | :--- | :--- | :--- |
| **TOPLA** | Sayıları toplar. | `=TOPLA(A1:A10)` | Metinleri yok sayar. |
| **ORTALAMA** | Aritmetik ortalama alır. | `=ORTALAMA(A1:A10)` | Boş hücreleri hesaba katmaz, '0' yazanları katar. |
| **MAK** | En büyük sayıyı bulur. | `=MAK(A1:Z99)` | |
| **MİN** | En küçük sayıyı bulur. | `=MİN(A1:Z99)` | |
| **EĞERSAY** | Şarta uyanları sayar. | `=EĞERSAY(A1:A10;">50")` | **Kriter tırnak içinde olmalıdır!** |
| **EĞER** | Şarta göre karar verir. | `=EĞER(Not<50;"Kaldı";"Geçti")` | Mantıksal sınama doğruysa ilk değer, yanlışsa ikinci değer çalışır. |

### 7.3. Hata Kodları ve Anlamları
Excel'de karşılaşılması muhtemel hatalar ve çözümleri:
*   **##### Hatası:** Hücredeki sayı sütun genişliğine sığmıyor demektir. Sütunu genişleterek çözülür.
*   **#SAYI/0! Hatası:** Bir sayıyı sıfıra bölmeye çalışıyorsunuz (Matematiksel tanımsızlık).
*   **#AD? Hatası:** Fonksiyon adını yanlış yazdınız (Örn: TOPLA yerine TPLA).
*   **#DEĞER! Hatası:** Matematiksel bir işlemde metin kullanmaya çalışıyorsunuz (Örn: "Ali" + 5).
*   **#TAŞMA! (SPILL) Hatası:** Yeni dinamik dizi fonksiyonlarında (METİNAYIR vb.), sonucun yazılacağı hücrelerde veri var. O hücreleri temizleyerek çözülür.

### 7.4. Yeni Nesil Fonksiyonlar (Eşleştirme Tablosu)
Sınavlarda veya uygulamalarda eski ve yeni yöntemleri ayırt etmek için:

| İşlem | Eski Yöntem | Yeni Fonksiyon (Excel 2024) |
| :--- | :--- | :--- |
| **Metni Parçalama** | Metni Sütunlara Dönüştür | **METİNAYIR** |
| **Öncesini Alma** | SOLDAN + BUL | **ÖNCEKİMETİN** |
| **Sonrasını Alma** | SAĞDAN + BUL + UZUNLUK | **SONRAKİMETİN** |
| **Tablo Birleştirme** | Kopyala / Yapıştır | **DİKEYBİRLEŞTİR / YATAYBİRLEŞTİR** |
| **Resim Ekleme** | Ekle > Resim (Yüzen nesne) | **RESİM** (Hücre içi veri) |

## 8. Sonuç

Atatürk Üniversitesi Temel Bilgi Teknolojileri I dersinin bu ünitesi, katılımcılara sadece bir yazılımın arayüzünü değil, "yapılandırılmış veri işleme" disiplinini kazandırmayı amaçlamaktadır. Hesap tablolarında işlemler, basit dört işlemden başlayıp yapay zeka destekli çeviri ve veri madenciliği fonksiyonlarına kadar uzanan geniş bir yelpazedir.

Raporun ortaya koyduğu temel içgörü şudur: Excel yetkinliği, fonksiyonları ezberlemekten ziyade, "hangi problemin hangi fonksiyon kombinasyonuyla çözüleceğini kurgulama" becerisidir. Hücre referanslarını doğru kullanan, mantıksal fonksiyonlarla (EĞER) veri akışını yöneten ve yeni nesil dinamik fonksiyonlarla (METİNAYIR, VSTACK) veri temizleme süreçlerini otomatize eden bir kullanıcı, veriyi ham halden stratejik bilgiye dönüştürme gücüne sahiptir. Bu rapor, sağlanan PDF belgesindeki teorik çerçeveyi, modern Excel literatürünün pratik uygulamalarıyla birleştirerek, öğrencinin bu yetkinliğe ulaşması için gereken tüm enstrümanları detaylı bir şekilde sunmuştur.
