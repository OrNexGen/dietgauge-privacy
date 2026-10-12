# HeartTrack: Sodium & Sat Fat — Privacy Policy

**Last updated:** 2026-10-12  
**Official live policy:** [https://ornexgen.github.io/hearttrack-privacy/](https://ornexgen.github.io/hearttrack-privacy/)  
**Contact:** organizer.next.generation@gmail.com  
**Application ID:** `com.ornexgen.hearttrack`  

This privacy policy explains how the Android application **HeartTrack: Sodium & Sat Fat** ("HeartTrack", "the app", "we", or "us") handles user data and protects your privacy.

## Summary

- **100% On-Device Data Storage:** The app operates without developer servers or user accounts. All food logs, companion vitals, custom recipes, daily journal notes, and nutritional targets are stored exclusively on your device in a private local database.
- **100% Ad-Free & Tracker-Free:** The app contains zero advertisements, zero third-party analytics SDKs, and zero advertising identifiers (no Google Advertising ID / AAID).
- **Public Nutrient Queries Only:** Food searches and barcode lookups query public and open food databases (USDA FoodData Central and Open Food Facts) without transmitting user accounts, names, or personal identifiers.
- **Privacy-Preserving Camera:** Camera access is requested solely for on-device barcode recognition. Camera frames are processed entirely in real time on your device; no photos, video feeds, or images are ever saved, stored, or transmitted.
- **Health Connect Limited Use Compliance:** Optional Android Health Connect synchronization operates strictly on-device between your local health apps. Health data is never sold, never transferred to third parties or developer servers, never used for advertising, and never used to train artificial intelligence (AI) or machine learning (ML) models.
- **Local-Only Meal Reminders:** Scheduled meal reminders are generated 100% on-device by the Android operating system. No cloud push servers, push tokens, or remote messaging services are used.
- **Offline Data Portability:** You can export and restore complete offline JSON backups of your health records at any time directly through your device's system share sheet.

---

## Information Stored on Your Device

HeartTrack stores your health and dietary information strictly on your local device within the application's private SQLite database and app preferences storage:

- **Food Intake Logs:** Food item titles, portion sizes (grams or household units), meal categories (Breakfast, Lunch, Dinner, Snack), logging timestamps, full nutrient breakdowns (sodium, saturated fat, calories, and any enabled companion metrics), and optional product barcodes.
- **Companion Vitals:** Blood pressure records (systolic, diastolic, pulse rate, measurement arm) and morning dry weight logs.
- **Templates & Notes:** User-created combo meal templates and daily dietary context notes.
- **Nutritional Targets & Preferences:** Selected cardiovascular target thresholds, display units, app language, and theme choices.
- **Disclaimer Acknowledgement:** The accepted disclaimer version and timestamp.

We have no access to this data, operate no cloud databases to receive it, and never sell or transfer it. This data is permanently removed if you clear the app's data in Android system settings or uninstall the application. If you have Android Auto-Backup enabled on your device, the Android operating system may include the app's private files in your personal Google Drive backup under your personal Google account.

---

## Device Permissions Disclosures

The application declares and requests only permissions strictly necessary to provide its core features. HeartTrack does not request background location, contacts, phone state, microphone, or external storage permissions.

### 1. Camera (`android.permission.CAMERA`)
- **Purpose:** Used solely for scanning packaged food barcodes to quickly look up nutritional values (`[FEAT-16]`).
- **Processing:** Barcode decoding is performed entirely on your device in real time using local machine-vision scanning libraries.
- **Zero Image Storage or Transmission:** The camera feed is never recorded, never captured into image or video files, and never sent across the internet.
- **Optional:** Camera permission is requested only when opening the barcode scanner. If you decline camera access, all other app features—including manual food logging and USDA text search—remain fully functional.

### 2. Network Access (`android.permission.INTERNET`)
- **Purpose:** Used strictly to make outbound HTTPS queries to public food databases when you search for foods or scan barcodes.
- **Scope:** Connects only to the **U.S. Department of Agriculture (USDA) FoodData Central** REST API and the **Open Food Facts** public database API.
- **Zero Tracking:** No user profile, device identifier, advertising identifier, or personal health log is ever transmitted. The app does not ping any developer server, crash-reporting endpoint, or remote analytics service.

### 3. Local Meal Reminders (`android.permission.POST_NOTIFICATIONS`, `android.permission.RECEIVE_BOOT_COMPLETED`, `android.permission.VIBRATE`)
- **Purpose:** Used to deliver optional, scheduled meal logging reminders at times configured by the user (`[FEAT-22]`).
- **`POST_NOTIFICATIONS`:** Requested on Android 13 (API level 33) and higher to display scheduled local notifications for designated meal times (e.g., Breakfast, Lunch, Dinner).
- **`RECEIVE_BOOT_COMPLETED`:** Allows the app to restore locally scheduled reminder alarms after your device is restarted, ensuring your chosen reminders continue without requiring you to manually open the app.
- **`VIBRATE`:** Allows your device to vibrate when a reminder notification fires, according to your system sound and vibration settings.
- **100% Local Scheduling:** All reminders are scheduled entirely on-device using Android's local alarm scheduler (`AlarmManager` / `NotificationManager`). HeartTrack does not use Firebase Cloud Messaging (FCM), push notification servers, device push tokens, or remote tracking. If you disable meal reminders, all scheduled alarms are immediately canceled.

---

## Android Health Connect Integration & Data Disclosures

HeartTrack provides optional, user-controlled integration with **Android Health Connect** (`androidx.health.connect.client`), allowing you to synchronize dietary intake and vital signs with your device's unified health ecosystem (`[FEAT-21]`).

### Health Connect Permissions Requested & Purposes
When you enable Health Connect sync, HeartTrack may request access to the following permissions:
- **`android.permission.health.READ_NUTRITION`:** Reads dietary nutrient records (calories, sodium, saturated fat, etc.) logged by other authorized apps on your device to prevent duplicate entries and provide comprehensive daily intake totals.
- **`android.permission.health.WRITE_NUTRITION`:** Writes nutrition data logged in HeartTrack (calories, sodium, saturated fat, trans fat, dietary fiber, added sugars, cholesterol, and potassium) to Health Connect, allowing other compatible health apps to reflect your dietary intake.
- **`android.permission.health.READ_BLOOD_PRESSURE`:** Reads resting systolic and diastolic blood pressure measurements and pulse records from Health Connect (e.g., from connected blood pressure monitors or compatible health apps).
- **`android.permission.health.READ_WEIGHT`:** Reads body weight measurements from Health Connect (e.g., from smart scales or companion fitness apps).

### Compliance with Google Play Health Connect Policy & Limited Use Requirements
HeartTrack strictly complies with the **Google Play Health Connect Policy**, including the **Limited Use Requirements**:
1. **Never Sold to Third Parties:** We do not sell, rent, lease, or monetize Health Connect data under any circumstances.
2. **Never Transferred to Third Parties or Developer Servers:** Health Connect data is accessed and processed strictly on your local device. It is never transferred to external servers, cloud databases, or third parties.
3. **Never Used for Advertising:** Health Connect data is never used or disclosed for personalized, retargeted, interest-based, or generalized advertising or marketing.
4. **Never Used for Artificial Intelligence / Machine Learning Training:** Health Connect data is never used to train machine learning models, artificial intelligence algorithms, or large language models.
5. **Used Solely for User-Facing Health Awareness:** All data accessed through Health Connect is used exclusively to provide and improve user-facing cardiovascular and dietary tracking features directly requested by the user.

### User Control, Transparency, and Revocation
- **Explicit User Control:** Health Connect integration is entirely optional and disabled by default. No health data is read from or written to Health Connect until you explicitly initiate synchronization.
- **Permission Management:** You can grant, deny, or revoke individual Health Connect permissions at any time directly in Android system settings (**Settings > Security & privacy > Privacy > Health Connect > App permissions > HeartTrack**).
- **Data Deletion:** You can view, manage, and delete any data synchronized by HeartTrack directly within the Android Health Connect management interface or by clearing HeartTrack's local app storage.

---

## Food Search and Barcode Lookup (USDA FoodData Central & Open Food Facts)

When you look up nutritional data:
- **Text Search:** When you search for a food by name, your search query is sent via HTTPS to the **U.S. Department of Agriculture (USDA) FoodData Central** REST API to retrieve public-domain nutritional information.
- **Barcode Lookup:** When you scan a packaged food barcode, the app queries **USDA FoodData Central** and **Open Food Facts** (an open crowdsourced database made available under the Open Database License, ODbL v1.0) to retrieve product names and reported nutrient profiles.
- **Zero Personal Identifiers:** No user accounts, personal names, device identifiers, or tracking tokens are sent with search or barcode requests. As with any standard internet request, the third-party service receives the query and can see your device's IP address. For more details on their data handling, refer to the [USDA FoodData Central Privacy Policy](https://www.usda.gov/privacy-policy) and [Open Food Facts Privacy Policy](https://world.openfoodfacts.org/privacy).

---

## Backup & Data Portability (100% Offline)

HeartTrack allows you to export your complete health and nutrition history into a portable JSON backup file and restore it on another device or after reinstalling. Backup files are generated strictly on your device and shared only through user-directed actions via your device's system share sheet (such as saving to local storage, Google Drive, or sending via message/email). We operate no developer servers, accounts, or cloud databases; your backup files are never transmitted to us or any third party.

---

## Advertising & Tracking (100% Ad-Free)

The app is completely free, contains zero advertisements, and includes no third-party advertising SDKs, ad networks, or user tracking services. We do not use or collect Google Advertising IDs (AAID), device tracking identifiers, or usage analytics. HeartTrack qualifies for European Union Digital Services Act (EU DSA) **Non-Trader** status.

---

## Health & Medical Boundaries (Not Medical Advice)

HeartTrack is a passive tracking and awareness tool designed in accordance with FDA General Wellness guidance. It is not a medical device (Software as a Medical Device - SaMD) and does not diagnose, treat, cure, mitigate, prevent, or provide clinical management for hypertension, cardiovascular disease, kidney disease, or any other medical condition. Always follow the personalized guidance of your physician, cardiologist, or registered dietitian regarding your diet, nutrient limits, and medical care.

---

## Children's Privacy

HeartTrack is not directed to children under 13 years of age, and we do not knowingly collect personal information from children.

---

## Changes to this Privacy Policy

If we update this privacy policy, the revised version will be published on this page with an updated "Last updated" date. You can review the authoritative live version at [https://ornexgen.github.io/hearttrack-privacy/](https://ornexgen.github.io/hearttrack-privacy/).

---

## Contact & Developer Information

If you have questions, feedback, or concerns regarding this privacy policy or HeartTrack's data practices, please contact:

- **Developer:** OrNexGen (Publisher: `com.ornexgen.hearttrack`)
- **Email:** organizer.next.generation@gmail.com
- **Website & Privacy Policy:** [https://ornexgen.github.io/hearttrack-privacy/](https://ornexgen.github.io/hearttrack-privacy/)
