# Bro — Personal AI Assistant for Android 🤖📱

A personal AI voice assistant customized for your Android phone, powered by **Google Gemini 1.5 Flash**, the **Web Speech API**, and **Android Foreground Wake Word Service**.

---

## 🌟 Highlights

- **Name & Persona:** **Bro** — friendly, intelligent, cool, loyal, and proactive companion. Fluent in both English and Telugu/Teluglish.
- **Wake Words:**
  - Say `"Hey Bro"`, `"Bro"`, `"హాయ్ బ్రో"`, or `"బ్రో"`.
  - Say `"Stop Bro"` or `"ఆపు Bro"` to pause.
- **Dual Mode Deployment:**
  1. **Instant PWA (Progressive Web App):** Open in mobile Chrome, tap *Add to Home Screen*, and use immediately (no laptop or Android Studio required).
  2. **Native Android APK:** Build the `android/` project for background foreground listening and hardware integration.
- **Privacy & Safety:**
  - API keys are stored locally on your device in browser `localStorage`.
  - Actions and tools are explicit and confirmation-gated.

---

## 🚀 Quick Start (Instant Mobile Setup)

### 1. Get a Free Gemini API Key
1. Go to [Google AI Studio](https://aistudio.google.com/).
2. Click **Create API Key**.
3. Copy your key (starts with `AIza...`).

### 2. Run / Host the Frontend
- **Option A (GitHub Pages / Vercel):**
  1. Push the `frontend/` directory to your GitHub repository.
  2. In GitHub, go to **Settings > Pages > Branch: `main` / Folder: `/frontend`** and save.
  3. Or import the repository into [Vercel](https://vercel.com) with root directory set to `frontend`.
- **Option B (Local Test in Chrome):**
  Open `frontend/index.html` directly in Google Chrome.

### 3. Install on Your Android Phone
1. Open your hosted frontend URL (e.g., `https://your-username.github.io/bro-ai-assistant/` or Vercel URL) in Chrome on Android.
2. Tap the three dots menu (**⋮**) in Chrome.
3. Select **"Add to Home Screen"** or **"Install App"**.
4. The **Bro** app icon will appear on your phone home screen!
5. Tap **Settings (⚙️)** inside the app, paste your **Gemini API Key**, and tap **Save**.
6. Tap the microphone icon or say your voice query!

---

## 🛠️ Native Android APK Build (For Background Wake Word)

If you want Bro to listen in the background while your screen is on:
1. Open the `android/` directory in **Android Studio**.
2. In `android/app/build.gradle.kts`, set your default `JARVIS_START_URL` to your hosted frontend URL.
3. Connect your Android phone via USB (or wireless debugging).
4. Build and install: `Build > Build Bundle(s) / APK(s) > Build APK(s)`.
5. Open the app on your phone, grant Microphone permission, and tap **Enable Wake Word**.
6. Bro will run a foreground notification service and respond whenever you say **"Hey Bro"**!

---

## 📂 Project Directory Structure

```text
bro-ai-assistant/
├── frontend/             # Mobile PWA client (HTML, CSS, JS, manifest.json)
│   ├── index.html        # App interface & chat UI
│   ├── script.js         # Voice recognition, TTS, and Gemini API caller
│   ├── style.css         # Cyberpunk/modern dark UI styling
│   └── manifest.json     # PWA configuration for Android installation
├── backend/              # Node.js / Express private gateway
│   ├── server.js         # API endpoint router & health checks
│   ├── interaction-brain.js # Conversational guidance & emotion handling
│   └── everyday-tools.js # Built-in utilities (weather, time, coin, password)
├── android/              # Native Android wrapper project
│   ├── app/src/main/java/com/growthos/jarvis/
│   │   ├── MainActivity.java           # WebView shell & JS bridge
│   │   ├── WakeWordService.java        # Background speech recognizer for "Hey Bro"
│   │   └── AdvancedIntelligenceBridge.java # Screen & camera hardware bridge
└── README.md
```
