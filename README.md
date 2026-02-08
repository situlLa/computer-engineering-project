### Sanal Makine (VirtualBox) ve Konteyner (Docker) Performans Karşılaştırması
Bu proje, İşletim Sistemleri dersi kapsamında; geleneksel sanal makineler ile modern konteyner teknolojilerinin performans verimliliğini niceliksel olarak analiz etmek amacıyla geliştirilmiştir. Proje, bizzat yürütülen benchmark testlerini ve literatür taramasını içeren teknik bir rapor ile sunum dosyasından oluşmaktadır.  
## Test Metodolojisi ve Ortamı
Testler, Ubuntu/CentOS tabanlı fiziksel bir sunucu üzerinde, VirtualBox (VM) ve Docker Engine (Konteyner) ortamları arasında adil bir karşılaştırma yapabilmek için benzer konfigürasyonlarla (4 CPU çekirdeği, 8 GB RAM) gerçekleştirilmiştir.  
Kullanılan Araçlar:
* CPU: sysbench, stress  
* Bellek (RAM): sysbench --test=memory, stress-ng  
* Disk I/O: dd, fio  
* Ağ: iperf3, ping  
* Başlatma Süresi: systemd-analyze, time, Measure-Command

###  Performans Karşılaştırma Sonuçları

Aşağıdaki tablo, VirtualBox VM ve Docker Konteyner ortamlarında gerçekleştirdiğim benchmark testlerinin özet sonuçlarını göstermektedir:

| Test Kategorisi | VirtualBox VM (Sanal Makine) | Docker Konteyner |
| :--- | :--- | :--- |
| *Başlatma Süresi* | Uzun (Tam OS önyüklemesi gerekli) | Çok Kısa (Instant başlatma) |
| *Disk (I/O) Performansı* | Orta / Düşük (I/O yavaşlayabilir) | Yüksek (Neredeyse native seviye) |
| *CPU Performansı* | Yakın (Bir miktar daha ağır) | Yakın (Yaklaşık native hız) |
| *Bellek (RAM) Performansı* | Yakın (Sabit rezervasyon yükü) | Yakın (Dinamik ve daha hafif) |
| *Ağ Performansı* | Orta (NAT/Köprüleme gecikmesi) | Orta / Yüksek (Düşük gecikme) |
