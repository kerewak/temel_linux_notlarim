Dosya, Hiyerarşi, Kök Dizin, Dizin Yapısı

Linux'ta her şey bir dosyadır.

Dosyalar (-)
Dizinler (d) Directory
Bağlantılar (l) Link

Linux'ta dosya sistemi hiyerarşiktir.


/ Kök dizin

Kök dizin, tüm dizinleri içerir.
Hiyerarşinin başladığı yerdir.


Kök dizinin altında bulunan dizinler

/bin : Temel kullanıcı komutları
/boot : Açılıştaki statik dosyalar
/dev (device) : Cihaz dosyaları
/etc : Sisteme özel ayarlar
/home : Kullanıcı ana dizinleri
/lib : Temel kütüphaneler ve çekirdek modülleri
/media : Çıkarılabilir ortam dosyaları
/mnt : Yerleştirilen dosya ortam dosyaları (Harici harddisk)
/srv : Servis dosyaları
/tmp : Geçici dosyalar
/var : Çeşitli dosyalar (Örneğin log dosyaları)
/root : Root kullanıcısı için ana dizin


Dosya Sisteminde Gezinme ve Listeleme

Normalde dosya sisteminde gezerken normal bir dosya yöneticisi veya Grafik Arabirim kullanırız.

ls

ls -a 
gizli dosya ve klasörleri de listeleyebiliyoruz.

Kök dizinindeyken cd .. komutu ile bir üst dizine çıkamayız çünkü kök dizin hiyerarşinin en üstündedir.

cd -
komutunu kullanarak bir önceki bulunduğumuz dizine gidebiliriz.

mkdir matematik
bu komutla bulunduğumuz dizin içerisine bir dizin oluşturabiliriz.

touch odevim.txt
isim ve uzantısıyla beraber dosya oluşturabiliriz.

touch ve mkdir komutlarını kullanarak birden fazla dosya veya dizin oluşturabiliyoruz, aralarında boşluk bırakarak.

rm odevim.txt
bu komut ile dosyaları silebiliriz.
Linux'ta komut satırı ile çalışırken sildiğimiz dosyaları kurtarabileceğimiz geri dönüşüm kutusu bulunmuyor.

rm -r hafta1
-r parametresi rekursif bir şekilde dizinin içerisindeki dosya ve klasörleri silecektir. Birden fazla dizinleri de bu komutla silebiliriz.


Dosya ve Dizinleri Kopyalama

cp dersprogrami.xls yeniprogram.xls

cp yeniprogram.xls matematik/

cp yeniprogram.xls ../
bir üst dizine kopyaladık.

cp /home/kerem/odevler/yeniprogram.xls /tmp/eskiprogram.xls

cp -r matematik/ dersler/
bir dizini kopyalamak için bunu -r parametresi ile rekursif bir şekilde yapmalıyız.

Dosya ve Dizinleri Taşıma

mv tasınacak_dosya tasınacak_yer

mv 'mat soruları.docx' matematik/

mv komudu ile birden fazla dosyayı bir dizinin altına taşıyabiliriz.

ls -al matematik/ 
komudu ile odevler dizinindeyken o dizinin içerisindeki matematik dizininin içerisini listelemiş olduk.

mv matematik/ dersler/
komudu ile matematik dizinini dersler dizinine taşımış olduk.



Dosya ve Dizinleri Yeniden Adlandırma

mv ogrenci-belgesi.pdf mezun-belgesi.pdf

mv fizik-kitap.pdf fizik/kitap.pdf

dizin ismi değiştirme:
mv dersler/ tumdersler/


Dosya ve Dizinleri Arşivleme-Çıkarma

Arşiv dediğimiz şey, dosyaları ve dizinleri tek bir dosya halinde sıkıştırılmış bir vaziyette bir dosyanın içinde tutma işlemidir.
rar, zip, tar, 7z, bu arşiv uzantıları tanıdık gelecektir.

tar -zcvf arsiv1.tar dersprogrami.xls 

tar -zcvf arsiv2.tar mezun-belgesi.pdf yeniprogram.xls
arşivleme işlemi sırasında eski dosyalar kaybolmaz veya silinmez, yeni oluşan arşiv dosyasının içerisine kopyalanır.

Bir dizini arşivlemek

tar -zcvf fizik.tar fizik/


Arşivi çıkarmak

tar -zxvf arsiv1.tar


Nano, terminal üzerinde çalışan bir text editor. Bir metin düzenleyicisi ile dosyanın içerisine herhangi bir metin yazabilir, o metini düzenleyebilir ve kaydetmek istediğimiz şekilde kaydedebiliriz.

nano dosya.txt
yazdıktan sonra ctrl + X ile kaydedebiliriz.

cat dosya.txt
dosyayı okumak için cat komutunu kullanıyoruz

dosyayı nano ile tekrar düzenleyip ctrl + O yaparak dosyayı farklı bir isimde kaydedebiliriz.

Nano ile çok daha büyük dosyalar, log dosyaları, sistem dosyaları veya belgelerde işimize yarayacak bir özellik dosya içerisinde arama.
ctrl + W ile arama yapabiliriz.


Diğer metin düzenleyiciler

vim ve GUI olan gedit uygulaması, bunların yanı sıra bir çok metin editörü yüklenip kullanılabilir.
vim, linux üzeirnde uygulama geliştiren veya sistem yöneticileri tarafından çok sıkca kullanılır.
vim'de bir kod dosyası açıyorsak vim o dosyayı çalıştırabilme imkanı sağlar, kodun içeriğini syntaxına göre renklendirebilir ve çeşitli komutları beraberinde getirir.
vim'de yazı yazarken aynı zamanda komut çalıştırabiliriz.
vi dosya.txt

: ile komut satırı moduna geçer.
vim'den çıkmak için :qa yazıp çıkarız.

gedit

gedit dosya.txt



Dosyaları Okuma

cat (concatenate) ile birden fazla dosyayı aynanda okuyabiliriz.

cat dosya.txt kelimeler.txt


cat -n 1a-liste.txt
satır sayılarını görüntülemek için -n parametresini kullanırız.

cat -E 1a-liste.txt
satır sonlarını işaretleme parametresi, dolar işaretiyle satır sonlarını işaretler.


tac 1a-liste.txt
tac komutu, cat'in tersten yazılmış halidir, bir listenin satırlarını sondan başa doğru göstermemizi sağlar.


head tumliste.txt
head komutu, bir dosyanın ilk satırlarını ekrana yazdırır.
ilk on satırını okur.

head -n5 tumliste.txt
baştan kaç satır okunacağını belirleyebiliriz,

tail tumliste.txt
tail komutu, bir dosyanın son satırlarını ekrana yazdırır.
son on satırını okur.

tail -n2 tumliste.txt
sondan kaç satır okunacağını belirleyebiliriz.

//-n parametresindeki n number manasına gelir.


tail komutu dosyaları canlı olarak izleyebilir.
tail -f tumliste.txt

yeni bir terminal açıp aynı dizine gidelim,
echo "klara" >> tumliste.txt
dosyanın sonuna eklediğimiz bu yeni satır anlık olarak okunur ve dosyanın sonuna listelenir. Özellikle log dosyalarının yani sistem kayıtlarını okurken
tail -f parametresi çokça işimize yarar.


more istiklalmarsi.txt
more komutu, terminal ekranına sığmayan metinleri okumayı kolaylaştırır. Enter tuşuna basarak metni aşağıya doğru okuyabiliriz.
Çıkmak için Q tuşuna basarız.


nl istiklalmarsi.txt
nl komutu, boş olan satırlar hariç diğer satırlara satır numarası ekler.



Dosyalar Hakkında Bilgi Alma

Dosyaları açmadan o dosyalar hakkında bilgi toplayabiliriz.

file istiklalmarsi.txt

ls -la komutu ile ll komutu benzerdir.


wc (word count) bize dosya hakkında belirli bilgiler verir. İlk sayı satır sayısı,
ikincisi kelime sayısı, üçüncüsü byte cinsinden boyutunu verir.

wc -w tumliste.txt
-w parametresi ile sadece kelime sayısını verir.

wc -l tumliste.txt
-l parametresi ile sadece satır sayısını verir.

wc -c tumliste.txt
-c parametresi ile sadece byte sayısını verir.

wc -L tumliste.txt
en uzun satırın boyutunu verir.


--Dosyaları Sıralama--

sort komutu, dosyaları sıralamamızı sağlar.
sort 1a-liste.txt

sıralama işlemi yaparken neye göre sıralayacağımızı belirleyebiliriz.

sort -k 2 tumliste.txt
-k (key) parametresi, dosyaları belirttiğimiz sütundan sıralamamızı sağlar.

sort -c tumliste.txt
-c parametresi, bir listenin sıralı olup olmadığını öğrenmemizi sağlar.
Sırayı bozan satırı kontrol ederiz.

sort -r tumliste.txt
-r parametresi ile listeyi tersten sıralamamızı sağlar.


sort -r k2 tumliste.txt
ile hem isme göre hem de tersten sıralamış olduk.

sort -rk2 tumliste.txt -o sirali.txt
-o parametresi bir listenin sıralamasını kaydetmemizi sağlar.


listeyi karıştırıp görmek istiyorsak:
sort -R sirali.txt
-R (Random) parametresi


--Dosya İçinde Arama--

grep 'a' tumliste.txt
grep komutu, dosya içerisinde arama yapmamızı sağlar.

grep -v 'a' tumliste.txt
-v parametresi ile aradığımız ifadenin bulunmadığı satırları görürüz.

grep -i 'a' tumliste.txt
-i parametresini, büyük-küçük harf duyarlılığını ortadan kaldırmak için kullanırız.


grep -i 'e' tumliste.txt 1a-liste.txt 2a-liste.txt sirali.txt
grep ile birçok dosya içerisinde de arama yapabiliriz.


grep -i 'a' -l tumliste.txt 1a-liste.txt
-l parametresi, aradığımız kelimenin yazdığımız hangi dosyalarda bulunup bulunmadığını gösterir.

grep -i 'vatan' -c istiklalmarsi.txt
-c parametresi ile verdiğimiz kelimenin dosyada kaç kez geçtiğini gösterir.




