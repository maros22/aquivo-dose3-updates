# Aquivo Dose 3 — aktualizácie

Verejná distribúcia hotového firmvéru pre Aquivo Dose 3 / NET4U-FERT3-ZB, ESP32-C6. Zdrojový kód firmvéru nie je súčasťou tohto repozitára.

## Aktualizácia zo zariadenia

Od verzie 1.2.0 otvor web dávkovača → Nové verzie firmvéru → Skontrolovať novú verziu. Zariadenie kontroluje vydania aj automaticky každých 6 hodín. Novšiu verziu nainštaluj po potvrdení v SERVICE pri zastavených pumpách. Po aktualizácii zostane SERVICE; kalibrácie, plány, názvy, Wi-Fi a Zigbee sa zachovajú.

Žiadny GitHub účet ani obnovovanie kľúča nie je potrebné. Kontrola potrebuje Wi-Fi, internet a overený čas. Dávkovanie nie je závislé od dostupnosti GitHubu.

## Ručná aktualizácia

Vo vydaní stiahni aplikačný `Aquivo-Dose-3-OTA-X.Y.Z.bin` a zodpovedajúci `Aquivo-Dose-3-OTA-X.Y.Z.manifest.json`. Na webe vyber oba súbory a nahraj v SERVICE. Nepoužívaj bootloader ani celý obraz flash. Počas aktualizácie nevypínaj napájanie.

## Overovanie

Manifest obsahuje podpis ECDSA-P256/SHA256 pre model, verziu, veľkosť a SHA256 celého firmvéru. Zariadenie používa verejný kľúč výrobcu pevne vložený do aplikácie a pri neplatnom podpise alebo poškodenom prenose nový firmvér neaktivuje. Súkromný podpisový kľúč sa nikdy nedistribuuje.

Ide o ochranu pravosti OTA aktualizácií. Samotný podpis nebráni kopírovaniu firmvéru a nenahrádza hardvérový Secure Boot ani ochranu pred priamym prepisom flash cez USB.

## Home Assistant

Karta a inštalácia cez HACS: https://github.com/maros22/aquivo-dose3-card . Kartu a slovenský návod možno stiahnuť aj priamo z webu dávkovača v sekcii Karta pre Home Assistant.
