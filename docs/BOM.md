# Kusovník

## Elektronika

| Komponenta | Množství | Stav | Poznámka |
| --- | ---: | --- | --- |
| ESP32-S3 SuperMini, USB-C | 1 | k dispozici | hlavní řídicí jednotka |
| Waveshare RGB COB WS2812B, 5 V, 1 m | 1 | objednáno | 160 LED/m, 12 W/m, šířka 2,7 mm |
| GY-302 BH1750 | 1 | objednáno | I²C senzor osvětlení |
| HC-SR501 | 1 | k dispozici | PIR senzor pohybu |
| TTP223 | 2 | k dispozici | kapacitní dotyková tlačítka |
| Rezistor 470 Ω / 0,25 W | 1 + rezerva | objednáno | sériově do datové linky LED |
| Kondenzátor 470 µF / 50 V | 1–2 + rezerva | objednáno | mezi 5 V a GND u LED, dodržet polaritu |
| Dupont vodiče | dle potřeby | k dispozici | prototypování a kabeláž |
| USB-C kabel | 1 | k dispozici | napájení ESP32 |

## Mechanika

| Materiál | Množství | Poznámka |
| --- | ---: | --- |
| Hliníkový profil nebo pásovina | přibližně 50 cm | podklad a chlazení předního pásku |
| PETG nebo ASA | dle modelu | držák a kryt; nepoužívat PLA |
| Průsvitný nebo bílý PETG | malé množství | volitelný difuzér 0,4–0,8 mm |
| Ocelové matky/šrouby | dle vyvážení | protiváha |
| Protiskluzová guma nebo pěna | dle držáku | ochrana monitoru a stabilita |
| Smršťovací bužírka | dle potřeby | izolace spojů |
| Oboustranná páska / příchytky | dle potřeby | zadní část pásku |

## Pozdější volitelná změna

Pro vyšší jas lze použít napájení 5 V / 3 A rozbočené před ESP32. V takovém případě se LED nenapájí přes proudovou cestu desky.

