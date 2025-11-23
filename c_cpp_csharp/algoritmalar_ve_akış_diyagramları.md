## Algoritmalar ve Akış Diyagramları

### Giriş ve Yöntemsel Çerçeve

Bilgisayar bilimlerinde, donanımın fiziksel gerçekliğinin ötesinde yazılım ve onun yapı taşı olan algoritmalar temel bir rol oynar. Bu rapor, Atatürk Üniversitesi Açıköğretim Fakültesi "Programlama Temelleri" dersi kapsamında sunulan "Algoritmalar ve Akış Diyagramları" ünitesini temel alarak algoritmik düşünceyi, teorik ve pratik boyutlarıyla, temsil araçlarıyla ve gerçek dünya uygulamalarıyla inceler. Amacımız, dil bağımsız (language-agnostic) çözüm tasarımı perspektifi sağlamaktır.

### Raporun Kapsamı

Bu belge; algoritma kavramının tanımı, "iyi" bir algoritmanın nitelikleri (kesinlik, sonluluk, etkinlik), doğrulama kriterleri (doğruluk, sonlandırma, süre ve sıra) ve insan–makine arayüzünde görünürlük için kullanılan araçları (sözde kod ve akış diyagramları) kapsar. Algoritmaların statik matematiksel yapılar olmadıkları; gereksinimlere göre evrilen, yaşayan mühendislik varlıkları oldukları vurgulanır.

## 1. Algoritma Kavramının Ontolojisi ve Yapısal Analizi

### 1.1 Tanımsal Çerçeve ve Tarihsel Bağlam

Algoritma terimi tarihsel kökenini el-Hârizmî'ye kadar uzatır. Modern tanımıyla algoritma; girdilerden başlayıp ölçülebilir çıktılara ulaşan, sonlu, kesin ve etkin adımlar bütünüdür. Bir talimat dizisinin algoritma sayılabilmesi için tekrarlanabilir, doğrulanabilir ve uygulanabilir olması gerekir.

### 1.2 Algoritma ve Program Ayrımı

- Algoritma: Dil- ve platformdan bağımsız, soyut çözüm tasarımı.
- Program: Algoritmanın belirli bir dil/sistem için uygulanmış somut halidir.

Farklar: amaçsal kesinlik, mantıksal doğruluk ve evrensellik (yeniden kullanılabilirlik).

### 1.3 Yapısal Bileşenler

- Girdiler (Inputs)
- Kontroller ve koşullar (Conditions)
- Döngüler (Loops)
- Çıktılar (Outputs)

Her algoritma bu yapı taşlarının uygun kombinasyonuyla bir süreç olarak işler.

## 2. Kavramsal Sözlük ve Temel Tanımlar

Aşağıda sık kullanılan terimler kısa tanımlarıyla verilmiştir.

| Kavram | Tanım |
|---|---|
| Girdi | Algoritmanın başlatılması için gereken veri setleri |
| Çıktı | Algoritmanın ürettiği ölçülebilir sonuç |
| Kesinlik | Her adımın tek anlamlı olması |
| Sonluluk | Algoritmanın sonlu adımda bitmesi |
| Etkinlik | Adımların pratikte uygulanabilir olması |
| Karmaşıklık | Zaman/alan (time/space) maliyetleri |
| Özyineleme | Problemin daha küçük benzer alt problemlerle çözülmesi |

## 3. Algoritma Analizinde Kritik Metrikler

### 3.1 Süre ve Sıra Analizi

"Süre ve sıra"; alt işlemlerin doğru sırayla ve uygun zamanlarda yürütülmesini vurgular. Bazı adımlar arasında katı öncelik ilişkileri vardır (precedence). Bekleme koşulları veya dış olaylara bağımlılık (ör. ağ yanıtı) işlem akışını etkiler. Eşzamanlılık durumunda senkronizasyon, yarış durumu ve idempotency gibi konular kritik hale gelir.

#### 3.1.1 Sıralama (Sequence) Önceliği

Bazı adımlar arasında katı bir öncelik–sonralık ilişkisi (partial order) vardır. Örnek: bir dosyayı okumadan önce açmak gerekir. Bu tür ilişkiler "Öncelik Grafiği" ile modellenir.

#### 3.1.2 Süre (Duration) ve Bekleme Koşulları

Bazı adımların yürütülmesi önceki adımın bitmesine veya belirli bir dış olayın gerçekleşmesine bağlıdır (ör. ağ yanıtı, sensör verisi). Zaman aşımları (timeouts) ve bekleme stratejileri tasarımda önemlidir.

#### 3.1.3 Eşzamanlılık ve Senkronizasyon

Paralel çalışan alt süreçlerin veri bütünlüğünü koruması için senkronizasyon gereklidir. Kilitler, bariyerler ve koşul değişkenleri yaygın araçlardır. Aksi halde yarış durumları (race conditions) ortaya çıkar.

#### 3.1.4 Güvenlik ve Durum Makineleri

Yanlış sırada veya gereksiz tekrarda işlem sistemin zarar görmesine neden olmamalıdır (idempotency). Durum makineleri ve zaman mantığı (temporal logic) ile kesin davranışlar tanımlanabilir.

### 3.2 Doğruluk ve Sonlandırma

Toplam doğruluk (total correctness) = doğruluk + sonlandırma. Doğruluk, algoritmanın spesifikasyona uygun çıktılar üretmesini; sonlandırma ise her geçerli girdi için finite bir sonuca ulaşmasını ifade eder. Döngü değişmezleri (loop invariants), önkoşullar ve sonkoşullar bu kanıtlamada kullanılır.

## 4. Gerçek Dünya Uygulamaları

- Navigasyon ve lojistik (Dijkstra, A*)
- E‑ticaret ve öneri motorları (Collaborative filtering)
- Finansal teknoloji ve dolandırıcılık tespiti
- Sosyal medya içerik sıralaması
- Arama motorları (PageRank ve indeksleme)

Bu örnekler algoritmaların sistem tasarımında ne kadar belirleyici olduğunu gösterir.

## 5. Algoritma Temsil Araçları I — Sözde Kod (Pseudocode)

Sözde kod, dil bağımsız ve insan tarafından okunabilir formatta çözüm mantığını ifade eder. Avantajları: odaklanma, iletişim, analiz ve kolay dil dönüşümü.

Yazım ilkeleri: tutarlı girintileme, anlamlı isimlendirme, anahtar kelimelerin kullanımı, tek eylem/satır, blok kapama göstergeleri.

Örnek (iki sayının toplamı):

```
BAŞLA
  YAZ "Birinci sayıyı giriniz:"
  OKU sayi1
  YAZ "İkinci sayıyı giriniz:"
  OKU sayi2
  toplam ← sayi1 + sayi2
  YAZ "Sayıların toplamı:", toplam
BİTİR
```

### 5.1 Sözde Kod Yazım Kuralları

- Hiyerarşik girintileme kullanın.
- Anlamlı değişken isimleri seçin.
- Anahtar kelimeleri (BAŞLA, EĞER, DÖNGÜ) tutarlı kullanın.
- Her satır bir eylem içermeli.

## 6. Algoritma Temsil Araçları II — Akış Diyagramları (Flowcharts)

Akış diyagramları, kontrol akışını şekiller ve oklarla gösterir. Temel semboller:

| Sembol | Şekil | İşlev |
|---|---:|---|
| Başla / Bitir | Oval | Giriş/çıkış noktası |
| İşlem (Process) | Dikdörtgen | Hesaplama veya atama |
| Girdi / Çıktı | Paralelkenar | Veri giriş/çıkış |
| Karar (Decision) | Elmas | Evet/Hayır dallanması |
| Alt Süreç | Çizgili dikdörtgen | Modüler çağrı |
| Bağlayıcı | Daire | Akış bağlantısı |

Kullanım alanları: iletişim, test planlama, hata ayıklama, üst düzey sistem tasarımı.

## 7. Akış Diyagramı Türleri

- Program akış diyagramı — kodlama seviyesine yakın detay.
- Sistem akış diyagramı — bileşenler arası veri akışı.
- Süreç (process) diyagramı — iş kurallarına odaklanır.
- Olay/zaman odaklı diyagram — gerçek zamanlı sistemler için.

## 8. Sonuç ve Gelecek Perspektifi

Algoritmalar, modern bilişim dünyasının görünmez ama merkezi bir unsurudur. İyi tasarlanmış algoritmalar; doğru, sonlanan, verimli ve sürdürülebilir çözümler sunar. Bu temelleri öğrenmek, öğrencilerin ve profesyonellerin yapay zeka ve veri bilimi çağında etkin üreticiler olmasına katkı sağlar.