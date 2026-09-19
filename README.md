# Muhammet Emin Atasever

**Elektrik-Elektronik Mühendisliği Öğrencisi | Gömülü Sistemler**

Bursa Uludağ Üniversitesi Elektrik-Elektronik Mühendisliği 2. sınıf öğrencisiyim. STM32 (ARM Cortex-M) ekosisteminde C diliyle, çevre birimlerinin çalışma prensiplerini yazmaç düzeyinde anlayarak gömülü yazılım geliştiriyorum. Savunma sanayii ve otomotiv sektörlerinde görev kritik gömülü sistemler üzerine çalışmayı hedefliyorum.

---

## Nasıl Çalışırım

* **Donanıma yakın çalışırım.** HAL ile hızlı prototipleme yapabiliyor; ancak kullandığım çevre birimlerinin çalışma mantığını anlamak için LL ve doğrudan yazmaç erişimiyle de çalışıyorum.
* **Kesme tabanlı ve bloklamayan tasarımları tercih ederim.** Veri akışını kesmeler ve hata callback'leri üzerinden yönetiyor; hat gürültüsü ve taşma gibi durumlarda sistemin kilitlenmesini önlemeye dikkat ediyorum.
* **Fail-safe yaklaşımını benimserim.** Eksik veya hatalı veri geldiğinde sistemin güvenli bir duruma geçmesini tasarım aşamasında ele alıyorum.
* **Donanım tarafını da dikkate alırım.** Yazdığım yazılımın üzerinde çalıştığı fiziksel katmana; sinyal seviyeleri, gürültü ve haberleşme hattı yapısı gibi unsurlara hâkim olmaya çalışıyorum. Bu sayede hata ayıklama sırasında yazılım ve donanım kaynaklı sorunları birbirinden ayırabiliyorum.

---

## Teknik Yetkinlikler

### Diller ve Araçlar

![C](https://img.shields.io/badge/C-00599C?style=flat-square\&logo=c\&logoColor=white)
![STM32CubeIDE](https://img.shields.io/badge/STM32CubeIDE-03234B?style=flat-square\&logo=stmicroelectronics\&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square\&logo=github\&logoColor=white)

Gömülü C, pointer aritmetiği, bit düzeyinde işlemler ve bellek haritalama.

### Mikrodenetleyiciler

![STM32](https://img.shields.io/badge/STM32-03234B?style=flat-square\&logo=stmicroelectronics\&logoColor=white)
![ESP32](https://img.shields.io/badge/ESP32-E7352C?style=flat-square\&logo=espressif\&logoColor=white)
![Arduino](https://img.shields.io/badge/Arduino-00878F?style=flat-square\&logo=arduino\&logoColor=white)

| Aile     | Modeller       |
| -------- | -------------- |
| STM32 F0 | STM32F072RB    |
| STM32 F1 | STM32F103C8T6  |
| STM32 F4 | STM32F446RE    |
| Diğer    | ESP32, Arduino |

### Yazılım Katmanları

| Katman       | Kapsam                                                                                        |
| ------------ | --------------------------------------------------------------------------------------------- |
| **HAL**      | Kesme tabanlı UART, ADC, Timer/PWM, CAN ve güç modları                                        |
| **LL**       | Sistem saati yapılandırması (HSI48 ile 48 MHz), çevre birimi başlatma                         |
| **Register** | Doğrudan yazmaç erişimi (ör. `GPIOA->BSRR`), bit operasyonlarıyla deterministik GPIO kontrolü |

### Çevre Birimleri

Timer/PWM, 12-bit ADC, harici kesmeler, kesme tabanlı RX, Sleep modu ve kesme ile uyandırma.

### Haberleşme Protokolleri

| Protokol         | Kapsam                                                                     |
| ---------------- | -------------------------------------------------------------------------- |
| **UART / USART** | Master-Slave mimarisi, bloklamayan RX, hata bayrağı yönetimi (ORE, NE, FE) |
| **CAN-BUS**      | 11-bit ID, donanımsal maske filtresi, TJA1051 fiziksel katmanı             |
| **I2C / SPI**    | Teorik bilgi, devam eden uygulamalı çalışmalar                             |

---

## Seçili Gömülü Sistem Çalışmaları

**CAN-BUS Röle Kontrol Düğümü** — `STM32F103C8T6`

CAN üzerinden gelen tek bir mesajla dört yükü yöneten bir slave düğüm geliştirdim. Projede donanımsal maske filtresi, eksik veri durumunda mevcut durumu koruyan fail-safe veri ayrıştırma mekanizması ve Sleep modundan CAN kesmesiyle uyanma özelliklerini uyguladım.

**Master-Slave Servo Kontrolü ve Telemetri** — `STM32F446RE` + `STM32F072RB`

Analog veriyi 12-bit ADC ile okuyarak UART üzerinden ikinci mikrodenetleyiciye aktaran ve alıcı tarafta 50 Hz donanımsal PWM ile servo motoru kontrol eden gerçek zamanlı bir sistem geliştirdim. Kesme tabanlı veri alımı ve hata callback'leri kullanarak sistemin kararlı çalışmasını hedefledim.

**LL ve Register Düzeyinde Programlama** — `STM32F072RB`

HAL kullanmadan LL sürücüleri ve doğrudan yazmaç erişimiyle sistem saati ve GPIO yapılandırması gerçekleştirdim.

Araç elektroniği tarafında OTAGG bünyesinde TEKNOFEST Robotaksi aracının kablaj ekibine liderlik ediyor ve araç içi CAN-BUS tesisatının entegrasyon çalışmalarında görev alıyorum. Ekibimiz, ülke genelindeki 650'nin üzerinde takım arasından finale kaldı.

---

## Güncel Odak ve Hedefler

* **Şu an:** STM32 üzerinde LL ve register düzeyinde programlama, kesme tabanlı haberleşme mimarileri, I2C ve SPI uygulamaları.
* **Kısa vadeli hedef:** Savunma sanayii ve otomotiv sektörlerinde gömülü sistemler alanında 2. sınıf yaz stajı yapmak.
* **Uzun vadeli hedef:** Gömülü yazılım alanında uzmanlaşmak.

---

## Eğitim ve Sertifikalar

* **Bursa Uludağ Üniversitesi** — Elektrik ve Elektronik Mühendisliği (Lisans), 2025–2029 (Beklenen)
* **STM32 ile İleri Seviye Gömülü Yazılım Geliştirme** — BTK Akademi, Ağustos 2026
* **EF SET İngilizce Sertifikası** — B2 Upper Intermediate, Şubat 2026

---

## İletişim ve Bağlantılar

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge\&logo=linkedin\&logoColor=white)](https://www.linkedin.com/in/muhammeteminatasever)

[![Gmail](https://img.shields.io/badge/E--posta-D14836?style=for-the-badge\&logo=gmail\&logoColor=white)](mailto:muhammedeminatasever@gmail.com)

[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge\&logo=github\&logoColor=white)](https://github.com/muhammedeminatasever-hash)

**Konum:** Bursa, Türkiye
