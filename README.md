# 🚀 Konveyör Kontrol Sistemi Projesi

*Konveyör Kontrol Sistemi* deposuna hoş geldiniz! Bu proje, PLC ve HMI teknolojileri kullanılarak güvenlik, kontrol ve izleme özelliklerini içeren bir konveyör bant sistemini göstermektedir.

---

## 📜 Proje Özeti
![konveyor](https://github.com/elfaltntas/CONVEYOR-BELT/blob/main/images/Ekran%20g%C3%B6r%C3%BCnt%C3%BCs%C3%BC%202024-12-22%20130555.png)
Bu proje şunları içermektedir:

1. *Güvenlik Mekanizmaları*:
   - Termik röle açıldığında, stop butonuna basıldığında veya kablolama/kontak sorunları olduğunda motor durur.
   - Arıza, 1 Hz frekansla yanıp sönen kırmızı bir lamba ve bir korna ile sinyallenir. Korna ayrı olarak susturulabilir.

2. *Yön Kontrolü*:
   - İleri Çalışma: İleri butonu ile aktif hale gelir ve yeşil bir ışıkla gösterilir.
   - Geri Çalışma: Geri butonu ile aktif hale gelir ve sarı bir ışıkla gösterilir.
   - Yön değişiklikleri, sistemin önce durdurulmasını gerektirir.

3. *HMI Entegrasyonu*:
   - Dinamik arıza ve durum göstergeleri için 100ms veri toplama döngüsü.
   - Veri bloklarına dayalı gerçek zamanlı nesne takibi.

4. *Veri Tabanlı Animasyon*:
   - Konveyör pozisyon kontrolü için tamsayı bazlı veri bloğu.
   - Değer ayarlamaları ve sıfırlama için özel algoritma.

---

## 🛠 Sistem Detayları

### Kontrol Özellikleri
- *Başlat/Durdur Mantığı*: İleri/Geri butonları yalnızca ON/OFF aktivasyonundan sonra çalışır.
- *Reset Fonksiyonu*: Korna durdurulabilir, ancak arıza göstergeleri termik röle sıfırlanana kadar devam eder.
- *Sorunsuz Operasyon*: Motor aktivasyonuna dayalı olarak konveyör nesneleri sorunsuz hareket eder.

### HMI Yapılandırması
- *Butonlar*: Basma/Bırakma eylemleri ile doğru/yanlış durumlarını değiştirir.
- *Taglar*: Tüm nesneler ve göstergeler, gerçek zamanlı etkileşim için tag bağlantılıdır.
- *Döngü Optimizasyonu*: Hafıza adresleri (M20.0 gibi) kullanılarak verimli performans sağlanır.

---

## 💡 Öne Çıkan Özellikler

- Hatasız görsel ve işitsel uyarılar ile hata tespiti.
- Güvenlik mantığı ile yön kontrolü.
- Animasyonlu konveyör nesne takibi.
- Kullanıcı dostu bir deneyim için HMI tabanlı izleme ve kontrol.

---

## 📂 Dosya Yapısı


/conveyor_project
├── PLC_Kodları
├── HMI_Konfigürasyonları
├── Dokümantasyon
└── README.md


---

## 📞 İletişim

Herhangi bir soru veya iş birliği için:

- 📧 elfaltntas123@gmail.com




