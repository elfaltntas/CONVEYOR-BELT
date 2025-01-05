# Çalışma Prensibi:
1- Termik açtığında ya da Stop butonuna basıldığında motor duracak. Aynı zamanda, kablo kırıkları ve stop butonu ile termik röle kontaklarının bozulması durumunda da motor duracaktır.<br/>
2-İleri yön butonuna basıldığında motor ileri yönde, geri yön butonuna basıldığı anda ise motor geri yönde çalışacaktır. İleri yöne çalışırken geri, geri yöne çalışırken ileri yönde çalışmayacaktır. Bant önce STOP ettirilip ondan sonra iste nen yöne çalıştırılacaktır.<br/>
3-Motorun ileri yönde çalışması yeşil, geri yönde çalışması ise sarı lamba ile gösterilecektir.<br/>
4- Termik açtığı durumlarda kırmızı bir sinyal lambası 1 Hz frekansla yanıp sünmeli, yine ayrı şekilde bir korna da aynı frekansta uyarmalıdır. Korna RESET butonu ile durdurulurken, arıza lambası ancak termik kurulduktan sonra resetlenmelidir.<br/><br/>
Konveyör animasyonları için data blok kullanılmıştır ve veri türü integer olarak ayarlanmıştır, bu data bloğun 0 ile 100 arasında bir veri tutması istenmiştir. Tuttuğu bu veriye göre konveyör üzerindeki kutunun konu belirlenecektir. Main blokta tutulacak bu veri için algoritma üretilmiştir. Bu algoritmada verinin ne zaman ne şekilde artacağı ve hangi değerlere ulaştığında sıfırlanacağını belirlenmiştir.

## Ayrıntılar:<br/> <br/>
•	Işıklandırmada özelikle arıza ışıklarının daha doğru gösterim yapabilmesi için HMI tags kısmında ışıklara bağladığımız tagların kontrol süresini (Acquisition Cycle) kısmını 100ms olarak değiştiriniz bu sayede arıza ışıkları yanıp sönecektir.<br/>
•	Kutu olarak basice objectslerden kare kutu kullanılmıştır.<br/>
•	HMI ekranda bir çok obje taglara bağlı olarak çalışmaktadır.<br/>
•	HMI ekrana taglar PLC nin default tag kısmından eklenir.<br/>
•	Butonların Press (Basıldığında) tagı set Release (Basılma bırakıldığında) tagı reset edecek şekilde ayarlanmıştır. Bu sayede simülasyondaki gibi bir çalışma mantığı oluşmaktadır. Taga basıldığında True bırakıldığında False olmasını sağlamış oluruz.<br/>
•	Butonların verimli çalışabilmesi için iç kontaklarda çalışılması gerekmektedir. I0.1 gibi dış kontaklarda çalışıldığında butonlar verimli çalışmayacaktır. M20.0 gibi tagları hafızaları kullanınız.<br/>
•	Konveyörün verimli ve doğru çalışması için konveyör data blogunun önüne motor çalışma açık kontağı konmuştur bu sayede motor çalışmadıkça konveyörde herhangi bir durum olmayacaktır <br/>



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
