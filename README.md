# SicaklikKontrolUygulamasi

## MARMARA ÜNİVERSİTESİ TEKNOLOJİ FAKULTESİ Elektrik Elektronik Mühendisliği

## 170519022 Yağmur Ertoksöz Ölçme ve Enstrümantasyon Laboratuvar Projesi

### Kullanılan Malzemeler
- Arduino Nano
- LM35 Sıcaklık Sensörü
- LabVIEW Yazılımı
- Breadboard
- M-M Jumper Kablolar

### Projenin Amacı
Bu projede LM35 Sıcaklık Sensörü ve Arduino Nano kullanılarak Labview üzerinden veri okunması hedeflenmiştir.
Bu proje geliştirilerek yaz ayları için ortam sıcaklığının kontrol edilmesini sağlayabilir.
Özellikle dökümhanelerdeki ekstrem çalışma koşulları bu proje ile bir nebze gözlemlenerek gereken çözümler üretilebilir.

### Projenin Yöntemi
Sistem ve Kontrol Paneli ile ilgili detaylar aşağıdaki gibidir:
- Kontrol Panelini devreye geçirmek için öncelikle COM Port üzerinden COM3 seçeneğini seçiniz. Arduino Nano'ya ilgili kodun yüklendiğinden emin olunuz. Kontrol Panelinde ölçümü başlatmak ve durdurmak için bir buton mevcuttur. Ölçülen değer termometre üzerinden gözlemlenebilir veya read buffer üzerinden okunabilir.

![Ekran görüntüsü 2022-06-05 153327](https://user-images.githubusercontent.com/98150341/172052712-fede8c8d-b049-4da7-92d0-12b5cdd6795d.png)

- Kontrol Panelinde ölçtüğümüz değer, belirlediğimiz değerin üzerine çıktığında uyarı niteliğinde bir led mevcuttur. Bu proje için ledin aktif olacağı değerler ile alakalı tablo aşağıdaki gibidir:

| Led Aktif | Led Pasif |
|--|--|
| Data<40 | Data>40 |

Bu ledin aktif halde olduğu görsel aşağıdaki gibidir:

![Ekran görüntüsü 2022-06-05 153705](https://user-images.githubusercontent.com/98150341/172053073-4d6fb9b4-f9fe-40a3-87be-89f560b48ed1.png)

- Sisteme ait Blok Diyagramı aşağıdaki gibidir:

![Ekran görüntüsü 2022-06-05 153733](https://user-images.githubusercontent.com/98150341/172053126-9137b3a0-ee10-41e6-a5bb-f1b10ce774fd.png)

- Sistemin çalışması için gerekli Arduino Nano kodu aşağıdaki gibidir:

```
// 170519022 Yağmur Ertoksöz
int value = 0;
float temp = 0;
void setup()
{
  Serial.begin(9600);
}

void loop()
{
  value = analogRead(A1);
  temp = (5.0 * value * 100.0) / 1024.0;
  Serial.println(temp);
  delay(500);
}
```

- 5V kırmızı, GND siyah, Sinya sarı kablo ile bağlanmıştır. Gerekli Arduino Nano bağlantıları Breadboard üzerinde aşağıdaki gibidir:

![WhatsApp Image 2022-06-05 at 17 23 50](https://user-images.githubusercontent.com/98150341/172055307-ed04e63c-e1c8-4e32-a103-be7c5a0b2a0d.jpeg)

### Sonuç
Gerek hobi olarak, gerek bir gereksinim olarak kullanabileceğiniz bu sistemi umarım kullanışlı bulursunuz.

