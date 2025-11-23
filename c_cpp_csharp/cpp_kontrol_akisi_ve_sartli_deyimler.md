# C++ Programlama Dilinde Kontrol Akışı Yönetimi: İlişkisel ve Mantıksal Operatörler ile Şartlı Deyimlerin Kapsamlı Analizi ve Uygulama Prensipleri

## Yönetici Özeti

Bu araştırma raporu, Atatürk Üniversitesi Açıköğretim Fakültesi Programlama Temelleri dersi kapsamında sunulan "İlişkisel ve Mantıksal Operatörler ve Şartlı Deyimler" başlıklı 6. Ünite ders notlarını temel alarak, C++ programlama dilindeki karar verme mekanizmalarını derinlemesine analiz etmek amacıyla hazırlanmıştır. Rapor, belirtilen kaynak belgenin içeriğini (ilişkisel operatörler, mantıksal bağlaçlar, if, if-else, switch-case yapıları) merkeze alırken, bu kavramları bilgisayar bilimlerinin teorik temelleri, bellek yönetimi, derleyici optimizasyonları ve endüstriyel kodlama standartları bağlamında genişletmektedir.

Programlama, özünde verilerin işlenmesi ve bu verilerin anlık durumlarına göre akışın yönlendirilmesi sanatıdır. Sıralı (sequential) akışın ötesine geçerek, koşullara bağlı dallanmalar (branching) yaratabilmek, yazılımın "zekasını" oluşturan temel unsurdur. Bu raporda, C++ dilinin sunduğu operatörlerin matematiksel temellerinden başlayarak, karmaşık karar ağaçlarının oluşturulmasına kadar uzanan süreç, akademik bir titizlikle ve genişletilmiş bir perspektifle ele alınmıştır.

## 1. Giriş ve Ünite Hedefleri

Programlama dillerinin evriminde, kodun satır satır yukarıdan aşağıya çalıştırıldığı doğrusal yapıdan, duruma göre farklı kod bloklarının icra edildiği yapısal ve nesne yönelimli paradigmalara geçiş, yazılımın karmaşık problemleri çözebilme kapasitesini artırmıştır. Belgede detaylandırılan bu ünite, öğrencilere ve geliştiricilere, program akışını kontrol etme yetkinliği kazandırmayı hedeflemektedir.

### 1.1. Ünitenin Temel Kazanımları

Belgede belirtilen hedefler doğrultusunda, bu raporun ve ilgili çalışma alanının temel kazanımları şu şekilde kategorize edilebilir:

- **Operatör Yetkinliği**: İlişkisel ve mantıksal operatörlerin sadece sözdizimsel (syntax) olarak değil, anlamsal (semantic) ve işlevsel olarak kavranması. İki veri birimi arasındaki ilişkinin (büyüklük, eşitlik vb.) sayısal olarak nasıl temsil edildiğinin anlaşılması.

- **Koşullu İfade Mimarisi**: Bu operatörleri kullanarak, gerçek hayat senaryolarını (örneğin: "Yaş 18'den büyükse oy kullanabilir") simüle eden if, if-else ve else-if bloklarının doğru kurgulanması.

- **Çoklu Seçim Yönetimi**: switch-case yapısının, karmaşık if-else merdivenlerine alternatif olarak nasıl, ne zaman ve neden kullanıldığının, performans ve okunabilirlik açısından değerlendirilmesi.

- **Algoritmik Düşünme**: Programlarda karar yapıları kurarak, farklı durumlara (state) göre farklı işlemlerin yapılmasını sağlayan dinamik algoritmaların geliştirilmesi.

### 1.2. Karar Verme Mekanizmasının Doğası

C++ dilinde (ve genel olarak Turing-tamamlanmış dillerde) karar verme, işlemcinin (CPU) durum bayraklarını (status flags) kontrol ederek program sayacını (program counter) belleğin farklı bir bölgesine yönlendirmesi işlemidir. Bu işlem, yüksek seviyeli dillerde "Şartlı Deyimler" olarak soyutlanır. Belgede vurgulandığı üzere, bu ifadeler bir veya daha fazla koşulu değerlendirir ve bir kod bloğunun çalıştırılıp çalıştırılmayacağına karar verir. Bu mekanizma, yazılımın statik bir metin olmaktan çıkıp, kullanıcı etkileşimlerine ve veri değişimlerine tepki veren dinamik bir yapıya dönüşmesini sağlar.

## 2. İlişkisel Operatörler: Karşılaştırmanın Matematiği

İlişkisel operatörler, programlamada iki değerin (işlenenin/operand) birbirine göre durumunu kıyaslayan ve bu kıyaslama sonucunda mantıksal bir değer üreten araçlardır. C++ dilinde bu operatörler, aritmetik işlemler kadar temel bir yere sahiptir. Bir programın herhangi bir noktasında "Bu değer diğerinden büyük mü?", "Şifreler eşleşiyor mu?" veya "Sayaç sınıra ulaştı mı?" sorularının cevabı bu operatörlerle verilir.

### 2.1. İlişkisel Operatörlerin Sınıflandırılması ve Tanımları

Belgede sunulan Tablo 6.1 ve kaynağındaki veriler ışığında, C++ dilindeki altı temel ilişkisel operatörün teknik analizi aşağıdaki tabloda detaylandırılmıştır:

**Tablo 1: C++ İlişkisel Operatörleri**

| Operatör Adı | Sembol | Matematiksel Gösterim | İşlevsel Tanım ve Davranış Modeli | Örnek Durum (a=10, b=5) | Döndürülen Değer (C++ Karşılığı) |
|-------------|--------|----------------------|----------------------------------|------------------------|--------------------------------|
| Eşittir | == | a=b | İki işlenenin değerlerinin bitsel veya sayısal olarak eşit olup olmadığını kontrol eder. | a == b | 0 (False) |
| Eşit Değildir | != | a≠b | İki işlenenin değerlerinin birbirinden farklı olup olmadığını kontrol eder. | a != b | 1 (True) |
| Büyüktür | > | a>b | Sol işlenenin değerinin sağ işlenenden büyük olup olmadığını kontrol eder. | a > b | 1 (True) |
| Küçüktür | < | a<b | Sol işlenenin değerinin sağ işlenenden küçük olup olmadığını kontrol eder. | a < b | 0 (False) |
| Büyük veya Eşittir | >= | a≥b | Sol işlenenin değerinin sağ işlenenden büyük veya ona eşit olup olmadığını kontrol eder. | a >= b | 1 (True) |
| Küçük veya Eşittir | <= | a≤b | Sol işlenenin değerinin sağ işlenenden küçük veya ona eşit olup olmadığını kontrol eder. | a <= b | 0 (False) |

### 2.2. Eşitlik (==) ve Atama (=) Operatörleri Arasındaki Kritik Fark

Programlamaya yeni başlayanların ve hatta deneyimli geliştiricilerin dahi zaman zaman düştüğü en büyük tuzaklardan biri, atama operatörü (=) ile eşitlik operatörünün (==) karıştırılmasıdır. Belgede bu konuya "Önemli Not" başlığı altında özel bir vurgu yapılmıştır.

**Atama Operatörü (=)**: Bu operatör, sağ taraftaki ifadenin (r-value) değerini hesaplar ve sol taraftaki değişkene (l-value) yazar. İşlemin sonucu, atanan değerdir.

**Eşitlik Operatörü (==)**: Bu operatör, iki değerin eşitliğini sorgular ve sonucu değiştirmeden sadece bir doğruluk değeri (0 veya 1) üretir.

**Hatalı Kullanım Analizi**:

```cpp
int x = 5;
if (x = 10) { 
    // Bu blok HER ZAMAN çalışır.
    // Çünkü (x = 10) işlemi x'e 10 değerini atar ve işlemin sonucu 10 olur.
    // C++'ta 0 olmayan her değer "True" kabul edildiği için koşul sağlanır.
}
```

**Doğru Kullanım Analizi**:

```cpp
int x = 5;
if (x == 10) {
    // Bu blok çalışmaz çünkü x, 10'a eşit değildir.
    // (x == 10) işlemi 0 (False) sonucunu üretir.
}
```

Bu tür hataların önüne geçmek için modern programlama pratiklerinde "Yoda Koşulları" (Yoda Conditions) adı verilen bir teknik önerilebilir. Sabit değerin sol tarafa yazılması (`if (10 == x)`), yanlışlıkla = kullanılması durumunda (`if (10 = x)`) derleyicinin hata vermesini sağlar, çünkü sabit bir değere atama yapılamaz.

### 2.3. C++'ta Doğruluk Değerlerinin Temsili

C++ dilinin erken versiyonlarında (C dili mirasıyla), özel bir boolean veri türü bulunmamaktaydı. Bunun yerine tamsayılar (integer) kullanılırdı. Belgedeki örneklerde de görüldüğü üzere:

- **Yanlış (False)**: Sayısal 0 değeri ile temsil edilir.

- **Doğru (True)**: 0 dışındaki herhangi bir tamsayı (genellikle 1) ile temsil edilir.

Modern C++ standartlarında bool veri türü bulunsa da, ilişkisel operatörlerin çıktıları hala bu tarihsel mirasla uyumlu çalışır. Belgedeki kod örneğinde:

```cpp
cout << "a > b: " << (a > b) << endl; 
```

ifadesinin çıktısı `a > b: 1` şeklindedir. Bu, C++'ın arka planda mantıksal doğruluğu sayısal 1 olarak işlediğini kanıtlar. Bu durum, mantıksal işlemlerin aritmetik işlemlerle karıştırılabilmesine (örneğin `true + true = 2`) olanak tanır ki bu da dilin esnek ama hataya açık yapılarından biridir.

### 2.4. Kod Üzerinde Uygulamalı Analiz

Belgede verilen kod örneği, operatörlerin çalışma mantığını somutlaştırmaktadır. `int a=6, b=4` değişkenleri üzerinden yapılan analiz şöyledir:

- **a == b**: 6, 4'e eşit değildir. Sonuç 0 (False).

- **a > b**: 6, 4'ten büyüktür. Sonuç 1 (True).

- **a >= b**: 6, 4'ten büyüktür (eşitlik şartı aranmaz). Sonuç 1 (True).

- **a < b**: 6, 4'ten küçüktür ifadesi yanlıştır. Sonuç 0 (False).

- **a <= b**: 6, 4'ten küçük veya eşit değildir. Sonuç 0 (False).

- **a != b**: 6, 4'ten farklıdır. Sonuç 1 (True).

Bu çıktıların her biri, işlemcinin aritmetik mantık biriminde (ALU) yapılan bir çıkarma işleminin sonucundaki bayraklara (Zero Flag, Carry Flag vb.) dayanır. Örneğin, CMP A, B komutu işlemcide çalıştırıldığında, eğer sonuç sıfırsa == operatörü True döner.

## 3. Mantıksal Operatörler: Karmaşık Koşulların İnşası

Gerçek dünya problemleri nadiren tek bir değişkenin kontrolü ile çözülebilir. Genellikle birden fazla koşulun bir arada değerlendirilmesi gerekir (Örneğin: "Kullanıcı adı doğruysa VE şifre geçerliyse sisteme gir"). Mantıksal operatörler, birden fazla ilişkisel önermeyi birleştirerek daha karmaşık mantıksal yapılar kurmamızı sağlar.

### 3.1. Mantıksal Operatörlerin Tanımları ve Doğruluk Tabloları

Belgedeki Tablo 6.2'ye göre C++'ta üç temel mantıksal operatör bulunur. Bunlar Boolean cebirinin temel taşlarıdır.

#### 3.1.1. Mantıksal VE (&& - Logical AND)

**Tanım**: İkili (binary) bir operatördür. İşlenenlerden her ikisi de doğru (sıfırdan farklı) ise sonuç 1 (doğru) döner. Aksi takdirde 0 (yanlış) döner.

**Kullanım Amacı**: Bir işlemin gerçekleşmesi için tüm şartların sağlanması gerektiği durumlarda kullanılır. "Hem bu, hem şu" mantığıdır.

**Doğruluk Tablosu**:

| İşlenen 1 (p) | İşlenen 2 (q) | Sonuç (p && q) |
|--------------|--------------|----------------|
| 0 (Yanlış) | 0 (Yanlış) | 0 |
| 0 (Yanlış) | 1 (Doğru) | 0 |
| 1 (Doğru) | 0 (Yanlış) | 0 |
| 1 (Doğru) | 1 (Doğru) | 1 |

**Belgeden Örnek**: a=6, b=4 için `(a && b)` ifadesi. Hem 6 hem de 4 sıfırdan farklı olduğu için (True), sonuç 1 olur.

#### 3.1.2. Mantıksal VEYA (|| - Logical OR)

**Tanım**: İkili bir operatördür. İşlenenlerden en az biri doğru (sıfırdan farklı) ise sonuç 1 (doğru) döner. Sadece her iki işlenen de yanlışsa sonuç 0 olur.

**Kullanım Amacı**: Bir işlemin gerçekleşmesi için alternatif şartlardan herhangi birinin yeterli olduğu durumlarda kullanılır. "Ya bu, ya şu (veya ikisi de)" mantığıdır.

**Doğruluk Tablosu**:

| İşlenen 1 (p) | İşlenen 2 (q) | Sonuç (p \|\| q) |
|--------------|--------------|------------------|
| 0 (Yanlış) | 0 (Yanlış) | 0 |
| 0 (Yanlış) | 1 (Doğru) | 1 |
| 1 (Doğru) | 0 (Yanlış) | 1 |
| 1 (Doğru) | 1 (Doğru) | 1 |

**Belgeden Örnek**: a=6, b=4 için `(a || b)` ifadesi. Herhangi biri (veya ikisi) doğru olduğu için sonuç 1 olur.

#### 3.1.3. Mantıksal DEĞİL (! - Logical NOT)

**Tanım**: Tekli (unary) bir operatördür. İşlenenin mantıksal değerini tersine çevirir. Doğruyu yanlışa, yanlışı doğruya dönüştürür.

**Kullanım Amacı**: Bir koşulun sağlanmadığı durumları kontrol etmek için kullanılır.

**Doğruluk Tablosu**:

| İşlenen (p) | Sonuç (!p) |
|------------|-----------|
| 0 (Yanlış) | 1 (Doğru) |
| 1 (Doğru) | 0 (Yanlış) |

**Belgeden Örnek**: b=4 (True) olduğu için `(!b)` ifadesi mantıksal tersini alır ve 0 (False) sonucunu üretir.

### 3.2. Kısa Devre (Short-Circuit) Değerlendirme Prensibi

Mantıksal operatörlerin C++ dilindeki en önemli özelliklerinden biri "Kısa Devre Değerlendirme" (Short-Circuit Evaluation) prensibidir. Bu özellik performans optimizasyonu ve kod güvenliği açısından kritiktir.

**VE (&&) İşleminde**: Sol taraftaki ifade Yanlış ise, sağ taraftaki ifadeye bakılmaksızın sonuç Yanlış olacaktır. Bu nedenle derleyici sağ tarafı çalıştırmaz.

**Örnek**: `if (x != 0 && y/x > 1)` -> Eğer x sıfırsa, ilk koşul yanlış olur ve ikinci kısımdaki bölme işlemi yapılmaz. Böylece "sıfıra bölme hatası" (divide by zero logic error) engellenmiş olur.

**VEYA (||) İşleminde**: Sol taraftaki ifade Doğru ise, sağ taraftaki ifadeye bakılmaksızın sonuç Doğru olacaktır. Derleyici sağ tarafı çalıştırmaz.

**Örnek**: `if (isAdmin || checkDatabase())` -> Eğer kullanıcı admin ise, veritabanı kontrolü gibi maliyetli bir fonksiyonun çalıştırılmasına gerek kalmaz.

Bu özellik, mantıksal operatörlerin sadece birer matematiksel işlem değil, aynı zamanda birer "akış kontrol" mekanizması olduğunu gösterir.

### 3.3. Operatör Önceliği ve Parantez Kullanımı

Matematikte olduğu gibi programlamada da işlem önceliği vardır. Kaynakta belirtildiği üzere, ilişkisel operatörler mantıksal operatörlerden önce değerlendirilir. Ancak && operatörü || operatöründen daha yüksek önceliğe sahiptir.

Örneğin `A || B && C` ifadesi, öncelik kuralları gereği `A || (B && C)` şeklinde yorumlanır. Eğer programcının niyeti `(A || B) && C` ise, mutlaka parantez kullanmalıdır. Belge ve genel programlama etiği, okunabilirlik ve hata riskini azaltmak için karmaşık ifadelerde her zaman parantez kullanılmasını önermektedir.

## 4. Şartlı Deyimler: Programın Karar Mekanizmaları

İlişkisel ve mantıksal operatörler bize "ham maddeyi" (True/False değerlerini) sağlar. Şartlı deyimler ise bu ham maddeyi kullanarak programın hangi yoldan gideceğini belirleyen "yol ayrımlarıdır". Belgede bu yapılar "Kontrol Akışı İfadeleri" başlığı altında incelenmiş ve Tablo 6.3 ile özetlenmiştir.

### 4.1. Kontrol Akışının Doğası ve goto Uyarısı

Programlar varsayılan olarak sıralı çalışır. Kontrol akış ifadeleri bu sırayı değiştirir. Belgede goto deyimine özel bir parantez açılmış ve "okunamayan ve hataya açık kod oluşturma potansiyeli nedeniyle genellikle önerilmez" uyarısı yapılmıştır. Modern programlama paradigmalarında goto, yapısal bütünlüğü bozan (spagetti kod) bir unsur olarak görülür ve yerini if, for, while, switch gibi yapısal bloklara bırakmıştır.

### 4.2. if Koşul İfadesi: Tek Yönlü Karar

En temel karar yapısıdır. Bir koşulun doğruluğuna bağlı olarak bir kod bloğunun çalıştırılmasını sağlar.

**Sözdizimi**:

```cpp
if (koşul) {
    // Koşul doğru (True/1) ise çalışacak kodlar
}
```

**Çalışma Mantığı**: Program if satırına geldiğinde parantez içindeki ifadeyi değerlendirir. Sonuç sıfırdan farklıysa blok içine girer, aksi takdirde bloğu atlar.

**Belgeden Örnek**:

```cpp
int yas = 19;
if (yas > 18) {
    cout << "oy kullanabilir";
}
```

Bu örnekte 19 > 18 önermesi doğru olduğu için ekrana çıktı verilir.

**Sözdizimsel Detay**: Eğer çalıştırılacak komut tek satırsa süslü parantez {} kullanımı zorunlu değildir. Ancak belgede ve endüstriyel standartlarda, kodun genişletilebilirliği ve hatasızlığı için her zaman parantez kullanılması tavsiye edilir.

### 4.3. if-else Koşul İfadesi: Çift Yönlü Karar

Bir koşulun doğru olması durumunda bir bloğu, yanlış olması durumunda ise başka bir bloğu çalıştırmak için kullanılır. "Ya o, ya bu" mantığıdır.

**Sözdizimi**:

```cpp
if (koşul) {
    // Doğruysa çalışır
} else {
    // Yanlışsa çalışır
}
```

**Çalışma Mantığı**: İki bloktan yalnızca biri çalışır. İkisinin aynı anda çalışması veya ikisinin de çalışmaması (yapısal olarak) mümkün değildir.

**Belgeden Örnek**: Bir sayının pozitiflik kontrolü.

```cpp
if (n > 0) cout << "sayi pozitiftir.";
else cout << "sayi pozitif değildir.";
```

Burada else kısmı, n'in 0'a eşit olduğu veya negatif olduğu durumları kapsar.

### 4.4. if-else-if Merdiveni: Çok Yönlü Karar

İkiden fazla olasılığın olduğu durumlarda kullanılır. Koşullar yukarıdan aşağıya doğru sırayla kontrol edilir. Doğru olan ilk koşulun bloğu çalıştırılır ve yapının geri kalanı atlanır.

**Belgeden Örnek**: Yaş kategorizasyonu.

- `if (yas < 13)` -> "Çocuk"
- `else if (yas >= 13 && yas <= 18)` -> "Büyüme çağında"
- `else` -> "Yetişkin"

**Önemli Nüans**: Sıralama hayati önem taşır. Eğer en genel koşul en başa yazılırsa, diğer özel koşullara asla sıra gelmeyebilir (Mantıksal maskeleme hatası). Ayrıca bu yapıda else bloğu, yukarıdaki hiçbir koşulun sağlanmadığı durumlar için "varsayılan" (default) bir çıkış kapısı görevi görür.

### 4.5. İç İçe (Nested) Koşul İfadeleri

Bir karar bloğunun içinde başka karar bloklarının yer almasıdır. Karmaşık ve hiyerarşik kararlar için kullanılır.

**Belgeden Örnek**: Sayı analizi.

- **Ana Blok**: Sayı pozitif mi? (n > 0)
  - **İç Blok**: Sayı çift mi? (n % 2 == 0) -> "Pozitif ve Çift"
  - **İç Blok Else**: -> "Pozitif ve Tek"
- **Ana Blok Else-If**: Sayı sıfır mı? (n == 0) -> "Sayı 0"
- **Ana Blok Else**: -> "Negatif"

**Tasarım Uyarısı**: Çok derin iç içe yapılar kodun okunabilirliğini düşürür. Bu duruma "Arrow Code" (Ok Ucu Kodu) denir. Mümkün olduğunca mantıksal operatörlerle (&&) koşulları birleştirmek veya switch yapısını kullanmak daha temiz kod yazımını sağlar.

## 5. Switch-Case İfadesi: Seçimli Yapı

Bir değişkenin alabileceği belirli sabit değerlere göre program akışını yönlendiren bir yapıdır. Özellikle menü sistemlerinde veya ayrık (discrete) değerlerin kontrolünde if-else-if yapısına göre daha okunaklı ve bazen daha performanslı bir alternatiftir.

### 5.1. Yapısal Bileşenler ve Kurallar

- **Switch İfadesi**: Parantez içindeki ifade (`switch(degisken)`) mutlaka tamsayı tabanlı (int, char, enum) bir sonuç üretmelidir. C++ standardı gereği string veya float değerler doğrudan switch ile kullanılamaz.

- **Case Etiketleri**: Her durum case anahtar kelimesi ve bir sabit değerle belirtilir (`case 1:`, `case 'A':`). Bu değerler derleme zamanında bilinen sabitler olmalıdır.

- **Break Komutu**: En kritik bileşendir. İlgili case bloğu çalıştıktan sonra switch yapısından çıkılmasını sağlar. Eğer break unutulursa, program bir sonraki case bloğuna girer. Buna "Fall-through" (aşağı düşme) denir. Bazen bilinçli kullanılsa da, genellikle bir hatadır.

- **Default Etiket**: if-else yapısındaki else gibi çalışır. Hiçbir case değeri eşleşmezse bu blok çalışır. Hata yönetimi (örn: "Geçersiz giriş") için kullanılması önerilir.

### 5.2. Switch vs If-Else Karşılaştırması

Aşağıdaki tablo, bu iki yapının farklarını ve kullanım alanlarını özetlemektedir:

**Tablo 2: Switch-Case vs If-Else-If Karşılaştırması**

| Özellik | Switch-Case | If-Else-If |
|---------|------------|-----------|
| Koşul Türü | Sadece eşitlik (==) kontrolü yapar. | Her türlü mantıksal ve ilişkisel koşulu (>, <, &&) kontrol edebilir. |
| Veri Türü | Sadece tamsayı ve karakter tabanlı veriler. | Tüm veri türleri (float, string, nesneler). |
| Performans | Çok sayıda durum (case) olduğunda derleyici "Jump Table" (Sıçrama Tablosu) oluşturarak O(1) erişim sağlayabilir. | Durum sayısına bağlı olarak doğrusal (lineer) bir arama yapar (O(n)). |
| Okunabilirlik | Çok sayıda sabit değer kontrolünde daha temizdir. | Karmaşık koşullarda daha esnektir. |

### 5.3. Belgeden Örnek Analizi

Belgede karakter tabanlı bir örnek verilmiştir:

```cpp
char c = 'B';
switch(c) {
    case 'A': cout << "Programlamayi Seviyorum"; break;
    case 'B': cout << "AtauniAOF"; break; // Çıktı burası olur
    default: cout << "gecersiz giris";
}
```

Bu örnekte c değişkeni 'B' olduğu için program doğrudan ikinci case'e atlar, çıktıyı verir ve break ile yapıdan çıkar. Eğer break olmasaydı default bloğundaki mesaj da ekrana basılacaktı.

## 6. Sonuç ve Özet Notlar

Bu rapor referans belgesi ve ek araştırmalar ışığında C++ dilindeki kontrol yapılarını detaylandırmıştır. Özetle:

- **İlişkisel Operatörler** (==, !=, <, >, <=, >=): Verilerin birbirine göre durumunu belirler. 0 (yanlış) veya 1 (doğru) döner. Atama (=) ile karıştırılmamalıdır.

- **Mantıksal Operatörler** (&&, ||, !): Koşulları birleştirir. Kısa devre değerlendirme özelliği performansı artırır ve hataları önler.

- **Şartlı Deyimler**:
  - **if**: Tek koşul.
  - **if-else**: İki alternatif.
  - **if-else-if**: Çoklu, öncelikli alternatifler.
  - **switch-case**: Sabit değerlere dayalı, performanslı çoklu seçim.

C++ dilinde yetkin bir programcı olabilmek için bu operatörlerin bellek üzerindeki etkilerini (örn: short-circuiting), işlemci seviyesindeki karşılıklarını (flag registers) ve kodun okunabilirliği üzerindeki etkilerini (nested if vs switch) iyi kavramak gerekmektedir. Atatürk Üniversitesi ders materyalleri, bu temeli atmak için gerekli teorik ve pratik bilgiyi sunmakta; bu rapor ise söz konusu bilgiyi profesyonel bir çerçeveye oturtmaktadır.

## 7. Ek: Ünite Değerlendirme Soruları Analizi

Belgenin sonunda yer alan değerlendirme soruları, konunun anlaşılma düzeyini ölçmek için kritiktir. Raporda işlenen konular ışığında bu soruların analizi:

**Soru 1 (== amacı)**: Cevap C (Değerlerin eşitliğini karşılaştırmak). Atama değil, kıyaslama yapar.

**Soru 2 (Yanlış operatör)**: Cevap E (=). Bu bir ilişkisel operatör değil, atama operatörüdür. (Not: =< da C++'ta geçersizdir, doğru yazım <= şeklindedir ancak şıklarda = temel kavramsal hata olarak sorulmuştur).

**Soru 3 (VEYA operatörü)**: Cevap B (||).

**Soru 4 (Mantıksal ifade sonucu)**: Cevap D (Doğrudur/1 döner). x=5, y=10 için (5<10) True VE (10>5) True -> Sonuç True.

**Soru 5 (! operatörü)**: Cevap D (Mantıksal değeri tersine çevirir).

**Soru 6 (if çalışmama durumu)**: Cevap C (x=0 olduğunda). C++'ta 0, False anlamına gelir ve blok çalışmaz.

**Soru 7 (Çoklu koşul)**: Cevap E (else if). Çoklu ve sıralı koşullar için en uygun yapıdır.

**Soru 8 (Switch zorunluluğu)**: Cevap B (case). Switch yapısının içinde en az bir durum veya yapısal olarak case blokları beklenir (Syntax açısından zorunlu olmasa da mantıksal olarak switch'in amacı budur).

**Soru 9 (default işlevi)**: Cevap B (Hiçbir koşul sağlanmazsa çalışır).

**Soru 10 (Dönüş türü)**: Cevap A (int 0 veya 1). C++'ın temel yapısında mantıksal sonuçlar tamsayı olarak döner.

