Genel Bakış

Bu belge, bir konveyör sisteminin çalışma prensiplerini ve kurulum gereksinimlerini açıklamaktadır. Sistem, arıza durumlarında net görsel ve işitsel geri bildirimlerle güvenli ve verimli bir çalışma sağlar.

Çalışma Prensipleri

1. Motor Çalışması ve Güvenlik

Durdurma Koşulları: Motor aşağıdaki durumlarda durur:

Termik röle tetiklendiğinde.

Stop butonuna basıldığında.

Kablo kopmaları ya da stop butonu veya termik röle kontaklarında arıza meydana geldiğinde.

2. Yön Kontrolü

İleri Yön: İleri butonuna basıldığında motor ileri yönde çalışır.

Geri Yön: Geri butonuna basıldığında motor geri yönde çalışır.

Yön Kilidi: Yön değişikliği yapmadan önce sistem durdurulmalıdır. Konveyör durdurulmadan yön değişikliği yapılamaz.

3. Görsel Göstergeler

Yeşil lamba: Motorun ileri yönde çalıştığını gösterir.

Sarı lamba: Motorun geri yönde çalıştığını gösterir.

Kırmızı yanıp sönen lamba (1 Hz): Termik röle arızasını gösterir.

4. Sesli Uyarılar

Termik röle arızası durumunda bir korna 1 Hz frekansla öter.

Reset butonu kullanılarak korna susturulabilir, ancak kırmızı lamba termik röle resetlenene kadar yanıp sönümeye devam eder.

5. Konveyör Pozisyon Verisi

Konveyör pozisyonu bir veri bloğu ile yönetilir.

Veri bloğu türü integer olup 0 ile 100 arasında değer tutar.

Bu değerler, kutunun konveyör üzerindeki pozisyonunu belirler.

Uygulama Detayları

Pozisyon Verisi İçin Algoritma

Ana blokta pozisyon verisini kontrol eden algoritma bulunur.

Bu algoritma, verinin ne zaman artacağı ve ne zaman sıfırlanacağını belirler.

HMI Yapılandırması

Edinim Döngüsü: Arıza lambalarının doğru çalışması için 100ms olarak ayarlanır.

Taglar: HMI ekranındaki objeler PLC'nin varsayılan taglarına bağlıdır.

Buton Fonksiyonları:

Basıldığında: Tag True yapılır.

Bırakıldığında: Tag False yapılır.

Giriş ve Hafıza İşleyişi

Buton işlemleri için dış kontaklar (I0.1 gibi) yerine iç hafıza tagları (M20.0 gibi) kullanın.

Bu, sistemin daha verimli ve güvenilir çalışmasını sağlar.

Çalışma Akışı

Başlatma:

ON/OFF butonuna basarak sistemi aktif hale getirin.

İleri butonuna basarak kutuyu konveyör üzerinde ileri doğru hareket ettirin.

Alternatif olarak, Geri butonuna basarak kutuyu geri doğru hareket ettirin.

Arıza Durumları:

Termik röle tetiklendiğinde:

Kırmızı lamba yanıp söner ve korna öter.

Reset butonuna basarak korna susturulur.

Kırmızı lamba, termik röle resetlenene kadar yanmaya devam eder.

Arıza giderildikten sonra sistemi yeniden başlatın.

Sistemi Kapatma:

Stop butonuna basarak tüm işlemleri durdurun.

Notlar

Konveyör veri bloğu ile işlem yapmadan önce motorun çalışır durumda olduğundan emin olun.

Sistem güvenliğini ve verimliliğini sağlamak için iç hafıza kontakları kullanın.

Tüm arıza göstergelerinin ve alarmların doğru çalıştığından emin olmak için sistemi periyodik olarak test edin.

Bu prensiplere uyulduğunda, konveyör sistemi her şartta güvenli, verimli ve sorunsuz bir şekilde çalışacaktır.



![konveyor](https://github.com/elfaltntas/CONVEYOR-BELT/blob/main/images/Ekran%20g%C3%B6r%C3%BCnt%C3%BCs%C3%BC%202024-12-22%20130516.png)
![konveyor](https://github.com/elfaltntas/CONVEYOR-BELT/blob/main/images/Ekran%20g%C3%B6r%C3%BCnt%C3%BCs%C3%BC%202024-12-22%20130539.png)
![konveyor](https://github.com/elfaltntas/CONVEYOR-BELT/blob/main/images/Ekran%20g%C3%B6r%C3%BCnt%C3%BCs%C3%BC%202024-12-22%20130555.png)
![konveyor](https://github.com/elfaltntas/CONVEYOR-BELT/blob/main/images/Ekran%20g%C3%B6r%C3%BCnt%C3%BCs%C3%BC%202024-12-22%20130607.png)
![konveyor](https://github.com/elfaltntas/CONVEYOR-BELT/blob/main/images/Ekran%20g%C3%B6r%C3%BCnt%C3%BCs%C3%BC%202024-12-22%20130634.png)
![konveyor](https://github.com/elfaltntas/CONVEYOR-BELT/blob/main/images/Ekran%20g%C3%B6r%C3%BCnt%C3%BCs%C3%BC%202024-12-22%20130639.png)
![konveyor](https://github.com/elfaltntas/CONVEYOR-BELT/blob/main/images/Ekran%20g%C3%B6r%C3%BCnt%C3%BCs%C3%BC%202024-12-22%20130659.png)
![konveyor](https://github.com/elfaltntas/CONVEYOR-BELT/blob/main/images/Ekran%20g%C3%B6r%C3%BCnt%C3%BCs%C3%BC%202024-12-22%20130206.png)
![konveyor](https://github.com/elfaltntas/CONVEYOR-BELT/blob/main/images/Ekran%20g%C3%B6r%C3%BCnt%C3%BCs%C3%BC%202024-12-22%20130715.png)
![konveyor](https://github.com/elfaltntas/CONVEYOR-BELT/blob/main/images/Ekran%20g%C3%B6r%C3%BCnt%C3%BCs%C3%BC%202024-12-22%20130820.png)
![konveyor](https://github.com/elfaltntas/CONVEYOR-BELT/blob/main/images/Ekran%20g%C3%B6r%C3%BCnt%C3%BCs%C3%BC%202024-12-22%20140921.png)
Start-stop düğmesine basmadan ileri veya geri butonları çalışmayacaktır. İlk önce ON/OFF düğmesine basılıp daha sonra ileri düğmesine basıldığında ürün konveyör bantta ileri doğru gitmeye başlayacaktır.<br/>
ON/OFF düğmesine bastıktan sonra geri düğmesine bastığımızda ürün kaldığı yerden geriye doğru gitmeye başlayacaktır.<br/>
Termik bozulduğunda ise arıza lambası ve korna çalmaya başlayacaktır. <br/>
Reset düğmesine bastığımızda ise korna susacak ve arıza lambası yanıp sönmeye devam edecektir. <br/>
Termik düzeldiğinde hem korna hem arıza lambası duracaktır ve sistemi tekrardan çalıştırabileceğiz.
