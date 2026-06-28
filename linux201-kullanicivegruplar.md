---Kullanıcı ve Grupler---


Kullanıcı nedir?

Sistem kaynaklarına, içinde bulunan dosyalara ve uygulamalara erişebilmek için kullanıcıların giriş yapması (login) gerekmekte.
Linux, çok kullanıcılı bir sistemdir.

Birçok program, sunucu yazılımı, komut; çok kullanıcılı sistem üzerinde çalışır.
Modern dağıtımlarda birden fazla kullanıcı hazır gelir.

normal, normal, root

root kullanıcısı

Tüm yetkilere ve erişimlere sahiptir.
Sistem seviyesinde yetkiler için kullanılır. (Genel amaçlı kullanılması pek tavsiye edilmez, yeni kullanıcı oluşturma, sisteme yeni program, paket yükleme işlerinde kullanılır.)
Ev dizinleri /root dizinidir.

Genel amaçlı kullanıcılar

Kendilerine veya gruplarına tanımlı yetkileri kullanırlar
Ev dizineri /home dizini altında bulunur.

--Grup Nedir?--

Birden fazla kullanıcının bir arada bulunduğu erişim gruplarıdır.

GID = Grup ID

Bir kullanıcı birfen fazla gruba üye olabilir.

Grup üyelikleri /etc/group altına tanımlanır.


-Kullanıcıları Görüntüleme--

cat /etc/passwd
bu dosyanın içerisinde bütün kullanıcıların listesi bulunuyor. Ve bu dosyayı bütün kullanıcılar okuyabiliyor.

ilk sütun kullanıcı adı, ikinci sütun eskiden parola hash lerin tutulduğu sütun -yaklaşık 1980'lerin ortasına doğru parolahler artık passwd dosyasının altında 
tutulmamaya başlandı- üçüncü sütun kullanıcı ID, dördüncü sütun grup ID, beşinci sütun kullanıcının tam ismi, altıncı sütun kullanıcının home dizini yer alır.

Root kullanıcısının home dizini kök dizinin altındaki root klasörüdür bu istisnai bir durumdur. Normal bir kullanıcının home dizini kök dizininin altındaki home klasörünün
içinde kendi kullanıcı ismiyle tutulur.

Son sütunda ise kullanıcının kabuk erişimi yer alır.

Bu dosyanın bu kadar kalabalık olmasının nedeni bunların gerçek kullanıcı olmaması. Bunlar sistemimizde tanımlı olan uygulamaların sadece kendi yetkisi olan dosya ve uygulamalara
erişmeleri için oluşturulmuş sanal kullanıcılar, bunların kabuk erişimine bakılırsa login erişimi yoktur.


cat /etc/shadow
Erişemiyoruz çünkü kullanıcı parolaları yer almakta, ancak root yetkisi erişimleriyle gerektiği zaman erişilebilir.

sudo cat /etc/shadow
burada yazan parolamız bir özettir. Parolamız bir algoritmadan geçirilerek geri döndürülemez bir şekilde başka bir metne dönüştürülüyor. Bundan parolayı elde etmek çok zordur.
Parola hash'i $ karakteriyle birbirinden ayrılmıştır. İlk iki dolar arası kısım hangi algoritmanın kullanılarak hashlendiğini ifade eder. İkinci kısım parolaya eklenen bir kelimeyi ifade eder
amacı parolayı geri döndürülmesini zorlaştırmaktır (Hashing ve tuzlama methodu). Sonraki kısım ise parolamızın hashidir. Sonraki sütun parolamızın hangi gün değiştiğini ifade eder. 
Sonraki sütunlar parolanın süresini, ne kadar zaman sonra değiştirilmesi gerektiğini ve değiştirilmeden önceki uyarı gününü ifade eder. Sonraki sütunlar başka amaçlar için rezerve edilmiştir
ve kullanılmamaktadır.


root kullanıcısında parola bölümünde hash bulunmuyor ! karakteri bulunuyor. ! karakteri bu kullanıcıya parolayla giriş yapılmanın mümkün olmadığını ifade eder.


--Kullanıcı Ekleme--
Kullanıcı eklemek için kullanabileceğimiz iki yöntem var.
Kullanıcı işlemleri için root haklarına sahip olmalıyız. (sudo)

sudo useradd franz

sudo passwd franz

sudo adduser 
oluştururken bilgi verir, kişisel bilgi sorar.


--Kullanıcı Silme--

sudo deluser sokrates

sudo userdel franz


--Grupları Listeleme ve Ekleme--

cat /etc/group
Bu komut ile sistemde tanımlı olan bütün grupları, isimleri ve ID'leriyle beraber görebiliyoruz.
İlk sütun grup ismi, sonraki sütun eskiden yer alan grup parolası, sonraki sütun grup ID, sonraki sütun virgülle birlikte ayrılmış olan kullanıcılar listeleniyor.
Bu liste içinde herhangi bir kullanıcı listelenmemiş olanlar, burada sadece ikincil gruptakiler olduğu için. Passwd dosyasında birinciller gözükür.
(/etc/passwd dizininde 4.sütun, kullanıcıların grup ID'lerini temsil eder.)

Yeni bir grup eklemek için yönetici izinlerine ihtiyacımız var.

sudo addgroup linuxsevenler



--Grup Silme--

sudo delgroup aile



--Kullanıcı Gruplarını Yönetme--

sudo aslında yönetici haklarıyla çalışmamızı sağlayan bir programdır.

sudo usermod -a -G linuxsevenler ahmet
-a (add), -G (grup) anlamına gelir.
Bu sayede ahmet kullanıcısı linuxsevenler grubuna dahil olmuş oldu.

sudo usermod -a -G linuxsevenler yusuf
Aynı şekilde yusuf kullanıcısını da linuxsevenler grubuna dahil ettik.


