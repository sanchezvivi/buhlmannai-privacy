# Buhlmann AI — Privacy Policy

Last updated: 2026-07-07

---

## 1. Overview

Buhlmann AI is a single-user, on-device dive planning tool, developed and maintained as an independent personal project and hobby, unaffiliated with any employer. It has no accounts, no cloud sync, and no server of its own. Your dive logs and health data are stored exclusively on your device and are never transmitted to our servers or to any third-party analytics or advertising service.

**Buhlmann AI is not a dive computer and not a medical device.** It is not
cleared or approved by the FDA or any equivalent regulatory body as a medical
or safety instrument. The gradient-factor suggestions it provides are
decision-support only — they are not a substitute for certified decompression
planning, a properly calibrated dive computer, hyperbaric/dive-medicine
professional advice, or your own training and judgment. You assume full
responsibility for your own dive planning and execution; the developer
accepts no liability for injury, decompression illness, or other harm arising
from use of this app. See the full disclaimer in section 13 and the in-app
disclaimer.

---

## 2. Data we do NOT collect

- We do not create or require an account.
- We do not operate any server that receives your data.
- We do not use analytics, crash-reporting SDKs, or advertising networks.
- We do not collect or transmit identifiers (device ID, advertising ID, IP address).
- We do not track your behaviour across sessions or across devices.

---

## 3. Data stored on your device

The app stores the following data locally on your device:

| Category | Examples | Where stored |
|---|---|---|
| Dive logs | Depth, time, gas mix, temperature, safety-stop records | On-device SQLite database |
| Health metrics | HRV, resting heart rate, sleep duration, weight, body-fat percentage, SpO2, VO2max, menstrual flow | On-device SQLite database (read from Apple HealthKit with your permission) |
| App preferences | Unit settings, GF baseline, AI-surface toggles | On-device key-value store |
| Gear inventory | Equipment list, service dates | On-device SQLite database |
| Planned dives | Planned depth, gas, dive site | On-device SQLite database |
| Paired dive computer | Dive records downloaded via Bluetooth from a paired Shearwater-compatible dive computer, and the paired device's identity for reconnection | On-device SQLite database / key-value store |

The app requests Bluetooth access solely to connect to and download dive logs from
a dive computer you pair yourself. This connection is device-to-device only —
no dive-computer data is transmitted to any server.

All on-device data is protected at rest by iOS hardware encryption
(NSFileProtectionComplete) and the SQLite database is excluded from iCloud
backup. This means the database does not sync to iCloud Drive and does not
appear in iCloud backups of your device. App preferences (key-value store) may
be included in a standard iCloud device backup.

---

## 4. Data that leaves your device

**One type of data leaves your device**: location information for your planned
dive site is sent to [Open-Meteo](https://open-meteo.com) to fetch a marine
weather forecast and the site's terrain elevation (used to set the altitude
of your dive plan). Specifically:

- If you select a dive site by coordinates, the **latitude and longitude** you
  entered are sent.
- If you search for a location by name, the **place name you type** is sent to
  Open-Meteo's geocoding endpoint to resolve it to coordinates, after which the
  resolved coordinates are used for the weather request.

No personal data, health data, dive-log data, or any device identifier
accompanies these requests. Open-Meteo is a free, open-source weather service;
refer to their [privacy policy](https://open-meteo.com/en/terms) for how they
handle request logs.

This location data is not linked to your identity, is not used for
tracking, and is not shared with any other party. Under Apple's App Privacy
labeling, this is disclosed as Location data used for App Functionality,
not linked to you.

No health data, dive data, or identifiers leave your device to any server we
or a third party operate.

**Data you choose to share yourself.** The app lets you export a dive log or
gear-sync file (for example, to send to another app or device via the iOS
share sheet) and import dive files (`.fit`/`.csv`) via "Open in…"/Files. These
actions are initiated entirely by you and go wherever you direct them (e.g.
AirDrop, Mail, Files, iCloud Drive) — they are not sent to us or to any
third-party service by the app itself.

---

## 5. HealthKit (Apple Health)

The app requests read-only access to the following HealthKit data types, each
used for a specific input into your personalized gradient-factor (dive
conservatism) suggestion:

- **Heart Rate Variability (SDNN)** — a marker of recovery/stress used to adjust conservatism
- **Resting Heart Rate** — a marker of recovery/stress used to adjust conservatism
- **Sleep Analysis** — sleep duration used to assess fatigue-related conservatism
- **Body Mass (weight)** — used with body composition to assess fitness-related decompression risk factors
- **Body Fat Percentage** — used alongside body mass to assess fitness-related decompression risk factors
- **Blood Oxygen Saturation (SpO2)** — used as a general fitness/respiratory signal in the conservatism calculation
- **VO2 Max** — a cardiorespiratory fitness marker used to adjust conservatism
- **Menstrual Flow** — used, where applicable, as one input to conservatism, reflecting known physiological effects of cycle phase on decompression stress
- **Date of Birth** (characteristic data, not a time-series sample) — used to derive age for the gradient-factor calculation

HealthKit data is read on-demand when you open the app and is stored only in
the on-device SQLite / key-value store. It is never written back to HealthKit
and never transmitted off-device. You can revoke HealthKit access at any time
in iOS Settings > Health > Data Access & Devices.

Date of birth is used only to derive your age for the gradient-factor
calculation. If you have already entered your date of birth manually in the
app, that entry always takes precedence — the Health app value is never used
to overwrite it. If Apple Health has no date of birth on file (or access is
denied), your manual entry or the app's conservative unknown-age fallback
applies, unchanged.

---

## 6. On-device AI (Apple Foundation Models)

Buhlmann AI uses Apple's on-device Foundation Models for the dive briefing
(including trip-context scenarios) and gear suggestion features. All inference
runs locally on your device's Neural Engine. No data is sent to any AI
provider — not to Anthropic, OpenAI, Apple, or any other service — as part of
these features. The on-device isolation is enforced by an automated boundary
test on every build.

---

## 7. No advertising or tracking

The app contains no advertising SDKs, no tracking pixels, no third-party
analytics (no Firebase, Amplitude, Mixpanel, Sentry, Crashlytics, or
equivalent), and no affiliate links or referral codes. If the app ever
introduces a paid unlock (in-app purchase), it will be processed entirely by
Apple's App Store payment system — the developer does not receive or store
your payment information, and this section will be updated accordingly.

---

## 8. Data deletion

Uninstalling the app removes all locally stored data. A data-reset option is
also available within the app's Settings. Note that app preferences
(key-value store) may be included in an iCloud device backup (see section 3)
and could be restored if you reinstall from that backup. Because there is no
server, there is nothing to request deletion of from us.

---

## 9. Children

This app is not directed at children under 13 and we do not knowingly collect
any personal data from children. Diving certifications require a minimum age;
this app is intended for certified divers.

---

## 10. Your rights

Because all data is processed and stored solely on your device and never
reaches a server we operate, there is no remote copy of your data for us to
access, export, or delete on your behalf — you have direct and exclusive
control over it at all times via the app's own data-deletion feature (section
8) or by uninstalling the app. This app is not directed to, and does not
knowingly process personal data of, residents of any specific jurisdiction in
a way requiring a data controller relationship; if you have questions about
your rights under GDPR, Brazil's LGPD (Lei Geral de Proteção de Dados), CCPA,
or an equivalent local law, contact the developer as described in section 11.

---

## 11. Contact

This is a single-developer, privacy-first app. Questions can be directed to
the developer at vivi.c.sanchez@gmail.com. There is no mailing list or
account system through which to contact users.

---

## 12. Changes to this policy

If we change this policy in a material way we will update the "Last updated"
date above and, where required, display a notice in the app. Continued use after
an update constitutes acceptance of the revised policy.

---

## 13. Safety and medical disclaimer

Buhlmann AI is not a dive computer and not a medical device. It is not cleared
or approved by the FDA or any equivalent regulatory body as a medical or safety
instrument. The gradient-factor suggestions it provides are decision-support
only — they are not a substitute for certified decompression planning, a
properly calibrated dive computer, hyperbaric/dive-medicine professional
advice, or your own training and judgment.

You use this app entirely at your own risk. To the fullest extent permitted by
law, the developer disclaims all liability for any injury, decompression
illness, equipment loss, or other harm arising from use of, or reliance on,
this app. See the in-app disclaimer for the full safety notice.
