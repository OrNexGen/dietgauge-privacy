# DietGauge: Sodium & Sat Fat — Privacy Policy

**Last updated:** 2026-10-26  
**Official live policy:** [https://ornexgen.github.io/dietgauge-privacy/](https://ornexgen.github.io/dietgauge-privacy/)  
**Contact:** organizer.next.generation@gmail.com  
**Application ID:** `com.ornexgen.dietgauge`  

This privacy policy explains how the Android application **DietGauge: Sodium & Sat Fat** ("DietGauge", "the app", "we", or "us") handles user data and protects your privacy.

## Summary

- **100% On-Device Data Storage:** The app operates without developer servers or user accounts. All food logs, companion vitals, custom recipes, daily journal notes, and nutritional targets are stored exclusively on your device in a private local database.
- **100% Ad-Free & Tracker-Free:** The app contains zero advertisements, zero third-party analytics SDKs, and zero advertising identifiers (no Google Advertising ID / AAID).
- **Public Nutrient Queries Only:** Food searches and barcode lookups query public and open food databases (USDA FoodData Central and Open Food Facts) without transmitting user accounts, names, or personal identifiers.
- **Privacy-Preserving Camera & On-Device ML Vision:** Camera access and optional photo gallery selection are used strictly on-device for barcode scanning, on-device food recognition image classification, and photographing packaged food nutrition facts labels (OCR text recognition). All image analysis, candidate labeling, and text extraction occur 100% locally on your device via Google ML Kit; no photos, images, or visual embeddings are ever uploaded, stored on developer servers, or transmitted across the internet.
- **Privacy-Preserving Voice Input & Dictation:** Optional voice food search and daily note dictation utilize Android's native system speech recognition intent without requesting microphone hardware permissions (`RECORD_AUDIO`). DietGauge never captures, accesses, or records audio streams, and operates zero voice servers; only the resulting transcribed text string is returned directly to the active input field.
- **Health Connect Limited Use Compliance:** Optional Android Health Connect synchronization operates strictly on-device between your local health apps. Health data is never sold, never transferred to third parties or developer servers, never used for advertising, and never used to train artificial intelligence (AI) or machine learning (ML) models.
- **Local-Only Meal Reminders:** Scheduled meal reminders are generated 100% on-device by the Android operating system. No cloud push servers, push tokens, or remote messaging services are used.
- **Offline Data Portability:** You can export and restore complete offline JSON backups of your health records at any time directly through your device's system share sheet.

---

## Information Stored on Your Device

DietGauge stores your health and dietary information strictly on your local device within the application's private SQLite database and app preferences storage:

- **Food Intake Logs:** Food item titles, portion sizes (grams or household units), meal categories (Breakfast, Lunch, Dinner, Snack), logging timestamps, full nutrient breakdowns (sodium, saturated fat, calories, and any enabled companion metrics), and optional product barcodes.
- **Companion Vitals:** Blood pressure records (systolic, diastolic, pulse rate, measurement arm) and morning dry weight logs.
- **Templates & Notes:** User-created combo meal templates and daily dietary context notes.
- **Nutritional Targets & Preferences:** Selected cardiovascular target thresholds, display units, app language, and theme choices.
- **Disclaimer Acknowledgement:** The accepted disclaimer version and timestamp.

We have no access to this data, operate no cloud databases to receive it, and never sell or transfer it. This data is permanently removed if you clear the app's data in Android system settings or uninstall the application. If you have Android Auto-Backup enabled on your device, the Android operating system may include the app's private files in your personal Google Drive backup under your personal Google account.

---

## Device Permissions Disclosures

The application declares and requests only permissions strictly necessary to provide its core features. DietGauge does not request background location, contacts, phone state, microphone, or external storage permissions.

### 1. Camera, Food Recognition & Nutrition Facts OCR (`android.permission.CAMERA`)
- **Purpose:** Used for scanning packaged food barcodes to look up nutritional values, capturing or selecting photos to recognize food items via on-device machine learning classification, and capturing photos of physical nutrition facts labels on food packaging for automated on-device text recognition.
- **Barcode Network Lookup:** Barcode image recognition occurs entirely on-device to decode the product digits. The resulting numeric code is then queried against public online databases (USDA FoodData Central / Open Food Facts) as disclosed under *Network Access* below; camera images or video feeds are never transmitted.
- **On-Device Food Recognition:** When taking a photo of a meal or selecting a photo from your gallery in 'Food' scanner mode, image classification is performed entirely on your device using local Google ML Kit machine learning models. The camera strictly classifies food candidate item names (e.g., 'Banana', 'Broccoli') without estimating calories or nutrients from raw pixels. The identified item label is then queried against public food databases only if you choose to search and log it. Captured photos are processed in temporary memory and immediately discarded—no photos are ever uploaded or transmitted.
- **On-Device Optical Character Recognition (OCR):** When snapping a nutrition label photo or choosing an existing image from your photo library, text recognition is performed entirely on your device using local Google ML Kit machine vision. Unlike barcode lookups, nutrition label text recognition and nutrient parsing occur entirely on-device with zero network requests.
- **Zero Remote Transmission & Ephemeral Processing:** Captured food photos and label images are processed strictly on-device in temporary local cache to extract item candidate labels or nutrient numbers, and are immediately discarded. No photos, image frames, or visual embeddings are ever sent to developer servers or third parties.
- **Photo Selection (Zero Extra Permissions):** When selecting an image from your photo library, the app utilizes the native Android Photo Picker, granting temporary access only to the single photo you choose without requesting broad storage or media permissions.
- **Optional:** Camera and photo access are strictly optional and requested only when using the barcode scanner, food recognition, or nutrition label OCR feature. If declined, all other app features—including manual food logging and USDA text search—remain fully functional.

### 2. Network Access (`android.permission.INTERNET`)
- **Purpose:** Used strictly to make outbound HTTPS queries to public food databases when you search for foods or scan barcodes.
- **Scope:** Connects only to the **U.S. Department of Agriculture (USDA) FoodData Central** REST API and the **Open Food Facts** public database API.
- **Zero Tracking:** No user profile, device identifier, advertising identifier, or personal health log is ever transmitted. The app does not ping any developer server, crash-reporting endpoint, or remote analytics service.

### 3. Local Meal Reminders (`android.permission.POST_NOTIFICATIONS`, `android.permission.RECEIVE_BOOT_COMPLETED`, `android.permission.VIBRATE`)
- **Purpose:** Used to deliver optional, scheduled meal logging reminders at times configured by the user.
- **`POST_NOTIFICATIONS`:** Requested on Android 13 (API level 33) and higher to display scheduled local notifications for designated meal times (e.g., Breakfast, Lunch, Dinner).
- **`RECEIVE_BOOT_COMPLETED`:** Allows the app to restore locally scheduled reminder alarms after your device is restarted, ensuring your chosen reminders continue without requiring you to manually open the app.
- **`VIBRATE`:** Allows your device to vibrate when a reminder notification fires, according to your system sound and vibration settings.
- **100% Local Scheduling:** All reminders are scheduled entirely on-device using Android's local alarm scheduler (`AlarmManager` / `NotificationManager`). DietGauge does not use Firebase Cloud Messaging (FCM), push notification servers, device push tokens, or remote tracking. If you disable meal reminders, all scheduled alarms are immediately canceled.

---

## Android Health Connect Integration & Data Disclosures

DietGauge provides optional, user-controlled integration with **Android Health Connect** (`androidx.health.connect.client`), allowing you to synchronize dietary intake and vital signs with your device's unified health ecosystem.

### Health Connect Permissions Requested & Purposes
When you enable Health Connect sync, DietGauge may request access to the following permissions:
- **`android.permission.health.READ_NUTRITION`:** Reads dietary nutrient records (calories, sodium, saturated fat, etc.) logged by other authorized apps on your device to prevent duplicate entries and provide comprehensive daily intake totals.
- **`android.permission.health.WRITE_NUTRITION`:** Writes nutrition data logged in DietGauge (calories, sodium, saturated fat, trans fat, dietary fiber, added sugars, cholesterol, and potassium) to Health Connect, allowing other compatible health apps to reflect your dietary intake.
- **`android.permission.health.READ_BLOOD_PRESSURE`:** Reads resting systolic and diastolic blood pressure measurements and pulse records from Health Connect (e.g., from connected blood pressure monitors or compatible health apps).
- **`android.permission.health.READ_WEIGHT`:** Reads body weight measurements from Health Connect (e.g., from smart scales or companion fitness apps).

### Compliance with Google Play Health Connect Policy & Limited Use Requirements
DietGauge strictly complies with the **Google Play Health Connect Policy**, including the **Limited Use Requirements**:
1. **Never Sold to Third Parties:** We do not sell, rent, lease, or monetize Health Connect data under any circumstances.
2. **Never Transferred to Third Parties or Developer Servers:** Health Connect data is accessed and processed strictly on your local device. It is never transferred to external servers, cloud databases, or third parties.
3. **Never Used for Advertising:** Health Connect data is never used or disclosed for personalized, retargeted, interest-based, or generalized advertising or marketing.
4. **Never Used for Artificial Intelligence / Machine Learning Training:** Health Connect data is never used to train machine learning models, artificial intelligence algorithms, or large language models.
5. **Used Solely for User-Facing Health Awareness:** All data accessed through Health Connect is used exclusively to provide and improve user-facing cardiovascular and dietary tracking features directly requested by the user.

### User Control, Transparency, and Revocation
- **Explicit User Control:** Health Connect integration is entirely optional and disabled by default. No health data is read from or written to Health Connect until you explicitly initiate synchronization.
- **Permission Management:** You can grant, deny, or revoke individual Health Connect permissions at any time directly in Android system settings (**Settings > Security & privacy > Privacy > Health Connect > App permissions > DietGauge**).
- **Data Deletion:** You can view, manage, and delete any data synchronized by DietGauge directly within the Android Health Connect management interface or by clearing DietGauge's local app storage.

---

## Food Search and Barcode Lookup (USDA FoodData Central & Open Food Facts)

When you look up nutritional data:
- **Text Search:** When you search for a food by name, your search query is sent via HTTPS to the **U.S. Department of Agriculture (USDA) FoodData Central** REST API to retrieve public-domain nutritional information.
- **Barcode Lookup:** When you scan a packaged food barcode, the app queries **USDA FoodData Central** and **Open Food Facts** (an open crowdsourced database made available under the Open Database License, ODbL v1.0) to retrieve product names and reported nutrient profiles.
- **Zero Personal Identifiers:** No user accounts, personal names, device identifiers, or tracking tokens are sent with search or barcode requests. As with any standard internet request, the third-party service receives the query and can see your device's IP address. For more details on their data handling, refer to the [USDA FoodData Central Privacy Policy](https://www.usda.gov/privacy-policy) and [Open Food Facts Privacy Policy](https://world.openfoodfacts.org/privacy).

---

## Voice Input & Speech Dictation (Zero Hardware Permissions)

When you choose to use optional voice search or daily note dictation:
- **System Intent Delegation:** DietGauge invokes Android's native system speech recognition intent (`RecognizerIntent.ACTION_RECOGNIZE_SPEECH`). Speech recognition is handled entirely by your device's operating system speech provider (such as Google Speech Services) under your device-level Android or Google privacy settings.
- **Zero Microphone Permissions (`RECORD_AUDIO`):** DietGauge does not declare, request, or hold the `android.permission.RECORD_AUDIO` hardware permission. Because speech recognition is executed by the system dialog, DietGauge never accesses your device's microphone hardware directly.
- **Zero Audio Capture, Streaming, or Storage:** DietGauge never receives, streams, intercepts, or stores raw audio data or recordings. We operate zero voice-processing servers; DietGauge receives solely the final transcribed text string via Android's standard activity result.
- **Strictly Opt-In:** Voice input shortcuts are disabled by default and can be enabled or disabled at any time in **Settings > Appearance & Display > Voice input & dictation**.

---

## Backup & Data Portability (100% Offline)

DietGauge allows you to export your complete health and nutrition history into a portable JSON backup file and restore it on another device or after reinstalling. Backup files are generated strictly on your device and shared only through user-directed actions via your device's system share sheet (such as saving to local storage, Google Drive, or sending via message/email). We operate no developer servers, accounts, or cloud databases; your backup files are never transmitted to us or any third party.

---

## Advertising & Tracking (100% Ad-Free)

The app is completely free, contains zero advertisements, and includes no third-party advertising SDKs, ad networks, or user tracking services. We do not use or collect Google Advertising IDs (AAID), device tracking identifiers, or usage analytics. DietGauge qualifies for European Union Digital Services Act (EU DSA) **Non-Trader** status.

---

## Health & Medical Boundaries (Not Medical Advice)

DietGauge is a passive tracking and awareness tool designed in accordance with FDA General Wellness guidance. It is not a medical device (Software as a Medical Device - SaMD) and does not diagnose, treat, cure, mitigate, prevent, or provide clinical management for hypertension, cardiovascular disease, kidney disease, or any other medical condition. Always follow the personalized guidance of your physician, cardiologist, or registered dietitian regarding your diet, nutrient limits, and medical care.

---

## Children's Privacy

DietGauge is not directed to children under 13 years of age, and we do not knowingly collect personal information from children.

---

## Changes to this Privacy Policy

If we update this privacy policy, the revised version will be published on this page with an updated "Last updated" date. You can review the authoritative live version at [https://ornexgen.github.io/dietgauge-privacy/](https://ornexgen.github.io/dietgauge-privacy/).

---

## Contact & Developer Information

If you have questions, feedback, or concerns regarding this privacy policy or DietGauge's data practices, please contact:

- **Developer:** OrNexGen (Publisher: `com.ornexgen.dietgauge`)
- **Email:** organizer.next.generation@gmail.com
- **Website & Privacy Policy:** [https://ornexgen.github.io/dietgauge-privacy/](https://ornexgen.github.io/dietgauge-privacy/)
