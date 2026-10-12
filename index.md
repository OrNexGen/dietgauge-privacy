# HeartTrack: Sodium & Sat Fat — Privacy Policy

**Last updated:** 2026-10-12  
**Official live policy:** [https://ornexgen.github.io/hearttrack-privacy/](https://ornexgen.github.io/hearttrack-privacy/)  
**Contact:** organizer.next.generation@gmail.com  

This policy explains how the Android application **HeartTrack: Sodium & Sat Fat** ("the app") handles information and protects user privacy.

## Summary

- The app has no user accounts and operates without developer servers. All personal food logs, companion vitals, notes, and nutritional targets stay exclusively on your device.
- Food searches and packaged food barcode lookups query public and open food databases (USDA FoodData Central and Open Food Facts) with no user accounts, names, or personal identifiers attached.
- Camera access is requested solely for on-device barcode recognition. Camera frames are processed in real time on your device; no photos, video streams, or image captures are ever recorded, stored, or transmitted.
- The app is 100% ad-free and tracker-free. It contains zero advertisements, zero analytics SDKs, and zero advertising identifiers.
- You can export and restore complete offline JSON backups of your health records at any time directly through your device's system share sheet.

## Information stored on your device

The app stores the following data only on your device, in the application's private SQLite database and preferences storage:

- Foods you log (food title, portion size in grams or household units, date, meal category, nutrient values, and optional scanned barcode)
- Companion vitals (resting blood pressure, pulse, measurement arm, and daily morning dry weight entries)
- Saved combo meal templates and daily journal context notes
- Your chosen cardiovascular nutrients, daily targets, and appearance preferences
- Your confirmation of the in-app health disclaimer (version and acceptance date)

We do not receive, access, or share this data. It is permanently removed when you uninstall the app or clear its local storage. If Android backup is enabled on your device, Android may copy the app's private data to your personal Google Drive backup under your device's Google account settings.

## Device permissions (Camera)

The app requests permission to access your device camera (`android.permission.CAMERA`) strictly for scanning packaged food barcodes:
- **On-Device Barcode Recognition:** Barcode recognition is executed locally on your device in real time via on-device scanning libraries.
- **Zero Image Storage or Transmission:** The camera feed is never recorded, saved as photos or videos to local storage, or transmitted across the network or to our servers.
- **Optional Permission:** Camera access is requested only when opening the barcode scanner. If you decline camera permission, all other features of the app remain fully accessible (including manual food logging and USDA text searches).

## Food search and barcode lookup (USDA FoodData Central & Open Food Facts)

When you look up nutritional data:
- **Text Search:** When you search for a food by name, your search query is sent to the **U.S. Department of Agriculture (USDA) FoodData Central** REST API to retrieve public-domain nutritional information.
- **Barcode Lookup:** When you scan a packaged food barcode, the app queries **USDA FoodData Central** and **Open Food Facts** (an open crowdsourced database made available under the Open Database License, ODbL v1.0) to retrieve product names and reported nutrient profiles.
- **Zero Personal Identifiers:** No user accounts, personal names, device identifiers, or tracking tokens are sent with search or barcode requests. As with any standard internet request, the third-party service receives the query and can see your device's IP address. For more details on their data handling, refer to the [USDA FoodData Central Privacy Policy](https://www.usda.gov/privacy-policy) and [Open Food Facts Privacy Policy](https://world.openfoodfacts.org/privacy).

## Backup & Data Portability (100% Offline)

HeartTrack allows you to export your complete health and nutrition history into a portable JSON backup file and restore it on another device or after reinstalling. Backup files are generated strictly on your device and shared only through user-directed actions via your device's system share sheet (such as saving to local storage, Google Drive, or sending via message/email). We operate no developer servers, accounts, or cloud databases; your backup files are never transmitted to us or any third party.

## Advertising & Tracking (100% Ad-Free)

The app is entirely free, contains zero advertisements, and includes no third-party advertising SDKs, ad networks, or user tracking services. We do not use or collect Google Advertising IDs (AAID), device tracking identifiers, or usage analytics.

## Not medical advice

HeartTrack is a passive tracking and awareness tool. It is not a medical device (Software as a Medical Device - SaMD) and does not diagnose, treat, prevent, or provide clinical management for any medical condition. Always follow your doctor's or dietitian's guidance regarding your diet and treatment plan.

## Children

The app is not directed to children, and we do not knowingly collect personal information from children.

## Changes to this policy

If this policy changes, the updated version will be posted on this page with a revised date. You can review the authoritative live version at [https://ornexgen.github.io/hearttrack-privacy/](https://ornexgen.github.io/hearttrack-privacy/).

## Contact

Questions about this privacy policy may be directed to: organizer.next.generation@gmail.com
