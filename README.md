# AutoLogin 3.0.2
* Requires [Nampower](https://gitea.com/avitasia/nampower/releases) `>= 3.2.0` (preferred) or [SuperWoW](https://github.com/balakethelock/SuperWoW/) `>= 1.4`

Patch for Vanilla WoW client that adds account saving and order features and character ordering and auto-login features.

Resized to original 4 account slot in order to keep Main Menu unchanged.

> This patch saves your login info into `\Imports\logins.txt` so keep in mind that it will **contain your passwords** (encrypted if using Nampower) and thus you should think before sharing this file with someone else.

> This patch is a replacement for patches like [vanilla-autologin](https://github.com/Haaxor1689/vanilla-autologin) and [Reorder-Patch](https://github.com/Otari98/Reorder-Patch), remove them before using it.

## Password Encryption

With Nampower, saved passwords can be encrypted using Windows DPAPI. To enable this:

1. Set an environment variable `WOW_ENCRYPTION_KEY` to any value (just don't make it really short). You don't need to remember it after setting it as passwords can not be unencrypted.
2. The Encrypt toggle on the login screen will become active.
3. Passwords are encrypted automatically when you log into each account.

### Environment Variable Setup

**Windows**
1. Open the Start Menu and search for "env".
2. Click on "Edit the system environment variables".
3. In the System Properties window, click on the "Environment Variables" button.
4. Click "New" under "System variables".
5. Enter `WOW_ENCRYPTION_KEY` as the variable name and your desired key as the value.
6. Click "OK" to save.

**Linux / macOS**

Add the following to your shell profile (`~/.bashrc`, `~/.zshrc`):
```bash
export WOW_ENCRYPTION_KEY="your_desired_encryption_key"
```
Then run `source ~/.bashrc` (or the appropriate profile file) to apply.

## Features

- Adds an Accounts selection panel to the login screen (4 accounts per page)
- Select an account to enter its login info (double-click to login directly)
- Automatically adds new accounts to the list
- Accounts and characters can be manually arranged
- Login-to-last-character buttons
- Streamer mode to reduce information leakage
- Password encryption toggle (Nampower only)
- Compatible with Turtle WoW's side menu buttons (Armory, Database, Community, etc.)

## Installation

Download the MPQ and place in your Vanilla WoW data folder.

NOTE: You need to have patched WoW.exe that allows glues patches.

OR

Download the repo and place the files in your WoW folder like this:
```
Data\Interface\GlueXML\GlueXML.toc
Data\Interface\GlueXML\AutoLogin.xml
Data\Interface\GlueXML\AutoLogin.lua
```

## Changelog

### 3.0.2
Fix for Linux/Wine: clear focus after UI updates so the glue screen, side buttons (Armory, Community, etc.) can receive subsequent clicks.

### 3.0.1
- Unhid side menu buttons (Turtle Wow, Armory, Database, Community, Cinematics, etc.) on the login screen
- Reduced account panel from 9 slots to 4 slots per page to prevent overlap with side menu buttons

---

* Created for Weird Vibes
* Original idea by [Haaxor1689](https://github.com/Haaxor1689)
* Inspiration from [Otari98](https://github.com/Otari98/Reorder-Patch)
