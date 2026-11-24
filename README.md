# DM-Care — independent diabetes-support app

A bilingual (Arabic/English), responsive starter project for people living with Type 1 or Type 2 diabetes.

> **Important status:** this ZIP contains the working front-end demo and the separate Firebase/GitHub setup files. The current app stores entries in the browser (`localStorage`). Firebase Authentication and Firestore are **not connected yet**. Do not enter real patient information until authentication, database rules, privacy review, and testing are completed.

## Project independence

Create a **new GitHub repository** and a **new Firebase project** for DM-Care. Do not use, import, overwrite, or change MedGuard-JO files, repositories, Firebase projects, credentials, or settings.

## What is included

- `public/index.html` — bilingual app prototype with dashboard, glucose log, medication reminders, symptom/event log, education, profile/settings, CSV export, and browser-local demo storage.
- `firebase.json` — Firebase Hosting and Firestore configuration.
- `firestore.rules` — owner-only Firestore access rules for a future `users/{uid}` data structure.
- `firestore.indexes.json` — currently empty index definition file (add indexes only when required by queries).
- `firebase-config.example.js` — safe placeholder template for Firebase web-app configuration; it is not a secret and contains no real project credentials.
- `.firebaserc.example` — example project alias file; replace the placeholder only after creating the new Firebase project.
- `.gitignore` — excludes local secrets and generated files.
- `docs/SETUP_GITHUB.md` — GitHub repository and Pages instructions.
- `docs/SETUP_FIREBASE.md` — separate Firebase project setup and deployment instructions.
- `docs/TEST_CHECKLIST.md` — functional, usability, and safety test checklist.
- `docs/PRIVACY_AND_SAFETY.md` — privacy and clinical-safety notes.

## Quick start

1. Extract this ZIP.
2. Create a new, empty GitHub repository named `DM-Care` (or another unused name).
3. Upload the **contents** of this folder to the repository root. Keep `public/` as a folder.
4. Follow `docs/SETUP_GITHUB.md` to publish using GitHub Pages, or use Firebase Hosting after completing the Firebase setup.
5. Test using demo data only.

## Local preview

You can open `public/index.html` directly in a browser. For a local web server, from this folder run:

```bash
python -m http.server 8000 -d public
```

Then open `http://localhost:8000`.

## Current limitations

- No Firebase connection, account sign-in, cloud sync, push notifications, or background reminder delivery is implemented in this milestone.
- Browser reminders and local storage are limited by the browser/device and may not run when the app is closed.
- The app does not diagnose, calculate insulin doses, recommend medication changes, or replace professional medical care.
- The education content is general and should be reviewed by a qualified diabetes-care professional before public release.
