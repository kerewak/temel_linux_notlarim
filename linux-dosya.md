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

