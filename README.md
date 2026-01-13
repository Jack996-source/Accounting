TJS Accounting – Android Installable (PWA) – Offline First

Why your old project made a .bat (batch) and not an Android app:
- The current code is a Python + Flask server packaged with PyInstaller for Windows.
- Android cannot run a Windows .exe/.bat.
- So to use it on a phone, we must make either:
  (A) a real Android APK app, or
  (B) a PWA (installable web app) that works offline.

This folder is option (B): PWA.
It works WITHOUT any Python server.
Data is saved locally on the phone using IndexedDB.

How to install on Android as an "app":
1) Upload the folder: Hikmatullah_PWA/static/ to any HTTPS hosting (Netlify, GitHub Pages, Firebase Hosting, etc.)
   - IMPORTANT: It must be HTTPS, otherwise Android will not allow installation as an app.
2) On the Android phone, open the website in Chrome.
3) Tap the menu (⋮) -> "Install app" (or "Add to Home screen").
4) Now it opens like a normal application and works offline.

Offline behavior:
- After first opening (one time), the app caches all files.
- Then you can use it with NO internet.

Where data is stored:
- Locally on the phone/browser (IndexedDB). This is private to that device.
- If you want cloud sync between devices, we can add it later.

Files changed from your original version:
- static/app.js is rewritten to NOT call /api/... anymore.
- It stores items locally and calculates Day/Week/Month/Year totals locally.

If you still want a real APK:
- The fastest method is to wrap this PWA into an Android APK using "Trusted Web Activity" or a simple Android WebView.
- Tell me and I will generate that Android project too.
