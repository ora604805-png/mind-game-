# MIND TRAP — starter project

A zero-cost, responsive HTML/CSS/JavaScript brain puzzle game. No framework or paid service is required for the local prototype.

## Included
- Mobile-first neon interface
- Solo, daily challenge and shareable score flow
- 12 starter puzzles with hints and explanations
- Score, streak, countdown timer and local best score (`localStorage`)
- PWA manifest + basic service worker for installation/offline caching
- Reserved banner-ad slot that does not cover gameplay
- Demo multiplayer room UI (not real network multiplayer yet)

## Run on Windows
1. Extract this ZIP to a folder, e.g. `C:\Projects\mind-trap`.
2. Open the folder in VS Code.
3. Install the VS Code extension **Live Server** (by Ritwick Dey), if not installed.
4. Right-click `index.html` → **Open with Live Server**.
5. Test the mobile layout with Chrome DevTools → device toolbar.

You can also run a local server if Python is installed:
```powershell
cd C:\Projects\mind-trap
py -m http.server 8000
```
Then open `http://localhost:8000`.

## Put it online for free
Deploy the folder to a static host such as GitHub Pages, Cloudflare Pages, or Netlify. For PWA installation/service worker, use HTTPS (static hosts provide it). Do not upload secrets or API keys into frontend files.

## Android app wrapper (free tools; Android Studio needed)
Use Node.js LTS and Android Studio. In a terminal opened inside this project:
```powershell
npm init -y
npm install @capacitor/core @capacitor/cli
npm install @capacitor/android
npx cap init "MIND TRAP" "com.example.mindtrap" --web-dir .
npx cap add android
npx cap open android
```
In Android Studio, wait for Gradle sync, choose an emulator or USB-connected Android phone, then press Run. For later web changes, run:
```powershell
npx cap sync android
```
Note: Capacitor may require a generated package.json and `webDir` setting. If `cap init` asks questions, use app name `MIND TRAP`, app ID `com.example.mindtrap`, and web directory `.`. For publishing, replace the example app ID with one you own before release.

## Important feature limits
- **Online multiplayer is only a UI/demo at this stage.** Real multiplayer requires a backend (for example Firebase Realtime Database/Firestore or Supabase), room synchronization, disconnect handling, abuse protection and testing. Never put admin/service keys in browser code.
- **Ads are placeholders only.** Apply to an ad network first; only insert its approved code after approval and ensure the placement follows the network's policies. Keep ads visually separate from answer buttons and do not click your own ads.
- **Viral growth is not guaranteed.** Add more original puzzles, test with real players, and improve based on completion and return rates.
- Puzzle text is a starter set. Review and expand the question bank before launch; use original questions and avoid unsupported claims such as “99% get it wrong.”

## Suggested next steps
1. Test the 5-question round on mobile and desktop.
2. Add 50–100 original puzzles and translations (English, Nepali, Hindi).
3. Add real backend-based online multiplayer.
4. Add privacy policy, contact page and age-appropriate content review before applying to an ad network.
