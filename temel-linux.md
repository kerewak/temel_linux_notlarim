En çok bilinen ve kullanılan açık kaynak kodlu işletim sistemi olan Linux’u ve işletim sistemlerinin en temel parçası olan çekirdek yazılımının detaylarını öğreneceğiz.

Linux, işletim sistemi çekirdek yazılımıdır.
Özgür yazılım projesidir.
GNU/Linux işletim sistemi dağıtımlarının temelini oluşturur.

GNU, 1984 yılında kullanıcı arabirimlerinin tasarlandığı bir projedir. Yani kişisel bilgisayarlarda kullanılacak yazılımların
geliştirildiği bir tasarıdır.

Lİnux, 1991 yılında geliştirilmeye başlanmış işletim sistemi çekirdeğidir.

GNU ve Linux birbirini tamamlayan temel yapılardır.
1993 İlk GNU/Linux ddağıtımları Debian.


Linux, işletim sisteminin çekirdeğini oluştururken, GNU Kullanıcı yazılımlarını oluşturuyor. Keskin ayrılmış değil ancak.
Dağıtım ise çekirdeği olan bir işletim sisteminin üzerinde kullanıcı yazılımları yüklü olan ve ek paketlerin de yüklü geldiği bir işletim sistemi dağıtımını temsil eder.


Sanallaştırma Teknolojisi

Bilgisayarımızın kaynakları, depolama, işlemci, ağ kartımız, görüntü işlemci, geçici bellek(RAM)

Bilgisayarımız içinde oluşturduğumuz sanal bilgisayarlara bu kaynakları paylaştırabiliyoruz.

Web sunucuları, depolama sistemleri, kurumsal IT sistemleri, veri işleme gibi departmanlarda sıkça kullanılan bir teknolojidir.

Virtualbox'ta iki yoldan ubuntu kurabiliriz.
Doğrudan yükleme ve içe aktarma.
.ova file


Terminal ortamı

Terminal, kabuk (shell) ile etkileşime geçmek için kullandığımız grafik arabirimdir.

Kabuk (shell) kullanarak komut ve programları çalıştırırız.
Terminal ekranı, çalışan komutların çıktılarını görmemizi sağlar.

kullanici@makineismi:~$

~: Kullanıcı ana dizini
$: Normal kullanıcı haklarıyla işlem.

whoami
>kullanici

uname -a
>Sistem özelliklerini ayrıntılı bir şekilde basan bir komut.

ping -c4 ubuntu.com
>ubunu.com adresine gönderdiği pinglerin sonucu

Ctrl+Alt+T ile terminali açabiliriz.

ls
>bulunduğumuz klasörün içindeki dosya ve klasörler listelenir.

ls -a
>gizli dosya ve klasörlerin de listelenmesini sağlar.

dosya ve klasörlerin başındaki nokta onların gizli olduğu anlamına gelir

Komutun sonuna çeşitli parametreler ekleyebiliyoruz.

ls -l
>dosyaları dizin içerisinde listeli bir vaziyette göstermeyi sağlar.

pwd komutu, içinde bulunulan dizini gösterir.

kerem@kerem:~$ pwd
>/home/kerem
kök klasörü içerisindeki home dizinin altındaki kerem klasörünün içerisindeyiz.

cd (change directory)
komutu, herhangi bir dizinin içine gidebilmek için kullanılır.

cd .. 
>bir üst dizine gitmemizi sağlar.







