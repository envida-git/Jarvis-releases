# Jarvis — a voice assistant for macOS

A J.A.R.V.I.S.-style assistant from *Iron Man*: it lives in the menu bar, listens for “Jarvis”, answers by voice and runs your Mac.

**Download:** [Jarvis.dmg](https://github.com/envida-git/Jarvis-releases/raw/main/Jarvis.dmg) — version 1.1.5.
Requirements: macOS 14 or later (recording your voice together with the screen needs macOS 15+), Apple Silicon or Intel.
Languages (speech and interface): English, Russian, Ukrainian — English by default, switch in Settings.

## What Jarvis can do

### 🎙 Voice and conversation
- Wakes up on “Jarvis” (or “Friday” — another persona), a double clap, or the **⌃⌥J** hotkey.
- One-phrase commands: “Jarvis, open Safari”, “Good morning, Jarvis”.
- Answers in the signature voice (Fish Audio) or a system voice; keeps listening after a reply without repeating the name.
- Interrupt mid-sentence: “stop”, “enough”, “wait”, “thanks, that's all”.
- “Only my voice” — other voices and the TV won't wake it.
- Personality: sarcasm 0–100 %, “sir” or “ma'am”.

### 🧠 Artificial intelligence
- Chain: Groq → Gemini → OpenRouter → Apple Intelligence → LM Studio; if one fails, the next one answers.
- Modes: Auto, Offline (on your Mac only), Online.
- Sees your screen: “what's on the screen?”, “what's this error?”, text from the screen and images.
- Memory: “remember that…”, “what do you know about me?”.

### 🖥 Mac, apps and windows
- Open / quit / minimize / restore apps, volume, brightness, music, desktops, keyboard layout.
- Browser tabs by voice: “switch to the mail tab”, “close the YouTube tabs”.
- “Tell me when it's downloaded”, “what's slowing my Mac down?”, day stats, presentation mode, wallpaper of the day.
- Window layouts: remembers windows on every desktop and display (including full-screen apps) and puts them back.

### ⌨️ Dictation and text
- Dictation mode types what you say into any field as you speak, with spoken punctuation (“comma”, “new line”).
- Translates selected text, reads aloud, summarizes the page.
- Chat window with history: messages grouped by day with timestamps, a slide-out list of past chats, “New chat”.
- Send files to the chat (attach, drag in, or paste ⌘V): Jarvis looks at images and reads PDFs, Word and text files.

### 🎬 Screen recording and screenshots
- **Screen recording to MP4** — “Record the screen” or **⌃⌥R**. Before recording, a panel lets you pick the whole screen, a window, a browser tab, an app or an area; turn your voice on or off; then a 3-2-1 countdown.
- A window keeps recording even on another desktop. While recording, a small panel shows the time, a microphone toggle and Stop. Jarvis never appears in the video.
- **Screenshot** — “Screenshot” or **⌃⌥S**: select an area, annotate with arrows, rectangles, circles, pen and text; copy or save.
- **Full web page** — “Screenshot of the page” or **⌃⌥P**: scrolls the active tab and stitches the whole page into one image.

### ⚡ Protocols and automation
- One-phrase scenarios: “work mode” opens apps and files, sites, sets the volume, arranges windows, says a phrase.
- Run by themselves on a schedule (“weekdays 9:00”) or on events: headphones, Wi-Fi, a display, charging, you're back at the Mac.
- Visual editor with drag-to-reorder steps; custom commands; macOS Shortcuts.
- Proactive: meetings, battery, morning briefing, stretch reminders, focus timer with a summary of what you missed.
- Meeting notes: records the call → transcript → a short summary with tasks.

### ✋ Gestures (camera)
- Cursor with your finger, pinch to click, scroll, volume by turning your hand, swipe between desktops, your own actions on palm, fist and circles.
- Trains on your hand; everything is recognized on the Mac, no photos are kept.

### 🎉 And more
- “Party protocol” — lights, lasers, music; a J.A.R.V.I.S. screensaver in three themes; Stark-style easter eggs.
- Custom-styled settings, hotkeys for every quick action, move all settings to another Mac in one file.

## Installation

1. Open `Jarvis.dmg` and drag **Jarvis** to Applications.
2. First launch: macOS warns that the app isn't from the App Store.
   Open **System Settings → Privacy & Security**, click **“Open Anyway”** at the bottom and enter your password.
   Or in Terminal: `xattr -dr com.apple.quarantine /Applications/Jarvis.app`
3. Allow access when macOS asks: **Microphone**, **Speech Recognition**, **Accessibility**.
   Optional: **Screen Recording** (recording, screenshots, screen analysis), **Camera** (gestures).

Updates arrive by themselves: Jarvis tells you about a new version — say “update yourself”.

## API keys (free)

Jarvis needs an AI key. On first launch it opens the Groq site and the settings window and explains everything by voice.

Settings window: the **◎** icon in the menu bar → **Settings…**.

| What | Where to get it | Where to paste it |
|---|---|---|
| **Groq** — main AI and accurate speech recognition (required unless you use Gemini) | [console.groq.com/keys](https://console.groq.com/keys) → sign in with Google → **Create API Key** → copy | Settings → **Artificial intelligence** → “Groq key” |
| **Gemini** — backup AI, sees the screen | [aistudio.google.com/apikey](https://aistudio.google.com/apikey) → **Create API key** | Settings → **Artificial intelligence** → “Gemini key” |
| **OpenRouter** — another backup AI (optional) | [openrouter.ai/keys](https://openrouter.ai/keys) → **Create Key** | Settings → **Artificial intelligence** → “OpenRouter key” |
| **Fish Audio** — Jarvis's signature voice (optional; without it — a system voice) | [fish.audio](https://fish.audio) → sign in → **API Keys** → create a key | Settings → **Voice** → “Fish Audio key” |

Click **Save** — changes apply immediately. A green check next to a field means the key is set.
Keys are stored only on your Mac: `~/.jarvis/config.json`.

## Where the AI runs

Answer order: **Groq → Gemini → OpenRouter → Apple Intelligence → LM Studio**.
Mode — Settings → Artificial intelligence: **Auto** (cloud, falls back to the Mac), **Offline** (Mac only), **Online** (cloud only).

**Apple Intelligence** — free, on your Mac, no internet. Needs macOS 26 on Apple Silicon.
Turn it on in **System Settings → Apple Intelligence & Siri** (Jarvis's settings have an “Enable” button).
Apple's model doesn't support Russian or Ukrainian yet — it works when Jarvis speaks English.

**LM Studio** — the last fallback: a local model on your Mac.
1. Install [LM Studio](https://lmstudio.ai/download) and open it once.
2. Jarvis Settings → Artificial intelligence → **LM Studio**: pick a model from the list or download one (“Popular” or a Hugging Face name/link).
   You need a model with tool support; with 16 GB of memory — models up to ~14B.
3. Jarvis starts the LM Studio server itself. The first answer can take up to a minute while the model loads.

## Getting started

Say **“Jarvis”** or press **⌃⌥J**. All commands: menu ◎ → **Help**.
Default hotkeys: ⌃⌥J — listen, ⌃⌥S — screenshot, ⌃⌥P — full-page screenshot, ⌃⌥R — screen recording. Change them in Settings → System.
