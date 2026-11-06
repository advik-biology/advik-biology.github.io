# Advik Biology Notes Library — Firebase starter

This starter includes student sign-in, Viewer/Member/Admin roles, an admin notes editor, and Firestore security rules.

## Configure Firebase
1. Create a Firebase project and register a Web app.
2. Enable **Authentication > Email/Password**.
3. Create a **Cloud Firestore** database.
4. Paste the Firebase web config into `index.html` in `firebaseConfig`.
5. Publish `firestore.rules` in Firebase Console > Firestore Database > Rules.
6. Set up your own account as Admin in Firestore: after signing up, find your user document in `users` (document ID = your Firebase Auth UID) and change `role` from `viewer` to `admin`.
7. Publish `index.html` to GitHub Pages.

## Role meaning
- `viewer`: can read signed-in free notes.
- `member`: can read free notes and Crash Course notes.
- `admin`: can read all notes and manage notes and student roles.

Admin sets a student's `role` to `member` only after payment is verified. This starter does not process payments automatically.

## Important security note
The Firestore rules protect note documents. If you use PDF files, do not put paid PDFs at public GitHub Pages URLs. Store them in Firebase Storage with Storage rules that enforce the same roles, or use short-lived authenticated downloads. The HTML interface alone is not a security boundary.

This is a starter code package; Firebase project setup and admin UID configuration must be completed before it works online.
