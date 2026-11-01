# ✦ Asterisk Cleaner

A simple, fast, and privacy-friendly web application that removes all `*` (asterisk) characters from text while preserving the original line breaks, spacing, and overall format.

Built with plain **HTML, CSS, and JavaScript** — no frameworks, backend, or external dependencies required.

## ✨ Features

**Cleaning (toggleable in ⚙️ Options, with presets)**
- Remove all `*` characters from any text or message — the original core rule
- Strip `#` heading markers, `_underscore_` emphasis, backticks & code fences, bullet markers, and flatten `[links](url)`
- Convert `**bold**` / `*italic*` to Unicode bold/italic letters that survive LinkedIn and other plain-text-only editors
- Strip invisible characters (zero-width chars, BOM, private-use citation glyphs) — emoji joiners and right-to-left marks are kept safe
- Punctuation clean-up (opt-in): curly quotes → straight, dashes → hyphens, `…` → `...`, non-breaking spaces → spaces
- Fix Cyrillic/Greek lookalike letters to Latin (opt-in; destructive for genuinely non-Latin text)
- One-click presets: **Default** · **Plain text** · **For messaging** · **For code**
- Live stat chips show exactly how many artifacts each rule removed

**Output & workflow**
- Preserve line breaks, spaces, and formatting
- Live preview in a fixed-height result panel that scrolls (vertically and horizontally for long lines) instead of expanding
- **Auto-copy** checkbox at the top of the page — copies the cleaned text automatically on every change while enabled
- **Paste & Clean** button — clipboard in, cleaned text copied back out, in one click
- One-click **Copy Result**, **Download .txt**, and **Share** (where the browser supports it)
- Session autosave — input, options, auto-copy flag, options panel, and theme restore on reload; stored only in your browser
- Character, word, and line counters for the input
- Keyboard shortcuts: `Ctrl/⌘+Alt+C` copy · `Ctrl/⌘+Alt+X` clear · `Ctrl/⌘+Shift+O` options
- Drag & drop `.txt` / `.md` files onto the input card to load them
- Dark / light theme — follows your system preference, switchable from the toolbar
- Installable as an app (PWA) with full offline support and a text share target
- Responsive design for desktop and mobile
- Works completely in the browser — no data is uploaded to a server

## 🖥️ Demo

Paste text such as:

```text
**Hello Amit!**

*This is an important message.*

Please remove *all asterisks* from this text.
```

The application produces:

```text
Hello Amit!

This is an important message.

Please remove all asterisks from this text.
```

## 🛠️ Tech Stack

- **HTML5** — page structure
- **CSS3** — styling, responsive layout, gradients, and UI
- **Vanilla JavaScript** — text processing and clipboard functionality

No npm packages or build tools are required.

## 📁 Project Structure

```text
asterisk-cleaner/
│
├── index.html              — the complete app (UI, styles, cleaning engine)
├── manifest.webmanifest    — PWA manifest (install, offline shell, share target)
├── sw.js                   — service worker for offline support
├── icon.svg                — app icon
├── plan.md                 — researched feature roadmap
└── Readme.md
```

## 🚀 Getting Started

### 1. Clone or download the project

Download the project files to your local machine.

### 2. Open the application

Simply open:

```text
index.html
```

in any modern web browser.

That's it. There is no setup or installation step.

### 3. Optional — install as an app / offline

Open the folder over http(s) (e.g. run `python3 -m http.server 8000` and visit
`http://localhost:8000`) and use your browser's **Install** option. The installed app:

- works with no internet connection, and
- can appear in your phone's share sheet ("Share text → Asterisk Cleaner").

Opening `index.html` directly still works fine — only the install/offline extras need a server.

## ⚙️ How It Works

The application removes every asterisk with a simple rule:

```javascript
return text.replace(/\*/g, "");
```

`clean(text, options)` now runs a pipeline of **toggleable rules** (invisible characters,
punctuation, markdown structure, emphasis pairs, Unicode conversion, and the asterisk sweep),
collecting per-rule counts that are shown as stat chips. Every rule is a pure function, so the
engine is easy to test and extend.

## 📋 Copy Functionality

The **Copy Result** button copies the cleaned text to the clipboard using the browser Clipboard API.

Alternatively, enable the **Auto-copy** checkbox at the top of the page: while it is checked, the cleaned text is copied to the clipboard automatically on every change.

The **Paste & Clean** button (shown when the browser allows clipboard reading) closes the loop: paste the
source from your clipboard, clean it, and the cleaned result is put straight on your clipboard for the
next paste.

A fallback method is also included for browsers or environments where the Clipboard API is unavailable.

## 🔒 Privacy

This application runs entirely on the client side.

Your text:

- Never leaves your browser
- Is not sent to an API
- Is not stored on a server
- Does not require an account
- Is only kept in your browser's local storage between sessions (typed text, options, and theme); clearing site data removes it permanently
- The service worker only caches the app's own files so it can load offline — it never transmits anything

## 📱 Responsive Design

The interface automatically adapts to smaller screens.

On desktop, the input and result panels appear side by side. On mobile devices, they stack vertically for easier use.

## 🌐 Browser Support

The application is designed for modern browsers such as:

- Google Chrome
- Mozilla Firefox
- Microsoft Edge
- Safari

## 💡 Possible Improvements

Some future enhancements could include:

- Remove Markdown formatting beyond asterisks
- Support for additional removable characters
- Export cleaned text as `.txt`
- Dark/light theme switcher
- Drag-and-drop text files
- Word and line counters
- Keyboard shortcuts
- PWA support for offline installation

## 📄 License

This project can be freely modified and used for personal or commercial purposes unless you choose to add a different license.

---

Made with ❤️ using HTML, CSS, and JavaScript.
