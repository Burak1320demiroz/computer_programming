# Temel Bilgi Teknolojileri ve Dijital Güvenlik: Kapsamlı Analiz ve Uygulama Raporu

## 1. Dijital Dönüşüm ve İnternet Ekosisteminin Temelleri

Günümüz bilgi çağında, bilgisayar sistemlerinin hayatımıza entegrasyonu, sadece bir teknolojik kolaylık olmaktan çıkmış, toplumsal ve iktisadi yapının temel taşı haline gelmiştir. Bu dönüşümün merkezinde, dünya üzerindeki milyarlarca cihazı birbirine bağlayan devasa ağ yapısı, yani internet bulunmaktadır. İnternet teknolojileri, masaüstü bilgisayarlardan akıllı telefonlara, televizyonlardan ev aletlerine kadar uzanan "Nesnelerin İnterneti" (IoT) kavramını hayatımıza sokmuş ve bu cihazların birbirleriyle sürekli iletişim halinde olduğu bir ekosistem yaratmıştır. Bu bağlamda, temel bilgisayar kullanımı eğitimi, sadece donanım ve yazılımı kullanmayı öğrenmek değil, aynı zamanda bu devasa bilgi ağında güvenli, verimli ve etik bir şekilde var olabilme becerisini kazanmak anlamına gelmektedir.1

Bilgisayarların ve akıllı cihazların internete bağlanabilmesi, çift yönlü bir veri transferini zorunlu kılar. Bu iletişim, kullanıcının bilgiye erişmesini sağlarken, aynı zamanda cihazın dış dünyaya açılması anlamına da gelmektedir. Bu dışa açılma süreci, Web Tarayıcıları (Web Browsers) adı verilen özel yazılımlar aracılığıyla gerçekleşir. Web tarayıcıları, World Wide Web (WWW) üzerinde bulunan sonsuz bilgi kaynağını işleyerek, metin, görsel ve işitsel verileri kullanıcının anlayabileceği bir formata dönüştürür. Ancak, bu erişim kolaylığı beraberinde ciddi güvenlik risklerini de getirmektedir. Ulaşılan bilginin doğruluğunun teyidi ve bu bilgiye erişim sürecinde sistemin bütünlüğünün korunması, dijital okuryazarlığın en kritik yetkinliklerinden biri haline gelmiştir.1

Siber uzayda veri transferinin çift yönlü doğası, kullanıcıyı sadece bir bilgi tüketicisi olmaktan çıkarıp, aynı zamanda potansiyel bir veri sağlayıcısı ve siber saldırı hedefi haline getirir. Kötü amaçlı yazılımların (malware) sistemlere sızma girişimleri, kişisel verilerin çalınması riski ve sistem kaynaklarının yetkisiz kullanımı, kullanıcıların proaktif bir güvenlik anlayışı geliştirmesini zorunlu kılmaktadır. Bu rapor, temel bilgisayar kullanımı çerçevesinde, tehdit unsurlarını tanıma, savunma mekanizmalarını (antivirüs yazılımları, güvenlik duvarları) etkin kullanma ve web teknolojilerine hakimiyet konularını derinlemesine incelemeyi amaçlamaktadır. Dijital dünyada "bilinçli kullanıcı" olmak, sadece doğru bilgiye ulaşmakla sınırlı kalmayıp, aynı zamanda dijital varlıklarını koruma altına alabilme kapasitesini de içermektedir.1

## 2. Siber Tehdit Peyzajı: Kötü Amaçlı Yazılımların Derinlemesine Analizi

Bilgisayar sistemlerinin güvenliğini tehdit eden unsurların başında, genel literatürde "Kötü Amaçlı Yazılımlar" veya teknik adıyla "Malware" (Malicious Software) olarak adlandırılan yazılımlar gelmektedir. Bu yazılımlar, bilgisayar sistemlerine, ağ altyapılarına veya mobil cihazlara zarar vermek, hassas verileri ele geçirmek, sistem işleyişini bozmak veya kullanıcının rızası dışında eylemler gerçekleştirmek amacıyla tasarlanmış, işletilebilir kod parçacıklarıdır. Kötü amaçlı yazılımların evrimi, basit şaka programlarından, devlet destekli siber casusluk araçlarına ve organize suç örgütlerinin finansal kazanç sağladığı fidye yazılımlarına kadar geniş bir yelpazeye yayılmıştır.1

Bu yazılımların en belirgin özelliği, kullanıcının bilgisi ve onayı olmaksızın sisteme yüklenmeleri ve arka planda gizlice faaliyet göstermeleridir. Bir sistemin "enfekte" olması, sadece o cihazın performansının düşmesiyle sınırlı kalmaz; aynı zamanda ağ üzerindeki diğer cihazlar için de bir tehdit kaynağı haline gelmesine neden olabilir. Kötü amaçlı yazılımlar, programlama amaçlarına, yayılma yöntemlerine ve sistem üzerinde yarattıkları etkilere göre çeşitli kategorilere ayrılmaktadır. Bu sınıflandırma, tehdidin doğasını anlamak ve doğru savunma stratejisini geliştirmek için elzemdir. Atatürk Üniversitesi ders materyallerinde ve modern siber güvenlik literatüründe öne çıkan temel kategoriler şunlardır: Virüsler, Solucanlar (Worms), Truva Atları (Trojans), Casus Yazılımlar (Spyware), Reklam Yazılımları (Adware) ve Spam (Çöp E-posta).1

### 2.1. Kötü Amaçlı Yazılımların Genel Karakteristiği ve Etkileri

Kötü amaçlı yazılımların sistem üzerindeki etkileri, yazılımın türüne göre değişiklik gösterse de, temel hedefleri genellikle sistemin bütünlüğünü (Integrity), gizliliğini (Confidentiality) veya erişilebilirliğini (Availability) bozmaktır. Bu üçlü, bilgi güvenliğinin CIA (Confidentiality, Integrity, Availability) üçgeni olarak bilinir ve malware saldırıları doğrudan bu prensipleri hedef alır.

- **Sistem Bütünlüğünün Bozulması**: Virüsler ve dosya enfektörleri, sistem dosyalarının yapısını değiştirerek, işletim sisteminin kararsız çalışmasına veya tamamen çökmesine neden olabilir.
- **Veri Hırsızlığı ve Gizlilik İhlali**: Casus yazılımlar ve keylogger'lar (tuş kaydediciler), kullanıcının şifrelerini, kredi kartı bilgilerini ve özel yazışmalarını çalarak üçüncü şahıslara iletir.
- **Sistem Kaynaklarının Tüketilmesi**: Solucanlar ve botnet ajanları, sistemin işlemci gücünü ve ağ bant genişliğini kullanarak cihazı yavaşlatır veya kullanılmaz hale getirir.
- **Erişimin Engellenmesi**: Fidye yazılımları (Ransomware), kullanıcı dosyalarını şifreleyerek verilere erişimi engeller ve verilerin kurtarılması karşılığında fidye talep eder.1

## 3. Virüslerin Yapısal Mimarisi ve Bulaşma Vektörleri

Siber tehditler arasında en bilinen ve tarihsel olarak en eski kategori olan "Virüsler", biyolojik virüslerin çalışma prensibine benzer bir mekanizmaya sahiptir. Bir bilgisayar virüsü, kendi kodunu başka bir programın veya dosyanın içine yerleştirerek (enfekte ederek) çoğalan ve yayılan bir yazılımdır. Virüslerin en kritik özelliği, hayatta kalmak ve çoğalmak için bir "konakçı" (host) dosyaya ihtiyaç duymalarıdır. Kullanıcı, enfekte olmuş programı çalıştırdığında, virüs kodu da belleğe yüklenir ve aktif hale gelir.1

Virüslerin karmaşıklığı zaman içinde artmış olsa da, temel yayılma stratejileri sistemin belirli alanlarına nüfuz etme üzerine kuruludur. Bu alanlara göre virüsler üç ana kategoride incelenebilir: Dosya Sistemi Virüsleri, Ön Yükleme (Boot Sector) Virüsleri ve Makro Yazılım Virüsleri.

### 3.1. Dosya Sistemi Virüsleri (File Infectors)

Dosya sistemi virüsleri, işletim sisteminde doğrudan çalıştırılabilir nitelikte olan dosyalara bulaşır. Windows işletim sistemlerinde bu dosyalar genellikle .EXE (Executable) ve .COM (Command) uzantılarına sahiptir. Ancak, modern virüsler .DLL, .SYS ve .SCR gibi sistem kütüphanelerini ve ekran koruyucu dosyalarını da hedef alabilmektedir.1

Bu virüslerin çalışma mantığı, zararlı kodun hedef dosyanın kod yapısına eklemlenmesi şeklindedir. Enfeksiyon yöntemleri şunlardır:

- **Başa Ekleme (Prepending)**: Virüs, kendi kodunu orijinal dosyanın en başına ekler. Kullanıcı programı çalıştırdığında, işlemci akışı önce virüs kodunu çalıştırır, virüs belleğe yerleşir ve ardından kontrolü orijinal programa devreder. Bu sayede kullanıcı, programın normal çalıştığını düşünürken arka planda virüs aktif olur.
- **Sona Ekleme (Appending)**: Virüs, kodunu dosyanın sonuna ekler ve dosyanın başındaki "Giriş Noktası" (Entry Point) adresini, dosyanın sonundaki virüs koduna yönlendirecek şekilde değiştirir (JUMP komutu).
- **Boşluklara Yerleşme (Cavity Infection)**: Bazı gelişmiş virüsler, dosya boyutunu değiştirmeden, dosya içindeki kullanılmayan boş alanlara kodlarını parçalayarak yerleştirir. Bu yöntem, virüsün antivirüs yazılımları tarafından dosya boyutu değişimi üzerinden tespit edilmesini zorlaştırır.

Dosya sistemi virüsleri, bulaştıkları sistemde diğer çalıştırılabilir dosyaları tarar ve onlara da kendi kodlarını enjekte ederek hızla çoğalır. Bazı türleri, bulaştıkları dosyaların niteliklerini (attributes) değiştirerek (örneğin "Salt Okunur" veya "Gizli" yaparak) kullanıcının müdahalesini veya dosyanın silinmesini engeller.1

### 3.2. Ön Yükleme (Boot Sector) Virüsleri

Bilgisayarın açılış sürecinin en kritik aşaması, işletim sisteminin sabit diskten belleğe yüklenmesidir. Bu işlem, sabit diskin ilk sektöründe bulunan "Master Boot Record" (MBR) adı verilen özel bir veri yapısı tarafından yönetilir. MBR, diskteki bölümleri tanımlar ve işletim sisteminin çekirdeğinin (kernel) nerede bulunduğunu BIOS'a bildirir.

Ön yükleme virüsleri, kendilerini bu MBR alanına veya disketlerin/USB belleklerin boot sektörüne yazar.

**Mekanizma**: Bilgisayar açıldığında, BIOS (Basic Input/Output System) kontrolü MBR'ye devreder. Eğer MBR virüs tarafından enfekte edilmişse, işletim sistemi yüklenmeden önce virüs belleğe yüklenir. Bu, virüse sistem üzerinde tam bir kontrol (root seviyesinde yetki) sağlar. Virüs belleğe yerleştikten sonra, disk okuma/yazma işlemlerini (INT 13h kesmesi gibi) izleyerek sisteme takılan diğer disketlere veya USB belleklere kendini kopyalar.

**Tarihsel Gelişim ve Modern Durum**: Eskiden disketler aracılığıyla yayılan bu virüsler, günümüzde USB bellekler üzerinden yayılmaktadır. Bir bilgisayarda ön yükleme virüsü varsa ve o bilgisayara takılı bir USB bellek ile sistem yeniden başlatılırsa, virüs belleğe bulaşabilir. Modern işletim sistemleri (Windows 10/11) ve yeni donanım standartları (UEFI ve Secure Boot), boot sektörünün değiştirilmesini dijital imzalarla denetleyerek bu tehdidi büyük ölçüde azaltmıştır, ancak tamamen ortadan kalkmamıştır.1

### 3.3. Makro Yazılım Virüsleri

Makrolar, Microsoft Office (Word, Excel, PowerPoint) gibi yazılımlarda sık tekrarlanan işlemleri otomatikleştirmek için kullanılan, genellikle Visual Basic for Applications (VBA) diliyle yazılmış küçük programlardır. Makro virüsleri, bu otomasyon yeteneğini kötüye kullanarak yayılır.

**Bulaşma Yöntemi**: Bir ofis belgesi (örneğin .doc, .xls) içine gizlenen makro virüsü, kullanıcı belgeyi açtığında otomatik olarak çalışır. Virüs, ofis yazılımının genel şablon dosyasına (örneğin Word için Normal.dot veya Normal.dotm) kendini kopyalar. Bu andan itibaren, kullanıcının oluşturduğu veya açtığı her yeni belge, şablondan virüsü alarak enfekte olur.

**Yayılma**: E-posta ekleri, makro virüslerinin en yaygın yayılma vektörüdür. "Fatura", "Sipariş Formu" gibi isimlerle gelen sahte belgeler, kullanıcıyı belgeyi açmaya ve "İçeriği Etkinleştir" (Enable Content) butonuna tıklamaya ikna etmeye çalışır.

**Risk**: Makro virüsleri, sadece belgeyi bozmakla kalmaz; işletim sistemi komutlarını çalıştırabilir, dosya silebilir, e-posta programını kullanarak kişi listesindeki herkese kendini gönderebilir veya başka zararlı yazılımları (dropper işlevi görerek) internetten indirebilir.1

## 4. Ağ Tabanlı Tehditler ve Sistem Manipülasyonu

Virüslerin aksine, modern siber tehditlerin büyük bir kısmı kullanıcı müdahalesine ihtiyaç duymadan veya kullanıcıyı manipüle ederek sistemlere sızmayı hedefler. Bu kategoride Solucanlar ve Truva Atları öne çıkmaktadır.

### 4.1. Solucanlar (Worms): Otonom Yayılma Makineleri

Solucanlar, virüslerden temel bir farkla ayrılır: Bir konakçı dosyaya ihtiyaç duymazlar. Kendi başlarına çalışabilen, bağımsız programlardır ve en belirgin özellikleri ağ üzerinden kendi kendilerini kopyalayarak yayılabilmeleridir.1

**Yayılma Mekanizması**: Solucanlar, işletim sistemlerinin veya ağ servislerinin güvenlik açıklarını (vulnerabilities) kullanır. Bir sisteme bulaştıktan sonra, ağ üzerindeki diğer bilgisayarları tarar (IP taraması). Açık bir port veya yamasız bir güvenlik açığı bulduğunda, kendini o sisteme kopyalar ve orada da çalışmaya başlar. Bu işlem zincirleme bir reaksiyon gibi katlanarak devam eder.

**E-posta Yoluyla Yayılma**: Solucanlar, bulaştıkları bilgisayardaki e-posta adres defterlerini, web tarayıcı önbelleklerini ve sosyal medya arkadaş listelerini tarar. Topladığı adreslere, kendini ek dosya veya zararlı bir link olarak içeren e-postalar gönderir. E-posta, genellikle tanıdık bir isimden geliyormuş gibi göründüğü için (spoofing), alıcının tuzağa düşme ihtimali yüksektir.

**Etkileri**: Solucanların birincil zararı genellikle ağ trafiğini aşırı yoğunlaştırmaktır. Binlerce kopyanın aynı anda ağ üzerinde dolaşması, bant genişliğini tüketerek internet erişimini yavaşlatır veya tamamen keser (Denial of Service). Ayrıca, sistemlere "arka kapı" (backdoor) açarak saldırganların sisteme uzaktan erişimini sağlarlar.1

### 4.2. Truva Atları (Trojan Horses): Aldatma Sanatı

Adını Yunan mitolojisindeki Truva Atı efsanesinden alan bu yazılımlar, kendilerini yararlı veya eğlenceli bir program gibi göstererek kullanıcının güvenini kazanır ve sistemine kendi eliyle yüklemesini sağlar.

**Gizlenme**: Bir Truva atı; bir oyun yaması (crack), bedava bir yardımcı program, bir ekran koruyucu veya popüler bir uygulamanın korsan sürümü gibi görünebilir. Kullanıcı programı indirip çalıştırdığında, program vaat ettiği işlevi yerine getirebilir (veya getirmeyebilir), ancak arka planda gizli zararlı kod aktif hale gelir.

**Virüslerden Farkı**: Truva atları kendi kendilerine çoğalmazlar (dosya enfekte etmezler). Yayılmak için kullanıcının onları indirmesine ve dağıtmasına muhtaçtırlar.

**Zararları**: Truva atlarının zararlı etkileri çok çeşitlidir ve genellikle "Payload" (Yük) olarak adlandırılan zararlı modüle bağlıdır:

- **Veri Hırsızlığı**: Şifreleri, banka bilgilerini ve kişisel dosyaları çalar.
- **Dosya Manipülasyonu**: Dosyaları silebilir, değiştirebilir veya şifreleyebilir (Fidye yazılımlarının dağıtımında sıkça kullanılır).
- **Uzaktan Erişim (RAT)**: Saldırgana, enfekte olan bilgisayar üzerinde tam kontrol sağlar (ekran görüntüsü alma, kamerayı açma, dosya indirme).
- **Botnet Katılımı**: Bilgisayarı bir "zombi" cihaza dönüştürerek, saldırganın komutası altında DDoS saldırıları gibi yasa dışı eylemlerde kullanılmasını sağlar.1

### 4.3. Casus Yazılımlar (Spyware) ve Dijital Takip

Casus yazılımlar, kullanıcının haberi olmadan sistemdeki aktiviteleri izleyen, veri toplayan ve bu verileri üçüncü taraflara ileten yazılımlardır. Genellikle ücretsiz indirilen yazılımlarla (bundleware) birlikte yüklenirler.

**İzleme Kapsamı**: Klavye hareketlerini kaydetmek (Keylogger), ziyaret edilen web sitelerini raporlamak, ekran görüntülerini almak ve formlara girilen verileri (kredi kartı numaraları gibi) çalmak temel işlevleridir.

**Adware (Reklam Yazılımları)**: Casus yazılımların bir alt türü veya onlarla birlikte çalışan yazılımlardır. Kullanıcının tarayıcı alışkanlıklarını analiz ederek hedefli reklamlar gösterirler. Tarayıcı ana sayfasını değiştirmek, istenmeyen araç çubukları (toolbar) eklemek ve sürekli açılan pop-up pencereler, sistemde adware olduğunun işaretidir.1

### 4.4. Spam (Çöp E-posta) ve Oltalama

Spam, kullanıcının isteği dışında gönderilen, genellikle ticari veya dolandırıcılık amaçlı toplu e-postalardır. Spam göndericileri (spammers), e-posta adreslerini virüsler aracılığıyla çalınan adres defterlerinden, web sitelerinden veya veri sızıntılarından elde ederler.

Spam'ın tehlikesi sadece posta kutusunu doldurması değil, aynı zamanda Oltalama (Phishing) saldırıları için ana dağıtım kanalı olmasıdır. "Banka hesabınız kilitlendi", "Ödül kazandınız" veya "Kargonuz teslim edilemedi" gibi sahte senaryolarla gelen e-postalar, kullanıcıyı sahte web sitelerine yönlendirerek kimlik bilgilerini çalmayı hedefler.

## 5. Siber Savunma Stratejileri: Antivirüs Yazılımları ve Güvenlik Duvarları

Kötü amaçlı yazılımların çeşitliliği ve sofistike yapısı, çok katmanlı bir savunma stratejisini zorunlu kılmaktadır. Bu stratejinin en temel bileşeni Antivirüs Yazılımlarıdır.

### 5.1. Antivirüs Yazılımlarının Çalışma Prensipleri

Antivirüs yazılımları, bilgisayar sistemlerini zararlı kodlara karşı korumak, tespit etmek ve temizlemek için geliştirilmiş güvenlik araçlarıdır. Çalışma prensipleri temel olarak üç yönteme dayanır:

1. **İmza Tabanlı Tarama (Signature-based Detection)**: Antivirüs üreticileri, tespit ettikleri her virüsün benzersiz kod yapısını (imzasını) bir veritabanına kaydeder. Antivirüs programı, taranan dosyanın içeriğini bu veritabanındaki imzalarla karşılaştırır. Eşleşme varsa dosya zararlı olarak işaretlenir. Bu yöntem bilinen virüslere karşı etkilidir ancak yeni çıkan (Zero-day) tehditleri yakalamakta yetersiz kalabilir.

2. **Sezgisel Analiz (Heuristic Analysis)**: Bilinmeyen virüsleri tespit etmek için kullanılır. Programın kod yapısına değil, davranışına ve şüpheli özelliklerine bakar. Örneğin, bir programın sistem dosyalarını değiştirmeye çalışması veya kendini açılış klasörüne kopyalaması şüpheli bir davranış olarak algılanır.

3. **Gerçek Zamanlı Koruma (Real-time Protection)**: Dosyaların açılması, kopyalanması veya indirilmesi sırasında arka planda sürekli çalışan ve anlık tarama yapan modüldür.2

**Seçkin Antivirüs Çözümleri**: Piyasada birçok güvenilir antivirüs çözümü bulunmaktadır. Ders notlarında ve sektörde öne çıkan markalar şunlardır:

- **Microsoft Defender**: Windows ile entegre gelen yerleşik çözüm.
- **ESET (NOD32)**: Hafif yapısı ve güçlü sezgisel analizi ile bilinir.
- **Norton**: Kapsamlı güvenlik paketleri sunar.
- **Sophos**: Kurumsal ağ güvenliği odaklıdır.
- **Trend Micro**: Bulut tabanlı güvenlik çözümlerinde etkindir.1

**Tamamlayıcı Temizleme Araçları**: Standart antivirüslerin bazen tespit edemediği veya temizleyemediği inatçı zararlılar (özellikle adware ve spyware) için özel araçlar kullanılmalıdır:

- **AdwCleaner**: Tarayıcı hijacker'larını ve reklam yazılımlarını temizler.
- **Malwarebytes (MBAM)**: Gelişmiş anti-malware taraması yapar.
- **RKill**: Zararlı yazılımların işlemlerini (process) sonlandırarak, diğer antivirüslerin çalışmasına olanak tanır.
- **Combofix**: (İleri düzey kullanıcılar için) Derinlemesine sistem temizliği yapar.
- **TDSSKiller**: Rootkit (kök dizin zararlıları) tespiti için kullanılır.1

### 5.2. Güvenlik Duvarı (Firewall) Yönetimi

Güvenlik duvarı, bilgisayar ile internet (veya yerel ağ) arasındaki veri trafiğini kontrol eden bir bariyerdir. Gelen ve giden veri paketlerini önceden belirlenmiş kurallara göre denetler.

**İşlevi**: Yetkisiz erişim girişimlerini (hacker saldırıları, port taramaları) engeller ve bilgisayardaki zararlı yazılımların dışarıya veri göndermesini (Command & Control sunucularına bağlanmasını) bloklar.

**Yapılandırma**: Microsoft Defender Güvenlik Duvarı, "Etki Alanı Ağı", "Özel Ağ" (Ev) ve "Ortak Ağ" (Kafe, Havaalanı) olmak üzere üç farklı profil sunar. Ortak ağlarda güvenlik duvarı ayarları en sıkı seviyede olmalıdır. Güvenlik duvarının kapatılması, sistemi ağ solucanlarına ve uzaktan saldırılara karşı tamamen savunmasız bırakır.

## 6. Microsoft Defender ve Windows Güvenlik Mimarisi

Windows 10 ve 11 işletim sistemlerinde varsayılan olarak gelen Microsoft Defender, ek bir maliyet gerektirmeyen ve işletim sistemiyle tam uyumlu çalışan kapsamlı bir güvenlik çözümüdür.

### 6.1. Temel Özellikler ve Avantajlar

- **Entegrasyon**: İşletim sisteminin çekirdeğine entegre olduğu için performans kaybı minimumdur ve uyumluluk sorunları yaşanmaz.
- **Koruma Kapsamı**: Sadece virüslere karşı değil; fidye yazılımlarına (Ransomware Protection), kimlik avı saldırılarına ve tarayıcı tabanlı tehditlere (SmartScreen) karşı da koruma sağlar.
- **Pasif Mod**: Sisteme başka bir antivirüs (örneğin ESET) yüklendiğinde, Defender kendini otomatik olarak "Pasif Mod"a alır veya devre dışı bırakır. Bu, iki antivirüsün çakışarak sistemi kilitlemesini engeller.

### 6.2. Tarama Seçenekleri ve Kullanım Senaryoları

Windows Güvenliği arayüzü üzerinden dört farklı tarama seçeneği sunulur:

- **Hızlı Tarama**: Sistemin en kritik bölgelerini (kayıt defteri, başlangıç klasörleri, bellek) tarar. Günlük rutin kontroller için idealdir.
- **Tam Tarama**: Sabit diskteki tüm dosyaları, çalışan programları ve yedekleme dosyalarını tarar. Uzun sürer ancak tam temizlik için gereklidir.
- **Özel Tarama**: Kullanıcının seçtiği belirli bir klasörü veya sürücüyü (örneğin şüpheli bir USB belleği) tarar.
- **Microsoft Defender Çevrimdışı Tarama (Offline Scan)**: Bazı virüsler (Rootkitler), işletim sistemi çalışırken kendilerini gizleyebilir veya silinmeyi engelleyebilir. Bu modda bilgisayar yeniden başlatılır ve Windows yüklenmeden önce, güvenli bir ortamda tarama yapılır. İnatçı virüslerin temizlenmesi için en etkili yöntemdir.

## 7. Web Tarayıcı Teknolojileri ve İnternet Erişim Protokolleri

Web tarayıcıları (Browsers), internet üzerindeki HTML belgelerini, görselleri ve diğer medya türlerini işleyerek kullanıcıya sunan istemci yazılımlarıdır. Tarayıcılar, HTTP (HyperText Transfer Protocol) ve HTTPS protokollerini kullanarak sunucularla iletişim kurar.

### 7.1. Yaygın Web Tarayıcıları

Kullanıcı deneyimi, hız, eklenti desteği ve gizlilik özelliklerine göre farklı tarayıcılar tercih edilmektedir:

- **Google Chrome**: Chromium tabanlıdır, geniş eklenti mağazası ve Google servisleri ile entegrasyonu sayesinde pazar lideridir.
- **Microsoft Edge**: Windows 10/11 ile gelen modern tarayıcıdır. O da Chromium tabanlıdır ancak kurumsal özellikler ve performans optimizasyonları sunar.
- **Mozilla Firefox**: Açık kaynak kodlu ve gizlilik odaklı bir tarayıcıdır. Kâr amacı gütmeyen bir vakıf tarafından geliştirilir.
- **Safari**: Apple cihazlarında (Mac, iPhone, iPad) varsayılan tarayıcıdır ve enerji verimliliği ile öne çıkar.
- **Opera / Vivaldi / Yandex**: Yerleşik VPN, reklam engelleyici ve özelleştirilebilir arayüz gibi ekstra özellikler sunan alternatiflerdir.1

### 7.2. Tarayıcı Arayüz Bileşenleri ve Fonksiyonları

Her tarayıcıda bulunan standart özellikler, güvenli ve verimli bir gezinme deneyimi için kritik öneme sahiptir:

| Bileşen | Açıklama ve İşlev | Güvenlik Boyutu |
|---------|-------------------|-----------------|
| Adres Çubuğu (Omnibox) | URL'nin girildiği ve arama yapılan alandır. | Phishing saldırılarını tespit etmek için URL'nin doğruluğu buradan kontrol edilmelidir. Kilit simgesi (HTTPS) güvenli bağlantıyı gösterir. |
| Açılış Sayfası | Tarayıcı ilk açıldığında yüklenen sayfadır. | Zararlı yazılımlar (Browser Hijackers) bu ayarı değiştirerek kullanıcıyı reklam sitelerine yönlendirebilir. |
| Web Geçmişi (History) | Ziyaret edilen sitelerin listesini tutar. | Daha önce girilen bir sayfayı bulmayı kolaylaştırır ancak ortak kullanılan bilgisayarlarda gizlilik riski oluşturur. |
| Gizli Sekme (Incognito) | Geçmişin, çerezlerin ve önbelleğin kaydedilmediği moddur. | Yerel gizlilik sağlar (bilgisayarda iz bırakmaz), ancak internet servis sağlayıcısından (ISP) veya web sitelerinden gizlenmeyi sağlamaz. |

## 8. İnternet Adresleme Sistemi (DNS ve URL Anatomisi)

İnternet üzerindeki her kaynağın (web sitesi, dosya) benzersiz bir adresi vardır. Buna URL (Uniform Resource Locator) denir. Bir web sitesine erişmek için tarayıcının adres çubuğuna girilen adresler, belirli bir hiyerarşik yapıya sahiptir. Bu yapıyı anlamak, sahte siteleri ayırt etmek için hayati önem taşır.

**Örnek Adres**: www.atauni.edu.tr

### 8.1. URL Bileşenlerinin Analizi

- **Protokol (Örn: http:// veya https://)**: İletişim dilini belirler. https, verilerin şifreli olarak iletildiğini gösterir.
- **Alt Alan Adı (Subdomain - Örn: www)**: World Wide Web servisini işaret eder. mail.google.com örneğinde mail bir alt alan adıdır.
- **Alan Adı (Domain Name - Örn: atauni)**: Kurumun veya sitenin kendine özgü adıdır.
- **Tür Kodu (Top-Level Domain / TLD - Örn: .edu)**: Sitenin faaliyet alanını ve türünü belirtir.
- **Ülke Kodu (Country Code TLD - Örn: .tr)**: Sitenin hangi ülkeye ait olduğunu veya o ülkede tescil edildiğini gösterir.

### 8.2. Alan Adı Uzantıları (TLD) ve Anlamları

Kullanıcılar, site uzantılarına bakarak sitenin amacı hakkında fikir sahibi olabilirler. Güvenilir bilgi kaynaklarını tespit etmek için bu uzantıların bilinmesi gerekir.1

| Uzantı | Anlamı (İngilizce) | Kullanım Alanı ve Güvenilirlik Notu |
|--------|-------------------|-------------------------------------|
| .com | Commercial | Ticari şirketler. En yaygın uzantıdır, herkes alabilir. Güvenilirlik değişkenlik gösterir. |
| .edu | Education | Eğitim kurumları (Üniversiteler). Yüksek güvenilirlik. Sadece akredite kurumlar alabilir. |
| .gov | Government | Devlet kurumları. En yüksek güvenilirlik. Resmi bilgi kaynaklarıdır. |
| .org | Organization | Vakıflar, dernekler, kar amacı gütmeyen örgütler. Genellikle güvenilirdir. |
| .net | Network | İnternet servis sağlayıcıları ve ağ teknoloji şirketleri. |
| .mil | Military | Askeri kurumlar. |
| .k12 | Kindergarten-12 | İlk ve orta dereceli okullar (Milli Eğitim Bakanlığına bağlı okullar). |
| .biz | Business | İş dünyası ve ticaret odaklı siteler. |
| .aero | Aeronautics | Havacılık endüstrisi. |

### 8.3. Ülke Kodları (ccTLD)

İnternet adreslerinde kullanılan bazı ülke kodları şunlardır 1:

- **.tr**: Türkiye
- **.de**: Almanya (Deutschland)
- **.uk**: Birleşik Krallık
- **.nl**: Hollanda
- **.ru**: Rusya
- **.ca**: Kanada
- **.es**: İspanya
- **.it**: İtalya
- **.jp**: Japonya

## 9. Güvenli İnternet Kullanımı, Dijital Etik ve Veri Koruma

Teknik önlemler (antivirüs vb.) ne kadar güçlü olursa olsun, güvenlik zincirinin en zayıf halkası insandır. "Sosyal Mühendislik" saldırıları, kullanıcının dikkatsizliğini veya korkularını kullanarak teknik engelleri aşmayı hedefler. Bu nedenle, internette gezinirken uyulması gereken davranış kuralları (Dijital Hijyen) büyük önem taşır.

### 9.1. Güvenli Gezinme İçin Altın Kurallar

**Kaynağı Doğrulama**: Bilimsel veya resmi bilgi ararken .edu ve .gov uzantılı siteler öncelikli tercih edilmelidir. Her okunan bilgiye şüpheyle yaklaşılmalı, bilginin kaynağı ve yazarı kontrol edilmelidir.1

**Dosya İndirme Disiplini**:

- Sadece üreticinin kendi resmi sitesinden veya güvenilir platformlardan indirme yapılmalıdır.
- "Crack", "Serial", "Keygen" gibi illegal yazılım araçları, en yaygın virüs bulaşma kaynaklarıdır; bunlardan uzak durulmalıdır.
- İndirilen her dosya, açılmadan önce mutlaka antivirüs taramasından geçirilmelidir.

**E-posta Güvenliği**: Tanınmayan kişilerden gelen e-postaların ekleri (özellikle .zip, .exe, .docm uzantılılar) asla açılmamalıdır. Bankalardan geliyormuş gibi görünen "Şifrenizi güncelleyin" maillerindeki linklere tıklanmamalı, bankanın adresi tarayıcıya manuel yazılmalıdır.

**Kişisel Verilerin Paylaşımı**: Sosyal ağlarda paylaşılan fotoğraflar, konum bilgileri ve kişisel detaylar, kötü niyetli kişiler tarafından profil oluşturmak (profiling) ve şifre tahmin saldırıları yapmak için kullanılabilir. Gizlilik ayarları "Sadece Arkadaşlar" seviyesinde tutulmalıdır.

**Telif Hakları ve Etik**: İnternet, "sahipsiz" bir alan değildir. Kullanılan görsellerin, metinlerin ve yazılımların telif haklarına saygı gösterilmeli, kaynak belirtilmelidir. Siber zorbalık, hakaret ve tehdit içeren paylaşımlar hukuki suç teşkil eder.

### 9.2. Veri Yedekleme (Backup) Stratejisi

Virüs saldırıları, donanım arızaları veya hırsızlık durumunda veri kaybını önlemenin tek kesin yolu yedeklemedir.

**3-2-1 Kuralı**: Verilerinizin en az 3 kopyası olmalı, bu kopyalar 2 farklı ortamda (örneğin bilgisayar diski ve harici USB disk) saklanmalı ve 1 kopyası fiziksel olarak farklı bir yerde (örneğin Bulut Depolama veya iş yeri) bulunmalıdır.

Düzenli yedekleme, özellikle dosyaları şifreleyen Fidye Yazılımlarına (Ransomware) karşı en etkili savunmadır. Fidye ödemek yerine, sistem temizlenip yedeği geri yüklenerek veri kaybı önlenebilir.

### 9.3. Bilgisayara Program İndirme Süreci

Program indirme süreci, basit gibi görünse de dikkat gerektirir.

1. **Resmi Kaynak**: Yazılımın üreticisinin web sitesi bulunur (Örn: Google Chrome indirmek için google.com/chrome).
2. **İndirme Butonu**: Sayfalarda bazen sahte "İndir" (Download) reklam butonları bulunur. Doğru butonu ayırt etmek gerekir.
3. **Kurulum Aşaması**: İndirilen kurulum dosyası çalıştırıldığında, "İleri" demeden önce ekrandaki yazılar okunmalıdır. Genellikle ücretsiz programlar, kurulum sırasında "Yanında şu tarayıcı eklentisini de kur" gibi kutucukları işaretli getirir (Bundleware). Bu kutucukların işareti kaldırılmalıdır, aksi takdirde sisteme istenmeyen yazılımlar (Adware) yüklenebilir.1

## Sonuç

Bilgi teknolojileri, sunduğu sınırsız olanaklarla birlikte, sürekli evrilen riskleri de beraberinde getirmektedir. Bu raporda detaylandırılan teknik bilgiler ve kullanım stratejileri, kullanıcının dijital dünyada güvenli bir "kale" inşa etmesine yardımcı olmayı amaçlamaktadır. Antivirüs yazılımları bu kalenin surları ise, bilinçli kullanıcı davranışları da kalenin muhafızlarıdır. Güvenlik, bir ürün değil, sürekli devam eden bir süreçtir; sistemlerin güncel tutulması, tehditlerin tanınması ve ihtiyatlı olunması bu sürecin ayrılmaz parçalarıdır.

