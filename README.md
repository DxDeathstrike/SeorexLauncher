<div align="center">


<img src="https://github.com/user-attachments/assets/7e2fc181-b437-4b47-99cb-f0f132e4d1ee" alt="SeorexTech Logo" width="80" />

# SeorexTech Launcher

**A modular desktop launcher for everything SeorexTech.**

Install the tools you want. Launch them like apps. Stay current automatically.

[![Version](https://img.shields.io/badge/version-1.0.0-blue?style=flat-square)](https://github.com/DxDeathstrike/SeorexLauncher/releases)
[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey?style=flat-square)](#)
[![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)](LICENSE)

</div>

---

## What is it?

SeorexTech Launcher is a single app that houses all SeorexTech tools. Browse and install tools as modules, launch them in one click, and receive updates automatically - no manual downloads required.

---

## Download & Install

1. Go to the [**Releases page**](https://github.com/DxDeathstrike/SeorexLauncher/releases).
2. Download the latest installer for your platform:
   - **Windows** - `SeorexTech-Launcher-Setup-x.x.x.exe`
   - **macOS** - `SeorexTech-Launcher-x.x.x.dmg`
   - **Linux** - `SeorexTech-Launcher-x.x.x.AppImage`
3. Run the installer. The launcher installs to your user folder — no admin rights needed.

> **Python:** Some modules use Python features. The launcher automatically installs Python 3.12 silently on first use via winget - no manual setup needed on Windows.

---

## Features

| Feature | Description |
|---|---|
| **Module system** | Install tools as modules. Enable, disable, or remove them at any time without affecting the launcher. |
| **Library** | All your installed and enabled modules in one place - launch any tool with one click. |
| **Download manager** | Queue, pause, resume, and cancel downloads with live progress. |
| **Auto-updater** | The launcher checks for updates on startup and downloads them silently in the background. |
| **Authentication** | Secure email-based login - enter your email, get a code, you're in. |
| **Ban system** | Banned accounts are blocked at login with a toast notification. Attempts are logged and reported via Discord. |
| **Python auto-install** | Python 3.12 is installed silently via winget on first use - no manual setup required. |

---

## Getting Started

1. **Sign in** — Enter your email on the login screen. You'll receive a 6-digit code; enter it to access the launcher. Your session stays active for 30 days.

2. **Browse modules** — Open the **Modules** page to see available tools.

3. **Install a module** — Click **+ Install Module** and select a `.zip` module file. The launcher extracts and registers it automatically.

4. **Enable and launch** — Toggle a module on in the **Modules** page, then go to **Library** and click **Launch**.

5. **Manage downloads** — The **Downloads** page shows active and queued downloads with pause/resume/cancel controls.

6. **Updates** — The **Updates** page shows the latest release notes. Updates download and install silently; you'll be prompted to restart when ready.

---

## Installing a Module (ZIP format)

Modules distributed as `.zip` files can be installed directly from the **Modules** page. A valid module ZIP contains at minimum:

```
my-module.zip
├── manifest.json      (required)
├── index.html         (required)
├── style.css          (optional)
└── module.js          (optional)
```

The `manifest.json` must look like this:

```json
{
  "id": "my-module",
  "name": "My Module",
  "version": "1.0.0",
  "description": "Shown in the launcher library.",
  "entry": "index.html",
  "enabled": true,
  "author": "SeorexTech"
}
```

> Make sure `manifest.json` is at the **root** of the ZIP, not inside a subfolder.

If the module lists Python dependencies (`pythonDeps`), the launcher installs them automatically via `pip` on first use.

---

## Updates

The launcher updates itself automatically:

- On startup it checks [GitHub Releases](https://github.com/DxDeathstrike/SeorexLauncher/releases) for a newer version.
- If one is found, it downloads in the background.
- A **Restart to update** prompt appears when the download is complete — click it to apply the update instantly.

You can also check manually any time on the **Updates** page.

---

## Troubleshooting

**The launcher won't open after install**
- On Windows, try right-clicking the desktop shortcut and selecting *Run as administrator* once. After that it should open normally.

**A module shows "failed to load"**
- Make sure the module ZIP has `manifest.json` at its root, not nested inside a folder.
- Re-install the module from the Modules page.

**Python tools aren't working**
- The launcher auto-installs Python 3.12 via winget. If it still fails, open a terminal and run `python --version` to confirm it installed correctly.

**I'm not receiving the login email**
- Check your spam folder.
- The code expires after 10 minutes — request a new one if it has expired.

---

## Roadmap

- [x] Modular Electron shell, SeorexTech-branded
- [x] ZIP-based module installer (enable / disable / uninstall)
- [x] Library with one-click launch
- [x] Download manager (queue, pause/resume, cancel)
- [x] Auto-updater
- [x] Python bridge + silent Python 3.12 auto-install
- [x] Email OTP authentication
- [x] Supabase user logging (upsert on login, last_seen tracking)
- [x] Ban system with Discord webhook alerts
- [x] Duplicate account detection (login vs signup redirect)
- [x] Enhanced diagnostics in settings
- [ ] Remote module marketplace
- [ ] Module signing and verification
- [ ] Theming engine
- [ ] Cloud sync / user profiles

---

## License

MIT (c) 2026 Seorex - see [LICENSE](LICENSE)

---

<div align="center">

Built by **SeorexTech** — [seorextech.com](https://seorextech.com)

</div>
