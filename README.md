# LinkedIn Login Loop Fixer 🐛🚀

A lightweight Chrome Extension (Manifest V3) built to resolve the infinite loading loop issue on the LinkedIn guest login page.

## 🔴 The Problem

When users attempt to log in to LinkedIn from the guest homepage navigation bar, they are redirected to a specific sub-path containing tracking parameters:
`https://www.linkedin.com/login/in/?trk=guest_homepage-basic_nav-header-signin`

Due to a routing or middleware mismatch on the platform side, this specific URL triggers an **infinite loading loop** (endless spinner/blank screen). However, the standard login path (`https://www.linkedin.com/login/`) works perfectly fine.

## 🟢 The Solution

This extension acts as a temporary workaround while waiting for the official fix from the LinkedIn engineering team. It utilizes Chrome's modern `declarativeNetRequest` API to instantly detect the broken `/login/in/` pattern and seamlessly redirect the user to the working `/login/` path, preserving a smooth user experience.

## 🛠️ Features

- **Manifest V3 Compliant:** Built using the latest extension standards.
- **Ultra-Lightweight:** Zero background scripts running constantly; uses declarative rules.
- **Privacy-Focused:** Does not track, read, or store any user data or credentials.

## 📂 Project Structure

```text
├── manifest.json   # Extension configuration & permissions
└── rules.json      # Declarative routing redirection logic

```

## 🚀 How to Install (Local Development Mode)

Since this is a quick patch and open-source workaround, you can load it manually into your browser:

1. **Clone or Download** this repository to your local machine.
2. Open Google Chrome (or any Chromium-based browser like Brave, Edge, or Opera).
3. Navigate to `chrome://extensions/`.
4. Enable **Developer mode** by toggling the switch in the top-right corner.
5. Click the **Load unpacked** button in the top-left corner.
6. Select the folder containing the `manifest.json` and `rules.json` files.
7. Done! Try navigating to the broken LinkedIn link, and it will now automatically redirect and load instantly.

## 📝 Disclaimer

*This project is an independent open-source workaround and is not affiliated, associated, authorized, endorsed by, or in any way officially connected with LinkedIn Corporation or Microsoft.*
