### Hayırlı olsun; Türk Not Hükümdarı Android Uygulaması 📝🇹🇷  
Ben bu uygulamayı “sadece not tutulsun” diye yazmadım; **notun düzenini, hızını ve güvenini** eline almak isteyen adamın/hanımın işi olsun diye yazdım.  
Kısa not → çat diye yakala. Checklist → hedefi tokat gibi takip et. Çöp kutusu → yanlış silmeye karşı sigorta. ✨🛡️  

#### Görseller;

![1](https://github.com/user-attachments/assets/d7629577-83b5-4193-a5c0-df10b52a52d5)
![2](https://github.com/user-attachments/assets/800f6a3e-f053-4e30-b97a-d3d9cacca9d6)
![3](https://github.com/user-attachments/assets/41e8e38c-6c14-4a3f-8fb4-68ac61eeac8b)
![4](https://github.com/user-attachments/assets/1727ef03-6dea-4a0b-b2ad-7f7c83fbbbd8)
![5](https://github.com/user-attachments/assets/f8ba05e0-ce5a-46b5-8b83-653de6760a58)
![6](https://github.com/user-attachments/assets/457981cb-efb1-41d3-88e9-7db44b5b517b)
![7](https://github.com/user-attachments/assets/bb856c52-a4e5-4bc2-ab8e-e3eec394b8ca)
![8](https://github.com/user-attachments/assets/a7197ca5-cc52-4417-9e07-ddb4d31617af)
![9](https://github.com/user-attachments/assets/6ccc72ee-6c05-4d76-ae82-497612b6a5ab)
![10](https://github.com/user-attachments/assets/a03b0b21-79dd-4c73-93bc-0ef5c43b973a)
![11](https://github.com/user-attachments/assets/f1dbd7e0-abf3-486e-9de3-5006484d7d50)
![12](https://github.com/user-attachments/assets/a0b48e23-8ba3-40a3-b9a8-1273779046d1)
![13](https://github.com/user-attachments/assets/db9207a1-e77c-4580-892a-1e39c5c7173b)
![14](https://github.com/user-attachments/assets/3d0e845b-d619-48dd-8858-15e53b9083e8)
![15](https://github.com/user-attachments/assets/37557430-7c28-4ee9-bbee-459bc6f07deb)
![16](https://github.com/user-attachments/assets/0c514208-6a25-435a-863e-c277631c224a)
![17](https://github.com/user-attachments/assets/81108cef-ee39-44a8-a83b-74753a0fb812)
![18](https://github.com/user-attachments/assets/028a6c8a-871c-4ba3-8087-a4b1b0b4e3fc)
![19](https://github.com/user-attachments/assets/fc4f0688-5ec6-4e62-96d2-2ee53d01bd15)
![20](https://github.com/user-attachments/assets/dd01c1b9-7ff1-4995-9086-3d7bb42a5544)

### 1) Nedir, ne değildir, ne işe yarar? 🧠
Bu uygulama; **metin notu + checklist notu** odağında, **kategorilerle toparlanan**, aramayla da “**yazdıkça bul**” hissi veren, **offline-first** bir not defteri.  
Benim derdim basit ama netti: Telefonu eline aldığında **3 saniyede hazır ol**, notu **5 saniyede yakala**, sonra da geri dönüp **adam gibi düzenleyebil**. ⏱️💪  

#### Hızlı özet (tek bakışta) ⚡
- 📝 **Metin Notu:** Konu + içerik (çok satırlı), sonradan düzenle/kaydet.  
- ✅ **Checklist:** Başlık + madde ekle/çıkar, yapılanları işaretle, düzenle.  
- 🗂️ **Kategoriler:** Kategori ekle/sil, seçince liste filtrelenir.  
- 🔎 **Arama:** Yazdıkça filtre (title + content + checklist item text).  
- 🗑️ **Çöp Kutusu:** Soft delete + geri yükleme; kalıcı silmede “geri alınamaz” netliği.  
- 📦 **Dışa Aktar:** Seçilen notları kullanıcı seçtiği klasöre **.txt** olarak yaz.  
- ☁️ **Drive Yedekleme:** Seçerek yedekle (minimum çalışır entegrasyon; restore ayrı adım).  

#### Bilerek “ne yapmadım?” (ne değildir) 🚫
Sosyal ağ değil, hesap/abonelik curcunası hiç değil. **Notun özü var, gürültü yok.**  
Ağır animasyonlar, şişirme efektler yok. “Premium” hissi benim için: **sadelik + clean design + tutarlılık + hız**. 🧊⚡  

### 2) Mimari ve yaklaşım 🧅🏛️
Uygulamanın omurgasını **Clean / Onion yaklaşımı + MVVM** ile kurdum.  
En içte **iş kuralları**, dışarıda **UI/Room/Drive** gibi detaylar… yani tek bir teknolojiye evlenmeden yürüyorum. Çünkü teknoloji değişir; **iş kuralı kalır**. 😌🧱  

**Presentation (UI): Activity + Adapter + ViewModel**  
Ekranlar sadece **UI’ı yönetir**; veri işini ViewModel ve alt katmanlar taşır. UI tarafı “gösterir”, “tıklandı” der, biter. 🖥️✅  

**Domain (UseCase): “Ne yapıyoruz?” sorusunun cevabı**  
AddNote, UpdateNote, SoftDeleteNote, RestoreNote, ListNotes, ListTrash…  
UI değişse bile aynı use-case çalışır; çünkü işin aklı **burada**. 🧠⚙️  

**Data (Repository): “Nasıl yapıyoruz?” katmanı**  
Room DAO’ları ile konuşur; gerekince farklı kaynaklara (Drive gibi) köprü olur. Kaynak değişir, sözleşme bozulmaz. 🔌  

**Infrastructure / Local: Room + DataStore + dosya export**  
Kalıcılık burada; UI’nin “nasıl saklıyoruz?” diye kafası şişmez. 💾📁  

#### Katmanlar + veri akışı (MVVM) 🔄
Ben Java uyumu ve sade kontrol için **LiveData** çizgisini tuttum:  
Room -> Repository -> UseCase -> ViewModel (LiveData) -> Activity/Adapter  
Bu akışta UI sadece **“gösterir ve niyet bildirir”**. Tek yönlü akış olunca debug da kolay, bakım da rahat. 🧭🔧  

**SOLID burada süs değil, refleks:**  
S — **Single Responsibility:** Activity ekrandır, Repository veridir, UseCase iştir. Herkes kendi işini yapar. 🎯  
O — **Open/Closed:** Yeni not tipi/ekran eklerim; mevcut akışı kırmam. Genişletirim, yıkmam. 🧱  
L — **Liskov:** Repository arayüzü değişmeden Room impl’i swap edilebilir. (Test/Mock yolu açık.) 🧪  
I — **Interface Segregation:** “Her şeyi yapan dev interface” yerine, ihtiyaca göre küçük arayüzler. 🧩  
D — **Dependency Inversion:** UI, somut veritabanına değil soyut repository sözleşmesine bakar. 🔌  

### 3) Özellikler, ekranlar ve teknolojiler 🚀
Ben bu projede “az ama sağlam” kafasındayım: **hızlı açılan, temiz görünen, veri kaybetmeyen** bir uygulama.  
Üç kelimeyle hedefim: **Hız + Düzen + Güven.** ⚔️🔥  

🧭 **Drawer Menü:** Tüm Notlar / Kategoriler / Çöp Kutusu / Dışa Aktar / Yedekleme / Ayarlar / Hakkımda  
➕✅ **FAB’ler:** Büyük “+” metin notu; mini “✓” checklist notu  
🗑️ **Silme Güvenliği:** Soft delete + geri yükleme + onay diyalogları  
🎨 **Tema:** Sistem / Açık / Koyu + 3 accent (Mint, Lavender, Ocean) — tatlı, clean, göz yormayan  
📄 **Export:** Seçilen notları klasöre **.txt** olarak yaz (checklist madde madde)  
☁️ **Drive Backup:** Seçerek yedekle, hata mesajları ve progress ile  

#### Ekranlar ve “bu ekranda ne yapıyorum?” 🧾
Aşağıdaki tabloyu, projeye giren biri 5 dakikada konuyu kavrasın diye yazdım:  

| Ekran / Activity | Ne yapar? | Not |
|---|---|---|
| SplashActivity ⏳ | Progress dolunca Main’e kontrollü geçer | ~3 sn premium açılış |
| MainActivity 📝 | Notları listeler, arar, seçim yapar, export başlatır | Toolbar search + RecyclerView |
| CreateNoteActivity ➕ | Metin notu veya checklist oluşturur | Kayıt sonrası finish() ile geri döner |
| TextNoteDetailActivity ✍️ | Metin notu görüntüle + düzenle + kaydet | updatedAt güncellenir |
| ChecklistDetailActivity ✅ | Checklist aç/düzenle, madde ekle-sil, done toggle | Position/sıralama korunur |
| TrashActivity 🗑️ | Silinenleri gösterir, geri yükler, kalıcı siler, çöpü boşaltır | İşlem öncesi onay |
| CategoryManagementActivity 🗂️ | Kategori ekle/sil | Silince bağlı notlar kategorisiz olur |
| SettingsActivity ⚙️ | Tema seçimi | Seçim kalıcı (DataStore) |
| AboutActivity 👤 | Hakkımda kartı + iletişim | Temiz placeholder görsel alanı |
| BackupActivity ☁️ | Google Sign-In + seçerek Drive’a yedekle | Restore sonraki adım |

#### Kullandığım teknolojiler (ve “neden”leri):  
Room (SQLite) 🗃️: Offline-first, hızlı sorgu, tip güvenli DAO.  
Repository + UseCase 🧠: Kodun niyeti net; test/evrim yolu açık.  
LiveData + ViewModel 👀: Ekran yaşam döngüsünde güvenli veri akışı.  
DataStore (Preferences, RxJava3) 💾: Tema gibi ayarları güvenli ve modern biçimde saklamak için.  
Material 3 🎨: Tutarlı, modern, “gereksiz şatafat olmadan premium” UI.  
Storage Access Framework 📁: Kullanıcının seçtiği klasöre export yapabilmek için (izin kaosu olmadan).  
Google Sign-In + Drive API (minimum) ☁️: Seçerek yedekleme; temiz hata mesajı ve progress ile.  

>Benim için bu proje; “not uygulaması”ndan çok, **disiplinli mimari + sade UI** birleşince neler çıkabildiğinin canlı kanıtı.  
Notlar senin, kontrol sende. Ben sadece yolu temizledim. 🛣️✨

---

#### MVVM 🔄🧠

MVVM (Model–View–ViewModel), UI (View) ile iş mantığı/veri (Model) arasına ViewModel koyarak bağımlılığı kıran bir sunum mimarisidir. ViewModel; ekranın durumunu ve aksiyonlarını yönetir, böylece UI tarafı “mantık çöplüğü”ne dönmeden test edilebilir ve sürdürülebilir kalır.

#### Clean Architecture 🧼🏛️

Clean Architecture, sistemi Entities → Use Cases → Interface Adapters → Frameworks & Drivers halkalarıyla kurgulayan ve bağımlılık yönünü dıştan içe kilitleyen bir mimari yaklaşımdır. Amaç; UI/DB/framework değişse bile use-case ve iş kurallarının bozulmadan kalması, yani kodun “çekirdeğinin” uzun ömürlü olmasıdır.

#### Onion Architecture 🧅🛡️

Onion Architecture, merkezi Domain olacak şekilde katmanları “soğan gibi” dizer ve bağımlılıkların içe doğru akmasını zorunlu kılar. Dış dünya (UI, DB, dosya sistemi, servisler) iç katmanlara hükmetmez; iç katmanlar arayüz/port tanımlar, dış katmanlar bu sözleşmelere uyar.

#### SOLID 🧱⚙️

SOLID, nesne yönelimli tasarımda kodu esnek, genişletilebilir ve kırılmaya dirençli kılmak için ortaya konmuş beş temel prensip setidir. Bu prensipler; modüller arası bağımlılıkları kontrol eder, değişikliklerin zincirleme hasar üretmesini azaltır ve “büyüdükçe çürüyen kod” riskini düşürür.

#### Repository Pattern 🗃️🔌

Repository Pattern, veri erişimini (DB/Network/File) uygulamanın geri kalanından soyutlayarak tek bir arayüz üzerinden yönetmeyi amaçlayan tasarım şablonudur. Böylece veri kaynağı değişse bile (SQLite → API gibi) üst katmanlar “veriyi nereden aldığını” bilmeden aynı sözleşmeyle çalışır.

#### Use Case Pattern 🎯⚔️

Use Case (Application Service) yaklaşımı, sistemin yaptığı işleri iş senaryoları halinde tek tek tanımlar ve her use-case’i “girdi → işlem → çıktı” çizgisinde izole eder. Bu, iş mantığının UI/DB gibi detaylara dağılmasını engeller ve uygulamanın gerçek değerini (karar mantığını) net bir yerde toplar.

#### LiveData 👀📡

LiveData, Android Jetpack’in lifecycle-aware observable veri tutucusudur; yani gözlemlenen veri değiştiğinde UI’yı güncellerken ekranın yaşam döngüsünü dikkate alır. Bu sayede “ekran kapalıyken güncelleme, sızıntı, çakışma” gibi problemler azaltılır ve durum yönetimi daha güvenli hale gelir.

#### DataStore 💾🧱

DataStore, Android’de anahtar-değer veya typed veri saklamayı asenkron, güvenli ve tutarlı şekilde yapan modern kalıcılık çözümüdür (Preferences/DataStore + Proto DataStore). SharedPreferences’ın senkron erişim ve tutarlılık problemlerine karşı daha sağlam bir temel sunar ve veri yazma/okuma süreçlerini daha güvenilir hale getirir.

#### Room (SQLite) 🗄️⚡

Room, SQLite üzerinde çalışan ORM/abstraction layer’dır; tip güvenli DAO’lar ve derleme zamanı doğrulamalarla veritabanı erişimini daha güvenli hale getirir. SQL gücünü korurken; entity, relation ve query yönetimini standartlaştırır, hataları daha erken yakalatır.

#### Storage Access Framework 📁🔐

Storage Access Framework (SAF), Android’in kullanıcı odaklı dosya erişim sistemidir; uygulamalara “ham dosya yolu” yerine kullanıcı seçimi + URI tabanlı erişim sağlar. Bu yaklaşım, gizlilik/izin modeline uyumlu çalışır ve farklı depolama sağlayıcılarıyla (dahili, SD, bulut) standart bir şekilde etkileşime imkan verir.

#### Material 3 🎨📐

Material 3, Google’ın modern arayüz tasarım sistemi olup bileşenler, tipografi, spacing ve renk kurallarıyla tutarlı ve erişilebilir UI üretmeyi hedefler. Temel amacı “güzel görünsün”den öte; ölçeklenebilir tasarım dili ve uyumlu component ekosistemiyle ürün tutarlılığını korumaktır.

#### Google Sign-In + Drive API ☁️🔑

Google Sign-In, kullanıcıyı Google hesabıyla güvenli şekilde kimliklendirip yetkilendirme akışını standartlaştıran oturum açma çözümüdür. Google Drive API ise uygulamanın Drive üzerinde dosya oluşturma/okuma/yönetme gibi işlemleri yetkili erişim ile yapmasını sağlayan programatik arayüzdür; yedekleme/senkron gibi senaryoların temelidir.

#### Onion Architecture ile Clean Architecture. Farkı Nedir?

Clean Architecture, sistemi “use-case merkezli” kurar: iş akışları çekirdektir, UI/DB sadece adaptördür. Onion Architecture ise “domain merkezli zırh” kurar: işin dili (domain) en içte kutsaldır, tüm dış dünya o çekirdeğe bağımlı ve tabi yaşar.

Clean Architecture literatürde çekirdeği Entities + Use Cases diye ikiye ayırıp özellikle Use Case katmanını (application business rules) ayrı ve belirgin bir halka olarak tarif eder. Yani merkez anlatımı “iş senaryoları” üzerinden yürür.

Onion Architecture anlatımı ise daha çok Domain modelini (kavramlar + kurallar) “tek kutsal merkez” gibi konumlar; application servisleri/use-case’ler bu merkezin etrafında bir halka olarak düşünülür. Yani merkez anlatımı “domain” üzerinden yürür.
