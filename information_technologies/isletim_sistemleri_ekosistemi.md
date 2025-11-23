# İşletim Sistemleri Ekosistemi: Mimari Derinlik, Tarihsel Dönüşüm ve Gelecek Projeksiyonu Üzerine Kapsamlı Araştırma Raporu

## 1. Giriş: Dijital Çağın Görünmez Mimarları

Yirmi birinci yüzyılın teknolojik manzarası, silikon çiplerin ve elektrik devrelerinin ötesinde, bu donanımlara ruh veren karmaşık yazılım katmanları tarafından şekillendirilmektedir. Bilgisayar bilimlerinin en temel ve aynı zamanda en sofistike alanlarından biri olan işletim sistemleri (İS), modern dijital yaşamın görünmez omurgasını oluşturur. Bir kullanıcının klavyedeki bir tuşa basmasından, küresel bir ağ üzerinden veri paketlerinin transferine kadar gerçekleşen milyarlarca işlem, bu sistemlerin yönetimi altındadır. Bu rapor, işletim sistemlerinin teorik temellerinden başlayarak, tarihsel evrimini, modern masaüstü ve mobil mimarilerini, ulusal stratejiler çerçevesinde geliştirilen yerli çözümleri ve yapay zeka ile bütünleşen gelecek vizyonunu, 2025 yılı verileri ve teknolojik gelişmeleri ışığında derinlemesine analiz etmeyi amaçlamaktadır.

İşletim sistemleri, en basit tanımıyla, donanım kaynakları ile kullanıcı uygulamaları arasında yer alan ve bu kaynakların adil, verimli ve güvenli bir şekilde paylaşılmasını sağlayan bir soyutlama katmanıdır. Ancak bu tanım, günümüz işletim sistemlerinin üstlendiği devasa rolü açıklamakta yetersiz kalır. Modern bir işletim sistemi, sadece bellek ve işlemci yöneten bir "trafik polisi" değil, aynı zamanda kullanıcı deneyimini şekillendiren, yapay zeka algoritmalarını barındıran ve cihazlar arası sürekliliği sağlayan bir "dijital yaşam platformu"dur. Rapor boyunca, Microsoft Windows, Apple macOS, Linux, Android ve iOS gibi hakim sistemlerin mimari yapıları, son sürümleri (Windows 11 24H2, Android 16, macOS Sequoia) ve stratejik farklılıkları, teknik literatür ve pazar verileri eşliğinde incelenecektir.

## 2. İşletim Sistemlerinin Kavramsal ve Teorik Çerçevesi

İşletim sistemlerinin karmaşık yapısını anlamak için, öncelikle varlık nedenlerini ve temel işlevlerini teorik bir zemine oturtmak gerekir. Bilgisayar donanımı, işlemci (CPU), bellek (RAM), depolama birimleri ve giriş/çıkış (I/O) aygıtlarından oluşan bir koleksiyondur. İşletim sistemi olmadan, bu bileşenler, üzerlerinde çalışacak kodun ne yapacağını, hangi adreste duracağını veya diğer donanımlarla nasıl iletişim kuracağını bilemez.

### 2.1. Kaynak Yönetimi ve Soyutlama Paradigması

İşletim sisteminin iki temel hedefi vardır: **Kaynak Yönetimi** ve **Soyutlama**. Kaynak yönetimi, sınırlı olan donanım kaynaklarının (işlemci zamanı, bellek alanı, ağ bant genişliği) birbiriyle rekabet eden süreçler (processes) arasında paylaştırılmasıdır. Örneğin, bir kullanıcı aynı anda müzik dinlerken, internette gezinip, arka planda bir dosya indiriyorsa, işletim sistemi milisaniyeler mertebesinde işlemciyi bu görevler arasında paylaştırarak "eş zamanlılık" illüzyonu yaratır. Soyutlama ise, donanımın karmaşık fiziksel detaylarını (disk sektörleri, ağ protokolleri, kesme sinyalleri) gizleyerek, uygulama geliştiricilerine temiz ve standart bir arayüz (API) sunmaktır. Programcı, veriyi diskin hangi sektörüne yazacağını değil, sadece "dosyayı kaydet" komutunu bilir; gerisini işletim sistemi halleder.

### 2.2. Çekirdek (Kernel) Mimarisi: Sistemin Kalbi

İşletim sisteminin en kritik bileşeni, sistem açıldığı andan kapanana kadar bellekte sürekli ikamet eden ve donanım üzerinde tam yetkiye (kernel mode) sahip olan "Çekirdek"tir. Çekirdek mimarileri, sistemin performansını, kararlılığını ve güvenliğini doğrudan belirler.

**Monolitik Çekirdek**: Linux ve dolayısıyla Android gibi sistemlerin temelini oluşturur. Dosya sistemi yönetimi, bellek yönetimi, donanım sürücüleri ve ağ protokolleri tek bir büyük çekirdek alanı içinde çalışır. Bu yapı, modüller arası iletişim (IPC) gerektirmediği için yüksek performans sunar. Ancak, bir ses sürücüsündeki hata, tüm çekirdeğin ve dolayısıyla sistemin çökmesine neden olabilir.

**Mikro Çekirdek**: Sadece en temel işlevlerin (süreçler arası iletişim, temel zamanlama) çekirdekte tutulduğu, dosya sistemi ve sürücülerin kullanıcı modunda (user mode) çalıştığı yapıdır. Bu, sistem kararlılığını artırır çünkü bir sürücü çökse bile çekirdek çalışmaya devam eder. Ancak, modüller arası sürekli mesajlaşma gerekliliği performans maliyeti yaratabilir.

**Hibrit Çekirdek**: Windows NT ve macOS (XNU) çekirdekleri, monolitik yapının performansını mikro çekirdeğin modülerliği ile birleştirmeyi hedefler.

### 2.3. Süreç ve Bellek Yönetimi Dinamikleri

Modern işletim sistemlerinde "Çoklu Görev" (Multitasking) yeteneği, işlemci zamanının dilimlenmesi (time slicing) prensibine dayanır. İşletim sistemi, her programa (sürece) işlemciyi belirli bir süre (quantum) tahsis eder. Bu süre dolduğunda veya daha yüksek öncelikli bir işlem geldiğinde, mevcut işlemin durumu (register değerleri, program sayacı) kaydedilir ve diğer işleme geçilir (context switch). Bu mekanizma, sistemin tepkiselliğini sağlar.

Bellek yönetimi ise, fiziksel belleğin (RAM) yetersiz kaldığı durumlarda disk alanının bir kısmının bellek gibi kullanılması (Sanal Bellek / Virtual Memory) prensibine dayanır. İşletim sistemi, programları küçük parçalara (sayfalara) bölerek, sadece o an ihtiyaç duyulan sayfaları fiziksel bellekte tutar. Bu sayede, fiziksel bellekten çok daha büyük programlar çalıştırılabilir. Android 16 ile gelen 16 KB sayfa boyutu desteği gibi yenilikler, bu bellek yönetimi operasyonlarının verimliliğini artırmayı hedefler.

## 3. Tarihsel Perspektif: Mekanik Hesaplayıcılardan Yapay Zekaya

İşletim sistemlerinin bugünkü formuna ulaşması, on yıllar süren bir evrimin ve donanım teknolojilerindeki sıçramaların sonucudur. Bu tarihsel süreç, insanlığın hesaplama gücünü nasıl kontrol altına aldığının da hikayesidir.

### 3.1. Mekanik Çağ ve İşletim Sisteminin Yokluğu (M.Ö. - 1940'lar)

Bilgisayar tarihinin kökleri M.Ö. 100'lü yıllara, abaküs ve Antikitera düzeneğine kadar uzansa da, bu cihazlar mekanik ve tek amaçlıydı. 17. yüzyılda Wilhelm Schickard ve Blaise Pascal'ın geliştirdiği hesap makineleri de benzer şekilde donanımsal olarak sabitlenmiş işlevlere sahipti. 1801'de Joseph Marie Jacquard'ın dokuma tezgahlarında kullandığı delikli kartlar, donanımın işleyişini dışarıdan bir veriyle (yazılımla) değiştirme fikrinin ilk kıvılcımıydı. Ancak bu dönemde, donanımı yönetecek bir ara katman fikri henüz doğmamıştı.

### 3.2. Birinci Nesil: Vakum Tüpleri ve Fiziksel Programlama (1945-1955)

İkinci Dünya Savaşı'nın getirdiği hesaplama ihtiyacı, elektronik bilgisayarların doğuşunu hızlandırdı. 1946 yılında ABD ordusu tarafından balistik hesaplamalar için geliştirilen ENIAC, genel amaçlı ilk elektronik bilgisayar olarak tarihe geçti. 30 ton ağırlığındaki bu dev, 167 metrekarelik bir alana yayılıyor ve 18.000 vakum tüpü içeriyordu. ENIAC döneminde bir işletim sistemi yoktu. Programcılar, makinenin farklı ünitelerini birbirine bağlayan kabloları söküp takarak (plugboards) ve binlerce anahtarı ayarlayarak programlama yapıyorlardı. Bu süreç günler alabiliyor, hesaplama ise dakikalar içinde bitiyordu. Alan Turing'in 1950'lerde geliştirdiği ilkel kontrol rutinleri, işletim sistemlerinin atası sayılabilecek ilk adımlardı.

### 3.3. İkinci Nesil: Transistörler ve Toplu İşlem Sistemleri (1955-1965)

Transistörlerin icadı, bilgisayarları daha küçük, daha hızlı ve daha güvenilir hale getirdi. Bu dönemde, bilgisayar zamanı çok pahalı olduğu için, bu zamanı verimli kullanmak adına "Toplu İşlem" (Batch Processing) sistemleri geliştirildi. Programcılar, işlerini (job) delikli kartlara kodlayıp operatöre veriyor, operatör de benzer işleri (örneğin hepsi FORTRAN dilinde yazılmış işleri) biriktirip manyetik bantlara kaydederek bilgisayara sırayla yüklüyordu. GM-NAA I/O gibi ilk ilkel işletim sistemleri, bir iş bittiğinde otomatik olarak diğerini yükleyerek CPU'nun boş kalma süresini azaltmayı hedefliyordu.

### 3.4. Üçüncü Nesil: Entegre Devreler ve Çoklu Programlama (1965-1980)

Entegre devrelerin (IC) kullanımı, bilgisayar mimarisinde devrim yarattı. IBM'in 1964'te tanıttığı System/360 ailesi ve onun işletim sistemi OS/360, bu dönemin sembolüdür. Bu sistemler, "Çoklu Programlama" (Multiprogramming) yeteneğine sahipti; yani bellekte aynı anda birden fazla program tutulabiliyor, biri I/O işlemi (diskten okuma gibi yavaş işlemler) beklerken, CPU diğer programa geçebiliyordu. Ayrıca "Zaman Paylaşımı" (Time-Sharing) kavramı doğdu; birden fazla kullanıcı terminaller üzerinden aynı ana bilgisayara bağlanıyor ve sistem her kullanıcıya hızlıca sıra vererek herkese "kendi bilgisayarıymış" hissi veriyordu. UNIX işletim sisteminin (1969) doğuşu da bu döneme rastlar ve modern işletim sistemlerinin (Linux, macOS, iOS, Android) temelini oluşturur.

### 3.5. Dördüncü Nesil: Kişisel Bilgisayarlar ve Grafik Arayüz (1980-Günümüz)

LSI (Large Scale Integration) teknolojisi, binlerce transistörü tek bir çipe sığdırarak mikroişlemcileri ve dolayısıyla Kişisel Bilgisayarları (PC) mümkün kıldı. 1981'de Microsoft'un MS-DOS'u ile başlayan PC devrimi, komut satırı arayüzünden (CLI), Xerox PARC'ta icat edilen ve Apple Macintosh (1984) ile ticarileşen Grafik Kullanıcı Arayüzü'ne (GUI) geçişle hızlandı. Windows 95, Başlat menüsü ve görev çubuğu ile modern masaüstü paradigmasını oturttu. Günümüzde ise bulut bilişim, mobilite ve yapay zeka entegrasyonu ile işletim sistemleri yeni bir çağa girmektedir.

## 4. Masaüstü İşletim Sistemleri: Mimari Analiz ve Modern Ekosistemler

Masaüstü ve dizüstü bilgisayar pazarı, on yıllardır süren rekabet sonucunda üç ana kutupta şekillenmiştir: Microsoft Windows, Apple macOS ve Linux tabanlı sistemler (ve Türkiye özelinde Pardus). Temmuz 2025 verileri, dünya genelindeki bilgisayarların yaklaşık %78'inin, Türkiye'de ise %85'inin bu sistemleri kullandığını göstermektedir.

### 4.1. Microsoft Windows: Pazar Liderinin Dönüşümü

Microsoft Windows, kişisel bilgisayar pazarının tartışmasız lideri olarak, ev kullanıcılarından kurumsal sunuculara kadar geniş bir yelpazede hizmet vermektedir. MS-DOS tabanlı (Windows 9x) mimariden, daha güvenli ve kararlı Windows NT çekirdeğine (Windows XP ve sonrası) geçiş, Windows'un başarısındaki en kritik dönüm noktasıdır.

#### 4.1.1. Windows 11 ve 24H2 Sürümünün Getirdiği Yenilikler

Windows 11, görsel olarak daha sadeleşmiş, mobil işletim sistemlerini andıran bir arayüz sunarken, 2024 sonlarında yayınlanan 24H2 sürümü ile kaputun altında devrimsel değişikliklere gitmiştir. Bu sürüm, işletim sisteminin sadece bir yazılım değil, yapay zeka ile güçlendirilmiş bir "asistan"a dönüşümünü simgeler.

**Tablo 1: Windows 11 24H2 Sürümü Öne Çıkan Özellikler**

| Özellik Alanı | Yenilik ve Açıklama | Kaynak |
|--------------|-------------------|--------|
| Yapay Zeka (Copilot+ PC) | Recall (Hatırlama): Kullanıcının ekranında gördüğü her şeyin anlık görüntülerini alıp analiz ederek, geçmişe dönük anlamsal arama yapabilmesini sağlayan "fotografik hafıza" özelliği. NPU donanımı gerektirir. | |
| Yapay Zeka (Görsel) | Cocreator: Paint uygulaması içinde metinden görsel üretme (Generative AI) ve Restyle Image ile fotoğrafları yeniden stilize etme yeteneği. | |
| Erişilebilirlik | Live Captions (Canlı Altyazılar): Sistemdeki herhangi bir ses veya videoyu (çevrimdışı dahil) gerçek zamanlı olarak metne dökme ve çevirme özelliği. | |
| Çekirdek Güvenliği | Rust Entegrasyonu: Windows çekirdeğinin bazı bölümleri, bellek güvenliği (memory safety) sağlayan Rust dili ile yeniden yazılarak, bellek taşması kaynaklı açıklar ve mavi ekran hataları azaltılmıştır. | |
| Geliştirici Araçları | Sudo for Windows: Linux ve macOS kullanıcılarının aşina olduğu, komut satırında yetki yükseltmeyi sağlayan sudo komutu Windows'a yerel olarak eklenmiştir. | |
| Enerji Verimliliği | Energy Saver: Dizüstü ve masaüstü bilgisayarlarda arka plan işlemlerini agresif şekilde kısıtlayarak enerji tüketimini azaltan yeni bir güç modu. | |
| Bağlantı | Wi-Fi 7 Desteği: Yeni nesil yüksek hızlı ve düşük gecikmeli kablosuz ağ standardı için yerel destek. | |

Bu yenilikler arasında özellikle Recall özelliği, işletim sisteminin kullanıcı verisini işleme biçiminde radikal bir değişimi işaret eder. Tüm ekran aktivitesinin yerel olarak indekslenmesi, verimlilik açısından büyük bir sıçrama olsa da, gizlilik tartışmalarını da beraberinde getirmektedir. Microsoft, bu verilerin cihaz dışına çıkmadığını ve NPU (Neural Processing Unit) üzerinde işlendiğini vurgulayarak, bulut tabanlı AI yerine "On-device AI" (Cihaz Üzerinde Yapay Zeka) modelini benimsediğini göstermektedir.

### 4.2. Apple macOS: Entegrasyonun Zirvesi

Apple'ın Macintosh bilgisayarları için geliştirdiği macOS, donanım ve yazılımın tek elden çıkmasının avantajını kullanarak yüksek optimizasyon sunar. UNIX tabanlı Darwin çekirdeği üzerine kurulu olan macOS, grafik arayüzü (Aqua), uygulama çatısı (Cocoa) ve çekirdek servisleriyle katmanlı bir yapıya sahiptir.

#### 4.2.1. macOS Sequoia (Sürüm 15) ve Ekosistem Sürekliliği

Eylül 2024'te yayınlanan macOS Sequoia, Apple'ın "Walled Garden" (Kapalı Bahçe) stratejisinin en olgun meyvesidir. Bu sürüm, masaüstü bilgisayar ile mobil cihaz (iPhone) arasındaki sınırları bulanıklaştırmayı hedefleyen özelliklerle donatılmıştır.

- **iPhone Mirroring (iPhone Yansıtma)**: Kullanıcılar, iPhone'ları fiziksel olarak yanlarında olmasa veya kilitli olsa bile, Mac ekranı üzerinden telefonlarına tam erişim sağlayabilmektedir. Telefon ekranı Mac masaüstünde bir pencere olarak açılmakta, klavye ve fare ile telefon uygulamaları kontrol edilebilmekte ve iPhone bildirimleri Mac bildirim merkezine düşmektedir. Bu özellik, süreklilik (Continuity) kavramını bir üst seviyeye taşıyarak, iki farklı işletim sisteminin tek bir arayüzde birleşmesini sağlar.

- **Pencere Döşeme (Window Tiling)**: Windows işletim sisteminde yıllardır var olan ve kullanıcıların pencereleri ekranın kenarlarına sürükleyerek otomatik düzenlemesini sağlayan özellik, macOS Sequoia ile Apple ekosistemine de dahil olmuştur. Bu, özellikle büyük ekranlı Mac kullanıcıları için çoklu görev yönetimini kolaylaştıran bir adımdır.

- **Passwords Uygulaması**: Daha önce sistem ayarları içine gömülü olan iCloud Anahtar Zinciri, artık bağımsız bir "Passwords" uygulaması olarak sunulmaktadır. Bu uygulama, parolaların, geçiş anahtarlarının (passkeys) ve Wi-Fi şifrelerinin güvenli bir şekilde saklanmasını ve Windows dahil diğer cihazlarla senkronize edilmesini sağlar.

- **Apple Intelligence**: M1 ve üzeri işlemcili Mac'lerde sunulan bu özellik seti, işletim sistemi genelinde metin yazma, özetleme ve görsel oluşturma araçları sunar. Siri'nin daha bağlamsal ve doğal çalışmasını sağlayan bu entegrasyon, yapay zekanın işletim sisteminin bir "uygulaması" değil, "dokusu" haline geldiğini gösterir.

### 4.3. Linux ve Özgür Yazılım Felsefesi

Linux, 1991 yılında Linus Torvalds tarafından geliştirilen, UNIX benzeri, açık kaynak kodlu ve ücretsiz bir çekirdektir. "Özgür Yazılım" (Free Software) felsefesiyle geliştirilen Linux, kodlarının herkese açık olması (GPL lisansı) sayesinde, dünya genelinde binlerce geliştiricinin katkısıyla sürekli evrilmektedir. Linux tek başına bir işletim sistemi değil, bir çekirdektir. Bu çekirdeğin, masaüstü ortamı (GNOME, KDE), paket yöneticisi ve yardımcı araçlarla birleştirilerek son kullanıcıya sunulmasına "Linux Dağıtımı" (Distro) denir. Ubuntu, Fedora, Debian ve Red Hat en bilinen dağıtımlardır.

#### 4.3.1. Ulusal İşletim Sistemi Girişimi: PARDUS

Türkiye'nin teknolojik bağımsızlığı ve siber güvenliği açısından stratejik bir öneme sahip olan PARDUS projesi, 2003 yılında TÜBİTAK BİLGEM bünyesinde başlatılmıştır. Adını Anadolu parsından alan proje, kamu kurumlarının ve savunma sanayisinin kapalı kaynak kodlu yabancı yazılımlara olan bağımlılığını azaltmayı ve lisans maliyetlerinden tasarruf etmeyi amaçlar.

**PARDUS'un Dönüşümü ve Sürümleri**: Başlangıçta kendine özgü paket yönetim sistemi (PİSİ) ve yapılandırma araçları (ÇOMAR, YALI) ile tamamen özgün bir yapı sunan PARDUS, 2013 yılından itibaren sürdürülebilirliği artırmak ve geniş paket havuzundan yararlanmak amacıyla Debian tabanına geçiş yapmıştır. Güncel PARDUS ailesi şu ana varyasyonları içerir:

- **Pardus Kurumsal**: Kamu kurumları ve şirketler için optimize edilmiş, kararlı (LTS) ve merkezi yönetim desteği sunan sürüm.
- **Pardus ETAP (Etkileşimli Tahta Projesi)**: MEB FATİH projesi kapsamındaki akıllı tahtalar için özel olarak geliştirilmiş, dokunmatik ekran uyumlu arayüze sahip sürüm.
- **Pardus Sunucu**: Grafik arayüzsüz, performans odaklı sunucu sürümü.

PARDUS'un açık kaynak kodlu olması, ulusal güvenlik açısından kritik bir avantajdır; kodların incelenebilir olması "arka kapı" (backdoor) riskini ortadan kaldırır. Ayrıca, Windows ve Office lisans ücretlerinin yarattığı döviz çıktısını engelleyerek ekonomik katkı sağlar.

## 5. Mobil İşletim Sistemleri: Mimari Derinlik ve Ekosistem Savaşı

Akıllı telefonların yaygınlaşmasıyla birlikte, mobil işletim sistemleri teknoloji dünyasının merkezi haline gelmiştir. 2025 itibarıyla pazar, Google'ın Android'i (~%72) ve Apple'ın iOS'u (~%28) arasında paylaşılmaktadır. Bu iki platform, benzer işlevleri sunsa da, mimari ve felsefi açıdan taban tabana zıt yaklaşımları temsil eder.

### 5.1. Android İşletim Sistemi: Açıklık ve Modülerlik

Google tarafından geliştirilen Android, Linux çekirdeği üzerine inşa edilmiş, açık kaynak kodlu (AOSP) bir platformdur. Üreticilere (Samsung, Xiaomi vb.) sistemi özelleştirme imkanı vermesi, pazar hakimiyetinin temel sebebidir.

#### 5.1.1. Android Katmanlı Mimarisi (Layered Architecture)

Android'in mimarisi, alttan üste doğru dört ana katmandan oluşur ve her katman bir alttakine bağımlıdır:

1. **Linux Çekirdeği (Kernel Layer)**: En alt katmandır. Güç yönetimi, bellek yönetimi ve donanım sürücüleri (kamera, ekran, Wi-Fi, ses) burada bulunur. Android, standart Linux çekirdeğine mobil cihazlara özgü güç yönetimi (wakelocks) ve bellek yönetimi (Low Memory Killer) yamaları ekler.

2. **Donanım Soyutlama Katmanı (HAL - Hardware Abstraction Layer)**: Üst katmanların donanımla iletişim kurmasını sağlayan standart arayüzdür. Örneğin, bir kamera uygulaması, fiziksel kamera sensörünün Sony mi Samsung mu olduğunu bilmez; sadece HAL'in sunduğu "fotoğraf çek" komutunu çağırır. HAL, bu komutu ilgili donanım sürücüsüne tercüme eder. Kaynağındaki örnekte belirtildiği gibi; kullanıcı butona bastığında Uygulama katmanı Framework'e, Framework HAL'e, HAL Kernel sürücüsüne istek gönderir ve veri aynı yoldan geri döner.

3. **Android Runtime (ART) ve Kütüphaneler**:
   - **ART**: Uygulamaların çalıştığı sanal makinedir. Android 5.0'dan itibaren Dalvik'in yerini almıştır. Her uygulama kendi ART örneğinde (instance) ve kendi işleminde (process) çalışır. Bu izolasyon, bir uygulamanın çökmesinin tüm sistemi etkilemesini engeller.
   - **Native Libraries**: C ve C++ ile yazılmış, performans kritik kütüphanelerdir (Grafik için OpenGL/Vulkan, Veritabanı için SQLite, Web tarayıcı motoru için WebKit).

4. **Uygulama Çatısı (Application Framework)**: Geliştiricilerin kullandığı API setidir. Bildirim yöneticisi (Notification Manager), Aktivite yöneticisi (Activity Manager) ve Konum servisleri burada yer alır.

5. **Uygulamalar (System Apps)**: Kullanıcının etkileşime girdiği Telefon, SMS, Tarayıcı gibi ön yüklü ve sonradan yüklenen uygulamalar.

#### 5.1.2. Android 16 ve Gelecek Vizyonu

Haziran 2025 itibarıyla kullanıma sunulan Android 16, mimari açıdan önemli iyileştirmeler içermektedir.

- **Modüler Güncellemeler (Project Mainline)**: Google, "Project Mainline" kapsamında, işletim sisteminin çekirdek bileşenlerini (örneğin ART modülü, medya kodekleri) tam bir sistem güncellemesine gerek kalmadan Google Play üzerinden güncelleyebilmektedir. Android 16, bu modülerliği daha da derinleştirerek, eski cihazların bile (Android 12 ve üzeri) en güncel çalışma zamanı (Runtime) iyileştirmelerini almasını sağlar.

- **Sanallaştırma (Android Virtualization Framework - AVF)**: Android 16, işletim sistemi içinde izole edilmiş sanal makineler (VM) çalıştırma yeteneğini geliştirmiştir. Bu özellik, biyometrik verilerin işlenmesi veya hassas kurumsal uygulamaların çalıştırılması gibi yüksek güvenlik gerektiren işlemlerin, ana işletim sisteminden tamamen yalıtılmış bir ortamda yapılmasını sağlar.

- **16 KB Sayfa Boyutu Desteği**: Geleneksel 4 KB bellek sayfası yerine 16 KB sayfa boyutu desteği getirilmiştir. Bu, bellek yönetim biriminin (MMU) yükünü azaltarak, özellikle yüksek RAM kapasiteli modern cihazlarda genel sistem performansını artırır.

### 5.2. Apple iOS İşletim Sistemi: Kapalı Devre Mükemmeliyet

Apple'ın mobil cihazları için geliştirdiği iOS, "Donanım ve Yazılımın Bütünleşmesi" felsefesine dayanır. Kapalı kaynak kodlu yapısı ve App Store üzerindeki sıkı denetimi, güvenliği ve kullanıcı deneyimi standardını yüksek tutar.

#### 5.2.1. iOS Mimari Katmanları

iOS mimarisi de katmanlıdır ancak isimlendirme ve sorumluluklar farklılaşır:

1. **Core OS (Çekirdek İşletim Sistemi)**: En alt katmandır. XNU çekirdeği üzerine kuruludur. Bellek yönetimi, dosya sistemi, güç yönetimi ve donanım güvenliği (Secure Enclave iletişimi) burada yönetilir. Bu katman, uygulamaların donanımla doğrudan konuşmasını engeller; tüm erişimler sıkı güvenlik politikalarından geçer.

2. **Core Services (Çekirdek Servisler)**: Grafik arayüzü olmayan ancak uygulamaların çalışması için kritik olan servisleri barındırır. Ağ yönetimi (Networking), iCloud veri senkronizasyonu, konum servisleri (Core Location) ve veritabanı yönetimi (Core Data) bu katmandadır.

3. **Media Katmanı**: Grafik, ses ve video işleme teknolojilerini içerir. Core Audio, Core Image ve oyunlar için Metal grafik motoru bu katmanda yer alır. iOS'un meşhur akıcı animasyonları ve multimedya performansı bu katmandaki optimizasyonlara dayanır.

4. **Cocoa Touch (Dokunmatik Arayüz)**: En üst katmandır. Kullanıcının dokunduğu ve gördüğü her şeyin yönetiminden sorumludur. UIKit çerçevesi (framework), butonlar, listeler, dokunmatik jest algılama (Multi-touch), ivmeölçer verileri ve kamera arayüzü burada yönetilir.

#### 5.2.2. Güvenlik ve Ekosistem Kontrolü

iOS'un en belirgin özelliği, uygulama yükleme sürecindeki sıkı kontrolüdür. Uygulamalar (Avrupa Birliği'ndeki yasal zorunluluklar nedeniyle esneme olsa da) temel olarak sadece App Store üzerinden yüklenebilir. Her uygulama "Sandbox" adı verilen yalıtılmış bir alanda çalışır. Bir uygulama, diğer uygulamanın verilerine veya sistem dosyalarına izinsiz erişemez. Bu durum, iOS ekosisteminde zararlı yazılım (malware) oranının Android'e kıyasla çok daha düşük olmasını sağlar.

## 6. Karşılaştırmalı Analiz ve Sentez

İşletim sistemleri dünyasındaki rekabet, sadece pazar payı mücadelesi değil, aynı zamanda bir felsefe çatışmasıdır. Aşağıdaki tablolar ve analizler, bu farklılıkları somutlaştırmaktadır.

### 6.1. Masaüstü ve Mobil Sistemlerin Karşılaştırması

**Tablo 2: Masaüstü İşletim Sistemleri Karşılaştırması**

| Özellik | Windows 11 (24H2) | macOS Sequoia | Linux (Pardus/Ubuntu) |
|---------|------------------|---------------|----------------------|
| Çekirdek Tipi | Hibrit (NT Kernel) - Rust destekli | Hibrit (XNU - Mach + BSD) | Monolitik (Linux Kernel) |
| Lisans Modeli | Kapalı Kaynak (Ticari) | Kapalı Kaynak (Ticari) | Açık Kaynak (GPL - Ücretsiz) |
| Donanım Uyumluluğu | Çok Geniş (Binlerce üretici) | Sadece Apple Donanımı | Geniş (Topluluk sürücüleri) |
| Yapay Zeka | Copilot, Recall (NPU Odaklı) | Apple Intelligence (Entegre) | Dağıtıma göre değişir |
| Güvenlik Yaklaşımı | Defender, VBS, Sıkı Güncelleme | Gatekeeper, Sandbox, T2/M Çip | İzin yönetimi, Açık Kaynak Denetimi |
| Hedef Kitle | Genel Kullanıcı, Oyuncu, Kurumsal | Yaratıcı Profesyonel, Geliştirici | Sunucu, Yazılımcı, Kamu (Pardus) |

**Tablo 3: Mobil İşletim Sistemleri Mimari Farklılıkları**

| Özellik | Android 16 | iOS 18 |
|---------|-----------|--------|
| Taban Çekirdek | Linux (Modifiye edilmiş) | XNU (Darwin) |
| Uygulama Dili | Java, Kotlin (ART üzerinde) | Swift, Objective-C (Native) |
| Donanım Erişimi | HAL (Hardware Abstraction Layer) | Doğrudan Core OS sürücüleri |
| Güncelleme Modeli | Parçalı (Üretici + Google Play) | Merkezi (Tüm cihazlara aynı anda) |
| Mağaza Politikası | Açık (Google Play + APK + Diğerleri) | Kapalı (App Store - İstisnalar hariç) |
| Dosya Yönetimi | Kullanıcı erişimine açık dosya sistemi | Uygulama bazlı kısıtlı erişim |

### 6.2. Gelecek Trendleri: Yakınsama ve Zeka

Raporun analizi, işletim sistemlerinin geleceğinde iki ana trendin hakim olacağını göstermektedir:

**Mobil ve Masaüstü Yakınsaması (Convergence)**: macOS Sequoia'nın iPhone yansıtma özelliği ve Windows 11'in Android alt sistemi (WSA) vizyonu, cihazlar arası sınırların kalktığını göstermektedir. Gelecekte "mobil" veya "masaüstü" işletim sistemi ayrımı yerine, ekran boyutuna ve giriş yöntemine (dokunmatik, klavye, ses) göre şekil değiştiren tek bir "Uyarlanabilir İşletim Sistemi" kavramı öne çıkacaktır.

**Yapay Zeka Entegrasyonu**: Windows Recall ve Apple Intelligence örneklerinde görüldüğü üzere, yapay zeka artık bir uygulama değil, işletim sisteminin bir katmanıdır. Kullanıcılar dosya ve klasör yapıları içinde kaybolmak yerine, doğal dil ile (örneğin "Geçen hafta Antalya tatilinde çektiğim fotoğrafları göster") sistemle iletişim kuracaktır. Bu durum, Grafik Kullanıcı Arayüzü'nden (GUI), Doğal Dil Arayüzü'ne (NLI) geçişin habercisidir.

## 7. Sonuç

İşletim sistemleri, ENIAC'ın kablolarla programlandığı günlerden, kullanıcısının niyetini okuyan yapay zeka destekli platformlara dönüşerek, insan-makine etkileşiminin en kritik arayüzü olmuştur. Bu raporda sunulan veriler, işletim sistemlerinin sadece donanım yöneten yazılımlar olmadığını; güvenlik, gizlilik, verimlilik ve kullanıcı deneyimi ekseninde şekillenen devasa ekosistemler olduğunu ortaya koymaktadır.

Türkiye özelinde PARDUS gibi milli işletim sistemi girişimleri, küresel teknoloji tekellerine karşı dijital egemenliğin korunması ve siber güvenliğin sağlanması açısından hayati öneme sahiptir. Açık kaynak kodlu sistemlerin sunduğu şeffaflık, ulusal verinin güvenliği için en sağlam temeli oluşturmaktadır.

Gelecekte işletim sistemleri, donanım detaylarını kullanıcıdan tamamen gizleyen, cihazlar arası geçişi kesintisiz hale getiren ve proaktif birer asistan gibi çalışan akıllı yapılara evrilecektir. Bu dönüşümde, donanım (NPU, bellek) ve yazılım (AI modelleri, Kernel optimizasyonları) arasındaki entegrasyon başarısı, platformların kaderini belirleyen en önemli faktör olacaktır.

