# Privacy, data handling, and clinical safety

## Prototype data

The current prototype stores entries in browser `localStorage` on the device/browser where they were entered. It does not currently send these entries to Firebase or another server. Anyone with access to the same browser profile/device may be able to view locally stored entries. Avoid entering names, contact details, medical record numbers, or real health readings during this milestone.

## Before a real-world release

- Complete a privacy and security review and publish a clear privacy notice.
- Collect only data that is necessary for a defined purpose.
- Implement authentication, account deletion, export, retention, and access controls.
- Test Firestore rules with authorized and unauthorized accounts.
- Use secure transport and review hosting/domain settings.
- Assess applicable local laws, institutional requirements, and health-data regulations.
- Have all health education content reviewed by a qualified clinician.
- Validate reminder behavior, time zones, device permissions, and failure states.

## Clinical boundaries

DM-Care is an educational and record-keeping support prototype. It is not a medical device or a substitute for a clinician's advice. It must not diagnose, prescribe, calculate insulin doses, or advise users to change prescribed medication. Medication reminders should repeat only the schedule and instructions entered by the user from their clinician's prescription. For urgent symptoms or suspected severe hypoglycemia/hyperglycemia, users should follow their clinician-provided emergency plan and seek urgent medical help as appropriate.
