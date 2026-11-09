# Aquivo Dose 3 1.5.3

Signed production firmware for AQUIVO-DOSE3-ZB (ESP32-C6, 4 MB).

- Enabling AUTO catches up today's missed doses, including after calibration, schedule edits or a power interruption. Earlier days are not replayed. Calibration saves remain in SERVICE. Actual daily and total doses, existing calibration, refill amounts, plan and pairing are preserved.
- Card 1.5.3 shows the scheduled part of today's dosing plus a red **+ X ml** for manual doses. The total entity includes both. Three standard Zigbee sensors expose device-counted manual doses, including doses requested from the device web interface; calibration/priming are excluded.
- Every positive refill amount is the new 100% reservoir reference. Zero marks the container empty.
- Calibration controls show cooldown and fresh device acknowledgements. No automatic retry of a physical command. Seven offline languages and the dynamic native external web link are retained.
- The macOS card uses plain text time fields instead of the native picker that can crash the Companion app. Fields stay inside their columns.
- Reporting configuration is held in RAM to avoid an SDK NVRAM failure. Source and destination binding tables each have 72 slots for 69 reporting pairs on 64 unchanged endpoints.
- Fertilizer names can be edited on the device web interface. HASS name synchronization requires an optional external converter; it is not installed or enabled automatically.
- The legacy state record stays compatible with rollback. Richer stored data is accepted only when its projection matches the current base; retired skip metadata is cleared without resetting actual dosing counters.

Update in SERVICE with stopped pumps, using the matching signed manifest. Do not erase NVS, partitions or Zigbee pairing. Refresh interview and reconfigure only Dose 3 after installation to discover its new standard sensors. Do not remove/re-pair the device.

Card and HACS repository: https://github.com/maros22/aquivo-dose3-card

Only application binaries, public signed metadata and user documentation belong here. Source archives, flash backups, signing keys and board-specific recovery tools stay private.
