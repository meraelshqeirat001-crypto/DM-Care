# DM-Care test checklist

Use fictional test data only until all checks pass.

## Authentication

- [ ] New user can create an account with email and password (minimum 6 characters).
- [ ] Existing user can sign in.
- [ ] Incorrect credentials show an understandable error.
- [ ] Password reset email can be requested.
- [ ] User can sign out and the app returns to the sign-in screen.
- [ ] Signed-in session is restored after reloading the page.
- [ ] Guest mode works without cloud access and is clearly marked as local-only.

## Cloud records

- [ ] Save a fasting glucose reading and confirm it appears after reload.
- [ ] Save a post-meal and random reading.
- [ ] Save a medication reminder and confirm the prescribed dose is only displayed as entered.
- [ ] Save and delete a symptom/event.
- [ ] Save profile settings and confirm they persist.
- [ ] Export readings to CSV.
- [ ] Confirm sign-out does not leave the previous user's data visible on screen.

## Account isolation and rules

- [ ] Create test account A and add a unique reading.
- [ ] Sign out, create/sign in to test account B, and confirm A's reading is not visible.
- [ ] Add a unique reading to B, sign back into A, and confirm B's reading is not visible.
- [ ] Confirm Firestore rules are owner-only and deny unauthenticated access.
- [ ] Confirm the exact GitHub Pages hostname is listed in Firebase Authentication Authorized domains.

## Safety and privacy

- [ ] No insulin dose calculation or treatment recommendation is present.
- [ ] Emergency notice is visible in the symptom section.
- [ ] Use test data only until privacy/security review and clinical content review are complete.
- [ ] Verify the app does not expose one user's data to another account.
