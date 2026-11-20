# Circle – friends chat & stories

A static web app (no build step) with friend requests, QR add, chat, and 24-hour stories.
Hosted free on **GitHub Pages**; backend is **Firebase** (Google sign-in + Firestore, free Spark plan).

## 1. Firebase setup (5 min)
1. Go to https://console.firebase.google.com → **Add project**.
2. **Build → Authentication → Get started → Google** → enable.
3. **Build → Firestore Database → Create database** (production mode).
4. Firestore → **Rules** tab → paste the contents of `firestore.rules` → **Publish**.
5. **Project settings → Your apps → Web (`</>`)** → register app → copy the config into `firebase-config.js`.

## 2. Create the GitHub repo
1. github.com → **New repository** → name it (e.g. `circle`), Public → **Create**.
2. **Add file → Upload files** → drag in `index.html`, `firebase-config.js`, `firestore.rules`, `README.md` → **Commit**.
3. **Settings → Pages → Source: Deploy from a branch → `main` / `(root)` → Save.**
4. Your site appears at `https://<username>.github.io/<repo>/` after about a minute.

## 3. Allow your domain to sign in
Firebase → **Authentication → Settings → Authorized domains → Add domain** → `<username>.github.io`.

## Notes
- Stories are hidden after 24h in the UI; they stay in Firestore until deleted.
- The camera QR scanner needs HTTPS (GitHub Pages provides it).
