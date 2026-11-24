# DM-Care — diabetes support app

DM-Care is an independent, bilingual (Arabic/English), responsive app for people living with Type 1 or Type 2 diabetes.

## Firebase integration included

- Firebase Authentication: email/password account creation, sign-in, sign-out, and password reset.
- Cloud Firestore: each authenticated user's readings, medication reminders, symptom/event records, and profile are stored under that user's Firebase UID.
- Guest mode: optional local-only demo data, separate from cloud accounts.
- Arabic/English interface and the existing dashboard, glucose log, medication reminders, symptom log, education, profile, and CSV export are retained.

## Project separation

This project uses only the separate Firebase project `dm-care-47739`. Do not import or modify MedGuard-JO files, repositories, Firebase projects, or credentials.

## Files

- `public/index.html` — complete app and Firebase client integration.
- `firestore.rules` — owner-only access to `users/{uid}/...`; deny all other paths.
- `firebase.json` and `firestore.indexes.json` — Firebase deployment configuration.
- `docs/SETUP_GITHUB.md` — GitHub Pages steps.
- `docs/SETUP_FIREBASE.md` — Firebase setup and authorized-domain steps.
- `docs/TEST_CHECKLIST.md` — account isolation and functional checks.
- `docs/PRIVACY_AND_SAFETY.md` — privacy and clinical-safety notes.

## Before using real patient data

The frontend is connected to the DM-Care Firebase Web App configuration, but the deployed site must still be tested. Confirm Email/Password is enabled, publish the owner-only Firestore rules, add the exact GitHub Pages hostname to Firebase Authentication's Authorized domains, and test with two separate accounts. Use test data until all checks pass and the privacy/security review is complete.

Firebase web configuration (including the API key) is designed to be present in client-side apps. It is not a secret and does not grant database access by itself; Firestore Security Rules and Authentication enforce access. Never place service-account JSON, Admin SDK credentials, or private keys in this repository.

## Data model

- `users/{uid}/readings/{recordId}`
- `users/{uid}/meds/{recordId}`
- `users/{uid}/events/{recordId}`
- `users/{uid}/profile/main`

The app derives `{uid}` from the authenticated Firebase user; it does not accept a UID from user input.

## Important limitations

- Medication entries are reminders only; the app does not calculate or change doses.
- No push notifications or guaranteed background reminder delivery are implemented.
- The app does not diagnose, recommend treatment changes, or replace professional medical care.
- Guest-mode data remains on the current browser/device and does not sync.
