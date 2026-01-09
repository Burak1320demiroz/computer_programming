# Photoshop Otomasyon Mimarisi: Eylemler, Toplu İşleme Süreçleri ve Sınav Hazırlık Stratejileri Üzerine Kapsamlı Araştırma Raporu

## Yönetici Özeti

Bu rapor, Atatürk Üniversitesi Açıköğretim Fakültesi Grafik Tasarım Lisans Programı müfredatında yer alan "Birden Fazla Dosya Üzerinde Toplu İşlemler (Batch Processes)" başlıklı 12. Ünite ders materyali temel alınarak hazırlanmıştır. Raporun temel amacı, Adobe Photoshop ekosisteminde otomasyonun teorik ve pratik altyapısını ayrıntılandırmak, eylem (action) oluşturma mekanizmalarını teknik derinliğiyle analiz etmek ve ilgili dersin sınavına yönelik kapsamlı bir çalışma rehberi sunmaktır.

Grafik tasarım endüstrisinde zaman yönetimi ve iş akışı optimizasyonu, yaratıcı yetenekler kadar kritik bir öneme sahiptir. Özellikle e-ticaret fotoğrafçılığı, dijital arşivleme ve web tasarımı gibi alanlarda binlerce görselin standart bir prosedürden geçirilmesi gerekliliği, manuel işlem kapasitesini aşmaktadır. Bu bağlamda, Photoshop'un sunduğu "Eylemler" (Actions) ve "Toplu İş" (Batch Processing) araçları, tasarımcının dijital asistanları olarak işlev görür. Bu rapor, söz konusu araçların nasıl oluşturulduğunu, yönetildiğini ve hata ayıklama süreçlerini irdelerken, aynı zamanda akademik başarıyı hedefleyen öğrenciler için genişletilmiş bir soru bankası analizi ve kavramsal haritalar sunmaktadır.

Rapor boyunca ana kaynak belgesindeki bilgiler, harici akademik ve teknik kaynaklardan elde edilen verilerle zenginleştirilmiştir. Özellikle sınav hazırlığı bölümünde, sadece ezber bilgiye dayalı değil, analitik düşünmeyi gerektiren senaryo bazlı soru analizlerine yer verilmiştir.

## 1. Grafik Tasarımda Otomasyonun Teorik Çerçevesi ve Gerekliliği

### 1.1. Tekrarlayan Görevlerin Yönetimi ve Bilişsel Yük

Grafik tasarım süreçleri doğası gereği yaratıcı kararlar ve teknik uygulamaların birleşiminden oluşur. Ancak, bir tasarımcının mesaisinin önemli bir kısmı, yaratıcılık gerektirmeyen, mekanik ve tekrarlayan görevlerle (redundant tasks) doludur. Örneğin, bir moda çekimi sonrası 500 adet ham fotoğrafın (RAW), belirli bir boyuta küçültülmesi, renk profilinin sRGB'ye dönüştürülmesi ve üzerine telif hakkı filigranı eklenmesi işlemi, manuel olarak yapıldığında saatler sürebilir. Bu durum, tasarımcı üzerinde "bilişsel yük" (cognitive load) oluşturmaz, aksine "bilişsel yorgunluk" ve dikkat dağınıklığına yol açar.

Ders notlarında belirtildiği üzere, toplu işlemlerin temel faydaları şunlardır:

*   **Zaman Tasarrufu:** İşlem süresini minimize ederek tasarımcının yaratıcı projelere odaklanmasını sağlar.
*   **Standartizasyon:** Her bir dosyanın pikseli pikseline aynı işleme tabi tutulmasını garanti eder. İnsan eliyle yapılan işlemlerde oluşabilecek "mouse kayması" veya "adım atlama" gibi riskleri ortadan kaldırır.
*   **Kaynak Verimliliği:** İşlemler, bilgisayarın işlemci (CPU) ve bellek (RAM) kaynaklarını optimize ederek, kullanıcı arayüzü (UI) etkileşimi olmadan arka planda yürütülebilir.

### 1.2. Photoshop Otomasyon Hiyerarşisi

Photoshop'ta otomasyon tek bir araçla sınırlı değildir. Karmaşıklık seviyesine göre bir hiyerarşi mevcuttur:

1.  **Seviye 1: Eylemler (Actions):** Kaydedilmiş komut dizileri. (Bu raporun odak noktası).
2.  **Seviye 2: Toplu İş (Batch):** Eylemlerin klasör bazlı uygulanması.
3.  **Seviye 3: Damlacıklar (Droplets):** Masaüstüne sürükle-bırak mantığıyla çalışan mini uygulamalar.
4.  **Seviye 4: Komut Dosyaları (Scripts):** JavaScript, AppleScript veya VBScript kullanılarak yazılan, koşullu mantık (if/else) içeren gelişmiş kodlar.

## 2. Eylemler (Actions) Paneli ve Altyapısı

### 2.1. Panel Arayüzü ve Erişim

Eylemler paneli, otomasyonun komuta merkezidir. Panele erişim için **Pencere > Eylemler** (Window > Actions) yolu izlenir veya **Alt + F9** kısayolu kullanılır. Panel, varsayılan olarak liste görünümündedir ancak dokunmatik ekranlar veya hızlı erişim için "Buton Modu"na (Button Mode) alınabilir.

**Buton Modu Analizi:**
*   **Avantajı:** Görsel karmaşayı azaltır, tek tıklamayla çalıştırma sağlar. Her eyleme farklı renk kodları (Kırmızı, Yeşil, Mavi vb.) atanarak görsel ayrışma sağlanabilir.
*   **Dezavantajı:** Bu moddayken yeni eylem kaydedilemez, eylemler düzenlenemez veya silinemez. Sınav sorusu potansiyeli taşıyan bu detay, kullanıcıların neden "Kaydet" butonunu göremediklerini açıklar.

### 2.2. Eylem Dosya Yapısı (.atn)

Photoshop eylemleri, **.atn** (Action) uzantılı dosyalarda saklanır. Bu dosyalar, XML benzeri bir yapıda komutların parametrelerini tutar. Bir eylem seti (Action Set), birden fazla eylemi içeren bir kapsayıcıdır.

**Dosya Yolu ve Yönetimi:**
Eylemler genellikle şu dizinde depolanır:
*   Windows: `C:\Program Files\Adobe\Adobe Photoshop\Presets\Actions`
*   Mac OS: `Applications/Adobe Photoshop/Presets/Actions`

Ders notlarında vurgulandığı üzere, eylemlerin taşınabilirliği (portability) önemlidir. Bir bilgisayarda oluşturulan .atn dosyası, USB bellek veya bulut üzerinden başka bir bilgisayara aktarılabilir. Creative Cloud senkronizasyonu sayesinde, kullanıcı hesabına bağlı kütüphaneler (Libraries) üzerinden de eylemler cihazlar arası senkronize edilebilir.

### 2.3. Panel Kontrol Düğmeleri ve İşlevleri

Panelin alt kısmındaki ikonlar, bir teyp veya medya oynatıcı metaforu üzerine kurulmuştur. Bu metafor, kullanıcıların öğrenme eğrisini hızlandırmayı amaçlar.

| İkon | Adı | İşlevi ve Teknik Detaylar |
| :--- | :--- | :--- |
| **Kare (Stop)** | Durdur | O anki kaydı veya oynatmayı sonlandırır. Eylem çalışırken basılırsa işlem yarıda kesilir. |
| **Daire (Record)** | Kaydı Başlat | Kırmızıya döner. Basıldığı andan itibaren yapılan arayüz etkileşimleri (menü seçimleri, panel ayarları) belleğe yazılır. |
| **Üçgen (Play)** | Seçimi Oynat | Seçili eylemi aktif dökümana uygular. Eğer bir klasör (Set) seçiliyse, içindeki tüm eylemleri sırayla oynatır. |
| **Klasör (Set)** | Yeni Küme | Eylemleri kategorize etmek için kullanılır (Örn: "Baskı Hazırlık", "Web Efektleri"). |
| **Kağıt/Artı (New)** | Yeni Eylem | Kayıt sürecini başlatmadan önce eylemin parametrelerini (Ad, Kısayol Tuşu, Renk) tanımlayan diyalog kutusunu açar. |
| **Çöp Kutusu** | Sil | Seçili eylemi veya komut satırını siler. Onay penceresi çıkar (Alt tuşuna basılı tutarak tıklanırsa onaysız siler). |

## 3. Eylem Oluşturma (Action Creation) Metodolojisi

Eylem oluşturma süreci, stratejik planlama gerektirir. Rastgele kayıt yapmak, genellikle hatalı veya verimsiz eylemlerle sonuçlanır. İdeal bir eylem oluşturma süreci şu adımları takip etmelidir:

### 3.1. Hazırlık Aşaması

Kayıt butonuna basmadan önce, yapılacak işlemlerin provası yapılmalıdır. Hangi menülerin kullanılacağı, değerlerin ne olacağı önceden belirlenmelidir. Ayrıca, eylemin uygulanacağı dosyanın durumu (açık mı, kapalı mı, katmanlı mı, düzleştirilmiş mi) kritiktir. Ders notlarında belirtildiği gibi, eğer eylem "Dosya Açma" komutunu içermeyecekse, örnek dosyanın önceden açılmış olması gerekir.

### 3.2. Kayıt Süreci ve Parametreler

"Yeni Eylem" (New Action) iletişim kutusu açıldığında, kullanıcıdan şu veriler istenir:
*   **Ad (Name):** Açıklayıcı olmalıdır (Örn: "1200px Genişlik - Filigranlı").
*   **Kısayol Tuşu (Function Key):** F1-F12 tuşlarına Shift ve Ctrl (Mac'te Command) kombinasyonları atanabilir. Bu, sık kullanılan eylemler için "Toplu İş" menüsüne girmeden hızlı uygulama sağlar.

**Kritik Teknik Detay:** Eylemler kaydedilirken "gerçek zamanlı hız" kaydedilmez. Yani, kullanıcının bir menüyü bulmak için 10 saniye beklemesi eyleme yansımaz. Eylem oynatılırken, işlemci gücünün elverdiği maksimum hızda (milisaniyeler içinde) komutlar uygulanır.

### 3.3. Kaydedilebilir ve Kaydedilemez Eylemler

Photoshop'taki çoğu işlem kaydedilebilir:
*   Filtre uygulamaları (Gaussian Blur, Unsharp Mask).
*   Ayarlama katmanları (Levels, Curves).
*   Boyutlandırma (Image Size, Canvas Size).
*   Kaydetme (Save As).

Ancak bazı işlemler doğrudan kaydedilemez veya dikkat gerektirir:
*   **Fırça Darbeleri:** Fırça ile boyama işlemleri kaydedilebilir ancak bu işlem "Yol" (Path) verisi olarak değil, koordinat verisi olarak tutulur. Görsel boyutu değişirse, fırça darbesi yanlış yere isabet edebilir.
*   **Yakınlaştırma/Kaydırma:** Görünüm (View) menüsündeki işlemler genellikle eylemin sonucunu etkilemediği için gereksiz adımlar olarak kabul edilir, ancak "Menü Öğesi Ekle" ile eklenebilir.

### 3.4. Eyleme Müdahale ve Gelişmiş Komutlar

Standart kaydın ötesinde, eylemleri daha akıllı hale getiren özellikler vardır:

#### 3.4.1. Menü Öğesi Ekleme (Insert Menu Item)
Bazı komutlar parametre içermez veya doğrudan kaydedilemez. Bu durumda eylemler paneli menüsünden "Menü Öğesi Ekle" seçilir ve ardından istenen menü komutu (Örn: Görünüm > Cetveller) tıklanır. Bu, eylemin o adımda ilgili menüyü çağırmasını sağlar.

#### 3.4.2. Durma Ekleme (Insert Stop)
Otomasyonun en büyük riski, her görselin aynı olmamasıdır. Bazen kullanıcı müdahalesi gerekir. "Durma Ekle" komutu, süreç içinde bir mesaj kutusu çıkarır.
*   **Kullanım Senaryosu:** Bir eylem, fotoğrafı açar, renk ayarını yapar ve ardından "Lütfen kırpma alanını seçin" mesajıyla durur. Kullanıcı kırpma işlemini yaptıktan sonra "Oynat" butonuna basarak eylemin geri kalanını (örn: kaydet ve kapat) tamamlar.
*   **"Devam Etmeye İzin Ver" (Allow Continue):** Bu seçenek işaretlenirse, mesaj kutusunda sadece "Tamam" butonu çıkar ve işlem duraksamadan devam eder; sadece bilgilendirme amaçlıdır.

#### 3.4.3. Koşullu İfade Ekleme (Insert Conditional)
Photoshop CS6 ve sonrasında gelen bu özellik, basit programlama mantığını (If/Else) arayüze taşır.
*   **Mantık:** Eğer [Koşul] ise [Eylem A'yı Oynat], değilse [Eylem B'yi Oynat].
*   **Örnek:** Eğer belge "Yatay" (Landscape) ise "90 Derece Çevir" eylemini oynat; değilse (yani dikeyse) hiçbir şey yapma. Bu özellik, karışık yönlerdeki fotoğrafları standartlaştırmak için hayati önem taşır.
*   **Desteklenen Koşullar:** Belge yönü, piksel en boy oranı, katman sayısı, seçim durumu, renk modu (RGB/CMYK) gibi yaklaşık 20 farklı parametre kontrol edilebilir.

#### 3.4.4. Diyalog Kutusu Kontrolü (Modal Controls)
Eylemler panelinde, eylem adının solunda küçük bir "pencere/kutu" ikonu bulunur.
*   **İkon Açık:** Eylem o adıma geldiğinde (Örn: Gaussian Blur), filtrenin ayar penceresini açar ve kullanıcının değer girmesini (Radius değerini değiştirmesini) bekler.
*   **İkon Kapalı:** Eylem kaydedilirken kullanılan değer (Örn: 5.0 px) neyse, diyalog kutusu açılmadan o değeri uygular. Tam otomasyon için bu ikonların genellikle kapalı olması tercih edilir.

## 4. Toplu İş (Batch Process) Yönetimi ve Stratejileri

Eylemler tekil dosyalar için harikadır, ancak binlerce dosya için Toplu İş komutu devreye girer. Bu komuta **Dosya > Otomatikleştir > Toplu İş** (File > Automate > Batch) yolundan ulaşılır. Bu pencere, otomasyonun lojistik merkezidir.

**Tablo 1: Toplu İş İletişim Kutusu Ayarları**

| Bölüm | Ayar / Parametre | Fonksiyon ve Kritik Önem | Kullanım İpuçları |
| :--- | :--- | :--- | :--- |
| **Oynat (Play)** | Küme (Set) & Eylem (Action) | Çalıştırılacak eylemin seçildiği yerdir. | Yanlış eylem seçimi, binlerce dosyanın hatalı işlenmesine neden olabilir. |
| **Kaynak (Source)** | Klasör (Folder) | İşlenecek dosyaların bulunduğu dizin. | Alt klasörleri dahil etmek için "Tüm Alt Klasörleri Kat" seçeneği kullanılmalıdır. |
| **Kaynak** | Açılmış Dosyalar | O an Photoshop'ta açık olan sekmeleri işler. | RAM kapasitesi sınırlıysa çok sayıda dosya için önerilmez. |
| **Kaynak** | Bridge | Adobe Bridge üzerinden seçilen dosyaları işler. | Görsel eleme yaptıktan sonra işlemek için en iyi yöntemdir. |
| **Kaynak (Kritik)** | Eylemdeki "Aç" Komutlarını Geçersiz Kıl | Eylem içinde "Aç" komutu varsa onu yok sayar. | Eylem belirli bir dosyayı (örn: logo.png) açmak üzere kaydedildiyse, bu seçenek işaretlenerek eylemin sıradaki kaynak dosyayı açması sağlanır. |
| **Hatalar (Errors)** | Hatalarda Durdur (Stop for Errors) | Bir hata olduğunda işlem durur ve uyarı verir. | Başında beklenen küçük işler için uygundur. |
| **Hatalar** | Hataları Günlüğe Kaydet (Log Errors) | Hata olsa bile işlem durmaz, hatalar.txt dosyasına yazılır. | Gece bırakılan veya büyük hacimli işler için zorunludur. İşlem bitince log dosyası incelenir. |
| **Hedef (Dest.)** | Kaydet ve Kapat | Orijinal dosyanın üzerine yazar (Overwrite). | Çok Risklidir. Orijinal dosyaların yedeği yoksa veri kaybına yol açar. |
| **Hedef** | Klasör (Folder) | İşlenen dosyaları yeni bir konuma kopyalar. | En güvenli yöntemdir. Orijinaller korunur. |
| **Hedef (Kritik)** | Eylemdeki "Farklı Kaydet" Komutlarını Geçersiz Kıl | Eylemdeki kayıt yolunu değil, Batch penceresindeki yolu kullanır. | Bu seçenek işaretlenmezse, dosyalar eylemin kaydedildiği andaki klasöre gitmeye çalışabilir veya sürekli isim sorabilir. |

### 4.1. Dosya Adlandırma Stratejileri (File Naming)

Toplu işlem çıktılarının isimlendirilmesi, arşiv düzeni için hayati önem taşır. Photoshop, parçalı bir isimlendirme yapısı sunar:
*   **Belge Adı (Document Name):** Dosyanın orijinal adı (Örn: IMG_1234).
*   **Seri Numarası (Serial Number):** 1 basamaklıdan 4 basamaklıya kadar otomatik artan sayılar.
*   **Tarih (Date):** İşlemin yapıldığı tarih (yymmdd formatında).
*   **Uzantı (Extension):** Dosya türü uzantısı (Mutlaka eklenmelidir, aksi takdirde işletim sistemi dosyayı tanıyamaz).

Ders notlarında belirtildiği üzere, dosya uyumluluğu için Windows, Mac OS ve Unix kutucuklarının işaretlenmesi, dosya adlarının farklı işletim sistemlerinde sorunsuz okunmasını sağlar.

### 4.2. Toplu İşlemlerde Sık Karşılaşılan Sorunlar ve Çözümleri

*   **Sürekli "Farklı Kaydet" Penceresi Açılması:**
    *   *Sebep:* Eylem içinde "Farklı Kaydet" komutu vardır ancak Toplu İş penceresinde "Eylemdeki Farklı Kaydet Komutlarını Geçersiz Kıl" seçeneği işaretlenmemiştir.
    *   *Çözüm:* İlgili kutucuk işaretlenmeli veya eylem içindeki Kaydet adımı silinerek kaydetme işlemi sadece Toplu İş penceresine bırakılmalıdır.
*   **Renk Profili Uyarıları:**
    *   *Sebep:* Kaynak dosyaların renk profili ile çalışma uzayının profili uyuşmuyordur.
    *   *Çözüm:* Kaynak bölümünde "Renk Profili Uyarılarını Verme" (Suppress Color Profile Warnings) seçeneği işaretlenmelidir.
*   **Dosyaların Yanlış Klasöre Kaydedilmesi:**
    *   *Sebep:* Hedef klasör ayarlarındaki belirsizlik.
    *   *Çözüm:* Eylem oluşturulurken, kaydetme adımı yapılmadan önce "Hedef" klasörün boş olduğundan emin olunmalı ve Toplu İş penceresinde hedef klasör manuel olarak tekrar seçilmelidir.

## 5. Alternatif Otomasyon Araçları: Görüntü İşlemcisi ve Scriptler

Ders materyali ağırlıklı olarak "Toplu İş" komutuna odaklansa da, modern Photoshop iş akışlarında diğer araçlar da önemlidir.

### 5.1. Görüntü İşlemcisi (Image Processor)

**Dosya > Komut Dosyaları > Görüntü İşlemcisi** (File > Scripts > Image Processor) yoluyla ulaşılır.
*   **Farkı:** Toplu İş komutuna göre daha basit bir arayüze sahiptir. Eylem oluşturmaya gerek kalmadan dosya formatı dönüştürme (JPG, PSD, TIFF), yeniden boyutlandırma ve kalite ayarı yapma imkanı sunar.
*   **Avantajı:** Eylem kaydetme zahmetine girmeden hızlıca "Tüm fotoğrafları 1000px genişliğinde JPG yap" demek için idealdir. Ayrıca aynı anda hem JPG, hem PSD hem de TIFF çıktısı verebilir.

### 5.2. Damlacıklar (Droplets)

**Dosya > Otomatikleştir > Damlacık Oluştur** yoluyla yapılır.
*   **İşlevi:** Bir eylemi, masaüstünde duran bir .exe (Windows) veya uygulama (Mac) ikonuna dönüştürür. Kullanıcı, işlemek istediği dosyaları sürükleyip bu ikonun üzerine bıraktığında, Photoshop otomatik açılır ve işlemi yapar. Tekrarlayan rutin işler için mükemmeldir.

## 6. Sınav Hazırlığı: Kritik Konular ve Soru Bankası Analizi

Bu bölüm, ATA AÖF Grafik Tasarım programı öğrencileri için özel olarak hazırlanmıştır.

### 6.1. Temel Bilgi Kontrol Listesi (Ezberlenmesi Gerekenler)

Sınavda başarı için aşağıdaki teknik detayların hafızaya alınması şarttır:
*   **Dosya Uzantısı:** Eylem dosyaları **.atn** uzantılıdır. (Tuzak şıklar: .act, .bat, .exe, .psd).
*   **Panel Kısayolu:** Eylemler Paneli = **Alt + F9** (veya Option + F9).
*   **Menü Yolları:**
    *   Eylemler Paneli: Pencere > Eylemler.
    *   Toplu İş: Dosya > Otomatikleştir > Toplu İş.
    *   Görüntü İşlemcisi: Dosya > Komut Dosyaları > Görüntü İşlemcisi.
*   **Kayıt İkonları:**
    *   Yuvarlak (Genellikle Kırmızı): Kaydı Başlat.
    *   Kare: Kaydı Durdur.
    *   Üçgen: Oynat.

### 6.2. Belge İçi Değerlendirme Soruları Analizi

| Soru Konusu | Doğru Cevap | Analiz ve İpucu |
| :--- | :--- | :--- |
| **Eylem Dosya Uzantısı** | .atn | .atn, "Action" kelimesinin kısaltmasıdır. .psd Photoshop dosyası, .pdf taşınabilir belge formatıdır. |
| **Panel Erişimi** | Pencere | Photoshop'taki tüm paneller (Katmanlar, Yollar, Renkler, Tarihçe) "Pencere" (Window) menüsü altındadır. |
| **Toplu İş Komutu** | Dosya > Otomatikleştir > Toplu İş | En sık karıştırılan şık "İçe Aktar" menüsüdür. Otomasyonla ilgili komutlar (Batch, Droplet) her zaman "Otomatikleştir" altındadır. |
| **Eylem Yükleme** | Eylemleri Yükle | Bu komut, Eylemler Paneli'nin sağ üst köşesindeki "hamburger menü" (dört çizgi) içinde yer alır. |
| **Dosya Yolu** | /Presets/Actions | Eylemler "Presets" (Ön Ayarlar) klasöründe saklanır. "Plug-ins" veya "Scripts" klasörleri ile karıştırılmamalıdır. |
| **Varsayılan Eylemler** | Güvenli Yayın (Yanlış Olan) | "Vinyet", "Sepya Tonlama", "Çerçeve" varsayılan kümede vardır. "Güvenli Yayın" (Broadcast Safe) genellikle video ile ilgilidir ve standart eylemlerde yer almaz. |
| **Eyleme Eklenen Öğeler** | Kaynak (Yanlış Olan) | Eyleme "Menü Öğesi", "Durma", "Koşullu İfade" eklenebilir. "Kaynak" (Source), eylemin parçası değil, Toplu İş komutunun bir girdisidir. Bu ayrım çok kritiktir. |

### 6.3. Harici Kaynaklardan Derlenen Potansiyel Soru Tipleri

*   **Soru:** Bir eylem içindeki "Gaussian Blur" adımında kullanıcıdan değer girmesini sağlamak için ne yapılmalıdır?
    *   **Cevap:** Eylemler panelinde ilgili adımın solundaki diyalog kutusu ikonu (modal control) aktif edilmelidir.
*   **Soru:** Toplu işlem sırasında "Renk Profili Uyuşmazlığı" uyarısının süreci durdurmasını engellemek için hangi ayar yapılmalıdır?
    *   **Cevap:** Toplu İş penceresinde Kaynak bölümündeki "Renk Profili Uyarılarını Verme" (Suppress Color Profile Warnings) seçeneği işaretlenmelidir.
*   **Soru:** Buton Modu (Button Mode) aktifken aşağıdakilerden hangisi yapılamaz?
    *   **Cevap:** Yeni eylem oluşturulamaz ve eylemler düzenlenemez. Sadece çalıştırma işlemi yapılabilir.
*   **Soru:** Hangi tuş kombinasyonu, "Farklı Kaydet" (Save As) penceresini açar?
    *   **Cevap:** Shift + Ctrl + S (veya Shift + Command + S). Eylem kaydederken bu kısayol sıkça kullanılır.

## 7. Senaryo Bazlı Uygulama Örnekleri

Sınavda veya profesyonel hayatta karşılaşılabilecek gerçek dünya senaryoları, konunun içselleştirilmesini sağlar.

### Senaryo 1: E-Ticaret Ürün Fotoğrafları
**Görev:** 1000 adet yüksek çözünürlüklü ürün fotoğrafı var. Hepsi 800x800 piksel kare içine sığdırılmalı, beyaz arka planlı olmalı, sağ alt köşeye logo eklenmeli ve "Web_Urun_001.jpg" şeklinde kaydedilmeli.

**Çözüm Adımları:**
1.  **Eylem Kaydı:** Örnek bir görsel açılır. "Web Hazırlık" adında eylem başlatılır.
2.  **Boyutlandırma:** Dosya > Otomatikleştir > Sığdır (Fit Image) kullanılarak 800x800 px sınırları belirlenir.
3.  **Logo Ekleme:** Dosya > Yerleştir (Place Embedded) ile logo dosyası çağrılır. Hizalama araçlarıyla sağ alta sabitlenir.
4.  **Kaydetme:** Eylem içinde "Farklı Kaydet" yapılmaz (Toplu İş menüsüne bırakılır) veya bir klasöre kaydedilip kapatılır.
5.  **Toplu İş:** Kaynak klasör seçilir. Hedef klasör belirlenir. Dosya adlandırma bölümüne "Web_Urun_" yazılır ve 3 haneli seri no eklenir.

### Senaryo 2: Hatalı Renk Profili Düzeltme
**Görev:** Farklı kaynaklardan gelen (kimisi CMYK, kimisi Adobe RGB) görsellerin hepsi baskı için CMYK formatına ve Fogra39 profiline dönüştürülmeli.

**Çözüm Adımları:**
1.  **Koşullu Eylem:** Eylemin başına bir "Koşullu İfade" eklenir: "Eğer Mod RGB ise, CMYK'ya çevir".
2.  **Profil Atama:** Düzenle > Profile Dönüştür (Convert to Profile) komutuyla hedef profil seçilir.
3.  **Hata Günlüğü:** Toplu İş penceresinde "Hataları Günlüğe Kaydet" seçilir. Çünkü bazı bozuk dosyalar dönüştürme hatası verebilir, sürecin durmaması gerekir.

## 8. İleri Seviye ve Teknik Detaylar

### 8.1. Bellek Yönetimi ve Performans
Çok adımlı ve karmaşık filtreler içeren eylemler (örneğin "Yağlı Boya Efekti"), bilgisayarın RAM'ini zorlayabilir. Photoshop'ta "Geçmiş Durumları" (History States) sayısını düşürmek veya eylemin içine periyodik olarak "Temizle > Tümü" (Purge All) komutunu eklemek (dikkatli kullanılmalıdır), uzun süreli toplu işlemlerde bellek şişmesini ve programın çökmesini engelleyebilir.

### 8.2. Telif ve Meta Veri İşlemleri
Eylemler sadece görseli değiştirmez, dosya bilgilerini (File Info) de güncelleyebilir. Dosya > Dosya Bilgileri menüsünden telif hakkı durumu "Telifli" olarak işaretlenip, sanatçı adı girilerek kaydedilen bir eylem, tüm görsellere yasal koruma etiketi eklemiş olur. Bu, profesyonel fotoğrafçılar için kritik bir otomasyon adımıdır.

## Sonuç

Photoshop'ta otomasyon, bir lüks değil, modern tasarım iş akışının bir zorunluluğudur. Atatürk Üniversitesi'nin ilgili ders materyali, bu yetkinliği kazandırmak için temel yapı taşlarını sunmaktadır. Eylemler Paneli'nin kullanımı, kayıt mantığı, toplu iş parametreleri ve dosya yönetim stratejileri, grafik tasarımcının "zamanı tasarlamasını" sağlar.

Öğrencilerin sınavda başarılı olabilmeleri için; **.atn** uzantısını, **Pencere > Eylemler** ve **Dosya > Otomatikleştir > Toplu İş** yollarını, Toplu İş penceresindeki **Kaynak/Hedef** ayrımını ve Hata Günlüğü kavramını, Eylem oluştururken kullanılan Kayıt/Durdur/Oynat ikonlarını ezbere bilmeleri ve bu raporun "Senaryo Bazlı Uygulama Örnekleri" bölümündeki mantığı kavramaları gerekmektedir.
