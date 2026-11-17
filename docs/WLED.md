# WLED a firmware

## Základní konfigurace

| Nastavení | Hodnota |
| --- | --- |
| MCU | ESP32-S3 |
| Typ LED | WS281x |
| Color order | GRB |
| Datový GPIO | 4 |
| Předpokládaný počet LED | 160 |
| Segment 1 | 0–79, přední světlo |
| Segment 2 | 80–159, zadní podsvícení |
| Proudový limit | 800–850 mA |

Počet pixelů ověřit na skutečném pásku ještě před stříháním. Dokumentace výrobce uvádí 160 LED/m a produktový materiál deklaruje samostatné řízení každé LED.

## Tlačítka

TTP223 moduly ponechat v momentovém režimu. Jejich výstup je při dotyku aktivní HIGH.

| Modul | GPIO | Funkce |
| --- | ---: | --- |
| TTP223 #1 | 6 | přepnutí světla ON/OFF |
| TTP223 #2 | 7 | přepnutí AUTO/MANUAL jasu |

V konfiguraci WLED pravděpodobně použít aktivní vysoký/invertovaný typ tlačítka a ověřit chování na stole.

## BH1750 a automatický jas

Standardní BH1750 usermod měří intenzitu osvětlení, ale sám nenastavuje hlavní jas WLED. Projekt proto potřebuje malý vlastní usermod s následujícím chováním:

1. Pravidelně načíst lux z BH1750.
2. Hodnotu filtrovat, aby jas nekolísal.
3. Převést rozsah lux na nastavitelný rozsah jasu.
4. Omezit rychlost změny jasu.
5. Respektovat proudový limit WLED.
6. GPIO 7 používat jako přepínač režimu AUTO/MANUAL.
7. Při vypnutí automatiky ponechat aktuální jas.
8. Stav režimu uložit a obnovit po restartu.

## Doporučené potvrzení režimu

- krátké zelené bliknutí: automatický jas zapnutý
- krátké oranžové bliknutí: ruční jas zapnutý

Potvrzení nesmí trvale měnit uložený preset ani segmenty.

## PIR

HC-SR501 nastavit na nejkratší hardwarovou prodlevu. Delší čas vypnutí řešit ve firmwaru, aby bylo možné chování později měnit bez přístupu k trimru.

