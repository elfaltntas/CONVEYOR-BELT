# Konveyör Sistemi

Bu proje, bir konveyör sisteminin çalışmasını simüle eden ve kontrol eden bir PLC (Programlanabilir Logic Controller) tabanlı sistemin yazılımını içerir. Sistem, motorun çalışmasını ve durmasını, yönünü ve hata durumlarını yönetir. HMI (Human-Machine Interface) kullanılarak görsel geri bildirim sağlanır ve kullanıcı etkileşimi gerçekleştirilir.

## Çalışma Prensibi

1. **Motor Durumu**: 
    - Termik röle açıldığında veya Stop butonuna basıldığında motor durur.
    - Kablo kırıkları veya termik röle kontaklarının bozulması durumunda da motor durur.

2. **İleri ve Geri Yön**:
    - İleri yön butonuna basıldığında motor ileri yönde çalışır.
    - Geri yön butonuna basıldığında motor geri yönde çalışır.
    - İleri yönde çalışırken geri, geri yönde çalışırken ileri yön çalışmaz.
    - Bant önce STOP ettirilip sonra istenen yöne çalıştırılacaktır.

3. **Işıklandırma**:
    - İleri yönde motor çalışırken yeşil, geri yönde çalışırken sarı lambalar yanar.

4. **Hata Durumu**:
    - Termik açtığında kırmızı bir sinyal lambası 1 Hz frekansla yanıp söner.
    - Korna da aynı frekansta çalar.
    - Korna, RESET butonuna basıldığında durur, arıza lambası ise ancak termik kurulduktan sonra resetlenebilir.

5. **Konveyör Animasyonları ve Veri Blokları**:
    - Konveyör üzerindeki kutular, integer veri türüyle saklanan bir data bloğuna bağlı olarak hareket eder.
    - Bu veri, konveyör animasyonlarını ve kutuların konumlarını belirler.
    - Verinin artma ve sıfırlanma algoritması, PLC'nin main blok kısmında tanımlıdır.

## HMI Detayları

- **Taglar ve Kontrol Süresi**:
    - Arıza ışıkları için ışıkların doğru gösterimi sağlanabilmesi amacıyla HMI taglarının kontrol süresi (Acquisition Cycle) 100ms olarak değiştirilmelidir. Bu ayar sayesinde ışıklar yanıp sönecektir.

- **Butonlar**:
    - Butonların `Press` (Basıldığında) tagı ve `Release` (Bırakıldığında) tagı düzgün şekilde ayarlanmalıdır.
    - Butonlar verimli çalışabilmesi için, M20.0 gibi hafıza tagları kullanılmalıdır. Dış kontaklar (örneğin, I0.1) ile verimli çalışma sağlanamaz.

- **Motor Çalışma Kontağı**:
    - Konveyörün doğru çalışması için, konveyör veri bloğunun önünde motor çalışma açık kontağı yer alır. Bu sayede motor çalışmadığı sürece konveyörde herhangi bir işlem yapılmaz.

## İşleyiş

- **Başlangıç ve Yön Seçimi**:
    - Start/Stop düğmesine basmadan önce, ileri veya geri butonları çalışmaz.
    - İlk olarak ON/OFF düğmesine basıldıktan sonra, ileri butonuna basıldığında konveyör ileri yönde hareket etmeye başlar.
    - ON/OFF düğmesine basıldıktan sonra geri butonuna basıldığında ürün, kaldığı yerden geri yönde hareket eder.

- **Hata Durumu ve Reset**:
    - Termik bozulduğunda, arıza lambası yanar ve korna çalmaya başlar.
    - RESET butonuna basıldığında, korna susar ancak arıza lambası yanıp sönmeye devam eder.
    - Termik kurulduğunda hem korna hem de arıza lambası durur, sistem tekrar çalıştırılabilir.

## Yapı

- **PLC Data Blokları**:
    - Konveyör animasyonları için kullanılan veri bloğunun veri türü `integer` olarak ayarlanmıştır. Bu veri 0 ile 100 arasında değerler tutar.
    - Verinin hangi değerlerde artacağı ve hangi değerlere ulaştığında sıfırlanacağı algoritmalarla belirlenmiştir.

- **HMI Objeleri**:
    - Konveyör üzerindeki kutular basit objelerle oluşturulmuştur.
    - HMI ekranında, birçok obje PLC’nin default taglarıyla bağlanır.
    - Butonlar için `Press` ve `Release` tagları uygun şekilde ayarlanmalıdır.

## Kurulum ve Kullanım

1. **PLC Programı**:
    - PLC'ye programı yükleyin ve bağlantıları doğru şekilde kurun.
  
2. **HMI Yapılandırması**:
    - HMI taglarını PLC'nin default tag kısmından ekleyin ve objeleri uygun şekilde konfigüre edin.

3. **Sistemi Çalıştırma**:
    - ON/OFF düğmesine basarak sistemi başlatın.
    - Yön butonlarıyla motorun ileri ya da geri yönde çalışmasını sağlayın.
    - Arıza durumlarında RESET butonuna basarak korna ve arıza lambasını durdurun.

## Lisans

Bu yazılım, [Lisans Adı] altında lisanslanmıştır. Kullanım koşulları için lütfen [lisans linki]yi inceleyin.

---

*Bu doküman, sistemin çalışma prensiplerini ve yazılımın doğru şekilde yapılandırılmasını amaçlamaktadır. Detaylı teknik bilgiler ve talimatlar için ilgili teknik dökümantasyona başvurabilirsiniz.*



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
