# Project SHUBHRA PWA V0.1

## GitHub Pages (Android-only setup)
1. GitHub par ek **public repository** banayein, jaise `project-shubhra`.
2. ZIP extract karke **andar ki saari files aur `icons` folder** repository root mein upload karein. Root par `index.html`, `style.css`, `app.js`, `manifest.webmanifest`, `sw.js`, `.nojekyll`, aur `icons/` dikhne chahiye.
3. Repository → **Settings → Pages** → Build and deployment: **Deploy from a branch** → Branch `main`, folder `/(root)` → Save.
4. Deployment complete hone par URL is pattern ka hoga: `https://YOUR-USERNAME.github.io/REPOSITORY-NAME/` (placeholders apne actual username/repository se badlein).
5. Android Chrome mein URL kholein. Microphone permission allow karein. Install button na dikhe to Chrome menu (⋮) → **Install app** ya **Add to Home screen**.
6. HTTPS URL par test karein. `index.html` ko local file ki tarah kholne se microphone aur service worker kaam na karein.

## APK banane ka agla step
GitHub Pages website host karta hai; woh APK compile nahi karta.
1. Pehle PWA ko publish karke test karein.
2. `https://www.pwabuilder.com/` par apna public HTTPS URL dein.
3. PWA report check karein, Android package workflow follow karein; app ID, icons aur signing details maangi ja sakti hain.
4. Signing key/password private rakhein—public GitHub repository mein kabhi upload na karein. Generated APK ko install karke test karein. Requirements badal sakti hain; APK/AAB ke liye extra signing/packaging steps ho sakte hain.

## Compatibility
- Voice input `SpeechRecognition` / `webkitSpeechRecognition` par depend karta hai; browser/device/region/language aur network ke hisaab se support badalta hai. Browser recognition audio ko provider service tak bhej sakta hai.
- Voice output `speechSynthesis` zyada browsers mein milta hai, lekin Hindi voice Android TTS settings mein enable karni pad sakti hai.
- Offline cache app shell ko first successful online visit ke baad load kar sakta hai; voice recognition offline kaam karna guaranteed nahi.
- Is demo mein fixed replies hain, generative AI nahi. Chat refresh ke baad save nahi hoti.

## Quick tests
- Type `नमस्ते`, `समय बताओ`, `आज की तारीख बताओ`.
- Mic permission ke saath Hindi mein bolkar test karein.
- Permission deny karein aur confirm karein ki typing phir bhi chale.
- First online load ke baad reload/offline behaviour check karein.
