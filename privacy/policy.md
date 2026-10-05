# Privacy Policy for Vinyl Diagnostics

**Effective date:** 5 October 2026

**App:** Vinyl Diagnostics (Android package / Flutter project `vinyl_diagnostics`)  
**Developer:** Mikko Pulli (GitHub: [otsatukka](https://github.com/otsatukka))  
**Contact:** CONTACT_EMAIL

This policy describes how Vinyl Diagnostics handles information. It is based on an audit of the app’s source code as of the effective date.

## Summary

Vinyl Diagnostics analyses vinyl / turntable test signals on your device. Audio is used only for on-device measurement. The developer does not collect, transmit, or share your measurement data, recordings, or personal information. There are no accounts, ads, or analytics in the app.

## What the app does with audio

- The app requests microphone / recording permission (`RECORD_AUDIO`) so it can capture audio from the input you select (for example a USB interface, line-in / headset jack, or the built-in mic).
- Capture uses an in-memory PCM stream. Analysis (speed, wow & flutter, rumble, balance, and related measurements) runs entirely on your device.
- In normal shipping builds, raw audio is **not** saved to disk. Optional WAV/JSON debug dumps exist only when the binary is specially built with a developer compile-time flag (`CAPTURE_DEBUG_DUMP`); that flag is off for the Play Store build.
- Demo mode can use synthetic signals instead of live audio; no hardware or microphone is required for demo mode.

## What is stored on your device

Stored only locally (not sent to the developer):

- **Measurement results** — named turntable / “test item” entries and analysis metrics in app support storage (`test_items.json`). This stores results (numbers and related analysis metadata), not raw recordings.
- **Settings** — SharedPreferences flags such as demo mode and coloured quality-scale bands. Theme preference is in-memory for the session (not persisted).
- **Purchase unlock state** — on Android, Google Play Billing reports whether you own the one-time “full unlock” product. The app keeps that entitlement in memory for the session and re-checks with Play as needed; it does not upload purchase data to a developer server.

You can delete local app data by clearing the app’s storage in Android settings, or by uninstalling the app.

## What we do not do

Based on the audited code and dependencies:

- No developer-operated servers or APIs for this app.
- No analytics, crash-reporting, advertising, or tracking SDKs.
- No in-app accounts or sign-in with the developer.
- No ads.
- No export/share features that send your data off the device.
- `INTERNET` appears only in debug/profile Android manifests (Flutter tooling). The release main manifest does not declare `INTERNET`. The app’s Dart code does not make HTTP/network calls to developer endpoints.

## Purchases (Android)

On Android store builds, a one-time full unlock may be offered through **Google Play Billing** (`com.android.vending.BILLING` / `in_app_purchase`). Payment details are handled by Google Play under [Google’s Privacy Policy](https://policies.google.com/privacy). The developer does not receive your card or bank details.

Desktop builds (for example the Windows tester) use a non-billing stub and do not process Play purchases.

## Children’s privacy

Vinyl Diagnostics is aimed at adults and enthusiasts setting up and measuring turntables. It is not directed at children under 13. We do not knowingly collect personal information from children.

## Changes

If this policy changes, the effective date at the top will be updated and the published copy on this site will be revised.

## Contact

Questions about this policy: **CONTACT_EMAIL**  
Developer profile: [https://github.com/otsatukka](https://github.com/otsatukka)

*(Replace CONTACT_EMAIL with a real address before Play Console submission if required.)*
