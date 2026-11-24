# Firebase setup for DM-Care

Use only the independent Firebase project `dm-care-47739`. Never select or change MedGuard-JO.

## Already configured in this project

- Firebase Web App: `DM-Care-Web`
- Authentication: Email/Password enabled
- Cloud Firestore database created
- Owner-only Firestore rules prepared in `firestore.rules`
- `public/index.html` imports Firebase JavaScript SDK 13.4.0 and uses the DM-Care Web App configuration

## Verify Firebase settings

1. Open the Firebase Console and select project `dm-care-47739`.
2. Go to **Authentication → Settings → Authorized domains**.
3. Add the exact hostname used by the published GitHub Pages site (for example, `your-account.github.io`; do not include `https://` or a path). Keep `localhost` only if you use it for local testing.
4. Go to **Firestore Database → Rules** and confirm the published rules match the project's `firestore.rules` file. They must allow authenticated users to access only `users/{their-own-uid}/...` and deny all other paths.
5. Confirm **Authentication → Sign-in method → Email/Password** remains enabled.

## Firestore data structure

- `users/{uid}/readings/{recordId}`
- `users/{uid}/meds/{recordId}`
- `users/{uid}/events/{recordId}`
- `users/{uid}/profile/main`

The client gets the UID from Firebase Authentication. Never loosen the rules to `allow read, write: if true`.

## Deploying rules (optional computer workflow)

If using Firebase CLI from the project root:

```bash
npm install -g firebase-tools
firebase login
firebase use --add
firebase deploy --only firestore:rules
```

When prompted, select `dm-care-47739` and verify the project ID before deployment. GitHub Pages can continue hosting the static frontend; Firebase Hosting is not required for the current setup.

## Privacy and testing

Use fictional test information until the app passes the checklist. Create two separate test accounts and verify that neither account can see or alter the other's records. Never upload a service-account key or Admin SDK credential to GitHub. The Firebase Web App config in `public/index.html` is client configuration, not a private key.
