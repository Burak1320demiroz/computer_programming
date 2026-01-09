# C++ Programlama Dilinde İki Boyutlu Diziler: Kapsamlı Teorik İnceleme, Algoritmik Uygulamalar ve Uygulama Analiz Raporu

## 1. Yönetici Özeti ve Doküman Analizi
Bu rapor, Atatürk Üniversitesi Açıköğretim Fakültesi Programlama Temelleri dersi kapsamında sunulan "Ünite 10: İki Boyutlu Diziler" başlıklı eğitim materyalinin derinlemesine analizini ve bu materyalin ötesine geçen kapsamlı bir teknik araştırmayı içermektedir. Raporun temel amacı, bilgisayar bilimleri öğrencileri ve yazılım geliştiriciler için iki boyutlu (2D) dizilerin teorik temellerini, bellek mimarisini, algoritmik uygulamalarını ve sınav hazırlık stratejilerini akademik bir titizlikle sunmaktır.

İncelenen PDF belgesi (43749-10.pdf), iki boyutlu dizilerin tanımı, bildirimi, başlatılması, elemanlara erişim yöntemleri ve temel matris işlemlerini (toplama, transpoz alma, çarpma) kapsamaktadır. Belge, tek boyutlu dizilerin karmaşık veri setlerini (örneğin öğrenci not tabloları, piksel tabanlı görseller) modellemede yetersiz kaldığı durumlarda, satır ve sütun yapısına sahip matrislerin gerekliliğini vurgulamaktadır. Ünite hedefleri arasında dizilerin C++ dilinde tanımlanması, bellek yerleşiminin kavranması ve fonksiyonlarla etkileşimi yer almaktadır.

Bu rapor, söz konusu belgenin sunduğu temel bilgileri, harici teknik kaynaklardan elde edilen ileri düzey işaretçi (pointer) aritmetiği, dinamik bellek yönetimi, önbellek (cache) optimizasyonu ve karmaşık algoritmik analizlerle birleştirerek genişletmektedir. Özellikle uygulama bağlamında, belgede yer alan değerlendirme soruları detaylı bir şekilde çözümlenmiş, ayrıca olası mülakat sorularına yönelik öngörüler ve çözüm stratejileri geliştirilmiştir.

## 2. Teorik Çerçeve: İki Boyutlu Dizilerin Yapısal Analizi

### 2.1 Tanım ve Kavramsal Model
İki boyutlu diziler, verilerin doğrusal olmayan, ızgara (grid) tabanlı bir düzende saklanmasını sağlayan veri yapılarıdır. Matematiksel matrislere veya elektronik tablolara (Excel gibi) benzeyen bu yapı, verileri satır (row) ve sütun (column) koordinatları ile indeksler. C++ standardı açısından bakıldığında, iki boyutlu bir dizi teknik olarak "**dizilerin dizisi**" (array of arrays) olarak tanımlanır. Bu tanım, her bir satırın aslında kendi başına tek boyutlu bir dizi olduğu ve bu satırların birleşerek ana yapıyı oluşturduğu anlamına gelir.

Gerçek dünya problemlerinin modellenmesinde 2D diziler kritik bir rol oynar. Örneğin, bir sınıftaki öğrencilerin farklı derslerden aldıkları notların saklanması, bir görüntünün piksel yoğunluk değerlerinin işlenmesi veya oyun programlamada (satranç tahtası, harita ızgarası vb.) uzamsal verilerin temsili bu yapı sayesinde mümkündür.

### 2.2 Bellek Mimarisi ve Satır Öncelikli Düzen (Row-Major Order)
Bilgisayar belleği (RAM), doğası gereği tek boyutlu ve doğrusal bir adres uzayıdır. Bu nedenle, iki boyutlu mantıksal bir yapının fiziksel belleğe haritalanması için belirli bir kural setine ihtiyaç duyulur. C++ dili, bu haritalama için **Satır Öncelikli Düzen (Row-Major Order)** kullanır. Bu, sistem mimarisini anlama sürecinde en kritik teknik detaylardan biridir.

Satır öncelikli düzende, dizinin ilk satırındaki tüm elemanlar bellekte ardışık adreslerde saklanır. İlk satırın bitiminden hemen sonra ikinci satırın elemanları gelir ve bu düzen son satıra kadar devam eder. Örneğin, `int A[2][3]` şeklinde tanımlanan bir dizi için bellek yerleşimi şu şekildedir:
`A[0][0], A[0][1], A[0][2], A[1][0], A[1][1], A[1][2]`.

Bu yerleşim stratejisi, performans açısından hayati öneme sahiptir. İşlemci önbellekleri (CPU Cache), verileri bloklar halinde (cache lines) ana bellekten çeker. Verilere satır bazlı erişildiğinde (yani `A[0][0], A[0][1]` sırasıyla), işlemci bir sonraki veriyi zaten önbelleğe almış olma ihtimali yüksektir. Buna "uzamsal yerellik" (spatial locality) denir. Aksine, sütun bazlı erişim (örneğin `A[0][0], A[1][0]` şeklinde gitmek), bellekte uzak adreslere atlamayı gerektireceğinden "cache miss" (önbellek ıskalaması) oranını artırır ve performansı ciddi ölçüde düşürür. Fortran veya MATLAB gibi dillerin aksine, C++'ta döngülerin `for(i=0; i<rows; i++)` (dış döngü) ve `for(j=0; j<cols; j++)` (iç döngü) şeklinde kurulmasının temel nedeni budur.

### 2.2.1 Adres Hesaplama Formülü
Mülakatlarda veya optimizasyon süreçlerinde sıklıkla karşılaşılan bir durum, belirli bir elemanın bellekteki fiziksel adresinin hesaplanmasıdır. `T A[M][N]` şeklinde tanımlı, `B` taban adresine (base address) sahip ve her elemanı `W` byte boyutunda olan bir dizi için, `A[i][j]` elemanının adresi şu formülle hesaplanır:

$$\text{Adres}(A[i][j]) = B + W \times (i \times N + j)$$

Burada:
- **$i$**: Erişilmek istenen satır indeksi.
- **$N$**: Dizinin toplam sütun sayısı (bir satırdaki eleman sayısı).
- **$j$**: Erişilmek istenen sütun indeksi.
- **$W$**: Veri türünün boyutu (örneğin `int` için genellikle 4 byte).

Bu formül, derleyicinin neden 2D dizileri fonksiyonlara parametre olarak geçirirken en azından sütun sayısını ($N$) bilmek zorunda olduğunu da açıklar. Sütun sayısı bilinmeden, bir sonraki satırın bellekte kaç byte ötede başladığı hesaplanamaz.

### 2.3 Bildirim ve Başlatma Sözdizimi
C++ dilinde statik (derleme zamanında boyutu bilinen) bir 2D dizi bildirimi şu sözdizimi ile yapılır:
`veri_türü dizi_adı[satır_sayısı][sütun_sayısı];`

Örneğin:
```cpp
int matris[3][4]; // 3 satır, 4 sütunlu, toplam 12 integer elemanlı dizi.
```
Bu bildirim, yığın (stack) belleğinde 12 adet `int` için yer ayırır.

#### Başlatma Yöntemleri
Diziler, tanımlandıkları anda ilk değerleri ile başlatılabilirler. C++ bu konuda esneklik sağlar:

1.  **Satır Bazlı Gruplama (Önerilen):** Okunabilirliği artırır ve yapıyı görselleştirir.
    ```cpp
    int tablo[2][3] = {
        {10, 20, 30}, // 0. Satır
        {40, 50, 60}  // 1. Satır
    };
    ```
    Bu yöntemle, hangi değerin hangi satıra ait olduğu açıktır.

2.  **Düz (Sıralı) Liste:** Bellek lineer olduğu için, tüm elemanlar tek bir liste halinde de verilebilir. Derleyici bunları sırasıyla satırlara doldurur.
    ```cpp
    int tablo[2][3] = {10, 20, 30, 40, 50, 60};
    ```
    Bu yöntem hataya açıktır ve matris yapısını gizlediği için genellikle önerilmez.

3.  **Kısmi Başlatma:** Eğer sağlanan değer sayısı toplam eleman sayısından azsa, C++ standardı gereği geri kalan elemanlar varsayılan değer (sıfır) ile doldurulur.
    ```cpp
    int tablo[2][3] = { {1}, {4, 5} };
    ```
    Bu durumda bellek içeriği şöyle olur:
    - Satır 0: 1, 0, 0
    - Satır 1: 4, 5, 0

4.  **Boyut Çıkarımı:** Başlatma listesi verildiğinde, satır sayısı boş bırakılabilir ancak sütun sayısı zorunludur.
    ```cpp
    int dizi[][3] = { {1,2,3}, {4,5,6} }; // Geçerli, derleyici 2 satır olduğunu anlar.
    int hata[2][] = ...; // Geçersiz, sütun sayısı bilinmiyor.
    ```
    Sütun sayısının zorunluluğu, yukarıda açıklanan adres hesaplama formülündeki $N$ çarpanının gerekliliğinden kaynaklanır.

## 3. İleri Düzey Erişim ve İşaretçi (Pointer) Aritmetiği
Konunun en ayırt edici bölümleri genellikle diziler ve işaretçiler arasındaki ilişkiyi sorgulayan sorulardan oluşur. C++'ta dizi isimleri, çoğu bağlamda dizinin ilk elemanının adresine dönüşür (array decay). Ancak 2D dizilerde bu durum bir seviye daha karmaşıktır.

### 3.1 Dizi İsmi ve İşaretçi İlişkisi
`int A[3][4]` tanımlı bir dizi için:
- **`A`**: Dizinin ismidir ve `&A[0]` değerine eşdeğerdir. Bu, ilk satırın (yani 4 elemanlı bir dizinin) başlangıç adresidir. Türü `int (*)[4]` şeklindedir (4 integer'lık bir diziye işaret eden pointer).
- **`A[0]`**: İlk satırı temsil eder ve `&A[0][0]` değerine eşdeğerdir. Bu, ilk elemanın (tek bir integer) adresidir. Türü `int*` şeklindedir.
- **`A[0][0]`**: İlk elemanın kendisidir (değer).

### 3.2 İşaretçi Aritmetiği ile Erişim
Matris elemanlarına köşeli parantez kullanmadan, sadece işaretçi aritmetiği ile erişmek mümkündür ve bu teknik sıklıkla mülakatlarda sorulur.
- **`A`**: 0. satırın adresi.
- **`A + i`**: i. satırın adresi. (Bellekte `i * 4 * sizeof(int)` kadar ilerler).
- **`*(A + i)`**: i. satırın kendisine (yani i. satırın ilk elemanının adresine) erişim. Bu ifade `A[i]` ile aynıdır.
- **`*(A + i) + j`**: i. satırın j. sütunundaki elemanın adresi. (Bellekte `j * sizeof(int)` kadar daha ilerler).
- **`*(*(A + i) + j)`**: i. satır, j. sütundaki elemanın değeri. Bu ifade `A[i][j]` ile tamamen eşdeğerdir.

**Örnek Senaryo:**
`int mat[3][3] = {{1,2,3},{4,5,6},{7,8,9}};` ve `int *p = mat[0];` veriliyor.
`*(p + 4)` ifadesinin değeri nedir?

**Çözüm:** `mat[0]`, dizinin başını gösteren `int*` türünde bir işaretçiye dönüşür. Bellek lineer olduğu için, `p + 4` işlemi 4. elemana (indeks 4) gider. Dizi 1, 2, 3, 4, 5... şeklinde sıralandığı için 0. indeks 1, 3. indeks (ilk satır sonu) 3, 4. indeks ise ikinci satırın başı olan **4** değeridir. Ancak bu tür erişimler sınır kontrolü yapmadığı için dikkatli olunmalıdır, fakat C++ standardında diziler arası taşma (row overflow) tanımlı davranış (defined behavior) olmayabilir, ancak pratikte lineer yapıda çalışır.

## 4. Algoritmik Uygulamalar ve Kod Çözümleri
PDF belgesi ve ek araştırmalar ışığında, 2D diziler üzerinde gerçekleştirilen temel algoritmalar aşağıda detaylandırılmıştır.

### 4.1 Matris Toplama ve Çıkarma
İki matrisin toplanabilmesi için boyutlarının ($m \times n$) birebir aynı olması gerekir. İşlem eleman bazlı (element-wise) yapılır.

```cpp
// Matris Toplama
int A[2][2] = {{1, 2}, {3, 4}};
int B[2][2] = {{5, 6}, {7, 8}};
int C[2][2];

for (int i = 0; i < 2; i++) {
    for (int j = 0; j < 2; j++) {
        C[i][j] = A[i][j] + B[i][j];
    }
}
// Sonuç Matrisi C: {{6, 8}, {10, 12}}
```
Bu algoritmanın karmaşıklığı $O(m \times n)$'dir.

### 4.2 Matris Çarpımı
Matris çarpımı, öğrenme sürecinin en zorlayıcı konularından biridir. $A$ matrisi ($m \times n$) ile $B$ matrisinin ($n \times p$) çarpılabilmesi için, $A$'nın sütun sayısı ile $B$'nin satır sayısının eşit olması gerekir. Sonuç matrisi $C$, ($m \times p$) boyutunda olur.

**Çarpma kuralı:** $C_{ij} = \sum_{k=0}^{n-1} (A_{ik} \times B_{kj})$

```cpp
// A ve B matrislerinin çarpımı
int A[2][3] = {{1, 2, 3}, {4, 5, 6}};
int B[3][2] = {{7, 8}, {9, 10}, {11, 12}};
int C[2][2] = {0}; // Sonuç matrisi sıfırlanmalı

for (int i = 0; i < 2; i++) {           // A'nın satırları
    for (int j = 0; j < 2; j++) {       // B'nin sütunları
        for (int k = 0; k < 3; k++) {   // Ortak boyut (dot product)
            C[i][j] += A[i][k] * B[k][j];
        }
    }
}
```
**Analiz:** Bu algoritmanın zaman karmaşıklığı $O(m \cdot p \cdot n)$ olup, kare matrisler için $O(N^3)$'tür. Büyük matrislerde bu yöntem, $B$ matrisine sütun bazlı erişim yaptığı için (bellekte atlamalı erişim) önbellek performansını düşürür. İleri düzey optimizasyonlarda "Tiling" veya $B$ matrisinin transpozunu alarak çarpma teknikleri kullanılır.

### 4.3 Matris Transpozu (Devrik Alma)
Transpoz işlemi, satırların sütun, sütunların satır yapılmasıdır. $A_{ij}$ elemanı $T_{ji}$ konumuna taşınır. Kare matrislerde bu işlem yerinde (in-place) yapılabilirken, dikdörtgen matrislerde boyutlar değişeceği ($2 \times 3$ matris $3 \times 2$ olur) için yeni bir dizi gereklidir.

```cpp
// Transpoz Algoritması
int matris[2][3] = {{1, 2, 3}, {4, 5, 6}};
int transpoz[3][2];

for (int i = 0; i < 2; i++) {
    for (int j = 0; j < 3; j++) {
        transpoz[j][i] = matris[i][j];
    }
}
```
Bu işlem sonucunda transpoz matrisi `{ {1, 4}, {2, 5}, {3, 6} }` halini alır.

### 4.4 Maksimum/Minimum ve Diyagonal İşlemler
Bir matrisin en büyük elemanını bulmak için tüm elemanlar gezilir. Kare matrislerde köşegen (diyagonal) toplamı ise tek bir döngü ile hesaplanabilir.

**Diyagonal Toplam (Kare Matris):**
Ana köşegen ($i=j$) ve ikincil köşegen ($i + j = N - 1$) elemanlarının toplamı:
```cpp
int toplam = 0;
for (int i = 0; i < N; i++) {
    toplam += matris[i][i]; // Ana köşegen
}
```
Bu işlem $O(N)$ karmaşıklığındadır.

## 5. Dinamik Bellek Yönetimi ve Vektörler
Uygulama geliştirmede statik dizilerin sınırlarını bilmek ve dinamik alternatifleri anlamak şarttır. Statik dizilerin boyutu derleme zamanında belirlenmelidir. Ancak çalışma zamanında (runtime) boyut belirlemek için dinamik bellek yönetimi kullanılır.

### 5.1 new ve delete ile Dinamik 2D Dizi
C++'ta dinamik 2D dizi oluşturmak için genellikle "işaretçi dizisi" (array of pointers) yöntemi kullanılır:
1. Satırları tutacak bir işaretçi dizisi oluşturulur (`int**`).
2. Her satır için ayrı ayrı bellek ayrılır (`int*`).

```cpp
int satır, sutun;
cin >> satır >> sutun;

// 1. Adım: Satır işaretçileri için bellek ayırma
int** matris = new int*[satır];

// 2. Adım: Her satır için sütunları ayırma
for(int i = 0; i < satır; i++) {
    matris[i] = new int[sutun];
}

// Kullanım
matris[0][1] = 5;

// 3. Adım: Bellek İadesi (Deallocation) - ÖNEMLİ
for(int i = 0; i < satır; i++) {
    delete[] matris[i]; // Önce satırlar silinir
}
delete[] matris; // Sonra ana işaretçi dizisi silinir
```
Bu yöntem esneklik sağlar ancak bellek yönetimi programcıya aittir. `delete` işlemlerinin unutulması "bellek sızıntısına" (memory leak) yol açar. Ayrıca, bellek blokları ardışık olmayabilir, bu da performansı etkileyebilir.

### 5.2 Alternatif: std::vector Kullanımı
Modern C++'ta ham diziler yerine `std::vector` kullanımı standarttır ve modern projelerde bu yaklaşımlar tercih edilir.

```cpp
#include <vector>
// Satır ve sütun sayısı çalışma zamanında belirlenebilir
int satır = 3, sutun = 4;
std::vector<std::vector<int>> matris(satır, std::vector<int>(sutun, 0));

matris[1][2] = 10; // Erişim sözdizimi aynıdır
```
Vektörler bellek yönetimini otomatik yapar, boyut değiştirebilir ve `.size()` fonksiyonu ile kendi boyutunu bilir, bu da fonksiyonlara parametre geçirmeyi kolaylaştırır.

## 6. Sık Yapılan Hatalar ve Güvenlik Analizi
Kod izleme çalışmalarında "kodun çıktısı nedir" veya "kod neden hatalıdır" şeklindeki soruları yanıtlayabilmek için yaygın hataların (pitfalls) bilinmesi gerekir.

### 6.1 Sınır Aşımı (Buffer Overflow)
Bir dizinin sınırları dışında bir indekse erişmek (örneğin 3 elemanlı bir dizide `dizi[3]`'e erişmek) C++'ta "**tanımsız davranış**" (undefined behavior) üretir. Program çökebilir (Segmentation Fault) veya bellekteki başka bir veriyi bozarak yanlış sonuçlar üretebilir. C++ derleyicileri varsayılan olarak sınır kontrolü (bounds checking) yapmaz.

### 6.2 Yanlış Başlatma (Initialization Errors)
Dizi boyutundan fazla elemanla başlatma yapılması derleme hatasına yol açar.
```cpp
int a[2][2] = {1, 2, 3, 4, 5}; // Hata: Çok fazla başlatıcı
```
Ayrıca, çok boyutlu dizilerde sütun boyutunun belirtilmemesi de yaygın bir hatadır:
```cpp
int a[][] = {{1,2}, {3,4}}; // Hata: Sütun boyutu bilinmeli
int a[][2] = {{1,2}, {3,4}}; // Doğru
```

### 6.3 Fonksiyon Parametre Uyumsuzluğu
Statik bir 2D diziyi (`int a[3][3]`), `int**` bekleyen bir fonksiyona geçiremezsiniz. Statik diziler `int (*)[3]`'e (satır işaretçisine) dönüşür, işaretçi işaretçisine değil.
- **Doğru parametre:** `void fonksiyon(int a[][3])` veya `void fonksiyon(int (*a)[3])`.
- **Yanlış parametre:** `void fonksiyon(int **a)` (Sadece dinamik diziler için çalışır).

## 7. Örnek Durum Analizleri
Atatürk Üniversitesi Ünite 10 materyalinde yer alan senaryolar, konunun anlaşılmasını ölçmek için kritik öneme sahiptir. Aşağıda bu senaryoların detaylı analizi ve çözümleri sunulmuştur.

**Durum 1:** C++ dilinde iki boyutlu dizi tanımlamanın doğru sözdizimi hangisidir?
- **Analiz:** C++'ta her boyut ayrı köşeli parantez içinde belirtilir. Parantez `()` veya virgül kullanımı yanlıştır.
- **Doğru Cevap:** `c) int matris[3][4];`

**Soru 2:** `int A[2][3];` ifadesi bellekte kaç elemanlık yer ayırır?
- **Analiz:** Toplam eleman sayısı = Satır Sayısı $\times$ Sütun Sayısı. $2 \times 3 = 6$.
- **Doğru Cevap:** `b) 6`

**Soru 3:** Aşağıdaki ifadelerden hangisi B dizisinin 2. satır 1. sütun elemanına erişir?
- **Analiz:** C++'ta indeksleme 0'dan başlar.
    - Satır $\rightarrow$ İndeks 1 (2. satır)
    - Sütun $\rightarrow$ İndeks 0 (1. sütun)
- **Sonuç:** `d) B[1][0]` (Sorudaki "2. satır" ifadesi mantıksal sıra olarak kabul edildiğinde indeks 1 olur).

**Soru 4:** `int X[2][3]={{1,2,3},{4,5,6}};` tanımında `X[1][2]` elemanının değeri nedir?
- **Analiz:**
    - X[0] (1. Satır): {1, 2, 3}
    - X[1] (2. Satır): {4, 5, 6}
    - `X[1][2]`: 2. satırın 3. elemanı (indeks 2) $\rightarrow$ **6**.
- **Doğru Cevap:** `e) 6`

**Soru 5:** Aşağıdaki dizilerden hangisi 3 satır ve 4 sütundan oluşur?
- **Analiz:** İlk boyut satır, ikinci boyut sütundur.
- **Doğru Cevap:** `d) int B[3][4];`

**Soru 6:** Kod Çıktısı Analizi:
```cpp
int A[2][2] = {{1, 2}, {3, 4}};
cout << A[0][1] + A[1][0];
```
- **Analiz:**
    - `A[0][1]`: 1. satır, 2. sütun $\rightarrow$ 2
    - `A[1][0]`: 2. satır, 1. sütun $\rightarrow$ 3
    - Toplam: $2 + 3 = 5$.
- **Doğru Cevap:** `e) 5`

**Soru 7:** İki matrisin transpoz ilişkisini aşağıdakilerden hangisi ifade eder?
- **Analiz:** Transpoz işleminde $A_{ij}$ elemanı $T_{ji}$ konumuna geçer.
- **Doğru Cevap:** `b) T[i][j] = A[j][i]`

**Soru 8:** `int A[2][3]={{1,2,3}, {4,5,6} };` tanımında bellekteki sıralama nasıldır?
- **Analiz:** Satır öncelikli düzen (Row-Major). Önce ilk satır, sonra ikinci satır.
- **Doğru Cevap:** `a) 123456`

**Soru 9:** Kod Çıktısı (Çift sayıların toplamı):
- **Analiz:** `int A[2][3] = {{1, 2, 3}, {4, 5, 6}};`
    - Çift sayılar: 2, 4, 6.
    - Toplam: $2 + 4 + 6 = 12$.
- **Doğru Cevap:** `c) 12`

**Soru 10:** Sınır Elemanlarını Seçme (Boundary Elements):
- **Analiz:** Bir matrisin kenarlarındaki elemanları seçmek için:
    - İlk Satır (`i == 0`) VEYA Son Satır (`i == n-1`)
    - VEYA İlk Sütun (`j == 0`) VEYA Son Sütun (`j == m-1`)
- **Doğru Cevap:** `a) i == 0 || i == n-1 || j == 0 || j == m-1`

## 8. Sonuç ve Öneriler
İki boyutlu diziler, C++ programlamada veri yapılarının temel taşlarından biridir. Bu konuya hakimiyet, sadece sözdizimini (syntax) ezberlemekle değil, bellek yönetimini (row-major order), işaretçi aritmetiğini ve algoritmik mantığı (nested loops) kavramakla mümkündür.

Öğrenme sürecinde dikkat edilmesi gereken en önemli noktalar şunlardır:
- **İndeksleme Mantığı:** İndekslerin 0'dan başladığını ve N elemanlı bir boyutta en son indeksin N-1 olduğunu unutmamak.
- **Bellek Yerleşimi:** Kod optimizasyonu ve işaretçi soruları için verilerin bellekte satır satır saklandığını bilmek.
- **Dinamik Yönetim:** `new` ile ayrılan belleğin `delete` ile iade edilmesi gerektiğini ve bunun 2D dizilerde döngü gerektirdiğini hatırlamak.
- **Fonksiyon Parametreleri:** Statik dizilerin fonksiyonlara geçirilirken sütun boyutunun zorunlu olduğunu bilmek.

Bu rapor, sağlanan ders materyali ve harici teknik kaynakların senteziyle, C++ iki boyutlu diziler konusunu her yönüyle ele almış ve konuya hakimiyet için gerekli tüm teorik ve pratik altyapıyı sunmuştur.
