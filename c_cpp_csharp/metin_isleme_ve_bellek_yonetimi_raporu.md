# C++ Programlama Dilinde Metin İşleme ve Bellek Yönetimi: Karakter Dizileri ve String Sınıfı Üzerine Kapsamlı Akademik Araştırma Raporu

## 1. Giriş: Metin Tabanlı Veri İşlemenin Bilgisayar Bilimlerindeki Yeri
Bilgisayar programlama temellerinin eğitiminde, sayısal algoritmaların ardından gelen en kritik eşik, metin tabanlı verilerin (string) işlenmesidir. Kullanıcı etkileşimleri, veri tabanı sorguları, dosya sistemi yönetimi ve ağ iletişimi gibi modern yazılımın omurgasını oluşturan süreçlerin neredeyse tamamı, karakter dizilerinin etkin ve güvenli bir şekilde manipüle edilmesine dayanır. Atatürk Üniversitesi Açıköğretim Fakültesi "Programlama Temelleri" dersinin 11. Ünitesi olan "String Sınıfı ve Karakter Dizisi İşlemleri" başlıklı materyal, bu karmaşık konuyu C++ dilinin sunduğu iki temel paradigma üzerinden ele almaktadır: C dilinden miras kalan prosedürel **"Karakter Dizileri" (C-Style Strings)** ve C++ Standart Kütüphanesi'nin modern, nesne yönelimli çözümü olan **`std::string` sınıfı**.

Bu rapor, söz konusu ders materyalinin kapsamlı bir özetini sunmanın ötesine geçerek, yazılım geliştirme ve teknik mülakatlara hazırlık sürecinde öğrencilerin karşılaşabileceği zorlukları, bellek yönetimi inceliklerini ve performans optimizasyon stratejilerini derinlemesine analiz etmeyi amaçlamaktadır. Araştırma, ders notlarındaki temel tanımları, akademik literatürdeki performans kıyaslamaları, bellek güvenliği tartışmaları ve ileri düzey algoritmik uygulama örnekleri ile harmanlayarak bütüncül bir kaynak oluşturmaktadır. Özellikle eğitim bağlamında, `strlen` ile `sizeof` arasındaki farklar, `capacity` ile `size` kavramlarının bellek üzerindeki etkileri ve işaretçi (pointer) aritmetiğinin string işlemleri üzerindeki rolü gibi öğrencilerin sıkça yanılgıya düştüğü konulara özel bir vurgu yapılmıştır.

Raporun ilerleyen bölümlerinde, metin işlemenin tarihsel evrimi, C-Style stringlerin düşük seviyeli bellek mimarisi, `std::string` sınıfının dinamik bellek yönetimi stratejileri ve bu iki yaklaşımın performans ve güvenlik ekseninde karşılaştırmalı analizi detaylandırılacaktır. Ayrıca, palindrom kontrolü, metin sansürleme ve frekans analizi gibi klasik problemlerin hem algoritmik mantığı hem de kodlama teknikleri, potansiyel uygulama senaryoları perspektifiyle irdelenecektir.

## 2. Karakter Dizileri (C-Style Strings): Mimari ve Bellek Yönetimi
C++ programlama dili, geriye dönük uyumluluk prensibi gereği C dilinin metin işleme mekanizması olan karakter dizilerini (character arrays) tam olarak destekler. Bu yapı, modern programlamada yerini büyük ölçüde `std::string` sınıfına bırakmış olsa da, gömülü sistemler, işletim sistemi çekirdekleri ve eski kod tabanları ile çalışma zorunluluğu nedeniyle, bilgisayar bilimleri eğitiminin vazgeçilmez bir parçasıdır.

### 2.1. Bellek Yerleşimi ve Null Karakter (\0) Paradigması
Bir karakter dizisi, teknik olarak bellekte ardışık (contiguous) adreslerde saklanan `char` türündeki verilerin bir koleksiyonudur. Ancak bu diziyi, örneğin bir tamsayı dizisinden (`int`) ayıran temel ontolojik fark, dizinin uzunluğunun ayrı bir değişkende saklanması zorunluluğunun olmamasıdır. Bunun yerine, **"Sentinel Value" (Nöbetçi Değer)** prensibi kullanılır; dizinin sonu, sayısal değeri 0 olan özel bir karakterle, yani **"Null Karakter" (`\0`)** ile işaretlenir.

Bellek haritası üzerinde "Sınav" kelimesinin C-Style string olarak temsili aşağıdaki gibidir:

**Tablo 2.1: "Sınav" Kelimesinin Bellek Yerleşimi**

| Bellek Adresi (Örnek) | 0x100 | 0x101 | 0x102 | 0x103 | 0x104 | 0x105 |
|-----------------------|-------|-------|-------|-------|-------|-------|
| **Karakter** | 'S' | 'ı' | 'n' | 'a' | 'v' | **'\0'** |
| **ASCII Değeri** | 83 | -110 | 97 | 118 | 0 | 0 |

Bu yapı, string işleme fonksiyonlarının (örneğin `strlen`, `strcpy`) çalışma mantığını belirler. Fonksiyonlar, dizinin başlangıç adresinden (base address) başlayarak, `\0` karakterine rastlayana kadar bellek üzerinde ilerler. Bu tasarımın en büyük avantajı, string uzunluğunu saklamak için ek bir bellek alanına ihtiyaç duyulmamasıdır. Ancak dezavantajı, string uzunluğunu bulmanın **$O(1)$ değil, $O(N)$** zaman karmaşıklığına sahip olmasıdır; yani string ne kadar uzunsa, sonunu bulmak o kadar uzun sürer.

> [!IMPORTANT]
> **Kritik Güvenlik Bilgisi:** Null karakterin unutulması veya yanlışlıkla üzerine yazılması, C ve C++ programlamadaki en yaygın ve tehlikeli hatalardan biri olan **"Buffer Overflow" (Tampon Taşması)** ve **"Undefined Behavior" (Tanımsız Davranış)** durumlarına yol açar. Eğer `\0` yoksa, `cout` gibi bir çıktı fonksiyonu, bellekte `\0` değerine sahip rastgele bir bayt bulana kadar stringe ait olmayan verileri okumaya ve ekrana basmaya devam eder. Bu durum, hassas verilerin sızmasına veya programın çökmesine (segmentation fault) neden olabilir.

### 2.2. Tanımlama ve Başlatma Yöntemleri: Statik ve Dinamik Yaklaşımlar
Karakter dizilerinin tanımlanması, belleğin nerede (stack veya heap) ayrılacağına bağlı olarak farklılık gösterir. Uygulamalarda sıkça karşılaşılan tanımlama biçimleri ve bunların bellek üzerindeki etkileri şunlardır:

1.  **Statik Boyutlu Dizi (Stack Allocation):**
    ```cpp
    char dizi[20];
    ```
    Bu komut, derleme zamanında (compile-time) belirlenen 20 baytlık bir alanı yığın (stack) bellekte ayırır. Dizinin içeriği başlangıçta belirsizdir (garbage value). Burada saklanabilecek maksimum metin uzunluğu 19 karakterdir, çünkü son bayt mutlaka `\0` için ayrılmalıdır. Eğer 20 karakterlik bir metin kopyalanmaya çalışılırsa, `\0` için yer kalmayacak ve taşma meydana gelecektir.

2.  **String Literali ile Başlatma:**
    ```cpp
    char selam[] = "Merhaba";
    ```
    Bu en güvenli yöntemlerden biridir. Derleyici, "Merhaba" metninin karakter sayısını (7) hesaplar ve otomatik olarak sonuna `\0` ekleyerek toplamda 8 baytlık bir dizi oluşturur. Programcı boyut belirtmek zorunda kalmaz.

3.  **İşaretçi (Pointer) ile Tanımlama:**
    ```cpp
    const char* ptr = "Merhaba";
    ```
    Burada "Merhaba" metni genellikle **salt okunur (read-only)** bellek bölgesinde (text segment veya data segment) saklanır. `ptr` değişkeni ise stack üzerinde bulunur ve bu metnin başlangıç adresini tutar.
    **Risk:** `ptr[0] = 'm';` gibi bir yazma işlemi, salt okunur belleğe yazma girişimi olduğu için çalışma zamanı hatasına (runtime error) neden olur. Buna karşın `char selam[]` dizisi stack üzerinde kopyalandığı için değiştirilebilir.

4.  **Karakter Listesi ile Başlatma (Yaygın Hatalar):**
    ```cpp
    char dogru[] = {'A', 't', 'a', '\0'}; // Geçerli C-String
    char yanlis[] = {'A', 't', 'a'};      // GEÇERSİZ! C-String değil.
    ```
    `yanlis` dizisi teknik olarak geçerli bir `char` dizisidir, ancak bir C-String değildir. String fonksiyonlarına (örn. `strlen(yanlis)`) parametre olarak geçilirse, fonksiyon `\0` bulamadığı için dizi sınırını aşarak bellekte ilerlemeye devam eder, bu da felakete yol açar.

### 2.3. Pointer Aritmetiği ve Dizi Erişimi
C-Style stringler, C dilinin "array decay" (dizinin pointer'a dönüşmesi) özelliği sayesinde işaretçi aritmetiği ile yakından ilişkilidir. Bir dizinin adı, ifadeler içinde kullanıldığında, o dizinin ilk elemanının adresine (`&dizi[0]`) dönüşür. Bu durum, stringler üzerinde indis kullanmadan dolaşmayı mümkün kılar.

**Tablo 2.2: Dizi Erişimi ve Pointer Aritmetiği Karşılaştırması**

| Erişim Yöntemi | Sözdizimi | Açıklama |
|----------------|-----------|----------|
| **İndisleme (Indexing)** | `str[i]` | Dizinin `i`. indisindeki elemana erişir. Arka planda `*(str + i)` işlemine dönüşür. |
| **Pointer Aritmetiği** | `*(str + i)` | `str` başlangıç adresine `i` birim (bayt) eklenir ve o adresteki değer okunur (dereference). |
| **Pointer Artırma** | `*ptr++` | Pointer bir sonraki adrese kaydırılır ve önceki değer okunur. Döngülerde yaygındır. |

**Kod Analizi:**
Aşağıdaki kod parçasının çıktısı nedir?
```cpp
char str[] = "Bilgisayar";
char* ptr = str;
cout << *(ptr + 3) << ptr[5];
```
-   `ptr`, "Bilgisayar"ın başlangıç adresi ('B').
-   `ptr + 3`: Adresi 3 bayt ileri taşır ('g' harfine). `*` operatörü bu değeri okur. Çıktı: **g**.
-   `ptr[5]`: İndis 5'teki eleman ('s'). Çıktı: **s**.
-   **Toplam Çıktı: gs.**

## 3. Standart C-String Kütüphanesi (`<cstring>`) ve Güvenlik Fonksiyonları
C++ dilinde `<cstring>` kütüphanesi (C dilindeki `<string.h>`'ın karşılığı), karakter dizileri üzerinde kopyalama, birleştirme, karşılaştırma ve arama gibi temel işlemleri gerçekleştiren fonksiyonları barındırır. Bu fonksiyonlar, bellek yönetimi açısından programcıya tam kontrol verirken, aynı zamanda yüksek hata riski taşır. Modern derleyiciler ve standartlar (C11), bu riskleri azaltmak için "Güvenli Fonksiyonlar" (`_s` sonekli) setini önermektedir.

### 3.1. Uzunluk Hesaplama: `strlen()` vs `sizeof()` Ayrımı
Bu konu, teknik mülakatlarda adayların bellek yapısını anlayıp anlamadığını ölçmek için en sık kullanılan ayırt edici konulardan biridir.

-   **`strlen(const char* str)`**: Fonksiyon, **çalışma zamanında (runtime)** çalışır. Parametre olarak aldığı adresten başlayarak karakterleri sayar ve `\0` karakterini gördüğü anda durur. Null karakter uzunluğa dahil edilmez.
-   **`sizeof(operand)`**: Operatör, **derleme zamanında (compile-time)** çalışır (VLA hariç). Değişkenin veya türün bellekte kapladığı toplam alanı (bayt cinsinden) döndürür. Statik dizilerde, dizi boyutu ne ise onu döndürür; içeriğin `\0` ile nerede bittiğiyle ilgilenmez. Null karakter dahil tüm ayrılan alanı sayar.

**Tablo 3.1: strlen ve sizeof Davranış Analizi**

| Kod Örneği | `strlen` Sonucu | `sizeof` Sonucu | Açıklama |
|------------|----------------|-----------------|----------|
| `char s[] = "Test";` | 4 | 5 | `strlen` 'T','e','s','t' sayar. `sizeof` 'T','e','s','t','\0' için ayrılan yeri sayar. |
| `char s[10] = "Test";` | 4 | 10 | `strlen` içeriğe bakar. `sizeof` dizinin toplam kapasitesine (10) bakar. |
| `char *p = "Test";` | 4 | 4 veya 8 | `strlen` pointer'ın gösterdiği içeriği sayar. `sizeof` pointer değişkeninin kendi boyutunu (32-bit veya 64-bit mimariye göre) döndürür! Bu, sıkça karşılaşılan bir hatadır. |

> [!NOTE]
> **Derinlemesine Analiz:** `char *p` durumunda `sizeof(p)`'nin 4 veya 8 dönmesi, `p`'nin bellekte bir adresi tutan bir değişken olmasından kaynaklanır. `p`'nin gösterdiği metnin uzunluğu `sizeof` ile bulunamaz.

### 3.2. Kopyalama İşlemleri: `strcpy` vs `strcpy_s`
Metin kopyalama, C-String yönetimindeki en riskli işlemdir.

-   **Klasik `strcpy(hedef, kaynak)`**: Bu fonksiyon, kaynak stringi (source) hedef diziye (destination) kopyalar. Ancak, **hedef dizinin bu veriyi alacak kadar büyük olup olmadığını kontrol etmez.**
    -   **Senaryo:** 5 baytlık bir hedef diziye 100 karakterlik bir kaynak kopyalanırsa, fonksiyon hedef dizinin sınırlarını aşar ve bellekteki komşu verilere (örneğin dönüş adreslerine, diğer değişkenlere) yazar. Bu durum **"Buffer Overflow"** olarak bilinir ve siber güvenlik açıklarının (exploit) temelini oluşturur.

-   **Güvenli `strcpy_s(hedef, boyut, kaynak)`**: Microsoft'un CRT (C Runtime) kütüphanesi ve C11 standardı ile gelen bu fonksiyon, ek bir parametre olarak hedef dizinin boyutunu alır.
    -   **Mekanizma:** Kopyalama başlamadan önce, kaynak stringin uzunluğunun hedef boyutuna sığıp sığmayacağını kontrol eder. Sığmıyorsa, kopyalama yapmaz, hedef dizinin ilk karakterini `\0` yapar ve bir hata kodu (veya assertion) döndürür. Bu, programın belirsiz bir durumda devam etmesi yerine kontrollü bir şekilde hata vermesini sağlar.

**İpucu:** Eğer mülakatlarda "Neden `strcpy` yerine `strcpy_s` (veya `strncpy`) kullanılmalıdır?" sorusu gelirse, anahtar kelimeler **Buffer Overflow**, **Memory Corruption** ve **Bounds Checking (Sınır Kontrolü)** olmalıdır.

### 3.3. Birleştirme ve Karşılaştırma: `strcat` ve `strcmp`
-   **`strcat(hedef, kaynak)`**: Hedef stringin sonundaki `\0` karakterini bulur ve kaynak stringi buradan itibaren yazmaya başlar. `strcpy` gibi, bu fonksiyon da hedef dizinin boyutunu kontrol etmez. Güvenli alternatifi `strcat_s`'dir.
-   **`strcmp(str1, str2)`**: İki stringi karakter karakter (ASCII kodlarına göre) karşılaştırır. Eşitlik durumunda 0 döner.
    -   Bu durum, `if (strcmp(a, b))` şeklinde yapılan yanlış kullanımlara yol açabilir; çünkü C++'ta `if` koşulu 0 olmayan değerleri `true` kabul eder. Stringler eşitse (sonuç 0), `if` bloğu çalışmaz. Doğru kullanım `if (strcmp(a, b) == 0)` olmalıdır.

## 4. Modern C++ Yaklaşımı: `std::string` Sınıfı
C++ Standart Kütüphanesi (`<string>`), C-Style stringlerin manuel bellek yönetimi yükünü ve güvenlik açıklarını ortadan kaldırmak amacıyla `std::string` sınıfını sunar. Bu sınıf, bir "container" (kapsayıcı) olarak davranır ve dinamik bellek yönetimini (Dynamic Memory Allocation) **RAII (Resource Acquisition Is Initialization)** prensibine göre otomatikleştirir.

### 4.1. `std::string` Sınıfının Mimari Üstünlükleri
1.  **Otomatik Bellek Yönetimi:** Programcı, stringin ne kadar yer kaplayacağını hesaplamak veya `malloc/free` (ya da `new/delete`) ile uğraşmak zorunda değildir. Stringe yeni karakterler eklendikçe, sınıf arka planda gerekirse daha büyük bir bellek bloğu ayırır, eski veriyi oraya taşır ve eski bloğu serbest bırakır.
2.  **Small String Optimization (SSO):** Modern `std::string` uygulamaları, küçük stringleri (genellikle 15-22 karaktere kadar) dinamik bellek (heap) yerine doğrudan stack üzerindeki nesne içinde saklar. Bu, bellek tahsisi (allocation) maliyetini ortadan kaldırarak performansı ciddi ölçüde artırır. Performans karşılaştırması söz konusu olduğunda SSO'dan bahsetmek derinlemesine bilgi göstergesidir.
3.  **Tip Güvenliği ve Operatör Yüklemesi:** `+` operatörü ile birleştirme (`str1 + str2`), `==`, `<`, `>` operatörleri ile doğal karşılaştırma yapılabilir. Bu, kodun okunabilirliğini ve yazım kolaylığını artırır.

### 4.2. Temel İşlemler
-   **Atama:** `string s = "Merhaba";`
-   **Birleştirme:** `string tamAd = ad + " " + soyad;` veya `mesaj += " Dünya";`
    -   Bu işlemde `std::string`, mevcut kapasitenin yeterli olup olmadığını kontrol eder. Yetersizse kapasiteyi artırır (genellikle 1.5 veya 2 katına çıkarır).
-   **Erişim:** `s[i]` ile C tarzı hızlı erişim veya `s.at(i)` ile güvenli erişim sağlanır.

**Örnek Senaryo:**
```cpp
string s1 = "Ali";
string s2 = "Veli";
if (s1 < s2) cout << "Ali küçük";
```
-   **Çıktı:** "Ali küçük". `std::string`, karşılaştırma operatörlerini (`operator<`) aşırı yükleyerek (overload) sözlük sırasına göre karşılaştırma yapar. C-Style stringlerde `str1 < str2` yazılırsa, içerik değil, bellek adresleri karşılaştırılır ki bu tamamen anlamsız bir işlemdir. Bu fark, oldukça önemlidir.

## 5. String Sınıfı Fonksiyonları: Kapasite ve Manipülasyon
Konunun en belirleyici bölümleri, `std::string` sınıfının bellek yönetimi fonksiyonları ve bunların yan etkileri üzerine kuruludur.

### 5.1. Uzunluk ve Kapasite Yönetimi: `size` vs `capacity`
Bu iki kavram, dinamik dizilerin (ve stringlerin) çalışma mantığının temelini oluşturur.

-   **`length()` ve `size()`**: Stringin o an içerdiği geçerli karakter sayısını döndürür. İkisi tamamen eş anlamlıdır. `size()` fonksiyonu, STL konteynerleri (vector, list vb.) ile uyumluluk sağlamak için eklenmiştir.
-   **`capacity()`**: String nesnesinin, yeniden maliyetli bir bellek tahsisi (reallocation) yapmadan saklayabileceği maksimum karakter sayısını gösterir. `capacity`, her zaman `size`'dan büyük veya ona eşittir.
    -   **Neden farklılar?** Her `push_back` veya `append` işleminde bellek tahsisi yapmak (işletim sisteminden yer istemek, eski veriyi kopyalamak) çok maliyetlidir. Bu yüzden `std::string`, yer dolduğunda ihtiyacından fazlasını (rezerv) ayırır. Buna **"Geometric Growth" (Geometrik Büyüme)** denir.

-   **`reserve(n)`**: Stringin kapasitesini en az `n` karakter olacak şekilde artırır. Eğer programcı, stringin ne kadar büyüyeceğini önceden biliyorsa (örneğin 1 milyon karakterlik bir dosya okunacaksa), `reserve` kullanarak tek seferde bellek ayırır. Bu, ara bellek tahsislerini engelleyerek performansı dramatik şekilde artırır.
-   **`resize(n)`**: Stringin mantıksal boyutunu (`size`) değiştirir.
    -   Eğer `n < size`: String sondan kırpılır.
    -   Eğer `n > size`: String uzatılır ve yeni alanlar null karakter (`\0`) veya belirtilen bir karakterle doldurulur. `reserve` sadece kapasiteyi etkilerken, `resize` içeriği değiştirir.
-   **`shrink_to_fit()`**: C++11 ile gelen bu özellik, `capacity` değerini `size` değerine düşürmeyi talep eder. Büyük bir stringi işleyip kısalttıktan sonra, boşa çıkan belleği sisteme iade etmek için kullanılır. Ancak bu bir "istektir" (non-binding request), derleyici bunu göz ardı edebilir (ancak genellikle uygular).

**Örnek Senaryo:**
```cpp
string s;
s.reserve(100);
s = "Test";
cout << s.size() << " " << s.capacity();
```
**Çıktı:** `size` 4'tür (içerik "Test"). `capacity` ise en az 100'dür (uygulamaya göre 100, 111, 128 olabilir). String 100 karaktere ulaşana kadar yeni bellek tahsisi yapılmaz.

### 5.2. Erişim Güvenliği: `operator[]` vs `at()`
String elemanlarına erişimde güvenlik ve hız takası (trade-off) söz konusudur.
-   **`operator[]` (Köşeli Parantez):** C dizileri gibi davranır. Sınır kontrolü (bounds checking) yapmaz. Çok hızlıdır ancak geçersiz bir indise (örn. `s[100]`) erişilirse programın davranışı tanımsızdır (çökebilir veya yanlış veri okuyabilir).
-   **`at(pos)`**: Sınır kontrolü yapar. Eğer `pos >= size()` ise, `std::out_of_range` istisnası (exception) fırlatır. Hata yakalama (try-catch) mekanizmalarıyla programın çökmesi engellenebilir. Güvenliğin kritik olduğu yerlerde tercih edilmelidir.

### 5.3. Arama ve Alt Dizi İşlemleri (`find`, `substr`)
-   **`find(str, pos)`**: `str` alt dizisini, `pos` indeksinden başlayarak arar. Bulursa başlangıç indisini, bulamazsa `string::npos` döndürür.
    -   **`string::npos` Nedir?** `size_t` türünün alabileceği en büyük değerdir (genellikle -1'in unsigned karşılığı, örn. 18446744073709551615). Dönüş değerinin `int` değil, `size_t` veya `auto` ile karşılanması önemlidir, aksi takdirde taşma sorunları yaşanabilir.
-   **`substr(pos, len)`**: Stringin `pos` indisinden başlayarak `len` kadar karakterini kopyalar ve yeni bir string nesnesi döndürür. Orijinal string değişmez.
    -   Eğer `len` belirtilmezse, `pos`'tan sona kadar olan kısmı alır.
    -   `pos` string boyutundan büyükse hata (`out_of_range`) fırlatır.

### 5.4. Manipülasyon: `insert`, `erase`, `replace`
Bu fonksiyonlar string üzerinde yerinde (in-place) değişiklik yapar.
-   `insert(pos, str)`: Belirtilen pozisyona yeni bir string ekler. Dizinin geri kalanı sağa kaydırılır.
-   `erase(pos, len)`: Belirtilen aralığı siler. Dizi sola kaydırılır.
-   `replace(pos, len, str)`: Belirtilen aralığı siler ve yerine yeni stringi yazar. Yeni stringin uzunluğu, silinen kısımla aynı olmak zorunda değildir; string otomatik olarak büyür veya küçülür.

## 6. Algoritmik Uygulamalar ve Örnek Çözümler
Bu bölüm, teorik bilgilerin pratiğe döküldüğü ve teknik mülakatlarda soru olarak karşımıza çıkan klasik problemleri kapsar.

### Uygulama 1: Palindrom Kontrolü (Detaylı Analiz)
Bir kelimenin tersten okunuşunun kendisiyle aynı olup olmadığını (örn. "Kavak") kontrol etme.

**Yöntem 1: İki Pointer Tekniği (Verimli Yaklaşım)**
Stringin başından (start) ve sonundan (end) merkeze doğru ilerlenir. Bu yöntem ek bellek kullanmaz ($O(1)$ space) ve tek geçişte ($O(N)$ time) tamamlar.
```cpp
bool isPalindrome(string s) {
    int start = 0;
    int end = s.length() - 1;
    while (start < end) {
        // İsteğe bağlı: Boşlukları ve noktalama işaretlerini atlama mantığı buraya eklenebilir.
        if (s[start] != s[end]) {
            return false; // Eşleşme bozulduğu an çık
        }
        start++;
        end--;
    }
    return true; // Döngü biterse palindromdur
}
```
**Önemli Not:** Döngü koşulu `start < end` olmalıdır. `start != end` kullanmak, string uzunluğu çift sayı olduğunda pointerların birbirini ıskalamasına ve sonsuz döngüye yol açabilir.

**Yöntem 2: `std::reverse` Kullanımı (STL Yaklaşımı)**
Stringin bir kopyası oluşturulur, ters çevrilir ve orijinali ile kıyaslanır. Kodlaması çok daha basittir ancak $O(N)$ ek bellek gerektirir.
```cpp
string s = "ey edip adanada pide ye";
string ters = s; // Kopya oluştur
reverse(ters.begin(), ters.end()); // <algorithm> kütüphanesi
if (s == ters) cout << "Palindromdur";
```

### Uygulama 2: Kelime Sayısı ve İsim Baş Harflerini Büyütme
Kullanıcıdan alınan bir cümledeki kelimeleri saymak ve baş harflerini manipüle etmek. Bu, **durum makinesi (state machine)** mantığıyla çözülür.

**Algoritma:**
1. Metin taranırken bir "durum" değişkeni (`kelimeIcinde`) tutulur.
2. Eğer karakter boşluk değilse ve biz şu an bir kelimenin içinde değilsek: Yeni bir kelime başlamıştır. Sayacı artır ve `kelimeIcinde = true` yap.
3. Eğer karakter boşluksa: Kelime bitmiştir (veya zaten boşluktayız). `kelimeIcinde = false` yap.

```cpp
int kelimeSayisi = 0;
bool kelimeIcinde = false;
string cumle = "  Bugun   hava   guzel  ";

for (char c : cumle) {
    if (c != ' ') { // Harf gördük
        if (!kelimeIcinde) {
            kelimeSayisi++;
            kelimeIcinde = true; // Durum değişti: Kelimeye girdik
        }
    } else { // Boşluk gördük
        kelimeIcinde = false; // Durum değişti: Kelimeden çıktık
    }
}
```
**Analiz:** Bu algoritma, ardışık birden fazla boşluk olması veya cümlenin boşlukla başlaması/bitmesi durumlarında da hatasız çalışır. Basit bir boşluk sayma yöntemi (boşluk + 1) bu durumlarda hatalı sonuç verir.

### Uygulama 3: "Bul ve Değiştir" (Find and Replace Pattern)
Bir metin içindeki tüm "kötü" kelimeleri "****" ile değiştirmek. `replace` fonksiyonu tek başına sadece bir kez çalışır. Tüm geçişleri (occurrences) değiştirmek için döngü gereklidir.

```cpp
string metin = "bu hava kotu, yemekler kotu ama ders guzel";
string aranan = "kotu";
string yeni = "****";

size_t pos = metin.find(aranan); // İlk konumu bul
while (pos != string::npos) {    // Bulunduğu sürece döngüye gir
    metin.replace(pos, aranan.length(), yeni);
    
    // Kritik Adım: Aramaya kaldığımız yerden (pos + yeni.length()) devam etmeliyiz.
    // Aksi takdirde, eğer 'yeni' string içinde 'aranan' string geçiyorsa sonsuz döngü olur.
    pos = metin.find(aranan, pos + yeni.length());
}
```
**Dikkat:** `pos = metin.find(aranan, pos + yeni.length());` satırında ikinci parametreyi vermezseniz, arama her zaman baştan başlar. Eğer aranan="a", yeni="ba" ise, fonksiyon sürekli en baştaki "a"yı bulup "ba" yapar, sonra "ba"nın içindeki "a"yı bulur ve sonsuz döngüye girerek belleği doldurur (memory exhaustion).

### Uygulama 4: Harf Frekansı Analizi (Histogram Oluşturma)
Bir stringde hangi karakterden kaç tane olduğunu bulmak.

**Yöntem: Dizi (Array) Kullanarak Map'leme**
ASCII karakterleri için 256 boyutunda bir dizi (frekans tablosu) oluşturulur. Karakterin ASCII değeri, dizinin indisi olarak kullanılır.

```cpp
string s = "programlama";
int frekans[256] = {0}; // Tüm değerleri 0 ile başlat

for (char c : s) {
    frekans[(unsigned char)c]++; // Karakteri indise çevir ve sayacı artır
}

// Sonuçları yazdır
for (int i = 0; i < 256; i++) {
    if (frekans[i] > 0) {
        cout << (char)i << ": " << frekans[i] << endl;
    }
}
```
**Analiz:** Bu yöntem $O(N)$ zaman karmaşıklığına sahiptir. İç içe döngü kurarak her karakteri tekrar saymak $O(N^2)$ olurdu ve büyük metinlerde çok yavaş çalışırdı.

## 7. Karşılaştırmalı Analiz ve Pratik İpuçları
Bu bölüm, C-String ve C++ String arasındaki seçimi belirleyen faktörleri ve öğrencileri hataya düşüren "Tricky" (çeldirici) noktaları özetler.

**Tablo 7.1: C-String vs C++ String Kapsamlı Karşılaştırma**

| Özellik | Karakter Dizileri (`char[]`) | C++ String Sınıfı (`std::string`) |
|---------|------------------------------|-----------------------------------|
| **Bellek Yönetimi** | Statik veya manuel (`malloc`/`free`). Programcı sorumluluğunda. | Dinamik ve otomatik (RAII). `std::allocator` kullanır. |
| **Boyut (Resizing)** | Sabittir. Çalışma zamanında değiştirilemez. | Dinamiktir. Gerektiğinde otomatik büyür/küçülür. |
| **Güvenlik** | Düşük. Buffer overflow riski yüksek. | Yüksek. `at()` metodu ve otomatik boyut yönetimi güvenliği sağlar. |
| **Performans** | Çok hafif ek yük (overhead). Stack üzerinde çok hızlı. | Heap tahsisi maliyetli olabilir. Ancak SSO ile küçük stringlerde çok hızlıdır. |
| **Kullanım Alanı** | Gömülü sistemler, C API'leri, sürücü geliştirme. | Genel uygulama geliştirme, veri işleme, GUI uygulamaları. |
| **Kopyalama** | `strcpy` ile manuel. | `=` operatörü ile otomatik (Deep Copy). |

### Sıkça Sorulan Sorular ve Kavram Yanılgıları

1.  **Soru:** `std::string s; s[5] = 'a';` kodunun sonucu nedir?
    -   **Cevap:** Hata veya Tanımsız Davranış. `s` varsayılan yapıcı ile boş (`size=0`) oluşturulmuştur. Bellekte 5. indis için yer ayrılmamıştır. `s[5]` ile bellekte rastgele bir yere yazmaya çalışılır. Doğrusu `s.resize(6); s[5] = 'a';` veya `s += ".....a";` olmalıdır.

2.  **Soru:** `char str[] = "A";` ile `char c = 'A';` bellekte ne kadar yer kaplar?
    -   **Cevap:** `str` bir dizidir ve 'A' + '\0' olmak üzere **2 bayt** yer kaplar. `c` bir karakterdir ve **1 bayt** yer kaplar.

3.  **Soru:** `find` fonksiyonu aranan metni bulamazsa -1 mi döner?
    -   **Cevap:** Hayır, `string::npos` döner. `npos` işaretsiz (unsigned) bir değerdir ve `size_t`'nin maksimum değeridir. Eğer dönüş değeri `int` türünde bir değişkene atanırsa ve -1 ile karşılaştırılırsa (signed/unsigned mismatch) bazı sistemlerde hatalı sonuçlar verebilir. Doğru kontrol `if (pos != string::npos)` şeklindedir.

4.  **Soru:** `strlen(s)` fonksiyonu `\0` karakterini sayar mı?
    -   **Cevap:** Hayır, saymaz. Sadece görünür karakterleri sayar. `sizeof` ise sayar.

## 8. Sonuç
C++ programlama dilinde metin işleme, dilin evrimini ve bellek mimarisini anlamak için mükemmel bir laboratuvar ortamı sunar. C-Style stringler, pointer aritmetiği ve bellek düzeni (memory layout) konularında temel bir anlayış kazandırırken; `std::string` sınıfı, modern yazılım mühendisliğinin soyutlama (abstraction), güvenlik (safety) ve kaynak yönetimi (resource management) prensiplerini öğretir.

Mesleki yetkinlik için öğrencilerin sadece `substr`, `find` gibi fonksiyonların parametrelerini ezberlemeleri yeterli değildir. Arka planda `capacity`'nin nasıl değiştiğini, `\0` karakterinin fonksiyonları nasıl yönlendirdiğini ve stack/heap farkının değişken ömrünü nasıl etkilediğini kavramaları gerekmektedir. Bu raporda sunulan teorik çerçeve ve kaynaklardan derlenen ileri düzey uygulama örnekleri, "Programlama Temelleri" dersinin ötesine geçerek, öğrencileri gerçek dünya problemlerine ve teknik mülakatlara hazırlayacak yetkinliği kazandırmayı hedeflemektedir.

**Önerilen Çalışma Stratejisi:**
-   Pointer ve dizi ilişkisini bellek şemaları çizerek pekiştirin.
-   `std::string`'in `size` ve `capacity` değişimlerini bir debugger (hata ayıklayıcı) ile adım adım izleyin.
-   Verilen algoritmaları (Palindrom, Frekans, Sansürleme) kağıt üzerinde "trace" (takip) ederek mantığını oturtun.
-   Güvenli olmayan C fonksiyonlarının (`strcpy`, `strcat`) neden tehlikeli olduğunu ve modern alternatiflerini (`_s` versiyonları veya `std::string`) neden tercih etmeniz gerektiğini analiz edin.
