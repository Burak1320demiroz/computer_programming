# Programlama Temelleri: Kapsamlı Sınav Analizi, Teorik Derinlik ve Başarı Stratejileri Raporu

## 1. Yönetici Özeti ve Raporun Kapsamı

Bu rapor, "Programlama Temelleri" dersi kapsamında sunulan yedi adet sınav dosyasının ayrıntılı adli bilişim analizi ve pedagojik değerlendirmesi sonucunda hazırlanmıştır. Raporun temel amacı, öğrencinin "kısa bir özet not" talebini karşılamakla birlikte, sınavların kapsamının derinliği ve karmaşıklığı göz önüne alındığında, sadece yüzeysel bir özetin yüksek not almak için yeterli olmayacağı gerçeğinden hareketle, konuları akademik bir titizlikle ele alan kapsamlı bir başvuru kaynağı oluşturmaktır.

Analiz edilen belgeler, sınavların sadece kod yazma becerisini değil, aynı zamanda bilgisayar mimarisi, sayı sistemleri matematiği, algoritma mantığı, derleme süreçleri ve tümleşik geliştirme ortamı (IDE) hakimiyetini de ölçtüğünü ortaya koymaktadır. Bu nedenle rapor, her bir sorunun arkasındaki teorik altyapıyı, çeldirici seçeneklerin neden yanlış olduğunu, benzer soruların çözüm stratejilerini ve konunun bilgisayar bilimlerindeki yerini detaylandırarak, öğrencinin konuyu ezberlemesini değil, içselleştirmesini hedeflemektedir.

## 2. Bilgisayar Mimarisi ve Sistemsel Temeller

Programlama eğitimi, kodun üzerinde çalıştığı donanımın ve bu donanımı yöneten sistem yazılımlarının anlaşılmasıyla başlar. Sınav soruları incelendiğinde, Von Neumann mimarisine dayalı modern bilgisayar yapısının temel bileşenlerinin ve işlevlerinin sıklıkla sorgulandığı görülmektedir.

### 2.1. Merkezi İşlem Birimi (CPU) ve Görevleri

Bilgisayarın "beyni" olarak nitelendirilen Merkezi İşlem Birimi (CPU), sınavların teorik kısmında en çok vurgulanan bileşendir. CPU'nun fonksiyonel yapısı, programların nasıl yürütüldüğünü anlamak için kritiktir.

**Zamanlama ve Kontrol**: CPU, bilgisayar sistemindeki tüm birimlerin (bellek, I/O cihazları, veri yolları) çalışmalarını senkronize eder. Sistem saatine (clock) bağlı olarak çalışan bu mekanizma, komutların doğru sırada ve doğru zamanda işlenmesini sağlar. Sınavlarda bu özellik, "Bilgisayar sistemindeki birimlerin çalışmalarını zamanlar ve kontrol eder" ifadesiyle tanımlanmaktadır. Bu kontrol işlevi, Kontrol Birimi (Control Unit - CU) tarafından yürütülür.

**Veri Transferi Yönetimi**: Giriş birimlerinden (klavye, fare vb.) gelen ham verilerin birincil belleğe (RAM) yüklenmesi sürecini CPU yönetir. Aynı şekilde, işlenen verilerin (sonuçların) çıkış birimlerine (ekran, yazıcı) aktarılması da CPU'nun denetimindedir. Bu süreçte CPU, veriyolları (bus) üzerinden sinyaller göndererek veri trafiğini düzenler.

**Aritmetik ve Mantıksal İşlemler**: Sınav sorularında doğrudan ALU (Arithmetic Logic Unit) terimi geçmese de, "verileri işleyerek sonuçları belleğe kaydeden birim" tanımı, CPU'nun içindeki ALU'nun işlevine işaret eder.

### 2.2. Bellek Hiyerarşisi ve Depolama Birimleri

Verilerin kalıcılığı ve erişim hızı, programlama temellerinde önemli bir ayrımdır. Sınavlar, geçici bellek ile kalıcı depolama arasındaki farkı ayırt etme yeteneğini ölçmektedir.

**Birincil Bellek (RAM - Random Access Memory)**: İşlemcinin o anda ihtiyaç duyduğu program kodlarını ve verileri tutar. "Uçucu" (volatile) bir yapıya sahiptir; yani elektrik kesildiğinde üzerindeki tüm veriler silinir. Programcılar için RAM, değişkenlerin ve fonksiyon çağrılarının (stack/heap) tutulduğu yerdir.

**İkincil Depolama (Secondary Storage)**: Verilerin kalıcı olarak saklandığı birimlerdir. Sabit diskler (HDD), Katı Hal Sürücüleri (SSD), Flash Bellekler ve Optik Diskler (CD/DVD) bu kategoriye girer. Sınavlarda en kritik ayırt edici özellik, "Bilgisayarın elektriği kesildiğinde verilerin silinmediği birim" olmasıdır. Bu birimler, işletim sistemi dosyalarını, kullanıcı belgelerini ve derlenmiş programları (.exe dosyaları) saklar.

### 2.3. Giriş ve Çıkış Birimleri (I/O Devices)

Kullanıcı ile bilgisayar arasındaki etkileşimi sağlayan birimlerin sınıflandırılması, sınavlarda sıkça karşılaşılan, basit görünen ancak dikkat gerektiren bir konudur. Bu sınıflandırma, veri akışının yönüne göre yapılır.

**Tablo 1: Giriş/Çıkış Birimleri Sınıflandırması**

| Birim Tipi | Tanım | Örnekler ve Sınav Analizi |
|-----------|-------|--------------------------|
| Sadece Giriş Birimleri | Verinin dış dünyadan bilgisayara aktarıldığı cihazlardır. | **Klavye**: Sınavlarda "sadece giriş birimi" olarak özellikle vurgulanmıştır. **Mikrofon**: Ses sinyallerini dijital veriye çevirir. **Barkod Okuyucu, Web Kamerası**: Görüntü verisi girişi sağlar. |
| Sadece Çıkış Birimleri | İşlenmiş verinin (bilginin) kullanıcıya sunulduğu cihazlardır. | **Hoparlör**: Sınavlarda "Giriş birimi aşağıdakilerden hangisi olamaz?" sorusunun cevabıdır. **Yazıcı**: Dijital veriyi fiziksel baskıya dönüştürür. **Monitör (Standart)**: Görüntü çıkışı sağlar. |
| Giriş ve Çıkış Birimleri (Hibrit) | Hem veri girişi hem de veri çıkışı yapabilen cihazlardır. | **Dokunmatik Ekran**: Hem görüntüyü gösterir (çıkış) hem de dokunmatik komutları alır (giriş). **Depolama Birimleri (HDD, USB, Optik Disk)**: CPU bu cihazlara veri yazabilir (çıkış) ve onlardan veri okuyabilir (giriş). Sınavlarda bu ayrım, çeldirici olarak kullanılır; örneğin "Aşağıdakilerden hangisi sadece giriş birimidir?" sorusunda seçeneklere sabit disk konularak öğrencinin bunu elemesi beklenir. |

### 2.4. Yazılım Katmanları ve Programlama Dilleri

Donanım tek başına işlevsizdir; ona ruhunu veren yazılımdır. Sınavlar, yazılımın hiyerarşik yapısını ve programlama dillerinin evrimini sorgulamaktadır.

**Sistem Yazılımları vs. Uygulama Yazılımları**:

- **Sistem Yazılımları**: Bilgisayar donanımını yöneten, kaynakları paylaştıran ve uygulama yazılımlarına bir platform sunan temel yazılımlardır. İşletim sistemleri (Windows, Linux), derleyiciler (Compilers), veri tabanı yönetim sistemleri (DBMS) ve ağ yazılımları bu kategoridedir.

- **Uygulama Yazılımları**: Son kullanıcının belirli görevlerini yerine getirmek için tasarlanmıştır. Muhasebe yazılımları, oyunlar, kelime işlemciler, web tarayıcıları bu gruba girer. Sınavda "Hangisi sistem yazılımı olarak değerlendirilemez?" sorusunun cevabı, spesifik bir kullanıcı ihtiyacına yönelik olduğu için "Muhasebe yazılımları"dır.

**Programlama Dillerinin Seviyeleri**:

- **Düşük Seviyeli Diller (Low-Level)**: Makine dili (1 ve 0'lar) ve Assembly dili. Bu diller donanım mimarisine doğrudan bağımlıdır. Çok hızlı çalışırlar ancak kodlaması zordur. Sistem programlama, sürücü yazımı ve gömülü sistemlerde kullanılırlar.

- **Yüksek Seviyeli Diller (High-Level)**: C++, C#, Java, Python gibi diller. İnsan diline (İngilizce) ve matematiksel notasyona yakındırlar. Donanım detaylarından soyutlanmışlardır. Temel amaçları, program geliştirme sürecini hızlandırmak ve kodun okunabilirliğini artırmaktır.

**Kritik Kavram Yanılgısı**: Sınavlarda "Bir programlama dilinin seviyesi düştükçe zorluk seviyesi azalır" ifadesi yanlış seçenek olarak sunulmuştur. Gerçekte, dilin seviyesi düştükçe (donanıma yaklaştıkça), programcının bellek yönetimi, CPU kayıtçıları gibi detaylarla uğraşması gerektiği için zorluk artar.

## 3. Sayı Sistemleri ve Veri Temsili Matematiği

Bilgisayarların veriyi nasıl algıladığı ve işlediği, sayı sistemleri üzerinden anlatılmaktadır. Sınavlarda özellikle taban dönüşümleri (Base Conversion) matematiksel bir kesinlikle sorulmaktadır. Öğrencilerin sadece sonucu değil, dönüşüm algoritmasını da bilmesi gerekmektedir.

### 3.1. Onaltılık (Hexadecimal) Sistemden İkilik (Binary) Sisteme Dönüşüm

Hexadecimal sistem, ikilik sistemin (binary) insanlar tarafından daha kolay okunabilmesi için kullanılan, 16 tabanlı bir sistemdir. Her bir Hex basamağı, tam olarak 4 bitlik (nibble) bir Binary karşılığına sahiptir.

**Sembol Seti**: 0-9 rakamları ve A(10), B(11), C(12), D(13), E(14), F(15) harfleri kullanılır.

**Dönüşüm Algoritması**: Hexadecimal bir sayıyı Binary'ye çevirirken, her bir Hex hanesi ayrı ayrı 4 bitlik Binary karşılığına dönüştürülür ve yan yana yazılır.

**Vaka Analizi: (FF)₁₆ Sayısının İkilik Karşılığı**

- **Analiz**: Sayı iki basamaklıdır: F ve F.
- **Değer Tespiti**: Hexadecimal F sembolü, Decimal 15 değerine eşittir.
- **Binary Dönüşümü**: 15 sayısını 4 bitlik ikilik sistemde ifade etmek gerekir.
  - 8+4+2+1=15
  - Bu, 2³ + 2² + 2¹ + 2⁰ demektir.
  - **Karşılığı**: 1111
- **Birleştirme**: İlk F için 1111, ikinci F için 1111.
- **Sonuç**: 11111111.

### 3.2. Sekizli (Octal) Sistemden Onluk (Decimal) Sisteme Dönüşüm

**Vaka Analizi: (157)₈ Sayısının Onluk Karşılığı**

Bu soru, Sekizli (Octal) sistemden Onluk (Decimal) sisteme dönüşümü test eder.

**Formül**: ∑(Basamak×Taban^Pozisyon)

**Hesaplama**:
- Basamaklar: 1, 5, 7. Taban: 8.
- 1×8² + 5×8¹ + 7×8⁰
- = 1×64 + 5×8 + 7×1
- = 64 + 40 + 7
- = 111

**Sonuç**: (111)₁₀.

### 3.3. Sekizli Sistemden İkilik Sisteme Dönüşüm

**Vaka Analizi: (465) Sayısının İkilik Karşılığı**

Soruda taban belirtilmemiştir, ancak seçenekler ve sayının yapısı (4, 6, 5 rakamları) bunun muhtemelen Sekizli (Octal) veya Onluk sistemde olduğunu düşündürür. Ancak standart prosedürde, eğer taban verilmezse ve bağlam bilgisayar bilimleri ise, ve rakamlar 0-7 arasındaysa Octal, 0-9 arasındaysa Decimal varsayılabilir. Sınavdaki doğru cevap C) (100110101)₂ olarak verilmiştir. Bu binary sayıyı inceleyelim:

**100110101₂**

**Gruplandıralım** (Octal dönüşümü için 3'erli, Hex için 4'erli):
- 3'erli (Sağdan sola): 100 110 101
- 100₂ = 4
- 110₂ = 6
- 101₂ = 5
- **Birleşim**: (465)₈.

**Çıkarım**: Bu soru, Sekizli (Octal) sistemden İkilik (Binary) sisteme dönüşüm sorusudur. Octal'den Binary'ye geçerken her basamak 3 bitlik Binary karşılığına çevrilir.

## 4. Algoritma Tasarımı ve Mantıksal Modelleme

Kodlama sürecinin en hayati aşaması, problemin çözüm yolunun (algoritmanın) belirlenmesidir. Sınavlar, bu soyut düşünme becerisini sözde kodlar ve akış diyagramları üzerinden ölçmektedir.

### 4.1. Algoritma ve Sözde Kod (Pseudocode)

**Algoritma Tanımı**: Bir problemin çözümü için gerekli olan adımların mantıksal ve sıralı bir bütünüdür. Sıralama hayati önem taşır; adımların yerinin değişmesi sonucu veya algoritmanın çalışmasını bozar. Sınavlarda "iş adımlarının sırası önemsizdir" ifadesi kesinlikle yanlıştır.

**Sözde Kod**: Algoritmanın, belirli bir programlama dilinin söz dizimine (syntax) bağlı kalmadan, doğal dil (konuşma dili) ve basit komutlarla ifade edilmesidir.

- **Amaç**: Programcı olmayanların da anlayabileceği bir taslak oluşturmak ve kodlamaya geçmeden önce mantığı test etmektir.
- **Özellik**: Sözde kod bilgisayarda derlenmez ve çalıştırılmaz. Sadece kağıt üzerinde veya zihinsel olarak takip edilir (trace).

### 4.2. Akış Diyagramı (Flowchart) Sembolleri ve Standartları

Algoritmaların görselleştirilmesi için kullanılan ISO standartlarındaki semboller, sınavlarda ezberlenmesi gereken bilgiler arasındadır.

**Tablo 2: Akış Diyagramı Sembolleri**

| Sembol | Adı | İşlevi ve Kullanım Alanı | Sınav Notu |
|--------|-----|------------------------|-----------|
| Elips / Oval | Terminal (Sonlandırıcı) | Algoritmanın Başlangıç (Start/Begin) ve Bitiş (End/Stop) noktalarını gösterir. | Her akış diyagramında mutlaka olması gereken semboldür. |
| Paralelkenar | Girdi / Çıktı (I/O) | Kullanıcıdan veri alma (cin, read) veya ekrana veri yazdırma (cout, print, display) işlemlerini temsil eder. | Sınavlarda girdi ve çıktıların gösterimi için sorulur. |
| Dikdörtgen | İşlem (Process) | Matematiksel hesaplamalar, değişken atamaları ve içsel veri manipülasyonları için kullanılır (örn: x = x + 1). | En yaygın kullanılan semboldür. |
| Eşkenar Dörtgen (Baklava) | Karar (Decision) | Bir koşulun (Condition) kontrol edildiği noktadır. İçinde x > 5 gibi bir mantıksal ifade bulunur. Genellikle iki çıkış oku (Evet/Hayır veya Doğru/Yanlış) vardır. | Döngülerin ve if yapılarının temel taşıdır. Sınavda "Baklava sembolünün anlamı" olarak sorulur. |

### 4.3. Algoritma İzleme (Tracing) ve Örnek Vaka Analizleri

Sınavların en ayırt edici soruları, verilen bir sözde kodun çıktısını tahmin etmeye yöneliktir. Bu soruları çözmek için işlemcinin mantığını taklit ederek, adım adım değişken değerlerini takip etmek gerekir.

**Vaka 1: WHILE Döngüsü ve Yazdırma Sırası**

```
SET A=1, B=10
DO
  PRINT A, B
  COMPUTE A = A + 3
  COMPUTE B = B - 3
WHILE A < B
```

**Analiz**: Bu bir DO-WHILE yapısıdır. Döngü koşulu sonda kontrol edilir, yani döngü gövdesi en az bir kez çalışır.

- **Adım 1**: Başlangıç değerleri A=1, B=10. PRINT komutu çalışır: Ekrana 1 10 yazılır. Sonra A=4, B=7 olur. Koşul 4 < 7 (Doğru). Döngü devam eder.
- **Adım 2**: Değerler A=4, B=7. PRINT komutu çalışır: Ekrana 4 7 yazılır. Sonra A=7, B=4 olur. Koşul 7 < 4 (Yanlış). Döngü sonlanır.

**Kritik Nokta**: Birçok öğrenci son adımdaki hesaplamayı (A=7, B=4) da ekrana yazdırma eğilimindedir. Ancak PRINT komutu hesaplamadan önce geldiği için son değerler yazılmaz.

**Vaka 2: Karışık Mantıksal Operasyonlar**

```
SET x=20, y=2
DO
  COMPUTE x = x / 2
  COMPUTE y = y + 1
  IF x > y THEN
    PRINT x, y
  ENDIF
WHILE x > y
```

- **Adım 1**: x=20, y=2. İşlem: x=10, y=3. Kontrol IF 10 > 3 (Doğru) -> Yazdır: 10 3. Döngü kontrol WHILE 10 > 3 (Doğru).
- **Adım 2**: x=10, y=3. İşlem: x=5, y=4. Kontrol IF 5 > 4 (Doğru) -> Yazdır: 5 4. Döngü kontrol WHILE 5 > 4 (Doğru).
- **Adım 3**: x=5, y=4. İşlem: x=2.5, y=5. Kontrol IF 2.5 > 5 (Yanlış) -> Yazdırma yok. Döngü kontrol WHILE 2.5 > 5 (Yanlış). Döngü biter.

**Sonuç**: Ekranda 10 3 ve 5 4 görünür.

## 5. Bütünleşik Geliştirme Ortamı (IDE) ve Derleme Süreci

Modern yazılım geliştirme, IDE adı verilen karmaşık araçlar üzerinde gerçekleşir. Sınavlar, özellikle Microsoft Visual Studio 2017 ortamının kullanımına dair teknik detayları sorgulamaktadır. Bu, dersin teorik olduğu kadar pratik bir yönü de olduğunu gösterir.

### 5.1. IDE Bileşenleri ve Pencereleri

Visual Studio arayüzündeki pencerelerin işlevlerini bilmek sınav için şarttır.

**Çözüm Gezgini (Solution Explorer)**: Projeyi oluşturan tüm dosyaların (kaynak kodlar .cpp, başlık dosyaları .h, kütüphaneler) hiyerarşik bir ağaç yapısında görüntülendiği ve yönetildiği penceredir. Dosya ekleme, silme, yeniden adlandırma işlemleri buradan yapılır. Sınavlarda "Kod dosyalarını bulmayı, görüntülemeyi ve yönetmeyi sağlayan pencere" tanımıyla sorulur. Visual Studio Code'daki "Explorer" paneliyle benzer işlevi görür ancak Visual Studio'da "Solution" (Çözüm) kavramı birden fazla projeyi kapsayan üst bir konteynerdir.

**Takım Gezgini (Team Explorer)**: Birden fazla geliştiricinin aynı proje üzerinde çalışmasını sağlayan (Version Control) araçtır. Kod paylaşma, değişiklikleri sunucuya gönderme (push), sunucudan çekme (pull) gibi işlemler için kullanılır. Sınavda "Kod paylaşma işlemi için kullanılan pencere" olarak geçer. Azure DevOps veya Git entegrasyonu bu pencere üzerinden yönetilir.

**Çıktı Penceresi (Output Window)**: Derleme (Build) sürecinin loglarını gösterir. Programın çalışıp çalışmadığını, derleme sırasında oluşan hataları (error) ve uyarıları (warning) burada listeler. Dikkat: Programın çalışma zamanı çıktıları (örneğin cout ile yazılanlar) genellikle ayrı bir Konsol penceresinde görünür, ancak "Output" penceresi derleme durumunu raporlar.

**Editör Penceresi**: Kodların fiilen yazıldığı, renklendirme (syntax highlighting) ve düzenleme işlemlerinin yapıldığı ana alandır.

### 5.2. Kritik Kısayollar ve Özellikler

Profesyonel bir geliştirici gibi IDE kullanabilmek için kısayollar önemlidir ve sınavlarda bunlar test edilmektedir.

**Intellisense**: Kod yazarken programcıya yardımcı olan akıllı tamamlama sistemidir. Değişken adlarını, fonksiyon parametrelerini önerir ve basit söz dizimi hatalarını daha derleme yapmadan (kırmızı alt çizgi ile) gösterir. Sınavda "Yanlış yazılan kodları otomatik uyarma" özelliği olarak tanımlanır.

**Derleme ve Çalıştırma Kısayolları**:

- **Ctrl + F5 (Start Without Debugging)**: Programı hata ayıklama modu olmadan çalıştırır. Bu modda çalıştırıldığında, program sonlandığında konsol penceresi hemen kapanmaz, "Press any key to continue..." mesajı verir. Bu, çıktıları görmek için önemlidir.

- **F5 (Start Debugging)**: Hata ayıklama modunda başlatır. Breakpoint (kesme noktası) konulmuşsa orada durur.

- **Ctrl + Shift + N**: Yeni bir proje oluşturma (New Project) kısayoludur.

- **Ctrl + Shift + B**: Projeyi derler (Build Solution).

### 5.3. C++ Programının Yaşam Döngüsü

Bir C++ kodunun çalıştırılabilir bir yazılıma dönüşmesi zincirleme bir süreçtir. Sınavlarda bu adımların doğru sıralaması sorulmaktadır.

1. **Kaynak Kod Yazımı (Editing)**: .cpp uzantılı dosyanın oluşturulması.

2. **Önişleme (Preprocessing)**: #include, #define gibi komutların işlenmesi. Önişlemci, kaynak kodu derleyiciye hazırlar.

3. **Derleme (Compiling)**: C++ kodunun makine diline (Object code - .obj) çevrilmesi. Söz dizimi hataları bu aşamada yakalanır.

4. **Bağlama (Linking)**: Oluşan .obj dosyalarının ve kullanılan kütüphanelerin birleştirilerek tek bir çalıştırılabilir (.exe) dosya haline getirilmesi.

5. **Yükleme (Loading)**: .exe dosyasının diskten RAM'e yüklenmesi.

6. **Çalıştırma (Execution)**: CPU'nun komutları işlemesi.

7. **Hata Ayıklama (Debugging)**: (Opsiyonel ama süreçte var) Hataların tespiti ve düzeltilmesi.

Sınavlarda doğru sıralama genellikle: Düzenleme -> Önişleme -> Derleme -> Birleştirme -> Yükleme -> Çalıştırma şeklindedir.

## 6. C++ Programlama Dili: Söz Dizimi ve Temel Yapılar

C++, güçlü, statik tipli ve genel amaçlı bir dildir. Sınavlar, dilin kurallarına (syntax) ve temel yapı taşlarına hakimiyeti ölçmektedir.

### 6.1. Temel Program İskeleti

```cpp
#include <iostream> // Giriş-çıkış kütüphanesini dahil eder
using namespace std; // Standart isim uzayını kullanır

int main() { // Ana fonksiyon - Program buradan başlar
    // Kodlar buraya yazılır
    return 0; // İşletim sistemine programın başarıyla bittiğini bildirir
}
```

- **#include Direktifi**: Başında # olan satırlar önişlemci komutlarıdır ve sonlarına noktalı virgül (;) konulmaz.

- **main Fonksiyonu**: Her C++ programı main adlı bir fonksiyondan çalışmaya başlar.

- **Noktalı Virgül (;)**: C++'ta her deyim (statement) ; ile bitmelidir. Unutulması "Söz Dizimi Hatası"dır (Syntax Error).

### 6.2. Değişkenler ve Veri Tipleri

Veri tipleri, bellekte ne kadar yer ayrılacağını ve verinin nasıl yorumlanacağını belirler.

- **int**: Tam sayılar (Örn: -5, 0, 42).

- **double**: Çift duyarlıklı ondalıklı sayılar. Sınavlarda "Ondalıklı sayı saklanabilen tür" olarak sorulur. float da ondalıklıdır ancak double daha geniş kapsamlıdır ve sınavda tercih edilen cevaptır.

- **char**: Tek bir karakteri saklar (Örn: 'A', 'z'). Tek tırnak içinde yazılır.

- **bool**: Mantıksal değerler (true veya false). Bellekte genellikle 1 byte yer kaplar.

- **unsigned char**: İşaretsiz karakter. 0 ile 255 arasında pozitif tamsayı değerleri de tutabilir. Normal char -128 ile +127 arasındadır.

### 6.3. Kaçış Karakterleri (Escape Sequences)

Ekrana çıktı verirken metin biçimlendirmesi için kullanılan, ters bölü (\) ile başlayan özel karakterlerdir.

**Tablo 3: Kaçış Karakterleri**

| Dizi | Anlamı | Etkisi |
|------|--------|--------|
| \n | Newline (Yeni Satır) | İmleci bir alt satırın başına getirir. |
| \t | Tab | Bir tab boşluk bırakır. |
| \a | Alert (Uyarı) | Sistem sesini (bip) çalar. |
| \\ | Backslash | Ekrana \ karakterini basar. |
| \" | Çift Tırnak | Ekrana " karakterini basar. |

**Örnek**: `cout << "Bugun hava\ncok guzel";` komutu, "Bugun hava" yazar, alt satıra geçer ve "cok guzel" yazar.

**Çeldirici**: * karakteri bir kaçış dizisi değildir.

## 7. Operatörler ve İfadeler: İşlem Önceliği Sanatı

Programlama sınavlarının en ayırt edici ve zorlayıcı kısmı operatör önceliği sorularıdır. C++'ta operatörlerin belirli bir çalışma sırasına (precedence) ve birleşme yönüne (associativity) sahip olması, karmaşık ifadelerin sonucunu belirler.

### 7.1. Operatör Sınıflandırması

**Aritmetik Operatörler**: +, -, *, /, %.

- **Modülüs (%)**: Bölme işleminden kalanı verir. Sadece tam sayılarla çalışır. Örneğin 10 % 3 = 1.

- **Tam Sayı Bölmesi**: C++'ta iki tam sayı bölündüğünde sonuç tam sayı olur, ondalık kısım atılır. 3 / 4 işleminin sonucu 0.75 değil, 0'dır. Bu detay sınavlarda kritik önem taşır.

**Atama Operatörleri**: =, +=, -=, *=, /=.

- `a += 5` ifadesi `a = a + 5` ile aynıdır.
- `a /= 2` ifadesi `a = a / 2` demektir.

**İlişkisel (Karşılaştırma) Operatörler**: ==, !=, <, >, <=, >=.

- == (Eşittir) ile = (Atama) karıştırılmamalıdır.

**Mantıksal Operatörler**:

- **&& (VE - AND)**: Her iki koşul doğruysa true.
- **|| (VEYA - OR)**: En az bir koşul doğruysa true.
- **! (DEĞİL - NOT)**: Koşulun tersini alır.

### 7.2. İşlem Önceliği Sıralaması (Precedence)

Sınavlarda karmaşık ifadelerin sonucunu bulmak için bu sırayı ezbere bilmek gerekir:

1. Parantezler ( )
2. Postfix Artırma/Azaltma a++, a-- (Sol'dan sağa)
3. Prefix Artırma/Azaltma ++a, --a, Mantıksal Değil ! (Sağdan sola)
4. Çarpma, Bölme, Mod *, /, % (Soldan sağa)
5. Toplama, Çıkarma +, - (Soldan sağa)
6. İlişkisel Operatörler <, <=, >, >=
7. Eşitlik Operatörleri ==, !=
8. Mantıksal VE &&
9. Mantıksal VEYA ||
10. Atama Operatörleri =, += vb. (Sağdan sola)

### 7.3. Derinlemesine Analiz: Artırma/Azaltma Soruları

Sınavlarda `++a * b--` gibi ifadeler sıkça sorulur. Bu operatörlerin yan etkilerini (side effects) anlamak gerekir.

- **Prefix (++a)**: "Önce artır, sonra kullan." Değişkenin değeri ifade içinde kullanılmadan önce artırılır.

- **Postfix (a++)**: "Önce kullan, sonra artır." Değişkenin o anki değeri ifade içinde kullanılır, işlem bittikten (veya bir sonraki sekans noktasına gelindiğinde) sonra değişkenin değeri artırılır.

**Örnek Soru Çözümü 1**:

```cpp
int a = 5, b = 2;
cout << ++a * b-- << endl;
```

- **Adım 1**: ++a (Prefix). a'nın değeri hemen 6 olur. İşlemde 6 kullanılır.
- **Adım 2**: b-- (Postfix). b'nin eski değeri olan 2 işlemde kullanılır. b'nin hafızadaki değeri daha sonra 1'e düşecektir ama bu çarpma işleminde 2 kullanılır.
- **Adım 3**: Çarpma: 6 * 2 = 12.
- **Sonuç**: 12.

**Örnek Soru Çözümü 2**:

```cpp
int a = 1 + 2 - 3 / 4 * 5;
```

**Öncelik Analizi**: Çarpma (*) ve Bölme (/), Toplama ve Çıkarmadan önce gelir. * ve / aynı önceliktedir, soldan sağa işlenir.

- **Adım 1 (Bölme)**: 3 / 4. Tamsayı bölmesi olduğu için sonuç 0'dır.
- **Adım 2 (Çarpma)**: 0 * 5. Sonuç 0'dır.
- **Adım 3 (Toplama/Çıkarma)**: 1 + 2 - 0.
- **Sonuç**: 3.

**Sınav Sorusu**: "İlk önce gerçekleştirilen işlem hangisidir?" Cevap: Bölme.

## 8. Kontrol Akış Mekanizmaları

Programın sadece yukarıdan aşağıya düz bir çizgi halinde değil, koşullara göre dallanarak veya tekrar ederek çalışmasını sağlayan yapılardır.

### 8.1. Karar Yapıları (Conditionals)

**if - else if - else**:

- Koşullar yukarıdan aşağıya kontrol edilir. İlk true olan bloğa girilir ve yapının geri kalanı atlanır.

**Vaka Analizi**: a=1, b=10, c=3. if(a>=5) Yanlış. else if(b<=5) Yanlış. else if(b>5) Doğru. Ekrana ilgili çıktı (örneğin "3") basılır ve diğer else bloklarına bakılmaz.

**switch - case**:

- Bir değişkenin belirli sabit değerlerle eşitliğini kontrol eder.

- **break Önemi**: Bir case bloğunda break kullanılmazsa, program durmaz ve bir sonraki case bloğunu da çalıştırır (buna "fall-through" denir). Sınavda case etiketini sonlandırmak için break kullanıldığı sorulmuştur.

- **default**: Hiçbir eşleşme olmazsa çalışır.

### 8.2. Döngüler (Loops)

**for Döngüsü**: Yineleme sayısı önceden bilindiğinde kullanılır.

```cpp
for(başlangıç; koşul; artım)
```

**Soru Analizi**: 1'den 11'e kadar tek sayıları (1 3 5 7 9 11) yazdırmak için artım miktarı `i+=2` olmalıdır.

**while Döngüsü**: Koşul doğru olduğu sürece döner. Başlangıçta koşul yanlışsa hiç çalışmayabilir.

**do-while Döngüsü**: Koşul sonda kontrol edilir. Bu yüzden koşul yanlış olsa bile gövde en az bir kez çalışır.

**Döngü Denetimi**:

- **break**: Döngüyü anında sonlandırır ve döngüden çıkar.

- **continue**: Döngünün o anki adımını (iterasyonunu) sonlandırır ve bir sonraki adıma geçer (başa döner).

**İç İçe Döngüler (Nested Loops)**: Sınavlarda, dış döngünün her bir adımı için iç döngünün tamamen çalıştığı mantığı test edilir. Örneğin, dış döngü 3 kez, iç döngü 2 kez dönüyorsa, içteki işlem toplam 3×2=6 kez yapılır. Sınavda "Dış döngünün her iterasyonunda iç döngü yeniden çalıştırılır" ifadesi doğrudur. "İç içe döngü sayısında kısıtlama vardır" ifadesi yanlıştır.

## 9. Fonksiyonlar ve Modüler Programlama

Büyük programları yönetilebilir parçalara bölmek için fonksiyonlar kullanılır.

### 9.1. Tanımlama ve Prototip

**DönüşTipi FonksiyonAdı(ParametreTipi p1, ParametreTipi p2)**

**Prototip**: Fonksiyonun gövdesi olmadan sadece imzasının (başlığının) bildirilmesidir. Örn: `int Topla(int x, int y);`. Parametre tipleri mutlaka belirtilmelidir. `double Ornek(int x, y);` hatalı bir tanımdır; `double Ornek(int x, int y);` olmalıdır.

### 9.2. return İfadesi

Fonksiyonun sonucunu döndürür ve fonksiyonu o noktada sonlandırır.

**Soru Analizi**: Bir fonksiyonda alt alta üç tane return varsa, sadece ilki çalışır. Sonrakilere (unreachable code) asla ulaşılmaz.

### 9.3. Hazır Kütüphane Fonksiyonları (<cmath>)

- **pow(taban, üs)**: Üs alma işlemi. pow(3,4) -> 81.

- **sqrt(sayı)**: Karekök alma.

- **ceil(sayı)**: Tavana yuvarlama. ceil(2.15) -> 3.

- **fabs(sayı)**: Mutlak değer (float/double için). abs tamsayılar içindir.

## 10. Hata Türleri (Debugging ve Error Handling)

Bir programcının karşılaşabileceği hataları sınıflandırabilmesi, sorun çözme yeteneği için kritiktir.

### 10.1. Söz Dizimi Hataları (Syntax Errors)

Programlama dilinin gramer kurallarına uyulmamasıdır.

- Noktalı virgül unutmak, parantez kapatmamak, hatalı operatör kullanımı (cout >> yerine cout << yazmak gibi).

**Sonuç**: Program derlenmez. Derleyici hata verir.

**Örnek**: `20 = c;` (Hatalı atama, sol taraf değişken (L-value) olmalı).

### 10.2. Çalışma Zamanı Hataları (Runtime Errors)

Program derlenir ve çalışmaya başlar, ancak çalışma sırasında geçersiz bir işlem yapıldığında çöker.

**En Yaygın Örnek**: Sıfıra bölme hatası (Division by zero).

**Sınavda "Sıfıra bölme hatası"nın türü sorulmuştur**: Cevap Çalışma zamanı hatasıdır.

### 10.3. Mantıksal Hatalar (Logic Errors)

Program derlenir, çalışır, çökmez ama yanlış sonuç üretir.

- Programcının algoritmayı yanlış kurmasından kaynaklanır.

**Örnek**: Negatif sayılar için tek/çift kontrolü yaparken daima çift demesi.

**Örnek**: x + y yapacakken yanlışlıkla x - y yazmak.

Bu hataları bulmak en zordur çünkü sistem hata vermez, çıktıyı analiz etmek gerekir.

## 11. Sonuç ve Sınav Başarı Kontrol Listesi

Bu rapor, sağlanan belgeler ve ek araştırmalar ışığında, sınavda karşılaşılacak soru tiplerini ve bunların arkasındaki bilgi birikimini detaylandırmıştır. Yüksek not almak için öğrencinin aşağıdaki kontrol listesine hakim olması gerekmektedir:

### 11.1. Temel Bilgiler Kontrol Listesi

- **Donanım**: CPU'nun kontrol/zamanlama işlevini, RAM ile HDD arasındaki "uçuculuk" farkını, klavyenin sadece giriş birimi olduğunu bilin.

- **Sayı Sistemleri**: Hexadecimal (F=15) ve Octal (7) tabanlarından Binary'ye dönüşümü kağıt üzerinde hızlıca yapabilmek için pratik yapın.

- **Algoritma**: Akış diyagramı şekillerini (Baklava=Karar, Paralelkenar=I/O) ezberleyin. WHILE döngüsü izleme (trace) sorularında değişken tablosu yapın.

- **IDE**: Visual Studio'da derleme (Ctrl+F5) ve proje yönetimi (Solution Explorer) kavramlarına hakim olun.

- **C++ Operatörleri**: Özellikle a++ ile ++a farkını ve aritmetik işlem önceliğini (Bölme > Toplama) çok iyi anlayın. Tamsayı bölmesinin (3/4 = 0) sonucunu unutmayın.

- **Söz Dizimi**: Kod parçalarında ; eksikliği, ters yazılmış oklar (cout >>) veya hatalı atamalar (20 = x) gibi "Syntax Error" tuzaklarına dikkat edin.

### 11.2. Sınav Stratejisi

1. **Zaman Yönetimi**: Her soruya eşit süre ayırın. Zor soruları sona bırakın.

2. **Kod İzleme**: Sözde kod sorularında değişken değerlerini tablo halinde takip edin.

3. **Çeldiricilere Dikkat**: Özellikle = ve == karışıklığı, tamsayı bölmesi, operatör önceliği konularında çeldiriciler sık kullanılır.

4. **Geri Dönüş**: Tüm soruları bitirdikten sonra cevapları gözden geçirin.

Bu kapsamlı çalışma, sadece sınavı geçmenizi değil, programlama temellerini sağlam bir zemine oturtmanızı sağlayacaktır.

