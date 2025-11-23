# Bilgisayar Bilimleri, Programlama Temelleri ve C++ Uygulama Mimarisi

Bu belge, bilgisayar mimarisi, sayı sistemleri, yazılım hiyerarşisi ve C++ programlama dilinin temel kavramlarına dair ders notlarının özetini sunar. İçerik teknik doğruluğu korunarak daha düzenli bir biçimde yapılandırılmıştır.

## 1. Bilgisayarın Temel Çalışma Mantığı

Bilgisayar; veriyi (girdi) alır, önceden tanımlanmış kurallara göre işler, sonuçları sunar ve bilgiyi saklar. Bu yaklaşım genellikle IPOS (Input — Process — Output — Storage) modeli ile açıklanır.

### Temel İşleyiş Döngüsü (IPOS)

- Girdi (Input): Verinin dış dünyadan alınması (ör. klavye, fare, sensör).
- İşlem (Process): Verinin Merkezi İşlem Birimi (CPU) tarafından işlenmesi.
- Çıktı (Output): İşlenen verinin kullanıcıya veya başka sistemlere sunulması (ör. ekran, yazıcı).
- Depolama (Storage): Verinin kalıcı veya geçici olarak saklanması (ör. HDD, SSD, RAM).

## 2. Donanım Bileşenleri

Bilgisayar sistemleri genellikle Von Neumann mimarisi ilkeleriyle tasarlanır. Başlıca bileşenler ve görevleri:

- Giriş birimleri: Fiziksel veriyi dijital forma çevirir (klavye, fare, mikrofon, tarayıcı).
- Merkezi İşlem Birimi (CPU): Sistemin kontrol merkezidir. Komutların yürütülmesini sağlar.
  - Kontrol Birimi (CU): Komut akışını ve yürütmeyi yönetir.
  - Aritmetik ve Mantık Birimi (ALU): Aritmetik ve mantıksal işlemleri gerçekleştirir.
- Ana bellek (RAM): İşlemcinin çalışma sırasında ihtiyaç duyduğu verileri ve kodu tutar (uçucu bellektir).
- İkincil depolama: Kalıcı veri saklama sağlar (HDD, SSD, USB bellek, optik diskler).
- Çıkış birimleri: İşlenmiş sonuçları insan algısına veya başka cihazlara sunar (monitör, yazıcı, hoparlör).


## 3. SAYI SİSTEMLERİ

Bilgisayarların işleyişini kavrayabilmek için hangi sembollerle ve hangi kurala göre sayıları yazdığımızı belirleyen sayı sistemlerinin mantığını bilmek zorunludur. İnsanlar gündelik hayatta tabanı 10 olan onluk (decimal) sistemi kullanır; bilgisayar donanımı ise fiziksel olarak iki ayrı durumu (sinyalin var / yok oluşu) ayırt edebildiğinden doğası gereği tabanı 2 olan ikilik (binary) sistem üzerinde çalışır.

Konumsal (pozisyonel) sayı sistemlerinin ortak ilkesi aynıdır: Bir sayıyı oluşturan her rakam, bulunduğu konuma göre tabanın bir kuvvetiyle ağırlıklandırılır ve toplam bu ağırlıklı değerlerin toplamına eşittir. Genel biçimiyle:

```
(a b c d e)_T = a·T^4 + b·T^3 + c·T^2 + d·T^1 + e·T^0
```

Burada T tabanı, a,b,c,d,e rakamlarıdır ve her rakam için 0 ≤ rakam < T koşulu sağlanır. Alt indisle yazılan ifade, sayının hangi tabanda verildiğini belirtir; aksi belirtilmezse genelde onluk kabul edilir.

Aşağıda yaygın sayı sistemleri, temel özellikleri ve dönüşüm yöntemleri özetlenmiştir.

- **Onluk (Decimal, taban 10)**: Günlük hayatta kullandığımız sistemdir. Rakam kümesi {0..9}’dur. Örnek:

    472 = 4 × 10^2 + 7 × 10^1 + 2 × 10^0

- **İkilik (Binary, taban 2)**: Bilgisayarların doğal temsilidir; yalnızca {0,1} kullanılır. Her ikili basamak "bit" olarak adlandırılır; 8 bit = 1 bayt (byte) olur. İkilikten onluğa dönüşümde her biti 2^n ile çarpıp toplarız.

    Örnek:

    (100101)_2 = 1×2^5 + 0×2^4 + 0×2^3 + 1×2^2 + 0×2^1 + 1×2^0 = 32 + 4 + 1 = 37_{10}

    Onluktan ikiliye dönüşüm (bölüm–kalan yöntemi): Sayıyı 2'ye bölerek kalanlar kaydedilir; bölüm 0 olana dek devam edilir; kalanlar ters sırada okunduğunda ikili gösterim elde edilir.

    Örnek:

    (25)_{10} → (11001)_2

- **Sekizlik (Octal, taban 8)**: Rakam kümesi {0..7}. 8 = 2^3 olduğundan ikilikle doğrudan ilişkilidir; ikilik dizileri üçerli gruplara ayrılarak kolayca sekizliye çevrilebilir. Eskiden özellikle UNIX sistemlerinde ve kısa gösterimlerde yaygın kullanılmıştır.

    Örnek:

    (731)_8 = 7×8^2 + 3×8^1 + 1×8^0 = 448 + 24 + 1 = 473_{10}

    Onluktan sekizliye dönüşüm: Tamsayıyı 8'e bölerek kalanları kaydetme yöntemiyle yapılır. Örnek: (470)_{10} = (726)_8

- **Onaltılık (Hexadecimal, taban 16)**: Rakam kümesi {0–9, A–F} (A=10,...,F=15). 16 = 2^4 olduğundan ikilikle birebir eşleşir; tek bir onaltılık hane 4 bite karşılık gelir. Bu özellik bellek adreslemelerinde, hata ayıklama çıktılarında ve renk kodlamalarında (ör. RGB) onaltılığı pratik kılar.

    Örnek:

    (2F)_{16} = 2×16^1 + 15×16^0 = 32 + 15 = 47_{10}

    Onluktan onaltılığa dönüşüm: Tamsayıyı 16'ya bölerek kalanları kaydetme yöntemine dayanır. Örnek: (1000)_{10} = (3E8)_{16}

Donanım ve yazılım bağlamında pratik dönüşümler:

- **İkilik ⇄ Sekizlik**: İkilik dizileri sağdan itibaren 3'erli gruplara ayrılır; her grup 0–7 aralığında bir sekizlik haneye karşılık gelir.
- **İkilik ⇄ Onaltılık**: İkilik dizileri 4'erli gruplara ayrılır; her grup 0–15 aralığında bir onaltılık haneyi temsil eder.

Bu grup bazlı dönüşümler hem insan okunabilirliğini artırır hem de düşük seviyeli adreste ve bellek gösterimlerinde hataları daha hızlı tanımlamayı sağlar. Özetle, sayı sistemlerini ve dönüşüm yöntemlerini bilmek bilgisayar mimarisi ve sistem programlama konularında temel bir gerekliliktir.

## 4. Yazılım ve Programlama Dilleri

Yazılım türleri ve dil seviyeleri:

- Sistem yazılımları: Donanım kaynaklarını yönetir ve temel işletim desteği sağlar (ör. işletim sistemleri, sürücüler).
- Uygulama yazılımları: Kullanıcı ihtiyaçlarını karşılayan programlardır (ör. ofis uygulamaları, tarayıcılar, oyunlar).

Programlama dilleri sınıflandırması:

- Makine dili: 0 ve 1'lerden oluşur; işlemciye özgüdür.
- Assembly: Makine komutlarının insan okunabilir sembolik karşılığıdır (MOV, ADD vb.).
- Yüksek seviyeli diller: İnsan diline daha yakın soyutlamalar sunar; derleyici veya yorumlayıcı gerektirir (C++, Java, Python vb.).

## 5. C++ Programlama Dili

C++ hem nesne yönelimli programlama (OOP) hem de sistem programlama için güçlü özellikler sunar.

### Tarihçe ve Standartlar

- 1979: Bjarne Stroustrup tarafından "C with Classes" olarak başlatıldı.
- C++11: Modern C++'ın temel özelliklerini (auto, lambda, akıllı işaretçiler) tanıttı.
- C++20: Modüller, konseptler ve diğer önemli iyileştirmeleri getirdi.

### Bir C++ Programının Derleme Süreci

1. Düzenleme (Editing): Kaynak kodun (.cpp) yazılması.
2. Önişleme (Preprocessing): #include vb. yönergelerin işlenmesi.
3. Derleme (Compiling): Kaynak kodun nesne koduna çevrilmesi.
4. Bağlama (Linking): Nesne kodlarının ve kütüphanelerin birleştirilmesi.
5. Yükleme (Loading): Çalıştırılacak programın belleğe yüklenmesi.
6. Çalıştırma (Execution): CPU tarafından komutların yürütülmesi.
7. Hata ayıklama (Debugging): Derleme, mantık veya çalışma zamanı hatalarının giderilmesi.

## 6. Algoritmik Yapı Taşları: Döngüler

Döngüler, tekrar eden işlemleri otomatikleştirmek için kullanılır. Yaygın döngü türleri:

### For Döngüsü

Tekrar sayısı biliniyorsa tercih edilir (pre-test).

```cpp
for (int i = 0; i < 10; i++) {
    std::cout << i << std::endl; // 0'dan 9'a kadar yazdırır
}
```

### While Döngüsü

Tekrar sayısı belirsiz ve bir koşula bağlı ise kullanılır (pre-test).

```cpp
while (sayi > 0) {
    // Koşul doğru olduğu sürece çalışır
}
```

### Do-While Döngüsü

En az bir kez çalışması gereken durumlarda (ör. menüler) kullanılır (post-test).

```cpp
do {
    // Önce işlem yapılır, sonra koşul kontrol edilir
} while (kosul);
```

### Kontrol İfadeleri

- break: Döngüyü derhal sonlandırır.
- continue: Mevcut yinelemeyi sonlandırır ve döngünün bir sonraki yinelemesine geçer.

---

Not: İçerikteki teknik bilgiler korunmuştur; düzenleme yalnızca biçim, dil ve okunabilirlik iyileştirmesi amaçlıdır.