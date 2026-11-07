# Aquivo Dose 3 · signed firmware 1.3.1

Fixes the Dose 3 card footer: visible card version and a larger device web link with its current IP, opened in the same window. Seven offline interface languages: Slovak, Czech, Hungarian, Polish, English, German and French. Automatic browser language and manual selection on all device pages. Home Assistant card 1.3.1 has the same languages with editor/YAML selection.

- Firmware: [releases](https://github.com/maros22/aquivo-dose3-updates/releases)
- HASS/HACS card and installation guide: [aquivo-dose3-card](https://github.com/maros22/aquivo-dose3-card)
- `latest.json`: public signed metadata used by devices. No customer GitHub account or expiring token is required.

Update from the device web interface in SERVICE with every pump stopped. The updater verifies the manufacturer’s ECDSA-P256 signature, model, version, size and SHA256. For manual Wi-Fi OTA select the matching `.bin` and `.manifest.json`. This is an application image, not a USB/full-flash image. Firmware remains in SERVICE after update; settings, calibration, volumes, schedules and Zigbee pairing are retained. Check the result before enabling AUTO. Language changes never send pump commands. Schedule time zone remains Europe/Bratislava.

SK: Aktualizácia v SERVICE so zastavenými pumpami; vyber zodpovedajúci .bin a .manifest.json. Jazyk vyber hore na webe.

CS: Aktualizuj v SERVICE se zastavenými čerpadly; vyber odpovídající .bin a .manifest.json. Jazyk vyber nahoře na webu.

HU: Frissíts SERVICE módban, leállított szivattyúkkal; válaszd a megfelelő .bin és .manifest.json fájlt. A nyelv a weboldal tetején állítható.

PL: Aktualizuj w SERVICE przy zatrzymanych pompach; wybierz pasujące pliki .bin i .manifest.json. Język wybierz na górze strony.

EN: Update in SERVICE with pumps stopped; select the matching .bin and .manifest.json. Choose the language at the top of the page.

DE: In SERVICE bei gestoppten Pumpen aktualisieren; passende .bin und .manifest.json wählen. Sprache oben auf der Seite auswählen.

FR: Mettez à jour en SERVICE avec les pompes arrêtées ; choisissez les fichiers .bin et .manifest.json correspondants. Choisissez la langue en haut de la page.

Source code, signing keys, private flash backups and credentials are not included in this public distribution.
