# Aquivo Dose 3 1.5.4

Signed production firmware for AQUIVO-DOSE3-ZB (ESP32-C6, 4 MB).

The device web calibration now matches the HASS card: fixed 4-second measurement, **Save** on both intermediate steps, and no time/flow proposal row. All seven offline languages are included. The 4 ml verification (3.9–4.1 ml) and separate final confirmation remain required. The previous saved flow remains until confirmation.

This is a web interface update. Dosing logic, schedules, reservoir calculations, state storage and Zigbee endpoints are unchanged from 1.5.3. Existing calibration, plans, names, counters, reservoir levels, inter-pump pause and Zigbee pairing are preserved. No new interview or reconfiguration is required for this release.

The device includes card 1.5.5 and its offline installer. In HASS click a fertilizer name directly to edit it; HASS-only labels are saved for the signed-in user account. This does not change the device-web name. Card/HACS repository: https://github.com/maros22/aquivo-dose3-card

Update in SERVICE with all pumps stopped, using the matching signed manifest. Do not erase NVS, partitions or pairing. Source archives, flash backups, signing keys and recovery scripts remain private.
