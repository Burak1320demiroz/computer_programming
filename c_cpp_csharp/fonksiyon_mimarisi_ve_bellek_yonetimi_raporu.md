# C++ Programlama Dilinde Fonksiyon Mimarisi, Bellek Yönetimi ve Modüler Tasarım: Kapsamlı Akademik Analiz ve Uygulama Analiz Raporu

## 1. Giriş ve Teorik Çerçeve
Yazılım mühendisliği disiplini, karmaşıklığın yönetilmesi üzerine kuruludur. Modern yazılım sistemleri, milyonlarca satır koddan oluşan devasa yapılardır ve bu yapıların tek bir blok halinde (monolitik) tasarlanması, geliştirilmesi ve bakımının yapılması insan bilişsel kapasitesinin sınırlarını aşar. Bu bağlamda, "böl ve yönet" (divide and conquer) prensibi, bilgisayar bilimlerinin en temel paradigmalarından biri olarak karşımıza çıkar. Bu prensibin programlama dillerindeki en somut karşılığı ise **Fonksiyonlar**dır. Atatürk Üniversitesi Açıköğretim Fakültesi Programlama Temelleri dersi kapsamında ele alınan "Fonksiyonlar" ünitesi 1, bu yapı taşlarının teorik ve pratik temellerini atmayı hedefler. Bu rapor, söz konusu ders materyalini temel alarak, C++ programlama dilinde fonksiyonların mimarisini, bellek yönetimindeki rollerini, parametre aktarım mekanizmalarının derinlemesine analizini ve mesleki yetkinliğe yönelik stratejik değerlendirmeleri kapsamlı bir şekilde sunmak amacıyla hazırlanmıştır.

Raporun temel amacı, sadece "kodun nasıl yazılacağını" göstermek değil, kodun derleyici ve işletim sistemi seviyesinde "nasıl çalıştığını" analiz etmektir. Özellikle, yığın (stack) bellek mimarisi, yaşam döngüsü (lifetime) ve kapsam (scope) kavramları arasındaki neden-sonuç ilişkileri, geliştiricilerin karşılaşabileceği karmaşık senaryoları çözümleyebilmeleri için detaylandırılmıştır. Literatürde yer alan akademik kaynaklar ve teknik dokümantasyonlar ışığında, fonksiyonların sadece birer kod kısaltma aracı olmadığı, aynı zamanda veri güvenliği, performans optimizasyonu ve sistem mimarisinin temel belirleyicisi olduğu ortaya konulmaktadır.

## 2. Modüler Programlama Paradigması ve Fonksiyonların Rolü

### 2.1. Monolitik Yapıdan Modülerliğe Geçiş
Programlamanın ilk dönemlerinde yazılan kodlar, genellikle doğrusal bir akış izleyen ve tüm işlemlerin tek bir ana blok içinde tanımlandığı yapılardı. Ancak programların kapsamı genişledikçe, bu yaklaşım "spagetti kod" olarak adlandırılan, takibi zor ve hataya açık yapıların oluşmasına neden olmuştur. Modüler programlama, bu sorunu çözmek için yazılımı bağımsız, yönetilebilir ve anlamlı parçalara ayırma disiplinidir. C++ dilinde bu modüllerin en küçük ve en işlevsel birimi fonksiyonlardır.

Fonksiyonlar, belirli bir görevi yerine getirmek üzere özelleşmiş, kendi yerel değişkenlerine ve mantıksal akışına sahip bağımsız kod bloklarıdır. Matematiksel fonksiyon kavramıyla ($f(x) \rightarrow y$) büyük benzerlik gösterirler; belirli bir girdiyi (input) alırlar, bir işlem sürecinden (process) geçirirler ve bir çıktı (output) üretirler. Ancak yazılım dünyasında fonksiyonlar, matematiksel tanımların ötesine geçerek, yan etkiler (side effects) oluşturabilir, sistem durumunu değiştirebilir ve dış kaynaklarla (dosya, ağ, donanım) etkileşime girebilirler.

### 2.2. Fonksiyonların Temel Karakteristikleri ve Avantajları
Ders materyalinde ve literatürde vurgulanan fonksiyon özellikleri, yazılım kalitesini doğrudan etkileyen faktörlerdir:

- **Soyutlama (Abstraction):** Fonksiyonlar, karmaşık işlemleri bir isim altında gizler. Programcı, `sqrt(x)` fonksiyonunu kullanırken Newton-Raphson yönteminin mi yoksa başka bir algoritmanın mı kullanıldığını bilmek zorunda değildir. Sadece ne girdi vereceğini ve ne çıktı alacağını bilmesi yeterlidir. Bu, bilişsel yükü azaltır.
- **Yeniden Kullanılabilirlik (Reusability):** Bir kez tanımlanan fonksiyon, projenin farklı yerlerinde veya farklı projelerde tekrar tekrar kullanılabilir. Bu, "Kendini Tekrar Etme" (Don't Repeat Yourself - DRY) prensibinin temelini oluşturur. Kod tekrarının önlenmesi, derlenen programın boyutunu (executable size) azaltmasa da kaynak kodun yönetimini kolaylaştırır.
- **Bakım Kolaylığı (Maintainability):** Bir algoritmada hata bulunduğunda veya iyileştirme yapılması gerektiğinde, değişikliğin sadece tek bir fonksiyon gövdesinde yapılması yeterlidir. Bu değişiklik, fonksiyonun çağrıldığı tüm noktaları otomatik olarak etkiler.
- **Kapsülleme ve Bağımsızlık:** Fonksiyonlar, kendi yerel değişkenlerine sahiptir. Bu değişkenler, fonksiyon dışındaki kodlardan izoledir. Bu özellik, değişken isimlendirme çakışmalarını önler ve veri güvenliğini artırır.

## 3. C++ Standart Kütüphane Mimarisi ve Hazır Fonksiyonlar
C++ dili, programcılara tekerleği yeniden icat ettirmemek adına son derece zengin bir Standart Kütüphane (Standard Template Library - STL ve C Standard Library) sunar. Profesyonel uygulamalarda ve mülakatlarda, bu kütüphanelerin hangi başlık dosyalarında (header files) bulunduğu, fonksiyonların prototipleri ve sınır durumları (edge cases) kritik önem taşır.

### 3.1. Giriş/Çıkış Yönetimi: `<iostream>`
C++'ın akış (stream) tabanlı giriş-çıkış mekanizmasıdır. Bu kütüphane, verinin kaynağından (klavye, dosya, ağ) hedefine (ekran, dosya) baytlar halinde akmasını sağlar.

- **`std::cout` (Character Output):** Tamponlanmış (buffered) standart çıktı akışıdır. `<<` (insertion) operatörü ile veriyi tampona yazar. Tampon dolduğunda veya `std::endl` gibi bir komut geldiğinde veriyi ekrana basar.
- **`std::cin` (Character Input):** Standart giriş akışıdır. `>>` (extraction) operatörü ile veriyi okur. Boşluk karakterlerini (boşluk, tab, yeni satır) ayırıcı olarak kullanır. Bu durum, boşluk içeren metinlerin okunmasında `std::getline` fonksiyonunun tercih edilmesini gerektirir.
- **`std::cerr`:** Tamponlanmamış hata akışıdır. Hata mesajlarının anında (program çökmeden önce) ekrana yansıması için kullanılır.
- **`std::clog`:** Tamponlanmış loglama akışıdır.

**Tablo 1: iostream Kütüphanesi Temel Nesneleri ve Görevleri**

| Nesne | Tip | Görev | İlişkili Operatör | Tamponlama |
|-------|-----|-------|-------------------|------------|
| `cout` | `ostream` | Normal veri çıktısı | `<<` | Var |
| `cin` | `istream` | Veri girişi | `>>` | Var |
| `cerr` | `ostream` | Hata mesajları | `<<` | Yok |
| `clog` | `ostream` | Log/Bilgi mesajları | `<<` | Var |

### 3.2. İleri Matematiksel Hesaplamalar: `<cmath>`
Matematiksel fonksiyonlar, genellikle işlemci seviyesindeki komutlara (FPU instructions) haritalanır. Bu kütüphanenin kullanımı sınavlarda sıkça sorulur, özellikle parametre tipleri ve dönüş değerleri konusunda dikkatli olunmalıdır.

- **Trigonometrik Fonksiyonlar (`sin`, `cos`, `tan`):** Bu fonksiyonlar parametre olarak derece değil, **radyan** cinsinden değer alır. Sıkça yapılan bir hata, doğrudan derece gönderilmesidir (`sin(90)` beklenen 1 sonucunu vermez). Dönüşüm için $Radyan = Derece \times (\pi / 180)$ formülü kullanılmalıdır.
- **Üstel ve Logaritmik Fonksiyonlar:**
    - `pow(base, exp)`: Tabanın üssünü alır. Dönüş tipi her zaman `double`'dır. Tamsayı aritmetiği beklenen durumlarda tip dönüşümü (casting) gerekebilir.
    - `sqrt(x)`: Karekök alır. Negatif değerler için "Domain Error" (Tanım Kümesi Hatası) üretir ve NaN (Not a Number) döndürür.
    - `log(x)`: Doğal logaritma ($\ln x$) hesaplar. 10 tabanında logaritma için `log10(x)` kullanılmalıdır.
- **Yuvarlama Fonksiyonları:**
    - `ceil(x)`: Tavana yuvarlar (kendisine eşit veya büyük en küçük tamsayı). Örn: `ceil(2.3)` $\to$ 3.0, `ceil(-2.3)` $\to$ -2.0. Negatif sayılarda sıfıra yaklaşır.
    - `floor(x)`: Tabana yuvarlar (kendisine eşit veya küçük en büyük tamsayı). Örn: `floor(2.8)` $\to$ 2.0, `floor(-2.8)` $\to$ -3.0. Negatif sayılarda sıfırdan uzaklaşır.
    - `round(x)`: En yakın tamsayıya yuvarlar. .5 durumlarında genellikle sıfırdan uzaklaşacak şekilde yuvarlar.

### 3.3. Metin Manipülasyonu: `<string>` ve `<cctype>`
Modern C++, C-stili karakter dizileri (`char`) yerine daha güvenli ve yetenekli `std::string` sınıfını kullanır.

- **`length()` / `size()`:** String'in karakter sayısını döner. `\0` (null terminator) karakterini saymaz.
- **`substr(pos, len)`:** Belirli bir konumdan başlayarak istenen uzunlukta alt metin alır. Eğer `pos` string boyutunu aşarsa hata fırlatır.
- **`find(str)`:** Aranan alt metnin başladığı ilk indeksi döner. Bulamazsa `string::npos` (genellikle -1'in unsigned karşılığı) döner.

**Karakter Analizi (`<cctype>`):** Tek bir karakterin tipini sorgular.
- `isalpha(c)`: Harf mi?
- `isdigit(c)`: Rakam mı?
- `isspace(c)`: Boşluk karakteri mi?
- `toupper(c)` / `tolower(c)`: Karakter dönüşümü yapar.

### 3.4. Rastgelelik ve Zaman: `<cstdlib>` ve `<ctime>`
Simülasyon ve oyun programlamada kullanılan bu fonksiyonlar, deterministik bilgisayar sistemlerinde sözde-rastgelelik (pseudo-randomness) üretir.

- **`rand()`:** 0 ile `RAND_MAX` (genellikle 32767 veya daha büyük) arasında bir tamsayı üretir. Ancak, program her çalıştığında aynı sayı dizisini üretir. Bu, deterministik yapının bir sonucudur ve hata ayıklama (debugging) için yararlıdır.
- **`srand(seed)`:** Rastgele sayı üretecini bir tohum (seed) değeriyle başlatır. Gerçek rastgelelik hissi yaratmak için tohum olarak genellikle o anki zaman (`time(0)`) kullanılır.

> [!IMPORTANT]
> **Kritik Bilgi:** `srand` fonksiyonu programın başında sadece bir kez çağrılmalıdır. Bir döngü içinde sürekli çağrılırsa (örneğin her milisaniyede), `time(0)` değeri değişmeyeceği için `rand()` sürekli aynı sayıyı üretir.

## 4. Kullanıcı Tanımlı Fonksiyon Mimarisi
Kullanıcı tanımlı fonksiyonlar, programcının dilin yeteneklerini genişletmesini sağlar. Bir fonksiyonun tanımlanması, bellekte o fonksiyon için bir kod segmentinin ayrılması ve giriş-çıkış arayüzünün belirlenmesi demektir.

### 4.1. Fonksiyon Prototipi ve Tanımlama Ayrımı
C++ derleyicisi (compiler), kodu yukarıdan aşağıya doğru okur (single-pass compilation mantığına yakın). Eğer bir fonksiyon, tanımlandığı satırdan önce çağrılırsa derleyici hata verir. Bunu çözmek için **Fonksiyon Prototipi** (Function Prototype) veya Bildirimi (Declaration) kullanılır.

- **Prototip:** Fonksiyonun imzasını (signature) derleyiciye bildirir. Dönüş tipi, fonksiyon adı ve parametre tiplerini içerir. Parametre isimlerinin yazılması zorunlu değildir ancak okunabilirlik için önerilir. Noktalı virgül `;` ile biter.
  - Örnek: `double Hesapla(int, double);`
- **Tanımlama (Definition):** Fonksiyonun gövdesini `{...}` içeren tam kodudur. Bellekte yer kaplar.

### 4.2. Parametre Aktarım Mekanizmaları (Parameter Passing)
Bu bölüm, C++ mülakatlarının en ayırt edici ve kavramsal derinliği en yüksek konusudur. Verinin fonksiyona nasıl aktarıldığı, bellek kullanımı, performans ve veri güvenliği açısından kritik sonuçlar doğurur.

#### 4.2.1. Değer ile Aktarım (Pass by Value)
Varsayılan aktarım yöntemidir.
- **Mekanizma:** Fonksiyon çağrıldığında, argümanların değerleri kopyalanarak fonksiyonun yığın (stack) bellek alanındaki parametrelerine atanır.
- **Bellek Etkisi:** Orijinal verinin boyutu kadar ek bellek kullanılır. Eğer büyük bir nesne (örneğin 10.000 elemanlı bir vektör) değer ile aktarılırsa, tüm elemanlar tek tek kopyalanır (deep copy). Bu, ciddi bir performans kaybıdır.
- **Veri Güvenliği:** Fonksiyon, verinin kopyası üzerinde çalıştığı için, fonksiyon içinde yapılan değişiklikler çağıran koddaki (caller) orijinal veriyi etkilemez. Yan etkisizdir (side-effect free).
- **Kullanım Senaryosu:** `int`, `double`, `char` gibi küçük temel veri tipleri için uygundur.

#### 4.2.2. Referans ile Aktarım (Pass by Reference)
Parametre tipinin sonuna `&` işareti eklenerek belirtilir.
- **Mekanizma:** Fonksiyona verinin kopyası değil, bellekteki adresi (veya o adrese bağlı bir takma ad/alias) gönderilir. Teknik olarak, arka planda genellikle sabit bir işaretçi (const pointer) gibi davranır ancak sözdizimi daha temizdir.
- **Bellek Etkisi:** Veri boyutu ne olursa olsun, sadece bellek adresi (32-bit sistemde 4 byte, 64-bit sistemde 8 byte) taşınır. Kopyalama maliyeti yoktur.
- **Veri Güvenliği:** Fonksiyon, orijinal bellek alanına doğrudan erişir. Fonksiyon içinde yapılan her değişiklik, orijinal değişkeni kalıcı olarak değiştirir. Bu durum "yan etki" (side effect) yaratır.
- **Const Referans (`const Type&`):** Hem performansı korumak (kopyalama yok) hem de veri güvenliğini sağlamak (değişiklik yapılamaz) için kullanılır. Büyük nesnelerin okunması (read-only) gereken durumlarda standarttır.

#### 4.2.3. İşaretçi ile Aktarım (Pass by Pointer)
C dilinden miras kalan yöntemdir. Parametre olarak adres (`*`) bekler ve çağırırken değişkenin adresi (`&`) gönderilir.
- **Fark:** Referanslar oluşturulurken bir nesneye bağlanmalı ve asla null olamaz. İşaretçiler ise `nullptr` olabilir ve çalışma zamanında farklı nesnelere yönlendirilebilir (re-seating). Mülakatlarda işaretçi aritmetiği ve `nullptr` kontrolü soruları bu başlık altında gelir.

### 4.3. Dönüş Değerleri ve void
Fonksiyonlar `return` ifadesi ile çağıran noktaya değer döndürür. `return` ifadesi çalıştırıldığında fonksiyon o noktada sonlanır.
`void` fonksiyonlar değer döndürmez, ancak `return;` komutu ile erken sonlandırılabilirler.
C++'da bir fonksiyonun referans döndürmesi (`int& func()`) de mümkündür, ancak yerel bir değişkenin referansını döndürmek, "Dangling Reference" (Sarkan Referans) hatasına yol açar ve tanımsız davranış (undefined behavior) oluşturur.

## 5. Değişken Kapsamı (Scope) ve Bellek Ömrü (Lifetime)
Değişkenlerin nerede erişilebilir olduğu (Scope) ve bellekte ne kadar süre kaldığı (Lifetime), programın hatasız çalışması için hayati öneme sahiptir.

### 5.1. Kapsam Türleri
- **Yerel Kapsam (Local Scope):** Bir blok `{}` içinde tanımlanan değişkenlerdir. Sadece o blok içinde görünürler. Blok sonlandığında yığın belleğinden (stack) silinirler (Automatic Storage Duration).
- **Global Kapsam (Global Scope):** Tüm fonksiyonların dışında tanımlanır. Program başladığında belleğin "Data Segment"ine yerleşir ve program bitene kadar orada kalır. Her yerden erişilebilir.
- **Gölgeleme (Variable Shadowing):** İç içe bloklarda, içteki blokta tanımlanan bir değişken, dıştaki blokta veya global alanda bulunan aynı isimli değişkeni "gölgeler". İç blokta o isme erişildiğinde, en yerel olan değişken kullanılır. Global değişkene erişmek için `::` (Scope Resolution Operator) kullanılmalıdır.

### 5.2. Statik Yerel Değişkenler (static)
Normal yerel değişkenler fonksiyon her çağrıldığında yeniden oluşturulur ve sıfırlanır. Ancak `static` anahtar kelimesi ile tanımlanan yerel değişkenler:
1. Sadece ilk çağrıda oluşturulur (initialize).
2. Fonksiyon sonlansa bile bellekteki değerini korur (Static Storage Duration).
3. Programın sonuna kadar yaşar.
4. Ancak kapsamı (scope) hala sadece tanımlandığı fonksiyon içindedir.

Bu yapı, bir fonksiyonun kaç kez çağrıldığını saymak veya durum bilgisini (state) korumak için idealdir.

## 6. Fonksiyon Aşırı Yükleme (Function Overloading)
C++, aynı isme sahip birden fazla fonksiyon tanımlanmasına izin verir. Buna "Function Overloading" denir. Bu özellik, polimorfizmin (çok biçimlilik) derleme zamanındaki (compile-time) bir formudur.

### 6.1. Ayırt Edici Faktörler (Fonksiyon İmzası)
Derleyici, aynı isimli fonksiyonları birbirinden ayırmak için "Fonksiyon İmzası"na (Function Signature) bakar. İmza şunları içerir:
- Fonksiyon Adı.
- Parametre Sayısı.
- Parametre Tipleri.
- Parametrelerin Sırası.

> [!NOTE]
> **Önemli Not:** Dönüş tipi (Return Type) imzaya dahil değildir. Sadece dönüş tipi farklı olan iki fonksiyon tanımlanamaz (`int f(int)` ve `double f(int)` aynı anda olamaz). Çünkü çağıran kod `f(5)` dediğinde, hangi dönüş tipini beklediği belirsiz olabilir.

### 6.2. Belirsizlik (Ambiguity) Sorunları
Aşırı yükleme sırasında, derleyicinin hangi fonksiyonu seçeceğine karar veremediği durumlar oluşabilir.

**Örnek:**
```cpp
void Test(int a);
void Test(float a);

// Çağrı:
Test(3.5); // HATA!
```
Burada `3.5` bir `double` sabitidir. `double`, hem `int`'e hem de `float`'a dönüşebilir. Derleyici hangisinin daha "uygun" olduğuna karar veremez ve "Ambiguous Call" hatası verir. Çözüm için `Test(3.5f)` veya `Test((int)3.5)` gibi açık dönüşüm yapılmalıdır.

## 7. Özyinelemeli (Recursive) Fonksiyonlar
Bir fonksiyonun kendi kendini çağırması işlemine özyineleme (recursion) denir. Karmaşık problemlerin (faktöriyel, Fibonacci, ağaç dolaşımı) daha küçük alt problemlere bölünerek çözülmesini sağlar.

### 7.1. Özyineleme Mimarisi
Her özyinelemeli çağrı, yığın bellekte (stack) yeni bir "Stack Frame" (Aktivasyon Kaydı) oluşturur. Bu kayıt, o anki parametreleri, yerel değişkenleri ve geri dönüş adresini saklar.

Özyinelemenin iki temel bileşeni vardır:
1. **Temel Durum (Base Case):** Özyinelemenin durduğu ve sonucun doğrudan döndüğü en basit durumdur. Base case olmazsa "Sonsuz Özyineleme" oluşur ve stack dolarak "Stack Overflow" hatasına neden olur.
2. **Özyineleme Adımı (Recursive Step):** Problemin daha küçük bir parçasını çözmek için fonksiyonun kendisini çağırdığı kısımdır.

## 8. Uygulama Analiz Modülü: Örnek Durumlar
Aşağıdaki bölüm, ders materyalindeki boşluğu doldurmak amacıyla, literatür taraması sonucu elde edilen verilerle oluşturulmuş kapsamlı bir durum analizi bankasıdır.

### 8.1. Kavramsal Durum Analizleri

**Durum 1:** Aşağıdaki parametre aktarım yöntemlerinden hangisi, hem büyük veri yapılarının kopyalanma maliyetini önler hem de orijinal verinin fonksiyon tarafından değiştirilmesini garanti altına alarak engeller?
- A) `void Fonk(int x)` (Pass by Value)
- B) `void Fonk(int &x)` (Pass by Reference)
- C) `void Fonk(const int &x)` (Pass by Const Reference)
- D) `void Fonk(int *x)` (Pass by Pointer)
- E) `int Fonk()`

**Analiz ve Sonuç:** Doğru yaklaşım **C** seçeneğidir.
- A şıkkı kopyalama yapar (maliyetli).
- B şıkkı değişikliğe izin verir (güvensiz).
- D şıkkı işaretçi kullanır, adres kopyalanır ama işaret edilen veri değiştirilebilir (eğer `const int*` değilse).
- C şıkkı, `&` ile adresi alarak kopyalamayı önler, `const` ile de veri üzerinde yazma işlemini (read-only yapar) engeller. Modern C++'ta büyük nesneler için standart yöntemdir.

**Durum 2:** `inline` fonksiyonların temel amacı ve potansiyel dezavantajı nedir?
- A) Özyinelemeyi sağlamak / Stack taşması.
- B) Fonksiyon çağırma maliyetini düşürmek / Kod boyutunun büyümesi (Code Bloat).
- C) Global değişkenlere erişimi engellemek / Performans kaybı.
- D) Derleme süresini kısaltmak / Çalışma zamanı hatası.
- E) Veri gizliliği sağlamak / Bellek sızıntısı.

**Analiz ve Sonuç:** Doğru yaklaşım **B** seçeneğidir.
`inline`, derleyiciye fonksiyon kodunu çağrıldığı yere kopyalaması talimatını verir. Bu, işlemcinin "jump" komutuyla fonksiyon adresine gitmesi, stack frame oluşturması gibi maliyetleri (overhead) yok eder. Ancak, kodun her çağrıldığı yere kopyalanması, programın boyutunu (binary size) artırabilir, bu da önbellek (cache) verimliliğini düşürebilir.

**Durum 3:** Aşağıdaki kod parçasında "Variable Shadowing" (Değişken Gölgeleme) mekanizması nasıl işler ve çıktı ne olur?

```cpp
int x = 50; // Global
int main() {
    int x = 10; // Yerel 1
    {
        int x = 20; // Yerel 2 (İç blok)
        cout << x << " " << ::x << " ";
    }
    cout << x;
    return 0;
}
```
- A) 20 20 10
- B) 20 50 10
- C) 10 50 10
- D) 20 50 20
- E) 50 50 50

**Analiz ve Sonuç:** Doğru seçenek **B**'dir.
1. İç blokta `cout << x` çağrıldığında, en yakın (most local) kapsamdaki `x` (Yerel 2, değeri 20) kullanılır.
2. `::x` operatörü, tüm yerel kapsamları atlayarak doğrudan global `x`'e (50) erişir.
3. Blok bittiğinde Yerel 2 bellekten silinir. Dış bloktaki `cout << x`, kendi kapsamındaki `x`'i (Yerel 1, değeri 10) görür.

### 8.2. Kod İzleme (Code Tracing) Çalışmaları

**Durum 4: Statik Değişken ve Referans Analizi**

```cpp
#include <iostream>
using namespace std;

int& Sayac() {
    static int count = 0;
    count++;
    return count;
}

int main() {
    cout << Sayac() << " ";
    int &ref = Sayac();
    ref = 10;
    cout << Sayac() << endl;
    return 0;
}
```

**Çözüm Adımları:**
1. İlk `Sayac()` çağrısı: `static count` 0'dan başlatılır (sadece bir kez). `count` 1 olur. Fonksiyon count değişkeninin referansını (kendisini) döndürür. Çıktı: 1.
2. İkinci `Sayac()` çağrısı: `count` hafızada 1 idi, 2 olur. `ref` referansı şimdi statik `count` değişkenine bağlandı.
3. `ref = 10`: `ref`, `count` değişkeninin takma adı olduğu için, `count` değişkeni 10 yapılır.
4. Üçüncü `Sayac()` çağrısı: `count` en son 10 idi. 1 artar ve 11 olur.
**Sonuç Çıktısı:** `1 11`.

**Durum 5: Varsayılan Argümanlar ve Çağrı Sırası**

```cpp
void Test(int a = 1, int b = 2, int c = 3) {
    cout << a + b + c << endl;
}
int main() {
    Test();
    Test(5);
    Test(5, 5);
    Test(5, 5, 5);
    return 0;
}
```

**Çözüm Adımları:**
1. `Test()`: Hiç argüman yok. Hepsi varsayılan değerleri alır. 1 + 2 + 3 = 6.
2. `Test(5)`: İlk parametre `a` 5 olur. `b` ve `c` varsayılan kalır. 5 + 2 + 3 = 10.
3. `Test(5, 5)`: `a` ve `b` 5 olur. `c` varsayılan kalır. 5 + 5 + 3 = 13.
4. `Test(5, 5, 5)`: Hepsi 5 olur. 5 + 5 + 5 = 15.
**Çıktı:**
```
6
10
13
15
```

### 8.3. Kritik Uyarılar
- **Geriye Değer Döndürme:** `int` tanımlı bir fonksiyonda `return` unutulursa, çoğu modern derleyici uyarı verir ancak bazı durumlarda program çalışmaya devam edip rastgele (garbage) bir değer üretebilir (Undefined Behavior).
- **Dizi Parametreleri:** Diziler (`int arr`) fonksiyonlara her zaman adres (pointer) olarak geçer. Yani varsayılan olarak referans gibi davranırlar. Fonksiyon içinde dizinin bir elemanını değiştirmek, orijinal diziyi değiştirir. Dizinin boyutu parametre olarak ayrıca gönderilmelidir, çünkü `sizeof(arr)` fonksiyon içinde sadece pointer boyutunu (4 veya 8 byte) verir, dizinin toplam boyutunu vermez.

## 9. Sonuç ve Öneriler
Bu rapor, C++ fonksiyonlarının sadece sözdizimsel kurallarını değil, altında yatan bellek ve işlem mimarisini de ortaya koymuştur. Konuya hakimiyet için geliştiricilerin;
- Parametre aktarımında "Değer" ve "Referans" arasındaki farkı bellek diyagramları çizerek çalışması,
- `static` ve global değişkenlerin yaşam sürelerini kod izleme egzersizleriyle pekiştirmesi,
- Standart kütüphane fonksiyonlarının (`cmath`, `string`) dönüş tiplerine hakim olması gerekmektedir.

Fonksiyonlar, modüler programlamanın temelidir ve bu konudaki yetkinlik, sadece "Programlama Temelleri" dersi için değil, gelecekteki Nesne Yönelimli Programlama (OOP) ve Veri Yapıları dersleri için de kritik bir ön koşuldur.
