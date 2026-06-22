  Yetkiler ve Sahiplikler

Her dosya, dizin ve uygulamanın sahibi olan bir kullanıcı ve bir grup buunmaktadır.
Erişirken hangi kullanıcı veya hangi grupla erişiyorsak o kullanıcı ve gruba tanımlanan izinler kapsamında erişebilir veya erişemeyiz.

terminalde herhangi bir dizinde ls -al dediğimizde 3.sütun bize sahip kullanıcıyı göstermektedir.
4.sütun'da sahip grubun ismini görüyoruz.

Bir dosyanın sahipliği neden bu kadar önemli? 
BUnun sebebi sahip olan kullanıcıya ve gruba ve bunun dışında kalan kullanıcılara belirli yetkiler tanımlanmış olması.

1.sütunda bu yetkileri görüntüleyebiliyoruz.

Okuma (Read) r
Yazma (Write) w 
Çalıştırma (eXecute) x

ilk 3 izin kullanıcının sahip olduğu yetkiler
sonraki 3 izin grubun sahip olduğu yetkiler
en sondaki 3 izin herkesin (public) sahip olduğu yetkiler.



--Root Yetkileri ile Çalışma--

root, TÜm erişim izinlerine sahiptir. Dosyaları okuyabilir, değiştirebilir, çalıştırabilir. Tüm izinlerini değiştirebilir.
Tüm sahiplikleri değiştirebilir.

root kullanıcısının yetkilerini kullanabilmek için yönetici grubuna eklenmiş bir kullanıcı isek sudo komutunu kullanıyorduk, yani kullanacağımız komutların
başına sudo yazıyorduk.



--Dosya ve Dizinlerin Sahibini Görüntüleme--

ls -al komutunun kısa hali ll idir.


--Dosya ve Dizinlerin Sahibini Değiştirme--

chown (change owner)

sudo chown ahmet dersprogrami.txt


chgrp (change group)

sudo chgrp ogretmenler dersprogrami.txt



--Toplu Sahiplik Değişiklikleri--

sudo chown yusuf arsiv1.tar arsiv2.tar eskiprogram.txt

sudo chgrp ogretmenler fizik.tar 'ogrenci kartı.png'


bir dizinin sahipliğini, grubunu değiştirdiğimiz zaman o dizinin altındaki dosya ve dizinlerinki değişmiyor.

-R (recursive), bir dizinin sahipliğini değiştirirken içinde bulunan dosyaların ve dizinlerin de sahipliklerini değiştirmemize yarar.
sudo chown -R yusuf fizik

sudo chgrp -R yusuf fizik
her kullanıcının kendi isminde bir grubu oluşur.

bir dizinin içindeki tüm dosyaların sahipliğini ve grubunu değiştirmek için * (hepsi) argümanını kullanabiliriz.

sudo chown -R kerem:ogrenciler *












