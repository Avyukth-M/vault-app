# 🔐 Vault — Local Password Manager

> A secure, minimal, and beautiful password manager that runs entirely in your browser. No cloud. No account. No tracking. Just your passwords, encrypted on your device.

![Vault App](screenshots/home.png)

---

## ✨ Features

- **AES-256 Encryption** — All credentials are encrypted using AES-GCM with a key derived from your master PIN via PBKDF2 (200,000 iterations). Your data is unreadable without the correct PIN.
- **100% Local** — Everything is stored in your browser's localStorage. Nothing ever leaves your device.
- **No Account Required** — No sign-up, no email, no server.
- **Auto-Lock** — Vault automatically locks after 5 minutes of inactivity.
- **Failed Attempt Lockout** — Locks for 2 minutes after 5 incorrect PIN attempts.
- **Password Generator** — Generate strong 18-character passwords instantly.
- **Password Strength Indicator** — Visual feedback as you type a password.
- **Categories** — Organize entries into Social, Work, Banking, Email, Shopping, Games, and Other.
- **Grid Layout** — Adjustable 2, 3, 4, or 5 column grid view.
- **Last-Used Timestamps** — See when you last accessed each entry.
- **URL Field** — Store the direct login URL separately from the site name, clickable from the detail view.
- **Light / Dark / Auto Theme** — Follows your system preference or set it manually.
- **PWA Ready** — Installable on Android and iOS as a home screen app.
- **Offline Support** — Works fully without an internet connection.

---

## 📸 Screenshots

| Vault Grid | Entry Detail | Add Entry |
|---|---|---|
| ![Grid](screenshots/grid.png) | ![Detail](screenshots/detail.png) | ![Form](screenshots/form.png) |

---

## 🚀 Getting Started

### Run locally

```bash
# Clone the repo
git clone https://github.com/yourusername/vault-app.git
cd vault-app

# Install dependencies
npm install

# Start the app
npm start
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

### Build for production

```bash
npm run build
```

The `build/` folder contains the production-ready app.

---

## 🗂 Project Structure

```
vault-app/
├── public/
│   ├── index.html          # HTML entry point with PWA meta tags
│   ├── manifest.json       # PWA manifest
│   ├── service-worker.js   # Offline caching
│   └── icons/              # App icons (72px to 512px)
├── src/
│   ├── App.jsx             # Main Vault component
│   └── index.js            # React entry point
└── README.md
```

---

## 🔒 Security Model

| What | How |
|---|---|
| Encryption | AES-256-GCM |
| Key derivation | PBKDF2 — SHA-256, 200,000 iterations, random salt |
| PIN storage | Never stored — only a SHA-256 hash of `salt + pin` |
| Data storage | Browser localStorage (encrypted blob only) |
| Network requests | None — fully offline |
| Auto-lock | After 5 minutes of inactivity |
| Brute-force protection | 2-minute lockout after 5 failed attempts |

> ⚠️ **Important:** If you forget your master PIN, your vault cannot be recovered. There is no reset option by design.

---

## 🛠 Built With

- [React](https://react.dev) — UI framework
- [Web Crypto API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Crypto_API) — AES-256 encryption & PBKDF2 key derivation
- [localStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage) — Local encrypted storage
- [Inter](https://fonts.google.com/specimen/Inter) — Typography

No external dependencies beyond React itself.

---

## 📱 Install as an App (PWA)

### Android
1. Open the hosted app in **Chrome**
2. Tap the menu (⋮) → **"Add to Home screen"**
3. Vault installs like a native app

### iOS
1. Open the hosted app in **Safari**
2. Tap the Share button → **"Add to Home Screen"**
3. Tap **Add**

---

## 🌐 Deploy for Free

### Vercel
```bash
npm install -g vercel
npm run build
vercel --prod
```

### Netlify
```bash
npm run build
# Drag and drop the build/ folder at app.netlify.com
```

### GitHub Pages
```bash
npm install gh-pages --save-dev
# Add to package.json scripts:
# "deploy": "gh-pages -d build"
npm run build
npm run deploy
```

---

## 🤝 Contributing

Contributions are welcome! Feel free to:

- 🐛 Report bugs by opening an issue
- 💡 Suggest features in the discussions tab
- 🔧 Submit a pull request

### To contribute
```bash
git checkout -b feature/your-feature-name
# make your changes
git commit -m "Add: your feature description"
git push origin feature/your-feature-name
# open a Pull Request on GitHub
```

---

## 📋 Roadmap

- [ ] Export vault to encrypted JSON file
- [ ] Import vault from backup file
- [ ] Password history (last 3 passwords per entry)
- [ ] Biometric unlock (Face ID / Fingerprint via WebAuthn)
- [ ] Duplicate entry detection
- [ ] Keyboard shortcuts
- [ ] Favorite / pinned entries

---

## 📄 License

MIT License — free to use, modify, and distribute.

---

## 🙏 Acknowledgements

Inspired by the need for a simple, trustworthy password manager that doesn't require handing your data to a third party.

---

<p align="center">Built with ❤️ — No cloud. No tracking. Just yours.</p>
