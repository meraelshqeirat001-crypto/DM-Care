# Create a separate Firebase project for DM-Care

Do this only in a **new Firebase project**. Do not select or modify MedGuard-JO.

## A. Create the project and Web App

1. Open https://console.firebase.google.com/ .
2. Choose **Add project** and name it `DM-Care` (or `dm-care` if the project ID requires lowercase).
3. Complete the project wizard. Analytics is optional for this prototype; leave it off unless there is a clear need and an appropriate privacy notice.
4. In the new project, choose **Add app → Web** and register the app as `DM-Care Web`.
5. Copy the Firebase web configuration into a private working copy of `firebase-config.example.js`, saved as `firebase-config.js`. The example file is only a template. Do not send passwords, service-account keys, or private credentials in chat.

## B. Enable sign-in and Firestore

1. Open **Build → Authentication → Get started**.
2. Under **Sign-in method**, enable **Email/Password**.
3. Open **Build → Firestore Database → Create database**.
4. Choose a location appropriate for your users and data-residency requirements. The database location cannot easily be changed later.
5. Start in production mode. Do not use open/test rules for real patient data.
6. Review `firestore.rules`. It restricts access to a signed-in user under `users/{uid}/...` and denies everything else. Deploy it only after reviewing the data model and testing with the Firebase Emulator or test accounts.

## C. Deploy Firebase Hosting and rules (computer recommended)

Install Node.js, then install the Firebase CLI:

```bash
npm install -g firebase-tools
firebase login
```

From the extracted `DM-Care-project` folder:

```bash
cp .firebaserc.example .firebaserc
```

Edit `.firebaserc` and replace `YOUR_NEW_DM_CARE_FIREBASE_PROJECT_ID` with the project ID of the **new DM-Care project**. Then run:

```bash
firebase use --add
firebase deploy --only hosting,firestore:rules
```

When asked to choose a project, select the new DM-Care project. Confirm the project ID carefully before deployment.

## D. Important integration status

The supplied `public/index.html` is still a local-storage demo and does not import or use the Firebase configuration. Creating a Firebase project or deploying the rules does not automatically connect the app to Authentication or Firestore. That integration is a separate development step and must be tested before storing real user data.

## Security reminders

- Firebase web config is intended to be present in a client app; it is not a substitute for security rules.
- Never place service-account JSON, private keys, passwords, or Admin SDK credentials in the `public` folder or GitHub.
- Do not collect real patient information during prototype testing.
