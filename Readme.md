# ✦ Asterisk Cleaner

A simple, fast, and privacy-friendly web application that removes all `*` (asterisk) characters from text while preserving the original line breaks, spacing, and overall format.

Built with plain **HTML, CSS, and JavaScript** — no frameworks, backend, or external dependencies required.

## ✨ Features

- Remove all `*` characters from any text or message
- Preserve line breaks, spaces, and formatting
- Live preview of the cleaned text
- Show the number of characters in the input
- Show how many asterisks were removed
- One-click **Copy Result** button
- **Clear** button to reset the input
- Responsive design for desktop and mobile
- Works completely in the browser
- No data is uploaded to a server

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
├── asterisk-cleaner.html
└── README.md
```

## 🚀 Getting Started

### 1. Clone or download the project

Download the project files to your local machine.

### 2. Open the application

Simply open:

```text
asterisk-cleaner.html
```

in any modern web browser.

That's it. There is no setup or installation step.

## ⚙️ How It Works

The application removes every asterisk using JavaScript:

```javascript
function cleanText(text) {
  return text.replace(/\*/g, "");
}
```

The `/\*/g` regular expression finds every `*` character in the input and replaces it with an empty string.

Because the replacement only targets the asterisk character, other text, whitespace, and line breaks remain unchanged.

## 📋 Copy Functionality

The **Copy Result** button copies the cleaned text to the clipboard using the browser Clipboard API.

A fallback method is also included for browsers or environments where the Clipboard API is unavailable.

## 🔒 Privacy

This application runs entirely on the client side.

Your text:

- Never leaves your browser
- Is not sent to an API
- Is not stored on a server
- Does not require an account

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
