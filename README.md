# Twin Tracker Helper

A simple single-page web app for tracking care tasks (feeds, nappies, temperatures, and expressed milk) for two children labeled **Twin 1** and **Twin 2**. The app stores entries in Firebase Firestore so multiple caregivers can keep information in sync.

## Prerequisites

- A Firebase project with Firestore enabled.
- Firestore rules that allow your intended access pattern (for quick testing you can use test rules, but production setups should be locked down appropriately).
- A static host or local web server to serve `Index.html`.

## Setup

1. **Create a Firebase project**
   - In the Firebase console, create a project and enable Firestore in native mode.
   - Add a web app to the project and copy the configuration values.

2. **Update the Firebase config in `Index.html`**
   - Locate the `firebaseConfig` object near the bottom of `Index.html`.
   - Replace the placeholder values (`YOUR_FIREBASE_API_KEY`, `your-project-id`, etc.) with the details from your Firebase project.
   - Optionally update `COLLECTION_NAME` to change the Firestore collection used for records (defaults to `careRecords`).

3. **Serve the page**
   - Open `Index.html` directly in a browser, or
   - Run a simple static server (for example, `python -m http.server 8000`) and visit `http://localhost:8000/Index.html`.

## Usage notes

- Select **Twin 1** or **Twin 2** before saving an entry.
- Use the built-in filters to review recent records or narrow by child and activity type.
- Feed timers and side recommendations rely on data stored in Firestore; if you clear the database, the recommendations reset.

## Security reminders

- Do not commit real Firebase credentials or sensitive caregiver notes to source control.
- Review Firestore security rules before deploying publicly to ensure data is protected for your family.
