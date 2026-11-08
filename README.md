# Aquivo Dose 3 · signed firmware 1.4.1

Guided calibration for all three pumps, on the device web interface and the [Home Assistant/HACS card](https://github.com/maros22/aquivo-dose3-card). Seven offline languages: Slovak, Czech, Hungarian, Polish, English, German and French.

Firmware 1.4.1 corrects the bundled card version label and the Wi-Fi setup footer. The calibration behavior and HASS card remain 1.4.0.

## Calibration

Use SERVICE and collect liquid outside the aquarium. Prime the tubing, release a little liquid and prepare an empty 5 ml measuring cylinder. Start with a 2-second measurement; stop before 5 ml. Increase duration only after checking actual flow (ideally collect 2–4 ml). Enter the collected volume, empty the cylinder, then run the 4 ml verification. Enter its actual measured volume. **Saving is allowed only after a completed verification of 3.9–4.1 ml (±2.5%).** A failed verification requires repeating calibration. Cancelling or rebooting preserves the previous saved flow.

Calibration and priming liquid is collected outside the aquarium and is excluded from aquarium daily/total doses. Reservoir use is estimated conservatively; check the actual remaining liquid after calibration. Never treat the initial time or a nominal pump specification as an accurate calibration.

## Installation and updates

Download the matching `.bin` and `.manifest.json` from [release v1.4.1](https://github.com/maros22/aquivo-dose3-updates/releases/tag/v1.4.1). This is an application image, not a USB/full-flash image. Use the device web updater in SERVICE with all pumps stopped. The updater verifies ECDSA-P256 signature, model, version, size and SHA256. Settings, saved calibration, volumes, schedules and Zigbee pairing are retained. Check the result before enabling AUTO.

The current model is `AQUIVO-DOSE3-ZB`, manufacturer Aquivo. After upgrading, interview and reconfigure the existing Dose 3 in Zigbee2MQTT to load its seven calibration entities. Keep the same device and entity IDs/history. Use card 1.4.0 with `custom:aquivo-dose3-card`; the installation guide covers migration and the `aquivo_dose3` helper. Load one JavaScript resource only.

Units from firmware older than 1.4.0 may require a one-time manufacturer-assisted migration to the Aquivo model/signature format; do not bypass signature checks or erase pairing/settings. Subsequent signed public updates require no customer GitHub account or expiring token. `latest.json` contains signed public metadata. Publishing an update does not start pumps.

## Validation

Controller, actual runtime output, signature/OTA policy, schema capacity, card, installer and seven-language DOM tests passed. On an ESP32-C6 board, all three disconnected output channels passed timed measurement, automatic verification cutoff, failed-save rejection, and successful-verification cancellation. The live HASS wizard and signed Wi-Fi OTA to the other slot were verified, preserving settings and SERVICE. Real liquid accuracy still requires measurement with each connected pump.

The Zigbee calibration reports use RAM reporting configuration and standard ZCL reports, avoiding expansion of the SDK persistent reporting dataset. The original persisted reporting records and Zigbee storage layout are retained. OTA boot acceptance waits for Zigbee restoration.

Source code, signing keys, private flash backups, targeted USB repair tools and credentials are not part of this public distribution.
